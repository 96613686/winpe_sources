# VsmmWheapBadPageBitmapSetup

- ea: `0x1400c8350`
- end: `0x1400c844a`
- name: `VsmmWheapBadPageBitmapSetup`
- size: `250`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x140083714`

## callees

- `0x14002f724`
- `0x1400c8350`

## import_xrefs

- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400c838c`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400c838c`
- `ntoskrnl!MmFreePagesFromMdl` at `0x1400c8410`
- `ntoskrnl!MmFreePagesFromMdl` at `0x1400c8410`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400c83db`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400c83db`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c8421`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400c8421`

## pseudocode

```c

```
