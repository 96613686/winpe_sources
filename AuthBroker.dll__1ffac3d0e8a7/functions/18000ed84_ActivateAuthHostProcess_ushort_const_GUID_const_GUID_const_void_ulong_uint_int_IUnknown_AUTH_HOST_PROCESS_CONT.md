# ActivateAuthHostProcess(ushort const *,_GUID const &,_GUID const *,void *,ulong,uint,int,IUnknown * *,_AUTH_HOST_PROCESS_CONTEXT *)

- ea: `0x18000ed84`
- end: `0x18000f346`
- name: `?ActivateAuthHostProcess@@YAJPEBGAEBU_GUID@@PEBU1@PEAXKIHPEAPEAUIUnknown@@PEAU_AUTH_HOST_PROCESS_CONTEXT@@@Z`
- size: `1474`
- prototype: `__int64 __fastcall(wchar_t *applicationName, const _GUID *tokenHandle, const _GUID *dwProcessId, void *brokerFlags, unsigned int useSsoAppContainer, unsigned int authHostIUnknown, int processContext, IUnknown **applicationName_0, _AUTH_HOST_PROCESS_CONTEXT *authHostClsid)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001449c`

## callees

- `0x180003f40`
- `0x180004940`
- `0x1800053f8`
- `0x18000737c`
- `0x180007a68`
- `0x18000ed84`
- `0x18000f488`
- `0x18000fcfc`
- `0x18001009c`
- `0x1800109b8`
- `0x180010cac`
- `0x180010e58`
- `0x180011034`
- `0x180011264`
- `0x180011474`
- `0x1800204ee`
- `0x180020520`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000efe6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000efe6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f015`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f015`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f1c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000f1c7`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000efff`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000efff`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f1b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f1b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f059`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ef41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ef41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f04e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f04e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f1ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000ef58`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000ef58`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000f195`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000f195`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x18000f2ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstanceEx` at `0x18000f2ba`

## string_xrefs

- `0x18000ef8e`: `-AuthHostBrokerActivated `

## pseudocode

```c
__int64 __fastcall ActivateAuthHostProcess(
        wchar_t *applicationName,
        const _GUID *tokenHandle,
        const _GUID *dwProcessId,
        void *brokerFlags,
        unsigned int useSsoAppContainer,
        unsigned int authHostIUnknown,
        int processContext,
        IUnknown **applicationName_0,
        _AUTH_HOST_PROCESS_CONTEXT *authHostClsid)
{
  _AUTH_HOST_PROCESS_CONTEXT *v9; // r12
  void *v11; // r15
  int v12; // r14d
  void *v13; // r13
  unsigned int AuthHostRegDWORDValue; // edi
  signed int v15; // eax
  HRESULT hr; // ebx
  int v17; // eax
  WPP_PROJECT_CONTROL_BLOCK *v18; // rcx
  unsigned __int16 v19; // dx
  unsigned int v20; // r9d
  DWORD CurrentProcessId; // edi
  signed __int32 v22; // ebx
  unsigned int v23; // r10d
  HANDLE MutexW; // rax
  DWORD v25; // eax
  signed int LastError; // eax
  void **p_processHandle; // r12
  signed int AuthHostProcess; // eax
  WPP_PROJECT_CONTROL_BLOCK *v29; // rcx
  unsigned __int16 v30; // dx
  unsigned int v31; // r9d
  unsigned int v32; // edx
  int v34; // eax
  __int64 dwCount; // [rsp+20h] [rbp-E0h]
  MULTI_QI *pResults; // [rsp+28h] [rbp-D8h]
  int v37; // [rsp+40h] [rbp-C0h]
  unsigned int capabilityCount; // [rsp+50h] [rbp-B0h] BYREF
  void *appContainerSid; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *v40; // [rsp+60h] [rbp-A0h]
  IUnknown **v41; // [rsp+68h] [rbp-98h]
  tagMULTI_QI multiQi; // [rsp+70h] [rbp-90h] BYREF
  _AUTH_HOST_IMPERSONATE_CONTEXT impersonateContext; // [rsp+88h] [rbp-78h] BYREF
  _SID_AND_ATTRIBUTES capabilitySidAndAttributes[5]; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t authHostIdString[32]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t commandLineArg[264]; // [rsp+130h] [rbp+30h] BYREF

  v9 = authHostClsid;
  v40 = applicationName;
  v41 = applicationName_0;
  capabilitySidAndAttributes[0].Sid = 0;
  impersonateContext = 0;
  memset_0(&capabilitySidAndAttributes[0].Attributes, 0, 0x48u);
  *applicationName_0 = 0;
  capabilityCount = 0;
  appContainerSid = 0;
  v11 = 0;
  memset(&multiQi, 0, sizeof(multiQi));
  v12 = 0;
  v37 = 0;
  memset(authHostIdString, 0, 54);
  v13 = 0;
  *authHostClsid = 0;
  if ( IsDevelopmentMode(brokerFlags) )
    AuthHostRegDWORDValue = 1;
  else
    AuthHostRegDWORDValue = GetAuthHostRegDWORDValue(L"EnablePrivateNetwork");
  v15 = InitializeAuthHostCapabilitySidAndAttributes(
          authHostIUnknown,
          AuthHostRegDWORDValue,
          capabilitySidAndAttributes,
          &capabilityCount);
  hr = v15;
  if ( v15 >= 0 )
  {
    v17 = CreateAuthHostAppContainer(
            authHostIUnknown,
            processContext,
            AuthHostRegDWORDValue,
            capabilitySidAndAttributes,
            capabilityCount,
            &appContainerSid,
            &authHostClsid->appContainerIndex);
    hr = v17;
    if ( v17 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        v19 = 16;
        v20 = v17;
LABEL_15:
        WPP_SF_d(v18[1].Control.Logger, v19, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v20);
        v11 = appContainerSid;
        goto LABEL_9;
      }
      goto LABEL_80;
    }
    CurrentProcessId = GetCurrentProcessId();
    v22 = _InterlockedIncrement(&AuthHostCount);
    LODWORD(pResults) = GetTickCount();
    LODWORD(dwCount) = v22;
    hr = StringCchPrintfW(authHostIdString, 0x1Bu, L"%08x_%08x_%08x", CurrentProcessId, dwCount, pResults);
    if ( hr < 0
      || (hr = StringCchCopyW(commandLineArg, 0x104u, L"-AuthHostBrokerActivated "), hr < 0)
      || (hr = StringCchCatW(commandLineArg, v23, authHostIdString), hr < 0) )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        v19 = 17;
        v20 = hr;
        goto LABEL_15;
      }
LABEL_80:
      v11 = appContainerSid;
      goto $Exit_6;
    }
    if ( processContext )
    {
      AcquireSRWLockExclusive(&AuthHostSsoLock);
      v37 = 1;
      MutexW = CreateMutexW(0, 0, L"AuthHostAppContainerMutex.SSO");
      v13 = MutexW;
      if ( MutexW )
      {
        v25 = WaitForSingleObject(MutexW, 0x7D0u);
        if ( v25 )
        {
          if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
            && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
            && WPP_GLOBAL_Control[1].Control.Level >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0x12u, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v25);
          }
          CloseHandle(v13);
          v13 = 0;
        }
      }
      else
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
          && WPP_GLOBAL_Control[1].Control.Level >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control[1].Control.Logger,
            0x13u,
            WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
            LastError);
        }
      }
    }
    v11 = appContainerSid;
    p_processHandle = &authHostClsid->processHandle;
    AuthHostProcess = CreateAuthHostProcess(
                        v40,
                        commandLineArg,
                        appContainerSid,
                        capabilitySidAndAttributes,
                        capabilityCount,
                        useSsoAppContainer,
                        &authHostClsid->processHandle);
    hr = AuthHostProcess;
    if ( AuthHostProcess < 0 )
    {
      if ( !useSsoAppContainer )
        goto LABEL_40;
      if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
        && WPP_GLOBAL_Control[1].Control.Level >= 2u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control[1].Control.Logger,
          0x14u,
          WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids,
          AuthHostProcess);
      }
      hr = CreateAuthHostProcess(
             v40,
             commandLineArg,
             v11,
             capabilitySidAndAttributes,
             capabilityCount,
             0,
             p_processHandle);
      if ( hr < 0 )
      {
LABEL_40:
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0
          || WPP_GLOBAL_Control[1].Control.Level < 2u )
        {
          goto LABEL_46;
        }
        v30 = 21;
LABEL_44:
        v31 = hr;
LABEL_45:
        WPP_SF_d(v29[1].Control.Logger, v30, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v31);
LABEL_46:
        v9 = authHostClsid;
        v12 = v37;
        goto $Exit_6;
      }
    }
    v34 = _ImpersonateAuthHostProcess(*p_processHandle, &impersonateContext);
    hr = v34;
    if ( v34 >= 0 )
    {
      v34 = WaitForAuthHostProcessToRegister(v11, *p_processHandle, authHostIdString);
      hr = v34;
      if ( v34 >= 0 )
      {
        multiQi.pIID = &IID_IAuthHost;
        hr = CoCreateInstanceEx(&CLSID_AuthHostObject, 0, 0x100015u, 0, 1u, &multiQi);
        if ( hr >= 0 )
        {
          hr = multiQi.hr;
          if ( multiQi.hr >= 0 )
          {
            *v41 = multiQi.pItf;
            goto LABEL_46;
          }
        }
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
          || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0
          || WPP_GLOBAL_Control[1].Control.Level < 2u )
        {
          goto LABEL_46;
        }
        v30 = 24;
        goto LABEL_44;
      }
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto LABEL_46;
      }
      v30 = 23;
    }
    else
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
        || (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) == 0
        || WPP_GLOBAL_Control[1].Control.Level < 2u )
      {
        goto LABEL_46;
      }
      v30 = 22;
    }
    v31 = v34;
    goto LABEL_45;
  }
  if ( WPP_GLOBAL_Control != (WPP_PROJECT_CONTROL_BLOCK *)&WPP_GLOBAL_Control
    && (WPP_GLOBAL_Control[1].ReserveSpace[28] & 0x10) != 0
    && WPP_GLOBAL_Control[1].Control.Level >= 2u )
  {
    WPP_SF_d(WPP_GLOBAL_Control[1].Control.Logger, 0xFu, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids, v15);
LABEL_9:
    v12 = 0;
  }
$Exit_6:
  v32 = 5;
  if ( capabilityCount < 5 )
    v32 = capabilityCount;
  FreeAuthHostCapabilitySidAndAttributes(capabilitySidAndAttributes, v32);
  if ( v11 )
    FreeSid(v11);
  _RevertAuthHostProcessImpersonation(&impersonateContext);
  if ( v12 )
  {
    if ( v13 )
    {
      ReleaseMutex(v13);
      CloseHandle(v13);
    }
    ReleaseSRWLockExclusive(&AuthHostSsoLock);
  }
  if ( hr < 0 )
    ReleaseAuthHostProcess(v9);
  return (unsigned int)hr;
}

```

## disassembly

```asm
0x18000ed84  mov     [rsp-8+arg_8], rbx
0x18000ed89  push    rbp
0x18000ed8a  push    rsi
0x18000ed8b  push    rdi
0x18000ed8c  push    r12
0x18000ed8e  push    r13
0x18000ed90  push    r14
0x18000ed92  push    r15
0x18000ed94  lea     rbp, [rsp-250h]
0x18000ed9c  sub     rsp, 350h
0x18000eda3  mov     rax, cs:__security_cookie
0x18000edaa  xor     rax, rsp
0x18000edad  mov     [rbp+280h+var_40], rax
0x18000edb4  mov     rdi, [rbp+280h+applicationName_0]
0x18000edbb  xor     esi, esi
0x18000edbd  mov     r12, [rbp+280h+authHostClsid]
0x18000edc4  xorps   xmm0, xmm0
0x18000edc7  mov     [rsp+380h+var_320], applicationName
0x18000edcc  xor     edx, edx; Val
0x18000edce  lea     applicationName, [rbp+280h+capabilitySidAndAttributes.Attributes]; void *
0x18000edd2  mov     [rsp+380h+var_318], rdi
0x18000edd7  lea     r8d, [rsi+48h]; Size
0x18000eddb  mov     [rsp+380h+var_338], r12
0x18000ede0  mov     rbx, tokenHandle
0x18000ede3  mov     [rbp+280h+capabilitySidAndAttributes.Sid], rsi
0x18000ede7  movups  xmmword ptr [rbp+280h+impersonateContext.doRevert], xmm0
0x18000edeb  call    memset_0
0x18000edf0  xorps   xmm1, xmm1
0x18000edf3  mov     [rdi], rsi
0x18000edf6  xorps   xmm0, xmm0
0x18000edf9  mov     [rsp+380h+capabilityCount], esi
0x18000edfd  xor     eax, eax
0x18000edff  mov     [rsp+380h+appContainerSid], rsi
0x18000ee04  movups  xmmword ptr [rbp+280h+authHostIdString+20h], xmm1
0x18000ee08  mov     applicationName, rbx; clientTokenHandle
0x18000ee0b  mov     qword ptr [rbp+280h+authHostIdString+2Eh], rax
0x18000ee0f  mov     r15d, esi
0x18000ee12  mov     qword ptr [rbp+280h+multiQi.hr], rax
0x18000ee16  movups  xmmword ptr [rsp+380h+multiQi.pIID], xmm0
0x18000ee1b  mov     r14d, esi
0x18000ee1e  mov     [rsp+380h+var_340], esi
0x18000ee22  movups  xmmword ptr [rbp+280h+authHostIdString], xmm1
0x18000ee26  mov     r13d, esi
0x18000ee29  movups  xmmword ptr [rbp+280h+authHostIdString+10h], xmm1
0x18000ee2d  movups  xmmword ptr [r12], xmm0
0x18000ee32  call    _IsDevelopmentMode
0x18000ee37  test    eax, eax
0x18000ee39  jz      short loc_18000EE40
0x18000ee3b  lea     edi, [rsi+1]
0x18000ee3e  jmp     short loc_18000EE4E
0x18000ee40  lea     applicationName, aEnableprivaten; "EnablePrivateNetwork"
0x18000ee47  call    ?GetAuthHostRegDWORDValue@@YAKPEBG@Z; GetAuthHostRegDWORDValue(ushort const *)
0x18000ee4c  mov     edi, eax
0x18000ee4e  mov     ecx, [rbp+280h+arg_28]; brokerFlags
0x18000ee54  lea     tokenHandle, [rsp+380h+capabilityCount]; capabilityCount
0x18000ee59  lea     r8, [rbp+280h+capabilitySidAndAttributes]; capabilitySidAndAttributes
0x18000ee5d  mov     edx, edi; enablePrivateNetwork
0x18000ee5f  call    _InitializeAuthHostCapabilitySidAndAttributes
0x18000ee64  mov     ebx, eax
0x18000ee66  test    eax, eax
0x18000ee68  jns     short loc_18000EEB8
0x18000ee6a  mov     applicationName, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000ee71  lea     rsi, WPP_GLOBAL_Control
0x18000ee78  cmp     applicationName, rsi
0x18000ee7b  jz      $Exit_6
0x18000ee81  test    byte ptr [applicationName+44h], 10h
0x18000ee85  jz      $Exit_6
0x18000ee8b  mov     dil, 2
0x18000ee8e  cmp     [applicationName+41h], dil
0x18000ee92  jb      $Exit_6
0x18000ee98  mov     applicationName, [applicationName+38h]; Logger
0x18000ee9c  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x18000eea3  mov     edx, 0Fh; id
0x18000eea8  mov     r9d, eax; _a1
0x18000eeab  call    WPP_SF_d
0x18000eeb0  mov     r14d, r13d
0x18000eeb3  jmp     $Exit_6
0x18000eeb8  mov     r15d, [rbp+280h+arg_30]
0x18000eebf  lea     rax, [rsp+380h+appContainerSid]
0x18000eec4  mov     ecx, [rbp+280h+arg_28]; brokerFlags
0x18000eeca  lea     tokenHandle, [rbp+280h+capabilitySidAndAttributes]; capabilities
0x18000eece  mov     [rsp+380h+slotIndex], r12; slotIndex
0x18000eed3  mov     r8d, edi; enablePrivateNetwork
0x18000eed6  mov     [rsp+380h+pResults], rax; appContainerSid
0x18000eedb  mov     edx, r15d; useSsoAppContainer
0x18000eede  mov     eax, [rsp+380h+capabilityCount]
0x18000eee2  mov     dword ptr [rsp+380h+dwCount], eax; capabilityCount
0x18000eee6  call    _CreateAuthHostAppContainer
0x18000eeeb  mov     ebx, eax
0x18000eeed  test    eax, eax
0x18000eeef  jns     short loc_18000EF41
0x18000eef1  mov     applicationName, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000eef8  lea     rsi, WPP_GLOBAL_Control
0x18000eeff  cmp     applicationName, rsi
0x18000ef02  jz      loc_18000F33C
0x18000ef08  test    byte ptr [applicationName+44h], 10h
0x18000ef0c  jz      loc_18000F33C
0x18000ef12  mov     dil, 2
0x18000ef15  cmp     [applicationName+41h], dil
0x18000ef19  jb      loc_18000F33C
0x18000ef1f  mov     edx, 10h; id
0x18000ef24  mov     r9d, eax; _a1
0x18000ef27  mov     applicationName, [applicationName+38h]; Logger
0x18000ef2b  lea     r8, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids; TraceGuid
0x18000ef32  call    WPP_SF_d
0x18000ef37  mov     r15, [rsp+380h+appContainerSid]
0x18000ef3c  jmp     loc_18000EEB0
0x18000ef41  call    cs:__imp_GetCurrentProcessId
0x18000ef47  mov     edi, eax
0x18000ef49  mov     ebx, 1
0x18000ef4e  lock xadd cs:_AuthHostCount, ebx
0x18000ef56  inc     ebx
0x18000ef58  call    cs:__imp_GetTickCount
0x18000ef5e  mov     dword ptr [rsp+380h+pResults], eax
0x18000ef62  mov     r9d, edi
0x18000ef65  lea     r8, a08x08x08x; "%08x_%08x_%08x"
0x18000ef6c  mov     dword ptr [rsp+380h+dwCount], ebx
0x18000ef70  mov     edx, 1Bh; cchDest
0x18000ef75  lea     applicationName, [rbp+280h+authHostIdString]; pszDest
0x18000ef79  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000ef7e  mov     ebx, eax
0x18000ef80  test    eax, eax
0x18000ef82  js      loc_18000F30D
0x18000ef88  mov     r10d, 104h
0x18000ef8e  lea     r8, aAuthhostbroker; "-AuthHostBrokerActivated "
0x18000ef95  mov     edx, r10d; cchDest
0x18000ef98  lea     applicationName, [rbp+280h+commandLineArg]; pszDest
0x18000ef9c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000efa1  mov     ebx, eax
0x18000efa3  test    eax, eax
0x18000efa5  js      loc_18000F30D
0x18000efab  lea     r8, [rbp+280h+authHostIdString]; pszSrc
0x18000efaf  mov     edx, r10d; cchDest
0x18000efb2  lea     applicationName, [rbp+280h+commandLineArg]; pszDest
0x18000efb6  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000efbb  mov     ebx, eax
0x18000efbd  test    eax, eax
0x18000efbf  js      loc_18000F30D
0x18000efc5  lea     r14, WPP_2e67a773e415305932e36b9aa11a69b0_Traceguids
0x18000efcc  mov     dil, 2
0x18000efcf  lea     rsi, WPP_GLOBAL_Control
0x18000efd6  test    r15d, r15d
0x18000efd9  jz      loc_18000F097
0x18000efdf  lea     applicationName, _AuthHostSsoLock; SRWLock
0x18000efe6  call    cs:__imp_AcquireSRWLockExclusive
0x18000efec  lea     r8, aAuthhostappcon_0; "AuthHostAppContainerMutex.SSO"
0x18000eff3  mov     [rsp+380h+var_340], 1
0x18000effb  xor     edx, edx; bInitialOwner
0x18000effd  xor     ecx, ecx; lpMutexAttributes
0x18000efff  call    cs:__imp_CreateMutexW
0x18000f005  mov     r13, rax
0x18000f008  test    rax, rax
0x18000f00b  jz      short loc_18000F059
0x18000f00d  mov     edx, 7D0h; dwMilliseconds
0x18000f012  mov     applicationName, rax; hHandle
0x18000f015  call    cs:__imp_WaitForSingleObject
0x18000f01b  test    eax, eax
0x18000f01d  jz      short loc_18000F097
0x18000f01f  mov     applicationName, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000f026  cmp     applicationName, rsi
0x18000f029  jz      short loc_18000F04B
0x18000f02b  test    byte ptr [applicationName+44h], 10h
0x18000f02f  jz      short loc_18000F04B
0x18000f031  cmp     [applicationName+41h], dil
0x18000f035  jb      short loc_18000F04B
0x18000f037  mov     applicationName, [applicationName+38h]; Logger
0x18000f03b  mov     edx, 12h; id
0x18000f040  mov     r9d, eax; _a1
0x18000f043  mov     r8, r14; TraceGuid
0x18000f046  call    WPP_SF_d
0x18000f04b  mov     applicationName, r13; hObject
0x18000f04e  call    cs:__imp_CloseHandle
0x18000f054  xor     r13d, r13d
0x18000f057  jmp     short loc_18000F097
0x18000f059  call    cs:__imp_GetLastError
0x18000f05f  test    eax, eax
0x18000f061  jle     short loc_18000F06B
0x18000f063  movzx   eax, ax
0x18000f066  or      eax, 80070000h
0x18000f06b  mov     applicationName, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000f072  cmp     applicationName, rsi
0x18000f075  jz      short loc_18000F097
0x18000f077  test    byte ptr [applicationName+44h], 10h
0x18000f07b  jz      short loc_18000F097
0x18000f07d  cmp     [applicationName+41h], dil
0x18000f081  jb      short loc_18000F097
0x18000f083  mov     applicationName, [applicationName+38h]; Logger
0x18000f087  mov     edx, 13h; id
0x18000f08c  mov     r9d, eax; _a1
0x18000f08f  mov     r8, r14; TraceGuid
0x18000f092  call    WPP_SF_d
0x18000f097  mov     eax, [rbp+280h+clientProcessId]
0x18000f09d  lea     tokenHandle, [rbp+280h+capabilitySidAndAttributes]; capabilities
0x18000f0a1  mov     r15, [rsp+380h+appContainerSid]
0x18000f0a6  lea     rdx, [rbp+280h+commandLineArg]; commandLineArg
0x18000f0aa  mov     applicationName, [rsp+380h+var_320]; applicationName
0x18000f0af  add     r12, 8
0x18000f0b3  mov     [rsp+380h+slotIndex], r12; processHandle
0x18000f0b8  mov     r8, r15; appContainerSid
0x18000f0bb  mov     dword ptr [rsp+380h+pResults], eax; clientProcessId
0x18000f0bf  mov     eax, [rsp+380h+capabilityCount]
0x18000f0c3  mov     dword ptr [rsp+380h+dwCount], eax; capabilityCount
0x18000f0c7  call    _CreateAuthHostProcess
0x18000f0cc  mov     ebx, eax
0x18000f0ce  test    eax, eax
0x18000f0d0  jns     loc_18000F205
0x18000f0d6  cmp     [rbp+280h+clientProcessId], 0
0x18000f0dd  jz      short loc_18000F13F
0x18000f0df  mov     applicationName, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000f0e6  cmp     applicationName, rsi
0x18000f0e9  jz      short loc_18000F10B
0x18000f0eb  test    byte ptr [applicationName+44h], 10h
0x18000f0ef  jz      short loc_18000F10B
0x18000f0f1  cmp     [applicationName+41h], dil
0x18000f0f5  jb      short loc_18000F10B
0x18000f0f7  mov     applicationName, [applicationName+38h]; Logger
0x18000f0fb  mov     edx, 14h; id
0x18000f100  mov     r9d, eax; _a1
0x18000f103  mov     r8, r14; TraceGuid
0x18000f106  call    WPP_SF_d
0x18000f10b  mov     eax, [rsp+380h+capabilityCount]
0x18000f10f  lea     tokenHandle, [rbp+280h+capabilitySidAndAttributes]; capabilities
0x18000f113  mov     applicationName, [rsp+380h+var_320]; applicationName
0x18000f118  lea     rdx, [rbp+280h+commandLineArg]; commandLineArg
0x18000f11c  mov     [rsp+380h+slotIndex], r12; processHandle
0x18000f121  mov     r8, r15; appContainerSid
0x18000f124  mov     dword ptr [rsp+380h+pResults], 0; clientProcessId
0x18000f12c  mov     dword ptr [rsp+380h+dwCount], eax; capabilityCount
0x18000f130  call    _CreateAuthHostProcess
0x18000f135  mov     ebx, eax
0x18000f137  test    eax, eax
0x18000f139  jns     loc_18000F205
0x18000f13f  mov     applicationName, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000f146  cmp     applicationName, rsi
0x18000f149  jz      short loc_18000F16B
0x18000f14b  test    byte ptr [applicationName+44h], 10h
0x18000f14f  jz      short loc_18000F16B
0x18000f151  cmp     [applicationName+41h], dil
0x18000f155  jb      short loc_18000F16B
0x18000f157  mov     edx, 15h; id
0x18000f15c  mov     r9d, ebx; _a1
0x18000f15f  mov     applicationName, [applicationName+38h]; Logger
0x18000f163  mov     r8, r14; TraceGuid
0x18000f166  call    WPP_SF_d
0x18000f16b  mov     r12, [rsp+380h+var_338]
0x18000f170  mov     r14d, [rsp+380h+var_340]
0x18000f175  mov     eax, [rsp+380h+capabilityCount]
0x18000f179  mov     edx, 5
0x18000f17e  cmp     eax, edx
0x18000f180  jnb     short loc_18000F184
0x18000f182  mov     edx, eax; capabilityCount
0x18000f184  lea     applicationName, [rbp+280h+capabilitySidAndAttributes]; capabilitySidAndAttributes
0x18000f188  call    _FreeAuthHostCapabilitySidAndAttributes
0x18000f18d  test    r15, r15
0x18000f190  jz      short loc_18000F19B
0x18000f192  mov     applicationName, r15; pSid
0x18000f195  call    cs:__imp_FreeSid
0x18000f19b  lea     applicationName, [rbp+280h+impersonateContext]; impersonateContext
0x18000f19f  call    ?_RevertAuthHostProcessImpersonation@@YAJPEAU_AUTH_HOST_IMPERSONATE_CONTEXT@@@Z; _RevertAuthHostProcessImpersonation(_AUTH_HOST_IMPERSONATE_CONTEXT *)
0x18000f1a4  test    r14d, r14d
0x18000f1a7  jz      short loc_18000F1CD
0x18000f1a9  test    r13, r13
0x18000f1ac  jz      short loc_18000F1C0
0x18000f1ae  mov     applicationName, r13; hMutex
0x18000f1b1  call    cs:__imp_ReleaseMutex
0x18000f1b7  mov     applicationName, r13; hObject
0x18000f1ba  call    cs:__imp_CloseHandle
0x18000f1c0  lea     applicationName, _AuthHostSsoLock; SRWLock
0x18000f1c7  call    cs:__imp_ReleaseSRWLockExclusive
0x18000f1cd  test    ebx, ebx
0x18000f1cf  jns     short loc_18000F1D9
0x18000f1d1  mov     applicationName, r12; processContext
0x18000f1d4  call    ?ReleaseAuthHostProcess@@YAJPEAU_AUTH_HOST_PROCESS_CONTEXT@@@Z; ReleaseAuthHostProcess(_AUTH_HOST_PROCESS_CONTEXT *)
0x18000f1d9  mov     eax, ebx
0x18000f1db  mov     applicationName, [rbp+280h+var_40]
0x18000f1e2  xor     applicationName, rsp; StackCookie
0x18000f1e5  call    __security_check_cookie
0x18000f1ea  mov     rbx, [rsp+380h+arg_8]
0x18000f1f2  add     rsp, 350h
0x18000f1f9  pop     r15
0x18000f1fb  pop     r14
0x18000f1fd  pop     r13
0x18000f1ff  pop     r12
0x18000f201  pop     rdi
0x18000f202  pop     rsi
0x18000f203  pop     rbp
0x18000f204  retn
0x18000f205  mov     applicationName, [r12]; processHandle
0x18000f209  lea     rdx, [rbp+280h+impersonateContext]; impersonateContext
0x18000f20d  call    ?_ImpersonateAuthHostProcess@@YAJPEAXPEAU_AUTH_HOST_IMPERSONATE_CONTEXT@@@Z; _ImpersonateAuthHostProcess(void *,_AUTH_HOST_IMPERSONATE_CONTEXT *)
0x18000f212  mov     ebx, eax
0x18000f214  test    eax, eax
0x18000f216  jns     short loc_18000F249
0x18000f218  mov     applicationName, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18000f21f  cmp     applicationName, rsi
0x18000f222  jz      loc_18000F16B
0x18000f228  test    byte ptr [applicationName+44h], 10h
0x18000f22c  jz      loc_18000F16B
0x18000f232  cmp     [applicationName+41h], dil
0x18000f236  jb      loc_18000F16B
  ... truncated ...
```
