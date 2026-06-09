# _CxxThrowException_0

- ea: `0x18000227c`
- end: `0x180002282`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `13`
- callee_count: `0`
- tags: ``

## callers

- `0x180001048`
- `0x180001444`
- `0x180001580`
- `0x1800015c0`
- `0x180001600`
- `0x1800016a4`
- `0x180001700`
- `0x1800035a4`
- `0x180003700`
- `0x180009682`
- `0x1800096e7`
- `0x180009a23`
- `0x180009a51`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000227c`

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
0x18000227c  jmp     cs:__imp__CxxThrowException
```
