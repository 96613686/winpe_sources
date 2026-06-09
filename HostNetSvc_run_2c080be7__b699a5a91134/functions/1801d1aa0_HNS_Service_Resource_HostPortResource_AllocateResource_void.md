# HNS::Service::Resource::HostPortResource::AllocateResource(void)

- ea: `0x1801d1aa0`
- end: `0x1801d2400`
- name: `?AllocateResource@HostPortResource@Resource@Service@HNS@@UEAA?AV?$com_ptr_t@VHNSObject@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `2400`
- prototype: ``
- caller_count: `3`
- callee_count: `38`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x180122ec4`
- `0x1801470d0`
- `0x18016e630`

## callees

- `0x180004b24`
- `0x18005f0c0`
- `0x18005f72c`
- `0x18005f794`
- `0x18005ffa0`
- `0x180061240`
- `0x1800666b4`
- `0x1800677fc`
- `0x180067c00`
- `0x18006c530`
- `0x1800759d8`
- `0x180075aac`
- `0x180077db0`
- `0x18007dd40`
- `0x18007f05c`
- `0x18007f21c`
- `0x18008aa04`
- `0x18008c27c`
- `0x180091854`
- `0x1800b5c7c`
- `0x1800d22b8`
- `0x1800d4834`
- `0x1800fbeb4`
- `0x180180c8c`
- `0x18019dbb4`
- `0x18019dcb8`
- `0x1801cddb0`
- `0x1801cedf4`
- `0x1801d1944`
- `0x1801d1aa0`
- `0x1801d299c`
- `0x1801d2ac8`
- `0x1801d4024`
- `0x1801d4254`
- `0x18023b590`
- `0x18023bcfc`
- `0x18023c078`
- `0x180271948`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801d233f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801d233f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801d1af5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1801d1af5`
- `NetMgmtIF!NetMgmtWaitForDeviceInstallAndGetInterfaceIdFromPnpId` at `0x1801d1db5`
- `NetMgmtIF!NetMgmtWaitForDeviceInstallAndGetInterfaceIdFromPnpId` at `0x1801d1db5`
- `NSI!NsiSetParameter` at `0x1801d216f`
- `NSI!NsiSetParameter` at `0x1801d216f`
- `RPCRT4!UuidCreate` at `0x1801d1be8`
- `RPCRT4!UuidCreate` at `0x1801d1be8`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801d202e`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1801d202e`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1801d2082`
- `IPHLPAPI!ConvertInterfaceGuidToLuid` at `0x1801d2082`

## string_xrefs

- `0x1801d2114`: `HNS::Service::Resource::HostPortResource::SetNetworkListInterfaceProperties`
- `0x1801d218c`: `HNS::Service::Resource::HostPortResource::SetNetworkListInterfaceProperties`
- `0x1801d23be`: `onecore\vm\dv\net\hns\service\resourcemgr\resources\src\hostportresource.cpp`
- `0x1801d23d3`: `onecore\vm\dv\net\hns\service\resourcemgr\resources\src\hostportresource.cpp`
- `0x1801d23eb`: `onecore\vm\dv\net\hns\service\resourcemgr\resources\src\hostportresource.cpp`
- `0x1801d1ae2`: `HNS::Service::Resource::HostPortResource::AllocateResource`
- `0x1801d1ed4`: `HNS::Service::Resource::HostPortResource::AllocateResource`
- `0x1801d1fd2`: `HNS::Service::Resource::HostPortResource::AllocateResource`
- `0x1801d2307`: `HNS::Service::Resource::HostPortResource::AllocateResource`
- `0x1801d1eaf`: `CreatedDeviceLessNIC`
- `0x1801d1fad`: `CreatedPNPBasedNIC`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
_QWORD *__fastcall HNS::Service::Resource::HostPortResource::AllocateResource(
        HNS::Service::Resource::HostPortResource *this,
        _QWORD *a2)
{
  unsigned int v3; // eax
  char *v4; // rdi
  GUID v5; // xmm0
  int v6; // r12d
  const unsigned __int16 *v7; // rcx
  __int64 FriendlyName; // rax
  HNS::Service::Resource::HostPortResource *v9; // rcx
  UUID *p_Src; // rcx
  unsigned int InterfaceIdFromPnpId; // ebx
  __int64 v12; // r8
  __int64 v13; // rax
  unsigned __int16 **v14; // rbx
  __int64 v15; // rax
  int v16; // r8d
  int v17; // r9d
  LPCOLESTR *v18; // rax
  unsigned __int16 **v19; // rbx
  __int64 v20; // rcx
  __int64 v21; // rax
  int v22; // r8d
  int v23; // r9d
  LPCOLESTR *v24; // rax
  const OLECHAR *v25; // rcx
  HRESULT v26; // eax
  LPCOLESTR *v27; // rdx
  __int64 v28; // r8
  char v29; // bl
  int v30; // eax
  bool v31; // dl
  int v32; // ebx
  unsigned int v33; // ebx
  char v34; // al
  unsigned __int16 v35; // r8
  char v36; // bl
  __int64 v37; // rdx
  _QWORD *v38; // rbx
  unsigned int v40; // eax
  GUID *p_Buf1; // [rsp+20h] [rbp-E0h]
  char v42; // [rsp+50h] [rbp-B0h]
  unsigned int v43; // [rsp+54h] [rbp-ACh] BYREF
  int v44; // [rsp+58h] [rbp-A8h]
  _QWORD *v45; // [rsp+60h] [rbp-A0h]
  char *v46; // [rsp+68h] [rbp-98h]
  _BYTE CallerContext[48]; // [rsp+70h] [rbp-90h] BYREF
  UUID Buf1; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v49[2]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v50; // [rsp+C0h] [rbp-40h]
  GUID v51; // [rsp+D0h] [rbp-30h] BYREF
  LPCOLESTR lpsz[2]; // [rsp+E0h] [rbp-20h] BYREF
  __m128i si128; // [rsp+F0h] [rbp-10h]
  GUID pclsid; // [rsp+100h] [rbp+0h] BYREF
  UUID Src; // [rsp+110h] [rbp+10h] BYREF
  __m128i v56; // [rsp+120h] [rbp+20h]
  _BYTE v57[32]; // [rsp+130h] [rbp+30h] BYREF
  HNSObject *v58; // [rsp+150h] [rbp+50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v45 = a2;
  *(_QWORD *)&Buf1.Data1 = a2;
  v44 = 0;
  HNSTraceProvider::TraceEnter("HNS::Service::Resource::HostPortResource::AllocateResource", 0x7Fu);
  AcquireSRWLockExclusive((PSRWLOCK)this + 5);
  v46 = (char *)this + 40;
  HNS::Service::Resource::PortResource::AllocateResource(this, &v58);
  if ( v58 )
    HNSObject::Release(v58);
  if ( (unsigned int)HNSObject::PropertyExists(*((_QWORD *)this + 287), (char *)this + 2240) )
    v3 = 0;
  else
    v3 = Property<unsigned long>::get((char *)this + 2240);
  HNS::AdapterMonitor::AdapterMonitor(CallerContext, v3);
  v4 = (char *)this + 1504;
  if ( (unsigned int)HNSObject::PropertyExists(*((_QWORD *)this + 195), (char *)this + 1504) )
  {
    v5 = GUID_NULL;
  }
  else
  {
    HNSObject::Get<_GUID>(*((_QWORD *)this + 195), &Buf1, (char *)this + 1504);
    v5 = Buf1;
  }
  v51 = v5;
  Buf1 = (UUID)*((_OWORD *)this + 154);
  p_Buf1 = &Buf1;
  HNSObject::Set<_GUID>(*((_QWORD *)this + 311), (char *)this + 2432, &v51, *((unsigned int *)this + 620));
  HNSObject::Get<_GUID>(*((_QWORD *)this + 311), &Buf1, (char *)this + 2432);
  if ( !memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
  {
    Buf1 = 0;
    UuidCreate(&Buf1);
    Src = Buf1;
    v51 = (GUID)*((_OWORD *)this + 154);
    p_Buf1 = &v51;
    HNSObject::Set<_GUID>(*((_QWORD *)this + 311), (char *)this + 2432, &Src, *((unsigned int *)this + 620));
  }
  HNSObject::Get<std::wstring>(*((_QWORD *)this + 163), v49, (char *)this + 1248);
  v6 = 8;
  v7 = (const unsigned __int16 *)v49;
  if ( *((_QWORD *)&v50 + 1) > 7u )
    v7 = v49[0];
  IPHelper::StringToMacAddress(v7, (unsigned __int8 *)&v58, &v43);
  std::wstring::~wstring(v49);
  if ( (unsigned int)HNSObject::PropertyExists(*((_QWORD *)this + 303), (char *)this + 2368) )
  {
    FriendlyName = HNS::Service::Resource::PortResource::GenerateFriendlyName(this, v49);
    Buf1 = (UUID)*((_OWORD *)this + 150);
    p_Buf1 = &Buf1;
    HNSObject::Set<std::wstring>(
      *((_QWORD *)this + 303),
      (char *)this + 2368,
      FriendlyName,
      *((unsigned int *)this + 604));
    std::wstring::~wstring(v49);
  }
  *(_OWORD *)lpsz = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(lpsz[0]) = 0;
  if ( (unsigned int)HNSObject::PropertyExists(*((_QWORD *)this + 351), (char *)this + 2752)
    || (HNSObject::Get<std::wstring>(*((_QWORD *)this + 351), v49, (char *)this + 2752), v6 = 25, v42 = 1, !(_QWORD)v50) )
  {
    v42 = 0;
  }
  if ( (v6 & 1) != 0 )
  {
    v6 &= ~1u;
    std::wstring::~wstring(v49);
  }
  if ( v42 )
  {
    v51 = GUID_NULL;
    HNSObject::Get<std::wstring>(*((_QWORD *)this + 351), v49, (char *)this + 2752);
    *(_QWORD *)&Buf1.Data1 = v49;
    Src = 0;
    v56 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Src.Data1) = 0;
    v6 |= 0x60u;
    v44 = v6;
    Vml::FormatString(&Src, (wchar_t *)L"VMBUS\\{%ls}\\%ls");
    std::wstring::~wstring(v49);
    p_Src = &Src;
    if ( v56.m128i_i64[1] > 7uLL )
      p_Src = *(UUID **)&Src.Data1;
    InterfaceIdFromPnpId = NetMgmtWaitForDeviceInstallAndGetInterfaceIdFromPnpId(p_Src, &v51);
    LOBYTE(v6) = v6 & 0xBF;
    std::wstring::~wstring(&Src);
    if ( InterfaceIdFromPnpId )
    {
      v40 = wil::verify_hresult<long>(InterfaceIdFromPnpId);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xAF,
        (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\resourcemgr\\resources\\src\\hostportresource.cpp",
        (const char *)v40,
        (int)p_Buf1);
    }
    LOBYTE(v12) = 1;
    v13 = GuidToString(v49, &v51, v12);
    std::wstring::operator=(lpsz, v13);
    std::wstring::~wstring(v49);
  }
  else
  {
    if ( HNS::Service::Resource::HostPortResource::GetDevicelessNICFlags(v9)
      || !(unsigned __int8)Property<unsigned char>::get((char *)this + 2688) )
    {
      Property<unsigned char>::get((char *)this + 2816);
      Property<unsigned long>::get((char *)this + 2240);
      HNSObject::Get<std::wstring>(*((_QWORD *)this + 303), v49, (char *)this + 2368);
      v19 = v49;
      if ( *((_QWORD *)&v50 + 1) > 7u )
        v19 = (unsigned __int16 **)v49[0];
      HNSObject::Get<_GUID>(*((_QWORD *)this + 311), &Buf1, (char *)this + 2432);
      p_Buf1 = (GUID *)&v58;
      v21 = SwitchHelper::InternalNicCreate(v20, v57, &Buf1, v19);
      std::wstring::operator=(lpsz, v21);
      std::wstring::~wstring(v57);
      std::wstring::~wstring(v49);
      if ( *(_DWORD *)qword_18039C168 > 5u )
      {
        *(_QWORD *)&Buf1.Data1 = L"CreatedPNPBasedNIC";
        v24 = lpsz;
        if ( si128.m128i_i64[1] > 7uLL )
          v24 = (LPCOLESTR *)lpsz[0];
        *(_QWORD *)&v51.Data1 = v24;
        v43 = 210;
        *(_QWORD *)&Src.Data1 = "HNS::Service::Resource::HostPortResource::AllocateResource";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          qword_18039C168,
          (unsigned int)&word_18033FFA6,
          v22,
          v23,
          (__int64)&Src,
          (__int64)&v43,
          (__int64)&v51,
          (__int64)&Buf1);
      }
    }
    else
    {
      Property<unsigned long>::get((char *)this + 2240);
      HNSObject::Get<std::wstring>(*((_QWORD *)this + 303), v49, (char *)this + 2368);
      LOBYTE(v6) = v6 | 0x80;
      v14 = v49;
      if ( *((_QWORD *)&v50 + 1) > 7u )
        v14 = (unsigned __int16 **)v49[0];
      HNSObject::Get<_GUID>(*((_QWORD *)this + 311), &Buf1, (char *)this + 2432);
      p_Buf1 = (GUID *)&v58;
      v15 = SwitchHelper::InternalLWNicCreate((char *)this + 2104, v57, &Buf1, v14);
      std::wstring::operator=(lpsz, v15);
      std::wstring::~wstring(v57);
      std::wstring::~wstring(v49);
      if ( *(_DWORD *)qword_18039C168 > 5u )
      {
        *(_QWORD *)&Src.Data1 = L"CreatedDeviceLessNIC";
        v18 = lpsz;
        if ( si128.m128i_i64[1] > 7uLL )
          v18 = (LPCOLESTR *)lpsz[0];
        *(_QWORD *)&v51.Data1 = v18;
        v43 = 193;
        *(_QWORD *)&Buf1.Data1 = "HNS::Service::Resource::HostPortResource::AllocateResource";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          qword_18039C168,
          (unsigned int)byte_18033FFE9,
          v16,
          v17,
          (__int64)&Buf1,
          (__int64)&v43,
          (__int64)&v51,
          (__int64)&Src);
      }
    }
    v4 = (char *)this + 1504;
  }
  pclsid = 0;
  v25 = (const OLECHAR *)lpsz;
  if ( si128.m128i_i64[1] > 7uLL )
    v25 = lpsz[0];
  v26 = CLSIDFromString(v25, &pclsid);
  if ( v26 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\resourcemgr\\resources\\src\\hostportresource.cpp",
      (const char *)(unsigned int)v26,
      (int)p_Buf1);
  Buf1 = (UUID)*((_OWORD *)this + 158);
  HNSObject::Set<_GUID>(*((_QWORD *)this + 319), (char *)this + 2496, &pclsid, *((unsigned int *)this + 636));
  if ( ConvertInterfaceGuidToLuid(&pclsid, (PNET_LUID)this + 392) < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecore\\vm\\dv\\net\\hns\\service\\resourcemgr\\resources\\src\\hostportresource.cpp",
      (const char *)0x803B0006LL,
      (int)&Buf1);
  v27 = lpsz;
  if ( si128.m128i_i64[1] > 7uLL )
    v27 = (LPCOLESTR *)lpsz[0];
  *(_OWORD *)v49 = 0;
  v50 = 0;
  v28 = -1;
  do
    ++v28;
  while ( *((_WORD *)v27 + v28) );
  std::wstring::_Construct<1,unsigned short const *>(v49, v27);
  Buf1 = (UUID)*((_OWORD *)this + 162);
  HNSObject::Set<std::wstring>(*((_QWORD *)this + 327), (char *)this + 2560, v49, *((unsigned int *)this + 652));
  std::wstring::~wstring(v49);
  v29 = Property<unsigned char>::get((char *)this + 2880);
  HNSTraceProvider::TraceEnter("HNS::Service::Resource::HostPortResource::SetNetworkListInterfaceProperties", 0x322u);
  if ( v29 )
  {
    v43 = 1;
    v30 = NsiSetParameter(1, 0, &NPI_MS_NDIS_MODULEID, 0, (char *)this + 3136, 8, 0, &v43, 4, 1088);
    if ( v30 < 0 )
      LogError(v30, L"NsiSetParameterFailed");
  }
  HNSTraceProvider::TraceSuccess("HNS::Service::Resource::HostPortResource::SetNetworkListInterfaceProperties", 0x33Bu);
  std::wstring::~wstring(lpsz);
  if ( (unsigned __int8)Property<unsigned char>::get((char *)this + 3008) )
    HNS::Service::Resource::HostPortResource::EnableDisableDhcp(this, v31);
  if ( (unsigned __int8)Property<unsigned char>::get((char *)this + 1312) == 1 )
  {
    v32 = *((unsigned __int8 *)this + 3144);
    HNSObject::Get<_GUID>(*((_QWORD *)this + 311), &pclsid, (char *)this + 2432);
    HNSObject::Get<_GUID>(*((_QWORD *)v4 + 7), &Buf1, v4);
    SwitchHelper::ConnectNicPort((HNS::Service::Resource::HostPortResource *)((char *)this + 2104), &Buf1, &pclsid, v32);
  }
  if ( (unsigned __int8)Property<unsigned char>::get((char *)this + 3072) )
  {
    v33 = Property<unsigned long>::get((char *)this + 2240);
    HNSObject::Get<_GUID>(*((_QWORD *)this + 319), &pclsid, (char *)this + 2496);
    HNSObject::Get<_GUID>(*((_QWORD *)v4 + 7), &Buf1, v4);
    ForwardDNSServerForCompartment(&Buf1, &pclsid, v33);
  }
  if ( dword_1803A5D98 > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index)
                                   + 16LL) )
  {
    Init_thread_header(&dword_1803A5D98);
    if ( dword_1803A5D98 == -1 )
    {
      word_1803A5D9C = 2 * !IPHelper::IsTcpIpv6Present();
      Init_thread_footer(&dword_1803A5D98);
    }
  }
  v34 = Property<unsigned char>::get((char *)this + 2624);
  v35 = word_1803A5D9C;
  if ( !v34 )
    v35 = 2;
  HNS::Service::Resource::HostPortResource::WaitForInterface(this, (struct HNS::AdapterMonitor *)CallerContext, v35);
  if ( (unsigned int)HNSObject::PropertyExists(*((_QWORD *)this + 351), (char *)this + 2752)
    || (HNSObject::Get<std::wstring>(*((_QWORD *)this + 351), v49, (char *)this + 2752),
        LOBYTE(v6) = v6 | 2,
        v36 = 0,
        !(_QWORD)v50) )
  {
    v36 = 1;
  }
  if ( (v6 & 2) != 0 )
    std::wstring::~wstring(v49);
  if ( v36 )
    HNS::Service::Resource::HostPortResource::UpdateInterfaceLocked(this, 2u, 0, 0);
  HNSTraceProvider::TraceSuccess("HNS::Service::Resource::HostPortResource::AllocateResource", 0x10Au);
  v37 = *((_QWORD *)this + 118);
  v38 = v45;
  *v45 = v37;
  if ( v37 )
    _InterlockedIncrement((volatile signed __int32 *)(v37 + 16));
  HNS::AdapterMonitor::~AdapterMonitor((HNS::AdapterMonitor *)CallerContext);
  if ( this != (HNS::Service::Resource::HostPortResource *)-40LL )
    ReleaseSRWLockExclusive((PSRWLOCK)this + 5);
  return v38;
}

```

## disassembly

```asm
0x1801d1aa0  mov     [rsp-8+arg_10], rbx
0x1801d1aa5  push    rbp
0x1801d1aa6  push    rsi
0x1801d1aa7  push    rdi
0x1801d1aa8  push    r12
0x1801d1aaa  push    r13
0x1801d1aac  push    r14
0x1801d1aae  push    r15
0x1801d1ab0  lea     rbp, [rsp-60h]
0x1801d1ab5  sub     rsp, 160h
0x1801d1abc  mov     rax, cs:__security_cookie
0x1801d1ac3  xor     rax, rsp
0x1801d1ac6  mov     [rbp+90h+var_38], rax
0x1801d1aca  mov     [rsp+190h+var_130], rdx
0x1801d1acf  mov     r14, rcx
0x1801d1ad2  mov     qword ptr [rbp+90h+Buf1], rdx
0x1801d1ad6  xor     r13d, r13d
0x1801d1ad9  mov     [rsp+190h+var_138], r13d
0x1801d1ade  lea     edx, [r13+7Fh]; unsigned int
0x1801d1ae2  lea     rcx, aHnsServiceReso_99; "HNS::Service::Resource::HostPortResourc"...
0x1801d1ae9  call    ?TraceEnter@HNSTraceProvider@@SAXPEBDI@Z; HNSTraceProvider::TraceEnter(char const *,uint)
0x1801d1aee  lea     rbx, [r14+28h]
0x1801d1af2  mov     rcx, rbx; SRWLock
0x1801d1af5  call    cs:__imp_AcquireSRWLockExclusive
0x1801d1afb  mov     [rsp+190h+var_128], rbx
0x1801d1b00  lea     rdx, [rbp+90h+var_40]
0x1801d1b04  mov     rcx, r14
0x1801d1b07  call    ?AllocateResource@PortResource@Resource@Service@HNS@@MEAA?AV?$com_ptr_t@VHNSObject@@Uerr_exception_policy@wil@@@wil@@XZ; HNS::Service::Resource::PortResource::AllocateResource(void)
0x1801d1b0c  mov     rcx, [rbp+90h+var_40]; this
0x1801d1b10  test    rcx, rcx
0x1801d1b13  jz      short loc_1801D1B1B
0x1801d1b15  call    ?Release@HNSObject@@QEAAKXZ; HNSObject::Release(void)
0x1801d1b1a  nop
0x1801d1b1b  lea     rsi, [r14+8C0h]
0x1801d1b22  mov     rdx, rsi
0x1801d1b25  mov     rcx, [rsi+38h]
0x1801d1b29  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x1801d1b2e  test    eax, eax
0x1801d1b30  jnz     short loc_1801D1B3C
0x1801d1b32  mov     rcx, rsi
0x1801d1b35  call    ?get@?$Property@K@@QEBA?BKXZ; Property<ulong>::get(void)
0x1801d1b3a  jmp     short loc_1801D1B3F
0x1801d1b3c  mov     eax, r13d
0x1801d1b3f  mov     edx, eax; unsigned int
0x1801d1b41  lea     rcx, [rsp+190h+CallerContext]; CallerContext
0x1801d1b46  call    ??0AdapterMonitor@HNS@@QEAA@I@Z; HNS::AdapterMonitor::AdapterMonitor(uint)
0x1801d1b4b  nop
0x1801d1b4c  lea     rdi, [r14+5E0h]
0x1801d1b53  mov     rdx, rdi
0x1801d1b56  mov     rcx, [rdi+38h]
0x1801d1b5a  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x1801d1b5f  test    eax, eax
0x1801d1b61  jnz     short loc_1801D1B79
0x1801d1b63  mov     r8, rdi
0x1801d1b66  lea     rdx, [rbp+90h+Buf1]
0x1801d1b6a  mov     rcx, [rdi+38h]
0x1801d1b6e  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1801d1b73  movaps  xmm0, [rbp+90h+Buf1]
0x1801d1b77  jmp     short loc_1801D1B80
0x1801d1b79  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801d1b80  movdqa  [rbp+90h+var_C0], xmm0
0x1801d1b85  lea     r15, [r14+980h]
0x1801d1b8c  movups  xmm0, xmmword ptr [r15+20h]
0x1801d1b91  movdqu  [rbp+90h+Buf1], xmm0
0x1801d1b96  lea     rax, [rbp+90h+Buf1]
0x1801d1b9a  mov     qword ptr [rsp+190h+var_170], rax
0x1801d1b9f  mov     r9d, [r15+30h]
0x1801d1ba3  lea     r8, [rbp+90h+var_C0]
0x1801d1ba7  mov     rdx, r15
0x1801d1baa  mov     rcx, [r15+38h]
0x1801d1bae  call    ??$Set@U_GUID@@@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@KU3@@Z; HNSObject::Set<_GUID>(std::wstring const &,_GUID const &,ulong,_GUID)
0x1801d1bb3  mov     r8, r15
0x1801d1bb6  lea     rdx, [rbp+90h+Buf1]
0x1801d1bba  mov     rcx, [r15+38h]
0x1801d1bbe  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1801d1bc3  mov     r8d, 10h; Size
0x1801d1bc9  lea     rdx, GUID_NULL; Buf2
0x1801d1bd0  lea     rcx, [rbp+90h+Buf1]; Buf1
0x1801d1bd4  call    memcmp_0
0x1801d1bd9  test    eax, eax
0x1801d1bdb  jnz     short loc_1801D1C1E
0x1801d1bdd  xorps   xmm0, xmm0
0x1801d1be0  movups  [rbp+90h+Buf1], xmm0
0x1801d1be4  lea     rcx, [rbp+90h+Buf1]; Uuid
0x1801d1be8  call    cs:__imp_UuidCreate
0x1801d1bee  movaps  xmm0, [rbp+90h+Buf1]
0x1801d1bf2  movdqa  [rbp+90h+Src], xmm0
0x1801d1bf7  movups  xmm1, xmmword ptr [r15+20h]
0x1801d1bfc  movdqu  [rbp+90h+var_C0], xmm1
0x1801d1c01  lea     rax, [rbp+90h+var_C0]
0x1801d1c05  mov     qword ptr [rsp+190h+var_170], rax
0x1801d1c0a  mov     r9d, [r15+30h]
0x1801d1c0e  lea     r8, [rbp+90h+Src]
0x1801d1c12  mov     rdx, r15
0x1801d1c15  mov     rcx, [r15+38h]
0x1801d1c19  call    ??$Set@U_GUID@@@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@KU3@@Z; HNSObject::Set<_GUID>(std::wstring const &,_GUID const &,ulong,_GUID)
0x1801d1c1e  lea     rcx, [r14+4E0h]
0x1801d1c25  mov     r8, rcx
0x1801d1c28  lea     rdx, [rbp+90h+var_E0]
0x1801d1c2c  mov     rcx, [rcx+38h]
0x1801d1c30  call    ??$Get@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@HNSObject@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; HNSObject::Get<std::wstring>(std::wstring const &)
0x1801d1c35  mov     r12d, 8
0x1801d1c3b  lea     rcx, [rbp+90h+var_E0]
0x1801d1c3f  cmp     qword ptr [rbp+90h+var_D0+8], 7
0x1801d1c44  cmova   rcx, [rbp+90h+var_E0]; unsigned __int16 *
0x1801d1c49  lea     r8, [rsp+190h+var_13C]; unsigned int *
0x1801d1c4e  lea     rdx, [rbp+90h+var_40]; unsigned __int8 *
0x1801d1c52  call    ?StringToMacAddress@IPHelper@@SAXPEBGPEAEPEAK@Z; IPHelper::StringToMacAddress(ushort const *,uchar *,ulong *)
0x1801d1c57  nop
0x1801d1c58  lea     rcx, [rbp+90h+var_E0]; void *
0x1801d1c5c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801d1c61  lea     rbx, [r14+940h]
0x1801d1c68  mov     rdx, rbx
0x1801d1c6b  mov     rcx, [rbx+38h]
0x1801d1c6f  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x1801d1c74  test    eax, eax
0x1801d1c76  jz      short loc_1801D1CB4
0x1801d1c78  lea     rdx, [rbp+90h+var_E0]
0x1801d1c7c  mov     rcx, r14
0x1801d1c7f  call    ?GenerateFriendlyName@PortResource@Resource@Service@HNS@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; HNS::Service::Resource::PortResource::GenerateFriendlyName(void)
0x1801d1c84  nop
0x1801d1c85  movups  xmm0, xmmword ptr [rbx+20h]
0x1801d1c89  movdqu  [rbp+90h+Buf1], xmm0
0x1801d1c8e  lea     rcx, [rbp+90h+Buf1]
0x1801d1c92  mov     qword ptr [rsp+190h+var_170], rcx; int
0x1801d1c97  mov     r9d, [rbx+30h]
0x1801d1c9b  mov     r8, rax
0x1801d1c9e  mov     rdx, rbx
0x1801d1ca1  mov     rcx, [rbx+38h]
0x1801d1ca5  call    ??$Set@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@HNSObject@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0KU_GUID@@@Z; HNSObject::Set<std::wstring>(std::wstring const &,std::wstring const &,ulong,_GUID)
0x1801d1caa  nop
0x1801d1cab  lea     rcx, [rbp+90h+var_E0]; void *
0x1801d1caf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801d1cb4  xorps   xmm0, xmm0
0x1801d1cb7  movups  xmmword ptr [rbp+90h+lpsz], xmm0
0x1801d1cbb  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801d1cc3  movdqu  [rbp+90h+var_A0], xmm1
0x1801d1cc8  mov     word ptr [rbp+90h+lpsz], r13w
0x1801d1ccd  lea     r13, [r14+0AC0h]
0x1801d1cd4  mov     rdx, r13
0x1801d1cd7  mov     rcx, [r13+38h]
0x1801d1cdb  call    ?PropertyExists@HNSObject@@QEBAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::PropertyExists(std::wstring const &)
0x1801d1ce0  test    eax, eax
0x1801d1ce2  jnz     short loc_1801D1D06
0x1801d1ce4  mov     r8, r13
0x1801d1ce7  lea     rdx, [rbp+90h+var_E0]
0x1801d1ceb  mov     rcx, [r13+38h]
0x1801d1cef  call    ??$Get@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@HNSObject@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; HNSObject::Get<std::wstring>(std::wstring const &)
0x1801d1cf4  mov     r12d, 19h
0x1801d1cfa  cmp     qword ptr [rbp+90h+var_D0], 0
0x1801d1cff  mov     [rsp+190h+var_140], 1
0x1801d1d04  jnz     short loc_1801D1D0B
0x1801d1d06  mov     [rsp+190h+var_140], 0
0x1801d1d0b  test    r12b, 1
0x1801d1d0f  jz      short loc_1801D1D1E
0x1801d1d11  and     r12d, 0FFFFFFFEh
0x1801d1d15  lea     rcx, [rbp+90h+var_E0]; void *
0x1801d1d19  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801d1d1e  cmp     [rsp+190h+var_140], 0
0x1801d1d23  jz      loc_1801D1DFC
0x1801d1d29  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1801d1d30  movdqu  [rbp+90h+var_C0], xmm0
0x1801d1d35  mov     r8, r13
0x1801d1d38  lea     rdx, [rbp+90h+var_E0]
0x1801d1d3c  mov     rcx, [r13+38h]
0x1801d1d40  call    ??$Get@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@HNSObject@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; HNSObject::Get<std::wstring>(std::wstring const &)
0x1801d1d45  or      r12d, 20h
0x1801d1d49  lea     rax, [rbp+90h+var_E0]
0x1801d1d4d  mov     qword ptr [rbp+90h+Buf1], rax
0x1801d1d51  xorps   xmm0, xmm0
0x1801d1d54  movups  [rbp+90h+Src], xmm0
0x1801d1d58  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1801d1d60  movdqu  [rbp+90h+var_70], xmm1
0x1801d1d65  xor     eax, eax
0x1801d1d67  mov     word ptr [rbp+90h+Src], ax
0x1801d1d6b  or      r12d, 40h
0x1801d1d6f  mov     [rsp+190h+var_138], r12d
0x1801d1d74  lea     r9, [rbp+90h+var_E0]
0x1801d1d78  cmp     qword ptr [rbp+90h+var_D0+8], 7
0x1801d1d7d  cmova   r9, [rbp+90h+var_E0]
0x1801d1d82  lea     r8, aF8615163Df3e46_0; "F8615163-DF3E-46c5-913F-F2D2F965ED0E"
0x1801d1d89  lea     rdx, aVmbusLsLs_0; "VMBUS\\{%ls}\\%ls"
0x1801d1d90  lea     rcx, [rbp+90h+Src]; Src
0x1801d1d94  call    ?FormatString@Vml@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGZZ; Vml::FormatString(std::wstring &,ushort const *,...)
0x1801d1d99  nop
0x1801d1d9a  lea     rcx, [rbp+90h+var_E0]; void *
0x1801d1d9e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801d1da3  lea     rcx, [rbp+90h+Src]
0x1801d1da7  cmp     qword ptr [rbp+90h+var_70+8], 7
0x1801d1dac  cmova   rcx, qword ptr [rbp+90h+Src]
0x1801d1db1  lea     rdx, [rbp+90h+var_C0]
0x1801d1db5  call    cs:__imp_NetMgmtWaitForDeviceInstallAndGetInterfaceIdFromPnpId
0x1801d1dbb  mov     ebx, eax
0x1801d1dbd  and     r12d, 0FFFFFFBFh
0x1801d1dc1  lea     rcx, [rbp+90h+Src]; void *
0x1801d1dc5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801d1dca  test    ebx, ebx
0x1801d1dcc  jnz     loc_1801D23AD
0x1801d1dd2  mov     r8b, 1
0x1801d1dd5  lea     rdx, [rbp+90h+var_C0]
0x1801d1dd9  lea     rcx, [rbp+90h+var_E0]
0x1801d1ddd  call    ?GuidToString@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@_N@Z; GuidToString(_GUID const &,bool)
0x1801d1de2  mov     rdx, rax
0x1801d1de5  lea     rcx, [rbp+90h+lpsz]
0x1801d1de9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801d1dee  lea     rcx, [rbp+90h+var_E0]; void *
0x1801d1df2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801d1df7  jmp     loc_1801D2015
0x1801d1dfc  call    ?GetDevicelessNICFlags@HostPortResource@Resource@Service@HNS@@QEAAKXZ; HNS::Service::Resource::HostPortResource::GetDevicelessNICFlags(void)
0x1801d1e01  test    eax, eax
0x1801d1e03  jnz     loc_1801D1F0B
0x1801d1e09  lea     rcx, [r14+0A80h]
0x1801d1e10  call    ?get@?$Property@E@@QEBA?BEXZ; Property<uchar>::get(void)
0x1801d1e15  test    al, al
0x1801d1e17  jz      loc_1801D1F0B
0x1801d1e1d  mov     rcx, rsi
0x1801d1e20  call    ?get@?$Property@K@@QEBA?BKXZ; Property<ulong>::get(void)
0x1801d1e25  mov     edi, eax
0x1801d1e27  mov     r8, rbx
0x1801d1e2a  lea     rdx, [rbp+90h+var_E0]
0x1801d1e2e  mov     rcx, [rbx+38h]
0x1801d1e32  call    ??$Get@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@HNSObject@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; HNSObject::Get<std::wstring>(std::wstring const &)
0x1801d1e37  bts     r12d, 7
0x1801d1e3c  lea     rbx, [rbp+90h+var_E0]
0x1801d1e40  cmp     qword ptr [rbp+90h+var_D0+8], 7
0x1801d1e45  cmova   rbx, [rbp+90h+var_E0]
0x1801d1e4a  mov     r8, r15
0x1801d1e4d  lea     rdx, [rbp+90h+Buf1]
0x1801d1e51  mov     rcx, [r15+38h]
0x1801d1e55  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1801d1e5a  lea     rcx, [r14+838h]
0x1801d1e61  mov     dword ptr [rsp+190h+var_168], edi
0x1801d1e65  lea     rax, [rbp+90h+var_40]
0x1801d1e69  mov     qword ptr [rsp+190h+var_170], rax
0x1801d1e6e  mov     r9, rbx
0x1801d1e71  lea     r8, [rbp+90h+Buf1]
0x1801d1e75  lea     rdx, [rbp+90h+var_60]
0x1801d1e79  call    ?InternalLWNicCreate@SwitchHelper@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@PEBGQEAY05EI@Z; SwitchHelper::InternalLWNicCreate(_GUID const &,ushort const *,uchar (* const)[6],uint)
0x1801d1e7e  mov     rdx, rax
0x1801d1e81  lea     rcx, [rbp+90h+lpsz]
0x1801d1e85  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801d1e8a  lea     rcx, [rbp+90h+var_60]; void *
0x1801d1e8e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801d1e93  nop
0x1801d1e94  lea     rcx, [rbp+90h+var_E0]; void *
0x1801d1e98  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1801d1e9d  mov     rcx, cs:qword_18039C168
0x1801d1ea4  mov     eax, [rcx]
0x1801d1ea6  cmp     eax, 5
0x1801d1ea9  jbe     loc_1801D200E
0x1801d1eaf  lea     rax, aCreateddevicel; "CreatedDeviceLessNIC"
0x1801d1eb6  mov     qword ptr [rbp+90h+Src], rax
0x1801d1eba  lea     rax, [rbp+90h+lpsz]
0x1801d1ebe  cmp     qword ptr [rbp+90h+var_A0+8], 7
0x1801d1ec3  cmova   rax, [rbp+90h+lpsz]
0x1801d1ec8  mov     qword ptr [rbp+90h+var_C0], rax
0x1801d1ecc  mov     [rsp+190h+var_13C], 0C1h
0x1801d1ed4  lea     rax, aHnsServiceReso_99; "HNS::Service::Resource::HostPortResourc"...
0x1801d1edb  mov     qword ptr [rbp+90h+Buf1], rax
0x1801d1edf  lea     rax, [rbp+90h+Src]
0x1801d1ee3  mov     [rsp+190h+var_158], rax
0x1801d1ee8  lea     rax, [rbp+90h+var_C0]
0x1801d1eec  mov     [rsp+190h+var_160], rax
0x1801d1ef1  lea     rax, [rsp+190h+var_13C]
0x1801d1ef6  mov     [rsp+190h+var_168], rax
0x1801d1efb  lea     rax, [rbp+90h+Buf1]
0x1801d1eff  lea     rdx, byte_18033FFE9
0x1801d1f06  jmp     loc_1801D2004
0x1801d1f0b  lea     rcx, [r14+0B00h]
0x1801d1f12  call    ?get@?$Property@E@@QEBA?BEXZ; Property<uchar>::get(void)
0x1801d1f17  test    al, al
0x1801d1f19  setnz   sil
0x1801d1f1d  lea     rcx, [r14+8C0h]
0x1801d1f24  call    ?get@?$Property@K@@QEBA?BKXZ; Property<ulong>::get(void)
0x1801d1f29  mov     edi, eax
0x1801d1f2b  mov     r8, rbx
0x1801d1f2e  lea     rdx, [rbp+90h+var_E0]
0x1801d1f32  mov     rcx, [rbx+38h]
0x1801d1f36  call    ??$Get@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@HNSObject@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV12@@Z; HNSObject::Get<std::wstring>(std::wstring const &)
0x1801d1f3b  bts     r12d, 8
0x1801d1f40  lea     rbx, [rbp+90h+var_E0]
0x1801d1f44  cmp     qword ptr [rbp+90h+var_D0+8], 7
0x1801d1f49  cmova   rbx, [rbp+90h+var_E0]
0x1801d1f4e  mov     r8, r15
0x1801d1f51  lea     rdx, [rbp+90h+Buf1]
0x1801d1f55  mov     rcx, [r15+38h]
0x1801d1f59  call    ??$Get@U_GUID@@@HNSObject@@QEAA?AU_GUID@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; HNSObject::Get<_GUID>(std::wstring const &)
0x1801d1f5e  mov     byte ptr [rsp+190h+var_160], sil
0x1801d1f63  mov     dword ptr [rsp+190h+var_168], edi
0x1801d1f67  lea     rax, [rbp+90h+var_40]
0x1801d1f6b  mov     qword ptr [rsp+190h+var_170], rax
0x1801d1f70  mov     r9, rbx
0x1801d1f73  lea     r8, [rbp+90h+Buf1]
0x1801d1f77  lea     rdx, [rbp+90h+var_60]
0x1801d1f7b  call    ?InternalNicCreate@SwitchHelper@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@PEBGQEAY05EI_N@Z; SwitchHelper::InternalNicCreate(_GUID const &,ushort const *,uchar (* const)[6],uint,bool)
0x1801d1f80  mov     rdx, rax
0x1801d1f83  lea     rcx, [rbp+90h+lpsz]
0x1801d1f87  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1801d1f8c  lea     rcx, [rbp+90h+var_60]; void *
0x1801d1f90  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
  ... truncated ...
```
