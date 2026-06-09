# _CxxThrowException_0

- ea: `0x180007469`
- end: `0x18000746f`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x18000247c`
- `0x180007731`
- `0x18000776d`
- `0x18000782c`
- `0x18000785d`
- `0x18000788e`
- `0x1800078bf`
- `0x180007902`
- `0x18000792c`
- `0x18000797a`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180007469`

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
0x180007469  jmp     cs:__imp__CxxThrowException
```
