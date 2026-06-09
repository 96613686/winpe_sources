# _CxxThrowException_0

- ea: `0x180003004`
- end: `0x18000300a`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180002be4`
- `0x180002c0c`
- `0x180004eb8`
- `0x180007df0`
- `0x180008910`
- `0x18000d7b8`
- `0x180010094`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180003004`

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
0x180003004  jmp     cs:__imp__CxxThrowException
```
