# CPolicyComponent::SetMetadataByName(IWICMetadataQueryReader *,ushort const *,tagPROPVARIANT const *)

- ea: `0x1800156d0`
- end: `0x1800157c0`
- name: `?SetMetadataByName@CPolicyComponent@@UEAAJPEAUIWICMetadataQueryReader@@PEBGPEBUtagPROPVARIANT@@@Z`
- size: `240`
- prototype: `__int64 __fastcall(CPolicyComponent *__hidden this, struct IWICMetadataQueryReader *, const unsigned __int16 *, const struct tagPROPVARIANT *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000168c`
- `0x180007804`
- `0x18000f474`
- `0x1800156d0`
- `0x180028010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPolicyComponent::SetMetadataByName(
        CPolicyComponent *this,
        struct IWICMetadataQueryReader *a2,
        const unsigned __int16 *a3,
        const struct tagPROPVARIANT *a4)
{
  int v7; // ebx
  int v9; // [rsp+20h] [rbp-48h]
  __int64 v10; // [rsp+50h] [rbp-18h] BYREF
  const ATL::CAtlException *v11; // [rsp+58h] [rbp-10h] BYREF
  __int64 v12; // [rsp+80h] [rbp+18h] BYREF

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
             (unsigned int *)this,
             a3,
             v12,
             (__int64)&gc_rgWritePathList,
             v9,
             (struct RULE_LIST_INDEX_ENTRY *)&gc_rgWritePathIndex,
             0x2DBu,
             0,
             &v10);
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
  if ( v10 )
    (**(void (__fastcall ***)(__int64, __int64))v10)(v10, 1);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800156d0  mov     rax, rsp
0x1800156d3  mov     [rax+8], rbx
0x1800156d7  mov     [rax+10h], rsi
0x1800156db  push    rdi
0x1800156dc  sub     rsp, 60h
0x1800156e0  mov     rdi, r9
0x1800156e3  mov     rbx, r8
0x1800156e6  mov     rsi, rcx
0x1800156e9  test    r8, r8
0x1800156ec  jz      loc_1800157AB
0x1800156f2  test    r9, r9
0x1800156f5  jz      loc_1800157AB
0x1800156fb  mov     qword ptr [rax-18h], 0
0x180015703  lea     rcx, [rax+18h]
0x180015707  call    ??0?$CComQIPtr@UIWICMetadataQueryWriter@@$1?_GUID_a721791a_0def_4d06_bd91_2118bf1db10b@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IWICMetadataQueryWriter,&__s_GUID const _GUID_a721791a_0def_4d06_bd91_2118bf1db10b>::CComQIPtr<IWICMetadataQueryWriter,&__s_GUID const _GUID_a721791a_0def_4d06_bd91_2118bf1db10b>(IUnknown *)
0x18001570c  nop
0x18001570d  mov     r8, [rsp+68h+arg_10]; int
0x180015715  test    r8, r8
0x180015718  jnz     short loc_180015721
0x18001571a  mov     ebx, 80004002h
0x18001571f  jmp     short loc_180015776
0x180015721  lea     rax, [rsp+68h+var_18]
0x180015726  mov     [rsp+68h+var_28], rax; __int64
0x18001572b  mov     [rsp+68h+var_30], 0; __int64
0x180015734  mov     [rsp+68h+var_38], 2DBh; unsigned int
0x18001573c  lea     rax, ?gc_rgWritePathIndex@@3QBURULE_LIST_INDEX_ENTRY@@B; RULE_LIST_INDEX_ENTRY const near * const gc_rgWritePathIndex
0x180015743  mov     [rsp+68h+var_40], rax; struct RULE_LIST_INDEX_ENTRY *
0x180015748  lea     r9, ?gc_rgWritePathList@@3QBURULE_PATH_INFO@@B; int
0x18001574f  mov     rdx, rbx; int
0x180015752  mov     rcx, rsi; int
0x180015755  call    ?CreateAndInitializeRuleWriter@CPolicyComponent@@AEAAJPEBGPEAUIWICMetadataQueryWriter@@PEBURULE_PATH_INFO@@IPEBURULE_LIST_INDEX_ENTRY@@IPEAV?$CSimpleArray@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@2@@ATL@@PEAPEAVCRuleWriter@@@Z; CPolicyComponent::CreateAndInitializeRuleWriter(ushort const *,IWICMetadataQueryWriter *,RULE_PATH_INFO const *,uint,RULE_LIST_INDEX_ENTRY const *,uint,ATL::CSimpleArray<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> *,CRuleWriter * *)
0x18001575a  mov     ebx, eax
0x18001575c  test    eax, eax
0x18001575e  js      short loc_180015776
0x180015760  mov     rcx, [rsp+68h+var_18]
0x180015765  mov     rax, [rcx]
0x180015768  mov     rdx, rdi
0x18001576b  mov     rax, [rax+18h]
0x18001576f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015774  mov     ebx, eax
0x180015776  lea     rcx, [rsp+68h+arg_10]
0x18001577e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180015783  nop
0x180015784  jmp     short loc_18001578D
0x180015786  mov     ebx, dword ptr [rsp+68h+arg_10]
0x18001578d  mov     rcx, [rsp+68h+var_18]
0x180015792  test    rcx, rcx
0x180015795  jz      short loc_1800157A7
0x180015797  mov     rdx, [rcx]
0x18001579a  mov     rax, [rdx]
0x18001579d  mov     edx, 1
0x1800157a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157a7  mov     eax, ebx
0x1800157a9  jmp     short loc_1800157B0
0x1800157ab  mov     eax, 80004003h
0x1800157b0  mov     rbx, [rsp+68h+arg_0]
0x1800157b5  mov     rsi, [rsp+68h+arg_8]
0x1800157ba  add     rsp, 60h
0x1800157be  pop     rdi
0x1800157bf  retn
```
