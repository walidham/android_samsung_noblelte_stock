################################################################################
1. How to Build
	- get Toolchain
		From android git serveru, codesourcery and etc ..
			- gcc/linux-x86/aarch64/aarch64-linux-android-4.9/bin/aarch64-linux-android-

	- edit Makefile
		edit "CROSS_COMPILE" to right toolchain path(You downloaded).
			EX)  CROSS_COMPILE= $(android platform directory you download)/android/prebuilts/gcc/linux-x86/aarch64/aarch64-linux-android-4.9/bin/aarch64-linux-android-
			Ex)  CROSS_COMPILE=/usr/local/toolchain/gcc/linux-x86/aarch64/aarch64-linux-android-4.9/bin/aarch64-linux-android-		// check the location of toolchain

	- to Build
		$ export ANDROID_MAJOR_VERSION=n
		$ make ARCH=arm64 exynos7420-noblelte_mea_jv_defconfig
		$ make ARCH=arm64
2. Output files
	- Kernel : arch/arm/boot/zImage
	- module : drivers/*/*.ko

3. How to Clean
	$ make clean
################################################################################

export ANDROID_MAJOR_VERSION=n
make O=out ARCH=arm64 exynos7420-noblelte_mea_jv_defconfig
make -j$(nproc --all) O=out ARCH=arm64