# _CxxThrowException_0

- ea: `0x14000a21a`
- end: `0x14000a220`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x14000519c`
- `0x1400053e0`
- `0x140005530`
- `0x140005e00`
- `0x14000a90c`
- `0x14000aa30`
- `0x14000aa56`
- `0x14000aa7c`
- `0x14000ab44`
- `0x14000ab6a`
- `0x14000abca`
- `0x14000ac42`
- `0x14000ade8`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x14000a21a`

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
0x14000a21a  jmp     cs:__imp__CxxThrowException
```
