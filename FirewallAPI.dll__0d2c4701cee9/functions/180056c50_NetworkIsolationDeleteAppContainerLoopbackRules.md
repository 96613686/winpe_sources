# NetworkIsolationDeleteAppContainerLoopbackRules

- ea: `0x180056c50`
- end: `0x180056fbe`
- name: `NetworkIsolationDeleteAppContainerLoopbackRules`
- size: `878`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005e0c`
- `0x18000ea10`
- `0x180026798`
- `0x1800294b0`
- `0x180056c50`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x1800603ee`
- `RPCRT4!RpcExceptionFilter` at `0x1800603ee`
- `RPCRT4!NdrClientCall3` at `0x180056ea1`
- `RPCRT4!NdrClientCall3` at `0x180056ea1`
- `RPCRT4!RpcBindingFree` at `0x180056f50`
- `RPCRT4!RpcBindingFree` at `0x180056f50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056dd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056d18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056dd3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180056dc3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180056dc3`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180056f12`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180056f12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180056cb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180056cb1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180056cff`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180056cff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180056ce8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180056ce8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180056cd0`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180056cd0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180056ca5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180056ca5`
- `fwbase!FwBaseFree` at `0x180056f37`
- `fwbase!FwBaseFree` at `0x180056f37`
- `fwbase!FwCloseHandle` at `0x180056f23`
- `fwbase!FwCloseHandle` at `0x180056f23`
- `fwbase!FwHResultToWindowsError` at `0x180056d84`
- `fwbase!FwHResultToWindowsError` at `0x180056d84`
- `fwbase!FwGetTokenInformation` at `0x180056d76`
- `fwbase!FwGetTokenInformation` at `0x180056d76`

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
            v15 = 618;
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
          v15 = 619;
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
            v15 = 620;
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
      v15 = 617;
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
      v15 = 616;
LABEL_8:
      v16 = LastError;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v16);
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
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 621, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v13);
  return v13;
}

```

## disassembly

```asm
0x180056c50  mov     r11, rsp
0x180056c53  push    rbx
0x180056c54  push    rsi
0x180056c55  push    rdi
0x180056c56  push    r12
0x180056c58  push    r13
0x180056c5a  push    r15
0x180056c5c  sub     rsp, 98h
0x180056c63  mov     rax, cs:__security_cookie
0x180056c6a  xor     rax, rsp
0x180056c6d  mov     [rsp+0C8h+var_40], rax
0x180056c75  mov     [rsp+0C8h+var_68], r9
0x180056c7a  mov     [rsp+0C8h+var_70], r8d
0x180056c7f  mov     r13, rdx
0x180056c82  mov     rdi, rcx
0x180056c85  mov     qword ptr [r11-50h], 0
0x180056c8d  mov     qword ptr [r11-48h], 0
0x180056c95  mov     qword ptr [r11-58h], 0
0x180056c9d  xor     r12d, r12d
0x180056ca0  mov     [rsp+0C8h+var_74], r12d
0x180056ca5  call    cs:__imp_GetTickCount64
0x180056cac  nop     dword ptr [rax+rax+00h]
0x180056cb1  call    cs:__imp_GetCurrentThread
0x180056cb8  nop     dword ptr [rax+rax+00h]
0x180056cbd  mov     rcx, rax; ThreadHandle
0x180056cc0  lea     r9, [rsp+0C8h+TokenHandle]; TokenHandle
0x180056cc5  lea     esi, [r12+1]
0x180056cca  mov     r8d, esi; OpenAsSelf
0x180056ccd  lea     edx, [rsi+0Bh]; DesiredAccess
0x180056cd0  call    cs:__imp_OpenThreadToken
0x180056cd7  nop     dword ptr [rax+rax+00h]
0x180056cdc  test    eax, eax
0x180056cde  jnz     short loc_180056D0D
0x180056ce0  xor     r15d, r15d
0x180056ce3  mov     [rsp+0C8h+var_78], r15d
0x180056ce8  call    cs:__imp_GetCurrentProcess
0x180056cef  nop     dword ptr [rax+rax+00h]
0x180056cf4  mov     rcx, rax; ProcessHandle
0x180056cf7  lea     r8, [rsp+0C8h+TokenHandle]; TokenHandle
0x180056cfc  lea     edx, [rsi+7]; DesiredAccess
0x180056cff  call    cs:__imp_OpenProcessToken
0x180056d06  nop     dword ptr [rax+rax+00h]
0x180056d0b  jmp     short loc_180056D14
0x180056d0d  mov     r15d, esi
0x180056d10  mov     [rsp+0C8h+var_78], esi
0x180056d14  test    eax, eax
0x180056d16  jnz     short loc_180056D64
0x180056d18  call    cs:__imp_GetLastError
0x180056d1f  nop     dword ptr [rax+rax+00h]
0x180056d24  mov     ebx, eax
0x180056d26  lea     rdi, WPP_GLOBAL_Control
0x180056d2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056d34  cmp     rcx, rdi
0x180056d37  jz      loc_180056F01
0x180056d3d  test    [rcx+1Ch], sil
0x180056d41  jz      loc_180056F01
0x180056d47  mov     edx, 268h
0x180056d4c  mov     r9d, eax
0x180056d4f  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180056d56  mov     rcx, [rcx+10h]
0x180056d5a  call    WPP_SF_d
0x180056d5f  jmp     loc_180056F01
0x180056d64  xor     r9d, r9d
0x180056d67  lea     r8, [rsp+0C8h+var_48]
0x180056d6f  mov     edx, esi
0x180056d71  mov     rcx, [rsp+0C8h+TokenHandle]
0x180056d76  call    cs:__imp_FwGetTokenInformation
0x180056d7d  nop     dword ptr [rax+rax+00h]
0x180056d82  mov     ecx, eax
0x180056d84  call    cs:__imp_FwHResultToWindowsError
0x180056d8b  nop     dword ptr [rax+rax+00h]
0x180056d90  mov     ebx, eax
0x180056d92  test    eax, eax
0x180056d94  jz      short loc_180056DBE
0x180056d96  lea     rdi, WPP_GLOBAL_Control
0x180056d9d  mov     rcx, cs:WPP_GLOBAL_Control
0x180056da4  cmp     rcx, rdi
0x180056da7  jz      loc_180056F01
0x180056dad  test    [rcx+1Ch], sil
0x180056db1  jz      loc_180056F01
0x180056db7  mov     edx, 269h
0x180056dbc  jmp     short loc_180056D4C
0x180056dbe  cmp     r15d, esi
0x180056dc1  jnz     short loc_180056E13
0x180056dc3  call    cs:__imp_RevertToSelf
0x180056dca  nop     dword ptr [rax+rax+00h]
0x180056dcf  test    eax, eax
0x180056dd1  jnz     short loc_180056E0C
0x180056dd3  call    cs:__imp_GetLastError
0x180056dda  nop     dword ptr [rax+rax+00h]
0x180056ddf  mov     ebx, eax
0x180056de1  lea     rdi, WPP_GLOBAL_Control
0x180056de8  mov     rcx, cs:WPP_GLOBAL_Control
0x180056def  cmp     rcx, rdi
0x180056df2  jz      loc_180056F01
0x180056df8  test    [rcx+1Ch], sil
0x180056dfc  jz      loc_180056F01
0x180056e02  mov     edx, 26Ah
0x180056e07  jmp     loc_180056D4C
0x180056e0c  mov     r12d, esi
0x180056e0f  mov     [rsp+0C8h+var_74], esi
0x180056e13  lea     rcx, [rsp+0C8h+Binding]
0x180056e18  call    Int_FWLocalRpcBindingCreate
0x180056e1d  mov     ebx, eax
0x180056e1f  test    eax, eax
0x180056e21  jz      short loc_180056E4E
0x180056e23  lea     rdi, WPP_GLOBAL_Control
0x180056e2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180056e31  cmp     rcx, rdi
0x180056e34  jz      loc_180056F01
0x180056e3a  test    [rcx+1Ch], sil
0x180056e3e  jz      loc_180056F01
0x180056e44  mov     edx, 26Bh
0x180056e49  jmp     loc_180056D4C
0x180056e4e  mov     rax, [rsp+0C8h+var_48]
0x180056e56  mov     rcx, [rax]
0x180056e59  mov     [rsp+0C8h+var_60], 0
0x180056e62  mov     eax, [rsp+0C8h+arg_20]
0x180056e69  mov     [rsp+0C8h+var_80], eax
0x180056e6d  mov     rax, [rsp+0C8h+var_68]
0x180056e72  mov     [rsp+0C8h+var_88], rax
0x180056e77  mov     eax, [rsp+0C8h+var_70]
0x180056e7b  mov     [rsp+0C8h+var_90], eax
0x180056e7f  mov     [rsp+0C8h+var_98], r13
0x180056e84  mov     [rsp+0C8h+var_A0], rdi
0x180056e89  mov     [rsp+0C8h+var_A8], rcx
0x180056e8e  mov     r9, [rsp+0C8h+Binding]
0x180056e93  xor     r8d, r8d; pReturnValue
0x180056e96  lea     edx, [r8+0Ah]; nProcNum
0x180056e9a  lea     rcx, ?FW_NET_ISO_DIAG_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180056ea1  call    cs:__imp_NdrClientCall3
0x180056ea8  nop     dword ptr [rax+rax+00h]
0x180056ead  mov     rbx, rax
0x180056eb0  mov     [rsp+0C8h+var_60], rax
0x180056eb5  mov     [rsp+0C8h+var_6C], eax
0x180056eb9  jmp     short loc_180056ED0
0x180056ebb  mov     ebx, eax
0x180056ebd  mov     [rsp+0C8h+var_6C], eax
0x180056ec1  mov     esi, 1
0x180056ec6  mov     r15d, [rsp+0C8h+var_78]
0x180056ecb  mov     r12d, [rsp+0C8h+var_74]
0x180056ed0  test    ebx, ebx
0x180056ed2  jz      short loc_180056EFA
0x180056ed4  lea     rdi, WPP_GLOBAL_Control
0x180056edb  mov     rcx, cs:WPP_GLOBAL_Control
0x180056ee2  cmp     rcx, rdi
0x180056ee5  jz      short loc_180056F01
0x180056ee7  test    [rcx+1Ch], sil
0x180056eeb  jz      short loc_180056F01
0x180056eed  mov     edx, 26Ch
0x180056ef2  mov     r9d, ebx
0x180056ef5  jmp     loc_180056D4F
0x180056efa  lea     rdi, WPP_GLOBAL_Control
0x180056f01  cmp     r15d, esi
0x180056f04  jnz     short loc_180056F1E
0x180056f06  cmp     r12d, esi
0x180056f09  jnz     short loc_180056F1E
0x180056f0b  mov     rdx, [rsp+0C8h+TokenHandle]; Token
0x180056f10  xor     ecx, ecx; Thread
0x180056f12  call    cs:__imp_SetThreadToken
0x180056f19  nop     dword ptr [rax+rax+00h]
0x180056f1e  mov     rcx, [rsp+0C8h+TokenHandle]
0x180056f23  call    cs:__imp_FwCloseHandle
0x180056f2a  nop     dword ptr [rax+rax+00h]
0x180056f2f  mov     rcx, [rsp+0C8h+var_48]
0x180056f37  call    cs:__imp_FwBaseFree
0x180056f3e  nop     dword ptr [rax+rax+00h]
0x180056f43  cmp     [rsp+0C8h+Binding], 0
0x180056f49  jz      short loc_180056F70
0x180056f4b  lea     rcx, [rsp+0C8h+Binding]; Binding
0x180056f50  call    cs:__imp_RpcBindingFree
0x180056f57  nop     dword ptr [rax+rax+00h]
0x180056f5c  test    eax, eax
0x180056f5e  jz      short loc_180056F67
0x180056f60  mov     edx, eax; __annotation("Debug", "TelemetryAssert", "status == RPC_S_OK", "RpcBindingFree")
0x180056f62  call    MicrosoftTelemetryAssertTriggeredArgs
0x180056f67  mov     [rsp+0C8h+Binding], 0
0x180056f70  mov     rcx, cs:WPP_GLOBAL_Control
0x180056f77  cmp     rcx, rdi
0x180056f7a  jz      short loc_180056F9A
0x180056f7c  test    byte ptr [rcx+1Ch], 8
0x180056f80  jz      short loc_180056F9A
0x180056f82  mov     edx, 26Dh
0x180056f87  mov     r9d, ebx
0x180056f8a  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180056f91  mov     rcx, [rcx+10h]
0x180056f95  call    WPP_SF_d
0x180056f9a  mov     eax, ebx
0x180056f9c  mov     rcx, [rsp+0C8h+var_40]
0x180056fa4  xor     rcx, rsp; StackCookie
0x180056fa7  call    __security_check_cookie
0x180056fac  add     rsp, 98h
0x180056fb3  pop     r15
0x180056fb5  pop     r13
0x180056fb7  pop     r12
0x180056fb9  pop     rdi
0x180056fba  pop     rsi
0x180056fbb  pop     rbx
0x180056fbc  retn
0x1800603e0  push    rbp
0x1800603e2  sub     rsp, 50h
0x1800603e6  mov     rbp, rdx
0x1800603e9  mov     rcx, [rcx]
0x1800603ec  mov     ecx, [rcx]; ExceptionCode
0x1800603ee  call    cs:__imp_RpcExceptionFilter
0x1800603f5  nop     dword ptr [rax+rax+00h]
0x1800603fa  nop
0x1800603fb  add     rsp, 50h
0x1800603ff  pop     rbp
0x180060400  retn
```
