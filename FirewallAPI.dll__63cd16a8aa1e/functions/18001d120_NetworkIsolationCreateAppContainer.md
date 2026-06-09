# NetworkIsolationCreateAppContainer

- ea: `0x18001d120`
- end: `0x18001d54e`
- name: `NetworkIsolationCreateAppContainer`
- size: `1070`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005954`
- `0x18000e960`
- `0x18001d120`
- `0x18001e378`
- `0x1800229b4`
- `0x180024c3c`
- `0x1800277b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001d318`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001d33e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001d3e1`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001d318`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001d33e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001d3e1`
- `RPCRT4!RpcExceptionFilter` at `0x18005ba4c`
- `RPCRT4!RpcExceptionFilter` at `0x18005ba4c`
- `RPCRT4!RpcBindingFree` at `0x18001d519`
- `RPCRT4!RpcBindingFree` at `0x18001d519`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d1ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d1ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d295`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18001d187`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18001d187`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001d28b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001d28b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d364`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d384`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d3f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d364`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d384`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001d3f0`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001d4e4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001d4e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d19b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d19b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001d1dc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001d1dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d1c8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d1c8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d1b6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d1b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001d195`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001d195`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001d302`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001d3cb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001d302`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001d3cb`
- `fwbase!FwBaseFree` at `0x18001d500`
- `fwbase!FwBaseFree` at `0x18001d500`
- `fwbase!FwCloseHandle` at `0x18001d4f2`
- `fwbase!FwCloseHandle` at `0x18001d4f2`
- `fwbase!FwHResultToWindowsError` at `0x18001d252`
- `fwbase!FwHResultToWindowsError` at `0x18001d252`
- `fwbase!FwGetTokenInformation` at `0x18001d24a`
- `fwbase!FwGetTokenInformation` at `0x18001d24a`

## pseudocode

```c
__int64 __fastcall NetworkIsolationCreateAppContainer(
        int a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6)
{
  __int64 v6; // r13
  int v7; // r14d
  int CurrentServiceSessionId; // r12d
  HANDLE CurrentThread; // rax
  BOOL v10; // eax
  int v11; // r15d
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  FwPolicy2 *v14; // rcx
  __int64 v15; // rdx
  unsigned int TokenInformation; // eax
  __int64 v17; // rdx
  unsigned int v18; // ebx
  int v19; // r13d
  __int64 v20; // r12
  int v21; // eax
  int v22; // ecx
  LPWSTR v23; // rcx
  int v24; // eax
  FwPolicy2 *v25; // rcx
  __int64 v26; // rdx
  unsigned int v27; // eax
  __int64 v28; // rcx
  int v30; // [rsp+40h] [rbp-98h]
  LPWSTR StringSid; // [rsp+78h] [rbp-60h] BYREF
  void *TokenHandle; // [rsp+80h] [rbp-58h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+88h] [rbp-50h] BYREF
  _QWORD *v38; // [rsp+90h] [rbp-48h] BYREF

  v6 = a5;
  Binding = 0;
  v38 = 0;
  TokenHandle = 0;
  v7 = 0;
  v30 = 0;
  CurrentServiceSessionId = RtlGetCurrentServiceSessionId();
  StringSid = 0;
  GetTickCount64();
  CurrentThread = GetCurrentThread();
  v10 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  if ( v10 )
  {
    v11 = 1;
  }
  else
  {
    v11 = 0;
    CurrentProcess = GetCurrentProcess();
    v10 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  }
  if ( !v10 )
  {
    LastError = GetLastError();
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 453;
LABEL_8:
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, LastError);
      goto LABEL_53;
    }
    goto LABEL_53;
  }
  TokenInformation = FwGetTokenInformation(TokenHandle, 1, &v38, 0);
  LastError = FwHResultToWindowsError(TokenInformation);
  if ( !LastError )
  {
    if ( v11 == 1 )
    {
      if ( !RevertToSelf() )
      {
        LastError = GetLastError();
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = 455;
          goto LABEL_8;
        }
        goto LABEL_53;
      }
      v30 = 1;
    }
    LOBYTE(v17) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppContainerConnectivityOnWindowsServerContainers>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_AppContainerConnectivityOnWindowsServerContainers>::GetImpl'::`2'::impl,
      v17);
    v18 = 0;
    if ( CurrentServiceSessionId )
    {
      while ( v18 < a6 )
      {
        if ( ConvertSidToStringSidW(*(PSID *)(v6 + 16LL * v18), &StringSid) )
        {
          if ( !(unsigned int)_o__wcsicmp(StringSid, L"S-1-15-3-4214768333-1334025770-122408079-3919188833") )
          {
            v23 = StringSid;
            goto LABEL_33;
          }
          v19 = 0;
          v20 = 0;
          do
          {
            if ( (unsigned int)v20 >= 3 )
              break;
            v21 = _o__wcsicmp(StringSid, (&networkingSidInfoTable)[v20]);
            if ( !v21 )
              v19 = 1;
            v20 = (unsigned int)(v20 + 1);
            v22 = v7 + 1;
            if ( v21 )
              v22 = v7;
            v7 = v22;
          }
          while ( !v19 );
          LocalFree(StringSid);
          StringSid = 0;
          v6 = a5;
        }
        ++v18;
      }
      if ( v7 != 3 && v7 )
LABEL_34:
        LastError = 50;
      else
        LastError = 0;
      goto LABEL_52;
    }
    while ( v18 < a6 )
    {
      if ( ConvertSidToStringSidW(*(PSID *)(a5 + 16LL * v18), &StringSid) )
      {
        v24 = _o__wcsicmp(
                StringSid,
                L"S-1-15-3-1024-820624432-2503302554-1536879699-4049119443-112573677-3799174643-950279649-4267032225");
        v23 = StringSid;
        if ( !v24 )
        {
LABEL_33:
          LocalFree(v23);
          StringSid = 0;
          goto LABEL_34;
        }
        LocalFree(StringSid);
        StringSid = 0;
      }
      ++v18;
    }
    LastError = Int_FWLocalRpcBindingCreate(&Binding);
    if ( LastError )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_52;
      v26 = 456;
    }
    else
    {
      LastError = RPC_NetworkIsolationCreateAppContainer((_DWORD)Binding, *v38, a1, a2, a3, a4, a5, a6);
      if ( !LastError )
        goto LABEL_52;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_52;
      v26 = 457;
    }
    WPP_SF_d(*((_QWORD *)v25 + 2), v26, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, LastError);
LABEL_52:
    v7 = v30;
    goto LABEL_53;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v15 = 454;
    goto LABEL_8;
  }
LABEL_53:
  if ( v11 == 1 && v7 == 1 )
    SetThreadToken(0, TokenHandle);
  FwCloseHandle(TokenHandle);
  FwBaseFree(v38);
  if ( Binding )
  {
    v27 = RpcBindingFree(&Binding);
    if ( v27 )
      MicrosoftTelemetryAssertTriggeredArgs(v28, v27);
  }
  return LastError;
}

```

## disassembly

```asm
0x18001d120  mov     r11, rsp
0x18001d123  push    rbx
0x18001d124  push    rsi
0x18001d125  push    r12
0x18001d127  push    r13
0x18001d129  push    r14
0x18001d12b  push    r15
0x18001d12d  sub     rsp, 0A8h
0x18001d134  mov     rax, cs:__security_cookie
0x18001d13b  xor     rax, rsp
0x18001d13e  mov     [rsp+0D8h+var_40], rax
0x18001d146  mov     [rsp+0D8h+var_80], r9
0x18001d14b  mov     [rsp+0D8h+var_78], r8
0x18001d150  mov     [rsp+0D8h+var_70], rdx
0x18001d155  mov     [rsp+0D8h+var_68], rcx
0x18001d15a  mov     r13, [rsp+0D8h+arg_20]
0x18001d162  mov     [rsp+0D8h+var_88], r13
0x18001d167  mov     qword ptr [r11-50h], 0
0x18001d16f  mov     qword ptr [r11-48h], 0
0x18001d177  mov     qword ptr [r11-58h], 0
0x18001d17f  xor     r14d, r14d
0x18001d182  mov     [rsp+0D8h+var_98], r14d
0x18001d187  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18001d18d  mov     r12d, eax
0x18001d190  mov     [rsp+0D8h+StringSid], r14
0x18001d195  call    cs:__imp_GetTickCount64
0x18001d19b  call    cs:__imp_GetCurrentThread
0x18001d1a1  mov     rcx, rax; ThreadHandle
0x18001d1a4  lea     r9, [rsp+0D8h+TokenHandle]; TokenHandle
0x18001d1ac  lea     esi, [r14+1]
0x18001d1b0  mov     r8d, esi; OpenAsSelf
0x18001d1b3  lea     edx, [rsi+0Bh]; DesiredAccess
0x18001d1b6  call    cs:__imp_OpenThreadToken
0x18001d1bc  test    eax, eax
0x18001d1be  jnz     short loc_18001D1E4
0x18001d1c0  xor     r15d, r15d
0x18001d1c3  mov     [rsp+0D8h+var_94], r15d
0x18001d1c8  call    cs:__imp_GetCurrentProcess
0x18001d1ce  mov     rcx, rax; ProcessHandle
0x18001d1d1  lea     r8, [rsp+0D8h+TokenHandle]; TokenHandle
0x18001d1d9  lea     edx, [rsi+7]; DesiredAccess
0x18001d1dc  call    cs:__imp_OpenProcessToken
0x18001d1e2  jmp     short loc_18001D1EB
0x18001d1e4  mov     r15d, esi
0x18001d1e7  mov     [rsp+0D8h+var_94], esi
0x18001d1eb  test    eax, eax
0x18001d1ed  jnz     short loc_18001D235
0x18001d1ef  call    cs:__imp_GetLastError
0x18001d1f5  mov     ebx, eax
0x18001d1f7  lea     rax, WPP_GLOBAL_Control
0x18001d1fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d205  cmp     rcx, rax
0x18001d208  jz      loc_18001D4D0
0x18001d20e  test    [rcx+1Ch], sil
0x18001d212  jz      loc_18001D4D0
0x18001d218  mov     edx, 1C5h
0x18001d21d  mov     r9d, ebx
0x18001d220  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18001d227  mov     rcx, [rcx+10h]
0x18001d22b  call    WPP_SF_d
0x18001d230  jmp     loc_18001D4D0
0x18001d235  xor     r9d, r9d
0x18001d238  lea     r8, [rsp+0D8h+var_48]
0x18001d240  mov     edx, esi
0x18001d242  mov     rcx, [rsp+0D8h+TokenHandle]
0x18001d24a  call    cs:__imp_FwGetTokenInformation
0x18001d250  mov     ecx, eax
0x18001d252  call    cs:__imp_FwHResultToWindowsError
0x18001d258  mov     ebx, eax
0x18001d25a  test    eax, eax
0x18001d25c  jz      short loc_18001D286
0x18001d25e  lea     rax, WPP_GLOBAL_Control
0x18001d265  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d26c  cmp     rcx, rax
0x18001d26f  jz      loc_18001D4D0
0x18001d275  test    [rcx+1Ch], sil
0x18001d279  jz      loc_18001D4D0
0x18001d27f  mov     edx, 1C6h
0x18001d284  jmp     short loc_18001D21D
0x18001d286  cmp     r15d, esi
0x18001d289  jnz     short loc_18001D2CC
0x18001d28b  call    cs:__imp_RevertToSelf
0x18001d291  test    eax, eax
0x18001d293  jnz     short loc_18001D2C8
0x18001d295  call    cs:__imp_GetLastError
0x18001d29b  mov     ebx, eax
0x18001d29d  lea     rax, WPP_GLOBAL_Control
0x18001d2a4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2ab  cmp     rcx, rax
0x18001d2ae  jz      loc_18001D4D0
0x18001d2b4  test    [rcx+1Ch], sil
0x18001d2b8  jz      loc_18001D4D0
0x18001d2be  mov     edx, 1C7h
0x18001d2c3  jmp     loc_18001D21D
0x18001d2c8  mov     [rsp+0D8h+var_98], esi
0x18001d2cc  mov     dl, sil
0x18001d2cf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppContainerConnectivityOnWindowsServerContainers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppContainerConnectivityOnWindowsServerContainers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppContainerConnectivityOnWindowsServerContainers> `wil::Feature<__WilFeatureTraits_Feature_AppContainerConnectivityOnWindowsServerContainers>::GetImpl(void)'::`2'::impl
0x18001d2d6  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppContainerConnectivityOnWindowsServerContainers@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppContainerConnectivityOnWindowsServerContainers>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001d2db  xor     ebx, ebx
0x18001d2dd  test    r12d, r12d
0x18001d2e0  jz      loc_18001D3AF
0x18001d2e6  cmp     ebx, [rsp+0D8h+arg_28]
0x18001d2ed  jnb     loc_18001D39D
0x18001d2f3  mov     ecx, ebx
0x18001d2f5  add     rcx, rcx
0x18001d2f8  lea     rdx, [rsp+0D8h+StringSid]; StringSid
0x18001d2fd  mov     rcx, [r13+rcx*8+0]; Sid
0x18001d302  call    cs:__imp_ConvertSidToStringSidW
0x18001d308  test    eax, eax
0x18001d30a  jz      short loc_18001D378
0x18001d30c  mov     rdx, cs:off_180064098; "S-1-15-3-4214768333-1334025770-12240807"...
0x18001d313  mov     rcx, [rsp+0D8h+StringSid]
0x18001d318  call    cs:__imp__o__wcsicmp
0x18001d31e  test    eax, eax
0x18001d320  jz      short loc_18001D37F
0x18001d322  xor     r13d, r13d
0x18001d325  xor     r12d, r12d
0x18001d328  cmp     r12d, 3
0x18001d32c  jnb     short loc_18001D35F
0x18001d32e  lea     rax, ?networkingSidInfoTable@@3PAPEAGA; ushort * near * networkingSidInfoTable
0x18001d335  mov     rdx, [rax+r12*8]
0x18001d339  mov     rcx, [rsp+0D8h+StringSid]
0x18001d33e  call    cs:__imp__o__wcsicmp
0x18001d344  test    eax, eax
0x18001d346  cmovz   r13d, esi
0x18001d34a  add     r12d, esi
0x18001d34d  lea     ecx, [r14+1]
0x18001d351  test    eax, eax
0x18001d353  cmovnz  ecx, r14d
0x18001d357  mov     r14d, ecx
0x18001d35a  test    r13d, r13d
0x18001d35d  jz      short loc_18001D328
0x18001d35f  mov     rcx, [rsp+0D8h+StringSid]; hMem
0x18001d364  call    cs:__imp_LocalFree
0x18001d36a  mov     [rsp+0D8h+StringSid], 0
0x18001d373  mov     r13, [rsp+0D8h+var_88]
0x18001d378  add     ebx, esi
0x18001d37a  jmp     loc_18001D2E6
0x18001d37f  mov     rcx, [rsp+0D8h+StringSid]; hMem
0x18001d384  call    cs:__imp_LocalFree
0x18001d38a  mov     [rsp+0D8h+StringSid], 0
0x18001d393  mov     ebx, 32h ; '2'
0x18001d398  jmp     loc_18001D4CB
0x18001d39d  cmp     r14d, 3
0x18001d3a1  jz      short loc_18001D3A8
0x18001d3a3  test    r14d, r14d
0x18001d3a6  jnz     short loc_18001D393
0x18001d3a8  xor     ebx, ebx
0x18001d3aa  jmp     loc_18001D4CB
0x18001d3af  mov     r14d, [rsp+0D8h+arg_28]
0x18001d3b7  cmp     ebx, r14d
0x18001d3ba  jnb     short loc_18001D403
0x18001d3bc  mov     ecx, ebx
0x18001d3be  add     rcx, rcx
0x18001d3c1  lea     rdx, [rsp+0D8h+StringSid]; StringSid
0x18001d3c6  mov     rcx, [r13+rcx*8+0]; Sid
0x18001d3cb  call    cs:__imp_ConvertSidToStringSidW
0x18001d3d1  test    eax, eax
0x18001d3d3  jz      short loc_18001D3FF
0x18001d3d5  lea     rdx, aS1153102482062; "S-1-15-3-1024-820624432-2503302554-1536"...
0x18001d3dc  mov     rcx, [rsp+0D8h+StringSid]
0x18001d3e1  call    cs:__imp__o__wcsicmp
0x18001d3e7  mov     rcx, [rsp+0D8h+StringSid]; hMem
0x18001d3ec  test    eax, eax
0x18001d3ee  jz      short loc_18001D384
0x18001d3f0  call    cs:__imp_LocalFree
0x18001d3f6  mov     [rsp+0D8h+StringSid], 0
0x18001d3ff  add     ebx, esi
0x18001d401  jmp     short loc_18001D3B7
0x18001d403  lea     rcx, [rsp+0D8h+Binding]
0x18001d40b  call    Int_FWLocalRpcBindingCreate
0x18001d410  mov     ebx, eax
0x18001d412  test    eax, eax
0x18001d414  jz      short loc_18001D43E
0x18001d416  lea     rax, WPP_GLOBAL_Control
0x18001d41d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d424  cmp     rcx, rax
0x18001d427  jz      loc_18001D4CB
0x18001d42d  test    [rcx+1Ch], sil
0x18001d431  jz      loc_18001D4CB
0x18001d437  mov     edx, 1C8h
0x18001d43c  jmp     short loc_18001D4B8
0x18001d43e  mov     [rsp+0D8h+var_A0], r14d
0x18001d443  mov     [rsp+0D8h+var_A8], r13
0x18001d448  mov     rax, [rsp+0D8h+var_80]
0x18001d44d  mov     [rsp+0D8h+var_B0], rax
0x18001d452  mov     rax, [rsp+0D8h+var_78]
0x18001d457  mov     [rsp+0D8h+var_B8], rax
0x18001d45c  mov     r9, [rsp+0D8h+var_70]
0x18001d461  mov     r8, [rsp+0D8h+var_68]
0x18001d466  mov     rdx, [rsp+0D8h+var_48]
0x18001d46e  mov     rdx, [rdx]
0x18001d471  mov     rcx, [rsp+0D8h+Binding]
0x18001d479  call    RPC_NetworkIsolationCreateAppContainer
0x18001d47e  mov     ebx, eax
0x18001d480  mov     [rsp+0D8h+var_90], eax
0x18001d484  jmp     short loc_18001D496
0x18001d486  mov     ebx, eax
0x18001d488  mov     [rsp+0D8h+var_90], eax
0x18001d48c  mov     esi, 1
0x18001d491  mov     r15d, [rsp+0D8h+var_94]
0x18001d496  test    ebx, ebx
0x18001d498  jz      short loc_18001D4CB
0x18001d49a  lea     rax, WPP_GLOBAL_Control
0x18001d4a1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d4a8  cmp     rcx, rax
0x18001d4ab  jz      short loc_18001D4CB
0x18001d4ad  test    [rcx+1Ch], sil
0x18001d4b1  jz      short loc_18001D4CB
0x18001d4b3  mov     edx, 1C9h
0x18001d4b8  mov     r9d, ebx
0x18001d4bb  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18001d4c2  mov     rcx, [rcx+10h]
0x18001d4c6  call    WPP_SF_d
0x18001d4cb  mov     r14d, [rsp+0D8h+var_98]
0x18001d4d0  cmp     r15d, esi
0x18001d4d3  jnz     short loc_18001D4EA
0x18001d4d5  cmp     r14d, esi
0x18001d4d8  jnz     short loc_18001D4EA
0x18001d4da  mov     rdx, [rsp+0D8h+TokenHandle]; Token
0x18001d4e2  xor     ecx, ecx; Thread
0x18001d4e4  call    cs:__imp_SetThreadToken
0x18001d4ea  mov     rcx, [rsp+0D8h+TokenHandle]
0x18001d4f2  call    cs:__imp_FwCloseHandle
0x18001d4f8  mov     rcx, [rsp+0D8h+var_48]
0x18001d500  call    cs:__imp_FwBaseFree
0x18001d506  cmp     [rsp+0D8h+Binding], 0
0x18001d50f  jz      short loc_18001D52A
0x18001d511  lea     rcx, [rsp+0D8h+Binding]; Binding
0x18001d519  call    cs:__imp_RpcBindingFree
0x18001d51f  test    eax, eax
0x18001d521  jz      short loc_18001D52A
0x18001d523  mov     edx, eax
0x18001d525  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001d52a  mov     eax, ebx
0x18001d52c  mov     rcx, [rsp+0D8h+var_40]
0x18001d534  xor     rcx, rsp; StackCookie
0x18001d537  call    __security_check_cookie
0x18001d53c  add     rsp, 0A8h
0x18001d543  pop     r15
0x18001d545  pop     r14
0x18001d547  pop     r13
0x18001d549  pop     r12
0x18001d54b  pop     rsi
0x18001d54c  pop     rbx
0x18001d54d  retn
0x18005ba3e  push    rbp
0x18005ba40  sub     rsp, 40h
0x18005ba44  mov     rbp, rdx
0x18005ba47  mov     rcx, [rcx]
0x18005ba4a  mov     ecx, [rcx]; ExceptionCode
0x18005ba4c  call    cs:__imp_RpcExceptionFilter
0x18005ba52  nop
0x18005ba53  add     rsp, 40h
0x18005ba57  pop     rbp
0x18005ba58  retn
```
