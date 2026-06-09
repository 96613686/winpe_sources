# MspVolumeCheckpointScan(uchar *)

- ea: `0x140128f58`
- end: `0x140129641`
- name: `?MspVolumeCheckpointScan@@YAXPEAE@Z`
- size: `1769`
- prototype: `void(unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x1401279a0`

## callees

- `0x140090ea8`
- `0x1400ab230`
- `0x1400ab3e4`
- `0x1400cf638`
- `0x1400f7160`
- `0x1400f72fc`
- `0x140128f58`
- `0x140135fb0`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x140128f90`
- `ntdll!RtlAcquireResourceExclusive` at `0x140129006`
- `ntdll!RtlAcquireResourceExclusive` at `0x140128f90`
- `ntdll!RtlAcquireResourceExclusive` at `0x140129006`
- `ntdll!DbgPrintEx` at `0x14012914a`
- `ntdll!DbgPrintEx` at `0x1401291f9`
- `ntdll!DbgPrintEx` at `0x14012928e`
- `ntdll!DbgPrintEx` at `0x14012933e`
- `ntdll!DbgPrintEx` at `0x14012939e`
- `ntdll!DbgPrintEx` at `0x1401293e7`
- `ntdll!DbgPrintEx` at `0x140129452`
- `ntdll!DbgPrintEx` at `0x1401294be`
- `ntdll!DbgPrintEx` at `0x140129578`
- `ntdll!DbgPrintEx` at `0x14012914a`
- `ntdll!DbgPrintEx` at `0x1401291f9`
- `ntdll!DbgPrintEx` at `0x14012928e`
- `ntdll!DbgPrintEx` at `0x14012933e`
- `ntdll!DbgPrintEx` at `0x14012939e`
- `ntdll!DbgPrintEx` at `0x1401293e7`
- `ntdll!DbgPrintEx` at `0x140129452`
- `ntdll!DbgPrintEx` at `0x1401294be`
- `ntdll!DbgPrintEx` at `0x140129578`
- `ntdll!RtlReleaseResource` at `0x140128ff0`
- `ntdll!RtlReleaseResource` at `0x14012961c`
- `ntdll!RtlReleaseResource` at `0x140128ff0`
- `ntdll!RtlReleaseResource` at `0x14012961c`

## string_xrefs

- `0x140129448`: `ckpt: scheduling after crossing processed delete queue entry count threshold (%d)\n`
- `0x1401293dd`: `ckpt: scheduling due to delete pending being larger than (%d)%%\n`

## pseudocode

```c

```
