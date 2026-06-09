# _CxxThrowException_0

- ea: `0x1400022f8`
- end: `0x1400022fe`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140002120`
- `0x140002e80`
- `0x1400049cc`
- `0x14000a4c0`
- `0x14000b320`
- `0x14000c688`
- `0x14000ca7c`
- `0x14000ebd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x1400022f8`

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
0x1400022f8  jmp     cs:__imp__CxxThrowException
```
