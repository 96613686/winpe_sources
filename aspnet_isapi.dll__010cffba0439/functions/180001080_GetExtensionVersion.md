# GetExtensionVersion

- ea: `0x180001080`
- end: `0x180001085`
- name: `GetExtensionVersion`
- size: `5`
- prototype: `BOOL __stdcall(HSE_VERSION_INFO *pVer)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001115`

## pseudocode

```c
// attributes: thunk
BOOL __stdcall GetExtensionVersion(HSE_VERSION_INFO *pVer)
{
  return AspNetGetExtensionVersion_0();
}

```

## disassembly

```asm
0x180001080  jmp     AspNetGetExtensionVersion_0
```
