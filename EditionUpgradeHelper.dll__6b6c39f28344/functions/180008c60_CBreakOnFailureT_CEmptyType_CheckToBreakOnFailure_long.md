# CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)

- ea: `0x180008c60`
- end: `0x180008c79`
- name: `?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z`
- size: `25`
- prototype: `__int64 __fastcall(int)`
- caller_count: `22`
- callee_count: `1`
- tags: ``

## callers

- `0x180008740`
- `0x180008a40`
- `0x180008bb0`
- `0x180008bf0`
- `0x180008dbc`
- `0x180008f10`
- `0x180009320`
- `0x1800093c0`
- `0x180009430`
- `0x1800094a0`
- `0x180009560`
- `0x1800096e8`
- `0x180009890`
- `0x180009a84`
- `0x18000a240`
- `0x18000a340`
- `0x18000a390`
- `0x18000a480`
- `0x18000a510`
- `0x18000ae50`
- `0x18000aed0`
- `0x18000b0a0`

## callees

- `0x180008c60`

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
0x180008c60  mov     eax, cs:?g_hResultToBreakOn@?$CBreakOnFailureT@VCEmptyType@@@@0JA; long CBreakOnFailureT<CEmptyType>::g_hResultToBreakOn
0x180008c66  test    eax, eax
0x180008c68  jz      short locret_180008C78
0x180008c6a  test    ecx, ecx
0x180008c6c  jns     short locret_180008C78
0x180008c6e  cmp     eax, ecx
0x180008c70  jz      short loc_180008C77
0x180008c72  cmp     eax, 0FFFFFFFFh
0x180008c75  jnz     short locret_180008C78
0x180008c77  int     3; Trap to Debugger
0x180008c78  retn
```
