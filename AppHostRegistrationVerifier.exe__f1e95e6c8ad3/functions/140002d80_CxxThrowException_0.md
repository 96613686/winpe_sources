# _CxxThrowException_0

- ea: `0x140002d80`
- end: `0x140002d86`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x140002b18`
- `0x140002b40`
- `0x1400066dc`
- `0x140006890`
- `0x140006a20`
- `0x1400071f0`
- `0x1400076e8`
- `0x140007a2c`
- `0x140007c54`
- `0x14000989c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x140002d80`

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
0x140002d80  jmp     cs:__imp__CxxThrowException
```
