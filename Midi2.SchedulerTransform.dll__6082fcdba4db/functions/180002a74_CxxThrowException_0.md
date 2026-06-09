# _CxxThrowException_0

- ea: `0x180002a74`
- end: `0x180002a7a`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002680`
- `0x180004908`
- `0x180007830`
- `0x180008330`
- `0x18000c178`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180002a74`

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
0x180002a74  jmp     cs:__imp__CxxThrowException
```
