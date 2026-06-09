# _CxxThrowException_0

- ea: `0x1800020f0`
- end: `0x1800020f6`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x180001f98`
- `0x1800030c0`
- `0x180005ee0`
- `0x180006ed0`
- `0x180007020`
- `0x180007090`
- `0x180007f00`
- `0x18000b0cc`
- `0x18000b3ac`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_CxxThrowException` at `0x1800020f0`

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
0x1800020f0  jmp     cs:__imp__CxxThrowException
```
