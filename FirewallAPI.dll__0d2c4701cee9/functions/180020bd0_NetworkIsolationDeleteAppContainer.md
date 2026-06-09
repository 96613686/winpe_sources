# NetworkIsolationDeleteAppContainer

- ea: `0x180020bd0`
- end: `0x180020ef6`
- name: `NetworkIsolationDeleteAppContainer`
- size: `806`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180005e0c`
- `0x18000ea10`
- `0x180020bd0`
- `0x180026798`
- `0x1800294b0`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005fcf8`
- `RPCRT4!RpcExceptionFilter` at `0x18005fcf8`
- `RPCRT4!NdrClientCall3` at `0x180020e06`
- `RPCRT4!NdrClientCall3` at `0x180020e06`
- `RPCRT4!RpcBindingFree` at `0x180020eb6`
- `RPCRT4!RpcBindingFree` at `0x180020eb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020c9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020d47`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180020c1e`
- `ntdll!RtlGetCurrentServiceSessionId` at `0x180020c1e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180020d37`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180020d37`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180020e7b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180020e7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020c39`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180020c39`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020c86`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180020c86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020c6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180020c6f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020c57`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180020c57`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180020c2d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180020c2d`
- `fwbase!FwBaseFree` at `0x180020e9d`
- `fwbase!FwBaseFree` at `0x180020e9d`
- `fwbase!FwCloseHandle` at `0x180020e8c`
- `fwbase!FwCloseHandle` at `0x180020e8c`
- `fwbase!FwHResultToWindowsError` at `0x180020cf5`
- `fwbase!FwHResultToWindowsError` at `0x180020cf5`
- `fwbase!FwGetTokenInformation` at `0x180020ce7`
- `fwbase!FwGetTokenInformation` at `0x180020ce7`

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
            v11 = 459;
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
          v11 = 460;
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
            v11 = 461;
            goto LABEL_28;
          }
        }
      }
      goto LABEL_29;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 458;
      goto LABEL_28;
    }
  }
  else
  {
    LastError = GetLastError();
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v11 = 457;
LABEL_28:
      WPP_SF_d(*((_QWORD *)v10 + 2), v11, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, LastError);
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
0x180020bd0  mov     r11, rsp
0x180020bd3  mov     [r11+18h], rbx
0x180020bd7  push    rsi
0x180020bd8  push    r12
0x180020bda  push    r13
0x180020bdc  push    r14
0x180020bde  push    r15
0x180020be0  sub     rsp, 80h
0x180020be7  mov     rax, cs:__security_cookie
0x180020bee  xor     rax, rsp
0x180020bf1  mov     [rsp+0A8h+var_30], rax
0x180020bf6  mov     [rsp+0A8h+var_58], rdx
0x180020bfb  mov     r13, rcx
0x180020bfe  mov     qword ptr [r11-40h], 0
0x180020c06  mov     qword ptr [r11-38h], 0
0x180020c0e  mov     qword ptr [r11-48h], 0
0x180020c16  xor     r15d, r15d
0x180020c19  mov     [rsp+0A8h+var_64], r15d
0x180020c1e  call    cs:__imp_RtlGetCurrentServiceSessionId
0x180020c25  nop     dword ptr [rax+rax+00h]
0x180020c2a  mov     r12d, eax
0x180020c2d  call    cs:__imp_GetTickCount64
0x180020c34  nop     dword ptr [rax+rax+00h]
0x180020c39  call    cs:__imp_GetCurrentThread
0x180020c40  nop     dword ptr [rax+rax+00h]
0x180020c45  mov     rcx, rax; ThreadHandle
0x180020c48  lea     r9, [rsp+0A8h+TokenHandle]; TokenHandle
0x180020c4d  lea     esi, [r15+1]
0x180020c51  mov     r8d, esi; OpenAsSelf
0x180020c54  lea     edx, [rsi+0Bh]; DesiredAccess
0x180020c57  call    cs:__imp_OpenThreadToken
0x180020c5e  nop     dword ptr [rax+rax+00h]
0x180020c63  test    eax, eax
0x180020c65  jnz     short loc_180020C94
0x180020c67  xor     r14d, r14d
0x180020c6a  mov     [rsp+0A8h+var_68], r14d
0x180020c6f  call    cs:__imp_GetCurrentProcess
0x180020c76  nop     dword ptr [rax+rax+00h]
0x180020c7b  mov     rcx, rax; ProcessHandle
0x180020c7e  lea     r8, [rsp+0A8h+TokenHandle]; TokenHandle
0x180020c83  lea     edx, [rsi+7]; DesiredAccess
0x180020c86  call    cs:__imp_OpenProcessToken
0x180020c8d  nop     dword ptr [rax+rax+00h]
0x180020c92  jmp     short loc_180020C9B
0x180020c94  mov     r14d, esi
0x180020c97  mov     [rsp+0A8h+var_68], esi
0x180020c9b  test    eax, eax
0x180020c9d  jnz     short loc_180020CD8
0x180020c9f  call    cs:__imp_GetLastError
0x180020ca6  nop     dword ptr [rax+rax+00h]
0x180020cab  mov     ebx, eax
0x180020cad  lea     rax, WPP_GLOBAL_Control
0x180020cb4  mov     rcx, cs:WPP_GLOBAL_Control
0x180020cbb  cmp     rcx, rax
0x180020cbe  jz      loc_180020E6A
0x180020cc4  test    [rcx+1Ch], sil
0x180020cc8  jz      loc_180020E6A
0x180020cce  mov     edx, 1C9h
0x180020cd3  jmp     loc_180020E57
0x180020cd8  xor     r9d, r9d
0x180020cdb  lea     r8, [rsp+0A8h+var_38]
0x180020ce0  mov     edx, esi
0x180020ce2  mov     rcx, [rsp+0A8h+TokenHandle]
0x180020ce7  call    cs:__imp_FwGetTokenInformation
0x180020cee  nop     dword ptr [rax+rax+00h]
0x180020cf3  mov     ecx, eax
0x180020cf5  call    cs:__imp_FwHResultToWindowsError
0x180020cfc  nop     dword ptr [rax+rax+00h]
0x180020d01  mov     ebx, eax
0x180020d03  test    eax, eax
0x180020d05  jz      short loc_180020D32
0x180020d07  lea     rax, WPP_GLOBAL_Control
0x180020d0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d15  cmp     rcx, rax
0x180020d18  jz      loc_180020E6A
0x180020d1e  test    [rcx+1Ch], sil
0x180020d22  jz      loc_180020E6A
0x180020d28  mov     edx, 1CAh
0x180020d2d  jmp     loc_180020E57
0x180020d32  cmp     r14d, esi
0x180020d35  jnz     short loc_180020D87
0x180020d37  call    cs:__imp_RevertToSelf
0x180020d3e  nop     dword ptr [rax+rax+00h]
0x180020d43  test    eax, eax
0x180020d45  jnz     short loc_180020D80
0x180020d47  call    cs:__imp_GetLastError
0x180020d4e  nop     dword ptr [rax+rax+00h]
0x180020d53  mov     ebx, eax
0x180020d55  lea     rax, WPP_GLOBAL_Control
0x180020d5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d63  cmp     rcx, rax
0x180020d66  jz      loc_180020E6A
0x180020d6c  test    [rcx+1Ch], sil
0x180020d70  jz      loc_180020E6A
0x180020d76  mov     edx, 1CBh
0x180020d7b  jmp     loc_180020E57
0x180020d80  mov     r15d, esi
0x180020d83  mov     [rsp+0A8h+var_64], esi
0x180020d87  lea     rcx, [rsp+0A8h+Binding]
0x180020d8c  call    Int_FWLocalRpcBindingCreate
0x180020d91  mov     ebx, eax
0x180020d93  test    r12d, r12d
0x180020d96  jz      short loc_180020D9F
0x180020d98  xor     ebx, ebx
0x180020d9a  jmp     loc_180020E6A
0x180020d9f  test    ebx, ebx
0x180020da1  jz      short loc_180020DCE
0x180020da3  lea     rax, WPP_GLOBAL_Control
0x180020daa  mov     rcx, cs:WPP_GLOBAL_Control
0x180020db1  cmp     rcx, rax
0x180020db4  jz      loc_180020E6A
0x180020dba  test    [rcx+1Ch], sil
0x180020dbe  jz      loc_180020E6A
0x180020dc4  mov     edx, 1CCh
0x180020dc9  jmp     loc_180020E57
0x180020dce  mov     rax, [rsp+0A8h+var_38]
0x180020dd3  mov     rcx, [rax]
0x180020dd6  mov     [rsp+0A8h+var_50], 0
0x180020ddf  mov     rax, [rsp+0A8h+var_58]
0x180020de4  mov     [rsp+0A8h+var_78], rax
0x180020de9  mov     [rsp+0A8h+var_80], r13
0x180020dee  mov     [rsp+0A8h+var_88], rcx
0x180020df3  mov     r9, [rsp+0A8h+Binding]
0x180020df8  xor     r8d, r8d; pReturnValue
0x180020dfb  lea     edx, [r8+7]; nProcNum
0x180020dff  lea     rcx, ?FW_NET_ISO_DIAG_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180020e06  call    cs:__imp_NdrClientCall3
0x180020e0d  nop     dword ptr [rax+rax+00h]
0x180020e12  mov     rbx, rax
0x180020e15  mov     [rsp+0A8h+var_50], rax
0x180020e1a  mov     [rsp+0A8h+var_60], eax
0x180020e1e  jmp     short loc_180020E35
0x180020e20  mov     ebx, eax
0x180020e22  mov     [rsp+0A8h+var_60], eax
0x180020e26  mov     esi, 1
0x180020e2b  mov     r14d, [rsp+0A8h+var_68]
0x180020e30  mov     r15d, [rsp+0A8h+var_64]
0x180020e35  test    ebx, ebx
0x180020e37  jz      short loc_180020E6A
0x180020e39  lea     rax, WPP_GLOBAL_Control
0x180020e40  mov     rcx, cs:WPP_GLOBAL_Control
0x180020e47  cmp     rcx, rax
0x180020e4a  jz      short loc_180020E6A
0x180020e4c  test    [rcx+1Ch], sil
0x180020e50  jz      short loc_180020E6A
0x180020e52  mov     edx, 1CDh
0x180020e57  mov     r9d, ebx
0x180020e5a  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180020e61  mov     rcx, [rcx+10h]
0x180020e65  call    WPP_SF_d
0x180020e6a  cmp     r14d, esi
0x180020e6d  jnz     short loc_180020E87
0x180020e6f  cmp     r15d, esi
0x180020e72  jnz     short loc_180020E87
0x180020e74  mov     rdx, [rsp+0A8h+TokenHandle]; Token
0x180020e79  xor     ecx, ecx; Thread
0x180020e7b  call    cs:__imp_SetThreadToken
0x180020e82  nop     dword ptr [rax+rax+00h]
0x180020e87  mov     rcx, [rsp+0A8h+TokenHandle]
0x180020e8c  call    cs:__imp_FwCloseHandle
0x180020e93  nop     dword ptr [rax+rax+00h]
0x180020e98  mov     rcx, [rsp+0A8h+var_38]
0x180020e9d  call    cs:__imp_FwBaseFree
0x180020ea4  nop     dword ptr [rax+rax+00h]
0x180020ea9  cmp     [rsp+0A8h+Binding], 0
0x180020eaf  jz      short loc_180020ECD
0x180020eb1  lea     rcx, [rsp+0A8h+Binding]; Binding
0x180020eb6  call    cs:__imp_RpcBindingFree
0x180020ebd  nop     dword ptr [rax+rax+00h]
0x180020ec2  test    eax, eax
0x180020ec4  jz      short loc_180020ECD
0x180020ec6  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree")
0x180020ec8  call    MicrosoftTelemetryAssertTriggeredArgs
0x180020ecd  mov     eax, ebx
0x180020ecf  mov     rcx, [rsp+0A8h+var_30]
0x180020ed4  xor     rcx, rsp; StackCookie
0x180020ed7  call    __security_check_cookie
0x180020edc  mov     rbx, [rsp+0A8h+arg_10]
0x180020ee4  add     rsp, 80h
0x180020eeb  pop     r15
0x180020eed  pop     r14
0x180020eef  pop     r13
0x180020ef1  pop     r12
0x180020ef3  pop     rsi
0x180020ef4  retn
0x18005fcea  push    rbp
0x18005fcec  sub     rsp, 40h
0x18005fcf0  mov     rbp, rdx
0x18005fcf3  mov     rcx, [rcx]
0x18005fcf6  mov     ecx, [rcx]; ExceptionCode
0x18005fcf8  call    cs:__imp_RpcExceptionFilter
0x18005fcff  nop     dword ptr [rax+rax+00h]
0x18005fd04  nop
0x18005fd05  add     rsp, 40h
0x18005fd09  pop     rbp
0x18005fd0a  retn
```
