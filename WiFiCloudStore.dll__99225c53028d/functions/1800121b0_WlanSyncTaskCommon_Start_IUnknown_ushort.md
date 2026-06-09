# WlanSyncTaskCommon::Start(IUnknown *,ushort *)

- ea: `0x1800121b0`
- end: `0x180012524`
- name: `?Start@WlanSyncTaskCommon@@UEAAJPEAUIUnknown@@PEAG@Z`
- size: `884`
- prototype: `__int64 __fastcall(WlanSyncTaskCommon *this, struct IUnknown *, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000ac14`
- `0x180011db8`
- `0x180011f8c`
- `0x180012180`
- `0x1800121b0`
- `0x180012570`
- `0x180013b00`
- `0x180013bc0`
- `0x180013c40`
- `0x180013ef0`
- `0x180013f18`
- `0x18001402c`
- `0x180014088`
- `0x1800140a4`
- `0x1800141dc`
- `0x18001428c`
- `0x18001e1a0`
- `0x18002477c`
- `0x180028748`
- `0x18002a030`
- `0x18003d8a4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012387`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012387`

## string_xrefs

- `0x180012298`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`
- `0x1800122f1`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`
- `0x1800123bb`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`
- `0x18001244b`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`

## pseudocode

```c
__int64 __fastcall WlanSyncTaskCommon::Start(WlanSyncTaskCommon *this, struct IUnknown *a2, unsigned __int16 *a3)
{
  const unsigned __int16 *v5; // rbx
  int v6; // eax
  unsigned int v7; // ebx
  int v9; // eax
  unsigned int v10; // ebx
  const unsigned __int16 *v11; // rbx
  int v12; // eax
  unsigned int v13; // ebx
  struct _FILETIME v14; // rcx
  int v15; // eax
  struct _FILETIME v16; // rcx
  struct _FILETIME v17; // rcx
  int v18[2]; // [rsp+20h] [rbp-188h] BYREF
  struct _FILETIME system_time; // [rsp+28h] [rbp-180h] BYREF
  HLOCAL hMem[2]; // [rsp+30h] [rbp-178h] BYREF
  void **v21; // [rsp+40h] [rbp-168h] BYREF
  _BYTE v22[272]; // [rsp+48h] [rbp-160h] BYREF
  _BYTE v23[8]; // [rsp+158h] [rbp-50h] BYREF
  _BYTE v24[48]; // [rsp+160h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  if ( a3 && (!wcscmp_0(a3, L"wlansvc") || !wcscmp_0(a3, L"netprofm") || !wcscmp_0(a3, L"dusmsvc")) )
  {
    hMem[0] = (HLOCAL)wil::filetime::get_system_time(this);
    v5 = *(const unsigned __int16 **)Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken((LPWSTR *)&system_time);
    wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v21);
    v21 = &WiFiCloudStoreTelemetry::WlanTriggeredSync::`vftable';
    WiFiCloudStoreTelemetry::WlanTriggeredSync::StartActivity(
      (WiFiCloudStoreTelemetry::WlanTriggeredSync *)&v21,
      v5,
      a3,
      (const struct _FILETIME *)hMem);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&system_time);
    *(_QWORD *)v18 = 0;
    v6 = Microsoft::WRL::Details::MakeAndInitialize<WlanSyncTaskWlanToCDS,WlanSyncTaskWlanToCDS,>(v18);
    v7 = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x162,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
        (const char *)(unsigned int)v6,
        v18[0]);
      Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(v18);
      WiFiCloudStoreTelemetry::WlanTriggeredSync::~WlanTriggeredSync((WiFiCloudStoreTelemetry::WlanTriggeredSync *)&v21);
      return v7;
    }
    system_time = *(struct _FILETIME *)v18;
    v9 = CommonStart<WlanSyncTaskWlanToCDS *,WiFiCloudStoreTelemetry::WlanTriggeredSync>(&system_time, &v21, a2);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x163,
        (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
        (const char *)(unsigned int)v9,
        v18[0]);
      Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(v18);
      WiFiCloudStoreTelemetry::WlanTriggeredSync::~WlanTriggeredSync((WiFiCloudStoreTelemetry::WlanTriggeredSync *)&v21);
      return v10;
    }
    Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(v18);
    WiFiCloudStoreTelemetry::WlanTriggeredSync::~WlanTriggeredSync((WiFiCloudStoreTelemetry::WlanTriggeredSync *)&v21);
    return 0;
  }
  system_time = wil::filetime::get_system_time(this);
  v11 = *(const unsigned __int16 **)Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken((LPWSTR *)hMem);
  wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)&v21);
  v21 = &WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::`vftable';
  WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::StartActivity(
    (WiFiCloudStoreTelemetry::CdsTriggeredWlanSync *)&v21,
    v11,
    &system_time);
  if ( hMem[0] )
    LocalFree(hMem[0]);
  *(_QWORD *)v18 = 0;
  Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(v18);
  v12 = Microsoft::WRL::Details::MakeAndInitialize<WlanSyncTaskCDSToWlan,WlanSyncTaskCDSToWlan,>(v18);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16A,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
      (const char *)(unsigned int)v12,
      v18[0]);
    v14 = *(struct _FILETIME *)v18;
    if ( *(_QWORD *)v18 )
    {
      *(_QWORD *)v18 = 0;
      ((void (__fastcall *)(_QWORD))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase>::Release)(v14);
    }
LABEL_15:
    v21 = &WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::`vftable';
    wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v21);
    wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v24);
    wil::details::shared_object<wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(v23);
    wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>(v22);
    return v13;
  }
  system_time = *(struct _FILETIME *)v18;
  v15 = CommonStart<WlanSyncTaskCDSToWlan *,WiFiCloudStoreTelemetry::CdsTriggeredWlanSync>(&system_time, &v21, a2);
  v13 = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x16B,
      (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
      (const char *)(unsigned int)v15,
      v18[0]);
    v16 = *(struct _FILETIME *)v18;
    if ( *(_QWORD *)v18 )
    {
      *(_QWORD *)v18 = 0;
      ((void (__fastcall *)(_QWORD))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase>::Release)(v16);
    }
    goto LABEL_15;
  }
  v17 = *(struct _FILETIME *)v18;
  if ( *(_QWORD *)v18 )
  {
    *(_QWORD *)v18 = 0;
    ((void (__fastcall *)(_QWORD))Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase>::Release)(v17);
  }
  v21 = &WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::`vftable';
  wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v21);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v24);
  wil::details::shared_object<wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(v23);
  wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>(v22);
  return 0;
}

```

## disassembly

```asm
0x1800121b0  mov     [rsp+arg_0], rbx
0x1800121b5  mov     [rsp+arg_18], rsi
0x1800121ba  push    rdi
0x1800121bb  sub     rsp, 1A0h
0x1800121c2  mov     rax, cs:__security_cookie
0x1800121c9  xor     rax, rsp
0x1800121cc  mov     [rsp+1A8h+var_18], rax
0x1800121d4  mov     rdi, r8
0x1800121d7  mov     rsi, rdx
0x1800121da  test    r8, r8
0x1800121dd  jz      loc_180012336
0x1800121e3  lea     rdx, aWlansvc; "wlansvc"
0x1800121ea  mov     rcx, r8; String1
0x1800121ed  call    wcscmp_0
0x1800121f2  test    eax, eax
0x1800121f4  jz      short loc_180012220
0x1800121f6  lea     rdx, aNetprofm; "netprofm"
0x1800121fd  mov     rcx, rdi; String1
0x180012200  call    wcscmp_0
0x180012205  test    eax, eax
0x180012207  jz      short loc_180012220
0x180012209  lea     rdx, aDusmsvc; "dusmsvc"
0x180012210  mov     rcx, rdi; String1
0x180012213  call    wcscmp_0
0x180012218  test    eax, eax
0x18001221a  jnz     loc_180012336
0x180012220  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x180012225  mov     [rsp+1A8h+hMem], rax
0x18001222a  lea     rcx, [rsp+1A8h+var_180]; StringSid
0x18001222f  call    ?GetUserSidStringFromToken@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAX@Z; Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken(void * const)
0x180012234  mov     rbx, [rax]
0x180012237  lea     rdx, aWlantriggereds; "WlanTriggeredSync"
0x18001223e  lea     rcx, [rsp+1A8h+var_168]; struct wil::details::IFailureCallback *
0x180012243  call    ??0?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180012248  lea     rax, ??_7WlanTriggeredSync@WiFiCloudStoreTelemetry@@6B@; const WiFiCloudStoreTelemetry::WlanTriggeredSync::`vftable'
0x18001224f  mov     [rsp+1A8h+var_168], rax
0x180012254  lea     r9, [rsp+1A8h+hMem]; struct _FILETIME *
0x180012259  mov     r8, rdi; unsigned __int16 *
0x18001225c  mov     rdx, rbx; unsigned __int16 *
0x18001225f  lea     rcx, [rsp+1A8h+var_168]; this
0x180012264  call    ?StartActivity@WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAAXPEBG0AEBU_FILETIME@@@Z; WiFiCloudStoreTelemetry::WlanTriggeredSync::StartActivity(ushort const *,ushort const *,_FILETIME const &)
0x180012269  nop
0x18001226a  lea     rcx, [rsp+1A8h+var_180]
0x18001226f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180012274  mov     qword ptr [rsp+1A8h+var_188], 0; int
0x18001227d  lea     rcx, [rsp+1A8h+var_188]
0x180012282  call    ??$MakeAndInitialize@VWlanSyncTaskWlanToCDS@@V1@$$V@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VWlanSyncTaskWlanToCDS@@@WRL@Microsoft@@@012@@Z; Microsoft::WRL::Details::MakeAndInitialize<WlanSyncTaskWlanToCDS,WlanSyncTaskWlanToCDS,>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>>)
0x180012287  mov     ebx, eax
0x180012289  test    eax, eax
0x18001228b  jns     short loc_1800122C4
0x18001228d  mov     rcx, [rsp+1A8h]; this
0x180012295  mov     r9d, eax; char *
0x180012298  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x18001229f  mov     edx, 162h; void *
0x1800122a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800122a9  lea     rcx, [rsp+1A8h+var_188]
0x1800122ae  call    ?InternalRelease@?$ComPtr@VWlanSyncTaskWlanToCDS@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(void)
0x1800122b3  lea     rcx, [rsp+1A8h+var_168]; this
0x1800122b8  call    ??1WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAA@XZ; WiFiCloudStoreTelemetry::WlanTriggeredSync::~WlanTriggeredSync(void)
0x1800122bd  mov     eax, ebx
0x1800122bf  jmp     loc_1800124FE
0x1800122c4  mov     rax, qword ptr [rsp+1A8h+var_188]
0x1800122c9  mov     qword ptr [rsp+1A8h+var_180.dwLowDateTime], rax
0x1800122ce  mov     r8, rsi
0x1800122d1  lea     rdx, [rsp+1A8h+var_168]
0x1800122d6  lea     rcx, [rsp+1A8h+var_180]
0x1800122db  call    ??$CommonStart@PEAVWlanSyncTaskWlanToCDS@@VWlanTriggeredSync@WiFiCloudStoreTelemetry@@@@YAJAEBQEAVWlanSyncTaskWlanToCDS@@AEAVWlanTriggeredSync@WiFiCloudStoreTelemetry@@PEAUIUnknown@@@Z; CommonStart<WlanSyncTaskWlanToCDS *,WiFiCloudStoreTelemetry::WlanTriggeredSync>(WlanSyncTaskWlanToCDS * const &,WiFiCloudStoreTelemetry::WlanTriggeredSync &,IUnknown *)
0x1800122e0  mov     ebx, eax
0x1800122e2  test    eax, eax
0x1800122e4  jns     short loc_18001231D
0x1800122e6  mov     rcx, [rsp+1A8h]; this
0x1800122ee  mov     r9d, eax; char *
0x1800122f1  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800122f8  mov     edx, 163h; void *
0x1800122fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012302  lea     rcx, [rsp+1A8h+var_188]
0x180012307  call    ?InternalRelease@?$ComPtr@VWlanSyncTaskWlanToCDS@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(void)
0x18001230c  lea     rcx, [rsp+1A8h+var_168]; this
0x180012311  call    ??1WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAA@XZ; WiFiCloudStoreTelemetry::WlanTriggeredSync::~WlanTriggeredSync(void)
0x180012316  mov     eax, ebx
0x180012318  jmp     loc_1800124FE
0x18001231d  lea     rcx, [rsp+1A8h+var_188]
0x180012322  call    ?InternalRelease@?$ComPtr@VWlanSyncTaskWlanToCDS@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(void)
0x180012327  lea     rcx, [rsp+1A8h+var_168]; this
0x18001232c  call    ??1WlanTriggeredSync@WiFiCloudStoreTelemetry@@QEAA@XZ; WiFiCloudStoreTelemetry::WlanTriggeredSync::~WlanTriggeredSync(void)
0x180012331  jmp     loc_1800124F6
0x180012336  call    ?get_system_time@filetime@wil@@YA?AU_FILETIME@@XZ; wil::filetime::get_system_time(void)
0x18001233b  mov     qword ptr [rsp+1A8h+var_180.dwLowDateTime], rax
0x180012340  lea     rcx, [rsp+1A8h+hMem]; StringSid
0x180012345  call    ?GetUserSidStringFromToken@WiFiCloudStore@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAX@Z; Windows::Internal::WiFiCloudStore::GetUserSidStringFromToken(void * const)
0x18001234a  mov     rbx, [rax]
0x18001234d  lea     rdx, aCdstriggeredwl; "CdsTriggeredWlanSync"
0x180012354  lea     rcx, [rsp+1A8h+var_168]; struct wil::details::IFailureCallback *
0x180012359  call    ??0?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18001235e  lea     rdi, ??_7CdsTriggeredWlanSync@WiFiCloudStoreTelemetry@@6B@; const WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::`vftable'
0x180012365  mov     [rsp+1A8h+var_168], rdi
0x18001236a  lea     r8, [rsp+1A8h+var_180]; struct _FILETIME *
0x18001236f  mov     rdx, rbx; unsigned __int16 *
0x180012372  lea     rcx, [rsp+1A8h+var_168]; this
0x180012377  call    ?StartActivity@CdsTriggeredWlanSync@WiFiCloudStoreTelemetry@@QEAAXPEBGAEBU_FILETIME@@@Z; WiFiCloudStoreTelemetry::CdsTriggeredWlanSync::StartActivity(ushort const *,_FILETIME const &)
0x18001237c  nop
0x18001237d  mov     rcx, [rsp+1A8h+hMem]; hMem
0x180012382  test    rcx, rcx
0x180012385  jz      short loc_18001238D
0x180012387  call    cs:__imp_LocalFree
0x18001238d  mov     qword ptr [rsp+1A8h+var_188], 0; int
0x180012396  lea     rcx, [rsp+1A8h+var_188]
0x18001239b  call    ?InternalRelease@?$ComPtr@VWlanSyncTaskWlanToCDS@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<WlanSyncTaskWlanToCDS>::InternalRelease(void)
0x1800123a0  lea     rcx, [rsp+1A8h+var_188]
0x1800123a5  call    ??$MakeAndInitialize@VWlanSyncTaskCDSToWlan@@V1@$$V@Details@WRL@Microsoft@@YAJPEAPEAVWlanSyncTaskCDSToWlan@@@Z; Microsoft::WRL::Details::MakeAndInitialize<WlanSyncTaskCDSToWlan,WlanSyncTaskCDSToWlan,>(WlanSyncTaskCDSToWlan * *)
0x1800123aa  mov     ebx, eax
0x1800123ac  test    eax, eax
0x1800123ae  jns     short loc_18001241E
0x1800123b0  mov     rcx, [rsp+1A8h]; this
0x1800123b8  mov     r9d, eax; char *
0x1800123bb  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x1800123c2  mov     edx, 16Ah; void *
0x1800123c7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800123cc  mov     rcx, qword ptr [rsp+1A8h+var_188]
0x1800123d1  test    rcx, rcx
0x1800123d4  jz      short loc_1800123E4
0x1800123d6  mov     qword ptr [rsp+1A8h+var_188], 0
0x1800123df  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase>::Release(void)
0x1800123e4  mov     [rsp+1A8h+var_168], rdi
0x1800123e9  lea     rcx, [rsp+1A8h+var_168]
0x1800123ee  call    ?Destroy@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800123f3  lea     rcx, [rsp+1A8h+var_48]; this
0x1800123fb  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180012400  lea     rcx, [rsp+1A8h+var_50]
0x180012408  call    ?reset@?$shared_object@V?$ActivityData@VWiFiCloudStoreTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18001240d  lea     rcx, [rsp+1A8h+var_160]
0x180012412  call    ??1?$ActivityData@VWiFiCloudStoreTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x180012417  mov     eax, ebx
0x180012419  jmp     loc_1800124FE
0x18001241e  mov     rax, qword ptr [rsp+1A8h+var_188]
0x180012423  mov     qword ptr [rsp+1A8h+var_180.dwLowDateTime], rax
0x180012428  mov     r8, rsi
0x18001242b  lea     rdx, [rsp+1A8h+var_168]
0x180012430  lea     rcx, [rsp+1A8h+var_180]
0x180012435  call    ??$CommonStart@PEAVWlanSyncTaskCDSToWlan@@VCdsTriggeredWlanSync@WiFiCloudStoreTelemetry@@@@YAJAEBQEAVWlanSyncTaskCDSToWlan@@AEAVCdsTriggeredWlanSync@WiFiCloudStoreTelemetry@@PEAUIUnknown@@@Z; CommonStart<WlanSyncTaskCDSToWlan *,WiFiCloudStoreTelemetry::CdsTriggeredWlanSync>(WlanSyncTaskCDSToWlan * const &,WiFiCloudStoreTelemetry::CdsTriggeredWlanSync &,IUnknown *)
0x18001243a  mov     ebx, eax
0x18001243c  test    eax, eax
0x18001243e  jns     short loc_1800124AB
0x180012440  mov     rcx, [rsp+1A8h]; this
0x180012448  mov     r9d, eax; char *
0x18001244b  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180012452  mov     edx, 16Bh; void *
0x180012457  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001245c  mov     rcx, qword ptr [rsp+1A8h+var_188]
0x180012461  test    rcx, rcx
0x180012464  jz      short loc_180012474
0x180012466  mov     qword ptr [rsp+1A8h+var_188], 0
0x18001246f  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase>::Release(void)
0x180012474  mov     [rsp+1A8h+var_168], rdi
0x180012479  lea     rcx, [rsp+1A8h+var_168]
0x18001247e  call    ?Destroy@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180012483  lea     rcx, [rsp+1A8h+var_48]; this
0x18001248b  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x180012490  lea     rcx, [rsp+1A8h+var_50]
0x180012498  call    ?reset@?$shared_object@V?$ActivityData@VWiFiCloudStoreTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x18001249d  lea     rcx, [rsp+1A8h+var_160]
0x1800124a2  call    ??1?$ActivityData@VWiFiCloudStoreTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800124a7  mov     eax, ebx
0x1800124a9  jmp     short loc_1800124FE
0x1800124ab  mov     rcx, qword ptr [rsp+1A8h+var_188]
0x1800124b0  test    rcx, rcx
0x1800124b3  jz      short loc_1800124C3
0x1800124b5  mov     qword ptr [rsp+1A8h+var_188], 0
0x1800124be  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Microsoft::WRL::FtmBase>::Release(void)
0x1800124c3  mov     [rsp+1A8h+var_168], rdi
0x1800124c8  lea     rcx, [rsp+1A8h+var_168]
0x1800124cd  call    ?Destroy@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800124d2  lea     rcx, [rsp+1A8h+var_48]; this
0x1800124da  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800124df  lea     rcx, [rsp+1A8h+var_50]
0x1800124e7  call    ?reset@?$shared_object@V?$ActivityData@VWiFiCloudStoreTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800124ec  lea     rcx, [rsp+1A8h+var_160]
0x1800124f1  call    ??1?$ActivityData@VWiFiCloudStoreTelemetry@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VWiFiCloudStoreTelemetry@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WiFiCloudStoreTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<WiFiCloudStoreTelemetry,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800124f6  xor     eax, eax
0x1800124f8  jmp     short loc_1800124FE
0x1800124fa  mov     eax, [rsp+1A8h+var_188]
0x1800124fe  mov     rcx, [rsp+1A8h+var_18]
0x180012506  xor     rcx, rsp; StackCookie
0x180012509  call    __security_check_cookie
0x18001250e  lea     r11, [rsp+1A8h+var_8]
0x180012516  mov     rbx, [r11+10h]
0x18001251a  mov     rsi, [r11+28h]
0x18001251e  mov     rsp, r11
0x180012521  pop     rdi
0x180012522  retn
```
