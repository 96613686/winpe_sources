# PublishWnfForTrialLicense(ushort const *,Microsoft::WRL::ComPtr<ILicenseInstance>)

- ea: `0x18008ea14`
- end: `0x18008f1da`
- name: `?PublishWnfForTrialLicense@@YAXPEBGV?$ComPtr@UILicenseInstance@@@WRL@Microsoft@@@Z`
- size: `1990`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180029664`
- `0x180058d60`

## callees

- `0x1800027c4`
- `0x180002a20`
- `0x180002b14`
- `0x180004738`
- `0x18000ca28`
- `0x180012dc0`
- `0x180013b50`
- `0x180017230`
- `0x18002aae8`
- `0x180046f88`
- `0x180055b04`
- `0x1800593bc`
- `0x18006cd80`
- `0x18006d3f8`
- `0x180075e60`
- `0x1800769f4`
- `0x18008ea14`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008ead4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008ead4`
- `ntdll!RtlPublishWnfStateData` at `0x18008ec32`
- `ntdll!RtlPublishWnfStateData` at `0x18008eecc`
- `ntdll!RtlPublishWnfStateData` at `0x18008ec32`
- `ntdll!RtlPublishWnfStateData` at `0x18008eecc`

## string_xrefs

- `0x18008ec60`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008eefa`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008f135`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008f14a`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008f15f`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008f174`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008f189`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008f19e`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008f1b3`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008f1c8`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PublishWnfForTrialLicense(unsigned __int16 *a1, _QWORD *a2)
{
  int v4; // eax
  int v5; // eax
  struct _FILETIME v6; // rbx
  int v7; // eax
  __int64 v8; // rax
  int v9; // eax
  const unsigned __int16 *v10; // r8
  int v11; // eax
  int v12; // r15d
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  unsigned __int16 **v16; // rax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  unsigned __int16 **v20; // rax
  int v21; // eax
  __int64 v22; // rax
  int v23; // eax
  const unsigned __int16 *v24; // r8
  int v25; // eax
  DWORD v26; // r15d
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  unsigned __int16 **v30; // rax
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  unsigned __int16 **v34; // rax
  __int64 *v35; // rcx
  int Format; // [rsp+20h] [rbp-E0h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+68h] [rbp-98h] BYREF
  struct _FILETIME v40; // [rsp+70h] [rbp-90h] BYREF
  const char *v41; // [rsp+78h] [rbp-88h] BYREF
  const wchar_t *v42; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v43; // [rsp+88h] [rbp-78h] BYREF
  __int64 v44; // [rsp+90h] [rbp-70h] BYREF
  const wchar_t *v45; // [rsp+98h] [rbp-68h] BYREF
  const char *v46; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD v47[2]; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE v48[16]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v49[2]; // [rsp+C8h] [rbp-38h] BYREF
  __m128i si128; // [rsp+D8h] [rbp-28h]
  int v51; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v52[4]; // [rsp+F4h] [rbp-Ch] BYREF
  unsigned __int16 v53[255]; // [rsp+F8h] [rbp-8h] BYREF
  unsigned __int16 v54[129]; // [rsp+2F6h] [rbp+1F6h] BYREF
  int v55; // [rsp+3F8h] [rbp+2F8h]
  wil::details::in1diag3 *retaddr; // [rsp+438h] [rbp+338h]

  v47[1] = a2;
  v43 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64 **))(*(_QWORD *)*a2 + 104LL))(
         *a2,
         &GUID_cb5b47a9_6537_451f_8dd7_d305ae3dea57,
         &v43);
  if ( v4 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11A,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)(unsigned int)v4,
      Format);
  v44 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(*v43 + 120))(v43, &v44);
  if ( v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x11F,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      (const char *)(unsigned int)v5,
      Format);
  SystemTimeAsFileTime = 0;
  if ( v44 == 0x7FFFFFFFFFFFFFFFLL )
  {
    v6 = SystemTimeAsFileTime;
  }
  else
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v39 = v44;
    v40 = SystemTimeAsFileTime;
    v6 = (struct _FILETIME)(v44 - *(_QWORD *)&SystemTimeAsFileTime);
  }
  SuspendImpersonationScope::SuspendImpersonationScope((SuspendImpersonationScope *)v48);
  if ( *(__int64 *)&v6 <= 0 )
  {
    v51 = -2143326195;
    memset_0(v52, 0, 0x308u);
    v21 = StringCchCopyW(v54, 0x80u, a1);
    if ( v21 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x164,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        (const char *)(unsigned int)v21,
        Format);
    SystemTimeAsFileTime = 0;
    v22 = *v43;
    SystemTimeAsFileTime = 0;
    v23 = (*(__int64 (__fastcall **)(__int64 *, struct _FILETIME *))(v22 + 96))(v43, &SystemTimeAsFileTime);
    if ( v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x167,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        (const char *)(unsigned int)v23,
        Format);
    *(_OWORD *)v49 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v49[0]) = 0;
    if ( SystemTimeAsFileTime )
    {
      ((void (__fastcall *)(_QWORD, _QWORD))std::wstring::assign)(v49, SystemTimeAsFileTime);
      v24 = (const unsigned __int16 *)v49;
      if ( si128.m128i_i64[1] > 7uLL )
        v24 = v49[0];
    }
    else
    {
      v24 = (const unsigned __int16 *)v49;
    }
    v25 = StringCchCopyW(v53, 0xFFu, v24);
    if ( v25 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x16E,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        (const char *)(unsigned int)v25,
        Format);
    v26 = RtlPublishWnfStateData(WNF_LM_APP_LICENSE_EVENT, 0, &v51, 780, 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      0x171u,
      "PublishWnfForTrialLicense",
      (wchar_t *)L"Sent LM_E_TRIAL_LICENSE_REMINDER for %s - status = 0x%08x",
      a1,
      v26);
    if ( (v26 & 0xC0000000) == 0xC0000000 )
    {
      if ( _UnitTestWnfCallback )
        goto LABEL_36;
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        0x17Bu,
        "PublishWnfForTrialLicense",
        (wchar_t *)L"Assert (%s): %s",
        L"0",
        L"FALSE");
      MicrosoftTelemetryAssertTriggeredNoArgs();
      if ( (unsigned int)dword_1800F11D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x200000000000LL) )
      {
        v30 = v49;
        if ( si128.m128i_i64[1] > 7uLL )
          v30 = (unsigned __int16 **)v49[0];
        v42 = (const wchar_t *)v30;
        v41 = (const char *)a1;
        v47[0] = "PublishWnfForTrialLicense";
        LODWORD(v39) = 383;
        v46 = "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp";
        v40.dwLowDateTime = v26;
        v45 = L"Failed to send LM_E_TRIAL_LICENSE_REMINDER";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v27,
          (unsigned int)&byte_1800D7627,
          v28,
          v29,
          (__int64)&v45,
          (__int64)&v40,
          (__int64)&v46,
          (__int64)&v39,
          (__int64)v47,
          (__int64)&v41,
          (__int64)&v42);
      }
    }
    else if ( (unsigned int)dword_1800F11D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x200000000000LL) )
    {
      v34 = v49;
      if ( si128.m128i_i64[1] > 7uLL )
        v34 = (unsigned __int16 **)v49[0];
      v42 = (const wchar_t *)v34;
      v41 = (const char *)a1;
      LODWORD(v39) = -2143326195;
      v40.dwLowDateTime = v26;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v31,
        (unsigned int)&unk_1800D75D0,
        v32,
        v33,
        (__int64)&v40,
        (__int64)&v39,
        (__int64)&v41,
        (__int64)&v42);
    }
  }
  else
  {
    v51 = -2143326194;
    memset_0(v52, 0, 0x308u);
    v55 = (int)((double)(int)v6.dwLowDateTime / 10.0 / 1000.0 / 1000.0 / 60.0);
    v7 = StringCchCopyW(v54, 0x80u, a1);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13A,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        (const char *)(unsigned int)v7,
        Format);
    SystemTimeAsFileTime = 0;
    v8 = *v43;
    SystemTimeAsFileTime = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, struct _FILETIME *))(v8 + 96))(v43, &SystemTimeAsFileTime);
    if ( v9 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x13E,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        (const char *)(unsigned int)v9,
        Format);
    *(_OWORD *)v49 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v49[0]) = 0;
    if ( SystemTimeAsFileTime )
    {
      ((void (__fastcall *)(_QWORD, _QWORD))std::wstring::assign)(v49, SystemTimeAsFileTime);
      v10 = (const unsigned __int16 *)v49;
      if ( si128.m128i_i64[1] > 7uLL )
        v10 = v49[0];
    }
    else
    {
      v10 = (const unsigned __int16 *)v49;
    }
    v11 = StringCchCopyW(v53, 0xFFu, v10);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x146,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        (const char *)(unsigned int)v11,
        Format);
    v12 = RtlPublishWnfStateData(WNF_LM_APP_LICENSE_EVENT, 0, &v51, 780, 0);
    LogMessage(
      3u,
      "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
      0x149u,
      "PublishWnfForTrialLicense",
      (wchar_t *)L"Sent LM_E_TRIAL_LICENSE_EXPIRING_SOON for %s - status = 0x%08x",
      a1,
      v12);
    if ( (v12 & 0xC0000000) == 0xC0000000 )
    {
      if ( !_UnitTestWnfCallback )
      {
        if ( (unsigned int)dword_1800F11D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x200000000000LL) )
        {
          v16 = v49;
          if ( si128.m128i_i64[1] > 7uLL )
            v16 = (unsigned __int16 **)v49[0];
          v45 = (const wchar_t *)v16;
          v46 = (const char *)a1;
          v47[0] = "PublishWnfForTrialLicense";
          v40.dwLowDateTime = 342;
          v41 = "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp";
          LODWORD(v39) = v12;
          v42 = L"Failed to send LM_E_TRIAL_LICENSE_EXPIRING_SOON";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            v13,
            (unsigned int)&dword_1800D771C,
            v14,
            v15,
            (__int64)&v42,
            (__int64)&v39,
            (__int64)&v41,
            (__int64)&v40,
            (__int64)v47,
            (__int64)&v46,
            (__int64)&v45);
        }
        goto LABEL_47;
      }
LABEL_36:
      _UnitTestWnfCallback((struct _WNF_STATE_NAME)WNF_LM_APP_LICENSE_EVENT, 0, 0, 0, &v51, 0x30Cu);
      goto LABEL_47;
    }
    if ( (unsigned int)dword_1800F11D0 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800F11D0, 0x200000000000LL) )
    {
      v20 = v49;
      if ( si128.m128i_i64[1] > 7uLL )
        v20 = (unsigned __int16 **)v49[0];
      v42 = (const wchar_t *)v20;
      v41 = (const char *)a1;
      LODWORD(v39) = -2143326194;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v17,
        (unsigned int)&byte_1800D76CF,
        v18,
        v19,
        (__int64)&v39,
        (__int64)&v41,
        (__int64)&v42);
    }
  }
LABEL_47:
  ContentIdString::~ContentIdString((ContentIdString *)v49);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&SystemTimeAsFileTime);
  SuspendImpersonationScope::~SuspendImpersonationScope((SuspendImpersonationScope *)v48);
  v35 = v43;
  if ( v43 )
  {
    v43 = 0;
    (*(void (__fastcall **)(__int64 *))(*v35 + 16))(v35);
  }
  return Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(a2);
}

```

## disassembly

```asm
0x18008ea14  mov     [rsp-8+arg_10], rbx
0x18008ea19  push    rbp
0x18008ea1a  push    rdi
0x18008ea1b  push    r12
0x18008ea1d  push    r14
0x18008ea1f  push    r15
0x18008ea21  lea     rbp, [rsp-310h]
0x18008ea29  sub     rsp, 410h
0x18008ea30  mov     rax, cs:__security_cookie
0x18008ea37  xor     rax, rsp
0x18008ea3a  mov     [rbp+330h+var_30], rax
0x18008ea41  mov     r12, rdx
0x18008ea44  mov     rdi, rcx
0x18008ea47  mov     [rbp+330h+var_380], rdx
0x18008ea4b  mov     [rbp+330h+var_3A8], 0
0x18008ea53  mov     rcx, [rdx]
0x18008ea56  mov     rax, [rcx]
0x18008ea59  lea     r8, [rbp+330h+var_3A8]
0x18008ea5d  lea     rdx, _GUID_cb5b47a9_6537_451f_8dd7_d305ae3dea57
0x18008ea64  mov     rax, [rax+68h]
0x18008ea68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea6d  mov     rcx, [rbp+338h]; this
0x18008ea74  test    eax, eax
0x18008ea76  js      loc_18008F147
0x18008ea7c  mov     [rbp+330h+var_3A0], 0
0x18008ea84  mov     rcx, [rbp+330h+var_3A8]
0x18008ea88  mov     rax, [rcx]
0x18008ea8b  lea     rdx, [rbp+330h+var_3A0]
0x18008ea8f  mov     rax, [rax+78h]
0x18008ea93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ea98  mov     rcx, [rbp+338h]; this
0x18008ea9f  test    eax, eax
0x18008eaa1  js      loc_18008F15C
0x18008eaa7  mov     qword ptr [rsp+430h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18008eab0  cmp     dword ptr [rbp+330h+var_3A0+4], 7FFFFFFFh
0x18008eab7  jnz     short loc_18008EAC6
0x18008eab9  cmp     dword ptr [rbp+330h+var_3A0], 0FFFFFFFFh
0x18008eabd  jnz     short loc_18008EAC6
0x18008eabf  mov     rbx, qword ptr [rsp+430h+SystemTimeAsFileTime.dwLowDateTime]
0x18008eac4  jmp     short loc_18008EB02
0x18008eac6  mov     qword ptr [rsp+430h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18008eacf  lea     rcx, [rsp+430h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18008ead4  call    cs:__imp_GetSystemTimeAsFileTime
0x18008eada  mov     eax, dword ptr [rbp+330h+var_3A0+4]
0x18008eadd  mov     dword ptr [rsp+430h+var_3C8+4], eax
0x18008eae1  mov     eax, dword ptr [rbp+330h+var_3A0]
0x18008eae4  mov     dword ptr [rsp+430h+var_3C8], eax
0x18008eae8  mov     eax, [rsp+430h+SystemTimeAsFileTime.dwHighDateTime]
0x18008eaec  mov     dword ptr [rsp+430h+var_3C0+4], eax
0x18008eaf0  mov     eax, [rsp+430h+SystemTimeAsFileTime.dwLowDateTime]
0x18008eaf4  mov     dword ptr [rsp+430h+var_3C0], eax
0x18008eaf8  mov     rbx, [rsp+430h+var_3C8]
0x18008eafd  sub     rbx, [rsp+430h+var_3C0]
0x18008eb02  lea     rcx, [rbp+330h+var_378]; this
0x18008eb06  call    ??0SuspendImpersonationScope@@QEAA@XZ; SuspendImpersonationScope::SuspendImpersonationScope(void)
0x18008eb0b  nop
0x18008eb0c  xor     edx, edx; Val
0x18008eb0e  mov     r8d, 308h; Size
0x18008eb14  lea     rcx, [rbp+330h+var_33C]; void *
0x18008eb18  test    rbx, rbx
0x18008eb1b  jle     loc_18008EDED
0x18008eb21  mov     [rbp+330h+var_340], 803F700Eh
0x18008eb28  call    memset_0
0x18008eb2d  xorps   xmm1, xmm1
0x18008eb30  cvtsi2sd xmm1, rbx
0x18008eb35  divsd   xmm1, cs:__real@4024000000000000
0x18008eb3d  divsd   xmm1, cs:__real@408f400000000000
0x18008eb45  divsd   xmm1, cs:__real@408f400000000000
0x18008eb4d  divsd   xmm1, cs:__real@404e000000000000
0x18008eb55  cvttsd2si eax, xmm1
0x18008eb59  mov     [rbp+330h+var_38], eax
0x18008eb5f  mov     r8, rdi; unsigned __int16 *
0x18008eb62  mov     edx, 80h; unsigned __int64
0x18008eb67  lea     rcx, [rbp+330h+var_13A]; unsigned __int16 *
0x18008eb6e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008eb73  mov     rcx, [rbp+338h]; this
0x18008eb7a  test    eax, eax
0x18008eb7c  js      loc_18008F171
0x18008eb82  mov     qword ptr [rsp+430h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18008eb8b  mov     rcx, [rbp+330h+var_3A8]
0x18008eb8f  mov     rax, [rcx]
0x18008eb92  mov     qword ptr [rsp+430h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18008eb9b  lea     rdx, [rsp+430h+SystemTimeAsFileTime]
0x18008eba0  mov     rax, [rax+60h]
0x18008eba4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eba9  mov     rcx, [rbp+338h]; this
0x18008ebb0  test    eax, eax
0x18008ebb2  js      loc_18008F186
0x18008ebb8  xorps   xmm0, xmm0
0x18008ebbb  movups  xmmword ptr [rbp+330h+var_368], xmm0
0x18008ebbf  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18008ebc7  movdqu  [rbp+330h+var_358], xmm1
0x18008ebcc  xor     eax, eax
0x18008ebce  mov     word ptr [rbp+330h+var_368], ax
0x18008ebd2  mov     rdx, qword ptr [rsp+430h+SystemTimeAsFileTime.dwLowDateTime]
0x18008ebd7  test    rdx, rdx
0x18008ebda  jnz     short loc_18008EBE2
0x18008ebdc  lea     r8, [rbp+330h+var_368]
0x18008ebe0  jmp     short loc_18008EBF9
0x18008ebe2  lea     rcx, [rbp+330h+var_368]
0x18008ebe6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18008ebeb  lea     r8, [rbp+330h+var_368]
0x18008ebef  cmp     qword ptr [rbp+330h+var_358+8], 7
0x18008ebf4  cmova   r8, [rbp+330h+var_368]; unsigned __int16 *
0x18008ebf9  mov     edx, 0FFh; unsigned __int64
0x18008ebfe  lea     rcx, [rbp+330h+var_338]; unsigned __int16 *
0x18008ec02  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008ec07  mov     rcx, [rbp+338h]; this
0x18008ec0e  test    eax, eax
0x18008ec10  js      loc_18008F19B
0x18008ec16  mov     [rsp+430h+Format], 0
0x18008ec1f  mov     r9d, 30Ch
0x18008ec25  lea     r8, [rbp+330h+var_340]
0x18008ec29  xor     edx, edx
0x18008ec2b  mov     rcx, cs:WNF_LM_APP_LICENSE_EVENT
0x18008ec32  call    cs:__imp_RtlPublishWnfStateData
0x18008ec38  mov     r15d, eax
0x18008ec3b  mov     dword ptr [rsp+430h+var_400], eax
0x18008ec3f  mov     [rsp+430h+var_408], rdi
0x18008ec44  lea     rax, aSentLmETrialLi; "Sent LM_E_TRIAL_LICENSE_EXPIRING_SOON f"...
0x18008ec4b  mov     [rsp+430h+Format], rax; Format
0x18008ec50  lea     r14, aPublishwnffort; "PublishWnfForTrialLicense"
0x18008ec57  mov     r9, r14; char *
0x18008ec5a  mov     r8d, 149h; unsigned int
0x18008ec60  lea     rbx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008ec67  mov     rdx, rbx; char *
0x18008ec6a  mov     ecx, 3; unsigned int
0x18008ec6f  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18008ec74  mov     ecx, r15d
0x18008ec77  mov     edx, 0C0000000h
0x18008ec7c  and     ecx, edx
0x18008ec7e  cmp     ecx, edx
0x18008ec80  jnz     loc_18008ED70
0x18008ec86  mov     rax, cs:?_UnitTestWnfCallback@@3P6AJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@ZEA; long (*_UnitTestWnfCallback)(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18008ec8d  test    rax, rax
0x18008ec90  jz      short loc_18008ECBC
0x18008ec92  mov     dword ptr [rsp+430h+var_408], 30Ch
0x18008ec9a  lea     rcx, [rbp+330h+var_340]
0x18008ec9e  mov     [rsp+430h+Format], rcx
0x18008eca3  xor     r9d, r9d
0x18008eca6  xor     r8d, r8d
0x18008eca9  xor     edx, edx
0x18008ecab  mov     rcx, cs:WNF_LM_APP_LICENSE_EVENT
0x18008ecb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ecb7  jmp     loc_18008EDDE
0x18008ecbc  mov     eax, cs:dword_1800F11D0
0x18008ecc2  cmp     eax, 2
0x18008ecc5  jbe     loc_18008EDDE
0x18008eccb  mov     rdx, 200000000000h
0x18008ecd5  lea     rcx, dword_1800F11D0
0x18008ecdc  call    _tlgKeywordOn
0x18008ece1  test    al, al
0x18008ece3  jz      loc_18008EDDE
0x18008ece9  lea     rax, [rbp+330h+var_368]
0x18008eced  cmp     qword ptr [rbp+330h+var_358+8], 7
0x18008ecf2  cmova   rax, [rbp+330h+var_368]
0x18008ecf7  mov     [rbp+330h+var_398], rax
0x18008ecfb  mov     [rbp+330h+var_390], rdi
0x18008ecff  mov     [rbp+330h+var_388], r14
0x18008ed03  mov     dword ptr [rsp+430h+var_3C0], 156h
0x18008ed0b  mov     [rsp+430h+var_3B8], rbx
0x18008ed10  mov     dword ptr [rsp+430h+var_3C8], r15d
0x18008ed15  lea     rax, aFailedToSendLm_1; "Failed to send LM_E_TRIAL_LICENSE_EXPIR"...
0x18008ed1c  mov     [rbp+330h+var_3B0], rax
0x18008ed20  lea     rax, [rbp+330h+var_398]
0x18008ed24  mov     [rsp+430h+var_3E0], rax
0x18008ed29  lea     rax, [rbp+330h+var_390]
0x18008ed2d  mov     [rsp+430h+var_3E8], rax
0x18008ed32  lea     rax, [rbp+330h+var_388]
0x18008ed36  mov     [rsp+430h+var_3F0], rax
0x18008ed3b  lea     rax, [rsp+430h+var_3C0]
0x18008ed40  mov     [rsp+430h+var_3F8], rax
0x18008ed45  lea     rax, [rsp+430h+var_3B8]
0x18008ed4a  mov     [rsp+430h+var_400], rax
0x18008ed4f  lea     rax, [rsp+430h+var_3C8]
0x18008ed54  mov     [rsp+430h+var_408], rax
0x18008ed59  lea     rax, [rbp+330h+var_3B0]
0x18008ed5d  mov     [rsp+430h+Format], rax
0x18008ed62  lea     rdx, dword_1800D771C
0x18008ed69  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@4533@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18008ed6e  jmp     short loc_18008EDDE
0x18008ed70  mov     eax, cs:dword_1800F11D0
0x18008ed76  cmp     eax, 4
0x18008ed79  jbe     short loc_18008EDDE
0x18008ed7b  mov     rdx, 200000000000h
0x18008ed85  lea     rcx, dword_1800F11D0
0x18008ed8c  call    _tlgKeywordOn
0x18008ed91  test    al, al
0x18008ed93  jz      short loc_18008EDDE
0x18008ed95  lea     rax, [rbp+330h+var_368]
0x18008ed99  cmp     qword ptr [rbp+330h+var_358+8], 7
0x18008ed9e  cmova   rax, [rbp+330h+var_368]
0x18008eda3  mov     [rbp+330h+var_3B0], rax
0x18008eda7  mov     [rsp+430h+var_3B8], rdi
0x18008edac  mov     dword ptr [rsp+430h+var_3C8], 803F700Eh
0x18008edb4  lea     rax, [rbp+330h+var_3B0]
0x18008edb8  mov     [rsp+430h+var_400], rax
0x18008edbd  lea     rax, [rsp+430h+var_3B8]
0x18008edc2  mov     [rsp+430h+var_408], rax
0x18008edc7  lea     rax, [rsp+430h+var_3C8]
0x18008edcc  mov     [rsp+430h+Format], rax
0x18008edd1  lea     rdx, byte_1800D76CF
0x18008edd8  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18008eddd  nop
0x18008edde  lea     rcx, [rbp+330h+var_368]; this
0x18008ede2  call    ??1ContentIdString@@QEAA@XZ; ContentIdString::~ContentIdString(void)
0x18008ede7  nop
0x18008ede8  jmp     loc_18008F0D0
0x18008eded  mov     [rbp+330h+var_340], 803F700Dh
0x18008edf4  call    memset_0
0x18008edf9  mov     r8, rdi; unsigned __int16 *
0x18008edfc  mov     edx, 80h; unsigned __int64
0x18008ee01  lea     rcx, [rbp+330h+var_13A]; unsigned __int16 *
0x18008ee08  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008ee0d  mov     rcx, [rbp+338h]; this
0x18008ee14  test    eax, eax
0x18008ee16  js      loc_18008F1B0
0x18008ee1c  mov     qword ptr [rsp+430h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18008ee25  mov     rcx, [rbp+330h+var_3A8]
0x18008ee29  mov     rax, [rcx]
0x18008ee2c  mov     qword ptr [rsp+430h+SystemTimeAsFileTime.dwLowDateTime], 0
0x18008ee35  lea     rdx, [rsp+430h+SystemTimeAsFileTime]
0x18008ee3a  mov     rax, [rax+60h]
0x18008ee3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ee43  mov     rcx, [rbp+338h]; this
0x18008ee4a  test    eax, eax
0x18008ee4c  js      loc_18008F1C5
0x18008ee52  xorps   xmm0, xmm0
0x18008ee55  movups  xmmword ptr [rbp+330h+var_368], xmm0
0x18008ee59  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18008ee61  movdqu  [rbp+330h+var_358], xmm1
0x18008ee66  xor     eax, eax
0x18008ee68  mov     word ptr [rbp+330h+var_368], ax
0x18008ee6c  mov     rdx, qword ptr [rsp+430h+SystemTimeAsFileTime.dwLowDateTime]
0x18008ee71  test    rdx, rdx
0x18008ee74  jnz     short loc_18008EE7C
0x18008ee76  lea     r8, [rbp+330h+var_368]
0x18008ee7a  jmp     short loc_18008EE93
0x18008ee7c  lea     rcx, [rbp+330h+var_368]
0x18008ee80  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18008ee85  lea     r8, [rbp+330h+var_368]
0x18008ee89  cmp     qword ptr [rbp+330h+var_358+8], 7
0x18008ee8e  cmova   r8, [rbp+330h+var_368]; unsigned __int16 *
0x18008ee93  mov     edx, 0FFh; unsigned __int64
0x18008ee98  lea     rcx, [rbp+330h+var_338]; unsigned __int16 *
0x18008ee9c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18008eea1  mov     rcx, [rbp+338h]; this
0x18008eea8  test    eax, eax
0x18008eeaa  js      loc_18008F132
0x18008eeb0  mov     [rsp+430h+Format], 0
0x18008eeb9  mov     r9d, 30Ch
0x18008eebf  lea     r8, [rbp+330h+var_340]
0x18008eec3  xor     edx, edx
0x18008eec5  mov     rcx, cs:WNF_LM_APP_LICENSE_EVENT
0x18008eecc  call    cs:__imp_RtlPublishWnfStateData
0x18008eed2  mov     r15d, eax
0x18008eed5  mov     dword ptr [rsp+430h+var_400], eax
0x18008eed9  mov     [rsp+430h+var_408], rdi
0x18008eede  lea     rax, aSentLmETrialLi_0; "Sent LM_E_TRIAL_LICENSE_REMINDER for %s"...
0x18008eee5  mov     [rsp+430h+Format], rax; Format
0x18008eeea  lea     r14, aPublishwnffort; "PublishWnfForTrialLicense"
0x18008eef1  mov     r9, r14; char *
0x18008eef4  mov     r8d, 171h; unsigned int
0x18008eefa  lea     rbx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008ef01  mov     rdx, rbx; char *
0x18008ef04  mov     ecx, 3; unsigned int
0x18008ef09  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18008ef0e  mov     ecx, r15d
0x18008ef11  mov     edx, 0C0000000h
0x18008ef16  and     ecx, edx
0x18008ef18  cmp     ecx, edx
0x18008ef1a  jnz     loc_18008F049
0x18008ef20  mov     rax, cs:?_UnitTestWnfCallback@@3P6AJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@ZEA; long (*_UnitTestWnfCallback)(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x18008ef27  test    rax, rax
0x18008ef2a  jz      short loc_18008EF56
0x18008ef2c  mov     dword ptr [rsp+430h+var_408], 30Ch
0x18008ef34  lea     rcx, [rbp+330h+var_340]
0x18008ef38  mov     [rsp+430h+Format], rcx
0x18008ef3d  xor     r9d, r9d
0x18008ef40  xor     r8d, r8d
0x18008ef43  xor     edx, edx
0x18008ef45  mov     rcx, cs:WNF_LM_APP_LICENSE_EVENT
0x18008ef4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008ef51  jmp     loc_18008F0C6
0x18008ef56  lea     rax, aFalse_1; "FALSE"
0x18008ef5d  mov     [rsp+430h+var_400], rax
0x18008ef62  lea     rax, a0; "0"
0x18008ef69  mov     [rsp+430h+var_408], rax
0x18008ef6e  lea     rax, aAssertSS; "Assert (%s): %s"
0x18008ef75  mov     [rsp+430h+Format], rax; Format
0x18008ef7a  mov     r9, r14; char *
0x18008ef7d  mov     r8d, 17Bh; unsigned int
0x18008ef83  mov     rdx, rbx; char *
0x18008ef86  mov     ecx, 1; unsigned int
0x18008ef8b  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18008ef90  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008ef95  mov     eax, cs:dword_1800F11D0
0x18008ef9b  cmp     eax, 2
0x18008ef9e  jbe     loc_18008F0C6
0x18008efa4  mov     rdx, 200000000000h
  ... truncated ...
```
