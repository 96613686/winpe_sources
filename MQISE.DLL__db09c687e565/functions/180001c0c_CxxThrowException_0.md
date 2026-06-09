# _CxxThrowException_0

- ea: `0x180001c0c`
- end: `0x180001c12`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `55`
- callee_count: `0`
- tags: ``

## callers

- `0x180001434`
- `0x180001490`
- `0x180002b90`
- `0x180002c38`
- `0x180004c7c`
- `0x180004df0`
- `0x180004f68`
- `0x180005528`
- `0x180006570`
- `0x180006a40`
- `0x180006e7c`
- `0x1800078e0`
- `0x180009590`
- `0x1800096b8`
- `0x180009748`
- `0x180009a3c`
- `0x18000a3a4`
- `0x18000a3d0`
- `0x18000b11c`
- `0x18000b260`
- `0x18000b290`
- `0x18000b2d0`
- `0x18000b310`
- `0x18000b40c`
- `0x18000b728`
- `0x18000b98c`
- `0x18000bc60`
- `0x18000bce4`
- `0x18000be1c`
- `0x18000c614`
- `0x18000d3e0`
- `0x18000dca0`
- `0x18000dd2c`
- `0x18000de78`
- `0x18000df04`
- `0x18000dfa4`
- `0x18000e068`
- `0x18000e124`
- `0x18000e1e4`
- `0x18000e66c`
- `0x18000e800`
- `0x18000e884`
- `0x18000eb70`
- `0x18000ecf8`
- `0x18000edd0`
- `0x18000eff8`
- `0x18000f0c8`
- `0x18000f170`
- `0x18000fcbe`
- `0x18000fce4`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x180001c0c`

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
0x180001c0c  jmp     cs:__imp__CxxThrowException
```
