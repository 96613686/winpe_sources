# CRuleWriter::WriteOtherKeysAffectedByChecksum(RULE_PATH_INFO const *)

- ea: `0x180012050`
- end: `0x180012156`
- name: `?WriteOtherKeysAffectedByChecksum@CRuleWriter@@IEAAJPEBURULE_PATH_INFO@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(CRuleWriter *__hidden this, const struct RULE_PATH_INFO *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000fa14`
- `0x18001dd00`

## callees

- `0x18000b90c`
- `0x18000c048`
- `0x18000e280`
- `0x18000ef18`
- `0x180012050`
- `0x180012950`
- `0x1800132dc`
- `0x18001395c`
- `0x18001d958`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001213e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001213e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRuleWriter::WriteOtherKeysAffectedByChecksum(CRuleWriter *this, const struct RULE_PATH_INFO *a2)
{
  int v4; // eax
  __int64 v5; // r8
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v9[2]; // [rsp+30h] [rbp-38h] BYREF
  PROPVARIANT pvar; // [rsp+40h] [rbp-28h] BYREF
  __int64 v11; // [rsp+90h] [rbp+28h] BYREF

  memset(&pvar, 0, sizeof(pvar));
  LODWORD(v11) = 0;
  v4 = CRuleHandler::CompareChecksums(*((struct IWICMetadataQueryReader **)this + 5), a2, (int *)&v11);
  v6 = v4;
  if ( v4 >= 0 )
  {
    if ( (_DWORD)v11 )
    {
      v9[0] = 0;
      v9[1] = 0;
      if ( *((_QWORD *)this + 11) )
        ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator=(v9);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v11,
        *((_QWORD *)a2 + 6),
        v5);
      ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add(
        v9,
        &v11);
      ATL::CStringData::Release((ATL::CStringData *)(v11 - 24));
      v7 = CPolicyComponent::WriteKeysAffectedByChecksum(
             *((CPolicyComponent **)this + 6),
             *((struct IWICMetadataQueryReader **)this + 5),
             (__int64)v9);
      v6 = v7;
      if ( v7 < 0 && g_doStackCaptures )
        DoStackCapture(v7);
      ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(v9);
    }
  }
  else if ( g_doStackCaptures )
  {
    DoStackCapture(v4);
  }
  PropVariantClear(&pvar);
  return v6;
}

```

## disassembly

```asm
0x180012050  push    rbp
0x180012052  push    rbx
0x180012053  push    rsi
0x180012054  push    rdi
0x180012055  mov     rbp, rsp
0x180012058  sub     rsp, 68h
0x18001205c  mov     rsi, rdx
0x18001205f  mov     rdi, rcx
0x180012062  xorps   xmm0, xmm0
0x180012065  xor     eax, eax
0x180012067  movups  xmmword ptr [rbp+pvar], xmm0
0x18001206b  mov     qword ptr [rbp+pvar+10h], rax
0x18001206f  mov     dword ptr [rbp+arg_0], eax
0x180012072  lea     r8, [rbp+arg_0]; int *
0x180012076  mov     rcx, [rcx+28h]; struct IWICMetadataQueryReader *
0x18001207a  call    ?CompareChecksums@CRuleHandler@@KAJPEAUIWICMetadataQueryReader@@PEBURULE_PATH_INFO@@PEAH@Z; CRuleHandler::CompareChecksums(IWICMetadataQueryReader *,RULE_PATH_INFO const *,int *)
0x18001207f  mov     ebx, eax
0x180012081  test    eax, eax
0x180012083  jns     short loc_1800120A2
0x180012085  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001208c  jz      short loc_18001209A
0x18001208e  mov     ecx, eax; int
0x180012090  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180012095  jmp     loc_18001213A
0x18001209a  test    eax, eax
0x18001209c  js      loc_18001213A
0x1800120a2  cmp     dword ptr [rbp+arg_0], 0
0x1800120a6  jz      loc_18001213A
0x1800120ac  mov     [rbp+var_38], 0
0x1800120b4  mov     [rbp+var_30], 0
0x1800120bc  mov     rdx, [rdi+58h]
0x1800120c0  test    rdx, rdx
0x1800120c3  jz      short loc_1800120CE
0x1800120c5  lea     rcx, [rbp+var_38]
0x1800120c9  call    ??4?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator=(ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x1800120ce  mov     rdx, [rsi+30h]
0x1800120d2  lea     rcx, [rbp+arg_0]
0x1800120d6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800120db  nop
0x1800120dc  lea     rdx, [rbp+arg_0]
0x1800120e0  lea     rcx, [rbp+var_38]
0x1800120e4  call    ?Add@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAHAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800120e9  nop
0x1800120ea  mov     rcx, [rbp+arg_0]
0x1800120ee  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800120f2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800120f7  mov     r9, [rdi+8]
0x1800120fb  lea     rax, [rbp+var_38]
0x1800120ff  mov     [rsp+68h+var_48], rax; __int64
0x180012104  mov     r9, [r9+8]
0x180012108  mov     r8, [rsi+30h]
0x18001210c  mov     rdx, [rdi+28h]; struct IWICMetadataQueryReader *
0x180012110  mov     rcx, [rdi+30h]; this
0x180012114  call    ?WriteKeysAffectedByChecksum@CPolicyComponent@@AEAAJPEAUIWICMetadataQueryWriter@@PEBG1PEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; CPolicyComponent::WriteKeysAffectedByChecksum(IWICMetadataQueryWriter *,ushort const *,ushort const *,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)
0x180012119  mov     ebx, eax
0x18001211b  test    eax, eax
0x18001211d  jns     short loc_180012130
0x18001211f  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180012126  jz      short loc_180012130
0x180012128  mov     ecx, eax; int
0x18001212a  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001212f  nop
0x180012130  lea     rcx, [rbp+var_38]
0x180012134  call    ?RemoveAll@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x180012139  nop
0x18001213a  lea     rcx, [rbp+pvar]; pvar
0x18001213e  call    cs:__imp_PropVariantClear
0x180012145  nop     dword ptr [rax+rax+00h]
0x18001214a  mov     eax, ebx
0x18001214c  add     rsp, 68h
0x180012150  pop     rdi
0x180012151  pop     rsi
0x180012152  pop     rbx
0x180012153  pop     rbp
0x180012154  retn
```
