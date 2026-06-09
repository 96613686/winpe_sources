# _CxxThrowException_0

- ea: `0x180002a34`
- end: `0x180002a3a`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `11`
- callee_count: `0`
- tags: ``

## callers

- `0x1800028f0`
- `0x18000701c`
- `0x180008230`
- `0x180008380`
- `0x1800092e0`
- `0x18000ea3c`
- `0x18001088c`
- `0x180011d50`
- `0x1800128d0`
- `0x18001879f`
- `0x18001881f`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180002a34`

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
0x180002a34  jmp     cs:__imp__CxxThrowException
```
