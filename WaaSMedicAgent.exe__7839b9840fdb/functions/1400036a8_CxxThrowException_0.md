# _CxxThrowException_0

- ea: `0x1400036a8`
- end: `0x1400036ae`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140003180`
- `0x140006410`
- `0x140006ef0`
- `0x1400073e4`
- `0x14000b1ec`
- `0x14000b218`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x1400036a8`

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
0x1400036a8  jmp     cs:__imp__CxxThrowException
```
