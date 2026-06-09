# NetworkIsolationDeleteContainer

- ea: `0x180053730`
- end: `0x180053a5a`
- name: `NetworkIsolationDeleteContainer`
- size: `810`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005954`
- `0x18000e960`
- `0x180024c3c`
- `0x1800277b0`
- `0x18003104c`
- `0x180053730`
- `0x180054f20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180053956`
- `RPCRT4!NdrClientCall3` at `0x180053956`
- `RPCRT4!RpcBindingFree` at `0x1800539ee`
- `RPCRT4!RpcBindingFree` at `0x1800539ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800538b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180053837`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800538b9`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800538af`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800538af`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800539c5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800539c5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800537e8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800537e8`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180053824`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180053824`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180053813`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180053813`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180053801`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180053801`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800537ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800537ae`
- `fwbase!FwBaseFree` at `0x1800539db`
- `fwbase!FwBaseFree` at `0x1800539db`
- `fwbase!FwCloseHandle` at `0x1800539d0`
- `fwbase!FwCloseHandle` at `0x1800539d0`
- `fwbase!FwHResultToWindowsError` at `0x18005387d`
- `fwbase!FwHResultToWindowsError` at `0x18005387d`
- `fwbase!FwGetTokenInformation` at `0x180053875`
- `fwbase!FwGetTokenInformation` at `0x180053875`

## pseudocode

```c
__int64 __fastcall NetworkIsolationDeleteContainer(int a1, const wchar_t *a2)
{
  int v4; // r12d
  int v5; // r8d
  const wchar_t *v6; // rax
  HANDLE CurrentThread; // rax
  BOOL v8; // eax
  int v9; // r15d
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  DWORD v12; // ebx
  FwPolicy2 *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // r9
  unsigned int TokenInformation; // eax
  unsigned int Pointer; // eax
  unsigned int v18; // eax
  __int64 v19; // rcx
  void *TokenHandle; // [rsp+58h] [rbp-50h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-48h] BYREF
  _QWORD *v24; // [rsp+68h] [rbp-40h] BYREF

  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 603, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  Binding = 0;
  v24 = 0;
  TokenHandle = 0;
  v4 = 0;
  GetTickCount64();
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v6 = a2;
    if ( !a2 )
      v6 = L"<null>";
    WPP_SF_DS(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)L"<null>", v5, a1, (__int64)v6);
  }
  CurrentThread = GetCurrentThread();
  v8 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  if ( v8 )
  {
    v9 = 1;
  }
  else
  {
    v9 = 0;
    CurrentProcess = GetCurrentProcess();
    v8 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  }
  if ( v8 )
  {
    TokenInformation = FwGetTokenInformation(TokenHandle, 1, &v24, 0);
    LastError = FwHResultToWindowsError(TokenInformation);
    v12 = LastError;
    if ( !LastError )
    {
      if ( v9 == 1 )
      {
        if ( !RevertToSelf() )
        {
          LastError = GetLastError();
          v12 = LastError;
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v14 = 607;
            goto LABEL_16;
          }
          goto LABEL_36;
        }
        v4 = 1;
      }
      LastError = Int_FWLocalRpcBindingCreate(&Binding);
      v12 = LastError;
      if ( LastError )
      {
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v14 = 608;
          goto LABEL_16;
        }
      }
      else
      {
        Pointer = (unsigned int)NdrClientCall3(
                                  (MIDL_STUBLESS_PROXY_INFO *)&FW_NET_ISO_DIAG_ProxyInfo,
                                  3u,
                                  0,
                                  Binding,
                                  *v24,
                                  a1,
                                  a2).Pointer;
        v12 = Pointer;
        if ( Pointer )
        {
          v13 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v14 = 609;
            v15 = Pointer;
            goto LABEL_35;
          }
        }
      }
      goto LABEL_36;
    }
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 606;
      goto LABEL_16;
    }
  }
  else
  {
    LastError = GetLastError();
    v12 = LastError;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = 605;
LABEL_16:
      v15 = LastError;
LABEL_35:
      WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v15);
    }
  }
LABEL_36:
  if ( v9 == 1 && v4 == 1 )
    SetThreadToken(0, TokenHandle);
  FwCloseHandle(TokenHandle);
  FwBaseFree(v24);
  if ( Binding )
  {
    v18 = RpcBindingFree(&Binding);
    if ( v18 )
      MicrosoftTelemetryAssertTriggeredArgs(v19, v18);
    Binding = 0;
  }
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 610, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v12);
  return v12;
}

```

## disassembly

```asm
0x180053730  mov     [rsp+arg_10], rbx
0x180053735  push    rsi
0x180053736  push    r12
0x180053738  push    r13
0x18005373a  push    r14
0x18005373c  push    r15
0x18005373e  sub     rsp, 80h
0x180053745  mov     rax, cs:__security_cookie
0x18005374c  xor     rax, rsp
0x18005374f  mov     [rsp+0A8h+var_38], rax
0x180053754  mov     r13, rdx
0x180053757  mov     ebx, ecx
0x180053759  mov     [rsp+0A8h+var_60], ecx
0x18005375d  lea     r14, WPP_GLOBAL_Control
0x180053764  mov     rcx, cs:WPP_GLOBAL_Control
0x18005376b  cmp     rcx, r14
0x18005376e  jz      short loc_18005378B
0x180053770  test    byte ptr [rcx+1Ch], 8
0x180053774  jz      short loc_18005378B
0x180053776  mov     edx, 25Bh
0x18005377b  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180053782  mov     rcx, [rcx+10h]
0x180053786  call    WPP_SF_
0x18005378b  mov     [rsp+0A8h+Binding], 0
0x180053794  mov     [rsp+0A8h+var_40], 0
0x18005379d  mov     [rsp+0A8h+TokenHandle], 0
0x1800537a6  xor     r12d, r12d
0x1800537a9  mov     [rsp+0A8h+var_64], r12d
0x1800537ae  call    cs:__imp_GetTickCount64
0x1800537b4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800537bb  cmp     rcx, r14
0x1800537be  jz      short loc_1800537E8
0x1800537c0  test    byte ptr [rcx+1Ch], 4
0x1800537c4  jz      short loc_1800537E8
0x1800537c6  lea     rdx, aNull; "<null>"
0x1800537cd  mov     rax, r13
0x1800537d0  test    r13, r13
0x1800537d3  cmovz   rax, rdx
0x1800537d7  mov     [rsp+0A8h+var_88], rax
0x1800537dc  mov     r9d, ebx
0x1800537df  mov     rcx, [rcx+10h]
0x1800537e3  call    WPP_SF_DS
0x1800537e8  call    cs:__imp_GetCurrentThread
0x1800537ee  mov     rcx, rax; ThreadHandle
0x1800537f1  lea     r9, [rsp+0A8h+TokenHandle]; TokenHandle
0x1800537f6  mov     esi, 1
0x1800537fb  mov     r8d, esi; OpenAsSelf
0x1800537fe  lea     edx, [rsi+0Bh]; DesiredAccess
0x180053801  call    cs:__imp_OpenThreadToken
0x180053807  test    eax, eax
0x180053809  jnz     short loc_18005382C
0x18005380b  xor     r15d, r15d
0x18005380e  mov     [rsp+0A8h+var_68], r15d
0x180053813  call    cs:__imp_GetCurrentProcess
0x180053819  mov     rcx, rax; ProcessHandle
0x18005381c  lea     r8, [rsp+0A8h+TokenHandle]; TokenHandle
0x180053821  lea     edx, [rsi+7]; DesiredAccess
0x180053824  call    cs:__imp_OpenProcessToken
0x18005382a  jmp     short loc_180053833
0x18005382c  mov     r15d, esi
0x18005382f  mov     [rsp+0A8h+var_68], esi
0x180053833  test    eax, eax
0x180053835  jnz     short loc_180053866
0x180053837  call    cs:__imp_GetLastError
0x18005383d  mov     ebx, eax
0x18005383f  mov     rcx, cs:WPP_GLOBAL_Control
0x180053846  cmp     rcx, r14
0x180053849  jz      loc_1800539B4
0x18005384f  test    [rcx+1Ch], sil
0x180053853  jz      loc_1800539B4
0x180053859  mov     edx, 25Dh
0x18005385e  mov     r9d, eax
0x180053861  jmp     loc_1800539A4
0x180053866  xor     r9d, r9d
0x180053869  lea     r8, [rsp+0A8h+var_40]
0x18005386e  mov     edx, esi
0x180053870  mov     rcx, [rsp+0A8h+TokenHandle]
0x180053875  call    cs:__imp_FwGetTokenInformation
0x18005387b  mov     ecx, eax
0x18005387d  call    cs:__imp_FwHResultToWindowsError
0x180053883  mov     ebx, eax
0x180053885  test    eax, eax
0x180053887  jz      short loc_1800538AA
0x180053889  mov     rcx, cs:WPP_GLOBAL_Control
0x180053890  cmp     rcx, r14
0x180053893  jz      loc_1800539B4
0x180053899  test    [rcx+1Ch], sil
0x18005389d  jz      loc_1800539B4
0x1800538a3  mov     edx, 25Eh
0x1800538a8  jmp     short loc_18005385E
0x1800538aa  cmp     r15d, esi
0x1800538ad  jnz     short loc_1800538EC
0x1800538af  call    cs:__imp_RevertToSelf
0x1800538b5  test    eax, eax
0x1800538b7  jnz     short loc_1800538E5
0x1800538b9  call    cs:__imp_GetLastError
0x1800538bf  mov     ebx, eax
0x1800538c1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800538c8  cmp     rcx, r14
0x1800538cb  jz      loc_1800539B4
0x1800538d1  test    [rcx+1Ch], sil
0x1800538d5  jz      loc_1800539B4
0x1800538db  mov     edx, 25Fh
0x1800538e0  jmp     loc_18005385E
0x1800538e5  mov     r12d, esi
0x1800538e8  mov     [rsp+0A8h+var_64], esi
0x1800538ec  lea     rcx, [rsp+0A8h+Binding]
0x1800538f1  call    Int_FWLocalRpcBindingCreate
0x1800538f6  mov     ebx, eax
0x1800538f8  test    eax, eax
0x1800538fa  jz      short loc_180053920
0x1800538fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180053903  cmp     rcx, r14
0x180053906  jz      loc_1800539B4
0x18005390c  test    [rcx+1Ch], sil
0x180053910  jz      loc_1800539B4
0x180053916  mov     edx, 260h
0x18005391b  jmp     loc_18005385E
0x180053920  mov     rax, [rsp+0A8h+var_40]
0x180053925  mov     rcx, [rax]
0x180053928  mov     [rsp+0A8h+var_58], 0
0x180053931  mov     [rsp+0A8h+var_78], r13
0x180053936  mov     eax, [rsp+0A8h+var_60]
0x18005393a  mov     [rsp+0A8h+var_80], eax
0x18005393e  mov     [rsp+0A8h+var_88], rcx
0x180053943  mov     r9, [rsp+0A8h+Binding]
0x180053948  xor     r8d, r8d; pReturnValue
0x18005394b  lea     edx, [r8+3]; nProcNum
0x18005394f  lea     rcx, ?FW_NET_ISO_DIAG_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180053956  call    cs:__imp_NdrClientCall3
0x18005395c  mov     rbx, rax
0x18005395f  mov     [rsp+0A8h+var_58], rax
0x180053964  mov     [rsp+0A8h+var_5C], eax
0x180053968  jmp     short loc_180053986
0x18005396a  mov     ebx, eax
0x18005396c  mov     [rsp+0A8h+var_5C], eax
0x180053970  lea     r14, WPP_GLOBAL_Control
0x180053977  mov     esi, 1
0x18005397c  mov     r15d, [rsp+0A8h+var_68]
0x180053981  mov     r12d, [rsp+0A8h+var_64]
0x180053986  test    ebx, ebx
0x180053988  jz      short loc_1800539B4
0x18005398a  mov     rcx, cs:WPP_GLOBAL_Control
0x180053991  cmp     rcx, r14
0x180053994  jz      short loc_1800539B4
0x180053996  test    [rcx+1Ch], sil
0x18005399a  jz      short loc_1800539B4
0x18005399c  mov     edx, 261h
0x1800539a1  mov     r9d, ebx
0x1800539a4  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x1800539ab  mov     rcx, [rcx+10h]
0x1800539af  call    WPP_SF_d
0x1800539b4  cmp     r15d, esi
0x1800539b7  jnz     short loc_1800539CB
0x1800539b9  cmp     r12d, esi
0x1800539bc  jnz     short loc_1800539CB
0x1800539be  mov     rdx, [rsp+0A8h+TokenHandle]; Token
0x1800539c3  xor     ecx, ecx; Thread
0x1800539c5  call    cs:__imp_SetThreadToken
0x1800539cb  mov     rcx, [rsp+0A8h+TokenHandle]
0x1800539d0  call    cs:__imp_FwCloseHandle
0x1800539d6  mov     rcx, [rsp+0A8h+var_40]
0x1800539db  call    cs:__imp_FwBaseFree
0x1800539e1  cmp     [rsp+0A8h+Binding], 0
0x1800539e7  jz      short loc_180053A08
0x1800539e9  lea     rcx, [rsp+0A8h+Binding]; Binding
0x1800539ee  call    cs:__imp_RpcBindingFree
0x1800539f4  test    eax, eax
0x1800539f6  jz      short loc_1800539FF
0x1800539f8  mov     edx, eax
0x1800539fa  call    MicrosoftTelemetryAssertTriggeredArgs
0x1800539ff  mov     [rsp+0A8h+Binding], 0
0x180053a08  mov     rcx, cs:WPP_GLOBAL_Control
0x180053a0f  cmp     rcx, r14
0x180053a12  jz      short loc_180053A32
0x180053a14  test    byte ptr [rcx+1Ch], 8
0x180053a18  jz      short loc_180053A32
0x180053a1a  mov     edx, 262h
0x180053a1f  mov     r9d, ebx
0x180053a22  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180053a29  mov     rcx, [rcx+10h]
0x180053a2d  call    WPP_SF_d
0x180053a32  mov     eax, ebx
0x180053a34  mov     rcx, [rsp+0A8h+var_38]
0x180053a39  xor     rcx, rsp; StackCookie
0x180053a3c  call    __security_check_cookie
0x180053a41  mov     rbx, [rsp+0A8h+arg_10]
0x180053a49  add     rsp, 80h
0x180053a50  pop     r15
0x180053a52  pop     r14
0x180053a54  pop     r13
0x180053a56  pop     r12
0x180053a58  pop     rsi
0x180053a59  retn
0x18005bb34  push    rbp
0x18005bb36  sub     rsp, 40h
0x18005bb3a  mov     rbp, rdx
0x18005bb3d  mov     rcx, [rcx]
0x18005bb40  mov     ecx, [rcx]; ExceptionCode
0x18005bb42  call    cs:__imp_RpcExceptionFilter
0x18005bb48  nop
0x18005bb49  add     rsp, 40h
0x18005bb4d  pop     rbp
0x18005bb4e  retn
```
