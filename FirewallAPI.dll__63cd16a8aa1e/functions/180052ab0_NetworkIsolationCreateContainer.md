# NetworkIsolationCreateContainer

- ea: `0x180052ab0`
- end: `0x180052e7f`
- name: `NetworkIsolationCreateContainer`
- size: `975`
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
- `0x180052ab0`
- `0x180054fcc`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180052d6a`
- `RPCRT4!NdrClientCall3` at `0x180052d6a`
- `RPCRT4!RpcBindingFree` at `0x180052e14`
- `RPCRT4!RpcBindingFree` at `0x180052e14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052c0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052c97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052c0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180052c97`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180052c8d`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180052c8d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180052ddf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180052ddf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180052bba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180052bba`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180052bfc`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180052bfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180052be8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180052be8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180052bd6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180052bd6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180052b57`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180052b57`
- `fwbase!FwBaseFree` at `0x180052dfb`
- `fwbase!FwBaseFree` at `0x180052dfb`
- `fwbase!FwCloseHandle` at `0x180052ded`
- `fwbase!FwCloseHandle` at `0x180052ded`
- `fwbase!FwHResultToWindowsError` at `0x180052c5b`
- `fwbase!FwHResultToWindowsError` at `0x180052c5b`
- `fwbase!FwGetTokenInformation` at `0x180052c53`
- `fwbase!FwGetTokenInformation` at `0x180052c53`

## pseudocode

```c
__int64 __fastcall NetworkIsolationCreateContainer(
        int a1,
        const wchar_t *a2,
        const wchar_t *a3,
        int a4,
        __int64 a5,
        int a6)
{
  char v6; // r15
  int v10; // r12d
  const wchar_t *v11; // r8
  const wchar_t *v12; // rdx
  HANDLE CurrentThread; // rax
  BOOL v14; // eax
  int v15; // r15d
  HANDLE CurrentProcess; // rax
  DWORD LastError; // eax
  DWORD v18; // ebx
  FwPolicy2 *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // r9
  unsigned int TokenInformation; // eax
  unsigned int Pointer; // eax
  unsigned int v24; // eax
  __int64 v25; // rcx
  __int64 v27; // [rsp+20h] [rbp-C8h]
  __int64 v28; // [rsp+40h] [rbp-A8h]
  void *TokenHandle; // [rsp+90h] [rbp-58h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp-50h] BYREF
  _QWORD *v34; // [rsp+A0h] [rbp-48h] BYREF

  v6 = a4;
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 595, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids);
  Binding = 0;
  v34 = 0;
  TokenHandle = 0;
  v10 = 0;
  GetTickCount64();
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v11 = a3;
    if ( !a3 )
      v11 = L"<null>";
    v12 = a2;
    if ( !a2 )
      v12 = L"<null>";
    WPP_SF_DSSDqD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)v12,
      (_DWORD)v11,
      a1,
      (__int64)v12,
      (__int64)v11,
      v6,
      a5,
      a6);
  }
  CurrentThread = GetCurrentThread();
  v14 = OpenThreadToken(CurrentThread, 0xCu, 1, &TokenHandle);
  if ( v14 )
  {
    v15 = 1;
  }
  else
  {
    v15 = 0;
    CurrentProcess = GetCurrentProcess();
    v14 = OpenProcessToken(CurrentProcess, 8u, &TokenHandle);
  }
  if ( v14 )
  {
    TokenInformation = FwGetTokenInformation(TokenHandle, 1, &v34, 0);
    LastError = FwHResultToWindowsError(TokenInformation);
    v18 = LastError;
    if ( !LastError )
    {
      if ( v15 == 1 )
      {
        if ( !RevertToSelf() )
        {
          LastError = GetLastError();
          v18 = LastError;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v20 = 599;
            goto LABEL_18;
          }
          goto LABEL_38;
        }
        v10 = 1;
      }
      LastError = Int_FWLocalRpcBindingCreate(&Binding);
      v18 = LastError;
      if ( LastError )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v20 = 600;
          goto LABEL_18;
        }
      }
      else
      {
        LODWORD(v28) = a4;
        LODWORD(v27) = a1;
        Pointer = (unsigned int)NdrClientCall3(
                                  (MIDL_STUBLESS_PROXY_INFO *)&FW_NET_ISO_DIAG_ProxyInfo,
                                  2u,
                                  0,
                                  Binding,
                                  v27,
                                  *v34,
                                  a2,
                                  a3,
                                  v28,
                                  a5,
                                  a6).Pointer;
        v18 = Pointer;
        if ( Pointer )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v20 = 601;
            v21 = Pointer;
            goto LABEL_37;
          }
        }
      }
      goto LABEL_38;
    }
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v20 = 598;
      goto LABEL_18;
    }
  }
  else
  {
    LastError = GetLastError();
    v18 = LastError;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v20 = 597;
LABEL_18:
      v21 = LastError;
LABEL_37:
      WPP_SF_d(*((_QWORD *)v19 + 2), v20, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v21);
    }
  }
LABEL_38:
  if ( v15 == 1 && v10 == 1 )
    SetThreadToken(0, TokenHandle);
  FwCloseHandle(TokenHandle);
  FwBaseFree(v34);
  if ( Binding )
  {
    v24 = RpcBindingFree(&Binding);
    if ( v24 )
      MicrosoftTelemetryAssertTriggeredArgs(v25, v24);
    Binding = 0;
  }
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 602, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids, v18);
  return v18;
}

```

## disassembly

```asm
0x180052ab0  push    rbx
0x180052ab2  push    rsi
0x180052ab3  push    r12
0x180052ab5  push    r13
0x180052ab7  push    r14
0x180052ab9  push    r15
0x180052abb  sub     rsp, 0B8h
0x180052ac2  mov     rax, cs:__security_cookie
0x180052ac9  xor     rax, rsp
0x180052acc  mov     [rsp+0E8h+var_40], rax
0x180052ad4  mov     r15d, r9d
0x180052ad7  mov     [rsp+0E8h+var_80], r9d
0x180052adc  mov     rbx, r8
0x180052adf  mov     [rsp+0E8h+var_68], rbx
0x180052ae7  mov     r13, rdx
0x180052aea  mov     esi, ecx
0x180052aec  mov     [rsp+0E8h+var_7C], ecx
0x180052af0  mov     rax, [rsp+0E8h+arg_20]
0x180052af8  mov     [rsp+0E8h+var_70], rax
0x180052afd  lea     r14, WPP_GLOBAL_Control
0x180052b04  mov     rcx, cs:WPP_GLOBAL_Control
0x180052b0b  cmp     rcx, r14
0x180052b0e  jz      short loc_180052B2B
0x180052b10  test    byte ptr [rcx+1Ch], 8
0x180052b14  jz      short loc_180052B2B
0x180052b16  mov     edx, 253h
0x180052b1b  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180052b22  mov     rcx, [rcx+10h]
0x180052b26  call    WPP_SF_
0x180052b2b  mov     [rsp+0E8h+Binding], 0
0x180052b37  mov     [rsp+0E8h+var_48], 0
0x180052b43  mov     [rsp+0E8h+TokenHandle], 0
0x180052b4f  xor     r12d, r12d
0x180052b52  mov     [rsp+0E8h+var_84], r12d
0x180052b57  call    cs:__imp_GetTickCount64
0x180052b5d  mov     rcx, cs:WPP_GLOBAL_Control
0x180052b64  cmp     rcx, r14
0x180052b67  jz      short loc_180052BBA
0x180052b69  test    byte ptr [rcx+1Ch], 4
0x180052b6d  jz      short loc_180052BBA
0x180052b6f  lea     rax, aNull; "<null>"
0x180052b76  mov     r8, rbx
0x180052b79  test    rbx, rbx
0x180052b7c  cmovz   r8, rax
0x180052b80  mov     rdx, r13
0x180052b83  test    r13, r13
0x180052b86  cmovz   rdx, rax
0x180052b8a  mov     eax, [rsp+0E8h+arg_28]
0x180052b91  mov     dword ptr [rsp+0E8h+var_A8], eax
0x180052b95  mov     rax, [rsp+0E8h+var_70]
0x180052b9a  mov     [rsp+0E8h+var_B0], rax
0x180052b9f  mov     dword ptr [rsp+0E8h+var_B8], r15d
0x180052ba4  mov     [rsp+0E8h+var_C0], r8
0x180052ba9  mov     [rsp+0E8h+var_C8], rdx
0x180052bae  mov     r9d, esi
0x180052bb1  mov     rcx, [rcx+10h]
0x180052bb5  call    WPP_SF_DSSDqD
0x180052bba  call    cs:__imp_GetCurrentThread
0x180052bc0  mov     rcx, rax; ThreadHandle
0x180052bc3  lea     r9, [rsp+0E8h+TokenHandle]; TokenHandle
0x180052bcb  mov     esi, 1
0x180052bd0  mov     r8d, esi; OpenAsSelf
0x180052bd3  lea     edx, [rsi+0Bh]; DesiredAccess
0x180052bd6  call    cs:__imp_OpenThreadToken
0x180052bdc  test    eax, eax
0x180052bde  jnz     short loc_180052C04
0x180052be0  xor     r15d, r15d
0x180052be3  mov     [rsp+0E8h+var_88], r15d
0x180052be8  call    cs:__imp_GetCurrentProcess
0x180052bee  mov     rcx, rax; ProcessHandle
0x180052bf1  lea     r8, [rsp+0E8h+TokenHandle]; TokenHandle
0x180052bf9  lea     edx, [rsi+7]; DesiredAccess
0x180052bfc  call    cs:__imp_OpenProcessToken
0x180052c02  jmp     short loc_180052C0B
0x180052c04  mov     r15d, esi
0x180052c07  mov     [rsp+0E8h+var_88], esi
0x180052c0b  test    eax, eax
0x180052c0d  jnz     short loc_180052C3E
0x180052c0f  call    cs:__imp_GetLastError
0x180052c15  mov     ebx, eax
0x180052c17  mov     rcx, cs:WPP_GLOBAL_Control
0x180052c1e  cmp     rcx, r14
0x180052c21  jz      loc_180052DCB
0x180052c27  test    [rcx+1Ch], sil
0x180052c2b  jz      loc_180052DCB
0x180052c31  mov     edx, 255h
0x180052c36  mov     r9d, eax
0x180052c39  jmp     loc_180052DBB
0x180052c3e  xor     r9d, r9d
0x180052c41  lea     r8, [rsp+0E8h+var_48]
0x180052c49  mov     edx, esi
0x180052c4b  mov     rcx, [rsp+0E8h+TokenHandle]
0x180052c53  call    cs:__imp_FwGetTokenInformation
0x180052c59  mov     ecx, eax
0x180052c5b  call    cs:__imp_FwHResultToWindowsError
0x180052c61  mov     ebx, eax
0x180052c63  test    eax, eax
0x180052c65  jz      short loc_180052C88
0x180052c67  mov     rcx, cs:WPP_GLOBAL_Control
0x180052c6e  cmp     rcx, r14
0x180052c71  jz      loc_180052DCB
0x180052c77  test    [rcx+1Ch], sil
0x180052c7b  jz      loc_180052DCB
0x180052c81  mov     edx, 256h
0x180052c86  jmp     short loc_180052C36
0x180052c88  cmp     r15d, esi
0x180052c8b  jnz     short loc_180052CCA
0x180052c8d  call    cs:__imp_RevertToSelf
0x180052c93  test    eax, eax
0x180052c95  jnz     short loc_180052CC3
0x180052c97  call    cs:__imp_GetLastError
0x180052c9d  mov     ebx, eax
0x180052c9f  mov     rcx, cs:WPP_GLOBAL_Control
0x180052ca6  cmp     rcx, r14
0x180052ca9  jz      loc_180052DCB
0x180052caf  test    [rcx+1Ch], sil
0x180052cb3  jz      loc_180052DCB
0x180052cb9  mov     edx, 257h
0x180052cbe  jmp     loc_180052C36
0x180052cc3  mov     r12d, esi
0x180052cc6  mov     [rsp+0E8h+var_84], esi
0x180052cca  lea     rcx, [rsp+0E8h+Binding]
0x180052cd2  call    Int_FWLocalRpcBindingCreate
0x180052cd7  mov     ebx, eax
0x180052cd9  test    eax, eax
0x180052cdb  jz      short loc_180052D01
0x180052cdd  mov     rcx, cs:WPP_GLOBAL_Control
0x180052ce4  cmp     rcx, r14
0x180052ce7  jz      loc_180052DCB
0x180052ced  test    [rcx+1Ch], sil
0x180052cf1  jz      loc_180052DCB
0x180052cf7  mov     edx, 258h
0x180052cfc  jmp     loc_180052C36
0x180052d01  mov     rax, [rsp+0E8h+var_48]
0x180052d09  mov     rcx, [rax]
0x180052d0c  mov     [rsp+0E8h+var_60], 0
0x180052d18  mov     eax, [rsp+0E8h+arg_28]
0x180052d1f  mov     [rsp+0E8h+var_98], eax
0x180052d23  mov     rax, [rsp+0E8h+var_70]
0x180052d28  mov     [rsp+0E8h+var_A0], rax
0x180052d2d  mov     eax, [rsp+0E8h+var_80]
0x180052d31  mov     dword ptr [rsp+0E8h+var_A8], eax
0x180052d35  mov     rax, [rsp+0E8h+var_68]
0x180052d3d  mov     [rsp+0E8h+var_B0], rax
0x180052d42  mov     [rsp+0E8h+var_B8], r13
0x180052d47  mov     [rsp+0E8h+var_C0], rcx
0x180052d4c  mov     eax, [rsp+0E8h+var_7C]
0x180052d50  mov     dword ptr [rsp+0E8h+var_C8], eax
0x180052d54  mov     r9, [rsp+0E8h+Binding]
0x180052d5c  xor     r8d, r8d; pReturnValue
0x180052d5f  lea     edx, [r8+2]; nProcNum
0x180052d63  lea     rcx, ?FW_NET_ISO_DIAG_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180052d6a  call    cs:__imp_NdrClientCall3
0x180052d70  mov     rbx, rax
0x180052d73  mov     [rsp+0E8h+var_60], rax
0x180052d7b  mov     [rsp+0E8h+var_78], eax
0x180052d7f  jmp     short loc_180052D9D
0x180052d81  mov     ebx, eax
0x180052d83  mov     [rsp+0E8h+var_78], eax
0x180052d87  lea     r14, WPP_GLOBAL_Control
0x180052d8e  mov     esi, 1
0x180052d93  mov     r15d, [rsp+0E8h+var_88]
0x180052d98  mov     r12d, [rsp+0E8h+var_84]
0x180052d9d  test    ebx, ebx
0x180052d9f  jz      short loc_180052DCB
0x180052da1  mov     rcx, cs:WPP_GLOBAL_Control
0x180052da8  cmp     rcx, r14
0x180052dab  jz      short loc_180052DCB
0x180052dad  test    [rcx+1Ch], sil
0x180052db1  jz      short loc_180052DCB
0x180052db3  mov     edx, 259h
0x180052db8  mov     r9d, ebx
0x180052dbb  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180052dc2  mov     rcx, [rcx+10h]
0x180052dc6  call    WPP_SF_d
0x180052dcb  cmp     r15d, esi
0x180052dce  jnz     short loc_180052DE5
0x180052dd0  cmp     r12d, esi
0x180052dd3  jnz     short loc_180052DE5
0x180052dd5  mov     rdx, [rsp+0E8h+TokenHandle]; Token
0x180052ddd  xor     ecx, ecx; Thread
0x180052ddf  call    cs:__imp_SetThreadToken
0x180052de5  mov     rcx, [rsp+0E8h+TokenHandle]
0x180052ded  call    cs:__imp_FwCloseHandle
0x180052df3  mov     rcx, [rsp+0E8h+var_48]
0x180052dfb  call    cs:__imp_FwBaseFree
0x180052e01  cmp     [rsp+0E8h+Binding], 0
0x180052e0a  jz      short loc_180052E31
0x180052e0c  lea     rcx, [rsp+0E8h+Binding]; Binding
0x180052e14  call    cs:__imp_RpcBindingFree
0x180052e1a  test    eax, eax
0x180052e1c  jz      short loc_180052E25
0x180052e1e  mov     edx, eax
0x180052e20  call    MicrosoftTelemetryAssertTriggeredArgs
0x180052e25  mov     [rsp+0E8h+Binding], 0
0x180052e31  mov     rcx, cs:WPP_GLOBAL_Control
0x180052e38  cmp     rcx, r14
0x180052e3b  jz      short loc_180052E5B
0x180052e3d  test    byte ptr [rcx+1Ch], 8
0x180052e41  jz      short loc_180052E5B
0x180052e43  mov     edx, 25Ah
0x180052e48  mov     r9d, ebx
0x180052e4b  lea     r8, WPP_e655d53778c4302b6aff4b61bf8e0cac_Traceguids
0x180052e52  mov     rcx, [rcx+10h]
0x180052e56  call    WPP_SF_d
0x180052e5b  mov     eax, ebx
0x180052e5d  mov     rcx, [rsp+0E8h+var_40]
0x180052e65  xor     rcx, rsp; StackCookie
0x180052e68  call    __security_check_cookie
0x180052e6d  add     rsp, 0B8h
0x180052e74  pop     r15
0x180052e76  pop     r14
0x180052e78  pop     r13
0x180052e7a  pop     r12
0x180052e7c  pop     rsi
0x180052e7d  pop     rbx
0x180052e7e  retn
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
