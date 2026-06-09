# _CxxThrowException_0

- ea: `0x180007c58`
- end: `0x180007c5e`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x1800073c8`
- `0x1800073f0`
- `0x18000741c`
- `0x18000b330`
- `0x18000c0f0`
- `0x18000f4c6`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180007c58`

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
0x180007c58  jmp     cs:__imp__CxxThrowException
```
