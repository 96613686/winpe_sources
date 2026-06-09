# _CxxThrowException_0

- ea: `0x140001f9a`
- end: `0x140001fa0`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140001f4c`
- `0x140001f74`
- `0x14000451c`
- `0x140004760`
- `0x1400048b0`
- `0x140005330`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x140001f9a`

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
0x140001f9a  jmp     cs:__imp__CxxThrowException
```
