# _CxxThrowException_0

- ea: `0x180002f94`
- end: `0x180002f9a`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180002e50`
- `0x1800055bc`
- `0x180005800`
- `0x180005950`
- `0x1800063c0`
- `0x180009e98`
- `0x18000b278`
- `0x18000b2a0`
- `0x18000b2fc`
- `0x18000b33c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180002f94`

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
0x180002f94  jmp     cs:__imp__CxxThrowException
```
