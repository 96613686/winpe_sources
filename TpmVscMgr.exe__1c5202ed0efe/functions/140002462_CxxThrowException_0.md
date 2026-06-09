# _CxxThrowException_0

- ea: `0x140002462`
- end: `0x140002468`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x140002280`
- `0x1400049ec`
- `0x140004c30`
- `0x140004d80`
- `0x1400057d0`
- `0x140009fa4`
- `0x14000b04c`
- `0x14000cf20`
- `0x14000cf5c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x140002462`

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
0x140002462  jmp     cs:__imp__CxxThrowException
```
