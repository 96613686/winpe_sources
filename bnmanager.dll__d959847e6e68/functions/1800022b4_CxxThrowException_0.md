# _CxxThrowException_0

- ea: `0x1800022b4`
- end: `0x1800022ba`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x180002140`
- `0x180004ae8`
- `0x18000a500`
- `0x18000b370`
- `0x18000bbd0`
- `0x18000bde4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x1800022b4`

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
0x1800022b4  jmp     cs:__imp__CxxThrowException
```
