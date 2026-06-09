# _CxxThrowException_0

- ea: `0x140001f42`
- end: `0x140001f48`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x140001d54`
- `0x1400046f0`
- `0x140005140`
- `0x140005fd4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x140001f42`

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
0x140001f42  jmp     cs:__imp__CxxThrowException
```
