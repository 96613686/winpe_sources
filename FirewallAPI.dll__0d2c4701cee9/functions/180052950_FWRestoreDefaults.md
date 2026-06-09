# FWRestoreDefaults

- ea: `0x180052950`
- end: `0x180052c58`
- name: `FWRestoreDefaults`
- size: `776`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180039d60`
- `0x180039f60`

## callees

- `0x180005e0c`
- `0x18000e750`
- `0x18000ecb0`
- `0x180026c9c`
- `0x1800294b0`
- `0x18002a1f4`
- `0x18003336c`
- `0x180052950`

## import_xrefs

- `RPCRT4!RpcExceptionFilter` at `0x180060466`
- `RPCRT4!RpcExceptionFilter` at `0x180060488`
- `RPCRT4!RpcExceptionFilter` at `0x180060466`
- `RPCRT4!RpcExceptionFilter` at `0x180060488`
- `RPCRT4!NdrClientCall3` at `0x180052a7b`
- `RPCRT4!NdrClientCall3` at `0x180052b46`
- `RPCRT4!NdrClientCall3` at `0x180052a7b`
- `RPCRT4!NdrClientCall3` at `0x180052b46`
- `ntdll!EtwEventWrite` at `0x18005298b`
- `ntdll!EtwEventWrite` at `0x180052c28`
- `ntdll!EtwEventWrite` at `0x18005298b`
- `ntdll!EtwEventWrite` at `0x180052c28`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800529d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800529d5`

## pseudocode

```c
__int64 __fastcall FWRestoreDefaults(unsigned __int16 *a1)
{
  unsigned int v2; // eax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  unsigned int v6; // ebx
  unsigned int v7; // eax
  unsigned int v8; // eax
  unsigned int Pointer; // eax
  _BYTE v11[4]; // [rsp+40h] [rbp-68h] BYREF
  unsigned int v12; // [rsp+44h] [rbp-64h]
  __int64 v13; // [rsp+60h] [rbp-48h]

  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Enter_RestoreDefaults, 0, 0);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  memset_0(v11, 0, 0x50u);
  GetTickCount64();
  v2 = Int_FWCreateConnectionHandle(512, a1, 2, 2, 0, (__int64)v11);
  v6 = v2;
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 71, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v2);
  }
  else
  {
    v7 = v12;
    if ( v12 > 1 )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v4, v3, v5);
      v7 = v12;
    }
    if ( v7 )
    {
      if ( v7 == 1 )
      {
        Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&RemoteFW_ProxyInfo, 2u, 0, v13).Pointer;
        v6 = Pointer;
        if ( Pointer )
        {
          if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 74, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, Pointer);
        }
      }
    }
    else
    {
      v8 = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&FW_ProxyInfo, 2u, 0, v13).Pointer;
      v6 = v8;
      if ( v8
        && WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids, v8);
      }
    }
  }
  Int_FWClientHandleCleanup(v11);
  if ( WPP_GLOBAL_Control != (FwPolicy2 *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 76, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids);
  if ( g_Provider )
    EtwEventWrite(g_Provider, MPS_CLNT_API_Exit_RestoreDefaults, 0, 0);
  return v6;
}

```

## disassembly

```asm
0x180052950  mov     [rsp+arg_8], rbx
0x180052955  push    rdi
0x180052956  sub     rsp, 0A0h
0x18005295d  mov     rax, cs:__security_cookie
0x180052964  xor     rax, rsp
0x180052967  mov     [rsp+0A8h+var_18], rax
0x18005296f  mov     rbx, rcx
0x180052972  mov     rcx, cs:g_Provider
0x180052979  test    rcx, rcx
0x18005297c  jz      short loc_180052997
0x18005297e  xor     r9d, r9d
0x180052981  xor     r8d, r8d
0x180052984  lea     rdx, MPS_CLNT_API_Enter_RestoreDefaults
0x18005298b  call    cs:__imp_EtwEventWrite
0x180052992  nop     dword ptr [rax+rax+00h]
0x180052997  lea     rdi, WPP_GLOBAL_Control
0x18005299e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800529a5  cmp     rcx, rdi
0x1800529a8  jz      short loc_1800529C5
0x1800529aa  test    byte ptr [rcx+1Ch], 8
0x1800529ae  jz      short loc_1800529C5
0x1800529b0  mov     edx, 46h ; 'F'
0x1800529b5  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x1800529bc  mov     rcx, [rcx+10h]
0x1800529c0  call    WPP_SF_
0x1800529c5  xor     edx, edx; Val
0x1800529c7  lea     r8d, [rdx+50h]; Size
0x1800529cb  lea     rcx, [rsp+0A8h+var_68]; void *
0x1800529d0  call    memset_0
0x1800529d5  call    cs:__imp_GetTickCount64
0x1800529dc  nop     dword ptr [rax+rax+00h]
0x1800529e1  mov     ecx, 200h
0x1800529e6  lea     rax, [rsp+0A8h+var_68]
0x1800529eb  mov     [rsp+0A8h+var_80], rax
0x1800529f0  mov     [rsp+0A8h+var_88], 0
0x1800529f8  mov     r9d, 2
0x1800529fe  mov     r8d, r9d
0x180052a01  mov     rdx, rbx
0x180052a04  call    Int_FWCreateConnectionHandle
0x180052a09  mov     ebx, eax
0x180052a0b  test    eax, eax
0x180052a0d  jz      short loc_180052A46
0x180052a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180052a16  cmp     rcx, rdi
0x180052a19  jz      loc_180052BDE
0x180052a1f  test    byte ptr [rcx+1Ch], 1
0x180052a23  jz      loc_180052BDE
0x180052a29  mov     edx, 47h ; 'G'
0x180052a2e  mov     r9d, eax
0x180052a31  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180052a38  mov     rcx, [rcx+10h]
0x180052a3c  call    WPP_SF_d
0x180052a41  jmp     loc_180052BDE
0x180052a46  mov     eax, [rsp+0A8h+var_64]
0x180052a4a  cmp     eax, 1
0x180052a4d  jbe     short loc_180052A58
0x180052a4f  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "(hClient.HandleType == FWINT_CLIENT_HANDLE_LRPC || hClient.HandleType == FWINT_CLIENT_HANDLE_RRPC)")
0x180052a54  mov     eax, [rsp+0A8h+var_64]
0x180052a58  test    eax, eax
0x180052a5a  jnz     loc_180052B22
0x180052a60  mov     [rsp+0A8h+var_70], 0
0x180052a69  mov     r9, [rsp+0A8h+var_48]
0x180052a6e  xor     r8d, r8d; pReturnValue
0x180052a71  lea     edx, [rax+2]; nProcNum
0x180052a74  lea     rcx, ?FW_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180052a7b  call    cs:__imp_NdrClientCall3
0x180052a82  nop     dword ptr [rax+rax+00h]
0x180052a87  mov     rbx, rax
0x180052a8a  mov     [rsp+0A8h+var_70], rax
0x180052a8f  mov     [rsp+0A8h+var_78], eax
0x180052a93  mov     [rsp+0A8h+var_78], eax
0x180052a97  test    eax, eax
0x180052a99  jz      short loc_180052ACA
0x180052a9b  mov     rcx, cs:WPP_GLOBAL_Control
0x180052aa2  cmp     rcx, rdi
0x180052aa5  jz      short loc_180052AC5
0x180052aa7  test    byte ptr [rcx+1Ch], 1
0x180052aab  jz      short loc_180052AC5
0x180052aad  mov     edx, 48h ; 'H'
0x180052ab2  mov     r9d, eax
0x180052ab5  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180052abc  mov     rcx, [rcx+10h]
0x180052ac0  call    WPP_SF_d
0x180052ac5  jmp     loc_180052BDE
0x180052aca  jmp     loc_180052BDE
0x180052acf  mov     ebx, eax
0x180052ad1  mov     [rsp+0A8h+var_78], eax
0x180052ad5  test    eax, eax
0x180052ad7  jz      short loc_180052B16
0x180052ad9  lea     rdx, WPP_GLOBAL_Control
0x180052ae0  mov     rcx, cs:WPP_GLOBAL_Control
0x180052ae7  cmp     rcx, rdx
0x180052aea  jz      short loc_180052B0A
0x180052aec  test    byte ptr [rcx+1Ch], 1
0x180052af0  jz      short loc_180052B0A
0x180052af2  mov     edx, 49h ; 'I'
0x180052af7  mov     r9d, eax
0x180052afa  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180052b01  mov     rcx, [rcx+10h]
0x180052b05  call    WPP_SF_d
0x180052b0a  lea     rdi, WPP_GLOBAL_Control
0x180052b11  jmp     loc_180052BDE
0x180052b16  lea     rdi, WPP_GLOBAL_Control
0x180052b1d  jmp     loc_180052BDE
0x180052b22  cmp     eax, 1
0x180052b25  jnz     loc_180052BDE
0x180052b2b  mov     [rsp+0A8h+var_70], 0
0x180052b34  mov     r9, [rsp+0A8h+var_48]
0x180052b39  xor     r8d, r8d; pReturnValue
0x180052b3c  lea     edx, [rax+1]; nProcNum
0x180052b3f  lea     rcx, ?RemoteFW_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180052b46  call    cs:__imp_NdrClientCall3
0x180052b4d  nop     dword ptr [rax+rax+00h]
0x180052b52  mov     [rsp+0A8h+var_70], rax
0x180052b57  mov     [rsp+0A8h+var_78], eax
0x180052b5b  mov     ebx, eax
0x180052b5d  mov     [rsp+0A8h+var_78], eax
0x180052b61  test    eax, eax
0x180052b63  jz      short loc_180052B91
0x180052b65  mov     rcx, cs:WPP_GLOBAL_Control
0x180052b6c  cmp     rcx, rdi
0x180052b6f  jz      short loc_180052B8F
0x180052b71  test    byte ptr [rcx+1Ch], 1
0x180052b75  jz      short loc_180052B8F
0x180052b77  mov     edx, 4Ah ; 'J'
0x180052b7c  mov     r9d, eax
0x180052b7f  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180052b86  mov     rcx, [rcx+10h]
0x180052b8a  call    WPP_SF_d
0x180052b8f  jmp     short loc_180052BDE
0x180052b91  jmp     short loc_180052BDE
0x180052b93  mov     ebx, eax
0x180052b95  mov     [rsp+0A8h+var_78], eax
0x180052b99  test    eax, eax
0x180052b9b  jz      short loc_180052BD7
0x180052b9d  lea     rdx, WPP_GLOBAL_Control
0x180052ba4  mov     rcx, cs:WPP_GLOBAL_Control
0x180052bab  cmp     rcx, rdx
0x180052bae  jz      short loc_180052BCE
0x180052bb0  test    byte ptr [rcx+1Ch], 1
0x180052bb4  jz      short loc_180052BCE
0x180052bb6  mov     edx, 4Bh ; 'K'
0x180052bbb  mov     r9d, eax
0x180052bbe  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180052bc5  mov     rcx, [rcx+10h]
0x180052bc9  call    WPP_SF_d
0x180052bce  lea     rdi, WPP_GLOBAL_Control
0x180052bd5  jmp     short loc_180052BDE
0x180052bd7  lea     rdi, WPP_GLOBAL_Control
0x180052bde  lea     rcx, [rsp+0A8h+var_68]
0x180052be3  call    Int_FWClientHandleCleanup
0x180052be8  mov     rcx, cs:WPP_GLOBAL_Control
0x180052bef  cmp     rcx, rdi
0x180052bf2  jz      short loc_180052C0F
0x180052bf4  test    byte ptr [rcx+1Ch], 8
0x180052bf8  jz      short loc_180052C0F
0x180052bfa  mov     edx, 4Ch ; 'L'
0x180052bff  lea     r8, WPP_5cee58fa6cc33cb1a279f0ddc56bd48a_Traceguids
0x180052c06  mov     rcx, [rcx+10h]
0x180052c0a  call    WPP_SF_
0x180052c0f  mov     rcx, cs:g_Provider
0x180052c16  test    rcx, rcx
0x180052c19  jz      short loc_180052C34
0x180052c1b  xor     r9d, r9d
0x180052c1e  xor     r8d, r8d
0x180052c21  lea     rdx, MPS_CLNT_API_Exit_RestoreDefaults
0x180052c28  call    cs:__imp_EtwEventWrite
0x180052c2f  nop     dword ptr [rax+rax+00h]
0x180052c34  mov     eax, ebx
0x180052c36  mov     rcx, [rsp+0A8h+var_18]
0x180052c3e  xor     rcx, rsp; StackCookie
0x180052c41  call    __security_check_cookie
0x180052c46  mov     rbx, [rsp+0A8h+arg_8]
0x180052c4e  add     rsp, 0A0h
0x180052c55  pop     rdi
0x180052c56  retn
0x180060458  push    rbp
0x18006045a  sub     rsp, 30h
0x18006045e  mov     rbp, rdx
0x180060461  mov     rcx, [rcx]
0x180060464  mov     ecx, [rcx]; ExceptionCode
0x180060466  call    cs:__imp_RpcExceptionFilter
0x18006046d  nop     dword ptr [rax+rax+00h]
0x180060472  nop
0x180060473  add     rsp, 30h
0x180060477  pop     rbp
0x180060478  retn
0x18006047a  push    rbp
0x18006047c  sub     rsp, 30h
0x180060480  mov     rbp, rdx
0x180060483  mov     rcx, [rcx]
0x180060486  mov     ecx, [rcx]; ExceptionCode
0x180060488  call    cs:__imp_RpcExceptionFilter
0x18006048f  nop     dword ptr [rax+rax+00h]
0x180060494  nop
0x180060495  add     rsp, 30h
0x180060499  pop     rbp
0x18006049a  retn
```
