# OSDeploymentHelper::CDeploymentSessionWrapper::CreateDeploymentSessionFromLibrary(wchar_t const *,wchar_t const *,_GUID const &,ulong,tagOptionalSessionInfo6 &,void *,IDeploymentSession * *)

- ea: `0x180053aec`
- end: `0x1800542ba`
- name: `?CreateDeploymentSessionFromLibrary@CDeploymentSessionWrapper@OSDeploymentHelper@@QEAAJPEB_W0AEBU_GUID@@KAEAUtagOptionalSessionInfo6@@PEAXPEAPEAUIDeploymentSession@@@Z`
- size: `1998`
- prototype: `__int64 __fastcall(OSDeploymentHelper::CDeploymentSessionWrapper *this, const wchar_t *, const wchar_t *, const struct _GUID *, unsigned int, struct tagOptionalSessionInfo6 *, void *, struct IDeploymentSession **)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1800530e4`

## callees

- `0x180003180`
- `0x1800110fc`
- `0x180053aec`
- `0x180054ab8`
- `0x180054b38`
- `0x18005e764`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180053b65`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180053b65`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180053b77`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180053b77`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180053be8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180053c1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180053fd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180053be8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180053c1b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180053fd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053b86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053fe6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053b86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053fe6`

## string_xrefs

- `0x180053ba9`: `Failed to load the service stack dll file '%ws'`
- `0x180053bde`: `CreateDeploymentSessionEx`
- `0x180053fa1`: `CreateDeploymentSessionEx`
- `0x180053df3`: `CreateDeploymentSessionEx: %ws with OptionalSessionInfo version 5.`
- `0x180054004`: `CreateDeploymentSession`
- `0x18005418d`: `CreateDeploymentSession`
- `0x180054276`: `CreateDeploymentSession`
- `0x180053fcd`: `CreateDeploymentSession`

## pseudocode

```c
__int64 __fastcall OSDeploymentHelper::CDeploymentSessionWrapper::CreateDeploymentSessionFromLibrary(
        OSDeploymentHelper::CDeploymentSessionWrapper *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const struct _GUID *a4,
        unsigned int a5,
        struct tagOptionalSessionInfo6 *a6,
        void *a7,
        struct IDeploymentSession **a8)
{
  signed int v12; // ebx
  __int64 v13; // rdx
  HMODULE Library; // rdi
  HMODULE v15; // rcx
  signed int LastError; // eax
  FARPROC v17; // rax
  int v18; // eax
  int *v19; // rax
  __int64 v20; // r8
  int v21; // ecx
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rax
  struct _GUID v25; // xmm0
  __int64 v26; // r9
  __int64 v27; // rdx
  unsigned int v28; // ecx
  int v29; // eax
  int *v30; // rax
  __int64 v31; // r8
  int v32; // ecx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rcx
  FARPROC ProcAddress; // r15
  signed int v37; // eax
  unsigned int v38; // ecx
  int v39; // eax
  unsigned __int64 v40; // r9
  __int64 v41; // rdx
  int *v42; // rax
  __int64 v43; // r9
  int v44; // edx
  __int64 v45; // rax
  __int64 v46; // r9
  __int64 v47; // rax
  struct IDeploymentSession *v48; // rax
  struct IDeploymentSession *v49; // rcx
  void *v51; // [rsp+20h] [rbp-A1h]
  int v52; // [rsp+20h] [rbp-A1h]
  void *v53; // [rsp+20h] [rbp-A1h]
  int v54; // [rsp+20h] [rbp-A1h]
  void *v55; // [rsp+20h] [rbp-A1h]
  int v56; // [rsp+20h] [rbp-A1h]
  void *v57; // [rsp+20h] [rbp-A1h]
  void *v58; // [rsp+20h] [rbp-A1h]
  struct SessionDataUtil::WUDeploymentSessionInfoWrapper *v59[2]; // [rsp+40h] [rbp-81h] BYREF
  struct _GUID v60; // [rsp+50h] [rbp-71h] BYREF
  struct _GUID v61; // [rsp+60h] [rbp-61h] BYREF
  struct IDeploymentSession **v62; // [rsp+70h] [rbp-51h]
  __int128 v63; // [rsp+78h] [rbp-49h] BYREF
  __int128 v64; // [rsp+88h] [rbp-39h]
  __int128 v65; // [rsp+98h] [rbp-29h]
  struct IDeploymentSession *v66; // [rsp+A8h] [rbp-19h] BYREF
  int v67; // [rsp+B0h] [rbp-11h] BYREF
  unsigned int v68; // [rsp+B4h] [rbp-Dh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  *(_QWORD *)&v60.Data1 = a4;
  v62 = a8;
  if ( !a8 )
  {
    v12 = -2147467261;
    v13 = 369;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
      (const char *)(unsigned int)v12,
      (int)v51);
    return (unsigned int)v12;
  }
  Library = LoadLibraryExW(a2, 0, 0);
  v15 = (HMODULE)*((_QWORD *)this + 9);
  if ( v15 )
    FreeLibrary(v15);
  *((_QWORD *)this + 9) = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v12 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v12 = LastError;
    if ( v12 >= 0 )
      v12 = -2147418113;
    LODWORD(v51) = v12;
    WUTrace(0, 0, 4096, 1, v51, L"Failed to load the service stack dll file '%ws'", a2);
    v13 = 376;
    goto LABEL_3;
  }
  v66 = 0;
  *(_QWORD *)&v61.Data1 = GetProcAddress(Library, "CreateDeploymentSessionEx");
  if ( !*(_QWORD *)&v61.Data1 )
  {
    ProcAddress = GetProcAddress(*((HMODULE *)this + 9), "CreateDeploymentSession");
    if ( !ProcAddress )
    {
      v37 = GetLastError();
      v12 = (unsigned __int16)v37 | 0x80070000;
      if ( v37 <= 0 )
        v12 = v37;
      if ( v12 >= 0 )
        v12 = -2147418113;
      LODWORD(v51) = v12;
      WUTrace(0, 0, 4096, 1, v51, L"CreateDeploymentSession");
      v27 = 516;
      goto LABEL_111;
    }
    v63 = 0;
    v64 = 0;
    v65 = 0;
    if ( a7 )
    {
      v63 = *(_OWORD *)a6;
      v64 = *((_OWORD *)a6 + 1);
      v65 = *((_OWORD *)a6 + 2);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl'::`2'::impl) )
    {
      v61 = *a4;
      v12 = ((__int64 (__fastcall *)(__int64, const wchar_t *, struct _GUID *, __int128 *, struct IDeploymentSession **))ProcAddress)(
              1,
              a3,
              &v61,
              &v63,
              &v66);
      if ( v12 < 0 )
      {
        LODWORD(v58) = v12;
        WUTrace(0, 0, 4096, 1, v58, L"CreateDeploymentSession");
        v27 = 566;
        goto LABEL_111;
      }
      goto LABEL_105;
    }
    v59[0] = 0;
    WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v59);
    v61 = *a4;
    v39 = SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(v38, a3, &v61, 5u, &v63, v59);
    v12 = v39;
    if ( v39 < 0 )
    {
      v40 = (unsigned int)v39;
      v41 = 540;
      goto LABEL_102;
    }
    if ( v66 )
    {
      (*(void (__fastcall **)(struct IDeploymentSession *))(*(_QWORD *)v66 + 16LL))(v66);
      v66 = 0;
    }
    v42 = (int *)*((_QWORD *)v59[0] + 4);
    if ( v42 )
    {
      v43 = *((_QWORD *)v42 + 6);
      if ( v43 )
      {
        v44 = *v42;
        if ( *v42 == 1 )
        {
          v45 = *((_QWORD *)v42 + 1);
LABEL_87:
          v46 = *(_QWORD *)(v45 + 48);
LABEL_100:
          v61 = (struct _GUID)*((_OWORD *)v59[0] + 1);
          v12 = ((__int64 (__fastcall *)(_QWORD, _QWORD, struct _GUID *, __int64, struct IDeploymentSession **))ProcAddress)(
                  *(unsigned int *)v59[0],
                  *((_QWORD *)v59[0] + 1),
                  &v61,
                  v46,
                  &v66);
          if ( v12 >= 0 )
          {
            WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v59);
            goto LABEL_105;
          }
          LODWORD(v57) = v12;
          WUTrace(0, 0, 4096, 1, v57, L"CreateDeploymentSession");
          v40 = (unsigned int)v12;
          v41 = 552;
LABEL_102:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v41,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
            (const char *)v40,
            v56);
          goto LABEL_103;
        }
        switch ( v44 )
        {
          case 2:
            v47 = *((_QWORD *)v42 + 2);
LABEL_90:
            v46 = *(_QWORD *)(v47 + 16);
            goto LABEL_100;
          case 3:
            v47 = *((_QWORD *)v42 + 3);
            goto LABEL_90;
          case 4:
            v47 = *((_QWORD *)v42 + 4);
            goto LABEL_90;
          case 5:
            v45 = *((_QWORD *)v42 + 5);
            goto LABEL_87;
          case 6:
            v46 = *(_QWORD *)(v43 + 16);
            goto LABEL_100;
        }
      }
    }
    v46 = 0;
    goto LABEL_100;
  }
  if ( a5 < 6 )
    goto LABEL_43;
  v17 = GetProcAddress(*((HMODULE *)this + 9), "GetSupportedSessionInitializationOptions");
  if ( !v17
    || (v67 = 0, v68 = 5, ((int (__fastcall *)(int *, unsigned int *))v17)(&v67, &v68) < 0)
    || (v67 & 1) == 0
    || v68 < 6 )
  {
    if ( (*((_BYTE *)a6 + 104) & 1) != 0 )
    {
      v12 = -2145116123;
      v27 = 457;
LABEL_111:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v27,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
        (const char *)(unsigned int)v12,
        (int)v51);
      goto LABEL_112;
    }
LABEL_43:
    WUTrace(0, 0, 4096, 4, 0, L"CreateDeploymentSessionEx: %ws with OptionalSessionInfo version 5.", L"Fallbacking");
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl'::`2'::impl) )
    {
      v25 = *(struct _GUID *)*(_QWORD *)&v60.Data1;
      v53 = a7;
      v26 = 5;
      goto LABEL_67;
    }
    v59[0] = 0;
    WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v59);
    v60 = *(struct _GUID *)*(_QWORD *)&v60.Data1;
    v29 = SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(v28, a3, &v60, 5u, a7, v59);
    v12 = v29;
    if ( v29 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DE,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
        (const char *)(unsigned int)v29,
        v54);
      goto LABEL_103;
    }
    if ( v66 )
    {
      (*(void (__fastcall **)(struct IDeploymentSession *))(*(_QWORD *)v66 + 16LL))(v66);
      v66 = 0;
    }
    v30 = (int *)*((_QWORD *)v59[0] + 4);
    if ( v30 )
    {
      v31 = *((_QWORD *)v30 + 6);
      if ( v31 )
      {
        v32 = *v30;
        if ( *v30 == 1 )
        {
          v33 = *((_QWORD *)v30 + 1);
LABEL_52:
          v23 = *(_QWORD *)(v33 + 48);
          goto LABEL_65;
        }
        switch ( v32 )
        {
          case 2:
            v34 = *((_QWORD *)v30 + 2);
LABEL_55:
            v23 = *(_QWORD *)(v34 + 16);
            goto LABEL_65;
          case 3:
            v34 = *((_QWORD *)v30 + 3);
            goto LABEL_55;
          case 4:
            v34 = *((_QWORD *)v30 + 4);
            goto LABEL_55;
          case 5:
            v33 = *((_QWORD *)v30 + 5);
            goto LABEL_52;
          case 6:
            v23 = *(_QWORD *)(v31 + 16);
            goto LABEL_65;
        }
      }
    }
    v23 = 0;
    goto LABEL_65;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl'::`2'::impl) )
  {
    v25 = *(struct _GUID *)*(_QWORD *)&v60.Data1;
    v53 = (void *)((unsigned __int64)a6 & -(__int64)(a7 != 0));
    v26 = 6;
LABEL_67:
    v60 = v25;
    v12 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, struct _GUID *, __int64, void *, struct IDeploymentSession **))&v61.Data1)(
            1,
            a3,
            &v60,
            v26,
            v53,
            &v66);
LABEL_68:
    if ( v12 < 0 )
    {
      LODWORD(v55) = v12;
      WUTrace(0, 0, 4096, 1, v55, L"CreateDeploymentSessionEx");
      v27 = 502;
      goto LABEL_111;
    }
LABEL_105:
    v48 = v66;
    v49 = 0;
    v66 = 0;
    *v62 = v48;
    v12 = 0;
    goto LABEL_106;
  }
  v59[0] = 0;
  WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v59);
  v60 = *(struct _GUID *)*(_QWORD *)&v60.Data1;
  v18 = SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(
          (unsigned int)v59,
          a3,
          &v60,
          6u,
          (const void *)((unsigned __int64)a6 & -(__int64)(a7 != 0)),
          v59);
  v12 = v18;
  if ( v18 >= 0 )
  {
    if ( v66 )
    {
      (*(void (__fastcall **)(struct IDeploymentSession *))(*(_QWORD *)v66 + 16LL))(v66);
      v66 = 0;
    }
    v19 = (int *)*((_QWORD *)v59[0] + 4);
    if ( v19 )
    {
      v20 = *((_QWORD *)v19 + 6);
      if ( v20 )
      {
        v21 = *v19;
        if ( *v19 == 1 )
        {
          v22 = *((_QWORD *)v19 + 1);
LABEL_27:
          v23 = *(_QWORD *)(v22 + 48);
LABEL_65:
          v35 = *(unsigned int *)v59[0];
          v60 = (struct _GUID)*((_OWORD *)v59[0] + 1);
          v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct _GUID *, _QWORD, __int64, struct IDeploymentSession **))&v61.Data1)(
                  v35,
                  *((_QWORD *)v59[0] + 1),
                  &v60,
                  (unsigned int)v35,
                  v23,
                  &v66);
          WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v59);
          goto LABEL_68;
        }
        switch ( v21 )
        {
          case 2:
            v24 = *((_QWORD *)v19 + 2);
LABEL_30:
            v23 = *(_QWORD *)(v24 + 16);
            goto LABEL_65;
          case 3:
            v24 = *((_QWORD *)v19 + 3);
            goto LABEL_30;
          case 4:
            v24 = *((_QWORD *)v19 + 4);
            goto LABEL_30;
          case 5:
            v22 = *((_QWORD *)v19 + 5);
            goto LABEL_27;
          case 6:
            v23 = *(_QWORD *)(v20 + 16);
            goto LABEL_65;
        }
      }
    }
    v23 = 0;
    goto LABEL_65;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1A8,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
    (const char *)(unsigned int)v18,
    v52);
LABEL_103:
  WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v59);
LABEL_112:
  v49 = v66;
LABEL_106:
  if ( v49 )
    (*(void (__fastcall **)(struct IDeploymentSession *))(*(_QWORD *)v49 + 16LL))(v49);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180053aec  push    rbp
0x180053aee  push    rbx
0x180053aef  push    rsi
0x180053af0  push    rdi
0x180053af1  push    r12
0x180053af3  push    r13
0x180053af5  push    r14
0x180053af7  push    r15
0x180053af9  lea     rbp, [rsp-7]
0x180053afe  sub     rsp, 0C8h
0x180053b05  mov     rax, cs:__security_cookie
0x180053b0c  xor     rax, rsp
0x180053b0f  mov     [rbp+3Fh+var_48], rax
0x180053b13  mov     rsi, r9
0x180053b16  mov     qword ptr [rbp+3Fh+var_B0.Data1], r9
0x180053b1a  mov     r13, r8
0x180053b1d  mov     r14, rdx
0x180053b20  mov     r15, rcx
0x180053b23  mov     rbx, [rbp+3Fh+arg_28]
0x180053b27  mov     r12, [rbp+3Fh+arg_30]
0x180053b2b  mov     rax, [rbp+3Fh+arg_38]
0x180053b32  mov     [rbp+3Fh+var_90], rax
0x180053b36  test    rax, rax
0x180053b39  jnz     short loc_180053B5D
0x180053b3b  mov     ebx, 80004003h
0x180053b40  mov     edx, 171h; void *
0x180053b45  lea     r8, aCW1SSrcClientE_10; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180053b4c  mov     r9d, ebx; char *
0x180053b4f  mov     rcx, [rbp+47h]; this
0x180053b53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053b58  jmp     loc_180054206
0x180053b5d  xor     r8d, r8d; dwFlags
0x180053b60  xor     edx, edx; hFile
0x180053b62  mov     rcx, r14; lpLibFileName
0x180053b65  call    cs:__imp_LoadLibraryExW
0x180053b6b  mov     rdi, rax
0x180053b6e  mov     rcx, [r15+48h]; hLibModule
0x180053b72  test    rcx, rcx
0x180053b75  jz      short loc_180053B7D
0x180053b77  call    cs:__imp_FreeLibrary
0x180053b7d  mov     [r15+48h], rdi
0x180053b81  test    rdi, rdi
0x180053b84  jnz     short loc_180053BD6
0x180053b86  call    cs:__imp_GetLastError
0x180053b8c  movzx   ebx, ax
0x180053b8f  or      ebx, 80070000h
0x180053b95  test    eax, eax
0x180053b97  cmovle  ebx, eax
0x180053b9a  mov     eax, 8000FFFFh
0x180053b9f  test    ebx, ebx
0x180053ba1  cmovns  ebx, eax
0x180053ba4  mov     [rsp+100h+var_D0], r14
0x180053ba9  lea     rax, aFailedToLoadTh; "Failed to load the service stack dll fi"...
0x180053bb0  mov     [rsp+100h+var_D8], rax
0x180053bb5  mov     dword ptr [rsp+100h+var_E0], ebx
0x180053bb9  xor     edx, edx
0x180053bbb  xor     ecx, ecx
0x180053bbd  lea     r9d, [rdi+1]
0x180053bc1  mov     r8d, 1000h
0x180053bc7  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180053bcc  mov     edx, 178h
0x180053bd1  jmp     loc_180053B45
0x180053bd6  mov     [rbp+3Fh+var_58], 0
0x180053bde  lea     rdx, aCreatedeployme_0; "CreateDeploymentSessionEx"
0x180053be5  mov     rcx, rdi; hModule
0x180053be8  call    cs:__imp_GetProcAddress
0x180053bee  mov     qword ptr [rbp+3Fh+var_A0.Data1], rax
0x180053bf2  test    rax, rax
0x180053bf5  jz      loc_180053FCD
0x180053bfb  mov     edi, 1
0x180053c00  lea     esi, [rdi+5]
0x180053c03  lea     r14d, [rdi+4]
0x180053c07  cmp     [rbp+3Fh+arg_20], esi
0x180053c0a  jb      loc_180053DE7
0x180053c10  lea     rdx, aGetsupportedse; "GetSupportedSessionInitializationOption"...
0x180053c17  mov     rcx, [r15+48h]; hModule
0x180053c1b  call    cs:__imp_GetProcAddress
0x180053c21  test    rax, rax
0x180053c24  jz      loc_180053DD2
0x180053c2a  mov     [rbp+3Fh+var_50], 0
0x180053c31  mov     [rbp+3Fh+var_4C], r14d
0x180053c35  lea     rdx, [rbp+3Fh+var_4C]
0x180053c39  lea     rcx, [rbp+3Fh+var_50]
0x180053c3d  call    _guard_dispatch_icall
0x180053c42  test    eax, eax
0x180053c44  js      loc_180053DD2
0x180053c4a  test    byte ptr [rbp+3Fh+var_50], dil
0x180053c4e  jz      loc_180053DD2
0x180053c54  cmp     [rbp+3Fh+var_4C], esi
0x180053c57  jb      loc_180053DD2
0x180053c5d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl(void)'::`2'::impl
0x180053c64  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(void)
0x180053c69  test    al, al
0x180053c6b  jz      loc_180053D8F
0x180053c71  mov     [rsp+100h+var_C0], 0
0x180053c7a  lea     rcx, [rsp+100h+var_C0]
0x180053c7f  call    ?InternalRelease@?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(void)
0x180053c84  mov     rax, qword ptr [rbp+3Fh+var_B0.Data1]
0x180053c88  movaps  xmm0, xmmword ptr [rax]
0x180053c8b  movdqa  xmmword ptr [rbp+3Fh+var_B0.Data1], xmm0
0x180053c90  neg     r12
0x180053c93  sbb     rax, rax
0x180053c96  and     rax, rbx
0x180053c99  lea     rcx, [rsp+100h+var_C0]; unsigned int
0x180053c9e  mov     [rsp+100h+var_D8], rcx; struct SessionDataUtil::WUDeploymentSessionInfoWrapper **
0x180053ca3  mov     [rsp+100h+var_E0], rax; int
0x180053ca8  mov     r9d, esi; unsigned int
0x180053cab  lea     r8, [rbp+3Fh+var_B0]; struct _GUID
0x180053caf  mov     rdx, r13; wchar_t *
0x180053cb2  call    ?CreateInstance@WUDeploymentSessionInfoWrapper@SessionDataUtil@@SAJKPEB_WU_GUID@@KPEBXPEAPEAV12@@Z; SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(ulong,wchar_t const *,_GUID,ulong,void const *,SessionDataUtil::WUDeploymentSessionInfoWrapper * *)
0x180053cb7  mov     ebx, eax
0x180053cb9  test    eax, eax
0x180053cbb  jns     short loc_180053CDB
0x180053cbd  mov     rcx, [rbp+47h]; this
0x180053cc1  mov     r9d, eax; char *
0x180053cc4  lea     r8, aCW1SSrcClientE_10; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180053ccb  mov     edx, 1A8h; void *
0x180053cd0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053cd5  nop
0x180053cd6  jmp     loc_1800541C8
0x180053cdb  mov     rcx, [rbp+3Fh+var_58]
0x180053cdf  test    rcx, rcx
0x180053ce2  jz      short loc_180053CF8
0x180053ce4  mov     rax, [rcx]
0x180053ce7  mov     rax, [rax+10h]
0x180053ceb  call    _guard_dispatch_icall
0x180053cf0  mov     [rbp+3Fh+var_58], 0
0x180053cf8  mov     rdx, [rsp+100h+var_C0]
0x180053cfd  mov     rax, [rdx+20h]
0x180053d01  test    rax, rax
0x180053d04  jz      short loc_180053D59
0x180053d06  mov     r8, [rax+30h]
0x180053d0a  test    r8, r8
0x180053d0d  jz      short loc_180053D59
0x180053d0f  mov     ecx, [rax]
0x180053d11  cmp     ecx, edi
0x180053d13  jnz     short loc_180053D1F
0x180053d15  mov     rax, [rax+8]
0x180053d19  mov     rax, [rax+30h]
0x180053d1d  jmp     short loc_180053D5B
0x180053d1f  cmp     ecx, 2
0x180053d22  jnz     short loc_180053D2E
0x180053d24  mov     rax, [rax+10h]
0x180053d28  mov     rax, [rax+10h]
0x180053d2c  jmp     short loc_180053D5B
0x180053d2e  cmp     ecx, 3
0x180053d31  jnz     short loc_180053D39
0x180053d33  mov     rax, [rax+18h]
0x180053d37  jmp     short loc_180053D28
0x180053d39  cmp     ecx, 4
0x180053d3c  jnz     short loc_180053D44
0x180053d3e  mov     rax, [rax+20h]
0x180053d42  jmp     short loc_180053D28
0x180053d44  cmp     ecx, r14d
0x180053d47  jnz     short loc_180053D4F
0x180053d49  mov     rax, [rax+28h]
0x180053d4d  jmp     short loc_180053D19
0x180053d4f  cmp     ecx, esi
0x180053d51  jnz     short loc_180053D59
0x180053d53  mov     rax, [r8+10h]
0x180053d57  jmp     short loc_180053D5B
0x180053d59  xor     eax, eax
0x180053d5b  mov     ecx, [rdx]
0x180053d5d  movups  xmm0, xmmword ptr [rdx+10h]
0x180053d61  movdqu  xmmword ptr [rbp+3Fh+var_B0.Data1], xmm0
0x180053d66  lea     r8, [rbp+3Fh+var_58]
0x180053d6a  mov     [rsp+100h+var_D8], r8
0x180053d6f  mov     [rsp+100h+var_E0], rax
0x180053d74  mov     r9d, ecx
0x180053d77  lea     r8, [rbp+3Fh+var_B0]
0x180053d7b  mov     rdx, [rdx+8]
0x180053d7f  mov     rax, qword ptr [rbp+3Fh+var_A0.Data1]
0x180053d83  call    _guard_dispatch_icall
0x180053d88  mov     ebx, eax
0x180053d8a  jmp     loc_180053F3F
0x180053d8f  mov     rcx, [rbp+3Fh+var_58]
0x180053d93  test    rcx, rcx
0x180053d96  jz      short loc_180053DAC
0x180053d98  mov     rax, [rcx]
0x180053d9b  mov     rax, [rax+10h]
0x180053d9f  call    _guard_dispatch_icall
0x180053da4  mov     [rbp+3Fh+var_58], 0
0x180053dac  mov     rax, qword ptr [rbp+3Fh+var_B0.Data1]
0x180053db0  movaps  xmm0, xmmword ptr [rax]
0x180053db3  neg     r12
0x180053db6  sbb     rax, rax
0x180053db9  and     rax, rbx
0x180053dbc  lea     rcx, [rbp+3Fh+var_58]
0x180053dc0  mov     [rsp+100h+var_D8], rcx
0x180053dc5  mov     [rsp+100h+var_E0], rax
0x180053dca  mov     r9d, esi
0x180053dcd  jmp     loc_180053F80
0x180053dd2  test    [rbx+68h], dil
0x180053dd6  jz      short loc_180053DE7
0x180053dd8  mov     ebx, 80242025h
0x180053ddd  mov     edx, 1C9h
0x180053de2  jmp     loc_18005429D
0x180053de7  lea     rax, aFallbacking; "Fallbacking"
0x180053dee  mov     [rsp+100h+var_D0], rax
0x180053df3  lea     rax, aCreatedeployme; "CreateDeploymentSessionEx: %ws with Opt"...
0x180053dfa  mov     [rsp+100h+var_D8], rax
0x180053dff  mov     [rsp+100h+var_E0], 0
0x180053e08  xor     edx, edx
0x180053e0a  xor     ecx, ecx
0x180053e0c  lea     r9d, [rdx+4]
0x180053e10  mov     r8d, 1000h
0x180053e16  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180053e1b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl(void)'::`2'::impl
0x180053e22  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(void)
0x180053e27  test    al, al
0x180053e29  jz      loc_180053F4B
0x180053e2f  mov     [rsp+100h+var_C0], 0
0x180053e38  lea     rcx, [rsp+100h+var_C0]
0x180053e3d  call    ?InternalRelease@?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(void)
0x180053e42  mov     rax, qword ptr [rbp+3Fh+var_B0.Data1]
0x180053e46  movaps  xmm0, xmmword ptr [rax]
0x180053e49  movdqa  xmmword ptr [rbp+3Fh+var_B0.Data1], xmm0
0x180053e4e  lea     rax, [rsp+100h+var_C0]
0x180053e53  mov     [rsp+100h+var_D8], rax; struct SessionDataUtil::WUDeploymentSessionInfoWrapper **
0x180053e58  mov     [rsp+100h+var_E0], r12; int
0x180053e5d  mov     r9d, r14d; unsigned int
0x180053e60  lea     r8, [rbp+3Fh+var_B0]; struct _GUID
0x180053e64  mov     rdx, r13; wchar_t *
0x180053e67  call    ?CreateInstance@WUDeploymentSessionInfoWrapper@SessionDataUtil@@SAJKPEB_WU_GUID@@KPEBXPEAPEAV12@@Z; SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(ulong,wchar_t const *,_GUID,ulong,void const *,SessionDataUtil::WUDeploymentSessionInfoWrapper * *)
0x180053e6c  mov     ebx, eax
0x180053e6e  test    eax, eax
0x180053e70  jns     short loc_180053E90
0x180053e72  mov     rcx, [rbp+47h]; this
0x180053e76  mov     r9d, eax; char *
0x180053e79  lea     r8, aCW1SSrcClientE_10; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x180053e80  mov     edx, 1DEh; void *
0x180053e85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053e8a  nop
0x180053e8b  jmp     loc_1800541C8
0x180053e90  mov     rcx, [rbp+3Fh+var_58]
0x180053e94  test    rcx, rcx
0x180053e97  jz      short loc_180053EAD
0x180053e99  mov     rax, [rcx]
0x180053e9c  mov     rax, [rax+10h]
0x180053ea0  call    _guard_dispatch_icall
0x180053ea5  mov     [rbp+3Fh+var_58], 0
0x180053ead  mov     rdx, [rsp+100h+var_C0]
0x180053eb2  mov     rax, [rdx+20h]
0x180053eb6  test    rax, rax
0x180053eb9  jz      short loc_180053F0E
0x180053ebb  mov     r8, [rax+30h]
0x180053ebf  test    r8, r8
0x180053ec2  jz      short loc_180053F0E
0x180053ec4  mov     ecx, [rax]
0x180053ec6  cmp     ecx, edi
0x180053ec8  jnz     short loc_180053ED4
0x180053eca  mov     rax, [rax+8]
0x180053ece  mov     rax, [rax+30h]
0x180053ed2  jmp     short loc_180053F10
0x180053ed4  cmp     ecx, 2
0x180053ed7  jnz     short loc_180053EE3
0x180053ed9  mov     rax, [rax+10h]
0x180053edd  mov     rax, [rax+10h]
0x180053ee1  jmp     short loc_180053F10
0x180053ee3  cmp     ecx, 3
0x180053ee6  jnz     short loc_180053EEE
0x180053ee8  mov     rax, [rax+18h]
0x180053eec  jmp     short loc_180053EDD
0x180053eee  cmp     ecx, 4
0x180053ef1  jnz     short loc_180053EF9
0x180053ef3  mov     rax, [rax+20h]
0x180053ef7  jmp     short loc_180053EDD
0x180053ef9  cmp     ecx, r14d
0x180053efc  jnz     short loc_180053F04
0x180053efe  mov     rax, [rax+28h]
0x180053f02  jmp     short loc_180053ECE
0x180053f04  cmp     ecx, esi
0x180053f06  jnz     short loc_180053F0E
0x180053f08  mov     rax, [r8+10h]
0x180053f0c  jmp     short loc_180053F10
0x180053f0e  xor     eax, eax
0x180053f10  mov     ecx, [rdx]
0x180053f12  movups  xmm0, xmmword ptr [rdx+10h]
0x180053f16  movdqu  xmmword ptr [rbp+3Fh+var_B0.Data1], xmm0
0x180053f1b  lea     r8, [rbp+3Fh+var_58]
0x180053f1f  mov     [rsp+100h+var_D8], r8
0x180053f24  mov     [rsp+100h+var_E0], rax
0x180053f29  mov     r9d, ecx
0x180053f2c  lea     r8, [rbp+3Fh+var_B0]
0x180053f30  mov     rdx, [rdx+8]
0x180053f34  mov     rax, qword ptr [rbp+3Fh+var_A0.Data1]
0x180053f38  call    _guard_dispatch_icall
0x180053f3d  mov     ebx, eax
0x180053f3f  lea     rcx, [rsp+100h+var_C0]
0x180053f44  call    ?InternalRelease@?$XPtrBase@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@U?$STPolicy@VWUDeploymentSessionInfoWrapper@SessionDataUtil@@@Policies@WuSmartPtr@@@WuSmartPtr@@IEAAXXZ; WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(void)
0x180053f49  jmp     short loc_180053F99
0x180053f4b  mov     rcx, [rbp+3Fh+var_58]
0x180053f4f  test    rcx, rcx
0x180053f52  jz      short loc_180053F68
0x180053f54  mov     rax, [rcx]
0x180053f57  mov     rax, [rax+10h]
0x180053f5b  call    _guard_dispatch_icall
0x180053f60  mov     [rbp+3Fh+var_58], 0
0x180053f68  mov     rax, qword ptr [rbp+3Fh+var_B0.Data1]
0x180053f6c  movaps  xmm0, xmmword ptr [rax]
  ... truncated ...
```
