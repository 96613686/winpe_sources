# _CxxThrowException_0

- ea: `0x140001e9c`
- end: `0x140001ea2`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x140001368`
- `0x1400013a8`
- `0x1400013d4`
- `0x1400033b8`
- `0x140003408`
- `0x140003458`
- `0x1400034a8`
- `0x140004454`
- `0x140004574`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x140001e9c`

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
0x140001e9c  jmp     cs:__imp__CxxThrowException
```
