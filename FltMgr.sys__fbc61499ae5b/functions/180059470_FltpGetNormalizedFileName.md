# FltpGetNormalizedFileName

- ea: `0x180059470`
- end: `0x1800599f4`
- name: `FltpGetNormalizedFileName`
- size: `1412`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path`

## callers

- `0x180058a30`
- `0x180058e80`

## callees

- `0x180009f20`
- `0x180013f50`
- `0x1800148b0`
- `0x1800248e0`
- `0x180058380`
- `0x180059470`
- `0x180059a00`
- `0x18005a2e0`
- `0x18005aa30`
- `0x18005b880`
- `0x18006e9a0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x1800595d9`
- `ntoskrnl!ObfDereferenceObject` at `0x1800595d9`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800597d0`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800597d0`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180059819`
- `ntoskrnl!RtlEqualUnicodeString` at `0x180059819`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x180059995`
- `ntoskrnl!KeExpandKernelStackAndCalloutEx` at `0x180059995`
- `ntoskrnl!ZwClose` at `0x1800595f5`
- `ntoskrnl!ZwClose` at `0x1800595f5`

## string_xrefs

- `0x1800596ae`: `minkernel\fs\filtermgr\filter\namecachesup.c`
- `0x1800596e5`: `minkernel\fs\filtermgr\filter\namecachesup.c`

## pseudocode

```c

```
