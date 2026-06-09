# std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)

- ea: `0x1800073f4`
- end: `0x180007508`
- name: `??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@@std@@QEAAAEAVCComVariant@ATL@@$$QEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@3@@Z`
- size: `276`
- prototype: `__int64 __fastcall(__int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007f08`

## callees

- `0x18000193c`
- `0x180002d44`
- `0x180003858`
- `0x180006fcc`
- `0x180007248`
- `0x1800073f4`
- `0x1800095c4`
- `0x1800097f4`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000749f`
- `OLEAUT32!__imp_VariantInit` at `0x18000749f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant>::operator[](
        __int64 *a1,
        __int64 *a2)
{
  __int64 inserted; // r8
  __int64 v5; // rdx
  unsigned __int16 *v6; // rax
  __int64 v7; // rdx
  unsigned __int16 v8; // cx
  int v9; // eax
  __int64 v10; // rdi
  char *v11; // rsi
  __int128 v13; // [rsp+20h] [rbp-58h] BYREF
  __int128 v14; // [rsp+30h] [rbp-48h] BYREF
  __int64 v15; // [rsp+40h] [rbp-38h]

  std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CComVariant,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>>,0>>::_Find_lower_bound<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(
    (__int64)a1,
    &v14,
    a2);
  inserted = v15;
  if ( *(_BYTE *)(v15 + 25) )
    goto LABEL_9;
  v5 = *(_QWORD *)(v15 + 32);
  if ( !v5 )
    ATL::AtlThrowImpl(-2147467259);
  v6 = (unsigned __int16 *)*a2;
  v7 = v5 - *a2;
  while ( 1 )
  {
    v8 = *v6;
    if ( *v6 != *(unsigned __int16 *)((char *)v6 + v7) )
      break;
    ++v6;
    if ( !v8 )
    {
      v9 = 0;
      goto LABEL_8;
    }
  }
  v9 = v8 < *(unsigned __int16 *)((char *)v6 + v7) ? -1 : 1;
LABEL_8:
  if ( v9 < 0 )
  {
LABEL_9:
    if ( a1[1] == 0x3FFFFFFFFFFFFFFLL )
      std::_Throw_tree_length_error();
    v10 = *a1;
    *(_QWORD *)&v13 = a1;
    v11 = (char *)operator new(0x40u);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (_QWORD *)v11 + 4,
      a2);
    VariantInit((VARIANTARG *)(v11 + 40));
    *(_QWORD *)v11 = v10;
    *((_QWORD *)v11 + 1) = v10;
    *((_QWORD *)v11 + 2) = v10;
    *((_WORD *)v11 + 12) = 0;
    *((_QWORD *)&v13 + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CComVariant>,void *>>>((__int64)&v13);
    v13 = v14;
    inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<enum PluginId const,std::vector<std::shared_ptr<PluginPendingMessage>>>>>::_Insert_node(
                 a1,
                 &v13,
                 v11);
  }
  return inserted + 40;
}

```

## disassembly

```asm
0x1800073f4  push    rbx
0x1800073f6  push    rsi
0x1800073f7  push    rdi
0x1800073f8  push    r14
0x1800073fa  push    r15
0x1800073fc  sub     rsp, 50h
0x180007400  mov     r15, rdx
0x180007403  mov     r14, rcx
0x180007406  mov     r8, rdx
0x180007409  lea     rdx, [rsp+78h+var_48]
0x18000740e  call    ??$_Find_lower_bound@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@PEAX@std@@@1@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CComVariant,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>>,0>>::_Find_lower_bound<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180007413  mov     r8, [rsp+78h+var_38]
0x180007418  cmp     byte ptr [r8+19h], 0
0x18000741d  jnz     short loc_180007458
0x18000741f  mov     rdx, [r8+20h]
0x180007423  test    rdx, rdx
0x180007426  jz      loc_1800074FD
0x18000742c  mov     rax, [r15]
0x18000742f  sub     rdx, rax
0x180007432  movzx   ecx, word ptr [rax]
0x180007435  cmp     cx, [rax+rdx]
0x180007439  jnz     short loc_180007448
0x18000743b  add     rax, 2
0x18000743f  test    cx, cx
0x180007442  jnz     short loc_180007432
0x180007444  xor     eax, eax
0x180007446  jmp     short loc_18000744D
0x180007448  sbb     eax, eax
0x18000744a  or      eax, 1
0x18000744d  shr     eax, 1Fh
0x180007450  test    al, al
0x180007452  jz      loc_1800074E7
0x180007458  mov     rax, 3FFFFFFFFFFFFFFh
0x180007462  cmp     [r14+8], rax
0x180007466  jz      loc_1800074F7
0x18000746c  mov     rdi, [r14]
0x18000746f  mov     qword ptr [rsp+78h+var_58], r14
0x180007474  mov     qword ptr [rsp+78h+var_58+8], 0
0x18000747d  mov     ecx, 40h ; '@'; Size
0x180007482  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007487  mov     rsi, rax
0x18000748a  mov     qword ptr [rsp+78h+var_58+8], rax
0x18000748f  mov     rdx, r15
0x180007492  lea     rcx, [rax+20h]
0x180007496  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000749b  lea     rcx, [rsi+28h]; pvarg
0x18000749f  call    cs:__imp_VariantInit
0x1800074a5  mov     [rsi], rdi
0x1800074a8  mov     [rsi+8], rdi
0x1800074ac  mov     [rsi+10h], rdi
0x1800074b0  mov     word ptr [rsi+18h], 0
0x1800074b6  mov     qword ptr [rsp+78h+var_58+8], 0
0x1800074bf  lea     rcx, [rsp+78h+var_58]
0x1800074c4  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@VCComVariant@2@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CComVariant>,void *>>>(void)
0x1800074c9  movups  xmm0, [rsp+78h+var_48]
0x1800074ce  movdqu  [rsp+78h+var_58], xmm0
0x1800074d4  mov     r8, rsi
0x1800074d7  lea     rdx, [rsp+78h+var_58]
0x1800074dc  mov     rcx, r14
0x1800074df  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBW4PluginId@@V?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBW4PluginId@@V?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBW4PluginId@@V?$vector@V?$shared_ptr@UPluginPendingMessage@@@std@@V?$allocator@V?$shared_ptr@UPluginPendingMessage@@@std@@@2@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<PluginId const,std::vector<std::shared_ptr<PluginPendingMessage>>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<PluginId const,std::vector<std::shared_ptr<PluginPendingMessage>>>,void *> *>,std::_Tree_node<std::pair<PluginId const,std::vector<std::shared_ptr<PluginPendingMessage>>>,void *> * const)
0x1800074e4  mov     r8, rax
0x1800074e7  lea     rax, [r8+28h]
0x1800074eb  add     rsp, 50h
0x1800074ef  pop     r15
0x1800074f1  pop     r14
0x1800074f3  pop     rdi
0x1800074f4  pop     rsi
0x1800074f5  pop     rbx
0x1800074f6  retn
0x1800074f7  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
0x1800074fd  mov     ecx, 80004005h; int
0x180007502  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
