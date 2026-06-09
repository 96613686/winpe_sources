# _CxxThrowException_0

- ea: `0x1800021a0`
- end: `0x1800021a6`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `15`
- callee_count: `0`
- tags: ``

## callers

- `0x180002050`
- `0x180005c40`
- `0x180006c30`
- `0x180006d80`
- `0x180007bf0`
- `0x180009e3c`
- `0x18000a88c`
- `0x18000aa30`
- `0x18000c514`
- `0x18000c7c4`
- `0x18000c89c`
- `0x18000c968`
- `0x18000d8f8`
- `0x18000d93c`
- `0x18000d9dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x1800021a0`

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
0x1800021a0  jmp     cs:__imp__CxxThrowException
```
