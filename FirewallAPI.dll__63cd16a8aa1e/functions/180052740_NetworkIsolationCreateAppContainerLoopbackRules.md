# NetworkIsolationCreateAppContainerLoopbackRules

- ea: `0x180052740`
- end: `0x180052aa1`
- name: `NetworkIsolationCreateAppContainerLoopbackRules`
- size: `865`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005954`
- `0x18000e960`
- `0x180024c3c`
- `0x1800277b0`
- `0x180052740`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180052991`
- `RPCRT4!NdrClientCall3` at `0x180052991`
- `RPCRT4!RpcBindingFree` at `0x180052a37`
- `RPCRT4!RpcBindingFree` at `0x180052a37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800528a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800528a6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005289c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18005289c`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180052a02`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180052a02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800527ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800527ab`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800527ed`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800527ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800527d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800527d9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800527c7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1800527c7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800527a5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800527a5`
- `fwbase!FwBaseFree` at `0x180052a1e`
- `fwbase!FwBaseFree` at `0x180052a1e`
- `fwbase!FwCloseHandle` at `0x180052a10`
- `fwbase!FwCloseHandle` at `0x180052a10`
- `fwbase!FwHResultToWindowsError` at `0x180052863`
- `fwbase!FwHResultToWindowsError` at `0x180052863`
- `fwbase!FwGetTokenInformation` at `0x18005285b`
- `fwbase!FwGetTokenInformation` at `0x18005285b`

## pseudocode

```c
__int64 __fastcall NetworkIsolationCreateAppContainerLoopbackRules(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int a7)
{
  int v9; // r12d
  HANDLE CurrentThread; // rax
  BOOL v11; // eax
  int v12; // r15d
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  DWORD v15; // ebx
  FwPolicy2 *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  unsigned int TokenInformation; // eax
  unsigned int Pointer; // eax
  unsigned int v21; // eax
  __int64 v22; // rcx
  __int64 v24; // [rsp+60h] [rbp-88h]
  void *TokenHandle; // [rsp+90h] [rbp-58h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp-50h] BYREF
  _QWORD *v29; // [rsp+A0h] [rbp-48h] BYREF

  Binding = 0;
  v29 = 0;
  TokenHandle = 0;
  v9 = 0;
  HIDWORD(v24) = 0;
  GetTickCount64();
  CurrentThread = GetCurrentThread();
  v11 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  if ( v11 )
  {
    v12 = 1;
    LODWORD(v24) = 1;
  }
  else
  {
    v12 = 0;
    LODWORD(v24) = 0;
    CurrentProcess = GetCurrentProcess();
    v11 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  }
  if ( v11 )
  {
    TokenInformation = FwGetTokenInformation(TokenHandle, 1, &v29, 0);
    LastError = FwHResultToWindowsError(TokenInformation);
    v15 = LastError;
    if ( !LastError )
    {
      if ( v12 == 1 )
      {
        if ( !RevertToSelf() )
        {
          LastError = GetLastError();
          v15 = LastError;
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v17 = 613;
            goto LABEL_8;
          }
          goto LABEL_28;
        }
        v9 = 1;
        HIDWORD(v24) = 1;
      }
      LastError = Int_FWLocalRpcBindingCreate(&Binding);
      v15 = LastError;
      if ( LastError )
      {
        v16 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v17 = 614;
          goto LABEL_8;
        }
      }
      else
      {
        Pointer = (unsigned int)NdrClientCall3(
                                  (MIDL_STUBLESS_PROXY_INFO *)&FW_NET_ISO_DIAG_ProxyInfo,
                                  9u,
                                  0,
                                  Binding,
                                  *v29,
                                  a1,
                                  a2,
                                  a3,
                                  a4,
                                  a5,
                                  a6,
                                  a7,
                                  v24).Pointer;
        v15 = Pointer;
        if ( Pointer )
        {
          v16 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v17 = 615;
            v18 = Pointer;
            goto LABEL_9;
          }
        }
      }
      goto LABEL_28;
    }
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 612;
      goto LABEL_8;
    }
  }
  else
  {
    LastError = GetLastError();
    v15 = LastError;
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v17 = 611;
LABEL_8:
      v18 = LastError;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v16 + 2), v17, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v18);
    }
  }
LABEL_28:
  if ( v12 == 1 && v9 == 1 )
    SetThreadToken(0, TokenHandle);
  FwCloseHandle(TokenHandle);
  FwBaseFree(v29);
  if ( Binding )
  {
    v21 = RpcBindingFree(&Binding);
    if ( v21 )
      MicrosoftTelemetryAssertTriggeredArgs(v22, v21);
    Binding = 0;
  }
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 616, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v15);
  return v15;
}

```

## disassembly

```asm
0x180052740  mov     r11, rsp
0x180052743  push    rbx
0x180052744  push    rsi
0x180052745  push    rdi
0x180052746  push    r12
0x180052748  push    r13
0x18005274a  push    r15
0x18005274c  sub     rsp, 0B8h
0x180052753  mov     rax, cs:__security_cookie
0x18005275a  xor     rax, rsp
0x18005275d  mov     [rsp+0E8h+var_40], rax
0x180052765  mov     [rsp+0E8h+var_70], r9
0x18005276a  mov     [rsp+0E8h+var_68], r8
0x180052772  mov     r13, rdx
0x180052775  mov     rdi, rcx
0x180052778  mov     rax, [rsp+0E8h+arg_28]
0x180052780  mov     [rsp+0E8h+var_78], rax
0x180052785  mov     qword ptr [r11-50h], 0
0x18005278d  mov     qword ptr [r11-48h], 0
0x180052795  mov     qword ptr [r11-58h], 0
0x18005279d  xor     r12d, r12d
0x1800527a0  mov     [rsp+0E8h+var_84], r12d
0x1800527a5  call    cs:__imp_GetTickCount64
0x1800527ab  call    cs:__imp_GetCurrentThread
0x1800527b1  mov     rcx, rax; ThreadHandle
0x1800527b4  lea     r9, [rsp+0E8h+TokenHandle]; TokenHandle
0x1800527bc  lea     esi, [r12+1]
0x1800527c1  mov     r8d, esi; OpenAsSelf
0x1800527c4  lea     edx, [rsi+0Bh]; DesiredAccess
0x1800527c7  call    cs:__imp_OpenThreadToken
0x1800527cd  test    eax, eax
0x1800527cf  jnz     short loc_1800527F5
0x1800527d1  xor     r15d, r15d
0x1800527d4  mov     [rsp+0E8h+var_88], r15d
0x1800527d9  call    cs:__imp_GetCurrentProcess
0x1800527df  mov     rcx, rax; ProcessHandle
0x1800527e2  lea     r8, [rsp+0E8h+TokenHandle]; TokenHandle
0x1800527ea  lea     edx, [rsi+7]; DesiredAccess
0x1800527ed  call    cs:__imp_OpenProcessToken
0x1800527f3  jmp     short loc_1800527FC
0x1800527f5  mov     r15d, esi
0x1800527f8  mov     [rsp+0E8h+var_88], esi
0x1800527fc  test    eax, eax
0x1800527fe  jnz     short loc_180052846
0x180052800  call    cs:__imp_GetLastError
0x180052806  mov     ebx, eax
0x180052808  lea     rdi, WPP_GLOBAL_Control
0x18005280f  mov     rcx, cs:WPP_GLOBAL_Control
0x180052816  cmp     rcx, rdi
0x180052819  jz      loc_1800529EE
0x18005281f  test    [rcx+1Ch], sil
0x180052823  jz      loc_1800529EE
0x180052829  mov     edx, 263h
0x18005282e  mov     r9d, eax
0x180052831  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180052838  mov     rcx, [rcx+10h]
0x18005283c  call    WPP_SF_d
0x180052841  jmp     loc_1800529EE
0x180052846  xor     r9d, r9d
0x180052849  lea     r8, [rsp+0E8h+var_48]
0x180052851  mov     edx, esi
0x180052853  mov     rcx, [rsp+0E8h+TokenHandle]
0x18005285b  call    cs:__imp_FwGetTokenInformation
0x180052861  mov     ecx, eax
0x180052863  call    cs:__imp_FwHResultToWindowsError
0x180052869  mov     ebx, eax
0x18005286b  test    eax, eax
0x18005286d  jz      short loc_180052897
0x18005286f  lea     rdi, WPP_GLOBAL_Control
0x180052876  mov     rcx, cs:WPP_GLOBAL_Control
0x18005287d  cmp     rcx, rdi
0x180052880  jz      loc_1800529EE
0x180052886  test    [rcx+1Ch], sil
0x18005288a  jz      loc_1800529EE
0x180052890  mov     edx, 264h
0x180052895  jmp     short loc_18005282E
0x180052897  cmp     r15d, esi
0x18005289a  jnz     short loc_1800528E0
0x18005289c  call    cs:__imp_RevertToSelf
0x1800528a2  test    eax, eax
0x1800528a4  jnz     short loc_1800528D9
0x1800528a6  call    cs:__imp_GetLastError
0x1800528ac  mov     ebx, eax
0x1800528ae  lea     rdi, WPP_GLOBAL_Control
0x1800528b5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800528bc  cmp     rcx, rdi
0x1800528bf  jz      loc_1800529EE
0x1800528c5  test    [rcx+1Ch], sil
0x1800528c9  jz      loc_1800529EE
0x1800528cf  mov     edx, 265h
0x1800528d4  jmp     loc_18005282E
0x1800528d9  mov     r12d, esi
0x1800528dc  mov     [rsp+0E8h+var_84], esi
0x1800528e0  lea     rcx, [rsp+0E8h+Binding]
0x1800528e8  call    Int_FWLocalRpcBindingCreate
0x1800528ed  mov     ebx, eax
0x1800528ef  test    eax, eax
0x1800528f1  jz      short loc_18005291E
0x1800528f3  lea     rdi, WPP_GLOBAL_Control
0x1800528fa  mov     rcx, cs:WPP_GLOBAL_Control
0x180052901  cmp     rcx, rdi
0x180052904  jz      loc_1800529EE
0x18005290a  test    [rcx+1Ch], sil
0x18005290e  jz      loc_1800529EE
0x180052914  mov     edx, 266h
0x180052919  jmp     loc_18005282E
0x18005291e  mov     rax, [rsp+0E8h+var_48]
0x180052926  mov     rcx, [rax]
0x180052929  mov     [rsp+0E8h+var_60], 0
0x180052935  mov     eax, [rsp+0E8h+arg_30]
0x18005293c  mov     [rsp+0E8h+var_90], eax
0x180052940  mov     rax, [rsp+0E8h+var_78]
0x180052945  mov     [rsp+0E8h+var_98], rax
0x18005294a  mov     eax, [rsp+0E8h+arg_20]
0x180052951  mov     [rsp+0E8h+var_A0], eax
0x180052955  mov     rax, [rsp+0E8h+var_70]
0x18005295a  mov     [rsp+0E8h+var_A8], rax
0x18005295f  mov     rax, [rsp+0E8h+var_68]
0x180052967  mov     [rsp+0E8h+var_B0], rax
0x18005296c  mov     [rsp+0E8h+var_B8], r13
0x180052971  mov     [rsp+0E8h+var_C0], rdi
0x180052976  mov     [rsp+0E8h+var_C8], rcx
0x18005297b  mov     r9, [rsp+0E8h+Binding]
0x180052983  xor     r8d, r8d; pReturnValue
0x180052986  lea     edx, [r8+9]; nProcNum
0x18005298a  lea     rcx, ?FW_NET_ISO_DIAG_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180052991  call    cs:__imp_NdrClientCall3
0x180052997  mov     rbx, rax
0x18005299a  mov     [rsp+0E8h+var_60], rax
0x1800529a2  mov     [rsp+0E8h+var_80], eax
0x1800529a6  jmp     short loc_1800529BD
0x1800529a8  mov     ebx, eax
0x1800529aa  mov     [rsp+0E8h+var_80], eax
0x1800529ae  mov     esi, 1
0x1800529b3  mov     r15d, [rsp+0E8h+var_88]
0x1800529b8  mov     r12d, [rsp+0E8h+var_84]
0x1800529bd  test    ebx, ebx
0x1800529bf  jz      short loc_1800529E7
0x1800529c1  lea     rdi, WPP_GLOBAL_Control
0x1800529c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800529cf  cmp     rcx, rdi
0x1800529d2  jz      short loc_1800529EE
0x1800529d4  test    [rcx+1Ch], sil
0x1800529d8  jz      short loc_1800529EE
0x1800529da  mov     edx, 267h
0x1800529df  mov     r9d, ebx
0x1800529e2  jmp     loc_180052831
0x1800529e7  lea     rdi, WPP_GLOBAL_Control
0x1800529ee  cmp     r15d, esi
0x1800529f1  jnz     short loc_180052A08
0x1800529f3  cmp     r12d, esi
0x1800529f6  jnz     short loc_180052A08
0x1800529f8  mov     rdx, [rsp+0E8h+TokenHandle]; Token
0x180052a00  xor     ecx, ecx; Thread
0x180052a02  call    cs:__imp_SetThreadToken
0x180052a08  mov     rcx, [rsp+0E8h+TokenHandle]
0x180052a10  call    cs:__imp_FwCloseHandle
0x180052a16  mov     rcx, [rsp+0E8h+var_48]
0x180052a1e  call    cs:__imp_FwBaseFree
0x180052a24  cmp     [rsp+0E8h+Binding], 0
0x180052a2d  jz      short loc_180052A54
0x180052a2f  lea     rcx, [rsp+0E8h+Binding]; Binding
0x180052a37  call    cs:__imp_RpcBindingFree
0x180052a3d  test    eax, eax
0x180052a3f  jz      short loc_180052A48
0x180052a41  mov     edx, eax
0x180052a43  call    MicrosoftTelemetryAssertTriggeredArgs
0x180052a48  mov     [rsp+0E8h+Binding], 0
0x180052a54  mov     rcx, cs:WPP_GLOBAL_Control
0x180052a5b  cmp     rcx, rdi
0x180052a5e  jz      short loc_180052A7E
0x180052a60  test    byte ptr [rcx+1Ch], 8
0x180052a64  jz      short loc_180052A7E
0x180052a66  mov     edx, 268h
0x180052a6b  mov     r9d, ebx
0x180052a6e  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180052a75  mov     rcx, [rcx+10h]
0x180052a79  call    WPP_SF_d
0x180052a7e  mov     eax, ebx
0x180052a80  mov     rcx, [rsp+0E8h+var_40]
0x180052a88  xor     rcx, rsp; StackCookie
0x180052a8b  call    __security_check_cookie
0x180052a90  add     rsp, 0B8h
0x180052a97  pop     r15
0x180052a99  pop     r13
0x180052a9b  pop     r12
0x180052a9d  pop     rdi
0x180052a9e  pop     rsi
0x180052a9f  pop     rbx
0x180052aa0  retn
0x18005c186  push    rbp
0x18005c188  sub     rsp, 60h
0x18005c18c  mov     rbp, rdx
0x18005c18f  mov     rcx, [rcx]
0x18005c192  mov     ecx, [rcx]; ExceptionCode
0x18005c194  call    cs:__imp_RpcExceptionFilter
0x18005c19a  nop
0x18005c19b  add     rsp, 60h
0x18005c19f  pop     rbp
0x18005c1a0  retn
```
