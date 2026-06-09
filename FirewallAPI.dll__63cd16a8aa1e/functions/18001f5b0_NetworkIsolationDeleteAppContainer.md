# NetworkIsolationDeleteAppContainer

- ea: `0x18001f5b0`
- end: `0x18001f875`
- name: `NetworkIsolationDeleteAppContainer`
- size: `709`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005954`
- `0x18000e960`
- `0x18001f5b0`
- `0x180024c3c`
- `0x1800277b0`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005bab4`
- `RPCRT4!RpcExceptionFilter` at `0x18005bab4`
- `RPCRT4!NdrClientCall3` at `0x18001f7a4`
- `RPCRT4!NdrClientCall3` at `0x18001f7a4`
- `RPCRT4!RpcBindingFree` at `0x18001f83c`
- `RPCRT4!RpcBindingFree` at `0x18001f83c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f65b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f6eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f65b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f6eb`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18001f5fe`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x18001f5fe`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001f6e1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001f6e1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f813`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001f813`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f60d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001f60d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001f648`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001f648`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f637`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001f637`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f625`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001f625`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001f607`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001f607`
- `fwbase!FwBaseFree` at `0x18001f829`
- `fwbase!FwBaseFree` at `0x18001f829`
- `fwbase!FwCloseHandle` at `0x18001f81e`
- `fwbase!FwCloseHandle` at `0x18001f81e`
- `fwbase!FwHResultToWindowsError` at `0x18001f6a5`
- `fwbase!FwHResultToWindowsError` at `0x18001f6a5`
- `fwbase!FwGetTokenInformation` at `0x18001f69d`
- `fwbase!FwGetTokenInformation` at `0x18001f69d`

## pseudocode

```c
__int64 __fastcall NetworkIsolationDeleteAppContainer(__int64 a1, __int64 a2)
{
  int v3; // r15d
  int CurrentServiceSessionId; // r12d
  HANDLE CurrentThread; // rax
  BOOL v6; // eax
  int v7; // r14d
  HANDLE CurrentProcess; // rax
  DWORD LastError; // ebx
  FwPolicy2 *v10; // rcx
  __int64 v11; // rdx
  unsigned int TokenInformation; // eax
  unsigned int v13; // eax
  __int64 v14; // rcx
  void *TokenHandle; // [rsp+60h] [rbp-48h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp-40h] BYREF
  _QWORD *v19; // [rsp+70h] [rbp-38h] BYREF

  Binding = 0;
  v19 = 0;
  TokenHandle = 0;
  v3 = 0;
  CurrentServiceSessionId = RtlGetCurrentServiceSessionId();
  GetTickCount64();
  CurrentThread = GetCurrentThread();
  v6 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  if ( v6 )
  {
    v7 = 1;
  }
  else
  {
    v7 = 0;
    CurrentProcess = GetCurrentProcess();
    v6 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  }
  if ( v6 )
  {
    TokenInformation = FwGetTokenInformation(TokenHandle, 1, &v19, 0);
    LastError = FwHResultToWindowsError(TokenInformation);
    if ( !LastError )
    {
      if ( v7 == 1 )
      {
        if ( !RevertToSelf() )
        {
          LastError = GetLastError();
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 460;
            goto LABEL_28;
          }
          goto LABEL_29;
        }
        v3 = 1;
      }
      LastError = Int_FWLocalRpcBindingCreate(&Binding);
      if ( CurrentServiceSessionId )
      {
        LastError = 0;
      }
      else if ( LastError )
      {
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v11 = 461;
          goto LABEL_28;
        }
      }
      else
      {
        LastError = (unsigned int)NdrClientCall3(
                                    (MIDL_STUBLESS_PROXY_INFO *)&FW_NET_ISO_DIAG_ProxyInfo,
                                    7u,
                                    0,
                                    Binding,
                                    *v19,
                                    a1,
                                    a2).Pointer;
        if ( LastError )
        {
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v11 = 462;
            goto LABEL_28;
          }
        }
      }
      goto LABEL_29;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 459;
      goto LABEL_28;
    }
  }
  else
  {
    LastError = GetLastError();
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 458;
LABEL_28:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, LastError);
    }
  }
LABEL_29:
  if ( v7 == 1 && v3 == 1 )
    SetThreadToken(0, TokenHandle);
  FwCloseHandle(TokenHandle);
  FwBaseFree(v19);
  if ( Binding )
  {
    v13 = RpcBindingFree(&Binding);
    if ( v13 )
      MicrosoftTelemetryAssertTriggeredArgs(v14, v13);
  }
  return LastError;
}

```

## disassembly

```asm
0x18001f5b0  mov     r11, rsp
0x18001f5b3  mov     [r11+18h], rbx
0x18001f5b7  push    rsi
0x18001f5b8  push    r12
0x18001f5ba  push    r13
0x18001f5bc  push    r14
0x18001f5be  push    r15
0x18001f5c0  sub     rsp, 80h
0x18001f5c7  mov     rax, cs:__security_cookie
0x18001f5ce  xor     rax, rsp
0x18001f5d1  mov     [rsp+0A8h+var_30], rax
0x18001f5d6  mov     [rsp+0A8h+var_58], rdx
0x18001f5db  mov     r13, rcx
0x18001f5de  mov     qword ptr [r11-40h], 0
0x18001f5e6  mov     qword ptr [r11-38h], 0
0x18001f5ee  mov     qword ptr [r11-48h], 0
0x18001f5f6  xor     r15d, r15d
0x18001f5f9  mov     [rsp+0A8h+var_64], r15d
0x18001f5fe  call    cs:__imp_RtlGetCurrentServiceSessionId
0x18001f604  mov     r12d, eax
0x18001f607  call    cs:__imp_GetTickCount64
0x18001f60d  call    cs:__imp_GetCurrentThread
0x18001f613  mov     rcx, rax; ThreadHandle
0x18001f616  lea     r9, [rsp+0A8h+TokenHandle]; TokenHandle
0x18001f61b  lea     esi, [r15+1]
0x18001f61f  mov     r8d, esi; OpenAsSelf
0x18001f622  lea     edx, [rsi+0Bh]; DesiredAccess
0x18001f625  call    cs:__imp_OpenThreadToken
0x18001f62b  test    eax, eax
0x18001f62d  jnz     short loc_18001F650
0x18001f62f  xor     r14d, r14d
0x18001f632  mov     [rsp+0A8h+var_68], r14d
0x18001f637  call    cs:__imp_GetCurrentProcess
0x18001f63d  mov     rcx, rax; ProcessHandle
0x18001f640  lea     r8, [rsp+0A8h+TokenHandle]; TokenHandle
0x18001f645  lea     edx, [rsi+7]; DesiredAccess
0x18001f648  call    cs:__imp_OpenProcessToken
0x18001f64e  jmp     short loc_18001F657
0x18001f650  mov     r14d, esi
0x18001f653  mov     [rsp+0A8h+var_68], esi
0x18001f657  test    eax, eax
0x18001f659  jnz     short loc_18001F68E
0x18001f65b  call    cs:__imp_GetLastError
0x18001f661  mov     ebx, eax
0x18001f663  lea     rax, WPP_GLOBAL_Control
0x18001f66a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f671  cmp     rcx, rax
0x18001f674  jz      loc_18001F802
0x18001f67a  test    [rcx+1Ch], sil
0x18001f67e  jz      loc_18001F802
0x18001f684  mov     edx, 1CAh
0x18001f689  jmp     loc_18001F7EF
0x18001f68e  xor     r9d, r9d
0x18001f691  lea     r8, [rsp+0A8h+var_38]
0x18001f696  mov     edx, esi
0x18001f698  mov     rcx, [rsp+0A8h+TokenHandle]
0x18001f69d  call    cs:__imp_FwGetTokenInformation
0x18001f6a3  mov     ecx, eax
0x18001f6a5  call    cs:__imp_FwHResultToWindowsError
0x18001f6ab  mov     ebx, eax
0x18001f6ad  test    eax, eax
0x18001f6af  jz      short loc_18001F6DC
0x18001f6b1  lea     rax, WPP_GLOBAL_Control
0x18001f6b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f6bf  cmp     rcx, rax
0x18001f6c2  jz      loc_18001F802
0x18001f6c8  test    [rcx+1Ch], sil
0x18001f6cc  jz      loc_18001F802
0x18001f6d2  mov     edx, 1CBh
0x18001f6d7  jmp     loc_18001F7EF
0x18001f6dc  cmp     r14d, esi
0x18001f6df  jnz     short loc_18001F725
0x18001f6e1  call    cs:__imp_RevertToSelf
0x18001f6e7  test    eax, eax
0x18001f6e9  jnz     short loc_18001F71E
0x18001f6eb  call    cs:__imp_GetLastError
0x18001f6f1  mov     ebx, eax
0x18001f6f3  lea     rax, WPP_GLOBAL_Control
0x18001f6fa  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f701  cmp     rcx, rax
0x18001f704  jz      loc_18001F802
0x18001f70a  test    [rcx+1Ch], sil
0x18001f70e  jz      loc_18001F802
0x18001f714  mov     edx, 1CCh
0x18001f719  jmp     loc_18001F7EF
0x18001f71e  mov     r15d, esi
0x18001f721  mov     [rsp+0A8h+var_64], esi
0x18001f725  lea     rcx, [rsp+0A8h+Binding]
0x18001f72a  call    Int_FWLocalRpcBindingCreate
0x18001f72f  mov     ebx, eax
0x18001f731  test    r12d, r12d
0x18001f734  jz      short loc_18001F73D
0x18001f736  xor     ebx, ebx
0x18001f738  jmp     loc_18001F802
0x18001f73d  test    ebx, ebx
0x18001f73f  jz      short loc_18001F76C
0x18001f741  lea     rax, WPP_GLOBAL_Control
0x18001f748  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f74f  cmp     rcx, rax
0x18001f752  jz      loc_18001F802
0x18001f758  test    [rcx+1Ch], sil
0x18001f75c  jz      loc_18001F802
0x18001f762  mov     edx, 1CDh
0x18001f767  jmp     loc_18001F7EF
0x18001f76c  mov     rax, [rsp+0A8h+var_38]
0x18001f771  mov     rcx, [rax]
0x18001f774  mov     [rsp+0A8h+var_50], 0
0x18001f77d  mov     rax, [rsp+0A8h+var_58]
0x18001f782  mov     [rsp+0A8h+var_78], rax
0x18001f787  mov     [rsp+0A8h+var_80], r13
0x18001f78c  mov     [rsp+0A8h+var_88], rcx
0x18001f791  mov     r9, [rsp+0A8h+Binding]
0x18001f796  xor     r8d, r8d; pReturnValue
0x18001f799  lea     edx, [r8+7]; nProcNum
0x18001f79d  lea     rcx, ?FW_NET_ISO_DIAG_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001f7a4  call    cs:__imp_NdrClientCall3
0x18001f7aa  mov     rbx, rax
0x18001f7ad  mov     [rsp+0A8h+var_50], rax
0x18001f7b2  mov     [rsp+0A8h+var_60], eax
0x18001f7b6  jmp     short loc_18001F7CD
0x18001f7b8  mov     ebx, eax
0x18001f7ba  mov     [rsp+0A8h+var_60], eax
0x18001f7be  mov     esi, 1
0x18001f7c3  mov     r14d, [rsp+0A8h+var_68]
0x18001f7c8  mov     r15d, [rsp+0A8h+var_64]
0x18001f7cd  test    ebx, ebx
0x18001f7cf  jz      short loc_18001F802
0x18001f7d1  lea     rax, WPP_GLOBAL_Control
0x18001f7d8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f7df  cmp     rcx, rax
0x18001f7e2  jz      short loc_18001F802
0x18001f7e4  test    [rcx+1Ch], sil
0x18001f7e8  jz      short loc_18001F802
0x18001f7ea  mov     edx, 1CEh
0x18001f7ef  mov     r9d, ebx
0x18001f7f2  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18001f7f9  mov     rcx, [rcx+10h]
0x18001f7fd  call    WPP_SF_d
0x18001f802  cmp     r14d, esi
0x18001f805  jnz     short loc_18001F819
0x18001f807  cmp     r15d, esi
0x18001f80a  jnz     short loc_18001F819
0x18001f80c  mov     rdx, [rsp+0A8h+TokenHandle]; Token
0x18001f811  xor     ecx, ecx; Thread
0x18001f813  call    cs:__imp_SetThreadToken
0x18001f819  mov     rcx, [rsp+0A8h+TokenHandle]
0x18001f81e  call    cs:__imp_FwCloseHandle
0x18001f824  mov     rcx, [rsp+0A8h+var_38]
0x18001f829  call    cs:__imp_FwBaseFree
0x18001f82f  cmp     [rsp+0A8h+Binding], 0
0x18001f835  jz      short loc_18001F84D
0x18001f837  lea     rcx, [rsp+0A8h+Binding]; Binding
0x18001f83c  call    cs:__imp_RpcBindingFree
0x18001f842  test    eax, eax
0x18001f844  jz      short loc_18001F84D
0x18001f846  mov     edx, eax
0x18001f848  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001f84d  mov     eax, ebx
0x18001f84f  mov     rcx, [rsp+0A8h+var_30]
0x18001f854  xor     rcx, rsp; StackCookie
0x18001f857  call    __security_check_cookie
0x18001f85c  mov     rbx, [rsp+0A8h+arg_10]
0x18001f864  add     rsp, 80h
0x18001f86b  pop     r15
0x18001f86d  pop     r14
0x18001f86f  pop     r13
0x18001f871  pop     r12
0x18001f873  pop     rsi
0x18001f874  retn
0x18005baa6  push    rbp
0x18005baa8  sub     rsp, 40h
0x18005baac  mov     rbp, rdx
0x18005baaf  mov     rcx, [rcx]
0x18005bab2  mov     ecx, [rcx]; ExceptionCode
0x18005bab4  call    cs:__imp_RpcExceptionFilter
0x18005baba  nop
0x18005babb  add     rsp, 40h
0x18005babf  pop     rbp
0x18005bac0  retn
```
