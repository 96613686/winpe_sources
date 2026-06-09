# _CxxThrowException_0

- ea: `0x14000224c`
- end: `0x140002252`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `6`
- callee_count: `0`
- tags: ``

## callers

- `0x140002054`
- `0x1400072b0`
- `0x140008210`
- `0x14000af2c`
- `0x14000b0a8`
- `0x14000b2d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x14000224c`

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
0x14000224c  jmp     cs:__imp__CxxThrowException
```
