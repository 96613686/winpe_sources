# _CxxThrowException_0

- ea: `0x14000dd7c`
- end: `0x14000dd82`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x14000732c`
- `0x140007590`
- `0x1400076e0`
- `0x1400081e0`
- `0x14000e07f`
- `0x14000e7b8`
- `0x14000e831`
- `0x14000e8b6`
- `0x14000e8dc`
- `0x14000eafd`
- `0x14000eb23`
- `0x14000eb59`
- `0x14000edd4`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x14000dd7c`

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
0x14000dd7c  jmp     cs:__imp__CxxThrowException
```
