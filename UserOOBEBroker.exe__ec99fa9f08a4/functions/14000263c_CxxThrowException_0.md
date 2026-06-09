# _CxxThrowException_0

- ea: `0x14000263c`
- end: `0x140002642`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140001fe8`
- `0x140002010`
- `0x14000203c`
- `0x14000512c`
- `0x1400052f0`
- `0x140005440`
- `0x140005d50`
- `0x14000e69c`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x14000263c`

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
0x14000263c  jmp     cs:__imp__CxxThrowException
```
