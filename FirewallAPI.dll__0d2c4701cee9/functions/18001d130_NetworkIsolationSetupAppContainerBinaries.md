# NetworkIsolationSetupAppContainerBinaries

- ea: `0x18001d130`
- end: `0x18001d4fb`
- name: `NetworkIsolationSetupAppContainerBinaries`
- size: `971`
- prototype: `HRESULT __stdcall(PSID applicationContainerSid, LPCWSTR packageFullName, LPCWSTR packageFolder, LPCWSTR displayName, BOOL bBinariesFullyComputed, LPCWSTR *binaries, DWORD binariesCount)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x180005e0c`
- `0x18000ea10`
- `0x18001d130`
- `0x180026798`
- `0x1800294b0`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005fc0c`
- `RPCRT4!RpcExceptionFilter` at `0x18005fc0c`
- `RPCRT4!NdrClientCall3` at `0x18001d2b1`
- `RPCRT4!NdrClientCall3` at `0x18001d2b1`
- `RPCRT4!RpcBindingFree` at `0x18001d4db`
- `RPCRT4!RpcBindingFree` at `0x18001d4db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d407`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d407`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001d3f7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001d3f7`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001d4c2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18001d4c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d1a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001d1a2`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001d3e6`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001d3e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d3cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18001d3cb`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d1c3`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001d1c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001d196`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001d196`
- `fwbase!FwBaseFree` at `0x18001d310`
- `fwbase!FwBaseFree` at `0x18001d310`
- `fwbase!FwCloseHandle` at `0x18001d2fc`
- `fwbase!FwCloseHandle` at `0x18001d2fc`
- `fwbase!FwHResultToWindowsError` at `0x18001d209`
- `fwbase!FwHResultToWindowsError` at `0x18001d209`
- `fwbase!FwGetTokenInformation` at `0x18001d1fb`
- `fwbase!FwGetTokenInformation` at `0x18001d1fb`

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
    v17 = 466;
LABEL_31:
    WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, (unsigned int)LastError);
    goto LABEL_8;
  }
  TokenInformation = FwGetTokenInformation(TokenHandle, 1, &v26, 0);
  LastError = FwHResultToWindowsError(TokenInformation);
  if ( LastError )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (FwPolicy2 *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_8;
    v17 = 467;
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
    v17 = 468;
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
    v17 = 469;
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
      v17 = 470;
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
0x18001d130  mov     r11, rsp
0x18001d133  push    rbx
0x18001d134  push    rdi
0x18001d135  push    r12
0x18001d137  push    r13
0x18001d139  push    r14
0x18001d13b  push    r15
0x18001d13d  sub     rsp, 0B8h
0x18001d144  mov     rax, cs:__security_cookie
0x18001d14b  xor     rax, rsp
0x18001d14e  mov     [rsp+0E8h+var_40], rax
0x18001d156  mov     [rsp+0E8h+var_70], r9
0x18001d15b  mov     [rsp+0E8h+var_68], r8
0x18001d163  mov     r13, rdx
0x18001d166  mov     r12, rcx
0x18001d169  mov     rax, [rsp+0E8h+binaries]
0x18001d171  mov     [rsp+0E8h+var_78], rax
0x18001d176  mov     qword ptr [r11-50h], 0
0x18001d17e  mov     qword ptr [r11-48h], 0
0x18001d186  mov     qword ptr [r11-58h], 0
0x18001d18e  xor     r15d, r15d
0x18001d191  mov     [rsp+0E8h+var_84], r15d
0x18001d196  call    cs:__imp_GetTickCount64
0x18001d19d  nop     dword ptr [rax+rax+00h]
0x18001d1a2  call    cs:__imp_GetCurrentThread
0x18001d1a9  nop     dword ptr [rax+rax+00h]
0x18001d1ae  mov     rcx, rax; ThreadHandle
0x18001d1b1  lea     r9, [rsp+0E8h+TokenHandle]; TokenHandle
0x18001d1b9  lea     edi, [r15+1]
0x18001d1bd  mov     r8d, edi; OpenAsSelf
0x18001d1c0  lea     edx, [rdi+0Bh]; DesiredAccess
0x18001d1c3  call    cs:__imp_OpenThreadToken
0x18001d1ca  nop     dword ptr [rax+rax+00h]
0x18001d1cf  test    eax, eax
0x18001d1d1  jz      loc_18001D3C3
0x18001d1d7  mov     r14d, edi
0x18001d1da  mov     [rsp+0E8h+var_88], edi
0x18001d1de  test    eax, eax
0x18001d1e0  jz      loc_18001D354
0x18001d1e6  xor     r9d, r9d
0x18001d1e9  lea     r8, [rsp+0E8h+var_48]
0x18001d1f1  mov     edx, edi
0x18001d1f3  mov     rcx, [rsp+0E8h+TokenHandle]
0x18001d1fb  call    cs:__imp_FwGetTokenInformation
0x18001d202  nop     dword ptr [rax+rax+00h]
0x18001d207  mov     ecx, eax
0x18001d209  call    cs:__imp_FwHResultToWindowsError
0x18001d210  nop     dword ptr [rax+rax+00h]
0x18001d215  mov     ebx, eax
0x18001d217  test    eax, eax
0x18001d219  jnz     loc_18001D398
0x18001d21f  cmp     r14d, edi
0x18001d222  jz      loc_18001D3F7
0x18001d228  lea     rcx, [rsp+0E8h+Binding]
0x18001d230  call    Int_FWLocalRpcBindingCreate
0x18001d235  mov     ebx, eax
0x18001d237  test    eax, eax
0x18001d239  jnz     loc_18001D449
0x18001d23f  mov     rax, [rsp+0E8h+var_48]
0x18001d247  mov     rcx, [rax]
0x18001d24a  mov     [rsp+0E8h+var_60], 0
0x18001d256  mov     eax, [rsp+0E8h+binariesCount]
0x18001d25d  mov     [rsp+0E8h+var_90], eax
0x18001d261  mov     rax, [rsp+0E8h+var_78]
0x18001d266  mov     [rsp+0E8h+var_98], rax
0x18001d26b  mov     eax, [rsp+0E8h+bBinariesFullyComputed]
0x18001d272  mov     [rsp+0E8h+var_A0], eax
0x18001d276  mov     rax, [rsp+0E8h+var_70]
0x18001d27b  mov     [rsp+0E8h+var_A8], rax
0x18001d280  mov     rax, [rsp+0E8h+var_68]
0x18001d288  mov     [rsp+0E8h+var_B0], rax
0x18001d28d  mov     [rsp+0E8h+var_B8], r13
0x18001d292  mov     [rsp+0E8h+var_C0], r12
0x18001d297  mov     [rsp+0E8h+var_C8], rcx
0x18001d29c  mov     r9, [rsp+0E8h+Binding]
0x18001d2a4  xor     r8d, r8d; pReturnValue
0x18001d2a7  lea     edx, [rbx+7]; nProcNum
0x18001d2aa  lea     rcx, ?FW_RESOURCE_INDICATION_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18001d2b1  call    cs:__imp_NdrClientCall3
0x18001d2b8  nop     dword ptr [rax+rax+00h]
0x18001d2bd  mov     rbx, rax
0x18001d2c0  mov     [rsp+0E8h+var_60], rax
0x18001d2c8  mov     [rsp+0E8h+var_80], eax
0x18001d2cc  jmp     short loc_18001D2E3
0x18001d2ce  mov     ebx, eax
0x18001d2d0  mov     [rsp+0E8h+var_80], eax
0x18001d2d4  mov     edi, 1
0x18001d2d9  mov     r14d, [rsp+0E8h+var_88]
0x18001d2de  mov     r15d, [rsp+0E8h+var_84]
0x18001d2e3  test    ebx, ebx
0x18001d2e5  jnz     loc_18001D471
0x18001d2eb  cmp     r14d, edi
0x18001d2ee  jz      loc_18001D4AF
0x18001d2f4  mov     rcx, [rsp+0E8h+TokenHandle]
0x18001d2fc  call    cs:__imp_FwCloseHandle
0x18001d303  nop     dword ptr [rax+rax+00h]
0x18001d308  mov     rcx, [rsp+0E8h+var_48]
0x18001d310  call    cs:__imp_FwBaseFree
0x18001d317  nop     dword ptr [rax+rax+00h]
0x18001d31c  cmp     [rsp+0E8h+Binding], 0
0x18001d325  jnz     loc_18001D4D3
0x18001d32b  test    ebx, ebx
0x18001d32d  jg      short loc_18001D38D
0x18001d32f  mov     eax, ebx
0x18001d331  mov     rcx, [rsp+0E8h+var_40]
0x18001d339  xor     rcx, rsp; StackCookie
0x18001d33c  call    __security_check_cookie
0x18001d341  add     rsp, 0B8h
0x18001d348  pop     r15
0x18001d34a  pop     r14
0x18001d34c  pop     r13
0x18001d34e  pop     r12
0x18001d350  pop     rdi
0x18001d351  pop     rbx
0x18001d352  retn
0x18001d354  call    cs:__imp_GetLastError
0x18001d35b  nop     dword ptr [rax+rax+00h]
0x18001d360  mov     ebx, eax
0x18001d362  lea     rax, WPP_GLOBAL_Control
0x18001d369  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d370  cmp     rcx, rax
0x18001d373  jz      loc_18001D2EB
0x18001d379  test    [rcx+1Ch], dil
0x18001d37d  jz      loc_18001D2EB
0x18001d383  mov     edx, 1D2h
0x18001d388  jmp     loc_18001D497
0x18001d38d  movzx   ebx, bx
0x18001d390  or      ebx, 80070000h
0x18001d396  jmp     short loc_18001D32F
0x18001d398  lea     rax, WPP_GLOBAL_Control
0x18001d39f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d3a6  cmp     rcx, rax
0x18001d3a9  jz      loc_18001D2EB
0x18001d3af  test    [rcx+1Ch], dil
0x18001d3b3  jz      loc_18001D2EB
0x18001d3b9  mov     edx, 1D3h
0x18001d3be  jmp     loc_18001D497
0x18001d3c3  xor     r14d, r14d
0x18001d3c6  mov     [rsp+0E8h+var_88], r14d
0x18001d3cb  call    cs:__imp_GetCurrentProcess
0x18001d3d2  nop     dword ptr [rax+rax+00h]
0x18001d3d7  mov     rcx, rax; ProcessHandle
0x18001d3da  lea     r8, [rsp+0E8h+TokenHandle]; TokenHandle
0x18001d3e2  lea     edx, [r14+8]; DesiredAccess
0x18001d3e6  call    cs:__imp_OpenProcessToken
0x18001d3ed  nop     dword ptr [rax+rax+00h]
0x18001d3f2  jmp     loc_18001D1DE
0x18001d3f7  call    cs:__imp_RevertToSelf
0x18001d3fe  nop     dword ptr [rax+rax+00h]
0x18001d403  test    eax, eax
0x18001d405  jnz     short loc_18001D43D
0x18001d407  call    cs:__imp_GetLastError
0x18001d40e  nop     dword ptr [rax+rax+00h]
0x18001d413  mov     ebx, eax
0x18001d415  lea     rax, WPP_GLOBAL_Control
0x18001d41c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d423  cmp     rcx, rax
0x18001d426  jz      loc_18001D2EB
0x18001d42c  test    [rcx+1Ch], dil
0x18001d430  jz      loc_18001D2EB
0x18001d436  mov     edx, 1D4h
0x18001d43b  jmp     short loc_18001D497
0x18001d43d  mov     r15d, edi
0x18001d440  mov     [rsp+0E8h+var_84], edi
0x18001d444  jmp     loc_18001D228
0x18001d449  lea     rax, WPP_GLOBAL_Control
0x18001d450  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d457  cmp     rcx, rax
0x18001d45a  jz      loc_18001D2EB
0x18001d460  test    [rcx+1Ch], dil
0x18001d464  jz      loc_18001D2EB
0x18001d46a  mov     edx, 1D5h
0x18001d46f  jmp     short loc_18001D497
0x18001d471  lea     rax, WPP_GLOBAL_Control
0x18001d478  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d47f  cmp     rcx, rax
0x18001d482  jz      loc_18001D2EB
0x18001d488  test    [rcx+1Ch], dil
0x18001d48c  jz      loc_18001D2EB
0x18001d492  mov     edx, 1D6h
0x18001d497  mov     r9d, ebx
0x18001d49a  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x18001d4a1  mov     rcx, [rcx+10h]
0x18001d4a5  call    WPP_SF_d
0x18001d4aa  jmp     loc_18001D2EB
0x18001d4af  cmp     r15d, edi
0x18001d4b2  jnz     loc_18001D2F4
0x18001d4b8  mov     rdx, [rsp+0E8h+TokenHandle]; Token
0x18001d4c0  xor     ecx, ecx; Thread
0x18001d4c2  call    cs:__imp_SetThreadToken
0x18001d4c9  nop     dword ptr [rax+rax+00h]
0x18001d4ce  jmp     loc_18001D2F4
0x18001d4d3  lea     rcx, [rsp+0E8h+Binding]; Binding
0x18001d4db  call    cs:__imp_RpcBindingFree
0x18001d4e2  nop     dword ptr [rax+rax+00h]
0x18001d4e7  test    eax, eax
0x18001d4e9  jz      loc_18001D32B
0x18001d4ef  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree")
0x18001d4f1  call    MicrosoftTelemetryAssertTriggeredArgs
0x18001d4f6  jmp     loc_18001D32B
0x18005fbfe  push    rbp
0x18005fc00  sub     rsp, 60h
0x18005fc04  mov     rbp, rdx
0x18005fc07  mov     rcx, [rcx]
0x18005fc0a  mov     ecx, [rcx]; ExceptionCode
0x18005fc0c  call    cs:__imp_RpcExceptionFilter
0x18005fc13  nop     dword ptr [rax+rax+00h]
0x18005fc18  nop
0x18005fc19  add     rsp, 60h
0x18005fc1d  pop     rbp
0x18005fc1e  retn
```
