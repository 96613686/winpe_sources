# ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAt(__POSITION *)

- ea: `0x14000c864`
- end: `0x14000c8ad`
- name: `?RemoveAt@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXPEAU__POSITION@@@Z`
- size: `73`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000f810`

## callees

- `0x140004890`
- `0x14000c4ac`
- `0x14000c864`

## pseudocode

```c
__int64 __fastcall ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAt(
        _QWORD *a1,
        _QWORD *a2)
{
  _QWORD *v2; // r8
  __int64 v3; // rax

  v2 = a1;
  if ( !a2 )
    ATL::AtlThrowImpl(-2147467259);
  if ( a2 != (_QWORD *)*a1 )
    a1 = (_QWORD *)a2[1];
  *a1 = *a2;
  v3 = a2[1];
  if ( a2 == (_QWORD *)v2[1] )
    v2[1] = v3;
  else
    *(_QWORD *)(*a2 + 8LL) = v3;
  return ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::FreeNode(v2);
}

```

## disassembly

```asm
0x14000c864  sub     rsp, 28h
0x14000c868  mov     r8, rcx
0x14000c86b  test    rdx, rdx
0x14000c86e  jz      short loc_14000C8A2
0x14000c870  mov     rax, [rdx]
0x14000c873  cmp     rdx, [rcx]
0x14000c876  jz      short loc_14000C87C
0x14000c878  mov     rcx, [rdx+8]
0x14000c87c  mov     [rcx], rax
0x14000c87f  mov     rax, [rdx+8]
0x14000c883  cmp     rdx, [r8+8]
0x14000c887  jnz     short loc_14000C88F
0x14000c889  mov     [r8+8], rax
0x14000c88d  jmp     short loc_14000C896
0x14000c88f  mov     rcx, [rdx]
0x14000c892  mov     [rcx+8], rax
0x14000c896  mov     rcx, r8
0x14000c899  add     rsp, 28h
0x14000c89d  jmp     ?FreeNode@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::FreeNode(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CNode *)
0x14000c8a2  mov     ecx, 80004005h; int
0x14000c8a7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
