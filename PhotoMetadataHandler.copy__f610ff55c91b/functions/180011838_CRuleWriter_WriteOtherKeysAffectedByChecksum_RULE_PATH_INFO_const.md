# CRuleWriter::WriteOtherKeysAffectedByChecksum(RULE_PATH_INFO const *)

- ea: `0x180011838`
- end: `0x180011937`
- name: `?WriteOtherKeysAffectedByChecksum@CRuleWriter@@IEAAJPEBURULE_PATH_INFO@@@Z`
- size: `255`
- prototype: `__int64 __fastcall(CRuleWriter *__hidden this, const struct RULE_PATH_INFO *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000f2d0`
- `0x18001cf60`

## callees

- `0x18000b3bc`
- `0x18000bac0`
- `0x18000dbd0`
- `0x18000e8a0`
- `0x180011838`
- `0x1800120a8`
- `0x1800129d8`
- `0x180013030`
- `0x18001cbc4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011926`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180011926`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CRuleWriter::WriteOtherKeysAffectedByChecksum(CRuleWriter *this, const struct RULE_PATH_INFO *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v8[2]; // [rsp+30h] [rbp-38h] BYREF
  PROPVARIANT pvar; // [rsp+40h] [rbp-28h] BYREF
  __int64 v10; // [rsp+90h] [rbp+28h] BYREF

  memset(&pvar, 0, sizeof(pvar));
  LODWORD(v10) = 0;
  v4 = CRuleHandler::CompareChecksums(*((struct IWICMetadataQueryReader **)this + 5), a2, (int *)&v10);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( (_DWORD)v10 )
    {
      v8[0] = 0;
      v8[1] = 0;
      if ( *((_QWORD *)this + 11) )
        ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::operator=(v8);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v10,
        *((_QWORD *)a2 + 6));
      ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::Add(
        v8,
        &v10);
      ATL::CStringData::Release((ATL::CStringData *)(v10 - 24));
      v6 = CPolicyComponent::WriteKeysAffectedByChecksum(
             *((CPolicyComponent **)this + 6),
             *((struct IWICMetadataQueryReader **)this + 5),
             (__int64)v8);
      v5 = v6;
      if ( v6 < 0 && g_doStackCaptures )
        DoStackCapture(v6);
      ATL::CSimpleArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::RemoveAll(v8);
    }
  }
  else if ( g_doStackCaptures )
  {
    DoStackCapture(v4);
  }
  PropVariantClear(&pvar);
  return v5;
}

```

## disassembly

```asm
0x180011838  push    rbp
0x18001183a  push    rbx
0x18001183b  push    rsi
0x18001183c  push    rdi
0x18001183d  mov     rbp, rsp
0x180011840  sub     rsp, 68h
0x180011844  mov     rsi, rdx
0x180011847  mov     rdi, rcx
0x18001184a  xorps   xmm0, xmm0
0x18001184d  xor     eax, eax
0x18001184f  movups  xmmword ptr [rbp+pvar], xmm0
0x180011853  mov     qword ptr [rbp+pvar+10h], rax
0x180011857  mov     dword ptr [rbp+arg_0], eax
0x18001185a  lea     r8, [rbp+arg_0]; int *
0x18001185e  mov     rcx, [rcx+28h]; struct IWICMetadataQueryReader *
0x180011862  call    ?CompareChecksums@CRuleHandler@@KAJPEAUIWICMetadataQueryReader@@PEBURULE_PATH_INFO@@PEAH@Z; CRuleHandler::CompareChecksums(IWICMetadataQueryReader *,RULE_PATH_INFO const *,int *)
0x180011867  mov     ebx, eax
0x180011869  test    eax, eax
0x18001186b  jns     short loc_18001188A
0x18001186d  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180011874  jz      short loc_180011882
0x180011876  mov     ecx, eax; int
0x180011878  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18001187d  jmp     loc_180011922
0x180011882  test    eax, eax
0x180011884  js      loc_180011922
0x18001188a  cmp     dword ptr [rbp+arg_0], 0
0x18001188e  jz      loc_180011922
0x180011894  mov     [rbp+var_38], 0
0x18001189c  mov     [rbp+var_30], 0
0x1800118a4  mov     rdx, [rdi+58h]
0x1800118a8  test    rdx, rdx
0x1800118ab  jz      short loc_1800118B6
0x1800118ad  lea     rcx, [rbp+var_38]
0x1800118b1  call    ??4?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::operator=(ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &)
0x1800118b6  mov     rdx, [rsi+30h]
0x1800118ba  lea     rcx, [rbp+arg_0]
0x1800118be  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800118c3  nop
0x1800118c4  lea     rdx, [rbp+arg_0]
0x1800118c8  lea     rcx, [rbp+var_38]
0x1800118cc  call    ?Add@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAHAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@2@@Z; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::Add(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800118d1  nop
0x1800118d2  mov     rcx, [rbp+arg_0]
0x1800118d6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800118da  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800118df  mov     r9, [rdi+8]
0x1800118e3  lea     rax, [rbp+var_38]
0x1800118e7  mov     [rsp+68h+var_48], rax; __int64
0x1800118ec  mov     r9, [r9+8]
0x1800118f0  mov     r8, [rsi+30h]
0x1800118f4  mov     rdx, [rdi+28h]; struct IWICMetadataQueryReader *
0x1800118f8  mov     rcx, [rdi+30h]; this
0x1800118fc  call    ?WriteKeysAffectedByChecksum@CPolicyComponent@@AEAAJPEAUIWICMetadataQueryWriter@@PEBG1PEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@@Z; CPolicyComponent::WriteKeysAffectedByChecksum(IWICMetadataQueryWriter *,ushort const *,ushort const *,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *)
0x180011901  mov     ebx, eax
0x180011903  test    eax, eax
0x180011905  jns     short loc_180011918
0x180011907  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18001190e  jz      short loc_180011918
0x180011910  mov     ecx, eax; int
0x180011912  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180011917  nop
0x180011918  lea     rcx, [rbp+var_38]
0x18001191c  call    ?RemoveAll@?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAXXZ; ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>::RemoveAll(void)
0x180011921  nop
0x180011922  lea     rcx, [rbp+pvar]; pvar
0x180011926  call    cs:__imp_PropVariantClear
0x18001192c  mov     eax, ebx
0x18001192e  add     rsp, 68h
0x180011932  pop     rdi
0x180011933  pop     rsi
0x180011934  pop     rbx
0x180011935  pop     rbp
0x180011936  retn
```
