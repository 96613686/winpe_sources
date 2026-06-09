# NetworkIsolationCreateAppContainer

- ea: `0x18001e4a0`
- end: `0x18001e959`
- name: `NetworkIsolationCreateAppContainer`
- size: `1209`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005e0c`
- `0x18000ea10`
- `0x18001e4a0`
- `0x18001f4bc`
- `0x180024414`
- `0x180026798`
- `0x1800294b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001e6e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001e70c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001e7c7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001e6e0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001e70c`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18001e7c7`
- `RPCRT4!RpcExceptionFilter` at `0x18005fc84`
- `RPCRT4!RpcExceptionFilter` at `0x18005fc84`
- `RPCRT4!RpcBindingFree` at `0x18001e91d`
- `RPCRT4!RpcBindingFree` at `0x18001e91d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e651`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e593`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e651`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18001e507`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18001e507`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001e641`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001e641`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e738`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e75e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7dc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e738`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e75e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7dc`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001e8d6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001e8d6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e527`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001e527`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001e57a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001e57a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e560`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001e560`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e548`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001e548`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001e51b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001e51b`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001e6c4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001e7ab`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001e6c4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18001e7ab`
- `fwbase!FwBaseFree` at `0x18001e8fe`
- `fwbase!FwBaseFree` at `0x18001e8fe`
- `fwbase!FwCloseHandle` at `0x18001e8ea`
- `fwbase!FwCloseHandle` at `0x18001e8ea`
- `fwbase!FwHResultToWindowsError` at `0x18001e602`
- `fwbase!FwHResultToWindowsError` at `0x18001e602`
- `fwbase!FwGetTokenInformation` at `0x18001e5f4`
- `fwbase!FwGetTokenInformation` at `0x18001e5f4`

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
      v15 = 452;
LABEL_8:
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, LastError);
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
          v15 = 454;
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
      v26 = 455;
    }
    else
    {
      LastError = RPC_NetworkIsolationCreateAppContainer((_DWORD)Binding, *v38, a1, a2, a3, a4, a5, a6);
      if ( !LastError )
        goto LABEL_52;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_52;
      v26 = 456;
    }
    WPP_SF_d(*((_QWORD *)v25 + 2), v26, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, LastError);
LABEL_52:
    v7 = v30;
    goto LABEL_53;
  }
  v14 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v15 = 453;
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
0x18001e4a0  mov     r11, rsp
0x18001e4a3  push    rbx
0x18001e4a4  push    rsi
0x18001e4a5  push    r12
0x18001e4a7  push    r13
0x18001e4a9  push    r14
0x18001e4ab  push    r15
0x18001e4ad  sub     rsp, 0A8h
0x18001e4b4  mov     rax, cs:__security_cookie
0x18001e4bb  xor     rax, rsp
0x18001e4be  mov     [rsp+0D8h+var_40], rax
0x18001e4c6  mov     [rsp+0D8h+var_80], r9
0x18001e4cb  mov     [rsp+0D8h+var_78], r8
0x18001e4d0  mov     [rsp+0D8h+var_70], rdx
0x18001e4d5  mov     [rsp+0D8h+var_68], rcx
0x18001e4da  mov     r13, [rsp+0D8h+arg_20]
0x18001e4e2  mov     [rsp+0D8h+var_88], r13
0x18001e4e7  mov     qword ptr [r11-50h], 0
0x18001e4ef  mov     qword ptr [r11-48h], 0
0x18001e4f7  mov     qword ptr [r11-58h], 0
0x18001e4ff  xor     r14d, r14d
0x18001e502  mov     [rsp+0D8h+var_98], r14d
0x18001e507  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18001e50e  nop     dword ptr [rax+rax+00h]
0x18001e513  mov     r12d, eax
0x18001e516  mov     [rsp+0D8h+StringSid], r14
0x18001e51b  call    cs:__imp_GetTickCount64
0x18001e522  nop     dword ptr [rax+rax+00h]
0x18001e527  call    cs:__imp_GetCurrentThread
0x18001e52e  nop     dword ptr [rax+rax+00h]
0x18001e533  mov     rcx, rax; ThreadHandle
0x18001e536  lea     r9, [rsp+0D8h+TokenHandle]; TokenHandle
0x18001e53e  lea     esi, [r14+1]
0x18001e542  mov     r8d, esi; OpenAsSelf
0x18001e545  lea     edx, [rsi+0Bh]; DesiredAccess
0x18001e548  call    cs:__imp_OpenThreadToken
0x18001e54f  nop     dword ptr [rax+rax+00h]
0x18001e554  test    eax, eax
0x18001e556  jnz     short loc_18001E588
0x18001e558  xor     r15d, r15d
0x18001e55b  mov     [rsp+0D8h+var_94], r15d
0x18001e560  call    cs:__imp_GetCurrentProcess
0x18001e567  nop     dword ptr [rax+rax+00h]
0x18001e56c  mov     rcx, rax; ProcessHandle
0x18001e56f  lea     r8, [rsp+0D8h+TokenHandle]; TokenHandle
0x18001e577  lea     edx, [rsi+7]; DesiredAccess
0x18001e57a  call    cs:__imp_OpenProcessToken
0x18001e581  nop     dword ptr [rax+rax+00h]
0x18001e586  jmp     short loc_18001E58F
0x18001e588  mov     r15d, esi
0x18001e58b  mov     [rsp+0D8h+var_94], esi
0x18001e58f  test    eax, eax
0x18001e591  jnz     short loc_18001E5DF
0x18001e593  call    cs:__imp_GetLastError
0x18001e59a  nop     dword ptr [rax+rax+00h]
0x18001e59f  mov     ebx, eax
0x18001e5a1  lea     rax, WPP_GLOBAL_Control
0x18001e5a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e5af  cmp     rcx, rax
0x18001e5b2  jz      loc_18001E8C2
0x18001e5b8  test    [rcx+1Ch], sil
0x18001e5bc  jz      loc_18001E8C2
0x18001e5c2  mov     edx, 1C4h
0x18001e5c7  mov     r9d, ebx
0x18001e5ca  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18001e5d1  mov     rcx, [rcx+10h]
0x18001e5d5  call    WPP_SF_d
0x18001e5da  jmp     loc_18001E8C2
0x18001e5df  xor     r9d, r9d
0x18001e5e2  lea     r8, [rsp+0D8h+var_48]
0x18001e5ea  mov     edx, esi
0x18001e5ec  mov     rcx, [rsp+0D8h+TokenHandle]
0x18001e5f4  call    cs:__imp_FwGetTokenInformation
0x18001e5fb  nop     dword ptr [rax+rax+00h]
0x18001e600  mov     ecx, eax
0x18001e602  call    cs:__imp_FwHResultToWindowsError
0x18001e609  nop     dword ptr [rax+rax+00h]
0x18001e60e  mov     ebx, eax
0x18001e610  test    eax, eax
0x18001e612  jz      short loc_18001E63C
0x18001e614  lea     rax, WPP_GLOBAL_Control
0x18001e61b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e622  cmp     rcx, rax
0x18001e625  jz      loc_18001E8C2
0x18001e62b  test    [rcx+1Ch], sil
0x18001e62f  jz      loc_18001E8C2
0x18001e635  mov     edx, 1C5h
0x18001e63a  jmp     short loc_18001E5C7
0x18001e63c  cmp     r15d, esi
0x18001e63f  jnz     short loc_18001E68E
0x18001e641  call    cs:__imp_RevertToSelf
0x18001e648  nop     dword ptr [rax+rax+00h]
0x18001e64d  test    eax, eax
0x18001e64f  jnz     short loc_18001E68A
0x18001e651  call    cs:__imp_GetLastError
0x18001e658  nop     dword ptr [rax+rax+00h]
0x18001e65d  mov     ebx, eax
0x18001e65f  lea     rax, WPP_GLOBAL_Control
0x18001e666  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e66d  cmp     rcx, rax
0x18001e670  jz      loc_18001E8C2
0x18001e676  test    [rcx+1Ch], sil
0x18001e67a  jz      loc_18001E8C2
0x18001e680  mov     edx, 1C6h
0x18001e685  jmp     loc_18001E5C7
0x18001e68a  mov     [rsp+0D8h+var_98], esi
0x18001e68e  mov     dl, sil
0x18001e691  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AppContainerConnectivityOnWindowsServerContainers@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AppContainerConnectivityOnWindowsServerContainers@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppContainerConnectivityOnWindowsServerContainers> `wil::Feature<__WilFeatureTraits_Feature_AppContainerConnectivityOnWindowsServerContainers>::GetImpl(void)'::`2'::impl
0x18001e698  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_AppContainerConnectivityOnWindowsServerContainers@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AppContainerConnectivityOnWindowsServerContainers>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18001e69d  xor     ebx, ebx
0x18001e69f  test    r12d, r12d
0x18001e6a2  jz      loc_18001E78F
0x18001e6a8  cmp     ebx, [rsp+0D8h+arg_28]
0x18001e6af  jnb     loc_18001E77D
0x18001e6b5  mov     ecx, ebx
0x18001e6b7  add     rcx, rcx
0x18001e6ba  lea     rdx, [rsp+0D8h+StringSid]; StringSid
0x18001e6bf  mov     rcx, [r13+rcx*8+0]; Sid
0x18001e6c4  call    cs:__imp_ConvertSidToStringSidW
0x18001e6cb  nop     dword ptr [rax+rax+00h]
0x18001e6d0  test    eax, eax
0x18001e6d2  jz      short loc_18001E752
0x18001e6d4  mov     rdx, cs:off_180068090; "S-1-15-3-4214768333-1334025770-12240807"...
0x18001e6db  mov     rcx, [rsp+0D8h+StringSid]
0x18001e6e0  call    cs:__imp__o__wcsicmp
0x18001e6e7  nop     dword ptr [rax+rax+00h]
0x18001e6ec  test    eax, eax
0x18001e6ee  jz      short loc_18001E759
0x18001e6f0  xor     r13d, r13d
0x18001e6f3  xor     r12d, r12d
0x18001e6f6  cmp     r12d, 3
0x18001e6fa  jnb     short loc_18001E733
0x18001e6fc  lea     rax, ?networkingSidInfoTable@@3PAPEAGA; ushort * near * networkingSidInfoTable
0x18001e703  mov     rdx, [rax+r12*8]
0x18001e707  mov     rcx, [rsp+0D8h+StringSid]
0x18001e70c  call    cs:__imp__o__wcsicmp
0x18001e713  nop     dword ptr [rax+rax+00h]
0x18001e718  test    eax, eax
0x18001e71a  cmovz   r13d, esi
0x18001e71e  add     r12d, esi
0x18001e721  lea     ecx, [r14+1]
0x18001e725  test    eax, eax
0x18001e727  cmovnz  ecx, r14d
0x18001e72b  mov     r14d, ecx
0x18001e72e  test    r13d, r13d
0x18001e731  jz      short loc_18001E6F6
0x18001e733  mov     rcx, [rsp+0D8h+StringSid]; hMem
0x18001e738  call    cs:__imp_LocalFree
0x18001e73f  nop     dword ptr [rax+rax+00h]
0x18001e744  mov     [rsp+0D8h+StringSid], 0
0x18001e74d  mov     r13, [rsp+0D8h+var_88]
0x18001e752  add     ebx, esi
0x18001e754  jmp     loc_18001E6A8
0x18001e759  mov     rcx, [rsp+0D8h+StringSid]; hMem
0x18001e75e  call    cs:__imp_LocalFree
0x18001e765  nop     dword ptr [rax+rax+00h]
0x18001e76a  mov     [rsp+0D8h+StringSid], 0
0x18001e773  mov     ebx, 32h ; '2'
0x18001e778  jmp     loc_18001E8BD
0x18001e77d  cmp     r14d, 3
0x18001e781  jz      short loc_18001E788
0x18001e783  test    r14d, r14d
0x18001e786  jnz     short loc_18001E773
0x18001e788  xor     ebx, ebx
0x18001e78a  jmp     loc_18001E8BD
0x18001e78f  mov     r14d, [rsp+0D8h+arg_28]
0x18001e797  cmp     ebx, r14d
0x18001e79a  jnb     short loc_18001E7F5
0x18001e79c  mov     ecx, ebx
0x18001e79e  add     rcx, rcx
0x18001e7a1  lea     rdx, [rsp+0D8h+StringSid]; StringSid
0x18001e7a6  mov     rcx, [r13+rcx*8+0]; Sid
0x18001e7ab  call    cs:__imp_ConvertSidToStringSidW
0x18001e7b2  nop     dword ptr [rax+rax+00h]
0x18001e7b7  test    eax, eax
0x18001e7b9  jz      short loc_18001E7F1
0x18001e7bb  lea     rdx, aS1153102482062; "S-1-15-3-1024-820624432-2503302554-1536"...
0x18001e7c2  mov     rcx, [rsp+0D8h+StringSid]
0x18001e7c7  call    cs:__imp__o__wcsicmp
0x18001e7ce  nop     dword ptr [rax+rax+00h]
0x18001e7d3  mov     rcx, [rsp+0D8h+StringSid]; hMem
0x18001e7d8  test    eax, eax
0x18001e7da  jz      short loc_18001E75E
0x18001e7dc  call    cs:__imp_LocalFree
0x18001e7e3  nop     dword ptr [rax+rax+00h]
0x18001e7e8  mov     [rsp+0D8h+StringSid], 0
0x18001e7f1  add     ebx, esi
0x18001e7f3  jmp     short loc_18001E797
0x18001e7f5  lea     rcx, [rsp+0D8h+Binding]
0x18001e7fd  call    Int_FWLocalRpcBindingCreate
0x18001e802  mov     ebx, eax
0x18001e804  test    eax, eax
0x18001e806  jz      short loc_18001E830
0x18001e808  lea     rax, WPP_GLOBAL_Control
0x18001e80f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e816  cmp     rcx, rax
0x18001e819  jz      loc_18001E8BD
0x18001e81f  test    [rcx+1Ch], sil
0x18001e823  jz      loc_18001E8BD
0x18001e829  mov     edx, 1C7h
0x18001e82e  jmp     short loc_18001E8AA
0x18001e830  mov     [rsp+0D8h+var_A0], r14d
0x18001e835  mov     [rsp+0D8h+var_A8], r13
0x18001e83a  mov     rax, [rsp+0D8h+var_80]
0x18001e83f  mov     [rsp+0D8h+var_B0], rax
0x18001e844  mov     rax, [rsp+0D8h+var_78]
0x18001e849  mov     [rsp+0D8h+var_B8], rax
0x18001e84e  mov     r9, [rsp+0D8h+var_70]
0x18001e853  mov     r8, [rsp+0D8h+var_68]
0x18001e858  mov     rdx, [rsp+0D8h+var_48]
0x18001e860  mov     rdx, [rdx]
0x18001e863  mov     rcx, [rsp+0D8h+Binding]
0x18001e86b  call    RPC_NetworkIsolationCreateAppContainer
0x18001e870  mov     ebx, eax
0x18001e872  mov     [rsp+0D8h+var_90], eax
0x18001e876  jmp     short loc_18001E888
0x18001e878  mov     ebx, eax
0x18001e87a  mov     [rsp+0D8h+var_90], eax
0x18001e87e  mov     esi, 1
0x18001e883  mov     r15d, [rsp+0D8h+var_94]
0x18001e888  test    ebx, ebx
0x18001e88a  jz      short loc_18001E8BD
0x18001e88c  lea     rax, WPP_GLOBAL_Control
0x18001e893  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e89a  cmp     rcx, rax
0x18001e89d  jz      short loc_18001E8BD
0x18001e89f  test    [rcx+1Ch], sil
0x18001e8a3  jz      short loc_18001E8BD
0x18001e8a5  mov     edx, 1C8h
0x18001e8aa  mov     r9d, ebx
0x18001e8ad  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18001e8b4  mov     rcx, [rcx+10h]
0x18001e8b8  call    WPP_SF_d
0x18001e8bd  mov     r14d, [rsp+0D8h+var_98]
0x18001e8c2  cmp     r15d, esi
0x18001e8c5  jnz     short loc_18001E8E2
0x18001e8c7  cmp     r14d, esi
0x18001e8ca  jnz     short loc_18001E8E2
0x18001e8cc  mov     rdx, [rsp+0D8h+TokenHandle]; Token
0x18001e8d4  xor     ecx, ecx; Thread
0x18001e8d6  call    cs:__imp_SetThreadToken
0x18001e8dd  nop     dword ptr [rax+rax+00h]
0x18001e8e2  mov     rcx, [rsp+0D8h+TokenHandle]
0x18001e8ea  call    cs:__imp_FwCloseHandle
0x18001e8f1  nop     dword ptr [rax+rax+00h]
0x18001e8f6  mov     rcx, [rsp+0D8h+var_48]
0x18001e8fe  call    cs:__imp_FwBaseFree
0x18001e905  nop     dword ptr [rax+rax+00h]
0x18001e90a  cmp     [rsp+0D8h+Binding], 0
0x18001e913  jz      short loc_18001E934
0x18001e915  lea     rcx, [rsp+0D8h+Binding]; Binding
0x18001e91d  call    cs:__imp_RpcBindingFree
0x18001e924  nop     dword ptr [rax+rax+00h]
0x18001e929  test    eax, eax
0x18001e92b  jz      short loc_18001E934
0x18001e92d  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree")
0x18001e92f  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001e934  mov     eax, ebx
0x18001e936  mov     rcx, [rsp+0D8h+var_40]
0x18001e93e  xor     rcx, rsp; StackCookie
0x18001e941  call    __security_check_cookie
0x18001e946  add     rsp, 0A8h
0x18001e94d  pop     r15
0x18001e94f  pop     r14
0x18001e951  pop     r13
0x18001e953  pop     r12
0x18001e955  pop     rsi
0x18001e956  pop     rbx
0x18001e957  retn
0x18005fc76  push    rbp
0x18005fc78  sub     rsp, 40h
0x18005fc7c  mov     rbp, rdx
0x18005fc7f  mov     rcx, [rcx]
0x18005fc82  mov     ecx, [rcx]; ExceptionCode
0x18005fc84  call    cs:__imp_RpcExceptionFilter
0x18005fc8b  nop     dword ptr [rax+rax+00h]
0x18005fc90  nop
0x18005fc91  add     rsp, 40h
0x18005fc95  pop     rbp
0x18005fc96  retn
```
