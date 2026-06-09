# _CxxThrowException_0

- ea: `0x1800021dc`
- end: `0x1800021e2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180001398`
- `0x1800013d8`
- `0x180001404`
- `0x180008854`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1800021dc`

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
0x1800021dc  jmp     cs:__imp__CxxThrowException
```
