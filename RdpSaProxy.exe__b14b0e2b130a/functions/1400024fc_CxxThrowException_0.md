# _CxxThrowException_0

- ea: `0x1400024fc`
- end: `0x140002502`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001e78`
- `0x140001eb8`
- `0x140001ee4`
- `0x14000587a`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x1400024fc`

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
0x1400024fc  jmp     cs:__imp__CxxThrowException
```
