# LicenseInstanceChangeListener::LicenseChanged(void)

- ea: `0x180058d60`
- end: `0x1800593b5`
- name: `?LicenseChanged@LicenseInstanceChangeListener@@UEAAJXZ`
- size: `1621`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `29`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000b7a4`
- `0x18000b7fc`
- `0x180012dc0`
- `0x180013b50`
- `0x180017230`
- `0x180017370`
- `0x180017654`
- `0x18001dad0`
- `0x18002aae8`
- `0x180058d60`
- `0x1800593bc`
- `0x1800629dc`
- `0x180062a40`
- `0x1800661b8`
- `0x180069b80`
- `0x18006cfe0`
- `0x18006d1bc`
- `0x18006d3f8`
- `0x18006edac`
- `0x180075e60`
- `0x1800767e0`
- `0x1800769f4`
- `0x18008a400`
- `0x18008dbd0`
- `0x18008e624`
- `0x18008ea14`
- `0x180090f14`
- `0x180090fe4`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180058ee5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180058f8e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180058fa5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180058ee5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180058f8e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180058fa5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18005906d`
- `api-ms-win-core-threadpool-legacy-l1-1-0!QueueUserWorkItem` at `0x18005906d`
- `ntdll!RtlPublishWnfStateData` at `0x1800592df`
- `ntdll!RtlPublishWnfStateData` at `0x1800592df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059201`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059201`

## string_xrefs

- `0x180058dc8`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180058dfc`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180058e30`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180058e64`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180058f48`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18005907f`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180059188`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x1800591cd`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180059235`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x1800592b2`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x180059315`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall LicenseInstanceChangeListener::LicenseChanged(char *Parameter)
{
  _QWORD *v2; // r14
  int v3; // eax
  int v4; // eax
  int v5; // eax
  int v6; // eax
  int v7; // eax
  void **v8; // rcx
  _QWORD *v9; // rdi
  const char *v10; // r9
  unsigned __int16 *v11; // rdi
  _QWORD *v12; // r8
  char *v13; // rcx
  const unsigned __int16 *v14; // r8
  int v15; // eax
  int v16; // eax
  _QWORD *v17; // r15
  __int64 (__fastcall *v18)(_QWORD *, LPVOID *); // r12
  void *v19; // r14
  int v20; // eax
  unsigned __int64 v21; // rcx
  const unsigned __int16 *v22; // r8
  int v23; // eax
  int v24; // eax
  int v25; // r14d
  unsigned int v26; // r8d
  _QWORD *v27; // rcx
  int DueTime; // [rsp+20h] [rbp-3E8h]
  int DueTimea; // [rsp+20h] [rbp-3E8h]
  _QWORD *v31; // [rsp+40h] [rbp-3C8h] BYREF
  int v32; // [rsp+48h] [rbp-3C0h] BYREF
  int v33; // [rsp+4Ch] [rbp-3BCh] BYREF
  int v34; // [rsp+50h] [rbp-3B8h] BYREF
  int v35; // [rsp+54h] [rbp-3B4h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-3B0h] BYREF
  char v37[8]; // [rsp+60h] [rbp-3A8h] BYREF
  unsigned __int16 *v38[2]; // [rsp+68h] [rbp-3A0h] BYREF
  __int64 v39; // [rsp+78h] [rbp-390h]
  __int64 v40; // [rsp+80h] [rbp-388h]
  _BYTE v41[16]; // [rsp+88h] [rbp-380h] BYREF
  __int64 v42; // [rsp+98h] [rbp-370h]
  int v43; // [rsp+B0h] [rbp-358h] BYREF
  int v44; // [rsp+B4h] [rbp-354h] BYREF
  unsigned __int16 v45[255]; // [rsp+B8h] [rbp-350h] BYREF
  unsigned __int16 v46[133]; // [rsp+2B6h] [rbp-152h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+408h] [rbp+0h]

  v34 = 0;
  v32 = 0;
  v33 = 0;
  v35 = 0;
  v2 = Parameter + 184;
  v3 = (*(__int64 (__fastcall **)(_QWORD, int *))(**((_QWORD **)Parameter + 23) + 24LL))(
         *((_QWORD *)Parameter + 23),
         &v34);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)(unsigned int)v3,
      DueTime);
  v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v2 + 72LL))(*v2, &v32);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AB,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)(unsigned int)v4,
      DueTime);
  v5 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v2 + 48LL))(*v2, &v33);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AC,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)(unsigned int)v5,
      DueTime);
  v6 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v2 + 56LL))(*v2, &v35);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1AD,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)(unsigned int)v6,
      DueTime);
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(Parameter + 200);
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(Parameter + 216);
  if ( v34 || v35 == 4 )
  {
    if ( v32 )
    {
      if ( v34 )
      {
        LicenseInstanceChangeListener::GetLeaseIdFromInstance(v41, v2);
        if ( v42 && (unsigned __int8)std::operator!=<unsigned short>(v41, Parameter + 144) )
        {
          std::wstring::swap(Parameter + 144, v41);
          v9 = operator new(0x28u);
          *(_OWORD *)v9 = 0;
          v9[2] = 0;
          v9[3] = 7;
          *(_WORD *)v9 = 0;
          v9[4] = 0;
          v31 = v9;
          std::wstring::operator=(v9, Parameter + 144);
          Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(v9 + 4, Parameter + 192);
          if ( !QueueUserWorkItem(LicenseInstanceChangeListener::AddLeaseToWnsThreadProc, v9, 0x10u) )
            wil::details::in1diag3::_Throw_GetLastError(
              retaddr,
              (void *)0x1FC,
              (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
              v10);
          v31 = 0;
          std::unique_ptr<ActiveLease>::~unique_ptr<ActiveLease>(&v31);
        }
        v11 = (unsigned __int16 *)(Parameter + 48);
        if ( !(unsigned int)std::wstring::compare(Parameter + 48, Parameter + 80) )
        {
          v31 = (_QWORD *)*v2;
          Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v31);
          v12 = Parameter + 112;
          if ( *((_QWORD *)Parameter + 17) > 7u )
            v12 = (_QWORD *)*v12;
          if ( *((_QWORD *)Parameter + 9) <= 7u )
            v13 = Parameter + 48;
          else
            v13 = *(char **)v11;
          if ( (unsigned __int8)ShouldPublishWnfForTrialLicense(v13, *((unsigned int *)Parameter + 45), v12, &v31) )
          {
            v31 = (_QWORD *)*v2;
            Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(&v31);
            if ( *((_QWORD *)Parameter + 9) > 7u )
              v11 = *(unsigned __int16 **)v11;
            PublishWnfForTrialLicense(v11);
          }
          else if ( *((_DWORD *)Parameter + 44) != v33 )
          {
            v43 = -2143326198;
            memset_0(&v44, 0, 0x308u);
            if ( *((_QWORD *)Parameter + 9) <= 7u )
              v14 = (const unsigned __int16 *)(Parameter + 48);
            else
              v14 = *(const unsigned __int16 **)v11;
            v15 = StringCchCopyW(v46, 0x80u, v14);
            if ( v15 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x20A,
                (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
                (const char *)(unsigned int)v15,
                DueTime);
            pv = 0;
            v31 = 0;
            v16 = (*(__int64 (__fastcall **)(_QWORD, GUID *, _QWORD **))(*(_QWORD *)*v2 + 104LL))(
                    *v2,
                    &GUID_cb5b47a9_6537_451f_8dd7_d305ae3dea57,
                    &v31);
            if ( v16 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x20E,
                (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
                (const char *)(unsigned int)v16,
                DueTime);
            v17 = v31;
            v18 = *(__int64 (__fastcall **)(_QWORD *, LPVOID *))(*v31 + 96LL);
            v19 = pv;
            if ( pv )
            {
              wil::last_error_context::last_error_context((wil::last_error_context *)v37);
              CoTaskMemFree(v19);
              wil::last_error_context::~last_error_context((wil::last_error_context *)v37);
            }
            pv = 0;
            v20 = v18(v17, &pv);
            if ( v20 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x20F,
                (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
                (const char *)(unsigned int)v20,
                DueTime);
            *(_OWORD *)v38 = 0;
            v39 = 0;
            v21 = 7;
            v40 = 7;
            LOWORD(v38[0]) = 0;
            if ( pv )
            {
              std::wstring::assign(v38, pv);
              v21 = v40;
            }
            v22 = (const unsigned __int16 *)v38;
            if ( v21 > 7 )
              v22 = v38[0];
            v23 = StringCchCopyW(v45, 0xFFu, v22);
            if ( v23 < 0 )
              wil::details::in1diag3::Throw_Hr(
                retaddr,
                (void *)0x217,
                (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
                (const char *)(unsigned int)v23,
                DueTime);
            v24 = RtlPublishWnfStateData(WNF_LM_APP_LICENSE_EVENT, 0, &v43, 780, 0);
            v25 = v24;
            if ( *((_QWORD *)Parameter + 9) > 7u )
              v11 = *(unsigned __int16 **)v11;
            LogMessage(
              3u,
              "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
              0x21Au,
              "LicenseInstanceChangeListener::LicenseChanged",
              (wchar_t *)L"Sent LM_E_BETTER_LICENSE_ACQUIRED for %s - status = 0x%08x",
              v11,
              v24);
            if ( v25 < 0 )
              wil::details::in1diag3::_Throw_NtStatus(
                retaddr,
                (void *)0x21B,
                v26,
                (const char *)(unsigned int)v25,
                DueTimea);
            ContentIdString::~ContentIdString((ContentIdString *)v38);
            v27 = v31;
            if ( v31 )
            {
              v31 = 0;
              (*(void (__fastcall **)(_QWORD *))(*v27 + 16LL))(v27);
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pv);
          }
        }
        ContentIdString::~ContentIdString((ContentIdString *)v41);
      }
    }
    else if ( (unsigned int)std::wstring::compare(Parameter + 48, Parameter + 80) )
    {
      CreateTimerQueueTimer(
        (PHANDLE)Parameter + 26,
        0,
        _lambda_015fa07e64deeaf16bb99ba439b03d5a_::_lambda_invoker_cdecl_,
        Parameter,
        0x2710u,
        0xFFFFFFFF,
        0);
      LicenseInstanceChangeListener::PublishWnfForOptionalPackage((LicenseInstanceChangeListener *)Parameter);
    }
    else
    {
      v43 = 0;
      v44 = *((_DWORD *)Parameter + 45);
      memset_0(v45, 0, 0x100u);
      v7 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v2 + 80LL))(*v2, &v43);
      if ( v7 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CD,
          (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
          (const char *)(unsigned int)v7,
          DueTime);
      v8 = (void **)(Parameter + 224);
      if ( v43 == -2143322103 )
      {
        CreateTimerQueueTimer(
          v8,
          0,
          _lambda_f64b3a118003134bf78be4bf13da95e4_::_lambda_invoker_cdecl_,
          Parameter,
          0x2710u,
          0xFFFFFFFF,
          0);
        LicenseInstanceChangeListener::PublishWnfForExpiredTrial((LicenseInstanceChangeListener *)Parameter);
      }
      else
      {
        CreateTimerQueueTimer(
          v8,
          0,
          _lambda_57ad34d32e88bcfb76fc2d55e38ecef1_::_lambda_invoker_cdecl_,
          Parameter,
          0x2710u,
          0xFFFFFFFF,
          0);
        LicenseInstanceChangeListener::PublishWnfForPackage((LicenseInstanceChangeListener *)Parameter);
      }
    }
  }
  *((_DWORD *)Parameter + 44) = v33;
  return 0;
}

```

## disassembly

```asm
0x180058d60  push    rbx
0x180058d62  push    rdi
0x180058d63  push    r12
0x180058d65  push    r13
0x180058d67  push    r14
0x180058d69  push    r15
0x180058d6b  sub     rsp, 3D8h
0x180058d72  mov     rax, cs:__security_cookie
0x180058d79  xor     rax, rsp
0x180058d7c  mov     [rsp+408h+var_48], rax
0x180058d84  mov     rbx, rcx
0x180058d87  xor     r13d, r13d
0x180058d8a  mov     [rsp+408h+var_3B8], r13d
0x180058d8f  mov     [rsp+408h+var_3C0], r13d
0x180058d94  mov     [rsp+408h+var_3BC], r13d
0x180058d99  mov     [rsp+408h+var_3B4], r13d
0x180058d9e  lea     r14, [rcx+0B8h]
0x180058da5  mov     rcx, [r14]
0x180058da8  mov     rax, [rcx]
0x180058dab  lea     rdx, [rsp+408h+var_3B8]
0x180058db0  mov     rax, [rax+18h]
0x180058db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058db9  mov     rcx, [rsp+408h]; this
0x180058dc1  test    eax, eax
0x180058dc3  jns     short loc_180058DD9
0x180058dc5  mov     r9d, eax; char *
0x180058dc8  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180058dcf  mov     edx, 1AAh; void *
0x180058dd4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058dd9  mov     rcx, [r14]
0x180058ddc  mov     rax, [rcx]
0x180058ddf  lea     rdx, [rsp+408h+var_3C0]
0x180058de4  mov     rax, [rax+48h]
0x180058de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058ded  mov     rcx, [rsp+408h]; this
0x180058df5  test    eax, eax
0x180058df7  jns     short loc_180058E0D
0x180058df9  mov     r9d, eax; char *
0x180058dfc  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180058e03  mov     edx, 1ABh; void *
0x180058e08  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058e0d  mov     rcx, [r14]
0x180058e10  mov     rax, [rcx]
0x180058e13  lea     rdx, [rsp+408h+var_3BC]
0x180058e18  mov     rax, [rax+30h]
0x180058e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e21  mov     rcx, [rsp+408h]; this
0x180058e29  test    eax, eax
0x180058e2b  jns     short loc_180058E41
0x180058e2d  mov     r9d, eax; char *
0x180058e30  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180058e37  mov     edx, 1ACh; void *
0x180058e3c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058e41  mov     rcx, [r14]
0x180058e44  mov     rax, [rcx]
0x180058e47  lea     rdx, [rsp+408h+var_3B4]
0x180058e4c  mov     rax, [rax+38h]
0x180058e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058e55  mov     rcx, [rsp+408h]; this
0x180058e5d  test    eax, eax
0x180058e5f  jns     short loc_180058E75
0x180058e61  mov     r9d, eax; char *
0x180058e64  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180058e6b  mov     edx, 1ADh; void *
0x180058e70  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058e75  lea     rcx, [rbx+0C8h]
0x180058e7c  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180058e81  lea     rcx, [rbx+0D8h]
0x180058e88  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180058e8d  mov     ecx, [rsp+408h+var_3B8]
0x180058e91  test    ecx, ecx
0x180058e93  jnz     short loc_180058EA0
0x180058e95  cmp     [rsp+408h+var_3B4], 4
0x180058e9a  jnz     loc_180059380
0x180058ea0  mov     eax, [rsp+408h+var_3C0]
0x180058ea4  test    eax, eax
0x180058ea6  jnz     loc_180058FB8
0x180058eac  lea     rdx, [rbx+50h]
0x180058eb0  lea     rcx, [rbx+30h]
0x180058eb4  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x180058eb9  test    eax, eax
0x180058ebb  jz      short loc_180058EF8
0x180058ebd  lea     rcx, [rbx+0D0h]; phNewTimer
0x180058ec4  mov     [rsp+408h+Flags], r13d; Flags
0x180058ec9  mov     [rsp+408h+Period], 0FFFFFFFFh; Period
0x180058ed1  mov     [rsp+408h+DueTime], 2710h; DueTime
0x180058ed9  mov     r9, rbx; Parameter
0x180058edc  lea     r8, ?_lambda_invoker_cdecl_@_lambda_015fa07e64deeaf16bb99ba439b03d5a_@@CA@PEAXE@Z; Callback
0x180058ee3  xor     edx, edx; TimerQueue
0x180058ee5  call    cs:__imp_CreateTimerQueueTimer
0x180058eeb  mov     rcx, rbx; this
0x180058eee  call    ?PublishWnfForOptionalPackage@LicenseInstanceChangeListener@@QEAAXXZ; LicenseInstanceChangeListener::PublishWnfForOptionalPackage(void)
0x180058ef3  jmp     loc_180058FB3
0x180058ef8  mov     [rsp+408h+var_358], r13d
0x180058f00  mov     eax, [rbx+0B4h]
0x180058f06  mov     [rsp+408h+var_354], eax
0x180058f0d  xor     edx, edx; Val
0x180058f0f  mov     r8d, 100h; Size
0x180058f15  lea     rcx, [rsp+408h+var_350]; void *
0x180058f1d  call    memset_0
0x180058f22  mov     rcx, [r14]
0x180058f25  mov     rax, [rcx]
0x180058f28  lea     rdx, [rsp+408h+var_358]
0x180058f30  mov     rax, [rax+50h]
0x180058f34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058f39  mov     rcx, [rsp+408h]; this
0x180058f41  test    eax, eax
0x180058f43  jns     short loc_180058F59
0x180058f45  mov     r9d, eax; char *
0x180058f48  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180058f4f  mov     edx, 1CDh; void *
0x180058f54  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180058f59  lea     rcx, [rbx+0E0h]; phNewTimer
0x180058f60  mov     [rsp+408h+Flags], r13d; Flags
0x180058f65  mov     r9, rbx; Parameter
0x180058f68  xor     edx, edx; TimerQueue
0x180058f6a  mov     [rsp+408h+Period], 0FFFFFFFFh; Period
0x180058f72  mov     [rsp+408h+DueTime], 2710h; DueTime
0x180058f7a  cmp     [rsp+408h+var_358], 803F8009h
0x180058f85  jnz     short loc_180058F9E
0x180058f87  lea     r8, ?_lambda_invoker_cdecl_@_lambda_f64b3a118003134bf78be4bf13da95e4_@@CA@PEAXE@Z; Callback
0x180058f8e  call    cs:__imp_CreateTimerQueueTimer
0x180058f94  mov     rcx, rbx; this
0x180058f97  call    ?PublishWnfForExpiredTrial@LicenseInstanceChangeListener@@QEAAXXZ; LicenseInstanceChangeListener::PublishWnfForExpiredTrial(void)
0x180058f9c  jmp     short loc_180058FB3
0x180058f9e  lea     r8, ?_lambda_invoker_cdecl_@_lambda_57ad34d32e88bcfb76fc2d55e38ecef1_@@CA@PEAXE@Z; Callback
0x180058fa5  call    cs:__imp_CreateTimerQueueTimer
0x180058fab  mov     rcx, rbx; this
0x180058fae  call    ?PublishWnfForPackage@LicenseInstanceChangeListener@@QEAAXXZ; LicenseInstanceChangeListener::PublishWnfForPackage(void)
0x180058fb3  jmp     loc_180059380
0x180058fb8  test    ecx, ecx
0x180058fba  jz      loc_180059380
0x180058fc0  test    eax, eax
0x180058fc2  jz      loc_180059380
0x180058fc8  mov     rdx, r14
0x180058fcb  lea     rcx, [rsp+408h+var_380]
0x180058fd3  call    ?GetLeaseIdFromInstance@LicenseInstanceChangeListener@@CA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@@Z; LicenseInstanceChangeListener::GetLeaseIdFromInstance(Microsoft::WRL::ComPtr<ILicenseInstance> const &)
0x180058fd8  nop
0x180058fd9  cmp     [rsp+408h+var_370], r13
0x180058fe1  jz      loc_18005909F
0x180058fe7  lea     r15, [rbx+90h]
0x180058fee  mov     rdx, r15
0x180058ff1  lea     rcx, [rsp+408h+var_380]
0x180058ff9  call    ??$?9GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator!=<ushort>(std::wstring const &,std::wstring const &)
0x180058ffe  test    al, al
0x180059000  jz      loc_18005909F
0x180059006  lea     rdx, [rsp+408h+var_380]
0x18005900e  mov     rcx, r15
0x180059011  call    ?swap@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAXAEAV12@@Z; std::wstring::swap(std::wstring &)
0x180059016  mov     ecx, 28h ; '('; Size
0x18005901b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180059020  mov     rdi, rax
0x180059023  xorps   xmm0, xmm0
0x180059026  movups  xmmword ptr [rax], xmm0
0x180059029  mov     [rax+10h], r13
0x18005902d  mov     qword ptr [rax+18h], 7
0x180059035  mov     [rax], r13w
0x180059039  mov     [rax+20h], r13
0x18005903d  mov     [rsp+408h+var_3C8], rax
0x180059042  mov     rdx, r15
0x180059045  mov     rcx, rax
0x180059048  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005904d  lea     rdx, [rbx+0C0h]
0x180059054  lea     rcx, [rdi+20h]
0x180059058  call    ??4?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ILicenseInstance>::operator=(Microsoft::WRL::ComPtr<ILicenseInstance> const &)
0x18005905d  mov     r8d, 10h; Flags
0x180059063  mov     rdx, rdi; Context
0x180059066  lea     rcx, ?AddLeaseToWnsThreadProc@LicenseInstanceChangeListener@@CAKPEAX@Z; Function
0x18005906d  call    cs:__imp_QueueUserWorkItem
0x180059073  mov     rcx, [rsp+408h]; this
0x18005907b  test    eax, eax
0x18005907d  jnz     short loc_180059090
0x18005907f  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x180059086  mov     edx, 1FCh; void *
0x18005908b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180059090  mov     [rsp+408h+var_3C8], r13
0x180059095  lea     rcx, [rsp+408h+var_3C8]
0x18005909a  call    ??1?$unique_ptr@VActiveLease@@U?$default_delete@VActiveLease@@@std@@@std@@QEAA@XZ; std::unique_ptr<ActiveLease>::~unique_ptr<ActiveLease>(void)
0x18005909f  lea     rdi, [rbx+30h]
0x1800590a3  lea     rdx, [rbx+50h]
0x1800590a7  mov     rcx, rdi
0x1800590aa  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHAEBV12@@Z; std::wstring::compare(std::wstring const &)
0x1800590af  test    eax, eax
0x1800590b1  jnz     loc_180059373
0x1800590b7  mov     rax, [r14]
0x1800590ba  mov     [rsp+408h+var_3C8], rax
0x1800590bf  lea     rcx, [rsp+408h+var_3C8]
0x1800590c4  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x1800590c9  lea     r8, [rbx+70h]
0x1800590cd  cmp     qword ptr [r8+18h], 7
0x1800590d2  jbe     short loc_1800590D7
0x1800590d4  mov     r8, [r8]
0x1800590d7  cmp     qword ptr [rdi+18h], 7
0x1800590dc  jbe     short loc_1800590E3
0x1800590de  mov     rcx, [rdi]
0x1800590e1  jmp     short loc_1800590E6
0x1800590e3  mov     rcx, rdi
0x1800590e6  lea     r9, [rsp+408h+var_3C8]
0x1800590eb  mov     edx, [rbx+0B4h]
0x1800590f1  call    ?ShouldPublishWnfForTrialLicense@@YA_NPEBGK0V?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@@Z; ShouldPublishWnfForTrialLicense(ushort const *,ulong,ushort const *,Microsoft::WRL::ComPtr<ILicenseInstance>)
0x1800590f6  test    al, al
0x1800590f8  jz      short loc_180059128
0x1800590fa  mov     rax, [r14]
0x1800590fd  mov     [rsp+408h+var_3C8], rax
0x180059102  lea     rcx, [rsp+408h+var_3C8]
0x180059107  call    ?InternalAddRef@?$ComPtr@VClipKeyDocument@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<ClipKeyDocument>::InternalAddRef(void)
0x18005910c  cmp     qword ptr [rdi+18h], 7
0x180059111  jbe     short loc_180059116
0x180059113  mov     rdi, [rdi]
0x180059116  lea     rdx, [rsp+408h+var_3C8]
0x18005911b  mov     rcx, rdi; unsigned __int16 *
0x18005911e  call    ?PublishWnfForTrialLicense@@YAXPEBGV?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@@Z; PublishWnfForTrialLicense(ushort const *,Microsoft::WRL::ComPtr<ILicenseInstance>)
0x180059123  jmp     loc_180059373
0x180059128  mov     eax, [rsp+408h+var_3BC]
0x18005912c  cmp     [rbx+0B0h], eax
0x180059132  jz      loc_180059373
0x180059138  mov     [rsp+408h+var_358], 803F700Ah
0x180059143  xor     edx, edx; Val
0x180059145  mov     r8d, 308h; Size
0x18005914b  lea     rcx, [rsp+408h+var_354]; void *
0x180059153  call    memset_0
0x180059158  cmp     qword ptr [rdi+18h], 7
0x18005915d  jbe     short loc_180059164
0x18005915f  mov     r8, [rdi]
0x180059162  jmp     short loc_180059167
0x180059164  mov     r8, rdi; unsigned __int16 *
0x180059167  mov     edx, 80h; unsigned __int64
0x18005916c  lea     rcx, [rsp+408h+var_152]; unsigned __int16 *
0x180059174  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180059179  mov     rcx, [rsp+408h]; this
0x180059181  test    eax, eax
0x180059183  jns     short loc_180059199
0x180059185  mov     r9d, eax; char *
0x180059188  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005918f  mov     edx, 20Ah; void *
0x180059194  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180059199  mov     [rsp+408h+pv], r13
0x18005919e  mov     [rsp+408h+var_3C8], r13
0x1800591a3  mov     rcx, [r14]
0x1800591a6  mov     rax, [rcx]
0x1800591a9  lea     r8, [rsp+408h+var_3C8]
0x1800591ae  lea     rdx, _GUID_cb5b47a9_6537_451f_8dd7_d305ae3dea57
0x1800591b5  mov     rax, [rax+68h]
0x1800591b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800591be  mov     rcx, [rsp+408h]; this
0x1800591c6  test    eax, eax
0x1800591c8  jns     short loc_1800591DE
0x1800591ca  mov     r9d, eax; char *
0x1800591cd  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800591d4  mov     edx, 20Eh; void *
0x1800591d9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800591de  mov     r15, [rsp+408h+var_3C8]
0x1800591e3  mov     rax, [r15]
0x1800591e6  mov     r12, [rax+60h]
0x1800591ea  mov     r14, [rsp+408h+pv]
0x1800591ef  test    r14, r14
0x1800591f2  jz      short loc_180059211
0x1800591f4  lea     rcx, [rsp+408h+var_3A8]; this
0x1800591f9  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800591fe  mov     rcx, r14; pv
0x180059201  call    cs:__imp_CoTaskMemFree
0x180059207  lea     rcx, [rsp+408h+var_3A8]; this
0x18005920c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180059211  mov     [rsp+408h+pv], r13
0x180059216  lea     rdx, [rsp+408h+pv]
0x18005921b  mov     rcx, r15
0x18005921e  mov     rax, r12
0x180059221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059226  mov     rcx, [rsp+408h]; this
0x18005922e  test    eax, eax
0x180059230  jns     short loc_180059246
0x180059232  mov     r9d, eax; char *
0x180059235  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18005923c  mov     edx, 20Fh; void *
0x180059241  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180059246  xorps   xmm0, xmm0
0x180059249  movups  xmmword ptr [rsp+408h+var_3A0], xmm0
0x18005924e  mov     [rsp+408h+var_390], r13
0x180059253  mov     ecx, 7
0x180059258  mov     [rsp+408h+var_388], rcx
0x180059260  mov     word ptr [rsp+408h+var_3A0], r13w
0x180059266  mov     rdx, [rsp+408h+pv]
0x18005926b  test    rdx, rdx
0x18005926e  jz      short loc_180059282
0x180059270  lea     rcx, [rsp+408h+var_3A0]
0x180059275  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18005927a  mov     rcx, [rsp+408h+var_388]
0x180059282  lea     r8, [rsp+408h+var_3A0]
0x180059287  cmp     rcx, 7
0x18005928b  cmova   r8, [rsp+408h+var_3A0]; unsigned __int16 *
0x180059291  mov     edx, 0FFh; unsigned __int64
0x180059296  lea     rcx, [rsp+408h+var_350]; unsigned __int16 *
0x18005929e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800592a3  mov     rcx, [rsp+408h]; this
0x1800592ab  test    eax, eax
0x1800592ad  jns     short loc_1800592C3
0x1800592af  mov     r9d, eax; char *
0x1800592b2  lea     r8, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800592b9  mov     edx, 217h; void *
0x1800592be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
  ... truncated ...
```
