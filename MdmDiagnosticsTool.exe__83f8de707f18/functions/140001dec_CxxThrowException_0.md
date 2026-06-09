# _CxxThrowException_0

- ea: `0x140001dec`
- end: `0x140001df2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x140001688`
- `0x1400016b0`
- `0x1400016dc`
- `0x140005c78`
- `0x140006410`
- `0x1400065b0`
- `0x140006cd0`
- `0x140009b90`
- `0x140009e86`
- `0x14000a23c`
- `0x14000a2a1`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x140001dec`

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
0x140001dec  jmp     cs:__imp__CxxThrowException
```
