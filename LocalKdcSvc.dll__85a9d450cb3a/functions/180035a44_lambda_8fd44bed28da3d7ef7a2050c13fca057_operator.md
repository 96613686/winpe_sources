# _lambda_8fd44bed28da3d7ef7a2050c13fca057_::operator()

- ea: `0x180035a44`
- end: `0x180035ebf`
- name: `_lambda_8fd44bed28da3d7ef7a2050c13fca057_::operator()`
- size: `1147`
- prototype: ``
- caller_count: `2`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180034ff4`
- `0x18003a5fc`

## callees

- `0x180002ad0`
- `0x1800038fc`
- `0x180003908`
- `0x1800101c4`
- `0x1800101ec`
- `0x180035a44`
- `0x1800364c4`
- `0x18003669c`
- `0x1800373d4`
- `0x18003b5d8`
- `0x18004026c`
- `0x1800402c4`
- `0x180052cfc`
- `0x1800579e0`
- `0x18005a090`
- `0x1800719c8`
- `0x18007345c`
- `0x180079bf4`
- `0x180079ee4`
- `0x18007c5ec`
- `0x18007db8c`
- `0x18007dc20`
- `0x180083da8`
- `0x18009c010`

## import_xrefs

- `Kerberos!KerbKdcCallBack` at `0x180035a6a`
- `Kerberos!KerbKdcCallBack` at `0x180035a6a`
- `Kerb3961!__imp_GetDomainCipherPolicy` at `0x180035dfe`
- `Kerb3961!__imp_GetDomainCipherPolicy` at `0x180035dfe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180035df8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180035df8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180035e65`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180035e65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035be7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035be7`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180035e76`
- `api-ms-win-core-processthreads-l1-1-0!TlsFree` at `0x180035e76`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035b91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035c87`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035b91`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180035c87`
- `WS2_32!__imp_WSACleanup` at `0x180035d67`
- `WS2_32!__imp_WSACleanup` at `0x180035d67`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180035cc8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180035cc8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180035b1f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x180035b1f`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180035dc4`
- `api-ms-win-security-cryptoapi-l1-1-0!CryptReleaseContext` at `0x180035dc4`
- `ntdll!EtwUnregisterTraceGuids` at `0x180035d8b`
- `ntdll!EtwUnregisterTraceGuids` at `0x180035d8b`
- `ntdll!RtlDeleteResource` at `0x180035a93`
- `ntdll!RtlDeleteResource` at `0x180035a93`
- `ntdll!RtlNtStatusToDosError` at `0x180035ced`
- `ntdll!RtlNtStatusToDosError` at `0x180035ced`
- `LSASRV!LsaIKerberosRegisterTrustNotification` at `0x180035ab7`
- `LSASRV!LsaIKerberosRegisterTrustNotification` at `0x180035ab7`
- `LSASRV!LsaIUnregisterAllPolicyChangeNotificationCallback` at `0x180035ac4`
- `LSASRV!LsaIUnregisterAllPolicyChangeNotificationCallback` at `0x180035ac4`
- `NETLOGON!I_NetLogonSetServiceBits` at `0x180035ad5`
- `NETLOGON!I_NetLogonSetServiceBits` at `0x180035ad5`
- `AUTHZ!AuthzFreeResourceManager` at `0x180035bcb`
- `AUTHZ!AuthzFreeResourceManager` at `0x180035bcb`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180035dd4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180035deb`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180035dd4`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180035deb`

## pseudocode

```c
__int64 __fastcall lambda_8fd44bed28da3d7ef7a2050c13fca057_::operator()(__int64 a1)
{
  int *v2; // rbx
  void *v3; // rcx
  struct IKdcBackend *v4; // rax
  DWORD LastError; // eax
  struct _RTL_CRITICAL_SECTION *v6; // rcx
  HANDLE **v7; // rbx
  HANDLE *v8; // rsi
  void *v9; // rdx
  CSecurityData *v10; // rbx
  HCRYPTPROV v11; // rcx
  void *v12; // rbx
  void *v13; // rcx
  __int64 DomainCipherPolicy; // rbx
  _BYTE *v15; // r8
  __int64 result; // rax
  __int64 v17; // rcx
  __int64 v18; // [rsp+20h] [rbp-48h] BYREF
  void *v19; // [rsp+28h] [rbp-40h] BYREF
  _QWORD v20[3]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v21; // [rsp+48h] [rbp-20h] BYREF

  KerbKdcCallBack(0);
  if ( KdcGlobalOidsCache )
  {
    if ( qword_1800B42F0 )
      KdcDereferenceOidsCacheEntry(qword_1800B42F0);
    RtlDeleteResource(&stru_1800B4288);
  }
  memset_0(&KdcGlobalOidsCache, 0, 0x78u);
  LsaIKerberosRegisterTrustNotification(&KdcTrustChangeCallback, 1);
  LsaIUnregisterAllPolicyChangeNotificationCallback(KdcPolicyChangeCallBack);
  v2 = *(int **)a1;
  *v2 = I_NetLogonSetServiceBits(**(unsigned int **)(a1 + 8), 0);
  if ( **(int **)a1 < 0
    && WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 77);
  }
  if ( KdcGlobalDsPausedWaitHandle )
  {
    UnregisterWaitEx(KdcGlobalDsPausedWaitHandle, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    KdcGlobalDsPausedWaitHandle = 0;
  }
  if ( GlobalKpasswdName )
    KerbFreeSid(&GlobalKpasswdName);
  v3 = **(void ***)(a1 + 16);
  if ( v3 )
  {
    MIDL_user_free(v3);
    **(_QWORD **)(a1 + 16) = 0;
  }
  KerbFreePrincipalName(&KdcGlobalAnonymousPrincipalName);
  KdcGlobalAnonymousPrincipalName = 0;
  KerbFreeString(&KdcGlobalFxFastCookieConstant);
  KdcGlobalFxFastCookieConstant = 0;
  if ( KdcGlobalDsEventHandle )
  {
    CloseHandle(KdcGlobalDsEventHandle);
    KdcGlobalDsEventHandle = 0;
  }
  UpdateStatus(3u);
  v4 = GlobalKdcService::Get();
  (*(void (__fastcall **)(struct IKdcBackend *))(*(_QWORD *)v4 + 96LL))(v4);
  if ( KdcAuthzRM )
  {
    if ( !AuthzFreeResourceManager(KdcAuthzRM)
      && WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids, LastError);
    }
    KdcAuthzRM = 0;
  }
  KdcCleanupCerts();
  v6 = (struct _RTL_CRITICAL_SECTION *)_InterlockedExchange64((volatile __int64 *)&ScHelperGlobalEventLogHandle, 0);
  if ( v6 )
    NetpEventlogClose(v6);
  if ( hEventLog )
  {
    NetpEventlogClose(hEventLog);
    hEventLog = 0;
  }
  UpdateStatus(3u);
  v20[0] = &hKdcShutdownEvent;
  v7 = (HANDLE **)v20;
  v20[1] = &hKdcKerbReadyEvent;
  v20[2] = &hKdcStartEvent;
  do
  {
    v8 = *v7;
    if ( *v7 && *v8 )
    {
      CloseHandle(*v8);
      *v8 = 0;
    }
    ++v7;
  }
  while ( v7 != (HANDLE **)&v21 );
  CleanupAccountDomain();
  UpdateStatus(3u);
  KdcCleanupDomainTree();
  KerbCleanupSearchForests();
  v9 = **(void ***)(a1 + 24);
  if ( v9 )
  {
    DeleteTimerQueueTimer(0, v9, 0);
    **(_QWORD **)(a1 + 24) = 0;
  }
  if ( **(_DWORD **)(a1 + 32) )
    SStatus.dwWin32ExitCode = **(_DWORD **)(a1 + 32);
  else
    SStatus.dwWin32ExitCode = RtlNtStatusToDosError(**(_DWORD **)(a1 + 40));
  SStatus.dwServiceSpecificExitCode = 0;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids);
  UpdateStatus(1u);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 79, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids);
    v10 = WPP_GLOBAL_Control;
  }
  if ( **(_BYTE **)(a1 + 48) )
  {
    WSACleanup();
    **(_BYTE **)(a1 + 48) = 0;
    v10 = WPP_GLOBAL_Control;
  }
  if ( v10 != (CSecurityData *)&WPP_GLOBAL_Control )
  {
    while ( v10 )
    {
      if ( *((_QWORD *)v10 + 1) )
      {
        EtwUnregisterTraceGuids();
        *((_QWORD *)v10 + 1) = 0;
      }
      v10 = *(CSecurityData **)v10;
    }
    WPP_GLOBAL_Control = (CSecurityData *)&WPP_GLOBAL_Control;
  }
  KerbUnLoadDH();
  v11 = _InterlockedExchange64((volatile __int64 *)&g_hProvHelper, 0);
  v12 = (void *)_InterlockedExchange64((volatile __int64 *)&g_hAlgorithm, 0);
  if ( v11 )
    CryptReleaseContext(v11, 0);
  if ( v12 )
    BCryptCloseAlgorithmProvider(v12, 0);
  v13 = (void *)_InterlockedExchange64((volatile __int64 *)&g_hSha256Algorithm, 0);
  if ( v13 )
    BCryptCloseAlgorithmProvider(v13, 0);
  AcquireSRWLockExclusive(&SRWLock);
  DomainCipherPolicy = GetDomainCipherPolicy();
  v18 = DomainCipherPolicy;
  ((void (__fastcall *)(void **, void *, __int64, __int64 *))utl::find<utl::_ArrayConstIt<Kerb3961::CipherPolicy *>,Kerb3961::CipherPolicy *>)(
    &v19,
    Src,
    qword_1800B26B0,
    &v18);
  if ( v19 != v15 )
  {
    memmove_0(v19, (char *)v19 + 8, (v15 - (_BYTE *)v19 - 8) & 0xFFFFFFFFFFFFFFF8uLL);
    qword_1800B26B0 -= 8;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)DomainCipherPolicy + 16LL))(DomainCipherPolicy);
  }
  ReleaseSRWLockExclusive(&SRWLock);
  if ( KdcThreadContext::s_tlsIndex != -1 )
    TlsFree(KdcThreadContext::s_tlsIndex);
  result = TlgUnregisterAggregateProvider();
  if ( (Microsoft_Windows_Kerberos_Local_Key_Distribution_CenterEnableBits & 2) != 0 )
    return McTemplateU0q_EtwEventWriteTransfer(v17, KdcStop, **(unsigned int **)(a1 + 40));
  return result;
}

```

## disassembly

```asm
0x180035a44  mov     [rsp+arg_8], rbx
0x180035a49  mov     [rsp+arg_10], rbp
0x180035a4e  push    rsi
0x180035a4f  push    rdi
0x180035a50  push    r14
0x180035a52  sub     rsp, 50h
0x180035a56  mov     rax, cs:__security_cookie
0x180035a5d  xor     rax, rsp
0x180035a60  mov     [rsp+68h+var_20], rax
0x180035a65  mov     rdi, rcx
0x180035a68  xor     ecx, ecx
0x180035a6a  call    cs:__imp_KerbKdcCallBack
0x180035a70  xor     ebp, ebp
0x180035a72  cmp     cs:?KdcGlobalOidsCache@@3U_KDC_OIDS_CACHE@@A, bpl; _KDC_OIDS_CACHE KdcGlobalOidsCache
0x180035a79  jz      short loc_180035A99
0x180035a7b  mov     rcx, cs:qword_1800B42F0; struct _KDC_OIDS_CACHE_ENTRY *
0x180035a82  test    rcx, rcx
0x180035a85  jz      short loc_180035A8C
0x180035a87  call    ?KdcDereferenceOidsCacheEntry@@YAXPEAU_KDC_OIDS_CACHE_ENTRY@@@Z; KdcDereferenceOidsCacheEntry(_KDC_OIDS_CACHE_ENTRY *)
0x180035a8c  lea     rcx, stru_1800B4288; Resource
0x180035a93  call    cs:__imp_RtlDeleteResource
0x180035a99  xor     edx, edx; Val
0x180035a9b  lea     rcx, ?KdcGlobalOidsCache@@3U_KDC_OIDS_CACHE@@A; void *
0x180035aa2  lea     r8d, [rdx+78h]; Size
0x180035aa6  call    memset_0
0x180035aab  mov     edx, 1
0x180035ab0  lea     rcx, ?KdcTrustChangeCallback@@YAXW4_SECURITY_DB_DELTA_TYPE@@@Z; KdcTrustChangeCallback(_SECURITY_DB_DELTA_TYPE)
0x180035ab7  call    cs:__imp_LsaIKerberosRegisterTrustNotification
0x180035abd  lea     rcx, ?KdcPolicyChangeCallBack@@YAXW4_POLICY_NOTIFICATION_INFORMATION_CLASS@@@Z; KdcPolicyChangeCallBack(_POLICY_NOTIFICATION_INFORMATION_CLASS)
0x180035ac4  call    cs:__imp_LsaIUnregisterAllPolicyChangeNotificationCallback
0x180035aca  mov     rcx, [rdi+8]
0x180035ace  xor     edx, edx
0x180035ad0  mov     rbx, [rdi]
0x180035ad3  mov     ecx, [rcx]
0x180035ad5  call    cs:__imp_I_NetLogonSetServiceBits
0x180035adb  mov     [rbx], eax
0x180035add  lea     r14, WPP_GLOBAL_Control
0x180035ae4  mov     rax, [rdi]
0x180035ae7  mov     r9d, [rax]
0x180035aea  test    r9d, r9d
0x180035aed  jns     short loc_180035B0F
0x180035aef  mov     rcx, cs:WPP_GLOBAL_Control
0x180035af6  cmp     rcx, r14
0x180035af9  jz      short loc_180035B0F
0x180035afb  test    byte ptr [rcx+1Ch], 4
0x180035aff  jz      short loc_180035B0F
0x180035b01  mov     rcx, [rcx+10h]
0x180035b05  mov     edx, 4Dh ; 'M'
0x180035b0a  call    WPP_SF_L
0x180035b0f  mov     rcx, cs:?KdcGlobalDsPausedWaitHandle@@3PEAXEA; WaitHandle
0x180035b16  test    rcx, rcx
0x180035b19  jz      short loc_180035B2C
0x180035b1b  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180035b1f  call    cs:__imp_UnregisterWaitEx
0x180035b25  mov     cs:?KdcGlobalDsPausedWaitHandle@@3PEAXEA, rbp; void * KdcGlobalDsPausedWaitHandle
0x180035b2c  cmp     cs:?GlobalKpasswdName@@3PEAU_KERB_INTERNAL_NAME@@EA, rbp; _KERB_INTERNAL_NAME * GlobalKpasswdName
0x180035b33  jz      short loc_180035B41
0x180035b35  lea     rcx, ?GlobalKpasswdName@@3PEAU_KERB_INTERNAL_NAME@@EA; _KERB_INTERNAL_NAME * GlobalKpasswdName
0x180035b3c  call    KerbFreeSid
0x180035b41  mov     rax, [rdi+10h]
0x180035b45  mov     rcx, [rax]; void *
0x180035b48  test    rcx, rcx
0x180035b4b  jz      short loc_180035B59
0x180035b4d  call    MIDL_user_free
0x180035b52  mov     rax, [rdi+10h]
0x180035b56  mov     [rax], rbp
0x180035b59  lea     rcx, ?KdcGlobalAnonymousPrincipalName@@3UKERB_PRINCIPAL_NAME@@A; KERB_PRINCIPAL_NAME KdcGlobalAnonymousPrincipalName
0x180035b60  call    KerbFreePrincipalName
0x180035b65  xorps   xmm0, xmm0
0x180035b68  lea     rcx, ?KdcGlobalFxFastCookieConstant@@3U_STRING@@A; _STRING KdcGlobalFxFastCookieConstant
0x180035b6f  movups  cs:?KdcGlobalAnonymousPrincipalName@@3UKERB_PRINCIPAL_NAME@@A, xmm0; KERB_PRINCIPAL_NAME KdcGlobalAnonymousPrincipalName
0x180035b76  call    KerbFreeString
0x180035b7b  mov     rcx, cs:?KdcGlobalDsEventHandle@@3PEAXEA; hObject
0x180035b82  xorps   xmm0, xmm0
0x180035b85  movups  xmmword ptr cs:?KdcGlobalFxFastCookieConstant@@3U_STRING@@A.Length, xmm0; _STRING KdcGlobalFxFastCookieConstant ...
0x180035b8c  test    rcx, rcx
0x180035b8f  jz      short loc_180035B9E
0x180035b91  call    cs:__imp_CloseHandle
0x180035b97  mov     cs:?KdcGlobalDsEventHandle@@3PEAXEA, rbp; void * KdcGlobalDsEventHandle
0x180035b9e  mov     ecx, 3; unsigned int
0x180035ba3  call    ?UpdateStatus@@YAEK@Z; UpdateStatus(ulong)
0x180035ba8  call    ?Get@GlobalKdcService@@SAAEAUIKdcBackend@@XZ; GlobalKdcService::Get(void)
0x180035bad  mov     rdx, rax
0x180035bb0  mov     rcx, [rax]
0x180035bb3  mov     rax, [rcx+60h]
0x180035bb7  mov     rcx, rdx
0x180035bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035bbf  mov     rcx, cs:?KdcAuthzRM@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA; hAuthzResourceManager
0x180035bc6  test    rcx, rcx
0x180035bc9  jz      short loc_180035C13
0x180035bcb  call    cs:__imp_AuthzFreeResourceManager
0x180035bd1  test    eax, eax
0x180035bd3  jnz     short loc_180035C0C
0x180035bd5  mov     rax, cs:WPP_GLOBAL_Control
0x180035bdc  cmp     rax, r14
0x180035bdf  jz      short loc_180035C0C
0x180035be1  test    byte ptr [rax+1Ch], 1
0x180035be5  jz      short loc_180035C0C
0x180035be7  call    cs:__imp_GetLastError
0x180035bed  mov     rcx, cs:WPP_GLOBAL_Control
0x180035bf4  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x180035bfb  mov     edx, 0Bh
0x180035c00  mov     r9d, eax
0x180035c03  mov     rcx, [rcx+10h]
0x180035c07  call    WPP_SF_d
0x180035c0c  mov     cs:?KdcAuthzRM@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA, rbp; AUTHZ_RESOURCE_MANAGER_HANDLE__ * KdcAuthzRM
0x180035c13  call    ?KdcCleanupCerts@@YAXE@Z; KdcCleanupCerts(uchar)
0x180035c18  mov     rcx, rbp
0x180035c1b  xchg    rcx, cs:?ScHelperGlobalEventLogHandle@@3REAXEA; lpCriticalSection
0x180035c22  test    rcx, rcx
0x180035c25  jz      short loc_180035C2C
0x180035c27  call    NetpEventlogClose
0x180035c2c  mov     rcx, cs:?hEventLog@@3PEAXEA; lpCriticalSection
0x180035c33  test    rcx, rcx
0x180035c36  jz      short loc_180035C44
0x180035c38  call    NetpEventlogClose
0x180035c3d  mov     cs:?hEventLog@@3PEAXEA, rbp; void * hEventLog
0x180035c44  mov     ecx, 3; unsigned int
0x180035c49  call    ?UpdateStatus@@YAEK@Z; UpdateStatus(ulong)
0x180035c4e  lea     rax, ?hKdcShutdownEvent@@3PEAXEA; void * hKdcShutdownEvent
0x180035c55  mov     [rsp+68h+var_38], rax
0x180035c5a  lea     rbx, [rsp+68h+var_38]
0x180035c5f  lea     rax, ?hKdcKerbReadyEvent@@3PEAXEA; void * hKdcKerbReadyEvent
0x180035c66  mov     [rsp+68h+var_30], rax
0x180035c6b  lea     rax, ?hKdcStartEvent@@3PEAXEA; void * hKdcStartEvent
0x180035c72  mov     [rsp+68h+var_28], rax
0x180035c77  mov     rsi, [rbx]
0x180035c7a  test    rsi, rsi
0x180035c7d  jz      short loc_180035C90
0x180035c7f  mov     rcx, [rsi]; hObject
0x180035c82  test    rcx, rcx
0x180035c85  jz      short loc_180035C90
0x180035c87  call    cs:__imp_CloseHandle
0x180035c8d  mov     [rsi], rbp
0x180035c90  add     rbx, 8
0x180035c94  lea     rax, [rsp+68h+var_20]
0x180035c99  cmp     rbx, rax
0x180035c9c  jnz     short loc_180035C77
0x180035c9e  call    ?CleanupAccountDomain@@YAXXZ; CleanupAccountDomain(void)
0x180035ca3  mov     ecx, 3; unsigned int
0x180035ca8  call    ?UpdateStatus@@YAEK@Z; UpdateStatus(ulong)
0x180035cad  call    ?KdcCleanupDomainTree@@YAXXZ; KdcCleanupDomainTree(void)
0x180035cb2  call    ?KerbCleanupSearchForests@@YAXXZ; KerbCleanupSearchForests(void)
0x180035cb7  mov     rax, [rdi+18h]
0x180035cbb  mov     rdx, [rax]; Timer
0x180035cbe  test    rdx, rdx
0x180035cc1  jz      short loc_180035CD5
0x180035cc3  xor     r8d, r8d; CompletionEvent
0x180035cc6  xor     ecx, ecx; TimerQueue
0x180035cc8  call    cs:__imp_DeleteTimerQueueTimer
0x180035cce  mov     rax, [rdi+18h]
0x180035cd2  mov     [rax], rbp
0x180035cd5  mov     rax, [rdi+20h]
0x180035cd9  mov     ecx, [rax]
0x180035cdb  test    ecx, ecx
0x180035cdd  jz      short loc_180035CE7
0x180035cdf  mov     cs:?SStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, ecx; _SERVICE_STATUS SStatus ...
0x180035ce5  jmp     short loc_180035CF9
0x180035ce7  mov     rcx, [rdi+28h]
0x180035ceb  mov     ecx, [rcx]; Status
0x180035ced  call    cs:__imp_RtlNtStatusToDosError
0x180035cf3  mov     cs:?SStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, eax; _SERVICE_STATUS SStatus ...
0x180035cf9  mov     cs:?SStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, ebp; _SERVICE_STATUS SStatus ...
0x180035cff  mov     rcx, cs:WPP_GLOBAL_Control
0x180035d06  cmp     rcx, r14
0x180035d09  jz      short loc_180035D26
0x180035d0b  test    byte ptr [rcx+1Ch], 4
0x180035d0f  jz      short loc_180035D26
0x180035d11  mov     rcx, [rcx+10h]
0x180035d15  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x180035d1c  mov     edx, 4Eh ; 'N'
0x180035d21  call    WPP_SF_
0x180035d26  mov     ecx, 1; unsigned int
0x180035d2b  call    ?UpdateStatus@@YAEK@Z; UpdateStatus(ulong)
0x180035d30  mov     rbx, cs:WPP_GLOBAL_Control
0x180035d37  cmp     rbx, r14
0x180035d3a  jz      short loc_180035D5E
0x180035d3c  test    byte ptr [rbx+1Ch], 4
0x180035d40  jz      short loc_180035D5E
0x180035d42  mov     rcx, [rbx+10h]
0x180035d46  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x180035d4d  mov     edx, 4Fh ; 'O'
0x180035d52  call    WPP_SF_
0x180035d57  mov     rbx, cs:WPP_GLOBAL_Control
0x180035d5e  mov     rax, [rdi+30h]
0x180035d62  cmp     [rax], bpl
0x180035d65  jz      short loc_180035D7B
0x180035d67  call    cs:__imp_WSACleanup
0x180035d6d  mov     rax, [rdi+30h]
0x180035d71  mov     [rax], bpl
0x180035d74  mov     rbx, cs:WPP_GLOBAL_Control
0x180035d7b  cmp     rbx, r14
0x180035d7e  jz      short loc_180035DA4
0x180035d80  jmp     short loc_180035D98
0x180035d82  mov     rcx, [rbx+8]
0x180035d86  test    rcx, rcx
0x180035d89  jz      short loc_180035D95
0x180035d8b  call    cs:__imp_EtwUnregisterTraceGuids
0x180035d91  mov     [rbx+8], rbp
0x180035d95  mov     rbx, [rbx]
0x180035d98  test    rbx, rbx
0x180035d9b  jnz     short loc_180035D82
0x180035d9d  mov     cs:WPP_GLOBAL_Control, r14
0x180035da4  call    ?KerbUnLoadDH@@YAXXZ; KerbUnLoadDH(void)
0x180035da9  mov     rcx, rbp
0x180035dac  mov     rbx, rbp
0x180035daf  xchg    rcx, cs:?g_hProvHelper@@3_KC; hProv
0x180035db6  xchg    rbx, cs:?g_hAlgorithm@@3REAXEA; void * g_hAlgorithm
0x180035dbd  test    rcx, rcx
0x180035dc0  jz      short loc_180035DCA
0x180035dc2  xor     edx, edx; dwFlags
0x180035dc4  call    cs:__imp_CryptReleaseContext
0x180035dca  test    rbx, rbx
0x180035dcd  jz      short loc_180035DDA
0x180035dcf  xor     edx, edx; dwFlags
0x180035dd1  mov     rcx, rbx; hAlgorithm
0x180035dd4  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180035dda  mov     rcx, rbp
0x180035ddd  xchg    rcx, cs:?g_hSha256Algorithm@@3REAXEA; hAlgorithm
0x180035de4  test    rcx, rcx
0x180035de7  jz      short loc_180035DF1
0x180035de9  xor     edx, edx; dwFlags
0x180035deb  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180035df1  lea     rcx, SRWLock; SRWLock
0x180035df8  call    cs:__imp_AcquireSRWLockExclusive
0x180035dfe  call    cs:__imp_GetDomainCipherPolicy
0x180035e04  mov     r8, cs:qword_1800B26B0
0x180035e0b  lea     r9, [rsp+68h+var_48]
0x180035e10  mov     rdx, cs:Src
0x180035e17  lea     rcx, [rsp+68h+var_40]
0x180035e1c  mov     rbx, rax
0x180035e1f  mov     [rsp+68h+var_48], rax
0x180035e24  call    ??$find@V?$_ArrayConstIt@PEAUCipherPolicy@Kerb3961@@@utl@@PEAUCipherPolicy@Kerb3961@@@utl@@YA?AV?$_ArrayConstIt@PEAUCipherPolicy@Kerb3961@@@0@V10@0AEBQEAUCipherPolicy@Kerb3961@@@Z; utl::find<utl::_ArrayConstIt<Kerb3961::CipherPolicy *>,Kerb3961::CipherPolicy *>(utl::_ArrayConstIt<Kerb3961::CipherPolicy *>,utl::_ArrayConstIt<Kerb3961::CipherPolicy *>,Kerb3961::CipherPolicy * const &)
0x180035e29  mov     rcx, [rsp+68h+var_40]; void *
0x180035e2e  cmp     rcx, r8
0x180035e31  jz      short loc_180035E5E
0x180035e33  sub     r8, rcx
0x180035e36  lea     rdx, [rcx+8]; Src
0x180035e3a  sub     r8, 8
0x180035e3e  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x180035e42  call    memmove_0
0x180035e47  sub     cs:qword_1800B26B0, 8
0x180035e4f  mov     rcx, rbx
0x180035e52  mov     rax, [rbx]
0x180035e55  mov     rax, [rax+10h]
0x180035e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e5e  lea     rcx, SRWLock; SRWLock
0x180035e65  call    cs:__imp_ReleaseSRWLockExclusive
0x180035e6b  mov     ecx, cs:?s_tlsIndex@KdcThreadContext@@0KA; dwTlsIndex
0x180035e71  cmp     ecx, 0FFFFFFFFh
0x180035e74  jz      short loc_180035E7C
0x180035e76  call    cs:__imp_TlsFree
0x180035e7c  call    TlgUnregisterAggregateProvider
0x180035e81  test    cs:Microsoft_Windows_Kerberos_Local_Key_Distribution_CenterEnableBits, 2
0x180035e88  jz      short loc_180035E9D
0x180035e8a  mov     r8, [rdi+28h]
0x180035e8e  lea     rdx, KdcStop
0x180035e95  mov     r8d, [r8]
0x180035e98  call    McTemplateU0q_EtwEventWriteTransfer
0x180035e9d  mov     rcx, [rsp+68h+var_20]
0x180035ea2  xor     rcx, rsp; StackCookie
0x180035ea5  call    __security_check_cookie
0x180035eaa  lea     r11, [rsp+68h+var_18]
0x180035eaf  mov     rbx, [r11+28h]
0x180035eb3  mov     rbp, [r11+30h]
0x180035eb7  mov     rsp, r11
0x180035eba  pop     r14
0x180035ebc  pop     rdi
0x180035ebd  pop     rsi
0x180035ebe  retn
```
