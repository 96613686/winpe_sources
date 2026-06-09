# _CxxThrowException_0

- ea: `0x18000255c`
- end: `0x180002562`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180001588`
- `0x1800015c8`
- `0x1800015f4`
- `0x180006a80`
- `0x18000c707`
- `0x18000cb84`
- `0x18000cbaa`
- `0x18000cdfe`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000255c`

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
0x18000255c  jmp     cs:__imp__CxxThrowException
```
