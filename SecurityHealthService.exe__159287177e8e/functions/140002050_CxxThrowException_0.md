# _CxxThrowException_0

- ea: `0x140002050`
- end: `0x140002056`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x140001e80`
- `0x14000b1a0`
- `0x14000bef0`
- `0x14000d15c`
- `0x14000d688`
- `0x14000d9c8`
- `0x14000e508`
- `0x14000e5bc`
- `0x140011498`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x140002050`

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
0x140002050  jmp     cs:__imp__CxxThrowException
```
