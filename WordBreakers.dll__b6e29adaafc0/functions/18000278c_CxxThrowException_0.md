# _CxxThrowException_0

- ea: `0x18000278c`
- end: `0x180002792`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180002038`
- `0x180002060`
- `0x18000208c`
- `0x1800058a0`
- `0x180006190`
- `0x18000bad4`
- `0x18000bb19`
- `0x18000bb3f`
- `0x18000bbb7`
- `0x18000bbe0`
- `0x18000bbfd`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000278c`

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
0x18000278c  jmp     cs:__imp__CxxThrowException
```
