# ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)

- ea: `0x14000c7e0`
- end: `0x14000c85c`
- name: `?RemoveAll@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ`
- size: `124`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x14000c270`
- `0x14000c4ac`
- `0x14000cdf4`
- `0x14000e538`
- `0x140010960`

## callees

- `0x140004890`
- `0x14000c4ac`
- `0x14000c7e0`

## import_xrefs

- `msvcrt!free` at `0x14000c834`
- `msvcrt!free` at `0x14000c834`

## pseudocode

```c
void __fastcall ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(
        __int64 a1)
{
  _QWORD *v2; // rcx
  _QWORD *v3; // rbx

  while ( *(_QWORD *)(a1 + 16) )
  {
    if ( !*(_QWORD *)a1 )
      ATL::AtlThrowImpl(-2147467259);
    *(_QWORD *)a1 = **(_QWORD **)a1;
    ATL::CAtlList<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::FreeNode(a1);
  }
  *(_QWORD *)a1 = 0;
  *(_QWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  v2 = *(_QWORD **)(a1 + 24);
  if ( v2 )
  {
    do
    {
      v3 = (_QWORD *)*v2;
      free(v2);
      v2 = v3;
    }
    while ( v3 );
    *(_QWORD *)(a1 + 24) = 0;
  }
}

```

## disassembly

```asm
0x14000c7e0  mov     [rsp+arg_0], rbx
0x14000c7e5  push    rdi
0x14000c7e6  sub     rsp, 20h
0x14000c7ea  mov     rdi, rcx
0x14000c7ed  cmp     qword ptr [rcx+10h], 0
0x14000c7f2  jbe     short loc_14000C811
0x14000c7f4  mov     rdx, [rdi]
0x14000c7f7  test    rdx, rdx
0x14000c7fa  jz      short loc_14000C851
0x14000c7fc  mov     rax, [rdx]
0x14000c7ff  mov     [rdi], rax
0x14000c802  mov     rcx, rdi
0x14000c805  call    ?FreeNode@?$CAtlList@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CElementTraits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::FreeNode(ATL::CAtlList<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CElementTraits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::CNode *)
0x14000c80a  cmp     qword ptr [rdi+10h], 0
0x14000c80f  ja      short loc_14000C7F4
0x14000c811  mov     qword ptr [rdi], 0
0x14000c818  mov     qword ptr [rdi+8], 0
0x14000c820  mov     qword ptr [rdi+20h], 0
0x14000c828  mov     rcx, [rdi+18h]; Block
0x14000c82c  test    rcx, rcx
0x14000c82f  jz      short loc_14000C846
0x14000c831  mov     rbx, [rcx]
0x14000c834  call    cs:__imp_free
0x14000c83a  mov     rcx, rbx
0x14000c83d  test    rbx, rbx
0x14000c840  jnz     short loc_14000C831
0x14000c842  mov     [rdi+18h], rbx
0x14000c846  mov     rbx, [rsp+28h+arg_0]
0x14000c84b  add     rsp, 20h
0x14000c84f  pop     rdi
0x14000c850  retn
0x14000c851  mov     ecx, 80004005h; int
0x14000c856  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
