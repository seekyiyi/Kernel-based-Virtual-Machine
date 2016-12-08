## Kernel-based-Virtual-Machine


KVM用於Linux內核中的虛擬化基礎設施，可以將Linux內核轉化為一個hypervisor。

KVM在具備#Intel VT#或#AMD-V#功能的x86平台上運行。

在不改變linux或windows鏡像的情況下同時執行多個虛擬機器，（它的意思是多個虛擬機器使用同一鏡像）並為每一個虛擬機器配置個性化硬件環境（網卡、磁盤、圖形介面卡……）同時KVM還能夠使用ksm技術幫助宿主伺服器節約記憶體。

KVM Model
![KVM Model] （http://benjr.tw/wp-content/uploads/2013/11/kvm_qemu01.png）

##QEMU 

![KVM & QEMU]（http://benjr.tw/wp-content/uploads/2013/11/kvm_qemu02.png）
#machine emulator (User mode emulation)

當 QEMU 當成 machine emulator 時它可以讓其他平台的作業系統 OSes 或是程式 Programes 比如是 ARM (一種常用於可攜式裝置的處理器) 系統可以直接執行在不同的平台上,比如是我們的桌機.使用的技術叫做 dynamic translation( JIT : just-in-time compilation http://en.wikipedia.org/wiki/Just-in-time_compilation ).藉此可以得到較佳的較能.

#virtualizer(System mode)

當 QEMU 當成 virtulizer 時, QEMU 幾乎可以以模擬的方式模擬出一台 PC ,包含了 CPU 以及其他的周邊裝置,所以透過這種方式,QEMU 可以模擬出不同的硬體出來,如 x86, AMD64, ARM, Alpha, ETRAX CRIS, MIPS, MicroBlaze 和 SPARC.不過目前可以執行 QEMU 的 virtualizer 只有 x86 x86_64 和 Power PC 詳細資料請參考 QEMU 的官方網頁 http://www.nongnu.org/qemu/status.html 也因此市面上的作業系統都可以模擬出來如 Linux, Solaris, Microsoft Windows, DOS, 以及 BSD.但是這種模擬的方式像是在 Host 的作業系統上跑應用程式(application),所以效能不是很好,所以在 Linux kernel 下的是使用另外一種的方式去模擬 KQEMU.
