# CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)

- ea: `0x1800090dc`
- end: `0x1800090f5`
- name: `?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z`
- size: `25`
- prototype: `__int64 __fastcall(int)`
- caller_count: `95`
- callee_count: `1`
- tags: ``

## callers

- `0x1800092c0`
- `0x180009300`
- `0x180009540`
- `0x180009f30`
- `0x18000a2cc`
- `0x18000a340`
- `0x18000a4c0`
- `0x18000a620`
- `0x18000a6d0`
- `0x18000a9c0`
- `0x18000aae0`
- `0x18000ac30`
- `0x18000ad40`
- `0x18000af78`
- `0x18000b0b0`
- `0x18000b220`
- `0x18000b310`
- `0x18000b3c0`
- `0x18000b400`
- `0x18000b448`
- `0x18000b57c`
- `0x18000b68c`
- `0x18000b7c0`
- `0x18000b860`
- `0x18000b884`
- `0x18000b984`
- `0x18000bb10`
- `0x18000be7c`
- `0x18000bf00`
- `0x18000c0cc`
- `0x18000c1c0`
- `0x18000c238`
- `0x18000c310`
- `0x18000c394`
- `0x18000c45c`
- `0x18000c55c`
- `0x18000c754`
- `0x18000c870`
- `0x18000cf20`
- `0x18000d124`
- `0x18000d7b4`
- `0x18000d95c`
- `0x18000f220`
- `0x18000f264`
- `0x1800117b0`
- `0x180011e90`
- `0x180011fac`
- `0x180012238`
- `0x1800124e8`
- `0x180012620`

## callees

- `0x1800090dc`

## pseudocode

```c
__int64 __fastcall CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(int a1)
{
  __int64 result; // rax

  result = (unsigned int)CBreakOnFailureT<CEmptyType>::g_hResultToBreakOn;
  if ( CBreakOnFailureT<CEmptyType>::g_hResultToBreakOn
    && a1 < 0
    && (CBreakOnFailureT<CEmptyType>::g_hResultToBreakOn == a1 || CBreakOnFailureT<CEmptyType>::g_hResultToBreakOn == -1) )
  {
    __debugbreak();
  }
  return result;
}

```

## disassembly

```asm
0x1800090dc  mov     eax, cs:?g_hResultToBreakOn@?$CBreakOnFailureT@VCEmptyType@@@@0JA; long CBreakOnFailureT<CEmptyType>::g_hResultToBreakOn
0x1800090e2  test    eax, eax
0x1800090e4  jz      short locret_1800090F4
0x1800090e6  test    ecx, ecx
0x1800090e8  jns     short locret_1800090F4
0x1800090ea  cmp     eax, ecx
0x1800090ec  jz      short loc_1800090F3
0x1800090ee  cmp     eax, 0FFFFFFFFh
0x1800090f1  jnz     short locret_1800090F4
0x1800090f3  int     3; Trap to Debugger
0x1800090f4  retn
```
