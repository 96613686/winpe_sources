# HttpExtensionProc

- ea: `0x180001090`
- end: `0x180001095`
- name: `HttpExtensionProc`
- size: `5`
- prototype: `DWORD __stdcall(EXTENSION_CONTROL_BLOCK *pECB)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180001121`

## pseudocode

```c
// attributes: thunk
DWORD __stdcall HttpExtensionProc(EXTENSION_CONTROL_BLOCK *pECB)
{
  return AspNetHttpExtensionProc_0(pECB);
}

```

## disassembly

```asm
0x180001090  jmp     AspNetHttpExtensionProc_0
```
