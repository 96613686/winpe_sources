# CPolicyComponent::SetMetadataByName(IWICMetadataQueryReader *,ushort const *,tagPROPVARIANT const *)

- ea: `0x1800160e0`
- end: `0x1800161d1`
- name: `?SetMetadataByName@CPolicyComponent@@UEAAJPEAUIWICMetadataQueryReader@@PEBGPEBUtagPROPVARIANT@@@Z`
- size: `241`
- prototype: `__int64 __fastcall(CPolicyComponent *__hidden this, struct IWICMetadataQueryReader *, const unsigned __int16 *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000170c`
- `0x180008b54`
- `0x18000fb30`
- `0x1800160e0`
- `0x180029010`

## pseudocode

```c
__int64 __fastcall CPolicyComponent::SetMetadataByName(
        CPolicyComponent *this,
        struct IWICMetadataQueryReader *a2,
        const unsigned __int16 *a3,
        const struct tagPROPVARIANT *a4)
{
  int v5; // ebx
  int v6; // esi
  int v7; // ebx
  int v9; // [rsp+20h] [rbp-48h]
  __int64 v10; // [rsp+50h] [rbp-18h] BYREF
  const ATL::CAtlException *v11; // [rsp+58h] [rbp-10h] BYREF
  __int64 v12; // [rsp+80h] [rbp+18h] BYREF

  v5 = (int)a3;
  v6 = (int)this;
  if ( !a3 || !a4 )
    return 2147500035LL;
  v10 = 0;
  ATL::CComQIPtr<IWICMetadataQueryWriter,&__s_GUID const _GUID_a721791a_0def_4d06_bd91_2118bf1db10b>::CComQIPtr<IWICMetadataQueryWriter,&__s_GUID const _GUID_a721791a_0def_4d06_bd91_2118bf1db10b>(
    &v12,
    a2);
  try
  {
    if ( v12 )
    {
      v7 = CPolicyComponent::CreateAndInitializeRuleWriter(
             v6,
             v5,
             v12,
             (int)&gc_rgWritePathList,
             v9,
             (struct RULE_LIST_INDEX_ENTRY *)&gc_rgWritePathIndex,
             0x2DBu,
             0,
             (__int64)&v10);
      if ( v7 >= 0 )
        v7 = (*(__int64 (__fastcall **)(__int64, const struct tagPROPVARIANT *))(*(_QWORD *)v10 + 24LL))(v10, a4);
    }
    else
    {
      v7 = -2147467262;
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
  }
  catch ( const ATL::CAtlException *v11 )
  {
    LODWORD(v12) = *(_DWORD *)v11;
    v7 = v12;
  }
  if ( v12 )
  {
    v7 = CPolicyComponent::CreateAndInitializeRuleWriter(
           v6,
           v5,
           v12,
           (int)&gc_rgWritePathList,
           v9,
           (struct RULE_LIST_INDEX_ENTRY *)&gc_rgWritePathIndex,
           0x2DBu,
           0,
           (__int64)&v10);
    if ( v7 >= 0 )
      v7 = (*(__int64 (__fastcall **)(__int64, const struct tagPROPVARIANT *))(*(_QWORD *)v10 + 24LL))(v10, a4);
  }
  else
  {
    v7 = -2147467262;
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
}

```

## disassembly

```asm
0x1800160e0  mov     rax, rsp
0x1800160e3  mov     [rax+8], rbx
0x1800160e7  mov     [rax+10h], rsi
0x1800160eb  push    rdi
0x1800160ec  sub     rsp, 60h
0x1800160f0  mov     rdi, r9
0x1800160f3  mov     rbx, r8
0x1800160f6  mov     rsi, rcx
0x1800160f9  test    r8, r8
0x1800160fc  jz      loc_1800161BB
0x180016102  test    r9, r9
0x180016105  jz      loc_1800161BB
0x18001610b  mov     qword ptr [rax-18h], 0
0x180016113  lea     rcx, [rax+18h]
0x180016117  call    ??0?$CComQIPtr@UIWICMetadataQueryWriter@@$1?_GUID_a721791a_0def_4d06_bd91_2118bf1db10b@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IWICMetadataQueryWriter,&__s_GUID const _GUID_a721791a_0def_4d06_bd91_2118bf1db10b>::CComQIPtr<IWICMetadataQueryWriter,&__s_GUID const _GUID_a721791a_0def_4d06_bd91_2118bf1db10b>(IUnknown *)
0x18001611c  nop
0x18001611d  mov     r8, [rsp+68h+arg_10]; int
0x180016125  test    r8, r8
0x180016128  jnz     short loc_180016131
0x18001612a  mov     ebx, 80004002h
0x18001612f  jmp     short loc_180016186
0x180016131  lea     rax, [rsp+68h+var_18]
0x180016136  mov     [rsp+68h+var_28], rax; __int64
0x18001613b  mov     [rsp+68h+var_30], 0; __int64
0x180016144  mov     [rsp+68h+var_38], 2DBh; unsigned int
0x18001614c  lea     rax, ?gc_rgWritePathIndex@@3QBURULE_LIST_INDEX_ENTRY@@B; RULE_LIST_INDEX_ENTRY const near * const gc_rgWritePathIndex
0x180016153  mov     [rsp+68h+var_40], rax; struct RULE_LIST_INDEX_ENTRY *
0x180016158  lea     r9, ?gc_rgWritePathList@@3QBURULE_PATH_INFO@@B; int
0x18001615f  mov     rdx, rbx; int
0x180016162  mov     rcx, rsi; int
0x180016165  call    ?CreateAndInitializeRuleWriter@CPolicyComponent@@AEAAJPEBGPEAUIWICMetadataQueryWriter@@PEBURULE_PATH_INFO@@IPEBURULE_LIST_INDEX_ENTRY@@IPEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAPEAVCRuleWriter@@@Z; CPolicyComponent::CreateAndInitializeRuleWriter(ushort const *,IWICMetadataQueryWriter *,RULE_PATH_INFO const *,uint,RULE_LIST_INDEX_ENTRY const *,uint,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,CRuleWriter * *)
0x18001616a  mov     ebx, eax
0x18001616c  test    eax, eax
0x18001616e  js      short loc_180016186
0x180016170  mov     rcx, [rsp+68h+var_18]
0x180016175  mov     rax, [rcx]
0x180016178  mov     rdx, rdi
0x18001617b  mov     rax, [rax+18h]
0x18001617f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016184  mov     ebx, eax
0x180016186  lea     rcx, [rsp+68h+arg_10]
0x18001618e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180016193  nop
0x180016194  jmp     short loc_18001619D
0x180016196  mov     ebx, dword ptr [rsp+68h+arg_10]
0x18001619d  mov     rcx, [rsp+68h+var_18]
0x1800161a2  test    rcx, rcx
0x1800161a5  jz      short loc_1800161B7
0x1800161a7  mov     rdx, [rcx]
0x1800161aa  mov     rax, [rdx]
0x1800161ad  mov     edx, 1
0x1800161b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800161b7  mov     eax, ebx
0x1800161b9  jmp     short loc_1800161C0
0x1800161bb  mov     eax, 80004003h
0x1800161c0  mov     rbx, [rsp+68h+arg_0]
0x1800161c5  mov     rsi, [rsp+68h+arg_8]
0x1800161ca  add     rsp, 60h
0x1800161ce  pop     rdi
0x1800161cf  retn
```
