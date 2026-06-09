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
  signed int v11; // ebx
  __int64 v12; // rdx
  HMODULE Library; // rdi
  HMODULE v14; // rcx
  signed int LastError; // eax
  FARPROC v16; // rax
  int v17; // eax
  int *v18; // rax
  __int64 v19; // r8
  int v20; // ecx
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rax
  struct _GUID v24; // xmm0
  __int64 v25; // r9
  __int64 v26; // rdx
  unsigned int v27; // ecx
  int v28; // eax
  int *v29; // rax
  __int64 v30; // r8
  int v31; // ecx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rcx
  FARPROC ProcAddress; // r15
  signed int v36; // eax
  unsigned int v37; // ecx
  int v38; // eax
  unsigned __int64 v39; // r9
  __int64 v40; // rdx
  int *v41; // rax
  __int64 v42; // r9
  int v43; // edx
  __int64 v44; // rax
  __int64 v45; // r9
  __int64 v46; // rax
  struct IDeploymentSession *v47; // rax
  struct IDeploymentSession *v48; // rcx
  int v50; // [rsp+20h] [rbp-A1h]
  int v51; // [rsp+20h] [rbp-A1h]
  void *v52; // [rsp+20h] [rbp-A1h]
  int v53; // [rsp+20h] [rbp-A1h]
  int v54; // [rsp+20h] [rbp-A1h]
  struct SessionDataUtil::WUDeploymentSessionInfoWrapper *v55[2]; // [rsp+40h] [rbp-81h] BYREF
  struct _GUID v56; // [rsp+50h] [rbp-71h] BYREF
  struct _GUID v57; // [rsp+60h] [rbp-61h] BYREF
  struct IDeploymentSession **v58; // [rsp+70h] [rbp-51h]
  __int128 v59; // [rsp+78h] [rbp-49h] BYREF
  __int128 v60; // [rsp+88h] [rbp-39h]
  __int128 v61; // [rsp+98h] [rbp-29h]
  struct IDeploymentSession *v62; // [rsp+A8h] [rbp-19h] BYREF
  int v63; // [rsp+B0h] [rbp-11h] BYREF
  unsigned int v64; // [rsp+B4h] [rbp-Dh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  *(_QWORD *)&v56.Data1 = a4;
  v58 = a8;
  if ( !a8 )
  {
    v11 = -2147467261;
    v12 = 369;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
      (const char *)(unsigned int)v11,
      v50);
    return (unsigned int)v11;
  }
  Library = LoadLibraryExW(a2, 0, 0);
  v14 = (HMODULE)*((_QWORD *)this + 9);
  if ( v14 )
    FreeLibrary(v14);
  *((_QWORD *)this + 9) = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v11 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v11 = LastError;
    if ( v11 >= 0 )
      v11 = -2147418113;
    v50 = v11;
    WUTrace(0, 0, 4096, 1);
    v12 = 376;
    goto LABEL_3;
  }
  v62 = 0;
  *(_QWORD *)&v57.Data1 = GetProcAddress(Library, "CreateDeploymentSessionEx");
  if ( !*(_QWORD *)&v57.Data1 )
  {
    ProcAddress = GetProcAddress(*((HMODULE *)this + 9), "CreateDeploymentSession");
    if ( !ProcAddress )
    {
      v36 = GetLastError();
      v11 = (unsigned __int16)v36 | 0x80070000;
      if ( v36 <= 0 )
        v11 = v36;
      if ( v11 >= 0 )
        v11 = -2147418113;
      WUTrace(0, 0, 4096, 1);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x204,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
        (const char *)(unsigned int)v11,
        v11);
      goto LABEL_112;
    }
    v59 = 0;
    v60 = 0;
    v61 = 0;
    if ( a7 )
    {
      v59 = *(_OWORD *)a6;
      v60 = *((_OWORD *)a6 + 1);
      v61 = *((_OWORD *)a6 + 2);
    }
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl'::`2'::impl) )
    {
      v57 = *a4;
      v11 = ((__int64 (__fastcall *)(__int64, const wchar_t *, struct _GUID *, __int128 *, struct IDeploymentSession **))ProcAddress)(
              1,
              a3,
              &v57,
              &v59,
              &v62);
      if ( v11 >= 0 )
        goto LABEL_105;
      v50 = v11;
      WUTrace(0, 0, 4096, 1);
      v26 = 566;
LABEL_111:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
        (const char *)(unsigned int)v11,
        v50);
      goto LABEL_112;
    }
    v55[0] = 0;
    WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v55);
    v57 = *a4;
    v38 = SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(v37, a3, &v57, 5u, &v59, v55);
    v11 = v38;
    if ( v38 < 0 )
    {
      v39 = (unsigned int)v38;
      v40 = 540;
      goto LABEL_102;
    }
    if ( v62 )
    {
      (*(void (__fastcall **)(struct IDeploymentSession *))(*(_QWORD *)v62 + 16LL))(v62);
      v62 = 0;
    }
    v41 = (int *)*((_QWORD *)v55[0] + 4);
    if ( v41 )
    {
      v42 = *((_QWORD *)v41 + 6);
      if ( v42 )
      {
        v43 = *v41;
        if ( *v41 == 1 )
        {
          v44 = *((_QWORD *)v41 + 1);
LABEL_87:
          v45 = *(_QWORD *)(v44 + 48);
LABEL_100:
          v57 = (struct _GUID)*((_OWORD *)v55[0] + 1);
          v11 = ((__int64 (__fastcall *)(_QWORD, _QWORD, struct _GUID *, __int64, struct IDeploymentSession **))ProcAddress)(
                  *(unsigned int *)v55[0],
                  *((_QWORD *)v55[0] + 1),
                  &v57,
                  v45,
                  &v62);
          if ( v11 >= 0 )
          {
            WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v55);
            goto LABEL_105;
          }
          v54 = v11;
          WUTrace(0, 0, 4096, 1);
          v39 = (unsigned int)v11;
          v40 = 552;
LABEL_102:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v40,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
            (const char *)v39,
            v54);
          goto LABEL_103;
        }
        switch ( v43 )
        {
          case 2:
            v46 = *((_QWORD *)v41 + 2);
LABEL_90:
            v45 = *(_QWORD *)(v46 + 16);
            goto LABEL_100;
          case 3:
            v46 = *((_QWORD *)v41 + 3);
            goto LABEL_90;
          case 4:
            v46 = *((_QWORD *)v41 + 4);
            goto LABEL_90;
          case 5:
            v44 = *((_QWORD *)v41 + 5);
            goto LABEL_87;
          case 6:
            v45 = *(_QWORD *)(v42 + 16);
            goto LABEL_100;
        }
      }
    }
    v45 = 0;
    goto LABEL_100;
  }
  if ( a5 < 6 )
    goto LABEL_43;
  v16 = GetProcAddress(*((HMODULE *)this + 9), "GetSupportedSessionInitializationOptions");
  if ( !v16
    || (v63 = 0, v64 = 5, ((int (__fastcall *)(int *, unsigned int *))v16)(&v63, &v64) < 0)
    || (v63 & 1) == 0
    || v64 < 6 )
  {
    if ( (*((_BYTE *)a6 + 104) & 1) != 0 )
    {
      v11 = -2145116123;
      v26 = 457;
      goto LABEL_111;
    }
LABEL_43:
    WUTrace(0, 0, 4096, 4);
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl'::`2'::impl) )
    {
      v24 = *(struct _GUID *)*(_QWORD *)&v56.Data1;
      v52 = a7;
      v25 = 5;
      goto LABEL_67;
    }
    v55[0] = 0;
    WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v55);
    v56 = *(struct _GUID *)*(_QWORD *)&v56.Data1;
    v28 = SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(v27, a3, &v56, 5u, a7, v55);
    v11 = v28;
    if ( v28 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1DE,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
        (const char *)(unsigned int)v28,
        v53);
      goto LABEL_103;
    }
    if ( v62 )
    {
      (*(void (__fastcall **)(struct IDeploymentSession *))(*(_QWORD *)v62 + 16LL))(v62);
      v62 = 0;
    }
    v29 = (int *)*((_QWORD *)v55[0] + 4);
    if ( v29 )
    {
      v30 = *((_QWORD *)v29 + 6);
      if ( v30 )
      {
        v31 = *v29;
        if ( *v29 == 1 )
        {
          v32 = *((_QWORD *)v29 + 1);
LABEL_52:
          v22 = *(_QWORD *)(v32 + 48);
          goto LABEL_65;
        }
        switch ( v31 )
        {
          case 2:
            v33 = *((_QWORD *)v29 + 2);
LABEL_55:
            v22 = *(_QWORD *)(v33 + 16);
            goto LABEL_65;
          case 3:
            v33 = *((_QWORD *)v29 + 3);
            goto LABEL_55;
          case 4:
            v33 = *((_QWORD *)v29 + 4);
            goto LABEL_55;
          case 5:
            v32 = *((_QWORD *)v29 + 5);
            goto LABEL_52;
          case 6:
            v22 = *(_QWORD *)(v30 + 16);
            goto LABEL_65;
        }
      }
    }
    v22 = 0;
    goto LABEL_65;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_BugFixIUpdateSupportsExtendedSessionData>::GetImpl'::`2'::impl) )
  {
    v55[0] = 0;
    WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v55);
    v56 = *(struct _GUID *)*(_QWORD *)&v56.Data1;
    v17 = SessionDataUtil::WUDeploymentSessionInfoWrapper::CreateInstance(
            (unsigned int)v55,
            a3,
            &v56,
            6u,
            (const void *)((unsigned __int64)a6 & -(__int64)(a7 != 0)),
            v55);
    v11 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A8,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
        (const char *)(unsigned int)v17,
        v51);
LABEL_103:
      WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v55);
      goto LABEL_112;
    }
    if ( v62 )
    {
      (*(void (__fastcall **)(struct IDeploymentSession *))(*(_QWORD *)v62 + 16LL))(v62);
      v62 = 0;
    }
    v18 = (int *)*((_QWORD *)v55[0] + 4);
    if ( v18 )
    {
      v19 = *((_QWORD *)v18 + 6);
      if ( v19 )
      {
        v20 = *v18;
        if ( *v18 == 1 )
        {
          v21 = *((_QWORD *)v18 + 1);
LABEL_27:
          v22 = *(_QWORD *)(v21 + 48);
LABEL_65:
          v34 = *(unsigned int *)v55[0];
          v56 = (struct _GUID)*((_OWORD *)v55[0] + 1);
          v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct _GUID *, _QWORD, __int64, struct IDeploymentSession **))&v57.Data1)(
                  v34,
                  *((_QWORD *)v55[0] + 1),
                  &v56,
                  (unsigned int)v34,
                  v22,
                  &v62);
          WuSmartPtr::XPtrBase<SessionDataUtil::WUDeploymentSessionInfoWrapper,WuSmartPtr::Policies::STPolicy<SessionDataUtil::WUDeploymentSessionInfoWrapper>>::InternalRelease(v55);
          goto LABEL_68;
        }
        switch ( v20 )
        {
          case 2:
            v23 = *((_QWORD *)v18 + 2);
LABEL_30:
            v22 = *(_QWORD *)(v23 + 16);
            goto LABEL_65;
          case 3:
            v23 = *((_QWORD *)v18 + 3);
            goto LABEL_30;
          case 4:
            v23 = *((_QWORD *)v18 + 4);
            goto LABEL_30;
          case 5:
            v21 = *((_QWORD *)v18 + 5);
            goto LABEL_27;
          case 6:
            v22 = *(_QWORD *)(v19 + 16);
            goto LABEL_65;
        }
      }
    }
    v22 = 0;
    goto LABEL_65;
  }
  v24 = *(struct _GUID *)*(_QWORD *)&v56.Data1;
  v52 = (void *)((unsigned __int64)a6 & -(__int64)(a7 != 0));
  v25 = 6;
LABEL_67:
  v56 = v24;
  v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, struct _GUID *, __int64, void *, struct IDeploymentSession **))&v57.Data1)(
          1,
          a3,
          &v56,
          v25,
          v52,
          &v62);
LABEL_68:
  if ( v11 >= 0 )
  {
LABEL_105:
    v47 = v62;
    v48 = 0;
    v62 = 0;
    *v58 = v47;
    v11 = 0;
    goto LABEL_106;
  }
  WUTrace(0, 0, 4096, 1);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1F6,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\DeploymentSessionWrapper.cpp",
    (const char *)(unsigned int)v11,
    v11);
LABEL_112:
  v48 = v62;
LABEL_106:
  if ( v48 )
    (*(void (__fastcall **)(struct IDeploymentSession *))(*(_QWORD *)v48 + 16LL))(v48);
  return (unsigned int)v11;
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
