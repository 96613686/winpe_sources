# OSDeploymentInformationFactory::~OSDeploymentInformationFactory(void)

- ea: `0x18004fd6c`
- end: `0x18004ff56`
- name: `??1OSDeploymentInformationFactory@@UEAA@XZ`
- size: `490`
- prototype: `void __fastcall(OSDeploymentInformationFactory *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18004fd30`
- `0x18006be40`

## callees

- `0x180007b6c`
- `0x18000b9bc`
- `0x18004fd6c`
- `0x180050830`
- `0x180050b1c`
- `0x180050dd8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18004fdf8`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18004fe67`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18004fdf8`
- `api-ms-win-core-com-l1-1-0!CoDisconnectObject` at `0x18004fe67`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ff01`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ff1f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ff01`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004ff1f`

## pseudocode

```c
void __fastcall OSDeploymentInformationFactory::~OSDeploymentInformationFactory(OSDeploymentInformationFactory *this)
{
  char *v2; // rsi
  unsigned int v3; // ebp
  char *i; // rdi
  IUnknown *v5; // rcx
  HRESULT v6; // eax
  char *v7; // rbp
  unsigned int j; // esi
  IUnknown *v9; // rcx
  HRESULT v10; // eax
  char *v11; // rcx
  char *v12; // r12
  char *v13; // r14
  int v14; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)this = &OSDeploymentInformationFactory::`vftable';
  *((_QWORD *)this + 6) = &OSDeploymentInformationFactory::`vftable'{for `IDeploymentInformationFactory'};
  *((_QWORD *)this + 7) = &OSDeploymentInformationFactory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWUInternalDeploymentInformationFactory>'};
  v2 = (char *)this + 152;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetImpl'::`2'::impl) )
  {
    v3 = 0;
    for ( i = v2; v3 < *((_DWORD *)v2 + 5); ++v3 )
    {
      v5 = *(IUnknown **)(*((_QWORD *)v2 + 1) + 16LL * v3);
      if ( v5 )
      {
        v6 = CoDisconnectObject(v5, 0);
        if ( v6 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x29,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeployment"
                          "InformationFactory.cpp",
            (const char *)(unsigned int)v6,
            v14);
      }
    }
    CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(
      v2,
      0,
      0xFFFFFFFFLL,
      1);
    v7 = (char *)this + 264;
    for ( j = 0; j < *((_DWORD *)this + 71); ++j )
    {
      v9 = *(IUnknown **)(*((_QWORD *)this + 34) + 16LL * j);
      if ( v9 )
      {
        v10 = CoDisconnectObject(v9, 0);
        if ( v10 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x29,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\DeploymentInformation\\OSDeployment"
                          "InformationFactory.cpp",
            (const char *)(unsigned int)v10,
            v14);
      }
    }
    v11 = (char *)this + 264;
    v12 = (char *)this + 232;
    v13 = (char *)this + 120;
  }
  else
  {
    v13 = (char *)this + 120;
    CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(
      (char *)this + 120,
      0,
      0xFFFFFFFFLL,
      1);
    v11 = (char *)this + 232;
    v7 = (char *)this + 264;
    v12 = (char *)this + 232;
    i = v2;
  }
  CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(
    v11,
    0,
    0xFFFFFFFFLL,
    1);
  CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(v7);
  CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(v12);
  *((_QWORD *)this + 23) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 192));
  CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(i);
  CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(v13);
  *((_QWORD *)this + 9) = &CSusLock::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 2);
  *((_DWORD *)this + 17) = -1073741823;
  *(_QWORD *)this = &CWuaSingletonClassFactory::`vftable';
  CWuaClassFactoryBase::~CWuaClassFactoryBase(this);
}

```

## disassembly

```asm
0x18004fd6c  mov     [rsp+arg_0], rbx
0x18004fd71  mov     [rsp+arg_8], rbp
0x18004fd76  mov     [rsp+arg_10], rsi
0x18004fd7b  push    rdi
0x18004fd7c  push    r12
0x18004fd7e  push    r14; int
0x18004fd80  sub     rsp, 20h
0x18004fd84  mov     rbx, rcx
0x18004fd87  lea     rax, ??_7OSDeploymentInformationFactory@@6B@; const OSDeploymentInformationFactory::`vftable'
0x18004fd8e  mov     [rcx], rax
0x18004fd91  lea     rax, ??_7OSDeploymentInformationFactory@@6BIDeploymentInformationFactory@@@; const OSDeploymentInformationFactory::`vftable'{for `IDeploymentInformationFactory'}
0x18004fd98  mov     [rcx+30h], rax
0x18004fd9c  lea     rax, ??_7OSDeploymentInformationFactory@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIWUInternalDeploymentInformationFactory@@@Details@WRL@Microsoft@@@; const OSDeploymentInformationFactory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWUInternalDeploymentInformationFactory>'}
0x18004fda3  mov     [rcx+38h], rax
0x18004fda7  lea     rsi, [rcx+98h]
0x18004fdae  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::GetImpl(void)'::`2'::impl
0x18004fdb5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_CoDisconnectDeploymentStubs>::__private_IsEnabled(void)
0x18004fdba  test    al, al
0x18004fdbc  jz      loc_18004FE9F
0x18004fdc2  xor     ebp, ebp
0x18004fdc4  mov     eax, [rsi+14h]
0x18004fdc7  mov     rdi, rsi
0x18004fdca  lea     r12, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18004fdd1  test    eax, eax
0x18004fdd3  jz      short loc_18004FE20
0x18004fdd5  cmp     ebp, eax
0x18004fdd7  jb      short loc_18004FDE4
0x18004fdd9  mov     r9d, 80240007h
0x18004fddf  lea     edx, [rbp+27h]
0x18004fde2  jmp     short loc_18004FE0A
0x18004fde4  mov     ecx, ebp
0x18004fde6  add     rcx, rcx
0x18004fde9  mov     rax, [rsi+8]
0x18004fded  mov     rcx, [rax+rcx*8]; pUnk
0x18004fdf1  test    rcx, rcx
0x18004fdf4  jz      short loc_18004FE17
0x18004fdf6  xor     edx, edx; dwReserved
0x18004fdf8  call    cs:__imp_CoDisconnectObject
0x18004fdfe  test    eax, eax
0x18004fe00  jns     short loc_18004FE17
0x18004fe02  mov     r9d, eax; char *
0x18004fe05  mov     edx, 29h ; ')'; void *
0x18004fe0a  mov     r8, r12; unsigned int
0x18004fe0d  mov     rcx, [rsp+38h]; this
0x18004fe12  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004fe17  inc     ebp
0x18004fe19  mov     eax, [rsi+14h]
0x18004fe1c  cmp     ebp, eax
0x18004fe1e  jb      short loc_18004FDE4
0x18004fe20  mov     r9d, 1
0x18004fe26  or      r8d, 0FFFFFFFFh
0x18004fe2a  xor     edx, edx
0x18004fe2c  mov     rcx, rsi
0x18004fe2f  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentProgress@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentProgress@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x18004fe34  lea     rbp, [rbx+108h]
0x18004fe3b  xor     esi, esi
0x18004fe3d  mov     eax, [rbp+14h]
0x18004fe40  test    eax, eax
0x18004fe42  jz      short loc_18004FE8F
0x18004fe44  cmp     esi, eax
0x18004fe46  jb      short loc_18004FE53
0x18004fe48  mov     r9d, 80240007h
0x18004fe4e  lea     edx, [rsi+27h]
0x18004fe51  jmp     short loc_18004FE79
0x18004fe53  mov     ecx, esi
0x18004fe55  add     rcx, rcx
0x18004fe58  mov     rax, [rbp+8]
0x18004fe5c  mov     rcx, [rax+rcx*8]; pUnk
0x18004fe60  test    rcx, rcx
0x18004fe63  jz      short loc_18004FE86
0x18004fe65  xor     edx, edx; dwReserved
0x18004fe67  call    cs:__imp_CoDisconnectObject
0x18004fe6d  test    eax, eax
0x18004fe6f  jns     short loc_18004FE86
0x18004fe71  mov     r9d, eax; char *
0x18004fe74  mov     edx, 29h ; ')'; void *
0x18004fe79  mov     r8, r12; unsigned int
0x18004fe7c  mov     rcx, [rsp+38h]; this
0x18004fe81  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004fe86  inc     esi
0x18004fe88  mov     eax, [rbp+14h]
0x18004fe8b  cmp     esi, eax
0x18004fe8d  jb      short loc_18004FE53
0x18004fe8f  mov     rcx, rbp
0x18004fe92  lea     r12, [rbx+0E8h]
0x18004fe99  lea     r14, [rbx+78h]
0x18004fe9d  jmp     short loc_18004FECB
0x18004fe9f  lea     r14, [rbx+78h]
0x18004fea3  mov     r9d, 1
0x18004fea9  or      r8d, 0FFFFFFFFh
0x18004fead  xor     edx, edx
0x18004feaf  mov     rcx, r14
0x18004feb2  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentProgress@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentProgress@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x18004feb7  lea     rcx, [rbx+0E8h]
0x18004febe  lea     rbp, [rbx+108h]
0x18004fec5  mov     r12, rcx
0x18004fec8  mov     rdi, rsi
0x18004fecb  mov     r9d, 1
0x18004fed1  or      r8d, 0FFFFFFFFh
0x18004fed5  xor     edx, edx
0x18004fed7  call    ?RemoveArraySection@?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentProgress@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentProgress@@@@@@VCMapEntryOps@2@@@IEAAXKKH@Z; CSusArrayList<CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentProgress *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentProgress *>>::CMapEntryOps>::RemoveArraySection(ulong,ulong,int)
0x18004fedc  mov     rcx, rbp
0x18004fedf  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentInformation@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(void)
0x18004fee4  mov     rcx, r12
0x18004fee7  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentInformation@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(void)
0x18004feec  lea     rsi, ??_7CSusLock@@6B@; const CSusLock::`vftable'
0x18004fef3  mov     [rbx+0B8h], rsi
0x18004fefa  lea     rcx, [rbx+0C0h]; lpCriticalSection
0x18004ff01  call    cs:__imp_DeleteCriticalSection
0x18004ff07  mov     rcx, rdi
0x18004ff0a  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentInformation@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(void)
0x18004ff0f  mov     rcx, r14
0x18004ff12  call    ??1?$CSusArrayList@U_tagMapEntry@?$CSusMap@PEA_WPEAUIDeploymentInformation@@VCSusSortedArrayListItemOpsLPWSTR@@V?$CSusArrayListItemOpInterfacePtr@PEAUIDeploymentInformation@@@@@@VCMapEntryOps@2@@@UEAA@XZ; CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>::~CSusArrayList<CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::_tagMapEntry,CSusMap<wchar_t *,IDeploymentInformation *,CSusSortedArrayListItemOpsLPWSTR,CSusArrayListItemOpInterfacePtr<IDeploymentInformation *>>::CMapEntryOps>(void)
0x18004ff17  mov     [rbx+48h], rsi
0x18004ff1b  lea     rcx, [rbx+50h]; lpCriticalSection
0x18004ff1f  call    cs:__imp_DeleteCriticalSection
0x18004ff25  mov     dword ptr [rbx+44h], 0C0000001h
0x18004ff2c  lea     rax, ??_7CWuaSingletonClassFactory@@6B@; const CWuaSingletonClassFactory::`vftable'
0x18004ff33  mov     [rbx], rax
0x18004ff36  mov     rcx, rbx; this
0x18004ff39  mov     rbx, [rsp+38h+arg_0]
0x18004ff3e  mov     rbp, [rsp+38h+arg_8]
0x18004ff43  mov     rsi, [rsp+38h+arg_10]
0x18004ff48  add     rsp, 20h
0x18004ff4c  pop     r14
0x18004ff4e  pop     r12
0x18004ff50  pop     rdi
0x18004ff51  jmp     ??1CWuaClassFactoryBase@@MEAA@XZ; CWuaClassFactoryBase::~CWuaClassFactoryBase(void)
```
