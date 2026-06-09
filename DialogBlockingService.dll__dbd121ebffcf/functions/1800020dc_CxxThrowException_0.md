# _CxxThrowException_0

- ea: `0x1800020dc`
- end: `0x1800020e2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180001cc4`
- `0x180006320`
- `0x180006660`
- `0x1800067b0`
- `0x180007500`
- `0x180007d74`
- `0x18000a23c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x1800020dc`

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
0x1800020dc  jmp     cs:__imp__CxxThrowException
```
