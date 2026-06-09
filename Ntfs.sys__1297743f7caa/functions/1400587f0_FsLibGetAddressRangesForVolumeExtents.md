# FsLibGetAddressRangesForVolumeExtents

- ea: `0x1400587f0`
- end: `0x140058c07`
- name: `FsLibGetAddressRangesForVolumeExtents`
- size: `1047`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64, int)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400d07b4`
- `0x14011afe8`

## callees

- `0x1400587f0`
- `0x1400b4238`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x140058872`
- `ntoskrnl!DbgPrintEx` at `0x1400588c1`
- `ntoskrnl!DbgPrintEx` at `0x1400588f4`
- `ntoskrnl!DbgPrintEx` at `0x140058975`
- `ntoskrnl!DbgPrintEx` at `0x1400589ed`
- `ntoskrnl!DbgPrintEx` at `0x140058a69`
- `ntoskrnl!DbgPrintEx` at `0x140058b0a`
- `ntoskrnl!DbgPrintEx` at `0x140058b54`
- `ntoskrnl!DbgPrintEx` at `0x140058b8c`
- `ntoskrnl!DbgPrintEx` at `0x140058bb0`
- `ntoskrnl!DbgPrintEx` at `0x140058bd7`
- `ntoskrnl!DbgPrintEx` at `0x140058872`
- `ntoskrnl!DbgPrintEx` at `0x1400588c1`
- `ntoskrnl!DbgPrintEx` at `0x1400588f4`
- `ntoskrnl!DbgPrintEx` at `0x140058975`
- `ntoskrnl!DbgPrintEx` at `0x1400589ed`
- `ntoskrnl!DbgPrintEx` at `0x140058a69`
- `ntoskrnl!DbgPrintEx` at `0x140058b0a`
- `ntoskrnl!DbgPrintEx` at `0x140058b54`
- `ntoskrnl!DbgPrintEx` at `0x140058b8c`
- `ntoskrnl!DbgPrintEx` at `0x140058bb0`
- `ntoskrnl!DbgPrintEx` at `0x140058bd7`

## string_xrefs

- `0x140058859`: `FsLibGetAddressRangesForVolumeExtents: Begin DeviceObject: %p, Irp: %p, DsmBuffer: %p SizeOfDsm: 0x%x,ExtentsDescriptor: %p, SizeOfExtentsDescriptor: 0x%x, MaxRuns: 0x%x\n`
- `0x140058af9`: `FsLibGetAddressRangesForVolumeExtents: StartAddress: 0x%I64x, Length: 0x%I64x, BasePage: 0x%I64x, PageCount: 0x%I64x, ExtentsDescriptorIndex: 0x%x\n`

## pseudocode

```c

```
