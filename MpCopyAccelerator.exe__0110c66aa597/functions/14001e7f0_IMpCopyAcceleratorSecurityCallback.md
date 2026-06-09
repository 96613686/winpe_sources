# IMpCopyAcceleratorSecurityCallback

- ea: `0x14001e7f0`
- end: `0x14001e9db`
- name: `IMpCopyAcceleratorSecurityCallback`
- size: `491`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140005c20`
- `0x14000b950`
- `0x14001da70`
- `0x14001dac4`
- `0x14001e7f0`
- `0x140024148`

## import_xrefs

- `RPCRT4!RpcStringBindingParseW` at `0x14001e884`
- `RPCRT4!RpcStringBindingParseW` at `0x14001e884`
- `RPCRT4!RpcStringFreeW` at `0x14001e9a4`
- `RPCRT4!RpcStringFreeW` at `0x14001e9b5`
- `RPCRT4!RpcStringFreeW` at `0x14001e9a4`
- `RPCRT4!RpcStringFreeW` at `0x14001e9b5`
- `RPCRT4!RpcBindingToStringBindingW` at `0x14001e839`
- `RPCRT4!RpcBindingToStringBindingW` at `0x14001e839`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x14001e94f`
- `RPCRT4!RpcBindingInqAuthClientW` at `0x14001e94f`

## string_xrefs

- `0x14001e8cb`: `Failed at security callback, request has been denied, status=0x%lx\n`

## pseudocode

```c
__int64 __fastcall IMpCopyAcceleratorSecurityCallback(__int64 a1, void *a2)
{
  unsigned int v3; // ebx
  _QWORD *v4; // rcx
  __int64 v5; // rdx
  RPC_WSTR Protseq; // [rsp+30h] [rbp-30h] BYREF
  RPC_WSTR StringBinding; // [rsp+38h] [rbp-28h] BYREF
  RPC_AUTHZ_HANDLE Privs; // [rsp+40h] [rbp-20h] BYREF
  unsigned int AuthnLevel; // [rsp+48h] [rbp-18h] BYREF

  StringBinding = 0;
  Protseq = 0;
  AuthnLevel = 1;
  Privs = 0;
  v3 = RpcBindingToStringBindingW(a2, &StringBinding);
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 10;
LABEL_9:
      WPP_SF_d(v4[2], v5, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids, v3);
      goto LABEL_10;
    }
    goto LABEL_10;
  }
  v3 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
  if ( v3 )
  {
    v4 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v5 = 11;
      goto LABEL_9;
    }
LABEL_10:
    if ( (v3 & 0x80000000) != 0 )
      MpCmdLogPrintf(L"Failed at security callback, request has been denied, status=0x%lx\n", v3);
    goto LABEL_22;
  }
  if ( wcsicmp(Protseq, L"ncalrpc") )
  {
    v3 = 5;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids, Protseq);
  }
  else
  {
    v3 = RpcBindingInqAuthClientW(a2, &Privs, 0, &AuthnLevel, 0, 0);
    if ( v3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids, v3);
    }
    else if ( AuthnLevel >= 6 )
    {
      goto LABEL_22;
    }
    v3 = 5;
  }
LABEL_22:
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return v3;
}

```

## disassembly

```asm
0x14001e7f0  mov     [rsp-8+arg_0], rbx
0x14001e7f5  mov     [rsp-8+arg_10], rdi
0x14001e7fa  push    rbp
0x14001e7fb  mov     rbp, rsp
0x14001e7fe  sub     rsp, 60h
0x14001e802  mov     rax, cs:__security_cookie
0x14001e809  xor     rax, rsp
0x14001e80c  mov     [rbp+var_10], rax
0x14001e810  mov     rdi, rdx
0x14001e813  mov     [rbp+StringBinding], 0
0x14001e81b  mov     rcx, rdi; Binding
0x14001e81e  mov     [rbp+Protseq], 0
0x14001e826  lea     rdx, [rbp+StringBinding]; StringBinding
0x14001e82a  mov     [rbp+AuthnLevel], 1
0x14001e831  mov     [rbp+Privs], 0
0x14001e839  call    cs:__imp_RpcBindingToStringBindingW
0x14001e83f  mov     ebx, eax
0x14001e841  test    eax, eax
0x14001e843  jz      short loc_14001E865
0x14001e845  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e84c  lea     rax, WPP_GLOBAL_Control
0x14001e853  cmp     rcx, rax
0x14001e856  jz      short loc_14001E8C1
0x14001e858  test    byte ptr [rcx+1Ch], 1
0x14001e85c  jz      short loc_14001E8C1
0x14001e85e  mov     edx, 0Ah
0x14001e863  jmp     short loc_14001E8AE
0x14001e865  mov     rcx, [rbp+StringBinding]; StringBinding
0x14001e869  lea     r8, [rbp+Protseq]; Protseq
0x14001e86d  mov     [rsp+60h+NetworkOptions], 0; NetworkOptions
0x14001e876  xor     r9d, r9d; NetworkAddr
0x14001e879  xor     edx, edx; ObjUuid
0x14001e87b  mov     [rsp+60h+Endpoint], 0; Endpoint
0x14001e884  call    cs:__imp_RpcStringBindingParseW
0x14001e88a  mov     ebx, eax
0x14001e88c  test    eax, eax
0x14001e88e  jz      short loc_14001E8DC
0x14001e890  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e897  lea     rax, WPP_GLOBAL_Control
0x14001e89e  cmp     rcx, rax
0x14001e8a1  jz      short loc_14001E8C1
0x14001e8a3  test    byte ptr [rcx+1Ch], 1
0x14001e8a7  jz      short loc_14001E8C1
0x14001e8a9  mov     edx, 0Bh
0x14001e8ae  mov     rcx, [rcx+10h]
0x14001e8b2  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001e8b9  mov     r9d, ebx
0x14001e8bc  call    WPP_SF_d
0x14001e8c1  test    ebx, ebx
0x14001e8c3  jns     loc_14001E999
0x14001e8c9  mov     edx, ebx
0x14001e8cb  lea     rcx, aFailedAtSecuri; "Failed at security callback, request ha"...
0x14001e8d2  call    ?MpCmdLogPrintf@@YAXPEB_WZZ; MpCmdLogPrintf(wchar_t const *,...)
0x14001e8d7  jmp     loc_14001E999
0x14001e8dc  mov     rcx, [rbp+Protseq]; String1
0x14001e8e0  lea     rdx, aNcalrpc; "ncalrpc"
0x14001e8e7  call    _wcsicmp
0x14001e8ec  test    eax, eax
0x14001e8ee  jz      short loc_14001E92F
0x14001e8f0  mov     ebx, 5
0x14001e8f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e8fc  lea     rax, WPP_GLOBAL_Control
0x14001e903  cmp     rcx, rax
0x14001e906  jz      loc_14001E999
0x14001e90c  test    byte ptr [rcx+1Ch], 1
0x14001e910  jz      loc_14001E999
0x14001e916  mov     r9, [rbp+Protseq]
0x14001e91a  lea     edx, [rbx+7]
0x14001e91d  mov     rcx, [rcx+10h]
0x14001e921  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001e928  call    WPP_SF_S
0x14001e92d  jmp     short loc_14001E999
0x14001e92f  mov     [rsp+60h+NetworkOptions], 0; AuthzSvc
0x14001e938  lea     r9, [rbp+AuthnLevel]; AuthnLevel
0x14001e93c  xor     r8d, r8d; ServerPrincName
0x14001e93f  mov     [rsp+60h+Endpoint], 0; AuthnSvc
0x14001e948  lea     rdx, [rbp+Privs]; Privs
0x14001e94c  mov     rcx, rdi; ClientBinding
0x14001e94f  call    cs:__imp_RpcBindingInqAuthClientW
0x14001e955  mov     ebx, eax
0x14001e957  test    eax, eax
0x14001e959  jz      short loc_14001E98E
0x14001e95b  mov     rcx, cs:WPP_GLOBAL_Control
0x14001e962  lea     rax, WPP_GLOBAL_Control
0x14001e969  cmp     rcx, rax
0x14001e96c  jz      short loc_14001E994
0x14001e96e  test    byte ptr [rcx+1Ch], 1
0x14001e972  jz      short loc_14001E994
0x14001e974  mov     rcx, [rcx+10h]
0x14001e978  lea     r8, WPP_8bd74dc90fc9383f1cca96c22ee052d7_Traceguids
0x14001e97f  mov     edx, 0Dh
0x14001e984  mov     r9d, ebx
0x14001e987  call    WPP_SF_d
0x14001e98c  jmp     short loc_14001E994
0x14001e98e  cmp     [rbp+AuthnLevel], 6
0x14001e992  jnb     short loc_14001E999
0x14001e994  mov     ebx, 5
0x14001e999  cmp     [rbp+Protseq], 0
0x14001e99e  jz      short loc_14001E9AA
0x14001e9a0  lea     rcx, [rbp+Protseq]; String
0x14001e9a4  call    cs:__imp_RpcStringFreeW
0x14001e9aa  cmp     [rbp+StringBinding], 0
0x14001e9af  jz      short loc_14001E9BB
0x14001e9b1  lea     rcx, [rbp+StringBinding]; String
0x14001e9b5  call    cs:__imp_RpcStringFreeW
0x14001e9bb  mov     eax, ebx
0x14001e9bd  mov     rcx, [rbp+var_10]
0x14001e9c1  xor     rcx, rsp; StackCookie
0x14001e9c4  call    __security_check_cookie
0x14001e9c9  lea     r11, [rsp+60h+var_s0]
0x14001e9ce  mov     rbx, [r11+10h]
0x14001e9d2  mov     rdi, [r11+20h]
0x14001e9d6  mov     rsp, r11
0x14001e9d9  pop     rbp
0x14001e9da  retn
```
