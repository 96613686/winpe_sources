# CLogonController::WaitForLockScreenDismiss(int *,int *)

- ea: `0x1800182c0`
- end: `0x1800190fa`
- name: `?WaitForLockScreenDismiss@CLogonController@@UEAAJPEAH0@Z`
- size: `3642`
- prototype: `__int64 __fastcall(CLogonController *__hidden this, int *, int *)`
- caller_count: `0`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000be10`
- `0x18000df10`
- `0x18000e750`
- `0x18000e840`
- `0x18000fff0`
- `0x180010348`
- `0x180015920`
- `0x180017400`
- `0x180017e18`
- `0x180017eb0`
- `0x180017ef0`
- `0x180017f74`
- `0x18001800c`
- `0x1800182c0`
- `0x180019100`
- `0x18001c56c`
- `0x18001c6a4`
- `0x18001c860`
- `0x18001db70`
- `0x18001f3a0`
- `0x18002318c`
- `0x180026e70`
- `0x18005b3e4`
- `0x18005d488`
- `0x180062064`
- `0x1800636b8`
- `0x18006c000`
- `0x18006cad0`
- `0x180075244`
- `0x18007c2e4`
- `0x18009b170`
- `0x18009b790`
- `0x18009d010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x1800184f0`
- `KERNEL32!ReleaseSRWLockShared` at `0x180018819`
- `KERNEL32!ReleaseSRWLockShared` at `0x1800184f0`
- `KERNEL32!ReleaseSRWLockShared` at `0x180018819`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180018451`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180018494`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180018608`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180018995`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800189f3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180018b00`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180018c08`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180018fdf`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180018451`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180018494`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180018608`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180018995`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800189f3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180018b00`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180018c08`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180018fdf`
- `KERNEL32!AcquireSRWLockShared` at `0x1800184bc`
- `KERNEL32!AcquireSRWLockShared` at `0x1800187e3`
- `KERNEL32!AcquireSRWLockShared` at `0x1800184bc`
- `KERNEL32!AcquireSRWLockShared` at `0x1800187e3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180018407`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180018594`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800187bc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800189c2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180018ad6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180018bc6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180018407`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180018594`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800187bc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800189c2`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180018ad6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180018bc6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018620`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018a6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018b66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018ca9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018d63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018ede`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018f70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001901d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018620`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018758`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018a6f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018b66`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018ca9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018d63`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018e1f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018ede`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018f70`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001901d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800187fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800187fc`
- `ntdll!NtQueryWnfStateData` at `0x1800188c0`
- `ntdll!NtQueryWnfStateData` at `0x1800188c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall CLogonController::WaitForLockScreenDismiss(RTL_SRWLOCK *this, RTL_SRWLOCK *a2, int *a3)
{
  __int64 (__fastcall ***v6)(PVOID, GUID *, void **); // r13
  int Ptr; // eax
  unsigned int v8; // edi
  __int64 (__fastcall ***v9)(PVOID, GUID *, void **); // rsi
  __int64 (__fastcall ***v10)(PVOID, GUID *, void **); // rdi
  int v11; // eax
  CLogonController *v12; // rcx
  PVOID v13; // rdi
  unsigned int v14; // r14d
  PVOID v15; // rcx
  __int64 (__fastcall *v16)(PVOID, GUID *, void **); // rbx
  __int64 v17; // rax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // rcx
  char *v22; // rbx
  int v23; // r13d
  bool v24; // r12
  CredProvPolicy *v25; // rcx
  PCWSTR StringRawBuffer; // rax
  int v27; // eax
  int v28; // eax
  CredProvPolicy *v29; // rcx
  int v30; // eax
  unsigned int WnfStateData; // eax
  const char *v32; // r9
  char v33; // al
  bool v34; // r12
  int v35; // eax
  int v36; // ecx
  int v37; // edx
  char v38; // al
  int v39; // edi
  RTL_SRWLOCK *v40; // r13
  __int64 v41; // rbx
  volatile int *v42; // rdx
  char *v43; // r8
  __int64 v44; // r8
  void *v45; // rcx
  RTL_SRWLOCK *v46; // rdi
  unsigned int v47; // ebx
  char v48; // r13
  PVOID v49; // r12
  int v50; // eax
  void *v51; // rcx
  PVOID v52; // rbx
  PVOID v53; // rdi
  __int64 (__fastcall *v54)(PVOID, GUID *, void **); // rbx
  int v55; // eax
  unsigned int v56; // ebx
  __int64 v57; // rcx
  void *v58; // rcx
  int v59; // eax
  __int64 v60; // rcx
  void *v61; // rcx
  int IsSystemManagedAccountLoggedIntoHomeScenario; // eax
  __int64 v63; // rcx
  void *v64; // rcx
  int IsSIDSystemManagedAccount; // eax
  int v66; // eax
  _BYTE *v67; // rbx
  __int64 v68; // rcx
  void *v69; // rcx
  int *v71; // [rsp+20h] [rbp-E0h]
  int v72; // [rsp+20h] [rbp-E0h]
  int v73; // [rsp+20h] [rbp-E0h]
  int v74; // [rsp+20h] [rbp-E0h]
  int v75; // [rsp+20h] [rbp-E0h]
  bool v76; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v78; // [rsp+40h] [rbp-C0h] BYREF
  void *v79; // [rsp+48h] [rbp-B8h] BYREF
  int v80[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v81; // [rsp+58h] [rbp-A8h] BYREF
  struct _GUID Buf1; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v83[2]; // [rsp+70h] [rbp-90h] BYREF
  char v84[8]; // [rsp+80h] [rbp-80h] BYREF
  __int64 (__fastcall ***v85)(PVOID, GUID *, void **); // [rsp+88h] [rbp-78h] BYREF
  RTL_SRWLOCK *v86; // [rsp+90h] [rbp-70h] BYREF
  CLogonController *v87; // [rsp+98h] [rbp-68h]
  PSRWLOCK SRWLock[3]; // [rsp+A0h] [rbp-60h] BYREF
  char v89; // [rsp+B8h] [rbp-48h]
  void **v90; // [rsp+C0h] [rbp-40h] BYREF
  int v91; // [rsp+C8h] [rbp-38h] BYREF
  char v92; // [rsp+CCh] [rbp-34h]
  int v93; // [rsp+F0h] [rbp-10h] BYREF
  const char *v94; // [rsp+F8h] [rbp-8h]
  __int64 v95; // [rsp+100h] [rbp+0h]
  char v96; // [rsp+108h] [rbp+8h]
  int v97; // [rsp+110h] [rbp+10h]
  char v98[152]; // [rsp+118h] [rbp+18h] BYREF
  __int128 v99; // [rsp+1B0h] [rbp+B0h]
  int v100; // [rsp+1C0h] [rbp+C0h]
  __int64 v101; // [rsp+1C8h] [rbp+C8h]
  int *v102; // [rsp+1D0h] [rbp+D0h]
  __int64 v103; // [rsp+1D8h] [rbp+D8h]
  __int64 v104; // [rsp+1E0h] [rbp+E0h]
  void ***v105; // [rsp+1E8h] [rbp+E8h]
  __int64 v106; // [rsp+1F0h] [rbp+F0h]
  int v107; // [rsp+1F8h] [rbp+F8h]
  int *v108; // [rsp+200h] [rbp+100h]
  char v109; // [rsp+208h] [rbp+108h]
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+158h]

  SRWLock[0] = a2;
  v6 = 0;
  v91 = 0;
  v92 = 0;
  v96 = 0;
  v93 = 0;
  v94 = "CLogonController_WaitForLockScreenDismiss_Activity";
  v95 = 0;
  v97 = 0;
  v99 = 0;
  memset_0(v98, 0, sizeof(v98));
  v100 = 1;
  v101 = 0;
  v102 = &v91;
  v103 = 0;
  v104 = 0;
  v105 = &v90;
  v106 = 0;
  v107 = 0;
  v108 = &v93;
  v109 = 0;
  v90 = &LogonControllerTelemetry::CLogonController_WaitForLockScreenDismiss_Activity::`vftable';
  Buf1 = *GetFirstRunTelemetryCorrelationId(&Buf1);
  if ( memcmp_0(&Buf1, &GUID_00000000_0000_0000_0000_000000000000, 0x10u) )
    wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(
      &v90,
      &Buf1);
  LogonControllerTelemetry::CLogonController_WaitForLockScreenDismiss_Activity::StartActivity((LogonControllerTelemetry::CLogonController_WaitForLockScreenDismiss_Activity *)&v90);
  LogonControllerTelemetry::User_Interaction_Requested();
  LODWORD(a2->Ptr) = 0;
  *a3 = 0;
  v87 = (CLogonController *)&this[-4];
  v78 = 0;
  AcquireSRWLockExclusive(this + 23);
  v86 = this + 23;
  Ptr = (int)this[24].Ptr;
  if ( Ptr && Ptr != 3 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v8 = -2147024739;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7A,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)0x8007009DLL,
      (int)v71);
    if ( this != (RTL_SRWLOCK *)-184LL )
      ReleaseSRWLockExclusive(this + 23);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x204,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)0x8007009DLL,
      v72);
    goto LABEL_148;
  }
  LODWORD(this[24].Ptr) = 1;
  v78 = ++LODWORD(this[26].Ptr);
  if ( this != (RTL_SRWLOCK *)-184LL )
    ReleaseSRWLockExclusive(this + 23);
  SRWLock[1] = this - 4;
  SRWLock[2] = (PSRWLOCK)&v78;
  v89 = 1;
  v9 = 0;
  v85 = 0;
  AcquireSRWLockShared(this + 27);
  v10 = (__int64 (__fastcall ***)(PVOID, GUID *, void **))this[28].Ptr;
  if ( v10 )
  {
    ((void (__fastcall *)(PVOID))(*v10)[1])(this[28].Ptr);
    v9 = v10;
    v85 = v10;
    v6 = v10;
  }
  if ( this != (RTL_SRWLOCK *)-216LL )
    ReleaseSRWLockShared(this + 27);
  if ( !v6 )
    goto LABEL_162;
  *(_QWORD *)&Buf1.Data1 = this - 4;
  Buf1.Data4[0] = 1;
  v79 = 0;
  v11 = (**v9)(v6, &GUID_00000036_0000_0000_c000_000000000046, &v79);
  v8 = v11;
  LODWORD(v6) = 0;
  if ( v11 >= 0 )
  {
    v13 = v79;
    v14 = v78;
    *a3 = 0;
    AcquireSRWLockExclusive(this + 23);
    if ( LODWORD(this[24].Ptr) == 1 && v14 == LODWORD(this[26].Ptr) )
    {
      LODWORD(this[24].Ptr) = 2;
      if ( this[25].Ptr != v13 )
      {
        if ( v13 )
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)v13 + 8LL))(v13);
        v15 = this[25].Ptr;
        this[25].Ptr = v13;
        if ( v15 )
          (*(void (__fastcall **)(PVOID))(*(_QWORD *)v15 + 16LL))(v15);
      }
    }
    else
    {
      *a3 = 1;
    }
    if ( this != (RTL_SRWLOCK *)-184LL )
      ReleaseSRWLockExclusive(this + 23);
    if ( *a3 )
    {
LABEL_156:
      v80[0] = 0;
      if ( (*(int (__fastcall **)(__int64, int *))(*((_QWORD *)this[14].Ptr + 4) + 48LL))(
             (__int64)this[14].Ptr + 32,
             v80) >= 0
        && (v80[0] & 0x200) != 0 )
      {
        LogonControllerTelemetry::DelayLockDismissed();
      }
      v69 = v79;
      if ( v79 )
      {
        v79 = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v69 + 16LL))(v69);
      }
      Buf1.Data4[0] = 0;
      lambda_ed01a7c2c5d72a51601480778acc1f76_::operator()(&Buf1);
LABEL_162:
      if ( v9 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(PVOID, GUID *, void **)))(*v9)[2])(v9);
      CLogonController::_TransitionToNone((CLogonController *)&this[-4], v78);
      wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v90, 0);
      v8 = (unsigned int)v6;
      goto LABEL_165;
    }
    WindowsDeleteString(0);
    string = 0;
    *a3 = 0;
    v8 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(v9);
    if ( (v8 & 0x80000000) == 0 )
      v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(PVOID, GUID *, void **), HSTRING *))(*v9)[8])(v9, &string);
    if ( v8 == -2147023673 )
    {
      *a3 = 1;
      goto LABEL_43;
    }
    if ( (v8 & 0x80000000) == 0 )
    {
      v83[0] = 0;
      v16 = **v9;
      v17 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(v83);
      v18 = v16(v9, &GUID_00000036_0000_0000_c000_000000000046, (void **)v17);
      v8 = v18;
      if ( v18 >= 0 )
      {
        v80[0] = 0;
        v19 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)v83[0] + 56LL))(v83[0], v80);
        v8 = v19;
        if ( v19 >= 0 )
        {
          *a3 = v80[0] != 1;
          v21 = v83[0];
          if ( v83[0] )
          {
            v83[0] = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          }
LABEL_43:
          v22 = (char *)this[14].Ptr;
          AcquireSRWLockExclusive((PSRWLOCK)v22 + 63);
          v86 = (RTL_SRWLOCK *)(v22 + 504);
          v76 = 0;
          v23 = *((_DWORD *)v22 + 128) & 0x10;
          v24 = 0;
          AcquireSRWLockShared((PSRWLOCK)v22 + 52);
          *(_QWORD *)v80 = v22 + 416;
          v25 = (CredProvPolicy *)*((_QWORD *)v22 + 53);
          if ( v25 )
          {
            StringRawBuffer = WindowsGetStringRawBuffer((HSTRING)v25, 0);
            v24 = (unsigned int)GetAssignedAccessTypeForUser(StringRawBuffer) == 1;
          }
          if ( v22 != (char *)-416LL )
            ReleaseSRWLockShared((PSRWLOCK)v22 + 52);
          v27 = *((_DWORD *)v22 + 128);
          if ( (v27 & 4) != 0 )
          {
            v76 = 1;
            v28 = v27 ^ 4 | 0x40000;
            *((_DWORD *)v22 + 128) = v28;
            if ( v24 )
              *((_DWORD *)v22 + 128) = v28 & 0xFFFFFFEF;
            if ( CredProvPolicy::IsPrimaryUserForEduEnvironment(v25)
              || CredProvPolicy::IsSharedUserForEduEnvironment(v29) )
            {
              *((_DWORD *)v22 + 128) |= 0x4000000u;
            }
          }
          v30 = *((_DWORD *)v22 + 128);
          if ( (v30 & 8) != 0 )
          {
            *((_DWORD *)v22 + 128) = v30 ^ 8;
            v76 = 1;
          }
          if ( v24 )
            goto LABEL_75;
          v80[0] = 0;
          *(_DWORD *)v84 = 4;
          LODWORD(v83[0]) = 0;
          v71 = v80;
          WnfStateData = NtQueryWnfStateData(&WNF_NGC_CREDENTIAL_RESET_EXPERIENCE_ACTIVE, 0, 0, v83);
          v32 = (const char *)WnfStateData;
          LODWORD(v32) = WnfStateData | 0x10000000;
          if ( (int)((WnfStateData | 0x10000000) + 0x80000000) >= 0 && (_DWORD)v32 != -805306333 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2CC,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
              v32,
              (int)v80);
            goto LABEL_59;
          }
          v35 = v83[0];
          if ( LODWORD(v83[0]) )
          {
            v36 = *(_DWORD *)v84;
            if ( *(_DWORD *)v84 == 4 )
            {
              v37 = v80[0];
            }
            else
            {
              wil::details::in1diag3::Log_HrMsg(
                retaddr,
                (void *)0x271,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
                (const char *)0x8000FFFFLL,
                (int)"Inconsistent state data size in wnf_query",
                v84);
              v37 = 0;
              v36 = *(_DWORD *)v84;
              v35 = v83[0];
            }
            if ( v35 && v36 == 4 )
            {
              v38 = 1;
LABEL_71:
              if ( v38 && v37 && !v23 )
              {
                v33 = 1;
LABEL_60:
                if ( v33 )
                  goto LABEL_61;
LABEL_75:
                v34 = v76;
                goto LABEL_76;
              }
LABEL_59:
              v33 = 0;
              if ( v23 )
              {
LABEL_61:
                *((_DWORD *)v22 + 128) ^= 0x10u;
                v34 = 1;
LABEL_76:
                v39 = *((_DWORD *)v22 + 128);
                if ( v22 != (char *)-504LL )
                  ReleaseSRWLockExclusive((PSRWLOCK)v22 + 63);
                if ( v34 )
                {
                  v40 = (RTL_SRWLOCK *)(v22 + 480);
                  v80[0] = v39;
                  v86 = (RTL_SRWLOCK *)v22;
                  v8 = 0;
                  v41 = 0;
                  *(_QWORD *)v84 = 0;
                  AcquireSRWLockExclusive(v40 + 1);
                  v43 = (char *)v40->Ptr;
                  v83[0] = 0;
                  if ( v43 )
                  {
                    Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v43 + 12), v42);
                    v41 = v44;
                    *(_QWORD *)v84 = v44;
                    v83[0] = v44;
                  }
                  if ( v40 != (RTL_SRWLOCK *)-8LL )
                    ReleaseSRWLockExclusive(v40 + 1);
                  if ( v83[0] )
                  {
                    v83[0] = &v86;
                    v83[1] = v80;
                    v8 = Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_df6e2a8822698adaa00bb4700851df6e_,Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::CredProvData::IDisplayStateProvider *,enum Windows::Internal::UI::Logon::CredProvData::DisplayStateFlags>,Microsoft::WRL::InvokeModeOptions<-2>>(
                           v83,
                           v41,
                           v40);
                  }
                  Microsoft::WRL::ComPtr<Microsoft::WRL::Details::EventTargetArray>::InternalRelease(v84);
                  if ( (v8 & 0x80000000) != 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x4DF,
                      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
                      (const char *)v8,
                      (int)v71);
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x231,
                      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
                      (const char *)v8,
                      v74);
                    WindowsDeleteString(string);
                    string = 0;
                    v45 = v79;
                    if ( v79 )
                    {
                      v79 = 0;
                      (*(void (__fastcall **)(void *))(*(_QWORD *)v45 + 16LL))(v45);
                    }
                    Buf1.Data4[0] = 0;
                    lambda_ed01a7c2c5d72a51601480778acc1f76_::operator()(&Buf1);
                    if ( v9 )
                      ((void (__fastcall *)(__int64 (__fastcall ***)(PVOID, GUID *, void **)))(*v9)[2])(v9);
                    goto LABEL_139;
                  }
                }
                v46 = (RTL_SRWLOCK *)this[14].Ptr;
                AcquireSRWLockExclusive(v46 + 63);
                v47 = (unsigned int)v46[64].Ptr;
                if ( (v47 & 0x80u) == 0 )
                {
                  v48 = 0;
                }
                else
                {
                  v47 ^= 0x80u;
                  LODWORD(v46[64].Ptr) = v47;
                  v48 = 1;
                }
                if ( v46 != (RTL_SRWLOCK *)-504LL )
                  ReleaseSRWLockExclusive(v46 + 63);
                v49 = 0;
                if ( v48 )
                {
                  v50 = Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::Internal::UI::Logon::CredProvData::IDisplayStateProvider *,enum Windows::Internal::UI::Logon::CredProvData::DisplayStateFlags>,Microsoft::WRL::InvokeModeOptions<-2>>::InvokeAll<CProcessStateManager *,enum Windows::Internal::UI::Logon::CredProvData::DisplayStateFlags>(
                          &v46[60],
                          v46,
                          v47);
                  v8 = v50;
                  if ( v50 < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x55E,
                      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\processstatemanager.cpp",
                      (const char *)(unsigned int)v50,
                      (int)v71);
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x232,
                      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
                      (const char *)v8,
                      v75);
                    WindowsDeleteString(string);
                    string = 0;
                    v51 = v79;
                    if ( v79 )
                    {
                      v79 = 0;
                      (*(void (__fastcall **)(void *))(*(_QWORD *)v51 + 16LL))(v51);
                    }
                    Buf1.Data4[0] = 0;
                    lambda_ed01a7c2c5d72a51601480778acc1f76_::operator()(&Buf1);
                    if ( v9 )
                      ((void (__fastcall *)(__int64 (__fastcall ***)(PVOID, GUID *, void **)))(*v9)[2])(v9);
                    goto LABEL_139;
                  }
                }
                *(_QWORD *)v80 = 0;
                AcquireSRWLockExclusive(this + 39);
                v52 = this[43].Ptr;
                this[43].Ptr = 0;
                v53 = 0;
                if ( v52 )
                {
                  (*(void (__fastcall **)(PVOID))(*(_QWORD *)v52 + 8LL))(v52);
                  v49 = v52;
                  *(_QWORD *)v80 = v52;
                  v53 = v52;
                }
                if ( this != (RTL_SRWLOCK *)-312LL )
                  ReleaseSRWLockExclusive(this + 39);
                LODWORD(v6) = 0;
                if ( v53 )
                  (*(void (__fastcall **)(PVOID))(*(_QWORD *)v53 + 72LL))(v53);
                v81 = 0;
                v54 = **v9;
                Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v81);
                v55 = v54(v9, &GUID_bd4fd664_fd5e_4ea2_8a71_48a75a4529c0, (void **)&v81);
                v56 = v55;
                if ( v55 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x243,
                    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
                    (const char *)(unsigned int)v55,
                    (int)v71);
                  v57 = v81;
                  if ( v81 )
                  {
                    v81 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 16LL))(v57);
                  }
                  if ( v53 )
                    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v53 + 16LL))(v53);
                  WindowsDeleteString(string);
                  string = 0;
                  v58 = v79;
                  if ( v79 )
                  {
                    v79 = 0;
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v58 + 16LL))(v58);
                  }
                  Buf1.Data4[0] = 0;
                  lambda_ed01a7c2c5d72a51601480778acc1f76_::operator()(&Buf1);
                  if ( v9 )
                    ((void (__fastcall *)(__int64 (__fastcall ***)(PVOID, GUID *, void **)))(*v9)[2])(v9);
LABEL_138:
                  v8 = v56;
LABEL_139:
                  CLogonController::_TransitionToNone(v87, v78);
LABEL_165:
                  v90 = &LogonControllerTelemetry::CLogonController_WaitForLockScreenDismiss_Activity::`vftable';
                  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v90);
                  wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v90);
                  return v8;
                }
                v59 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v81 + 64LL))(v81);
                v56 = v59;
                if ( v59 < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x244,
                    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
                    (const char *)(unsigned int)v59,
                    (int)v71);
                  v60 = v81;
                  if ( v81 )
                  {
                    v81 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v60 + 16LL))(v60);
                  }
                  if ( v53 )
                    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v53 + 16LL))(v53);
                  WindowsDeleteString(string);
                  string = 0;
                  v61 = v79;
                  if ( v79 )
                  {
                    v79 = 0;
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v61 + 16LL))(v61);
                  }
                  Buf1.Data4[0] = 0;
                  lambda_ed01a7c2c5d72a51601480778acc1f76_::operator()(&Buf1);
                  if ( v9 )
                    ((void (__fastcall *)(__int64 (__fastcall ***)(PVOID, GUID *, void **)))(*v9)[2])(v9);
                  goto LABEL_138;
                }
                v76 = 0;
                IsSystemManagedAccountLoggedIntoHomeScenario = CLogonController::_IsSystemManagedAccountLoggedIntoHomeScenario(
                                                                 (CLogonController *)&this[-4],
                                                                 &v76);
                v56 = IsSystemManagedAccountLoggedIntoHomeScenario;
                if ( IsSystemManagedAccountLoggedIntoHomeScenario < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x24A,
                    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
                    (const char *)(unsigned int)IsSystemManagedAccountLoggedIntoHomeScenario,
                    (int)v71);
                  v63 = v81;
                  if ( v81 )
                  {
                    v81 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
                  }
                  if ( v53 )
                    (*(void (__fastcall **)(PVOID))(*(_QWORD *)v53 + 16LL))(v53);
                  WindowsDeleteString(string);
                  string = 0;
                  v64 = v79;
                  if ( v79 )
                  {
                    v79 = 0;
                    (*(void (__fastcall **)(void *))(*(_QWORD *)v64 + 16LL))(v64);
                  }
                  Buf1.Data4[0] = 0;
                  lambda_ed01a7c2c5d72a51601480778acc1f76_::operator()(&Buf1);
                  if ( v9 )
                    ((void (__fastcall *)(__int64 (__fastcall ***)(PVOID, GUID *, void **)))(*v9)[2])(v9);
                  goto LABEL_138;
                }
                if ( v76 )
                {
                  v76 = 0;
                  IsSIDSystemManagedAccount = CLogonController::_IsSIDSystemManagedAccount(
                                                (CLogonController *)&this[-4],
                                                string,
                                                &v76);
                  v8 = IsSIDSystemManagedAccount;
                  if ( IsSIDSystemManagedAccount < 0 )
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x24F,
                      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
                      (const char *)(unsigned int)IsSIDSystemManagedAccount,
                      (int)v71);
                    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v81);
                    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(v80);
                    WindowsDeleteString(string);
                    string = 0;
                    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
                    Buf1.Data4[0] = 0;
                    lambda_ed01a7c2c5d72a51601480778acc1f76_::operator()(&Buf1);
LABEL_146:
                    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v85);
                    v12 = (CLogonController *)&this[-4];
                    goto LABEL_147;
                  }
                  if ( !v76 )
                  {
                    LODWORD(SRWLock[0]->Ptr) = 1;
                    v66 = (*(__int64 (__fastcall **)(__int64, HSTRING))(*((_QWORD *)this[14].Ptr + 2) + 88LL))(
                            (__int64)this[14].Ptr + 16,
                            string);
                    v8 = v66;
                    if ( v66 < 0 )
                    {
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x254,
                        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
                        (const char *)(unsigned int)v66,
                        (int)v71);
                      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v81);
                      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(v80);
                      WindowsDeleteString(string);
                      string = 0;
                      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
                      Buf1.Data4[0] = 0;
                      lambda_ed01a7c2c5d72a51601480778acc1f76_::operator()(&Buf1);
                      goto LABEL_146;
                    }
                    v67 = this[14].Ptr;
                    Microsoft::WRL::Wrappers::SRWLock::LockExclusive(SRWLock, v67 + 416);
                    v67[453] = 1;
                    if ( SRWLock[0] )
                      ReleaseSRWLockExclusive(SRWLock[0]);
                  }
                }
                v68 = v81;
                if ( v81 )
                {
                  v81 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v68 + 16LL))(v68);
                }
                if ( v49 )
                  (*(void (__fastcall **)(PVOID))(*(_QWORD *)v49 + 16LL))(v49);
                WindowsDeleteString(string);
                goto LABEL_156;
              }
              goto LABEL_60;
            }
          }
          else
          {
            v37 = v80[0];
          }
          v38 = 0;
          goto LABEL_71;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDB4,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
          (const char *)(unsigned int)v19,
          (int)v71);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEE2,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
          (const char *)v8,
          v73);
        v20 = v83[0];
        if ( v83[0] )
        {
          v83[0] = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEE1,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
          (const char *)(unsigned int)v18,
          (int)v71);
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v83);
      }
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x230,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)v8,
      (int)v71);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
    Buf1.Data4[0] = 0;
    lambda_ed01a7c2c5d72a51601480778acc1f76_::operator()(&Buf1);
    goto LABEL_17;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x22A,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
    (const char *)(unsigned int)v11,
    (int)v71);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v79);
  Buf1.Data4[0] = 0;
  lambda_ed01a7c2c5d72a51601480778acc1f76_::operator()(&Buf1);
LABEL_17:
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v85);
  v12 = v87;
LABEL_147:
  CLogonController::_TransitionToNone(v12, v78);
LABEL_148:
  LogonControllerTelemetry::CLogonController_WaitForLockScreenDismiss_Activity::~CLogonController_WaitForLockScreenDismiss_Activity((LogonControllerTelemetry::CLogonController_WaitForLockScreenDismiss_Activity *)&v90);
  return v8;
}

```

## disassembly

```asm
0x1800182c0  mov     [rsp-8+arg_18], rbx
0x1800182c5  push    rbp
0x1800182c6  push    rsi
0x1800182c7  push    rdi
0x1800182c8  push    r12
0x1800182ca  push    r13
0x1800182cc  push    r14
0x1800182ce  push    r15
0x1800182d0  lea     rbp, [rsp-120h]
0x1800182d8  sub     rsp, 220h
0x1800182df  mov     rax, cs:__security_cookie
0x1800182e6  xor     rax, rsp
0x1800182e9  mov     [rbp+150h+var_40], rax
0x1800182f0  mov     r12, r8
0x1800182f3  mov     rbx, rdx
0x1800182f6  mov     [rbp+150h+SRWLock], rdx
0x1800182fa  mov     r15, rcx
0x1800182fd  xor     r13d, r13d
0x180018300  mov     [rbp+150h+var_188], r13d
0x180018304  mov     [rbp+150h+var_184], r13b
0x180018308  mov     [rbp+150h+var_148], r13b
0x18001830c  mov     [rbp+150h+var_160], r13d
0x180018310  lea     rax, aClogoncontroll_19; "CLogonController_WaitForLockScreenDismi"...
0x180018317  mov     [rbp+150h+var_158], rax
0x18001831b  mov     [rbp+150h+var_150], r13
0x18001831f  mov     [rbp+150h+var_140], r13d
0x180018323  xorps   xmm0, xmm0
0x180018326  movdqa  [rbp+150h+var_A0], xmm0
0x18001832e  xor     edx, edx; Val
0x180018330  mov     r8d, 98h; Size
0x180018336  lea     rcx, [rbp+150h+var_138]; void *
0x18001833a  call    memset_0
0x18001833f  lea     esi, [r13+1]
0x180018343  mov     [rbp+150h+var_90], esi
0x180018349  xor     eax, eax
0x18001834b  mov     [rbp+150h+var_88], rax
0x180018352  lea     rax, [rbp+150h+var_188]
0x180018356  mov     [rbp+150h+var_80], rax
0x18001835d  mov     [rbp+150h+var_78], r13
0x180018364  mov     [rbp+150h+var_70], r13
0x18001836b  lea     rax, [rbp+150h+var_190]
0x18001836f  mov     [rbp+150h+var_68], rax
0x180018376  mov     [rbp+150h+var_60], r13
0x18001837d  mov     [rbp+150h+var_58], r13d
0x180018384  lea     rax, [rbp+150h+var_160]
0x180018388  mov     [rbp+150h+var_50], rax
0x18001838f  mov     [rbp+150h+var_48], r13b
0x180018396  lea     rax, ??_7CLogonController_WaitForLockScreenDismiss_Activity@LogonControllerTelemetry@@6B@; const LogonControllerTelemetry::CLogonController_WaitForLockScreenDismiss_Activity::`vftable'
0x18001839d  mov     [rbp+150h+var_190], rax
0x1800183a1  lea     rcx, [rsp+250h+Buf1]; retstr
0x1800183a6  call    ?GetFirstRunTelemetryCorrelationId@@YA?AU_GUID@@XZ; GetFirstRunTelemetryCorrelationId(void)
0x1800183ab  movups  xmm0, xmmword ptr [rax]
0x1800183ae  movdqu  [rsp+250h+Buf1], xmm0
0x1800183b4  lea     r8d, [r13+10h]; Size
0x1800183b8  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000; Buf2
0x1800183bf  lea     rcx, [rsp+250h+Buf1]; Buf1
0x1800183c4  call    memcmp_0
0x1800183c9  test    eax, eax
0x1800183cb  jz      short loc_1800183DB
0x1800183cd  lea     rdx, [rsp+250h+Buf1]
0x1800183d2  lea     rcx, [rbp+150h+var_190]
0x1800183d6  call    ?SetRelatedActivityId@?$ActivityBase@VLogonControllerLogger@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXAEBU_GUID@@@Z; wil::ActivityBase<LogonControllerLogger,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::SetRelatedActivityId(_GUID const &)
0x1800183db  lea     rcx, [rbp+150h+var_190]; this
0x1800183df  call    ?StartActivity@CLogonController_WaitForLockScreenDismiss_Activity@LogonControllerTelemetry@@QEAAXXZ; LogonControllerTelemetry::CLogonController_WaitForLockScreenDismiss_Activity::StartActivity(void)
0x1800183e4  call    ?User_Interaction_Requested@LogonControllerTelemetry@@SAXXZ; LogonControllerTelemetry::User_Interaction_Requested(void)
0x1800183e9  mov     [rbx], r13d
0x1800183ec  mov     [r12], r13d
0x1800183f0  lea     rdi, [r15-20h]
0x1800183f4  mov     [rbp+150h+var_1B8], rdi
0x1800183f8  mov     [rsp+250h+var_210], r13d
0x1800183fd  lea     rbx, [rdi+0D8h]
0x180018404  mov     rcx, rbx; SRWLock
0x180018407  call    cs:__imp_AcquireSRWLockExclusive
0x18001840d  mov     [rbp+150h+var_1C0], rbx
0x180018411  mov     eax, [rdi+0E0h]
0x180018417  test    eax, eax
0x180018419  jz      short loc_180018473
0x18001841b  cmp     eax, 3
0x18001841e  jz      short loc_180018473
0x180018420  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180018425  mov     rcx, [rbp+158h]; this
0x18001842c  mov     edi, 8007009Dh
0x180018431  mov     r9d, edi; char *
0x180018434  lea     r14, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18001843b  mov     r8, r14; unsigned int
0x18001843e  mov     edx, 0D7Ah; void *
0x180018443  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018448  nop
0x180018449  test    rbx, rbx
0x18001844c  jz      short loc_180018457
0x18001844e  mov     rcx, rbx; SRWLock
0x180018451  call    cs:__imp_ReleaseSRWLockExclusive
0x180018457  mov     rcx, [rbp+158h]; this
0x18001845e  mov     r9d, edi; char *
0x180018461  mov     r8, r14; unsigned int
0x180018464  mov     edx, 204h; void *
0x180018469  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001846e  jmp     loc_180018FAD
0x180018473  mov     [r15+0C0h], esi
0x18001847a  add     [r15+0D0h], esi
0x180018481  mov     eax, [r15+0D0h]
0x180018488  mov     [rsp+250h+var_210], eax
0x18001848c  test    rbx, rbx
0x18001848f  jz      short loc_18001849A
0x180018491  mov     rcx, rbx; SRWLock
0x180018494  call    cs:__imp_ReleaseSRWLockExclusive
0x18001849a  mov     [rbp+150h+var_1A8], rdi
0x18001849e  lea     rax, [rsp+250h+var_210]
0x1800184a3  mov     [rbp+150h+var_1A0], rax
0x1800184a7  mov     [rbp+150h+var_198], sil
0x1800184ab  mov     rsi, r13
0x1800184ae  mov     [rbp+150h+var_1C8], r13
0x1800184b2  lea     r14, [r15+0D8h]
0x1800184b9  mov     rcx, r14; SRWLock
0x1800184bc  call    cs:__imp_AcquireSRWLockShared
0x1800184c2  mov     rdi, [r15+0E0h]
0x1800184c9  test    rdi, rdi
0x1800184cc  jz      short loc_1800184E8
0x1800184ce  mov     rax, [rdi]
0x1800184d1  mov     rcx, rdi
0x1800184d4  mov     rax, [rax+8]
0x1800184d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184dd  nop
0x1800184de  mov     rsi, rdi
0x1800184e1  mov     [rbp+150h+var_1C8], rdi
0x1800184e5  mov     r13, rdi
0x1800184e8  test    r14, r14
0x1800184eb  jz      short loc_1800184F6
0x1800184ed  mov     rcx, r14; SRWLock
0x1800184f0  call    cs:__imp_ReleaseSRWLockShared
0x1800184f6  test    r13, r13
0x1800184f9  jz      loc_180019081
0x1800184ff  lea     rax, [r15-20h]
0x180018503  mov     qword ptr [rsp+250h+Buf1], rax
0x180018508  mov     byte ptr [rsp+250h+Buf1+8], 1
0x18001850d  mov     [rsp+250h+var_208], 0
0x180018516  mov     rax, [rsi]
0x180018519  lea     r8, [rsp+250h+var_208]
0x18001851e  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180018525  mov     rcx, r13
0x180018528  mov     rax, [rax]
0x18001852b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018530  mov     edi, eax
0x180018532  xor     r13d, r13d
0x180018535  test    eax, eax
0x180018537  jns     short loc_180018583
0x180018539  mov     rcx, [rbp+158h]; this
0x180018540  mov     r9d, eax; char *
0x180018543  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18001854a  mov     edx, 22Ah; void *
0x18001854f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018554  nop
0x180018555  lea     rcx, [rsp+250h+var_208]
0x18001855a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001855f  nop
0x180018560  mov     byte ptr [rsp+250h+Buf1+8], r13b
0x180018565  lea     rcx, [rsp+250h+Buf1]
0x18001856a  call    _lambda_ed01a7c2c5d72a51601480778acc1f76___operator__
0x18001856f  nop
0x180018570  lea     rcx, [rbp+150h+var_1C8]
0x180018574  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180018579  nop
0x18001857a  mov     rcx, [rbp+150h+var_1B8]
0x18001857e  jmp     loc_180018FA3
0x180018583  mov     rdi, [rsp+250h+var_208]
0x180018588  mov     r14d, [rsp+250h+var_210]
0x18001858d  mov     [r12], r13d
0x180018591  mov     rcx, rbx; SRWLock
0x180018594  call    cs:__imp_AcquireSRWLockExclusive
0x18001859a  cmp     dword ptr [r15+0C0h], 1
0x1800185a2  jnz     short loc_1800185F8
0x1800185a4  cmp     r14d, [r15+0D0h]
0x1800185ab  jnz     short loc_1800185F8
0x1800185ad  mov     dword ptr [r15+0C0h], 2
0x1800185b8  cmp     [r15+0C8h], rdi
0x1800185bf  jz      short loc_180018600
0x1800185c1  test    rdi, rdi
0x1800185c4  jz      short loc_1800185D6
0x1800185c6  mov     rax, [rdi]
0x1800185c9  mov     rcx, rdi
0x1800185cc  mov     rax, [rax+8]
0x1800185d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185d5  nop
0x1800185d6  mov     rcx, [r15+0C8h]
0x1800185dd  mov     [r15+0C8h], rdi
0x1800185e4  test    rcx, rcx
0x1800185e7  jz      short loc_1800185F6
0x1800185e9  mov     rax, [rcx]
0x1800185ec  mov     rax, [rax+10h]
0x1800185f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185f5  nop
0x1800185f6  jmp     short loc_180018600
0x1800185f8  mov     dword ptr [r12], 1
0x180018600  test    rbx, rbx
0x180018603  jz      short loc_18001860F
0x180018605  mov     rcx, rbx; SRWLock
0x180018608  call    cs:__imp_ReleaseSRWLockExclusive
0x18001860e  nop
0x18001860f  cmp     [r12], r13d
0x180018613  jnz     loc_180019023
0x180018619  mov     [rsp+250h+string], r13
0x18001861e  xor     ecx, ecx; string
0x180018620  call    cs:__imp_WindowsDeleteString
0x180018626  mov     [rsp+250h+string], r13
0x18001862b  mov     [r12], r13d
0x18001862f  mov     rcx, rsi
0x180018632  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUHSTRING__@@@Foundation@Windows@@U?$IAsyncOperation@PEAUHSTRING__@@@23@@@YAJPEAU?$IAsyncOperation@PEAUHSTRING__@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<HSTRING__ *>,Windows::Foundation::IAsyncOperation<HSTRING__ *>>(Windows::Foundation::IAsyncOperation<HSTRING__ *> *,tagCOWAIT_FLAGS,void *)
0x180018637  mov     edi, eax
0x180018639  test    eax, eax
0x18001863b  js      short loc_180018653
0x18001863d  mov     rax, [rsi]
0x180018640  lea     rdx, [rsp+250h+string]
0x180018645  mov     rcx, rsi
0x180018648  mov     rax, [rax+40h]
0x18001864c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018651  mov     edi, eax
0x180018653  lea     r14, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18001865a  cmp     edi, 800704C7h
0x180018660  jnz     short loc_18001866F
0x180018662  mov     dword ptr [r12], 1
0x18001866a  jmp     loc_1800187AE
0x18001866f  test    edi, edi
0x180018671  js      loc_18001873B
0x180018677  mov     [rsp+250h+var_1E0], r13
0x18001867c  mov     rax, [rsi]
0x18001867f  mov     rbx, [rax]
0x180018682  lea     rcx, [rsp+250h+var_1E0]
0x180018687  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UIAsyncInfo@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IAsyncInfo>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IAsyncInfo>>)
0x18001868c  mov     r8, rax
0x18001868f  lea     rdx, _GUID_00000036_0000_0000_c000_000000000046
0x180018696  mov     rcx, rsi
0x180018699  mov     rax, rbx
0x18001869c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186a1  mov     edi, eax
0x1800186a3  test    eax, eax
0x1800186a5  jns     short loc_1800186CB
0x1800186a7  mov     rcx, [rbp+158h]; this
0x1800186ae  mov     r9d, eax; char *
0x1800186b1  mov     r8, r14; unsigned int
0x1800186b4  mov     edx, 0EE1h; void *
0x1800186b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800186be  nop
0x1800186bf  lea     rcx, [rsp+250h+var_1E0]
0x1800186c4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800186c9  jmp     short loc_18001873B
0x1800186cb  mov     rcx, [rsp+250h+var_1E0]
0x1800186d0  mov     [rsp+250h+var_200], r13d
0x1800186d5  mov     rax, [rcx]
0x1800186d8  lea     rdx, [rsp+250h+var_200]
0x1800186dd  mov     rax, [rax+38h]
0x1800186e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186e6  mov     edi, eax
0x1800186e8  test    eax, eax
0x1800186ea  jns     loc_180018783
0x1800186f0  mov     rcx, [rbp+158h]; this
0x1800186f7  mov     r9d, eax; char *
0x1800186fa  mov     r8, r14; unsigned int
0x1800186fd  mov     edx, 0DB4h; void *
0x180018702  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018707  mov     rcx, [rbp+158h]; this
0x18001870e  mov     r9d, edi; char *
0x180018711  mov     r8, r14; unsigned int
0x180018714  mov     edx, 0EE2h; void *
0x180018719  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001871e  nop
0x18001871f  mov     rcx, [rsp+250h+var_1E0]
0x180018724  test    rcx, rcx
0x180018727  jz      short loc_18001873B
0x180018729  mov     [rsp+250h+var_1E0], r13
0x18001872e  mov     rax, [rcx]
0x180018731  mov     rax, [rax+10h]
0x180018735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001873a  nop
0x18001873b  mov     rcx, [rbp+158h]; this
0x180018742  mov     r9d, edi; char *
0x180018745  mov     r8, r14; unsigned int
0x180018748  mov     edx, 230h; void *
0x18001874d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018752  nop
0x180018753  mov     rcx, [rsp+250h+string]; string
0x180018758  call    cs:__imp_WindowsDeleteString
0x18001875e  mov     [rsp+250h+string], r13
0x180018763  lea     rcx, [rsp+250h+var_208]
0x180018768  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001876d  nop
0x18001876e  mov     byte ptr [rsp+250h+Buf1+8], r13b
0x180018773  lea     rcx, [rsp+250h+Buf1]
0x180018778  call    _lambda_ed01a7c2c5d72a51601480778acc1f76___operator__
0x18001877d  nop
0x18001877e  jmp     loc_180018570
0x180018783  mov     eax, r13d
0x180018786  cmp     [rsp+250h+var_200], 1
0x18001878b  setnz   al
0x18001878e  mov     [r12], eax
0x180018792  mov     rcx, [rsp+250h+var_1E0]
0x180018797  test    rcx, rcx
0x18001879a  jz      short loc_1800187AE
0x18001879c  mov     [rsp+250h+var_1E0], r13
0x1800187a1  mov     rax, [rcx]
0x1800187a4  mov     rax, [rax+10h]
  ... truncated ...
```
