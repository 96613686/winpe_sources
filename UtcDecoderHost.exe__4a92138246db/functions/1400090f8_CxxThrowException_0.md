# _CxxThrowException_0

- ea: `0x1400090f8`
- end: `0x1400090fe`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `8`
- callee_count: `0`
- tags: ``

## callers

- `0x140008efc`
- `0x14000c06c`
- `0x14000c240`
- `0x14000c390`
- `0x14000c400`
- `0x14000ced0`
- `0x14000d3d4`
- `0x14000d918`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x1400090f8`

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
0x1400090f8  jmp     cs:__imp__CxxThrowException
```
