# NetworkIsolationDeleteAppContainerLoopbackRules

- ea: `0x180053410`
- end: `0x180053723`
- name: `NetworkIsolationDeleteAppContainerLoopbackRules`
- size: `787`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005954`
- `0x18000e960`
- `0x180024c3c`
- `0x1800277b0`
- `0x180053410`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x18005c172`
- `RPCRT4!RpcExceptionFilter` at `0x18005c172`
- `RPCRT4!NdrClientCall3` at `0x180053625`
- `RPCRT4!NdrClientCall3` at `0x180053625`
- `RPCRT4!RpcBindingFree` at `0x1800536bc`
- `RPCRT4!RpcBindingFree` at `0x1800536bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800534ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005355d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800534ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005355d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180053553`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180053553`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180053690`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180053690`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005346b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005346b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800534a7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800534a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180053496`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180053496`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180053484`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180053484`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180053465`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180053465`
- `fwbase!FwBaseFree` at `0x1800536a9`
- `fwbase!FwBaseFree` at `0x1800536a9`
- `fwbase!FwCloseHandle` at `0x18005369b`
- `fwbase!FwCloseHandle` at `0x18005369b`
- `fwbase!FwHResultToWindowsError` at `0x18005351a`
- `fwbase!FwHResultToWindowsError` at `0x18005351a`
- `fwbase!FwGetTokenInformation` at `0x180053512`
- `fwbase!FwGetTokenInformation` at `0x180053512`

## pseudocode

```c
__int64 __fastcall NetworkIsolationDeleteAppContainerLoopbackRules(__int64 a1, __int64 a2, int a3, __int64 a4, int a5)
{
  int v7; // r12d
  HANDLE CurrentThread; // rax
  BOOL v9; // eax
  int v10; // r15d
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  DWORD v13; // ebx
  FwPolicy2 *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  unsigned int TokenInformation; // eax
  unsigned int Pointer; // eax
  unsigned int v19; // eax
  __int64 v20; // rcx
  __int64 v22; // [rsp+50h] [rbp-78h]
  void *TokenHandle; // [rsp+70h] [rbp-58h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+78h] [rbp-50h] BYREF
  _QWORD *v27; // [rsp+80h] [rbp-48h] BYREF

  Binding = 0;
  v27 = 0;
  TokenHandle = 0;
  v7 = 0;
  HIDWORD(v22) = 0;
  GetTickCount64();
  CurrentThread = GetCurrentThread();
  v9 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  if ( v9 )
  {
    v10 = 1;
    LODWORD(v22) = 1;
  }
  else
  {
    v10 = 0;
    LODWORD(v22) = 0;
    CurrentProcess = GetCurrentProcess();
    v9 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  }
  if ( v9 )
  {
    TokenInformation = FwGetTokenInformation(TokenHandle, 1, &v27, 0);
    LastError = FwHResultToWindowsError(TokenInformation);
    v13 = LastError;
    if ( !LastError )
    {
      if ( v10 == 1 )
      {
        if ( !RevertToSelf() )
        {
          LastError = GetLastError();
          v13 = LastError;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v15 = 619;
            goto LABEL_8;
          }
          goto LABEL_28;
        }
        v7 = 1;
        HIDWORD(v22) = 1;
      }
      LastError = Int_FWLocalRpcBindingCreate(&Binding);
      v13 = LastError;
      if ( LastError )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = 620;
          goto LABEL_8;
        }
      }
      else
      {
        Pointer = (unsigned int)NdrClientCall3(
                                  (MIDL_STUBLESS_PROXY_INFO *)&FW_NET_ISO_DIAG_ProxyInfo,
                                  0xAu,
                                  0,
                                  Binding,
                                  *v27,
                                  a1,
                                  a2,
                                  a3,
                                  a4,
                                  a5,
                                  v22).Pointer;
        v13 = Pointer;
        if ( Pointer )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v15 = 621;
            v16 = Pointer;
            goto LABEL_9;
          }
        }
      }
      goto LABEL_28;
    }
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 618;
      goto LABEL_8;
    }
  }
  else
  {
    LastError = GetLastError();
    v13 = LastError;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v15 = 617;
LABEL_8:
      v16 = LastError;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v16);
    }
  }
LABEL_28:
  if ( v10 == 1 && v7 == 1 )
    SetThreadToken(0, TokenHandle);
  FwCloseHandle(TokenHandle);
  FwBaseFree(v27);
  if ( Binding )
  {
    v19 = RpcBindingFree(&Binding);
    if ( v19 )
      MicrosoftTelemetryAssertTriggeredArgs(v20, v19);
    Binding = 0;
  }
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 622, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x180053410  mov     r11, rsp
0x180053413  push    rbx
0x180053414  push    rsi
0x180053415  push    rdi
0x180053416  push    r12
0x180053418  push    r13
0x18005341a  push    r15
0x18005341c  sub     rsp, 98h
0x180053423  mov     rax, cs:__security_cookie
0x18005342a  xor     rax, rsp
0x18005342d  mov     [rsp+0C8h+var_40], rax
0x180053435  mov     [rsp+0C8h+var_68], r9
0x18005343a  mov     [rsp+0C8h+var_70], r8d
0x18005343f  mov     r13, rdx
0x180053442  mov     rdi, rcx
0x180053445  mov     qword ptr [r11-50h], 0
0x18005344d  mov     qword ptr [r11-48h], 0
0x180053455  mov     qword ptr [r11-58h], 0
0x18005345d  xor     r12d, r12d
0x180053460  mov     [rsp+0C8h+var_74], r12d
0x180053465  call    cs:__imp_GetTickCount64
0x18005346b  call    cs:__imp_GetCurrentThread
0x180053471  mov     rcx, rax; ThreadHandle
0x180053474  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x180053479  lea     esi, [r12+1]
0x18005347e  mov     r8d, esi; OpenAsSelf
0x180053481  lea     edx, [rsi+0Bh]; DesiredAccess
0x180053484  call    cs:__imp_OpenThreadToken
0x18005348a  test    eax, eax
0x18005348c  jnz     short loc_1800534AF
0x18005348e  xor     r15d, r15d
0x180053491  mov     [rsp+0C8h+var_78], r15d
0x180053496  call    cs:__imp_GetCurrentProcess
0x18005349c  mov     rcx, rax; ProcessHandle
0x18005349f  lea     r8, [rsp+0C8h+TokenHandle]; TokenHandle
0x1800534a4  lea     edx, [rsi+7]; DesiredAccess
0x1800534a7  call    cs:__imp_OpenProcessToken
0x1800534ad  jmp     short loc_1800534B6
0x1800534af  mov     r15d, esi
0x1800534b2  mov     [rsp+0C8h+var_78], esi
0x1800534b6  test    eax, eax
0x1800534b8  jnz     short loc_180053500
0x1800534ba  call    cs:__imp_GetLastError
0x1800534c0  mov     ebx, eax
0x1800534c2  lea     rdi, WPP_GLOBAL_Control
0x1800534c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800534d0  cmp     rcx, rdi
0x1800534d3  jz      loc_18005367F
0x1800534d9  test    [rcx+1Ch], sil
0x1800534dd  jz      loc_18005367F
0x1800534e3  mov     edx, 269h
0x1800534e8  mov     r9d, eax
0x1800534eb  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800534f2  mov     rcx, [rcx+10h]
0x1800534f6  call    WPP_SF_d
0x1800534fb  jmp     loc_18005367F
0x180053500  xor     r9d, r9d
0x180053503  lea     r8, [rsp+0C8h+var_48]
0x18005350b  mov     edx, esi
0x18005350d  mov     rcx, [rsp+0C8h+TokenHandle]
0x180053512  call    cs:__imp_FwGetTokenInformation
0x180053518  mov     ecx, eax
0x18005351a  call    cs:__imp_FwHResultToWindowsError
0x180053520  mov     ebx, eax
0x180053522  test    eax, eax
0x180053524  jz      short loc_18005354E
0x180053526  lea     rdi, WPP_GLOBAL_Control
0x18005352d  mov     rcx, cs:WPP_GLOBAL_Control
0x180053534  cmp     rcx, rdi
0x180053537  jz      loc_18005367F
0x18005353d  test    [rcx+1Ch], sil
0x180053541  jz      loc_18005367F
0x180053547  mov     edx, 26Ah
0x18005354c  jmp     short loc_1800534E8
0x18005354e  cmp     r15d, esi
0x180053551  jnz     short loc_180053597
0x180053553  call    cs:__imp_RevertToSelf
0x180053559  test    eax, eax
0x18005355b  jnz     short loc_180053590
0x18005355d  call    cs:__imp_GetLastError
0x180053563  mov     ebx, eax
0x180053565  lea     rdi, WPP_GLOBAL_Control
0x18005356c  mov     rcx, cs:WPP_GLOBAL_Control
0x180053573  cmp     rcx, rdi
0x180053576  jz      loc_18005367F
0x18005357c  test    [rcx+1Ch], sil
0x180053580  jz      loc_18005367F
0x180053586  mov     edx, 26Bh
0x18005358b  jmp     loc_1800534E8
0x180053590  mov     r12d, esi
0x180053593  mov     [rsp+0C8h+var_74], esi
0x180053597  lea     rcx, [rsp+0C8h+Binding]
0x18005359c  call    Int_FWLocalRpcBindingCreate
0x1800535a1  mov     ebx, eax
0x1800535a3  test    eax, eax
0x1800535a5  jz      short loc_1800535D2
0x1800535a7  lea     rdi, WPP_GLOBAL_Control
0x1800535ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800535b5  cmp     rcx, rdi
0x1800535b8  jz      loc_18005367F
0x1800535be  test    [rcx+1Ch], sil
0x1800535c2  jz      loc_18005367F
0x1800535c8  mov     edx, 26Ch
0x1800535cd  jmp     loc_1800534E8
0x1800535d2  mov     rax, [rsp+0C8h+var_48]
0x1800535da  mov     rcx, [rax]
0x1800535dd  mov     [rsp+0C8h+var_60], 0
0x1800535e6  mov     eax, [rsp+0C8h+arg_20]
0x1800535ed  mov     [rsp+0C8h+var_80], eax
0x1800535f1  mov     rax, [rsp+0C8h+var_68]
0x1800535f6  mov     [rsp+0C8h+var_88], rax
0x1800535fb  mov     eax, [rsp+0C8h+var_70]
0x1800535ff  mov     [rsp+0C8h+var_90], eax
0x180053603  mov     [rsp+0C8h+var_98], r13
0x180053608  mov     [rsp+0C8h+var_A0], rdi
0x18005360d  mov     [rsp+0C8h+var_A8], rcx
0x180053612  mov     r9, [rsp+0C8h+Binding]
0x180053617  xor     r8d, r8d; pReturnValue
0x18005361a  lea     edx, [r8+0Ah]; nProcNum
0x18005361e  lea     rcx, ?FW_NET_ISO_DIAG_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180053625  call    cs:__imp_NdrClientCall3
0x18005362b  mov     rbx, rax
0x18005362e  mov     [rsp+0C8h+var_60], rax
0x180053633  mov     [rsp+0C8h+var_6C], eax
0x180053637  jmp     short loc_18005364E
0x180053639  mov     ebx, eax
0x18005363b  mov     [rsp+0C8h+var_6C], eax
0x18005363f  mov     esi, 1
0x180053644  mov     r15d, [rsp+0C8h+var_78]
0x180053649  mov     r12d, [rsp+0C8h+var_74]
0x18005364e  test    ebx, ebx
0x180053650  jz      short loc_180053678
0x180053652  lea     rdi, WPP_GLOBAL_Control
0x180053659  mov     rcx, cs:WPP_GLOBAL_Control
0x180053660  cmp     rcx, rdi
0x180053663  jz      short loc_18005367F
0x180053665  test    [rcx+1Ch], sil
0x180053669  jz      short loc_18005367F
0x18005366b  mov     edx, 26Dh
0x180053670  mov     r9d, ebx
0x180053673  jmp     loc_1800534EB
0x180053678  lea     rdi, WPP_GLOBAL_Control
0x18005367f  cmp     r15d, esi
0x180053682  jnz     short loc_180053696
0x180053684  cmp     r12d, esi
0x180053687  jnz     short loc_180053696
0x180053689  mov     rdx, [rsp+0C8h+TokenHandle]; Token
0x18005368e  xor     ecx, ecx; Thread
0x180053690  call    cs:__imp_SetThreadToken
0x180053696  mov     rcx, [rsp+0C8h+TokenHandle]
0x18005369b  call    cs:__imp_FwCloseHandle
0x1800536a1  mov     rcx, [rsp+0C8h+var_48]
0x1800536a9  call    cs:__imp_FwBaseFree
0x1800536af  cmp     [rsp+0C8h+Binding], 0
0x1800536b5  jz      short loc_1800536D6
0x1800536b7  lea     rcx, [rsp+0C8h+Binding]; Binding
0x1800536bc  call    cs:__imp_RpcBindingFree
0x1800536c2  test    eax, eax
0x1800536c4  jz      short loc_1800536CD
0x1800536c6  mov     edx, eax
0x1800536c8  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800536cd  mov     [rsp+0C8h+Binding], 0
0x1800536d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800536dd  cmp     rcx, rdi
0x1800536e0  jz      short loc_180053700
0x1800536e2  test    byte ptr [rcx+1Ch], 8
0x1800536e6  jz      short loc_180053700
0x1800536e8  mov     edx, 26Eh
0x1800536ed  mov     r9d, ebx
0x1800536f0  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800536f7  mov     rcx, [rcx+10h]
0x1800536fb  call    WPP_SF_d
0x180053700  mov     eax, ebx
0x180053702  mov     rcx, [rsp+0C8h+var_40]
0x18005370a  xor     rcx, rsp; StackCookie
0x18005370d  call    __security_check_cookie
0x180053712  add     rsp, 98h
0x180053719  pop     r15
0x18005371b  pop     r13
0x18005371d  pop     r12
0x18005371f  pop     rdi
0x180053720  pop     rsi
0x180053721  pop     rbx
0x180053722  retn
0x18005c164  push    rbp
0x18005c166  sub     rsp, 50h
0x18005c16a  mov     rbp, rdx
0x18005c16d  mov     rcx, [rcx]
0x18005c170  mov     ecx, [rcx]; ExceptionCode
0x18005c172  call    cs:__imp_RpcExceptionFilter
0x18005c178  nop
0x18005c179  add     rsp, 50h
0x18005c17d  pop     rbp
0x18005c17e  retn
```
