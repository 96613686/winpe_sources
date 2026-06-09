# ShieldProvider::ShieldProcessLauncher::TurnTimeServiceOn(void)

- ea: `0x18007e610`
- end: `0x18007ec99`
- name: `?TurnTimeServiceOn@ShieldProcessLauncher@ShieldProvider@@UEAAJXZ`
- size: `1673`
- prototype: `__int64 __fastcall(ShieldProvider::ShieldProcessLauncher *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180001a1c`
- `0x180002244`
- `0x180002cf0`
- `0x180004710`
- `0x18000517c`
- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x18007e610`
- `0x1800df118`
- `0x1800e3e20`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007e708`
- `KERNEL32!GetLastError` at `0x18007e81d`
- `KERNEL32!GetLastError` at `0x18007e889`
- `KERNEL32!GetLastError` at `0x18007e916`
- `KERNEL32!GetLastError` at `0x18007e9b6`
- `KERNEL32!GetLastError` at `0x18007ea9f`
- `KERNEL32!GetLastError` at `0x18007eaf6`
- `KERNEL32!GetLastError` at `0x18007e708`
- `KERNEL32!GetLastError` at `0x18007e81d`
- `KERNEL32!GetLastError` at `0x18007e889`
- `KERNEL32!GetLastError` at `0x18007e916`
- `KERNEL32!GetLastError` at `0x18007e9b6`
- `KERNEL32!GetLastError` at `0x18007ea9f`
- `KERNEL32!GetLastError` at `0x18007eaf6`
- `KERNEL32!CloseHandle` at `0x18007e7cf`
- `KERNEL32!CloseHandle` at `0x18007e7f0`
- `KERNEL32!CloseHandle` at `0x18007e7cf`
- `KERNEL32!CloseHandle` at `0x18007e7f0`
- `KERNEL32!GetCurrentThread` at `0x18007e6e3`
- `KERNEL32!GetCurrentThread` at `0x18007e6e3`
- `KERNEL32!SleepEx` at `0x18007eb41`
- `KERNEL32!SleepEx` at `0x18007eb41`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007e6f8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18007e6f8`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18007e87b`
- `api-ms-win-service-management-l1-1-0!OpenServiceW` at `0x18007e87b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007e8d8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007e969`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007ec0b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007ec19`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007ec5f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007ec6d`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007e8d8`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007e969`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007ec0b`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007ec19`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007ec5f`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18007ec6d`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18007e80f`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18007e80f`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18007eaec`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x18007eaec`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18007e90c`
- `api-ms-win-service-management-l2-1-0!QueryServiceConfigW` at `0x18007e90c`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18007ea5c`
- `api-ms-win-service-management-l2-1-0!NotifyServiceStatusChangeW` at `0x18007ea5c`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18007e9ac`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfigW` at `0x18007e9ac`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18007ea09`
- `api-ms-win-service-winsvc-l1-1-0!QueryServiceStatus` at `0x18007ea09`

## string_xrefs

- `0x18007e806`: `ServicesActive`
- `0x18007e647`: `TimeServiceAssessment`

## pseudocode

```c
__int64 __fastcall ShieldProvider::ShieldProcessLauncher::TurnTimeServiceOn(
        ShieldProvider::ShieldProcessLauncher *this)
{
  int v1; // ecx
  int v2; // r8d
  int v3; // r9d
  signed int v4; // ebx
  HANDLE CurrentThread; // rax
  void *v6; // r8
  unsigned int v7; // r9d
  signed int LastError; // eax
  _QWORD *v9; // rax
  __int64 v10; // rdx
  int v11; // eax
  __int64 v12; // rcx
  __int64 v13; // r9
  SC_HANDLE v15; // rbx
  signed int v16; // eax
  unsigned int v17; // edi
  SC_HANDLE v18; // rdi
  signed int v19; // eax
  signed int v20; // esi
  signed int v21; // eax
  _QWORD *v22; // rax
  __int64 v23; // rdx
  signed int v24; // eax
  signed int v25; // eax
  signed int v26; // eax
  signed int v27; // eax
  _QWORD *v28; // rax
  __int64 v29; // rdx
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  unsigned int lpBinaryPathName; // [rsp+20h] [rbp-E0h]
  _BYTE v34[8]; // [rsp+60h] [rbp-A0h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v36[2]; // [rsp+70h] [rbp-90h] BYREF
  DWORD pcbBytesNeeded; // [rsp+78h] [rbp-88h] BYREF
  SERVICE_NOTIFY_2W pNotifyBuffer; // [rsp+80h] [rbp-80h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+D0h] [rbp-30h] BYREF
  struct _QUERY_SERVICE_CONFIGW ServiceConfig; // [rsp+F0h] [rbp-10h] BYREF

  if ( (unsigned int)dword_18012F2B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18012F2B8, 0x400000000000LL) )
  {
    *(_QWORD *)v36 = L"TimeServiceAssessment";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
      v1,
      (unsigned int)byte_180122179,
      v2,
      v3,
      (__int64)v36);
  }
  *(_QWORD *)v36 = 0;
  v4 = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(v36);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        28,
        WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids,
        (unsigned int)v4);
LABEL_27:
    CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(v36);
    return (unsigned int)v4;
  }
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 8u, 0, &TokenHandle) )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      v9 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v10 = 29;
LABEL_23:
        v12 = v9[2];
        v13 = (unsigned int)v4;
        goto LABEL_24;
      }
      goto LABEL_25;
    }
  }
  v34[0] = 0;
  v11 = CommonUtil::UtilCheckTokenMembershipByRid((CommonUtil *)v34, (bool *)TokenHandle, v6, v7, lpBinaryPathName);
  v4 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v10 = 30;
      v13 = (unsigned int)v11;
LABEL_24:
      WPP_SF_d(v12, v10, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids, v13);
      goto LABEL_25;
    }
    goto LABEL_25;
  }
  if ( !v34[0] )
  {
    v9 = WPP_GLOBAL_Control;
    v4 = -2147024891;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v10 = 31;
      goto LABEL_23;
    }
LABEL_25:
    if ( TokenHandle )
      CloseHandle(TokenHandle);
    goto LABEL_27;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(v36);
  v15 = OpenSCManagerW(0, L"ServicesActive", 5u);
  if ( !v15 )
  {
    v16 = GetLastError();
    v17 = v16;
    if ( v16 > 0 )
      v17 = (unsigned __int16)v16 | 0x80070000;
    if ( (v17 & 0x80000000) != 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids, v17);
      return v17;
    }
  }
  v18 = OpenServiceW(v15, L"w32time", 0x17u);
  if ( !v18 )
  {
    v19 = GetLastError();
    v20 = v19;
    if ( v19 > 0 )
      v20 = (unsigned __int16)v19 | 0x80070000;
    if ( v20 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          33,
          WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids,
          (unsigned int)v20);
LABEL_45:
      if ( v15 )
        CloseServiceHandle(v15);
      return (unsigned int)v20;
    }
  }
  memset_0(&ServiceConfig, 0, 0x2000u);
  pcbBytesNeeded = 0;
  if ( !QueryServiceConfigW(v18, &ServiceConfig, 0x2000u, &pcbBytesNeeded) )
  {
    v21 = GetLastError();
    v20 = v21;
    if ( v21 > 0 )
      v20 = (unsigned __int16)v21 | 0x80070000;
    if ( v20 < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v23 = 34;
LABEL_55:
        WPP_SF_d(v22[2], v23, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids, (unsigned int)v20);
        goto LABEL_56;
      }
      goto LABEL_56;
    }
  }
  if ( ServiceConfig.dwStartType == 4 && !ChangeServiceConfigW(v18, 0xFFFFFFFF, 3u, 0xFFFFFFFF, 0, 0, 0, 0, 0, 0, 0) )
  {
    v24 = GetLastError();
    v20 = v24;
    if ( v24 > 0 )
      v20 = (unsigned __int16)v24 | 0x80070000;
    if ( v20 < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v23 = 35;
        goto LABEL_55;
      }
LABEL_56:
      if ( v18 )
        CloseServiceHandle(v18);
      goto LABEL_45;
    }
  }
  memset(&ServiceStatus, 0, sizeof(ServiceStatus));
  if ( QueryServiceStatus(v18, &ServiceStatus) )
  {
    v20 = 0;
  }
  else
  {
    v26 = GetLastError();
    v20 = v26;
    if ( v26 > 0 )
      v20 = (unsigned __int16)v26 | 0x80070000;
    if ( v20 < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v23 = 36;
        goto LABEL_55;
      }
      goto LABEL_56;
    }
  }
  if ( ((ServiceStatus.dwCurrentState - 2) & 0xFFFFFFFD) != 0 )
  {
    memset_0(&pNotifyBuffer, 0, sizeof(pNotifyBuffer));
    pNotifyBuffer.dwVersion = 2;
    pNotifyBuffer.pfnNotifyCallback = (PFN_SC_NOTIFY_CALLBACK)wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy;
    pNotifyBuffer.pContext = 0;
    v25 = NotifyServiceStatusChangeW(v18, 8u, &pNotifyBuffer);
    v20 = v25;
    if ( v25 )
    {
      if ( v25 > 0 )
        v20 = (unsigned __int16)v25 | 0x80070000;
      if ( v20 < 0 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v23 = 37;
          goto LABEL_55;
        }
        goto LABEL_56;
      }
    }
    if ( !StartServiceW(v18, 0, 0) )
    {
      v27 = GetLastError();
      v20 = v27;
      if ( v27 > 0 )
        v20 = (unsigned __int16)v27 | 0x80070000;
      if ( v20 < 0 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v23 = 38;
          goto LABEL_55;
        }
        goto LABEL_56;
      }
    }
    if ( !SleepEx(0x1388u, 1) )
    {
      v22 = WPP_GLOBAL_Control;
      v20 = -2147023436;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v23 = 39;
        goto LABEL_55;
      }
      goto LABEL_56;
    }
    if ( pNotifyBuffer.dwNotificationStatus )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_111;
      v29 = 40;
LABEL_110:
      WPP_SF_d(v28[2], v29, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids, 2147500037LL);
LABEL_111:
      if ( v18 )
        CloseServiceHandle(v18);
      if ( v15 )
        CloseServiceHandle(v15);
      return 2147500037LL;
    }
    if ( pNotifyBuffer.ServiceStatus.dwCurrentState != 4 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_111;
      v29 = 41;
      goto LABEL_110;
    }
    v20 = 0;
  }
  if ( (unsigned int)dword_18012F2B8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18012F2B8, 0x400000000000LL) )
  {
    LODWORD(TokenHandle) = v20;
    *(_QWORD *)v36 = L"TimeServiceAssessment";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)&byte_180122137,
      v31,
      v32,
      (__int64)v36,
      (__int64)&TokenHandle);
  }
  if ( v18 )
    CloseServiceHandle(v18);
  if ( v15 )
    CloseServiceHandle(v15);
  return 0;
}

```

## disassembly

```asm
0x18007e610  push    rbp
0x18007e612  push    rbx
0x18007e613  push    rsi
0x18007e614  push    rdi
0x18007e615  push    r12
0x18007e617  push    r14
0x18007e619  push    r15
0x18007e61b  lea     rbp, [rsp-2000h]
0x18007e623  mov     eax, 2100h
0x18007e628  call    _alloca_probe
0x18007e62d  sub     rsp, rax
0x18007e630  mov     rax, cs:__security_cookie
0x18007e637  xor     rax, rsp
0x18007e63a  mov     [rbp+2030h+var_40], rax
0x18007e641  mov     eax, cs:dword_18012F2B8
0x18007e647  lea     r12, aTimeserviceass; "TimeServiceAssessment"
0x18007e64e  xor     r14d, r14d
0x18007e651  cmp     eax, 5
0x18007e654  jbe     short loc_18007E68B
0x18007e656  mov     rdx, 400000000000h
0x18007e660  lea     rcx, dword_18012F2B8
0x18007e667  call    _tlgKeywordOn
0x18007e66c  test    al, al
0x18007e66e  jz      short loc_18007E68B
0x18007e670  lea     rax, [rsp+2130h+var_20C0]
0x18007e675  mov     qword ptr [rsp+2130h+var_20C0], r12
0x18007e67a  lea     rdx, byte_180122179
0x18007e681  mov     [rsp+2130h+lpBinaryPathName], rax; unsigned int
0x18007e686  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x18007e68b  lea     rcx, [rsp+2130h+var_20C0]
0x18007e690  mov     qword ptr [rsp+2130h+var_20C0], r14
0x18007e695  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x18007e69a  mov     ebx, eax
0x18007e69c  test    eax, eax
0x18007e69e  jns     short loc_18007E6DE
0x18007e6a0  mov     rax, cs:WPP_GLOBAL_Control
0x18007e6a7  lea     rcx, WPP_GLOBAL_Control
0x18007e6ae  cmp     rax, rcx
0x18007e6b1  jz      loc_18007E7D5
0x18007e6b7  test    byte ptr [rax+1Ch], 1
0x18007e6bb  jz      loc_18007E7D5
0x18007e6c1  mov     rcx, [rax+10h]
0x18007e6c5  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007e6cc  mov     edx, 1Ch
0x18007e6d1  mov     r9d, ebx
0x18007e6d4  call    WPP_SF_d
0x18007e6d9  jmp     loc_18007E7D5
0x18007e6de  mov     [rsp+2130h+TokenHandle], r14
0x18007e6e3  call    cs:__imp_GetCurrentThread
0x18007e6e9  xor     r8d, r8d; OpenAsSelf
0x18007e6ec  lea     r9, [rsp+2130h+TokenHandle]; TokenHandle
0x18007e6f1  mov     rcx, rax; ThreadHandle
0x18007e6f4  lea     edx, [r8+8]; DesiredAccess
0x18007e6f8  call    cs:__imp_OpenThreadToken
0x18007e6fe  mov     r15d, 80070000h
0x18007e704  test    eax, eax
0x18007e706  jnz     short loc_18007E746
0x18007e708  call    cs:__imp_GetLastError
0x18007e70e  mov     ebx, eax
0x18007e710  test    eax, eax
0x18007e712  jle     short loc_18007E71A
0x18007e714  movzx   ebx, ax
0x18007e717  or      ebx, r15d
0x18007e71a  test    ebx, ebx
0x18007e71c  jns     short loc_18007E746
0x18007e71e  mov     rax, cs:WPP_GLOBAL_Control
0x18007e725  lea     rcx, WPP_GLOBAL_Control
0x18007e72c  cmp     rax, rcx
0x18007e72f  jz      loc_18007E7C5
0x18007e735  test    byte ptr [rax+1Ch], 1
0x18007e739  jz      loc_18007E7C5
0x18007e73f  mov     edx, 1Dh
0x18007e744  jmp     short loc_18007E7B2
0x18007e746  mov     rdx, [rsp+2130h+TokenHandle]; bool *
0x18007e74b  lea     rcx, [rsp+2130h+var_20D0]; this
0x18007e750  mov     [rsp+2130h+var_20D0], r14b
0x18007e755  call    ?UtilCheckTokenMembershipByRid@CommonUtil@@YAJPEA_NPEAXKK@Z; CommonUtil::UtilCheckTokenMembershipByRid(bool *,void *,ulong,ulong)
0x18007e75a  mov     ebx, eax
0x18007e75c  test    eax, eax
0x18007e75e  jns     short loc_18007E788
0x18007e760  mov     r10, cs:WPP_GLOBAL_Control
0x18007e767  lea     rcx, WPP_GLOBAL_Control
0x18007e76e  cmp     r10, rcx
0x18007e771  jz      short loc_18007E7C5
0x18007e773  test    byte ptr [r10+1Ch], 1
0x18007e778  jz      short loc_18007E7C5
0x18007e77a  mov     rcx, [r10+10h]
0x18007e77e  mov     edx, 1Eh
0x18007e783  mov     r9d, eax
0x18007e786  jmp     short loc_18007E7B9
0x18007e788  cmp     [rsp+2130h+var_20D0], r14b
0x18007e78d  jnz     short loc_18007E7E6
0x18007e78f  mov     rax, cs:WPP_GLOBAL_Control
0x18007e796  lea     rcx, WPP_GLOBAL_Control
0x18007e79d  mov     ebx, 80070005h
0x18007e7a2  cmp     rax, rcx
0x18007e7a5  jz      short loc_18007E7C5
0x18007e7a7  test    byte ptr [rax+1Ch], 1
0x18007e7ab  jz      short loc_18007E7C5
0x18007e7ad  mov     edx, 1Fh
0x18007e7b2  mov     rcx, [rax+10h]
0x18007e7b6  mov     r9d, ebx
0x18007e7b9  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007e7c0  call    WPP_SF_d
0x18007e7c5  mov     rcx, [rsp+2130h+TokenHandle]; hObject
0x18007e7ca  test    rcx, rcx
0x18007e7cd  jz      short loc_18007E7D5
0x18007e7cf  call    cs:__imp_CloseHandle
0x18007e7d5  lea     rcx, [rsp+2130h+var_20C0]
0x18007e7da  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x18007e7df  mov     eax, ebx
0x18007e7e1  jmp     loc_18007EC78
0x18007e7e6  mov     rcx, [rsp+2130h+TokenHandle]; hObject
0x18007e7eb  test    rcx, rcx
0x18007e7ee  jz      short loc_18007E7F6
0x18007e7f0  call    cs:__imp_CloseHandle
0x18007e7f6  lea     rcx, [rsp+2130h+var_20C0]
0x18007e7fb  call    ??1?$AutoRef@VAssessmentQueueItem@HealthAdvisor@WSD@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(void)
0x18007e800  mov     r8d, 5; dwDesiredAccess
0x18007e806  lea     rdx, DatabaseName; "ServicesActive"
0x18007e80d  xor     ecx, ecx; lpMachineName
0x18007e80f  call    cs:__imp_OpenSCManagerW
0x18007e815  mov     rbx, rax
0x18007e818  test    rax, rax
0x18007e81b  jnz     short loc_18007E86B
0x18007e81d  call    cs:__imp_GetLastError
0x18007e823  mov     edi, eax
0x18007e825  test    eax, eax
0x18007e827  jle     short loc_18007E82F
0x18007e829  movzx   edi, ax
0x18007e82c  or      edi, r15d
0x18007e82f  test    edi, edi
0x18007e831  jns     short loc_18007E86B
0x18007e833  mov     rax, cs:WPP_GLOBAL_Control
0x18007e83a  lea     rcx, WPP_GLOBAL_Control
0x18007e841  cmp     rax, rcx
0x18007e844  jz      short loc_18007E864
0x18007e846  test    byte ptr [rax+1Ch], 1
0x18007e84a  jz      short loc_18007E864
0x18007e84c  mov     rcx, [rax+10h]
0x18007e850  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007e857  mov     edx, 20h ; ' '
0x18007e85c  mov     r9d, edi
0x18007e85f  call    WPP_SF_d
0x18007e864  mov     eax, edi
0x18007e866  jmp     loc_18007EC78
0x18007e86b  mov     r8d, 17h; dwDesiredAccess
0x18007e871  lea     rdx, ServiceName; "w32time"
0x18007e878  mov     rcx, rbx; hSCManager
0x18007e87b  call    cs:__imp_OpenServiceW
0x18007e881  mov     rdi, rax
0x18007e884  test    rax, rax
0x18007e887  jnz     short loc_18007E8E5
0x18007e889  call    cs:__imp_GetLastError
0x18007e88f  mov     esi, eax
0x18007e891  test    eax, eax
0x18007e893  jle     short loc_18007E89B
0x18007e895  movzx   esi, ax
0x18007e898  or      esi, r15d
0x18007e89b  test    esi, esi
0x18007e89d  jns     short loc_18007E8E5
0x18007e89f  mov     rax, cs:WPP_GLOBAL_Control
0x18007e8a6  lea     rcx, WPP_GLOBAL_Control
0x18007e8ad  cmp     rax, rcx
0x18007e8b0  jz      short loc_18007E8D0
0x18007e8b2  test    byte ptr [rax+1Ch], 1
0x18007e8b6  jz      short loc_18007E8D0
0x18007e8b8  mov     rcx, [rax+10h]
0x18007e8bc  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007e8c3  mov     edx, 21h ; '!'
0x18007e8c8  mov     r9d, esi
0x18007e8cb  call    WPP_SF_d
0x18007e8d0  test    rbx, rbx
0x18007e8d3  jz      short loc_18007E8DE
0x18007e8d5  mov     rcx, rbx; hSCObject
0x18007e8d8  call    cs:__imp_CloseServiceHandle
0x18007e8de  mov     eax, esi
0x18007e8e0  jmp     loc_18007EC78
0x18007e8e5  mov     esi, 2000h
0x18007e8ea  lea     rcx, [rbp+2030h+ServiceConfig]; void *
0x18007e8ee  mov     r8d, esi; Size
0x18007e8f1  xor     edx, edx; Val
0x18007e8f3  call    memset_0
0x18007e8f8  lea     r9, [rsp+2130h+pcbBytesNeeded]; pcbBytesNeeded
0x18007e8fd  mov     [rsp+2130h+pcbBytesNeeded], r14d
0x18007e902  mov     r8d, esi; cbBufSize
0x18007e905  lea     rdx, [rbp+2030h+ServiceConfig]; lpServiceConfig
0x18007e909  mov     rcx, rdi; hService
0x18007e90c  call    cs:__imp_QueryServiceConfigW
0x18007e912  test    eax, eax
0x18007e914  jnz     short loc_18007E974
0x18007e916  call    cs:__imp_GetLastError
0x18007e91c  mov     esi, eax
0x18007e91e  test    eax, eax
0x18007e920  jle     short loc_18007E928
0x18007e922  movzx   esi, ax
0x18007e925  or      esi, r15d
0x18007e928  test    esi, esi
0x18007e92a  jns     short loc_18007E974
0x18007e92c  mov     rax, cs:WPP_GLOBAL_Control
0x18007e933  lea     rcx, WPP_GLOBAL_Control
0x18007e93a  cmp     rax, rcx
0x18007e93d  jz      short loc_18007E95D
0x18007e93f  test    byte ptr [rax+1Ch], 1
0x18007e943  jz      short loc_18007E95D
0x18007e945  mov     edx, 22h ; '"'
0x18007e94a  mov     rcx, [rax+10h]
0x18007e94e  lea     r8, WPP_e1d6bb52c6223884ab5d8dc0c510db61_Traceguids
0x18007e955  mov     r9d, esi
0x18007e958  call    WPP_SF_d
0x18007e95d  test    rdi, rdi
0x18007e960  jz      loc_18007E8D0
0x18007e966  mov     rcx, rdi; hSCObject
0x18007e969  call    cs:__imp_CloseServiceHandle
0x18007e96f  jmp     loc_18007E8D0
0x18007e974  cmp     [rbp+2030h+ServiceConfig.dwStartType], 4
0x18007e978  jnz     short loc_18007E9F7
0x18007e97a  mov     [rsp+2130h+lpDisplayName], r14; lpDisplayName
0x18007e97f  or      edx, 0FFFFFFFFh; dwServiceType
0x18007e982  mov     [rsp+2130h+lpPassword], r14; lpPassword
0x18007e987  mov     r9d, edx; dwErrorControl
0x18007e98a  mov     [rsp+2130h+lpServiceStartName], r14; lpServiceStartName
0x18007e98f  mov     r8d, 3; dwStartType
0x18007e995  mov     [rsp+2130h+lpDependencies], r14; lpDependencies
0x18007e99a  mov     rcx, rdi; hService
0x18007e99d  mov     [rsp+2130h+lpdwTagId], r14; lpdwTagId
0x18007e9a2  mov     [rsp+2130h+lpLoadOrderGroup], r14; lpLoadOrderGroup
0x18007e9a7  mov     [rsp+2130h+lpBinaryPathName], r14; lpBinaryPathName
0x18007e9ac  call    cs:__imp_ChangeServiceConfigW
0x18007e9b2  test    eax, eax
0x18007e9b4  jnz     short loc_18007E9F7
0x18007e9b6  call    cs:__imp_GetLastError
0x18007e9bc  mov     esi, eax
0x18007e9be  test    eax, eax
0x18007e9c0  jle     short loc_18007E9C8
0x18007e9c2  movzx   esi, ax
0x18007e9c5  or      esi, r15d
0x18007e9c8  test    esi, esi
0x18007e9ca  jns     short loc_18007E9F7
0x18007e9cc  mov     rax, cs:WPP_GLOBAL_Control
0x18007e9d3  lea     rcx, WPP_GLOBAL_Control
0x18007e9da  cmp     rax, rcx
0x18007e9dd  jz      loc_18007E95D
0x18007e9e3  test    byte ptr [rax+1Ch], 1
0x18007e9e7  jz      loc_18007E95D
0x18007e9ed  mov     edx, 23h ; '#'
0x18007e9f2  jmp     loc_18007E94A
0x18007e9f7  xorps   xmm0, xmm0
0x18007e9fa  lea     rdx, [rbp+2030h+ServiceStatus]; lpServiceStatus
0x18007e9fe  movups  xmmword ptr [rbp+2030h+ServiceStatus.dwServiceType], xmm0
0x18007ea02  mov     rcx, rdi; hService
0x18007ea05  movups  xmmword ptr [rbp+2030h+ServiceStatus.dwWin32ExitCode], xmm0
0x18007ea09  call    cs:__imp_QueryServiceStatus
0x18007ea0f  test    eax, eax
0x18007ea11  jz      loc_18007EA9F
0x18007ea17  mov     esi, r14d
0x18007ea1a  mov     eax, [rbp+2030h+ServiceStatus.dwCurrentState]
0x18007ea1d  add     eax, 0FFFFFFFEh
0x18007ea20  test    eax, 0FFFFFFFDh
0x18007ea25  jz      loc_18007EBB5
0x18007ea2b  xor     edx, edx; Val
0x18007ea2d  lea     rcx, [rbp+2030h+pNotifyBuffer]; void *
0x18007ea31  lea     r8d, [rdx+50h]; Size
0x18007ea35  call    memset_0
0x18007ea3a  lea     rax, ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
0x18007ea41  mov     [rbp+2030h+pNotifyBuffer.dwVersion], 2
0x18007ea48  lea     r8, [rbp+2030h+pNotifyBuffer]; pNotifyBuffer
0x18007ea4c  mov     [rbp+2030h+pNotifyBuffer.pfnNotifyCallback], rax
0x18007ea50  mov     edx, 8; dwNotifyMask
0x18007ea55  mov     [rbp+2030h+pNotifyBuffer.pContext], r14
0x18007ea59  mov     rcx, rdi; hService
0x18007ea5c  call    cs:__imp_NotifyServiceStatusChangeW
0x18007ea62  mov     esi, eax
0x18007ea64  test    eax, eax
0x18007ea66  jz      short loc_18007EAE4
0x18007ea68  jle     short loc_18007EA70
0x18007ea6a  movzx   esi, ax
0x18007ea6d  or      esi, r15d
0x18007ea70  test    esi, esi
0x18007ea72  jns     short loc_18007EAE4
0x18007ea74  mov     rax, cs:WPP_GLOBAL_Control
0x18007ea7b  lea     rcx, WPP_GLOBAL_Control
0x18007ea82  cmp     rax, rcx
0x18007ea85  jz      loc_18007E95D
0x18007ea8b  test    byte ptr [rax+1Ch], 1
0x18007ea8f  jz      loc_18007E95D
0x18007ea95  mov     edx, 25h ; '%'
0x18007ea9a  jmp     loc_18007E94A
0x18007ea9f  call    cs:__imp_GetLastError
0x18007eaa5  mov     esi, eax
0x18007eaa7  test    eax, eax
0x18007eaa9  jle     short loc_18007EAB1
0x18007eaab  movzx   esi, ax
0x18007eaae  or      esi, r15d
0x18007eab1  test    esi, esi
0x18007eab3  jns     loc_18007EA1A
0x18007eab9  mov     rax, cs:WPP_GLOBAL_Control
0x18007eac0  lea     rcx, WPP_GLOBAL_Control
0x18007eac7  cmp     rax, rcx
0x18007eaca  jz      loc_18007E95D
  ... truncated ...
```
