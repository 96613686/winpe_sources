# LocalFree

- ea: `0x1800220f0`
- end: `0x180022217`
- name: `LocalFree`
- size: `295`
- prototype: `HLOCAL __stdcall(HLOCAL hMem)`
- caller_count: `105`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180003880`
- `0x18000394c`
- `0x180004560`
- `0x180004700`
- `0x180005210`
- `0x180005b50`
- `0x180006714`
- `0x180006e80`
- `0x180007164`
- `0x1800087b0`
- `0x180008db0`
- `0x180009610`
- `0x18000974c`
- `0x18000a320`
- `0x18000b220`
- `0x18000b370`
- `0x18001eec0`
- `0x18001f680`
- `0x18001ff60`
- `0x180020560`
- `0x180020b70`
- `0x1800224a0`
- `0x1800226f0`
- `0x180022940`
- `0x180022ec0`
- `0x180023380`
- `0x180023490`
- `0x180023760`
- `0x180023b80`
- `0x180024290`
- `0x180025180`
- `0x1800258a0`
- `0x180026490`
- `0x180026d90`
- `0x180026ea0`
- `0x180027bf0`
- `0x180028d1c`
- `0x180028ee0`
- `0x18002af0c`
- `0x18002bf64`
- `0x18002d000`
- `0x18002fd98`
- `0x1800307a0`
- `0x180030cf4`
- `0x180030eac`
- `0x1800314f0`
- `0x180049460`
- `0x1800496e0`
- `0x1800576c0`
- `0x18006995c`

## callees

- `0x1800134a0`
- `0x1800220f0`

## import_xrefs

- `ntdll!RtlSetLastWin32Error` at `0x180022133`
- `ntdll!RtlSetLastWin32Error` at `0x1800221cf`
- `ntdll!RtlSetLastWin32Error` at `0x1800221dc`
- `ntdll!RtlSetLastWin32Error` at `0x180022133`
- `ntdll!RtlSetLastWin32Error` at `0x1800221cf`
- `ntdll!RtlSetLastWin32Error` at `0x1800221dc`
- `ntdll!RtlIsValidHandle` at `0x180022175`
- `ntdll!RtlIsValidHandle` at `0x180022175`
- `ntdll!RtlFreeHandle` at `0x180022192`
- `ntdll!RtlFreeHandle` at `0x180022192`
- `ntdll!RtlUnlockHeap` at `0x1800221fe`
- `ntdll!RtlUnlockHeap` at `0x1800221fe`
- `ntdll!RtlUnlockHeap` at `0x180189445`
- `ntdll!RtlLockHeap` at `0x180022163`
- `ntdll!RtlLockHeap` at `0x180022163`
- `ntdll!RtlFreeHeap` at `0x180022119`
- `ntdll!RtlFreeHeap` at `0x1800221b7`
- `ntdll!RtlFreeHeap` at `0x180022119`
- `ntdll!RtlFreeHeap` at `0x1800221b7`

## pseudocode

```c

```
