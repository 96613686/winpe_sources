# HNS::Service::Network::Endpoint::Attach(uint,ushort const *)

- ea: `0x18014bf24`
- end: `0x18014c5d4`
- name: `?Attach@Endpoint@Network@Service@HNS@@QEAAXIPEBG@Z`
- size: `1712`
- prototype: `void __fastcall(HNS::Service::Network::Endpoint *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `37`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x1801060cc`

## callees

- `0x180003920`
- `0x180003a58`
- `0x18005f0c0`
- `0x18005f560`
- `0x18005ffc4`
- `0x180061240`
- `0x180064754`
- `0x180064814`
- `0x180064b4c`
- `0x180065d70`
- `0x1800666b4`
- `0x1800677fc`
- `0x18006c530`
- `0x1800759d8`
- `0x180075aac`
- `0x1800776d8`
- `0x180077db0`
- `0x18008ac10`
- `0x1800a25e8`
- `0x1800a49ec`
- `0x1800b5c7c`
- `0x1800b65d8`
- `0x1800bb77c`
- `0x180114da8`
- `0x180115b50`
- `0x18014ae74`
- `0x18014bf24`
- `0x18014eb58`
- `0x1801512d8`
- `0x180154a40`
- `0x180157738`
- `0x1801578a0`
- `0x1801586e4`
- `0x180174b20`
- `0x18019a920`
- `0x18019ace0`
- `0x1802b7010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18014c4a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18014c52a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18014c4a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18014c52a`

## string_xrefs

- `0x18014c5c2`: `onecore\vm\dv\net\hns\service\entity\endpoint\endpoint.cpp`
- `0x18014bf67`: `HNS::Service::Network::Endpoint::Attach`
- `0x18014c1e5`: `HNS::Service::Network::Endpoint::Attach`
- `0x18014c382`: `HNS::Service::Network::Endpoint::Attach`
- `0x18014c55a`: `HNS::Service::Network::Endpoint::Attach`
- `0x18014c1cd`: `AlreadyAttached`
- `0x18014c45b`: `HNS::Service::Resource::PortResource::GetVFPPortState`
- `0x18014c4ad`: `HNS::Service::Resource::PortResource::GetVFPPortState`
- `0x18014c4ec`: `HNS::Service::Resource::PortResource::UnblockVFPPort`
- `0x18014c535`: `HNS::Service::Resource::PortResource::UnblockVFPPort`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall HNS::Service::Network::Endpoint::Attach(
        HNS::Service::Network::Endpoint *this,
        unsigned int a2,
        const unsigned __int16 *a3)
{
  bool v6; // r13
  __int64 *v7; // rsi
  const unsigned __int16 *v8; // rdx
  RTL_SRWLOCK *v9; // rcx
  __int64 v10; // rax
  char *v11; // rdi
  volatile signed __int32 *v12; // rdi
  PSRWLOCK *v13; // rax
  unsigned int v14; // eax
  char *v15; // rdi
  int v16; // ebx
  int v17; // r8d
  int v18; // r9d
  const unsigned __int16 *v19; // rdx
  RTL_SRWLOCK *v20; // rcx
  __int64 v21; // rax
  PSRWLOCK v22; // rdi
  int v23; // edi
  int v24; // r8d
  int v25; // r9d
  volatile signed __int32 *v26; // rdi
  __int64 v27; // rax
  HNS::Service::Network::Endpoint *v28; // rcx
  __int64 v29; // rbx
  bool State; // di
  VfpPort *v31; // rcx
  __int64 v32; // rbx
  VfpPort *v33; // rcx
  unsigned int v34; // eax
  int v35; // [rsp+20h] [rbp-E0h]
  bool v36; // [rsp+50h] [rbp-B0h]
  unsigned int v37; // [rsp+54h] [rbp-ACh] BYREF
  const wchar_t *v38; // [rsp+58h] [rbp-A8h] BYREF
  void *v39[2]; // [rsp+60h] [rbp-A0h] BYREF
  PSRWLOCK SRWLock[2]; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v41; // [rsp+80h] [rbp-80h] BYREF
  volatile signed __int32 *v42; // [rsp+88h] [rbp-78h]
  void *v43[2]; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v44; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v45[3]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v46; // [rsp+C8h] [rbp-38h]
  _QWORD v47[42]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  v37 = a2;
  HNSTraceProvider::TraceEnter("HNS::Service::Network::Endpoint::Attach", 0x4DBu);
  HNSObject::Get<_GUID>(*((_QWORD *)this + 101), &v44, (char *)this + 752);
  wil::ActivityBase<HNSTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<HNSTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v47,
    "EndpointAttachShared");
  v47[0] = &HNSTraceProvider::EndpointAttachShared::`vftable';
  HNSTraceProvider::EndpointAttachShared::StartActivity((HNSTraceProvider::EndpointAttachShared *)v47, &v44, a2, a3);
  HNS::Service::Interface::IEntity::ValidateAndThrow(this);
  if ( (unsigned __int8)Property<unsigned long>::get((char *)this + 496) != 2
    && (unsigned __int8)Property<unsigned long>::get((char *)this + 496) != 3 )
  {
    v6 = 0;
    HNS::Service::Network::Endpoint::Attach(this, a2);
    v7 = (__int64 *)((char *)this + 1864);
    std::static_pointer_cast<HNS::Service::Resource::HostPortResource,HNS::Service::Resource::PortResource>(
      &v41,
      (char *)this + 1864);
    HNSObject::Get<std::wstring>(*((_QWORD *)v41 + 327), v45, v41 + 1280);
    v8 = (const unsigned __int16 *)v45;
    if ( v46 > 7 )
      v8 = v45[0];
    IPHelper::MergeHostKeysToContainer(a3, v8);
    std::wstring::~wstring(v45);
    v9 = *(RTL_SRWLOCK **)Property<wil::com_ptr_t<HNSStringList,wil::err_exception_policy>>::get(
                            (char *)this + 1128,
                            v39);
    SRWLock[0] = (PSRWLOCK)a3;
    v10 = -1;
    do
      ++v10;
    while ( a3[v10] );
    SRWLock[1] = (PSRWLOCK)v10;
    v44 = GUID_NULL;
    HNSStringList::AddString(v9);
    v11 = (char *)v39[0];
    if ( v39[0] && _InterlockedExchangeAdd((volatile signed __int32 *)v39[0] + 10, 0xFFFFFFFF) == 1 && v11 )
    {
      std::vector<std::wstring>::_Tidy(v11 + 16);
      operator delete(v11, (const struct std::nothrow_t *)0x40);
    }
    v12 = v42;
    if ( v42 )
    {
      if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
        if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
      }
    }
LABEL_38:
    v27 = *((_QWORD *)this + 1);
    v38 = (const wchar_t *)v27;
    if ( v27 )
      _InterlockedIncrement((volatile signed __int32 *)(v27 + 16));
    if ( (unsigned __int8)HNS::Service::Policy::BasePolicy::ObjectHasPolicyOfType(&v38, L"VmNic") )
    {
      HNS::Service::Network::Endpoint::SendNetChangeNotification(v28, v37);
    }
    else
    {
      if ( v6 )
      {
        memset_0(v45, 0, 0x40u);
        v29 = *v7;
        HNSTraceProvider::TraceEnter("HNS::Service::Resource::PortResource::GetVFPPortState", 0x1A5u);
        State = 0;
        (*(void (__fastcall **)(__int64, PSRWLOCK *))(*(_QWORD *)(v29 + 32) + 8LL))(v29 + 32, SRWLock);
        v31 = *(VfpPort **)(v29 + 2200);
        if ( v31 )
          State = VfpPort::GetState(v31, (struct _VFX_PORT_STATE *)v45);
        if ( SRWLock[0] )
          ReleaseSRWLockExclusive(SRWLock[0]);
        HNSTraceProvider::TraceSuccess("HNS::Service::Resource::PortResource::GetVFPPortState", 0x1B1u);
        if ( !State || BYTE1(v45[0]) )
          v6 = 0;
      }
      HNS::Service::Network::Endpoint::Disconnect(this);
      HNS::Service::Network::Endpoint::Connect(this);
      HNS::Service::Network::Endpoint::SendNetworkChangeStatus(this);
      if ( v6 )
      {
        v32 = *v7;
        HNSTraceProvider::TraceEnter("HNS::Service::Resource::PortResource::UnblockVFPPort", 0x190u);
        (*(void (__fastcall **)(__int64, PSRWLOCK *))(*(_QWORD *)(v32 + 32) + 8LL))(v32 + 32, SRWLock);
        v33 = *(VfpPort **)(v32 + 2200);
        if ( v33 )
          VfpPort::Unblock(v33);
        if ( SRWLock[0] )
          ReleaseSRWLockExclusive(SRWLock[0]);
        HNSTraceProvider::TraceSuccess("HNS::Service::Resource::PortResource::UnblockVFPPort", 0x19Cu);
      }
    }
    wil::ActivityBase<HNSTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v47);
    HNSTraceProvider::TraceSuccess("HNS::Service::Network::Endpoint::Attach", 0x546u);
    goto LABEL_57;
  }
  v13 = (PSRWLOCK *)Property<wil::com_ptr_t<HNSStringList,wil::err_exception_policy>>::get((char *)this + 1128, v43);
  v14 = HNSStringList::Count(*v13);
  LODWORD(v39[0]) = v14;
  v15 = (char *)v43[0];
  if ( v43[0] && _InterlockedExchangeAdd((volatile signed __int32 *)v43[0] + 10, 0xFFFFFFFF) == 1 && v15 )
  {
    std::vector<std::wstring>::_Tidy(v15 + 16);
    operator delete(v15, (const struct std::nothrow_t *)0x40);
    v14 = (unsigned int)v39[0];
  }
  if ( !v14 )
  {
    v34 = wil::verify_hresult<long>(2151350301LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x4ED,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\entity\\endpoint\\endpoint.cpp",
      (const char *)v34,
      v35);
  }
  if ( !HNS::Service::Network::Endpoint::IsAttachedToContainer(this, a3) )
  {
    v7 = (__int64 *)((char *)this + 1864);
    std::static_pointer_cast<HNS::Service::Resource::HostPortResource,HNS::Service::Resource::PortResource>(
      &v44,
      (char *)this + 1864);
    v36 = *((_QWORD *)this + 233) != 0;
    HNSObject::Get<std::wstring>(*(_QWORD *)(*(_QWORD *)&v44.Data1 + 2616LL), v45, *(_QWORD *)&v44.Data1 + 2560LL);
    v19 = (const unsigned __int16 *)v45;
    if ( v46 > 7 )
      v19 = v45[0];
    IPHelper::MergeHostKeysToContainer(a3, v19);
    std::wstring::~wstring(v45);
    v20 = *(RTL_SRWLOCK **)Property<wil::com_ptr_t<HNSStringList,wil::err_exception_policy>>::get(
                             (char *)this + 1128,
                             SRWLock);
    v41 = a3;
    v21 = -1;
    do
      ++v21;
    while ( a3[v21] );
    v42 = (volatile signed __int32 *)v21;
    *(GUID *)v43 = GUID_NULL;
    HNSStringList::AddString(v20);
    v22 = SRWLock[0];
    if ( SRWLock[0] && _InterlockedExchangeAdd((volatile signed __int32 *)&SRWLock[0][5], 0xFFFFFFFF) == 1 && v22 )
    {
      std::vector<std::wstring>::_Tidy(&v22[2]);
      operator delete(v22, (const struct std::nothrow_t *)0x40);
    }
    LODWORD(v39[0]) = 3;
    *(_OWORD *)SRWLock = *((_OWORD *)this + 33);
    HNSObject::Set<unsigned long>(*((_QWORD *)this + 69), (char *)this + 496, v39, *((unsigned int *)this + 136));
    v23 = qword_18039AA48;
    if ( *(_DWORD *)qword_18039AA48 > 5u )
    {
      LODWORD(v39[0]) = v37;
      HNSObject::Get<_GUID>(*((_QWORD *)this + 101), v45, (char *)this + 752);
      SRWLock[0] = (PSRWLOCK)v45;
      v41 = a3;
      LODWORD(v38) = 1300;
      v43[0] = (void *)"HNS::Service::Network::Endpoint::Attach";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        v23,
        (unsigned int)qword_18033BF78,
        v24,
        v25,
        (__int64)v43,
        (__int64)&v38,
        (__int64)&v41,
        (__int64)SRWLock,
        (__int64)v39);
    }
    v26 = *(volatile signed __int32 **)v44.Data4;
    if ( *(_QWORD *)v44.Data4 )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v44.Data4 + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
        if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
      }
    }
    v6 = v36;
    goto LABEL_38;
  }
  v16 = qword_18039AA48;
  if ( *(_DWORD *)qword_18039AA48 > 5u )
  {
    LODWORD(v39[0]) = v37;
    HNSObject::Get<_GUID>(*((_QWORD *)this + 101), &v44, (char *)this + 752);
    v43[0] = &v44;
    v38 = L"AlreadyAttached";
    v41 = a3;
    v37 = 1273;
    SRWLock[0] = (PSRWLOCK)"HNS::Service::Network::Endpoint::Attach";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v16,
      (unsigned int)&byte_18033BD57,
      v17,
      v18,
      (__int64)SRWLock,
      (__int64)&v37,
      (__int64)&v41,
      (__int64)&v38,
      (__int64)v43,
      (__int64)v39);
  }
LABEL_57:
  v47[0] = &HNSTraceProvider::EndpointAttachShared::`vftable';
  wil::ActivityBase<HNSTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(v47);
  wil::ActivityBase<HNSTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<HNSTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(v47);
}

```

## disassembly

```asm
0x18014bf24  mov     [rsp-8+arg_18], rbx
0x18014bf29  push    rbp
0x18014bf2a  push    rsi
0x18014bf2b  push    rdi
0x18014bf2c  push    r12
0x18014bf2e  push    r13
0x18014bf30  push    r14
0x18014bf32  push    r15
0x18014bf34  lea     rbp, [rsp-150h]
0x18014bf3c  sub     rsp, 250h
0x18014bf43  mov     rax, cs:__security_cookie
0x18014bf4a  xor     rax, rsp
0x18014bf4d  mov     [rbp+180h+var_40], rax
0x18014bf54  mov     r15, r8
0x18014bf57  mov     ebx, edx
0x18014bf59  mov     [rsp+280h+var_22C], edx
0x18014bf5d  mov     r14, rcx
0x18014bf60  xor     edi, edi
0x18014bf62  mov     edx, 4DBh; unsigned int
0x18014bf67  lea     rcx, aHnsServiceNetw_51; "HNS::Service::Network::Endpoint::Attach"
0x18014bf6e  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x18014bf73  nop
0x18014bf74  lea     rsi, [r14+2F0h]
0x18014bf7b  mov     r8, rsi
0x18014bf7e  lea     rdx, [rbp+180h+var_1E0]
0x18014bf82  mov     rcx, [rsi+38h]
0x18014bf86  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x18014bf8b  nop
0x18014bf8c  lea     rdx, aEndpointattach; "EndpointAttachShared"
0x18014bf93  lea     rcx, [rbp+180h+var_190]
0x18014bf97  call    ??0?$ActivityBase@VHNSTraceProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<HNSTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<HNSTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18014bf9c  lea     rax, ??_7EndpointAttachShared@HNSTraceProvider@@6B@; const HNSTraceProvider::EndpointAttachShared::`vftable'
0x18014bfa3  mov     [rbp+180h+var_190], rax
0x18014bfa7  movaps  xmm0, xmmword ptr [rbp+180h+var_1E0.Data1]
0x18014bfab  movdqa  xmmword ptr [rbp+180h+var_1E0.Data1], xmm0
0x18014bfb0  mov     r9, r15; unsigned __int16 *
0x18014bfb3  mov     r8d, ebx; unsigned int
0x18014bfb6  lea     rdx, [rbp+180h+var_1E0]; struct _GUID
0x18014bfba  lea     rcx, [rbp+180h+var_190]; this
0x18014bfbe  call    ?StartActivity@EndpointAttachShared@HNSTraceProvider@@QEAAXU_GUID@@IPEBG@Z; HNSTraceProvider::EndpointAttachShared::StartActivity(_GUID,uint,ushort const *)
0x18014bfc3  nop
0x18014bfc4  mov     rcx, r14; this
0x18014bfc7  call    ?ValidateAndThrow@IEntity@Interface@Service@HNS@@QEAAXXZ; HNS::Service::Interface::IEntity::ValidateAndThrow(void)
0x18014bfcc  nop
0x18014bfcd  lea     r13, [r14+1F0h]
0x18014bfd4  mov     rcx, r13
0x18014bfd7  call    ?get@?$Property@K@@QEBA?BKXZ; Property<ulong>::get(void)
0x18014bfdc  nop
0x18014bfdd  cmp     al, 2
0x18014bfdf  jz      loc_18014C126
0x18014bfe5  mov     rcx, r13
0x18014bfe8  call    ?get@?$Property@K@@QEBA?BKXZ; Property<ulong>::get(void)
0x18014bfed  nop
0x18014bfee  cmp     al, 3
0x18014bff0  jz      loc_18014C126
0x18014bff6  mov     r13b, dil
0x18014bff9  mov     r8b, 1; bool
0x18014bffc  mov     edx, ebx; unsigned int
0x18014bffe  mov     rcx, r14; this
0x18014c001  call    ?Attach@Endpoint@Network@Service@HNS@@AEAAXI_N@Z; HNS::Service::Network::Endpoint::Attach(uint,bool)
0x18014c006  lea     rsi, [r14+748h]
0x18014c00d  mov     rdx, rsi
0x18014c010  lea     rcx, [rbp+180h+var_200]
0x18014c014  call    ??$static_pointer_cast@VHostPortResource@Resource@Service@HNS@@VPortResource@234@@std@@YA?AV?$shared_ptr@VHostPortResource@Resource@Service@HNS@@@0@AEBV?$shared_ptr@VPortResource@Resource@Service@HNS@@@0@@Z; std::static_pointer_cast<HNS::Service::Resource::HostPortResource,HNS::Service::Resource::PortResource>(std::shared_ptr<HNS::Service::Resource::PortResource> const &)
0x18014c019  nop
0x18014c01a  mov     rcx, [rbp+180h+var_200]
0x18014c01e  lea     r8, [rcx+0A00h]
0x18014c025  lea     rdx, [rbp+180h+var_1D0]
0x18014c029  mov     rcx, [rcx+0A38h]
0x18014c030  call    ??$Get@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@HNSObject@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; HNSObject::Get<std::wstring>(std::wstring const &)
0x18014c035  nop
0x18014c036  lea     rdx, [rbp+180h+var_1D0]
0x18014c03a  cmp     [rbp+180h+var_1B8], 7
0x18014c03f  cmova   rdx, [rbp+180h+var_1D0]; unsigned __int16 *
0x18014c044  mov     rcx, r15; unsigned __int16 *
0x18014c047  call    ?MergeHostKeysToContainer@IPHelper@@SAXQEBGPEBG@Z; IPHelper::MergeHostKeysToContainer(ushort const * const,ushort const *)
0x18014c04c  nop
0x18014c04d  lea     rcx, [rbp+180h+var_1D0]; void *
0x18014c051  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18014c056  lea     rcx, [r14+468h]
0x18014c05d  lea     rdx, [rsp+280h+var_220]
0x18014c062  call    ?get@?$Property@V?$com_ptr_t@VHNSStringList@@Uerr_exception_policy@wil@@@wil@@@@QEBA?BV?$com_ptr_t@VHNSStringList@@Uerr_exception_policy@wil@@@wil@@XZ; Property<wil::com_ptr_t<HNSStringList,wil::err_exception_policy>>::get(void)
0x18014c067  nop
0x18014c068  mov     rcx, [rax]; SRWLock
0x18014c06b  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18014c072  mov     [rsp+280h+SRWLock], r15
0x18014c077  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18014c07b  mov     rax, rbx
0x18014c07e  inc     rax
0x18014c081  cmp     [r15+rax*2], di
0x18014c086  jnz     short loc_18014C07E
0x18014c088  mov     [rsp+280h+SRWLock+8], rax
0x18014c08d  movdqu  xmmword ptr [rbp+180h+var_1E0.Data1], xmm0
0x18014c092  lea     r8, [rbp+180h+var_1E0]
0x18014c096  lea     rdx, [rsp+280h+SRWLock]
0x18014c09b  call    ?AddString@HNSStringList@@QEAAXAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@U_GUID@@@Z; HNSStringList::AddString(std::basic_string_view<ushort> const &,_GUID)
0x18014c0a0  nop
0x18014c0a1  mov     r12d, 40h ; '@'
0x18014c0a7  mov     rdi, [rsp+280h+var_220]
0x18014c0ac  xor     r15d, r15d
0x18014c0af  test    rdi, rdi
0x18014c0b2  jz      short loc_18014C0D9
0x18014c0b4  mov     eax, ebx
0x18014c0b6  lock xadd [rdi+28h], eax
0x18014c0bb  add     eax, ebx
0x18014c0bd  jnz     short loc_18014C0D9
0x18014c0bf  test    rdi, rdi
0x18014c0c2  jz      short loc_18014C0D9
0x18014c0c4  lea     rcx, [rdi+10h]
0x18014c0c8  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18014c0cd  mov     edx, r12d; struct std::nothrow_t *
0x18014c0d0  mov     rcx, rdi; void *
0x18014c0d3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18014c0d8  nop
0x18014c0d9  mov     rdi, [rbp+180h+var_1F8]
0x18014c0dd  test    rdi, rdi
0x18014c0e0  jz      loc_18014C411
0x18014c0e6  mov     eax, ebx
0x18014c0e8  lock xadd [rdi+8], eax
0x18014c0ed  add     eax, ebx
0x18014c0ef  jnz     loc_18014C411
0x18014c0f5  mov     rax, [rdi]
0x18014c0f8  mov     rcx, rdi
0x18014c0fb  mov     rax, [rax]
0x18014c0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014c103  mov     eax, ebx
0x18014c105  lock xadd [rdi+0Ch], eax
0x18014c10a  add     eax, ebx
0x18014c10c  jnz     loc_18014C411
0x18014c112  mov     rax, [rdi]
0x18014c115  mov     rcx, rdi
0x18014c118  mov     rax, [rax+8]
0x18014c11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014c121  jmp     loc_18014C411
0x18014c126  lea     rcx, [r14+468h]
0x18014c12d  lea     rdx, [rbp+180h+var_1F0]
0x18014c131  call    ?get@?$Property@V?$com_ptr_t@VHNSStringList@@Uerr_exception_policy@wil@@@wil@@@@QEBA?BV?$com_ptr_t@VHNSStringList@@Uerr_exception_policy@wil@@@wil@@XZ; Property<wil::com_ptr_t<HNSStringList,wil::err_exception_policy>>::get(void)
0x18014c136  mov     rcx, [rax]; SRWLock
0x18014c139  call    ?Count@HNSStringList@@QEBAKXZ; HNSStringList::Count(void)
0x18014c13e  mov     dword ptr [rsp+280h+var_220], eax
0x18014c142  mov     r12d, 40h ; '@'
0x18014c148  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18014c14c  mov     rdi, [rbp+180h+var_1F0]
0x18014c150  test    rdi, rdi
0x18014c153  jz      short loc_18014C17D
0x18014c155  mov     ecx, ebx
0x18014c157  lock xadd [rdi+28h], ecx
0x18014c15c  add     ecx, ebx
0x18014c15e  jnz     short loc_18014C17D
0x18014c160  test    rdi, rdi
0x18014c163  jz      short loc_18014C17D
0x18014c165  lea     rcx, [rdi+10h]
0x18014c169  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18014c16e  mov     edx, r12d; struct std::nothrow_t *
0x18014c171  mov     rcx, rdi; void *
0x18014c174  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18014c179  mov     eax, dword ptr [rsp+280h+var_220]
0x18014c17d  xor     edi, edi
0x18014c17f  test    eax, eax
0x18014c181  jz      loc_18014C5AE
0x18014c187  mov     rdx, r15; unsigned __int16 *
0x18014c18a  mov     rcx, r14; this
0x18014c18d  call    ?IsAttachedToContainer@Endpoint@Network@Service@HNS@@AEAA_NPEBG@Z; HNS::Service::Network::Endpoint::IsAttachedToContainer(ushort const *)
0x18014c192  test    al, al
0x18014c194  jz      loc_18014C23F
0x18014c19a  mov     rbx, cs:qword_18039AA48
0x18014c1a1  mov     eax, [rbx]
0x18014c1a3  cmp     eax, 5
0x18014c1a6  jbe     loc_18014C567
0x18014c1ac  mov     eax, [rsp+280h+var_22C]
0x18014c1b0  mov     dword ptr [rsp+280h+var_220], eax
0x18014c1b4  mov     r8, rsi
0x18014c1b7  lea     rdx, [rbp+180h+var_1E0]
0x18014c1bb  mov     rcx, [rsi+38h]
0x18014c1bf  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x18014c1c4  nop
0x18014c1c5  lea     rax, [rbp+180h+var_1E0]
0x18014c1c9  mov     [rbp+180h+var_1F0], rax
0x18014c1cd  lea     rax, aAlreadyattache; "AlreadyAttached"
0x18014c1d4  mov     [rsp+280h+var_228], rax
0x18014c1d9  mov     [rbp+180h+var_200], r15
0x18014c1dd  mov     [rsp+280h+var_22C], 4F9h
0x18014c1e5  lea     rax, aHnsServiceNetw_51; "HNS::Service::Network::Endpoint::Attach"
0x18014c1ec  mov     [rsp+280h+SRWLock], rax
0x18014c1f1  lea     rax, [rsp+280h+var_220]
0x18014c1f6  mov     [rsp+280h+var_238], rax
0x18014c1fb  lea     rax, [rbp+180h+var_1F0]
0x18014c1ff  mov     [rsp+280h+var_240], rax
0x18014c204  lea     rax, [rsp+280h+var_228]
0x18014c209  mov     [rsp+280h+var_248], rax
0x18014c20e  lea     rax, [rbp+180h+var_200]
0x18014c212  mov     [rsp+280h+var_250], rax
0x18014c217  lea     rax, [rsp+280h+var_22C]
0x18014c21c  mov     [rsp+280h+var_258], rax
0x18014c221  lea     rax, [rsp+280h+SRWLock]
0x18014c226  mov     [rsp+280h+var_260], rax
0x18014c22b  lea     rdx, byte_18033BD57
0x18014c232  mov     rcx, rbx
0x18014c235  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18014c23a  jmp     loc_18014C567
0x18014c23f  lea     rsi, [r14+748h]
0x18014c246  mov     rdx, rsi
0x18014c249  lea     rcx, [rbp+180h+var_1E0]
0x18014c24d  call    ??$static_pointer_cast@VHostPortResource@Resource@Service@HNS@@VPortResource@234@@std@@YA?AV?$shared_ptr@VHostPortResource@Resource@Service@HNS@@@0@AEBV?$shared_ptr@VPortResource@Resource@Service@HNS@@@0@@Z; std::static_pointer_cast<HNS::Service::Resource::HostPortResource,HNS::Service::Resource::PortResource>(std::shared_ptr<HNS::Service::Resource::PortResource> const &)
0x18014c252  nop
0x18014c253  cmp     [rsi], rdi
0x18014c256  setnz   [rsp+280h+var_230]
0x18014c25b  mov     rcx, qword ptr [rbp+180h+var_1E0.Data1]
0x18014c25f  lea     r8, [rcx+0A00h]
0x18014c266  lea     rdx, [rbp+180h+var_1D0]
0x18014c26a  mov     rcx, [rcx+0A38h]
0x18014c271  call    ??$Get@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@HNSObject@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; HNSObject::Get<std::wstring>(std::wstring const &)
0x18014c276  nop
0x18014c277  lea     rdx, [rbp+180h+var_1D0]
0x18014c27b  cmp     [rbp+180h+var_1B8], 7
0x18014c280  cmova   rdx, [rbp+180h+var_1D0]; unsigned __int16 *
0x18014c285  mov     rcx, r15; unsigned __int16 *
0x18014c288  call    ?MergeHostKeysToContainer@IPHelper@@SAXQEBGPEBG@Z; IPHelper::MergeHostKeysToContainer(ushort const * const,ushort const *)
0x18014c28d  nop
0x18014c28e  lea     rcx, [rbp+180h+var_1D0]; void *
0x18014c292  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18014c297  lea     rdx, [rsp+280h+SRWLock]
0x18014c29c  lea     rcx, [r14+468h]
0x18014c2a3  call    ?get@?$Property@V?$com_ptr_t@VHNSStringList@@Uerr_exception_policy@wil@@@wil@@@@QEBA?BV?$com_ptr_t@VHNSStringList@@Uerr_exception_policy@wil@@@wil@@XZ; Property<wil::com_ptr_t<HNSStringList,wil::err_exception_policy>>::get(void)
0x18014c2a8  nop
0x18014c2a9  mov     rcx, [rax]; SRWLock
0x18014c2ac  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x18014c2b3  mov     [rbp+180h+var_200], r15
0x18014c2b7  mov     rax, rbx
0x18014c2ba  inc     rax
0x18014c2bd  cmp     [r15+rax*2], di
0x18014c2c2  jnz     short loc_18014C2BA
0x18014c2c4  mov     [rbp+180h+var_1F8], rax
0x18014c2c8  movdqu  xmmword ptr [rbp+180h+var_1F0], xmm0
0x18014c2cd  lea     r8, [rbp+180h+var_1F0]
0x18014c2d1  lea     rdx, [rbp+180h+var_200]
0x18014c2d5  call    ?AddString@HNSStringList@@QEAAXAEBV?$basic_string_view@GU?$char_traits@G@std@@@std@@U_GUID@@@Z; HNSStringList::AddString(std::basic_string_view<ushort> const &,_GUID)
0x18014c2da  nop
0x18014c2db  mov     rdi, [rsp+280h+SRWLock]
0x18014c2e0  test    rdi, rdi
0x18014c2e3  jz      short loc_18014C309
0x18014c2e5  mov     eax, ebx
0x18014c2e7  lock xadd [rdi+28h], eax
0x18014c2ec  add     eax, ebx
0x18014c2ee  jnz     short loc_18014C309
0x18014c2f0  test    rdi, rdi
0x18014c2f3  jz      short loc_18014C309
0x18014c2f5  lea     rcx, [rdi+10h]
0x18014c2f9  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18014c2fe  mov     rdx, r12; struct std::nothrow_t *
0x18014c301  mov     rcx, rdi; void *
0x18014c304  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18014c309  mov     dword ptr [rsp+280h+var_220], 3
0x18014c311  movups  xmm0, xmmword ptr [r13+20h]
0x18014c316  movdqu  xmmword ptr [rsp+280h+SRWLock], xmm0
0x18014c31c  lea     rax, [rsp+280h+SRWLock]
0x18014c321  mov     [rsp+280h+var_260], rax
0x18014c326  mov     r9d, [r13+30h]
0x18014c32a  lea     r8, [rsp+280h+var_220]
0x18014c32f  mov     rdx, r13
0x18014c332  mov     rcx, [r13+38h]
0x18014c336  call    ??$Set@K@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBKKU_GUID@@@Z; HNSObject::Set<ulong>(std::wstring const &,ulong const &,ulong,_GUID)
0x18014c33b  mov     rdi, cs:qword_18039AA48
0x18014c342  mov     eax, [rdi]
0x18014c344  cmp     eax, 5
0x18014c347  jbe     loc_18014C3CD
0x18014c34d  mov     eax, [rsp+280h+var_22C]
0x18014c351  mov     dword ptr [rsp+280h+var_220], eax
0x18014c355  lea     rcx, [r14+2F0h]
0x18014c35c  mov     r8, rcx
0x18014c35f  lea     rdx, [rbp+180h+var_1D0]
0x18014c363  mov     rcx, [rcx+38h]
0x18014c367  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x18014c36c  nop
0x18014c36d  lea     rax, [rbp+180h+var_1D0]
0x18014c371  mov     [rsp+280h+SRWLock], rax
0x18014c376  mov     [rbp+180h+var_200], r15
0x18014c37a  mov     dword ptr [rsp+280h+var_228], 514h
0x18014c382  lea     rax, aHnsServiceNetw_51; "HNS::Service::Network::Endpoint::Attach"
0x18014c389  mov     [rbp+180h+var_1F0], rax
0x18014c38d  lea     rax, [rsp+280h+var_220]
0x18014c392  mov     [rsp+280h+var_240], rax
0x18014c397  lea     rax, [rsp+280h+SRWLock]
0x18014c39c  mov     [rsp+280h+var_248], rax
0x18014c3a1  lea     rax, [rbp+180h+var_200]
0x18014c3a5  mov     [rsp+280h+var_250], rax
0x18014c3aa  lea     rax, [rsp+280h+var_228]
0x18014c3af  mov     [rsp+280h+var_258], rax
0x18014c3b4  lea     rax, [rbp+180h+var_1F0]
0x18014c3b8  mov     [rsp+280h+var_260], rax
0x18014c3bd  lea     rdx, qword_18033BF78
0x18014c3c4  mov     rcx, rdi
0x18014c3c7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByRef@$0BA@@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByRef@$0BA@@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x18014c3cc  nop
0x18014c3cd  mov     rdi, qword ptr [rbp+180h+var_1E0.Data4]
0x18014c3d1  xor     r15d, r15d
0x18014c3d4  test    rdi, rdi
0x18014c3d7  jz      short loc_18014C40C
0x18014c3d9  mov     eax, ebx
0x18014c3db  lock xadd [rdi+8], eax
  ... truncated ...
```
