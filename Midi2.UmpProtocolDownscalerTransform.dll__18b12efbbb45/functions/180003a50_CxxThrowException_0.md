# _CxxThrowException_0

- ea: `0x180003a50`
- end: `0x180003a56`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `21`
- callee_count: `0`
- tags: ``

## callers

- `0x1800038a8`
- `0x1800059d8`
- `0x1800088f0`
- `0x1800093f0`
- `0x18000c050`
- `0x18000c140`
- `0x18000c264`
- `0x18000dcc4`
- `0x18000de04`
- `0x18000df90`
- `0x18000e090`
- `0x18000e350`
- `0x18000f930`
- `0x180010e54`
- `0x180011044`
- `0x1800111c0`
- `0x180011290`
- `0x180011400`
- `0x1800116c4`
- `0x180011a4c`
- `0x180011d2c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180003a50`

## pseudocode

```c
// attributes: thunk
void __stdcall __noreturn CxxThrowException_0(void *pExceptionObject, _ThrowInfo *pThrowInfo)
{
  _CxxThrowException(pExceptionObject, pThrowInfo);
}

```

## disassembly

```asm
0x180003a50  jmp     cs:__imp__CxxThrowException
```
