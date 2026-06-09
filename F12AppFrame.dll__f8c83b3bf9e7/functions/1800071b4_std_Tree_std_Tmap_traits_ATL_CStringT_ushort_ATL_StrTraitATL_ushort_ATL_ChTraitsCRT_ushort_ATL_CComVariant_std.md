# std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>,0>>(void)

- ea: `0x1800071b4`
- end: `0x180007241`
- name: `??1?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@QEAA@XZ`
- size: `141`
- prototype: `void __fastcall(void **)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800072e4`
- `0x180007f08`
- `0x18002dec0`

## callees

- `0x180001900`
- `0x180006f4c`
- `0x1800071b4`
- `0x180035010`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1800071e8`
- `OLEAUT32!__imp_VariantClear` at `0x1800071e8`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>,0>>(
        void **a1)
{
  __int64 *v2; // rbx
  __int64 *v3; // rsi
  volatile signed __int32 *v4; // rdx

  v2 = (__int64 *)*((_QWORD *)*a1 + 1);
  while ( !*((_BYTE *)v2 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>,void *>>>(
      (__int64)a1,
      (__int64)a1,
      (__int64 *)v2[2]);
    v3 = v2;
    v2 = (__int64 *)*v2;
    VariantClear((VARIANTARG *)(v3 + 5));
    v4 = (volatile signed __int32 *)(v3[4] - 24);
    if ( _InterlockedExchangeAdd(v4 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4);
    operator delete(v3);
  }
  operator delete(*a1);
}

```

## disassembly

```asm
0x1800071b4  mov     [rsp+arg_0], rbx
0x1800071b9  mov     [rsp+arg_8], rsi
0x1800071be  push    rdi
0x1800071bf  sub     rsp, 20h
0x1800071c3  mov     rax, [rcx]
0x1800071c6  mov     rdi, rcx
0x1800071c9  mov     rbx, [rax+8]
0x1800071cd  jmp     short loc_18000721F
0x1800071cf  mov     r8, [rbx+10h]
0x1800071d3  mov     rdx, rdi
0x1800071d6  mov     rcx, rdi
0x1800071d9  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>,void *>>>(std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>,void *>> &,std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>,void *> *)
0x1800071de  mov     rsi, rbx
0x1800071e1  mov     rbx, [rbx]
0x1800071e4  lea     rcx, [rsi+28h]; pvarg
0x1800071e8  call    cs:__imp_VariantClear
0x1800071ee  mov     rdx, [rsi+20h]
0x1800071f2  add     rdx, 0FFFFFFFFFFFFFFE8h
0x1800071f6  or      eax, 0FFFFFFFFh
0x1800071f9  lock xadd [rdx+10h], eax
0x1800071fe  sub     eax, 1
0x180007201  jg      short loc_180007212
0x180007203  mov     rcx, [rdx]
0x180007206  mov     rax, [rcx]
0x180007209  mov     rax, [rax+8]
0x18000720d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007212  mov     edx, 40h ; '@'
0x180007217  mov     rcx, rsi; Block
0x18000721a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000721f  cmp     byte ptr [rbx+19h], 0
0x180007223  jz      short loc_1800071CF
0x180007225  mov     rcx, [rdi]; Block
0x180007228  mov     edx, 40h ; '@'
0x18000722d  mov     rbx, [rsp+28h+arg_0]
0x180007232  mov     rsi, [rsp+28h+arg_8]
0x180007237  add     rsp, 20h
0x18000723b  pop     rdi
0x18000723c  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
