# _CxxThrowException_0

- ea: `0x18000257c`
- end: `0x180002582`
- name: `_CxxThrowException_0`
- size: `6`
- prototype: `void __stdcall __noreturn(void *pExceptionObject, _ThrowInfo *pThrowInfo)`
- caller_count: `57`
- callee_count: `0`
- tags: ``

## callers

- `0x180001578`
- `0x1800015b8`
- `0x1800015e4`
- `0x180004684`
- `0x180005a20`
- `0x18000a58c`
- `0x18000a690`
- `0x18000aa6c`
- `0x18000ae80`
- `0x18000afc0`
- `0x18000c4b0`
- `0x18000ca40`
- `0x18000d374`
- `0x18000d3d8`
- `0x18000dd04`
- `0x18000dda4`
- `0x18000def4`
- `0x18000e010`
- `0x18000e10c`
- `0x18000e25c`
- `0x18000e3b8`
- `0x18000e49c`
- `0x18000e594`
- `0x18000e6a8`
- `0x18000ea24`
- `0x18000eb74`
- `0x18000eddc`
- `0x18000f624`
- `0x18000f850`
- `0x18000fd87`
- `0x180010d28`
- `0x180010d4e`
- `0x180010dba`
- `0x180010e0f`
- `0x180010e49`
- `0x180010e92`
- `0x180010ecd`
- `0x180010f12`
- `0x180010f54`
- `0x180010f9c`
- `0x18001101e`
- `0x18001109d`
- `0x1800110c3`
- `0x1800110ec`
- `0x180011148`
- `0x1800111a1`
- `0x1800111ec`
- `0x180011249`
- `0x180011289`
- `0x1800112e0`

## import_xrefs

- `msvcrt!_CxxThrowException` at `0x18000257c`

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
0x18000257c  jmp     cs:__imp__CxxThrowException
```
