# CLocationPermissionManagerCam::DetermineAccessByProcess(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,ClientPermissionOptions,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>)

- ea: `0x18004edbc`
- end: `0x18004f142`
- name: `?DetermineAccessByProcess@CLocationPermissionManagerCam@@AEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KW4ClientPermissionOptions@@0V?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z`
- size: `902`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004ed60`

## callees

- `0x180012310`
- `0x18001bb40`
- `0x180020c64`
- `0x180021a4c`
- `0x18004741c`
- `0x18004ac50`
- `0x18004dd28`
- `0x18004edbc`
- `0x1800526dc`
- `0x180056b3c`
- `0x1800a98c0`
- `0x1801171c0`
- `0x18015e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004ef52`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004ef52`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004ee75`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18004ee75`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18004eec8`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18004eec8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004ef65`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004ef65`

## string_xrefs

- `0x18004edfb`: `Windows.Internal.CapabilityAccess.CapabilityAccess`
- `0x18004ee2f`: `CLocationPermissionManagerCam::DetermineAccessByProcess`
- `0x18004eee6`: `CLocationPermissionManagerCam::DetermineAccessByProcess`
- `0x18004efa8`: `CLocationPermissionManagerCam::DetermineAccessByProcess`
- `0x18004f058`: `CLocationPermissionManagerCam::DetermineAccessByProcess`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall CLocationPermissionManagerCam::DetermineAccessByProcess(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        void ***a6)
{
  HSTRING *v8; // rax
  int v9; // eax
  void *v11; // rdx
  void *v12; // rdx
  unsigned int v13; // r8d
  const char *v14; // r9
  unsigned __int64 v15; // rdi
  HRESULT v16; // eax
  IUnknown *v17; // r14
  ULONG (__stdcall *Release)(IUnknown *); // r12
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rdx
  bool IsCtaPolicyActive; // al
  __int64 v23; // rdx
  bool v24; // di
  int v25; // eax
  __int64 v26; // rdx
  bool v27; // di
  __int64 v28; // rdx
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  const char *dwAuthnLevel; // [rsp+20h] [rbp-A9h]
  const char *dwImpLevel; // [rsp+28h] [rbp-A1h]
  const char *dwImpLevela; // [rsp+28h] [rbp-A1h]
  int pAuthInfo; // [rsp+30h] [rbp-99h]
  int pAuthInfoa; // [rsp+30h] [rbp-99h]
  bool v37[4]; // [rsp+50h] [rbp-79h] BYREF
  int v38; // [rsp+54h] [rbp-75h] BYREF
  int v39; // [rsp+58h] [rbp-71h] BYREF
  unsigned int v40; // [rsp+5Ch] [rbp-6Dh] BYREF
  __int64 v41; // [rsp+60h] [rbp-69h] BYREF
  char *v42; // [rsp+68h] [rbp-61h] BYREF
  char v43; // [rsp+70h] [rbp-59h]
  void ***v44; // [rsp+78h] [rbp-51h] BYREF
  HSTRING string; // [rsp+80h] [rbp-49h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-41h] BYREF
  char v47; // [rsp+A0h] [rbp-29h] BYREF
  IUnknown *pProxy; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v49; // [rsp+B0h] [rbp-19h] BYREF
  int v50; // [rsp+B8h] [rbp-11h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+118h] [rbp+4Fh]

  v41 = a2;
  v44 = a6;
  pProxy = 0;
  v8 = Windows::Internal::StringReference::StringReference(
         &string,
         L"Windows.Internal.CapabilityAccess.CapabilityAccess");
  v9 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(
         *v8,
         &pProxy);
  if ( v9 < 0 )
  {
    LODWORD(dwImpLevel) = v9;
    wil::details::in1diag5::Log_Hr(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationpermissionmanagercam.cpp",
      "CLocationPermissionManagerCam::DetermineAccessByProcess",
      "hr",
      dwImpLevel,
      pAuthInfo);
LABEL_3:
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
    std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(a6);
    return 0;
  }
  v47 = 0;
  if ( *a6 )
    v11 = **a6;
  else
    v11 = 0;
  if ( !SetThreadToken(0, v11) )
  {
    wil::details::in1diag5::Log_GetLastError(retaddr, v12, v13, v14, dwAuthnLevel, dwImpLevel);
    goto LABEL_3;
  }
  v47 = 1;
  v42 = &v47;
  v43 = 1;
  v15 = -1;
  v16 = CoSetProxyBlanket(
          pProxy,
          0xFFFFFFFF,
          0xFFFFFFFF,
          (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
          0,
          3u,
          (RPC_AUTH_IDENTITY_HANDLE)0xFFFFFFFFFFFFFFFFLL,
          0x40u);
  if ( v16 < 0 )
  {
    LODWORD(dwImpLevela) = v16;
    wil::details::in1diag5::Log_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationpermissionmanagercam.cpp",
      "CLocationPermissionManagerCam::DetermineAccessByProcess",
      "hr",
      dwImpLevela,
      pAuthInfoa);
LABEL_11:
    wil::details::lambda_call__CLocationPermissionManagerCam::DetermineAccessByProcess_::_2_::_lambda_1___::reset(&v42);
    goto LABEL_3;
  }
  v49 = 0;
  v17 = pProxy;
  Release = pProxy->lpVtbl[2].Release;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
  do
    ++v15;
  while ( c_szCapabilityLocation[v15] );
  if ( v15 > 0xFFFFFFFF )
  {
    LODWORD(v15) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(c_szCapabilityLocation, v15, &hstringHeader, &string);
  v19 = ((__int64 (__fastcall *)(IUnknown *, HSTRING, _QWORD, _QWORD, __int64 *))Release)(v17, string, a3, 0, &v49);
  if ( v19 < 0 )
  {
    v20 = 141;
LABEL_18:
    LODWORD(dwImpLevela) = v19;
    wil::details::in1diag5::Log_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationpermissionmanagercam.cpp",
      "CLocationPermissionManagerCam::DetermineAccessByProcess",
      "hr",
      dwImpLevela,
      pAuthInfoa);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
    goto LABEL_11;
  }
  wil::details::lambda_call__CLocationPermissionManagerCam::DetermineAccessByProcess_::_2_::_lambda_1___::reset(&v42);
  LOBYTE(v21) = 1;
  v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 88LL))(v49, v21);
  if ( v19 < 0 )
  {
    v20 = 152;
    goto LABEL_18;
  }
  IsCtaPolicyActive = CLocationCamPrimitives::IsCtaPolicyActive();
  v24 = IsCtaPolicyActive;
  if ( a4 == 1 && !IsCtaPolicyActive )
  {
    LOBYTE(v23) = 1;
    v19 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v49 + 128LL))(v49, v23);
    if ( v19 < 0 )
    {
      v20 = 165;
      goto LABEL_18;
    }
  }
  v50 = 0;
  v25 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v49 + 152LL))(v49, &v50);
  if ( v25 >= 0 )
  {
    if ( (unsigned int)dword_1801DDEF8 > 5 )
    {
      v37[0] = v24;
      v38 = a4;
      v39 = v50;
      v40 = a3;
      v44 = (void ***)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5, v26);
      v41 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v41, v28);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(
        v29,
        (unsigned int)&byte_1801B413F,
        v30,
        v31,
        (__int64)&v41,
        (__int64)&v44,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v38,
        (__int64)v37);
    }
    v27 = v50 == 3;
  }
  else
  {
    LODWORD(dwImpLevela) = v25;
    wil::details::in1diag5::Log_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\permissions\\locationpermissionmanagercam.cpp",
      "CLocationPermissionManagerCam::DetermineAccessByProcess",
      "hr",
      dwImpLevela,
      pAuthInfoa);
    v27 = 0;
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v49);
  wil::details::lambda_call__CLocationPermissionManagerCam::DetermineAccessByProcess_::_2_::_lambda_1___::reset(&v42);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
  std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(a6);
  return v27;
}

```

## disassembly

```asm
0x18004edbc  push    rbp
0x18004edbe  push    rbx
0x18004edbf  push    rsi
0x18004edc0  push    rdi
0x18004edc1  push    r12
0x18004edc3  push    r13
0x18004edc5  push    r14
0x18004edc7  push    r15
0x18004edc9  lea     rbp, [rsp-0Fh]
0x18004edce  sub     rsp, 0D8h
0x18004edd5  mov     rax, cs:__security_cookie
0x18004eddc  xor     rax, rsp
0x18004eddf  mov     [rbp+47h+var_50], rax
0x18004ede3  mov     r15d, r9d
0x18004ede6  mov     r13d, r8d
0x18004ede9  mov     [rbp+47h+var_B0], rdx
0x18004eded  mov     rbx, [rbp+47h+arg_28]
0x18004edf1  mov     [rbp+47h+var_98], rbx
0x18004edf5  xor     esi, esi
0x18004edf7  mov     [rbp+47h+pProxy], rsi
0x18004edfb  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_CapabilityAccess@@3QBGB; "Windows.Internal.CapabilityAccess.Capab"...
0x18004ee02  lea     rcx, [rbp+47h+string]; string
0x18004ee06  call    ??$?0$0DD@@StringReference@Internal@Windows@@QEAA@AEAY0DD@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[51])
0x18004ee0b  lea     rdx, [rbp+47h+pProxy]
0x18004ee0f  mov     rcx, [rax]
0x18004ee12  call    ??$GetActivationFactory@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>)
0x18004ee17  test    eax, eax
0x18004ee19  jns     short loc_18004EE5F
0x18004ee1b  mov     rcx, [rbp+4Fh]; this
0x18004ee1f  mov     [rsp+110h+dwImpLevel], eax; char *
0x18004ee23  lea     rax, aHr; "hr"
0x18004ee2a  mov     qword ptr [rsp+110h+dwAuthnLevel], rax; char *
0x18004ee2f  lea     r9, aClocationpermi_4; "CLocationPermissionManagerCam::Determin"...
0x18004ee36  lea     r8, aOnecoreuapDriv_33; "onecoreuap\\drivers\\mobilepc\\location"...
0x18004ee3d  lea     edx, [rsi+62h]; void *
0x18004ee40  call    ?Log_Hr@in1diag5@details@wil@@YAJPEAXIPEBD11J@Z; wil::details::in1diag5::Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18004ee45  nop
0x18004ee46  lea     rcx, [rbp+47h+pProxy]
0x18004ee4a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ee4f  nop
0x18004ee50  mov     rcx, rbx
0x18004ee53  call    ??1?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAA@XZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18004ee58  xor     al, al
0x18004ee5a  jmp     loc_18004F122
0x18004ee5f  mov     [rbp+47h+var_70], sil
0x18004ee63  mov     rax, [rbx]
0x18004ee66  test    rax, rax
0x18004ee69  jz      short loc_18004EE70
0x18004ee6b  mov     rdx, [rax]
0x18004ee6e  jmp     short loc_18004EE73
0x18004ee70  mov     rdx, rsi; Token
0x18004ee73  xor     ecx, ecx; Thread
0x18004ee75  call    cs:__imp_SetThreadToken
0x18004ee7b  test    eax, eax
0x18004ee7d  jnz     short loc_18004EE8A
0x18004ee7f  mov     rcx, [rbp+4Fh]; this
0x18004ee83  call    ?Log_GetLastError@in1diag5@details@wil@@YAKPEAXIPEBD11@Z; wil::details::in1diag5::Log_GetLastError(void *,uint,char const *,char const *,char const *)
0x18004ee88  jmp     short loc_18004EE46
0x18004ee8a  mov     [rbp+47h+var_70], 1
0x18004ee8e  lea     rax, [rbp+47h+var_70]
0x18004ee92  mov     [rbp+47h+var_A8], rax
0x18004ee96  mov     [rbp+47h+var_A0], 1
0x18004ee9a  mov     [rsp+110h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18004eea2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004eea6  mov     [rsp+110h+pAuthInfo], rdi; int
0x18004eeab  mov     [rsp+110h+dwImpLevel], 3; dwImpLevel
0x18004eeb3  mov     [rsp+110h+dwAuthnLevel], esi; dwAuthnLevel
0x18004eeb7  mov     r9, rdi; pServerPrincName
0x18004eeba  mov     eax, 0FFFFFFFFh
0x18004eebf  mov     r8d, eax; dwAuthzSvc
0x18004eec2  mov     edx, eax; dwAuthnSvc
0x18004eec4  mov     rcx, [rbp+47h+pProxy]; pProxy
0x18004eec8  call    cs:__imp_CoSetProxyBlanket
0x18004eece  test    eax, eax
0x18004eed0  jns     short loc_18004EF0D
0x18004eed2  mov     rcx, [rbp+4Fh]; this
0x18004eed6  mov     [rsp+110h+dwImpLevel], eax; char *
0x18004eeda  lea     rax, aHr; "hr"
0x18004eee1  mov     qword ptr [rsp+110h+dwAuthnLevel], rax; char *
0x18004eee6  lea     r9, aClocationpermi_4; "CLocationPermissionManagerCam::Determin"...
0x18004eeed  lea     r8, aOnecoreuapDriv_33; "onecoreuap\\drivers\\mobilepc\\location"...
0x18004eef4  mov     edx, 84h; void *
0x18004eef9  call    ?Log_Hr@in1diag5@details@wil@@YAJPEAXIPEBD11J@Z; wil::details::in1diag5::Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18004eefe  nop
0x18004eeff  lea     rcx, [rbp+47h+var_A8]
0x18004ef03  call    wil__details__lambda_call__CLocationPermissionManagerCam__DetermineAccessByProcess____2____lambda_1_____reset
0x18004ef08  jmp     loc_18004EE46
0x18004ef0d  mov     [rbp+47h+var_60], rsi
0x18004ef11  mov     r14, [rbp+47h+pProxy]
0x18004ef15  mov     rax, [r14]
0x18004ef18  mov     r12, [rax+40h]
0x18004ef1c  lea     rcx, [rbp+47h+var_60]
0x18004ef20  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004ef25  mov     rsi, cs:?c_szCapabilityLocation@@3QEBGEB; ushort const * const c_szCapabilityLocation
0x18004ef2c  xor     eax, eax
0x18004ef2e  inc     rdi
0x18004ef31  cmp     [rsi+rdi*2], ax
0x18004ef35  jnz     short loc_18004EF2E
0x18004ef37  mov     eax, 0FFFFFFFFh
0x18004ef3c  cmp     rdi, rax
0x18004ef3f  jbe     short loc_18004EF58
0x18004ef41  mov     edi, eax
0x18004ef43  xor     r9d, r9d; lpArguments
0x18004ef46  xor     r8d, r8d; nNumberOfArguments
0x18004ef49  lea     edx, [r9+1]; dwExceptionFlags
0x18004ef4d  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004ef52  call    cs:__imp_RaiseException
0x18004ef58  lea     r9, [rbp+47h+string]; string
0x18004ef5c  lea     r8, [rbp+47h+hstringHeader]; hstringHeader
0x18004ef60  mov     edx, edi; length
0x18004ef62  mov     rcx, rsi; sourceString
0x18004ef65  call    cs:__imp_WindowsCreateStringReference
0x18004ef6b  lea     rax, [rbp+47h+var_60]
0x18004ef6f  mov     qword ptr [rsp+110h+dwAuthnLevel], rax
0x18004ef74  xor     r9d, r9d
0x18004ef77  mov     r8d, r13d
0x18004ef7a  mov     rdx, [rbp+47h+string]
0x18004ef7e  mov     rcx, r14
0x18004ef81  mov     rax, r12
0x18004ef84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ef89  xor     esi, esi
0x18004ef8b  test    eax, eax
0x18004ef8d  jns     short loc_18004EFCA
0x18004ef8f  mov     edx, 8Dh; void *
0x18004ef94  mov     [rsp+110h+dwImpLevel], eax; char *
0x18004ef98  lea     rax, aHr; "hr"
0x18004ef9f  mov     rcx, [rbp+4Fh]; this
0x18004efa3  mov     qword ptr [rsp+110h+dwAuthnLevel], rax; char *
0x18004efa8  lea     r9, aClocationpermi_4; "CLocationPermissionManagerCam::Determin"...
0x18004efaf  lea     r8, aOnecoreuapDriv_33; "onecoreuap\\drivers\\mobilepc\\location"...
0x18004efb6  call    ?Log_Hr@in1diag5@details@wil@@YAJPEAXIPEBD11J@Z; wil::details::in1diag5::Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18004efbb  nop
0x18004efbc  lea     rcx, [rbp+47h+var_60]
0x18004efc0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004efc5  jmp     loc_18004EEFF
0x18004efca  lea     rcx, [rbp+47h+var_A8]
0x18004efce  call    wil__details__lambda_call__CLocationPermissionManagerCam__DetermineAccessByProcess____2____lambda_1_____reset
0x18004efd3  mov     rcx, [rbp+47h+var_60]
0x18004efd7  mov     rax, [rcx]
0x18004efda  mov     dl, 1
0x18004efdc  mov     rax, [rax+58h]
0x18004efe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004efe5  test    eax, eax
0x18004efe7  jns     short loc_18004EFF0
0x18004efe9  mov     edx, 98h
0x18004efee  jmp     short loc_18004EF94
0x18004eff0  call    ?IsCtaPolicyActive@CLocationCamPrimitives@@SA_NXZ; CLocationCamPrimitives::IsCtaPolicyActive(void)
0x18004eff5  mov     dil, al
0x18004eff8  cmp     r15d, 1
0x18004effc  jnz     short loc_18004F026
0x18004effe  test    al, al
0x18004f000  jnz     short loc_18004F026
0x18004f002  mov     rcx, [rbp+47h+var_60]
0x18004f006  mov     r8, [rcx]
0x18004f009  mov     dl, r15b
0x18004f00c  mov     rax, [r8+80h]
0x18004f013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f018  test    eax, eax
0x18004f01a  jns     short loc_18004F026
0x18004f01c  mov     edx, 0A5h
0x18004f021  jmp     loc_18004EF94
0x18004f026  mov     [rbp+47h+var_58], esi
0x18004f029  mov     rcx, [rbp+47h+var_60]
0x18004f02d  mov     rax, [rcx]
0x18004f030  lea     rdx, [rbp+47h+var_58]
0x18004f034  mov     rax, [rax+98h]
0x18004f03b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f040  test    eax, eax
0x18004f042  jns     short loc_18004F078
0x18004f044  mov     rcx, [rbp+4Fh]; this
0x18004f048  mov     [rsp+110h+dwImpLevel], eax; char *
0x18004f04c  lea     rax, aHr; "hr"
0x18004f053  mov     qword ptr [rsp+110h+dwAuthnLevel], rax; char *
0x18004f058  lea     r9, aClocationpermi_4; "CLocationPermissionManagerCam::Determin"...
0x18004f05f  lea     r8, aOnecoreuapDriv_33; "onecoreuap\\drivers\\mobilepc\\location"...
0x18004f066  mov     edx, 0AEh; void *
0x18004f06b  call    ?Log_Hr@in1diag5@details@wil@@YAJPEAXIPEBD11J@Z; wil::details::in1diag5::Log_Hr(void *,uint,char const *,char const *,char const *,long)
0x18004f070  mov     dil, sil
0x18004f073  jmp     loc_18004F0F9
0x18004f078  mov     eax, cs:dword_1801DDEF8
0x18004f07e  cmp     eax, 5
0x18004f081  jbe     short loc_18004F0F1
0x18004f083  mov     [rbp+47h+var_C0], dil
0x18004f087  mov     [rbp+47h+var_BC], r15d
0x18004f08b  mov     eax, [rbp+47h+var_58]
0x18004f08e  mov     [rbp+47h+var_B8], eax
0x18004f091  mov     [rbp+47h+var_B4], r13d
0x18004f095  mov     rcx, [rbp+47h+arg_20]
0x18004f099  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004f09e  mov     [rbp+47h+var_98], rax
0x18004f0a2  mov     rcx, [rbp+47h+var_B0]
0x18004f0a6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004f0ab  mov     [rbp+47h+var_B0], rax
0x18004f0af  lea     rax, [rbp+47h+var_C0]
0x18004f0b3  mov     [rsp+110h+var_C8], rax
0x18004f0b8  lea     rax, [rbp+47h+var_BC]
0x18004f0bc  mov     [rsp+110h+var_D0], rax
0x18004f0c1  lea     rax, [rbp+47h+var_B8]
0x18004f0c5  mov     qword ptr [rsp+110h+dwCapabilities], rax
0x18004f0ca  lea     rax, [rbp+47h+var_B4]
0x18004f0ce  mov     [rsp+110h+pAuthInfo], rax
0x18004f0d3  lea     rax, [rbp+47h+var_98]
0x18004f0d7  mov     qword ptr [rsp+110h+dwImpLevel], rax
0x18004f0dc  lea     rax, [rbp+47h+var_B0]
0x18004f0e0  mov     qword ptr [rsp+110h+dwAuthnLevel], rax
0x18004f0e5  lea     rdx, byte_1801B413F
0x18004f0ec  call    ??$Write@U?$_tlgWrapSz@G@@U1@U?$_tlgWrapperByVal@$03@@U2@U2@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3AEBU?$_tlgWrapperByVal@$03@@44AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &)
0x18004f0f1  cmp     [rbp+47h+var_58], 3
0x18004f0f5  setz    dil
0x18004f0f9  lea     rcx, [rbp+47h+var_60]
0x18004f0fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004f102  nop
0x18004f103  lea     rcx, [rbp+47h+var_A8]
0x18004f107  call    wil__details__lambda_call__CLocationPermissionManagerCam__DetermineAccessByProcess____2____lambda_1_____reset
0x18004f10c  nop
0x18004f10d  lea     rcx, [rbp+47h+pProxy]
0x18004f111  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004f116  nop
0x18004f117  mov     rcx, rbx
0x18004f11a  call    ??1?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@QEAA@XZ; std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18004f11f  mov     al, dil
0x18004f122  mov     rcx, [rbp+47h+var_50]
0x18004f126  xor     rcx, rsp; StackCookie
0x18004f129  call    __security_check_cookie
0x18004f12e  add     rsp, 0D8h
0x18004f135  pop     r15
0x18004f137  pop     r14
0x18004f139  pop     r13
0x18004f13b  pop     r12
0x18004f13d  pop     rdi
0x18004f13e  pop     rsi
0x18004f13f  pop     rbx
0x18004f140  pop     rbp
0x18004f141  retn
```
