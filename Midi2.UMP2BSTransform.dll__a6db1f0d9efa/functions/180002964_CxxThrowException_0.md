# _CxxThrowException_0

- ea: `0x180002964`
- end: `0x18000296a`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180002570`
- `0x1800047f8`
- `0x180007710`
- `0x180008210`
- `0x18000aad4`
- `0x18000caf0`
- `0x18000dd20`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180002964`

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
0x180002964  jmp     cs:__imp__CxxThrowException
```
