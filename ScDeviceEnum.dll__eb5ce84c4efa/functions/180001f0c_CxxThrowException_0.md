# _CxxThrowException_0

- ea: `0x180001f0c`
- end: `0x180001f12`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `19`
- callee_count: `0`
- tags: ``

## callers

- `0x1800015e8`
- `0x180001610`
- `0x18000163c`
- `0x1800046cc`
- `0x180004880`
- `0x180004a10`
- `0x1800050b0`
- `0x18000810c`
- `0x18001e758`
- `0x18001ea47`
- `0x18001eb2c`
- `0x18001eb53`
- `0x18001eb7c`
- `0x18001ecf0`
- `0x18001f393`
- `0x18001f3b9`
- `0x18001f3e0`
- `0x18001f469`
- `0x18001f490`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180001f0c`

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
0x180001f0c  jmp     cs:__imp__CxxThrowException
```
