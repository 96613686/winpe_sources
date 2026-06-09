# _CxxThrowException_0

- ea: `0x140003df4`
- end: `0x140003dfa`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140003bf4`
- `0x140003c1c`
- `0x1400082f0`
- `0x140008db0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x140003df4`

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
0x140003df4  jmp     cs:__imp__CxxThrowException
```
