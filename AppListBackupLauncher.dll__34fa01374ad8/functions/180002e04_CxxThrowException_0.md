# _CxxThrowException_0

- ea: `0x180002e04`
- end: `0x180002e0a`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x180002c60`
- `0x18000a47c`
- `0x18000bdc0`
- `0x18000bf10`
- `0x18000bf80`
- `0x18000d6f0`
- `0x18000e89c`
- `0x18000ec24`
- `0x18000f09c`
- `0x18000f214`
- `0x18000f4f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180002e04`

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
0x180002e04  jmp     cs:__imp__CxxThrowException
```
