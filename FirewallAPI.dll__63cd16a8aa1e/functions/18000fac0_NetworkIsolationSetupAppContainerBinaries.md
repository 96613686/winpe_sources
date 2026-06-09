# NetworkIsolationSetupAppContainerBinaries

- ea: `0x18000fac0`
- end: `0x18000fe28`
- name: `NetworkIsolationSetupAppContainerBinaries`
- size: `872`
- prototype: `HRESULT __stdcall(PSID applicationContainerSid, LPCWSTR packageFullName, LPCWSTR packageFolder, LPCWSTR displayName, BOOL bBinariesFullyComputed, LPCWSTR *binaries, DWORD binariesCount)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180005954`
- `0x18000e960`
- `0x18000fac0`
- `0x180024c3c`
- `0x1800277b0`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005b912`
- `RPCRT4!RpcExceptionFilter` at `0x18005b912`
- `RPCRT4!NdrClientCall3` at `0x18000fc23`
- `RPCRT4!NdrClientCall3` at `0x18000fc23`
- `RPCRT4!RpcBindingFree` at `0x18000fe0e`
- `RPCRT4!RpcBindingFree` at `0x18000fe0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd46`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fcb3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000fd46`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000fd3c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18000fd3c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000fdfb`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000fdfb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000fb2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000fb2c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000fd31`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000fd31`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000fd1c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000fd1c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000fb47`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18000fb47`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fb26`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000fb26`
- `fwbase!FwBaseFree` at `0x18000fc76`
- `fwbase!FwBaseFree` at `0x18000fc76`
- `fwbase!FwCloseHandle` at `0x18000fc68`
- `fwbase!FwCloseHandle` at `0x18000fc68`
- `fwbase!FwHResultToWindowsError` at `0x18000fb81`
- `fwbase!FwHResultToWindowsError` at `0x18000fb81`
- `fwbase!FwGetTokenInformation` at `0x18000fb79`
- `fwbase!FwGetTokenInformation` at `0x18000fb79`

## pseudocode

```c
HRESULT __stdcall NetworkIsolationSetupAppContainerBinaries(
        PSID applicationContainerSid,
        LPCWSTR packageFullName,
        LPCWSTR packageFolder,
        LPCWSTR displayName,
        BOOL bBinariesFullyComputed,
        LPCWSTR *binaries,
        DWORD binariesCount)
{
  int v9; // r15d
  HANDLE CurrentThread; // rax
  BOOL v11; // eax
  int v12; // r14d
  unsigned int TokenInformation; // eax
  HRESULT LastError; // ebx
  FwPolicy2 *v16; // rcx
  __int64 v17; // rdx
  HANDLE CurrentProcess; // rax
  unsigned int v19; // eax
  __int64 v20; // rcx
  __int64 v21; // [rsp+60h] [rbp-88h]
  void *TokenHandle; // [rsp+90h] [rbp-58h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp-50h] BYREF
  _QWORD *v26; // [rsp+A0h] [rbp-48h] BYREF

  Binding = 0;
  v26 = 0;
  TokenHandle = 0;
  v9 = 0;
  HIDWORD(v21) = 0;
  GetTickCount64();
  CurrentThread = GetCurrentThread();
  v11 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  if ( v11 )
  {
    v12 = 1;
    LODWORD(v21) = 1;
  }
  else
  {
    v12 = 0;
    LODWORD(v21) = 0;
    CurrentProcess = GetCurrentProcess();
    v11 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  }
  if ( !v11 )
  {
    LastError = GetLastError();
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_8;
    v17 = 467;
LABEL_31:
    WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, (unsigned int)LastError);
    goto LABEL_8;
  }
  TokenInformation = FwGetTokenInformation(TokenHandle, 1, &v26, 0);
  LastError = FwHResultToWindowsError(TokenInformation);
  if ( LastError )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_8;
    v17 = 468;
    goto LABEL_31;
  }
  if ( v12 != 1 )
    goto LABEL_6;
  if ( !RevertToSelf() )
  {
    LastError = GetLastError();
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_8;
    v17 = 469;
    goto LABEL_31;
  }
  v9 = 1;
  HIDWORD(v21) = 1;
LABEL_6:
  LastError = Int_FWLocalRpcBindingCreate(&Binding);
  if ( LastError )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_8;
    v17 = 470;
    goto LABEL_31;
  }
  LastError = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&FW_RESOURCE_INDICATION_ProxyInfo,
                              7u,
                              0,
                              Binding,
                              *v26,
                              applicationContainerSid,
                              packageFullName,
                              packageFolder,
                              displayName,
                              bBinariesFullyComputed,
                              binaries,
                              binariesCount,
                              v21).Pointer;
  if ( LastError )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 471;
      goto LABEL_31;
    }
  }
LABEL_8:
  if ( v12 == 1 && v9 == 1 )
    SetThreadToken(0, TokenHandle);
  FwCloseHandle(TokenHandle);
  FwBaseFree(v26);
  if ( Binding )
  {
    v19 = RpcBindingFree(&Binding);
    if ( v19 )
      MicrosoftTelemetryAssertTriggeredArgs(v20, v19);
  }
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0x80070000;
  return LastError;
}

```

## disassembly

```asm
0x18000fac0  mov     r11, rsp
0x18000fac3  push    rbx
0x18000fac4  push    rdi
0x18000fac5  push    r12
0x18000fac7  push    r13
0x18000fac9  push    r14
0x18000facb  push    r15
0x18000facd  sub     rsp, 0B8h
0x18000fad4  mov     rax, cs:__security_cookie
0x18000fadb  xor     rax, rsp
0x18000fade  mov     [rsp+0E8h+var_40], rax
0x18000fae6  mov     [rsp+0E8h+var_70], r9
0x18000faeb  mov     [rsp+0E8h+var_68], r8
0x18000faf3  mov     r13, rdx
0x18000faf6  mov     r12, rcx
0x18000faf9  mov     rax, [rsp+0E8h+binaries]
0x18000fb01  mov     [rsp+0E8h+var_78], rax
0x18000fb06  mov     qword ptr [r11-50h], 0
0x18000fb0e  mov     qword ptr [r11-48h], 0
0x18000fb16  mov     qword ptr [r11-58h], 0
0x18000fb1e  xor     r15d, r15d
0x18000fb21  mov     [rsp+0E8h+var_84], r15d
0x18000fb26  call    cs:__imp_GetTickCount64
0x18000fb2c  call    cs:__imp_GetCurrentThread
0x18000fb32  mov     rcx, rax; ThreadHandle
0x18000fb35  lea     r9, [rsp+0E8h+TokenHandle]; TokenHandle
0x18000fb3d  lea     edi, [r15+1]
0x18000fb41  mov     r8d, edi; OpenAsSelf
0x18000fb44  lea     edx, [rdi+0Bh]; DesiredAccess
0x18000fb47  call    cs:__imp_OpenThreadToken
0x18000fb4d  test    eax, eax
0x18000fb4f  jz      loc_18000FD14
0x18000fb55  mov     r14d, edi
0x18000fb58  mov     [rsp+0E8h+var_88], edi
0x18000fb5c  test    eax, eax
0x18000fb5e  jz      loc_18000FCB3
0x18000fb64  xor     r9d, r9d
0x18000fb67  lea     r8, [rsp+0E8h+var_48]
0x18000fb6f  mov     edx, edi
0x18000fb71  mov     rcx, [rsp+0E8h+TokenHandle]
0x18000fb79  call    cs:__imp_FwGetTokenInformation
0x18000fb7f  mov     ecx, eax
0x18000fb81  call    cs:__imp_FwHResultToWindowsError
0x18000fb87  mov     ebx, eax
0x18000fb89  test    eax, eax
0x18000fb8b  jnz     loc_18000FCE9
0x18000fb91  cmp     r14d, edi
0x18000fb94  jz      loc_18000FD3C
0x18000fb9a  lea     rcx, [rsp+0E8h+Binding]
0x18000fba2  call    Int_FWLocalRpcBindingCreate
0x18000fba7  mov     ebx, eax
0x18000fba9  test    eax, eax
0x18000fbab  jnz     loc_18000FD82
0x18000fbb1  mov     rax, [rsp+0E8h+var_48]
0x18000fbb9  mov     rcx, [rax]
0x18000fbbc  mov     [rsp+0E8h+var_60], 0
0x18000fbc8  mov     eax, [rsp+0E8h+binariesCount]
0x18000fbcf  mov     [rsp+0E8h+var_90], eax
0x18000fbd3  mov     rax, [rsp+0E8h+var_78]
0x18000fbd8  mov     [rsp+0E8h+var_98], rax
0x18000fbdd  mov     eax, [rsp+0E8h+bBinariesFullyComputed]
0x18000fbe4  mov     [rsp+0E8h+var_A0], eax
0x18000fbe8  mov     rax, [rsp+0E8h+var_70]
0x18000fbed  mov     [rsp+0E8h+var_A8], rax
0x18000fbf2  mov     rax, [rsp+0E8h+var_68]
0x18000fbfa  mov     [rsp+0E8h+var_B0], rax
0x18000fbff  mov     [rsp+0E8h+var_B8], r13
0x18000fc04  mov     [rsp+0E8h+var_C0], r12
0x18000fc09  mov     [rsp+0E8h+var_C8], rcx
0x18000fc0e  mov     r9, [rsp+0E8h+Binding]
0x18000fc16  xor     r8d, r8d; pReturnValue
0x18000fc19  lea     edx, [rbx+7]; nProcNum
0x18000fc1c  lea     rcx, ?FW_RESOURCE_INDICATION_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18000fc23  call    cs:__imp_NdrClientCall3
0x18000fc29  mov     rbx, rax
0x18000fc2c  mov     [rsp+0E8h+var_60], rax
0x18000fc34  mov     [rsp+0E8h+var_80], eax
0x18000fc38  jmp     short loc_18000FC4F
0x18000fc3a  mov     ebx, eax
0x18000fc3c  mov     [rsp+0E8h+var_80], eax
0x18000fc40  mov     edi, 1
0x18000fc45  mov     r14d, [rsp+0E8h+var_88]
0x18000fc4a  mov     r15d, [rsp+0E8h+var_84]
0x18000fc4f  test    ebx, ebx
0x18000fc51  jnz     loc_18000FDAA
0x18000fc57  cmp     r14d, edi
0x18000fc5a  jz      loc_18000FDE8
0x18000fc60  mov     rcx, [rsp+0E8h+TokenHandle]
0x18000fc68  call    cs:__imp_FwCloseHandle
0x18000fc6e  mov     rcx, [rsp+0E8h+var_48]
0x18000fc76  call    cs:__imp_FwBaseFree
0x18000fc7c  cmp     [rsp+0E8h+Binding], 0
0x18000fc85  jnz     loc_18000FE06
0x18000fc8b  test    ebx, ebx
0x18000fc8d  jg      short loc_18000FCDE
0x18000fc8f  mov     eax, ebx
0x18000fc91  mov     rcx, [rsp+0E8h+var_40]
0x18000fc99  xor     rcx, rsp; StackCookie
0x18000fc9c  call    __security_check_cookie
0x18000fca1  add     rsp, 0B8h
0x18000fca8  pop     r15
0x18000fcaa  pop     r14
0x18000fcac  pop     r13
0x18000fcae  pop     r12
0x18000fcb0  pop     rdi
0x18000fcb1  pop     rbx
0x18000fcb2  retn
0x18000fcb3  call    cs:__imp_GetLastError
0x18000fcb9  mov     ebx, eax
0x18000fcbb  lea     rax, WPP_GLOBAL_Control
0x18000fcc2  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcc9  cmp     rcx, rax
0x18000fccc  jz      short loc_18000FC57
0x18000fcce  test    [rcx+1Ch], dil
0x18000fcd2  jz      short loc_18000FC57
0x18000fcd4  mov     edx, 1D3h
0x18000fcd9  jmp     loc_18000FDD0
0x18000fcde  movzx   ebx, bx
0x18000fce1  or      ebx, 80070000h
0x18000fce7  jmp     short loc_18000FC8F
0x18000fce9  lea     rax, WPP_GLOBAL_Control
0x18000fcf0  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fcf7  cmp     rcx, rax
0x18000fcfa  jz      loc_18000FC57
0x18000fd00  test    [rcx+1Ch], dil
0x18000fd04  jz      loc_18000FC57
0x18000fd0a  mov     edx, 1D4h
0x18000fd0f  jmp     loc_18000FDD0
0x18000fd14  xor     r14d, r14d
0x18000fd17  mov     [rsp+0E8h+var_88], r14d
0x18000fd1c  call    cs:__imp_GetCurrentProcess
0x18000fd22  mov     rcx, rax; ProcessHandle
0x18000fd25  lea     r8, [rsp+0E8h+TokenHandle]; TokenHandle
0x18000fd2d  lea     edx, [r14+8]; DesiredAccess
0x18000fd31  call    cs:__imp_OpenProcessToken
0x18000fd37  jmp     loc_18000FB5C
0x18000fd3c  call    cs:__imp_RevertToSelf
0x18000fd42  test    eax, eax
0x18000fd44  jnz     short loc_18000FD76
0x18000fd46  call    cs:__imp_GetLastError
0x18000fd4c  mov     ebx, eax
0x18000fd4e  lea     rax, WPP_GLOBAL_Control
0x18000fd55  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd5c  cmp     rcx, rax
0x18000fd5f  jz      loc_18000FC57
0x18000fd65  test    [rcx+1Ch], dil
0x18000fd69  jz      loc_18000FC57
0x18000fd6f  mov     edx, 1D5h
0x18000fd74  jmp     short loc_18000FDD0
0x18000fd76  mov     r15d, edi
0x18000fd79  mov     [rsp+0E8h+var_84], edi
0x18000fd7d  jmp     loc_18000FB9A
0x18000fd82  lea     rax, WPP_GLOBAL_Control
0x18000fd89  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fd90  cmp     rcx, rax
0x18000fd93  jz      loc_18000FC57
0x18000fd99  test    [rcx+1Ch], dil
0x18000fd9d  jz      loc_18000FC57
0x18000fda3  mov     edx, 1D6h
0x18000fda8  jmp     short loc_18000FDD0
0x18000fdaa  lea     rax, WPP_GLOBAL_Control
0x18000fdb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fdb8  cmp     rcx, rax
0x18000fdbb  jz      loc_18000FC57
0x18000fdc1  test    [rcx+1Ch], dil
0x18000fdc5  jz      loc_18000FC57
0x18000fdcb  mov     edx, 1D7h
0x18000fdd0  mov     r9d, ebx
0x18000fdd3  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x18000fdda  mov     rcx, [rcx+10h]
0x18000fdde  call    WPP_SF_d
0x18000fde3  jmp     loc_18000FC57
0x18000fde8  cmp     r15d, edi
0x18000fdeb  jnz     loc_18000FC60
0x18000fdf1  mov     rdx, [rsp+0E8h+TokenHandle]; Token
0x18000fdf9  xor     ecx, ecx; Thread
0x18000fdfb  call    cs:__imp_SetThreadToken
0x18000fe01  jmp     loc_18000FC60
0x18000fe06  lea     rcx, [rsp+0E8h+Binding]; Binding
0x18000fe0e  call    cs:__imp_RpcBindingFree
0x18000fe14  test    eax, eax
0x18000fe16  jz      loc_18000FC8B
0x18000fe1c  mov     edx, eax
0x18000fe1e  call    MicrosoftTelemetryAssertTriggeredArgs
0x18000fe23  jmp     loc_18000FC8B
0x18005b904  push    rbp
0x18005b906  sub     rsp, 60h
0x18005b90a  mov     rbp, rdx
0x18005b90d  mov     rcx, [rcx]
0x18005b910  mov     ecx, [rcx]; ExceptionCode
0x18005b912  call    cs:__imp_RpcExceptionFilter
0x18005b918  nop
0x18005b919  add     rsp, 60h
0x18005b91d  pop     rbp
0x18005b91e  retn
```
