# LocalAlloc

- ea: `0x180020880`
- end: `0x180020a56`
- name: `LocalAlloc`
- size: `470`
- prototype: `HLOCAL __stdcall(UINT uFlags, SIZE_T uBytes)`
- caller_count: `64`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800044e0`
- `0x180004d1c`
- `0x180004f90`
- `0x180007164`
- `0x180008db0`
- `0x18000a320`
- `0x18000b220`
- `0x18000b370`
- `0x18001eec0`
- `0x18001f680`
- `0x18001fec0`
- `0x18001ff60`
- `0x180020560`
- `0x180020b70`
- `0x1800224a0`
- `0x1800226f0`
- `0x180022940`
- `0x180022ec0`
- `0x180023490`
- `0x180024290`
- `0x180025180`
- `0x1800258a0`
- `0x180026490`
- `0x180026d90`
- `0x180026ea0`
- `0x18002af0c`
- `0x180030eac`
- `0x1800314f0`
- `0x1800576c0`
- `0x180079c50`
- `0x180094e40`
- `0x180094ef0`
- `0x180095960`
- `0x1800a4490`
- `0x1800a5530`
- `0x1800a7028`
- `0x1800a7118`
- `0x1800a75c4`
- `0x1800a7858`
- `0x1800ac950`
- `0x1800ad410`
- `0x1800ad720`
- `0x1800c66c0`
- `0x1800dd990`
- `0x1800ddbf0`
- `0x1800e26f0`
- `0x1800e6750`
- `0x1800e67d0`
- `0x1800e6964`
- `0x1800eb760`

## callees

- `0x1800134a0`
- `0x180020880`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x1800208e7`
- `ntdll!RtlSetLastWin32Error` at `0x1800208f4`
- `ntdll!RtlSetLastWin32Error` at `0x1800209c1`
- `ntdll!RtlSetLastWin32Error` at `0x1800209d8`
- `ntdll!RtlSetLastWin32Error` at `0x1800208e7`
- `ntdll!RtlSetLastWin32Error` at `0x1800208f4`
- `ntdll!RtlSetLastWin32Error` at `0x1800209c1`
- `ntdll!RtlSetLastWin32Error` at `0x1800209d8`
- `ntdll!RtlAllocateHandle` at `0x18002092e`
- `ntdll!RtlAllocateHandle` at `0x18002092e`
- `ntdll!RtlFreeHandle` at `0x1800209ae`
- `ntdll!RtlFreeHandle` at `0x1800209ae`
- `ntdll!RtlSetUserValueHeap` at `0x180020998`
- `ntdll!RtlSetUserValueHeap` at `0x180020998`
- `ntdll!RtlUnlockHeap` at `0x180020a11`
- `ntdll!RtlUnlockHeap` at `0x180020a11`
- `ntdll!RtlUnlockHeap` at `0x1801893d5`
- `ntdll!RtlLockHeap` at `0x18002091e`
- `ntdll!RtlLockHeap` at `0x18002091e`
- `ntdll!RtlAllocateHeap` at `0x1800208c3`
- `ntdll!RtlAllocateHeap` at `0x180020971`
- `ntdll!RtlAllocateHeap` at `0x1800208c3`
- `ntdll!RtlAllocateHeap` at `0x180020971`

## pseudocode

```c

```
