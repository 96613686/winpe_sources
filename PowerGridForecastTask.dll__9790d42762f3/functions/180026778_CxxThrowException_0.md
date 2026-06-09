# _CxxThrowException_0

- ea: `0x180026778`
- end: `0x18002677e`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `60`
- callee_count: `0`
- tags: ``

## callers

- `0x1800022c8`
- `0x1800022f0`
- `0x18000231c`
- `0x180002c3c`
- `0x180002d80`
- `0x180002ec4`
- `0x180003008`
- `0x18000314c`
- `0x1800095bc`
- `0x180009700`
- `0x180009844`
- `0x180009988`
- `0x180009acc`
- `0x180009c10`
- `0x180009d54`
- `0x180009e98`
- `0x180009fdc`
- `0x18000a120`
- `0x18000a264`
- `0x18000a3a8`
- `0x18000a4ec`
- `0x18000a630`
- `0x18000a774`
- `0x18000a8b8`
- `0x18000a9fc`
- `0x18000ab40`
- `0x18000ac84`
- `0x18000adc8`
- `0x18000af0c`
- `0x18000b050`
- `0x18000b194`
- `0x18000b2d8`
- `0x18000b41c`
- `0x18000b560`
- `0x18001cc84`
- `0x18001cdc8`
- `0x18001cf0c`
- `0x18001d050`
- `0x18001d194`
- `0x18001d2d8`
- `0x18001d41c`
- `0x18001d560`
- `0x18002dca0`
- `0x18002f1d0`
- `0x18003178c`
- `0x180034d18`
- `0x180035391`
- `0x180035473`
- `0x18003574c`
- `0x180035775`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180026778`

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
0x180026778  jmp     cs:__imp__CxxThrowException
```
