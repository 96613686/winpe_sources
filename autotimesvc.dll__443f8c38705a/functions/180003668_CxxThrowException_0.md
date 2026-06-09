# _CxxThrowException_0

- ea: `0x180003668`
- end: `0x18000366e`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x180003210`
- `0x180003238`
- `0x180008cc0`
- `0x180008fb0`
- `0x180009140`
- `0x180009ef0`
- `0x18000a694`
- `0x18000a6d0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180003668`

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
0x180003668  jmp     cs:__imp__CxxThrowException
```
