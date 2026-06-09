# _CxxThrowException_0

- ea: `0x14000220c`
- end: `0x140002212`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140001bb8`
- `0x140001be0`
- `0x140001c0c`
- `0x1400049f4`
- `0x140004bb0`
- `0x140004d40`
- `0x1400053e0`
- `0x140009920`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x14000220c`

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
0x14000220c  jmp     cs:__imp__CxxThrowException
```
