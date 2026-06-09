# HCI_HandleDisconnectionComplete(HCI_INTERFACE *,_HCI_CONNECTION *,uchar,uchar,_GUID *)

- ea: `0x140044880`
- end: `0x1400457eb`
- name: `?HCI_HandleDisconnectionComplete@@YAXPEAUHCI_INTERFACE@@PEAU_HCI_CONNECTION@@EEPEAU_GUID@@@Z`
- size: `3947`
- prototype: `void __usercall(struct HCI_INTERFACE *@<rcx>, struct _HCI_CONNECTION *@<rdx>, unsigned __int8@<r8b>, unsigned __int8@<r9b>, struct _GUID *)`
- caller_count: `4`
- callee_count: `45`
- tags: `broker_com_uri`

## callers

- `0x140038440`
- `0x140041230`
- `0x140110e10`
- `0x140120774`

## callees

- `0x14000113c`
- `0x1400012bc`
- `0x14000175c`
- `0x140001930`
- `0x1400043d0`
- `0x140005504`
- `0x140005608`
- `0x140005b4c`
- `0x140005c04`
- `0x140007210`
- `0x1400118f4`
- `0x140028938`
- `0x14002dee0`
- `0x14002fb2c`
- `0x140031ef8`
- `0x140035fc8`
- `0x14003b1cc`
- `0x14003b220`
- `0x14003c820`
- `0x14003c8cc`
- `0x14003c94c`
- `0x14003cb4c`
- `0x14003d5e4`
- `0x14003db44`
- `0x14003f26c`
- `0x140040834`
- `0x140044880`
- `0x140045e60`
- `0x140048140`
- `0x140048280`
- `0x14004b7e4`
- `0x14004b86c`
- `0x14004c260`
- `0x1400535e8`
- `0x1400a5498`
- `0x1400a5550`
- `0x1400a6b84`
- `0x1400b0a1c`
- `0x1400ba080`
- `0x14014ee20`
- `0x140161a44`
- `0x140161d7c`
- `0x14016241c`
- `0x140165540`
- `0x140165940`

## import_xrefs

- `ntoskrnl!EtwTelemetryCoverageReport` at `0x14004568f`
- `ntoskrnl!EtwTelemetryCoverageReport` at `0x14004568f`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x140044aac`
- `ntoskrnl!ExSystemTimeToLocalTime` at `0x140044aac`
- `ntoskrnl!_ui64tow_s` at `0x140044c39`
- `ntoskrnl!_ui64tow_s` at `0x140044c39`
- `ntoskrnl!KeCancelTimer` at `0x140045110`
- `ntoskrnl!KeCancelTimer` at `0x140045110`
- `ntoskrnl!KeSetEvent` at `0x14004523e`
- `ntoskrnl!KeSetEvent` at `0x14004523e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140044f92`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400452fa`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140044f92`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400452fa`
- `ntoskrnl!KeReleaseSpinLock` at `0x140045024`
- `ntoskrnl!KeReleaseSpinLock` at `0x140045217`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004565e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140045024`
- `ntoskrnl!KeReleaseSpinLock` at `0x140045217`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004565e`

## pseudocode

```c

```
