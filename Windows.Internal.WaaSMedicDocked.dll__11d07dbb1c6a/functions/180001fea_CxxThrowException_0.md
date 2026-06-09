# _CxxThrowException_0

- ea: `0x180001fea`
- end: `0x180001ff0`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `10`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e98`
- `0x1800048b0`
- `0x180005300`
- `0x1800071d0`
- `0x180008230`
- `0x180009104`
- `0x18000972c`
- `0x1800097e0`
- `0x180009c90`
- `0x180009f70`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x180001fea`

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
0x180001fea  jmp     cs:__imp__CxxThrowException
```
