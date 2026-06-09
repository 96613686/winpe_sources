# _CxxThrowException_0

- ea: `0x180002876`
- end: `0x18000287c`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `7`
- callee_count: `0`
- tags: ``

## callers

- `0x180002804`
- `0x18000282c`
- `0x18000485c`
- `0x180004a10`
- `0x180004ba0`
- `0x1800052d0`
- `0x180007a24`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180002876`

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
0x180002876  jmp     cs:__imp__CxxThrowException
```
