# FreeTestMemory(void *)

- ea: `0x18000ee10`
- end: `0x18000ee17`
- name: `?FreeTestMemory@@YAXPEAX@Z`
- size: `7`
- prototype: `void __stdcall(LPVOID pv)`
- caller_count: `26`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c4b0`
- `0x18000ca40`
- `0x18000def4`
- `0x18000e010`
- `0x18000e10c`
- `0x18000e3b8`
- `0x18000e49c`
- `0x18000e594`
- `0x18000e6a8`
- `0x18000ea24`
- `0x180010e0f`
- `0x180010e49`
- `0x180010e92`
- `0x180010ecd`
- `0x180010f12`
- `0x180010f54`
- `0x180010f9c`
- `0x18001101e`
- `0x1800111a1`
- `0x1800111ec`
- `0x180011249`
- `0x180011289`
- `0x18001130b`
- `0x18001134d`
- `0x180011383`
- `0x180011461`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ee10`

## pseudocode

```c
// attributes: thunk
void __stdcall FreeTestMemory(LPVOID pv)
{
  CoTaskMemFree(pv);
}

```

## disassembly

```asm
0x18000ee10  jmp     cs:__imp_CoTaskMemFree
```
