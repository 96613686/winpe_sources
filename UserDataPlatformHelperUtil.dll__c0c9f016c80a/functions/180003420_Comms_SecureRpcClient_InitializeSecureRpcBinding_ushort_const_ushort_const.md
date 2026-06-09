# Comms::SecureRpcClient::_InitializeSecureRpcBinding(ushort const *,ushort const *)

- ea: `0x180003420`
- end: `0x1800035f2`
- name: `?_InitializeSecureRpcBinding@SecureRpcClient@Comms@@IEAAJPEBG0@Z`
- size: `466`
- prototype: `__int64 __fastcall(Comms::SecureRpcClient *this, unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003420`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800034a5`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800034a5`
- `RPCRT4!RpcStringBindingComposeW` at `0x180003460`
- `RPCRT4!RpcStringBindingComposeW` at `0x180003460`
- `RPCRT4!RpcStringFreeW` at `0x180003488`
- `RPCRT4!RpcStringFreeW` at `0x1800035de`
- `RPCRT4!RpcStringFreeW` at `0x180003488`
- `RPCRT4!RpcStringFreeW` at `0x1800035de`
- `RPCRT4!RpcBindingFree` at `0x1800034cd`
- `RPCRT4!RpcBindingFree` at `0x180003599`
- `RPCRT4!RpcBindingFree` at `0x1800035c7`
- `RPCRT4!RpcBindingFree` at `0x1800034cd`
- `RPCRT4!RpcBindingFree` at `0x180003599`
- `RPCRT4!RpcBindingFree` at `0x1800035c7`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180003560`
- `RPCRT4!RpcBindingSetAuthInfoExW` at `0x180003560`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x1800034e9`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x1800034e9`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180003502`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800035b0`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180003502`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800035b0`

## pseudocode

```c
__int64 __fastcall Comms::SecureRpcClient::_InitializeSecureRpcBinding(
        Comms::SecureRpcClient *this,
        unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  RPC_STATUS v5; // eax
  unsigned int v6; // ebx
  RPC_STATUS v8; // eax
  int v9; // ebx
  RPC_STATUS v10; // eax
  unsigned __int16 *v11; // rbx
  unsigned __int16 *v12; // rax
  unsigned __int16 *v13; // rcx
  RPC_WSTR StringBinding; // [rsp+40h] [rbp-19h] BYREF
  __int64 v15; // [rsp+48h] [rbp-11h] BYREF
  RPC_WSTR String; // [rsp+50h] [rbp-9h] BYREF
  RPC_SECURITY_QOS SecurityQOS; // [rsp+58h] [rbp-1h] BYREF
  __int128 v18; // [rsp+68h] [rbp+Fh]
  __int128 v19; // [rsp+78h] [rbp+1Fh]
  __int64 v20; // [rsp+88h] [rbp+2Fh]
  RPC_BINDING_HANDLE Binding; // [rsp+D8h] [rbp+7Fh] BYREF

  StringBinding = 0;
  v5 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, a2, 0, &StringBinding);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 > 0 )
      v6 = (unsigned __int16)v5 | 0x80070000;
LABEL_4:
    if ( StringBinding )
    {
      String = StringBinding;
      RpcStringFreeW(&String);
    }
    return v6;
  }
  Binding = 0;
  v8 = RpcBindingFromStringBindingW(StringBinding, &Binding);
  v6 = v8;
  if ( v8 )
  {
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
LABEL_10:
    if ( Binding )
    {
      String = (RPC_WSTR)Binding;
      RpcBindingFree((RPC_BINDING_HANDLE *)&String);
    }
    goto LABEL_4;
  }
  v15 = 0;
  v9 = QueryTransientObjectSecurityDescriptor(9, a3, &v15);
  if ( v9 < 0 )
  {
    v6 = v9 | 0x10000000;
LABEL_14:
    if ( v15 )
      FreeTransientObjectSecurityDescriptor();
    goto LABEL_10;
  }
  v20 = v15;
  *(_QWORD *)&SecurityQOS.Version = 5;
  v18 = 0;
  SecurityQOS.IdentityTracking = 0;
  v19 = 0;
  SecurityQOS.ImpersonationType = 2;
  v10 = RpcBindingSetAuthInfoExW(Binding, 0, 6u, 0xAu, 0, 0, &SecurityQOS);
  v6 = v10;
  if ( v10 )
  {
    if ( v10 > 0 )
      v6 = (unsigned __int16)v10 | 0x80070000;
    goto LABEL_14;
  }
  v11 = (unsigned __int16 *)Binding;
  v12 = 0;
  v13 = (unsigned __int16 *)*((_QWORD *)this + 1);
  Binding = 0;
  if ( v11 != v13 )
  {
    if ( v13 )
    {
      String = v13;
      RpcBindingFree((RPC_BINDING_HANDLE *)&String);
      v12 = (unsigned __int16 *)Binding;
    }
    *((_QWORD *)this + 1) = v11;
  }
  if ( v15 )
  {
    FreeTransientObjectSecurityDescriptor();
    v12 = (unsigned __int16 *)Binding;
  }
  if ( v12 )
  {
    String = v12;
    RpcBindingFree((RPC_BINDING_HANDLE *)&String);
  }
  if ( StringBinding )
  {
    String = StringBinding;
    RpcStringFreeW(&String);
  }
  return 0;
}

```

## disassembly

```asm
0x180003420  push    rbp
0x180003422  push    rbx
0x180003423  push    rsi
0x180003424  push    rdi
0x180003425  lea     rbp, [rsp-3Fh]
0x18000342a  sub     rsp, 98h
0x180003431  lea     rax, [rbp+57h+var_70]
0x180003435  mov     [rbp+57h+var_70], 0
0x18000343d  mov     rsi, r8
0x180003440  mov     [rsp+0B0h+StringBinding], rax; StringBinding
0x180003445  mov     rdi, rcx
0x180003448  mov     [rsp+0B0h+Options], 0; Options
0x180003451  mov     r9, rdx; Endpoint
0x180003454  xor     r8d, r8d; NetworkAddr
0x180003457  lea     rdx, ProtSeq; "ncalrpc"
0x18000345e  xor     ecx, ecx; ObjUuid
0x180003460  call    cs:__imp_RpcStringBindingComposeW
0x180003466  mov     ebx, eax
0x180003468  test    eax, eax
0x18000346a  jz      short loc_180003495
0x18000346c  jle     short loc_180003477
0x18000346e  movzx   ebx, ax
0x180003471  or      ebx, 80070000h
0x180003477  mov     rcx, [rbp+57h+var_70]
0x18000347b  test    rcx, rcx
0x18000347e  jz      short loc_18000348E
0x180003480  mov     [rbp+57h+String], rcx
0x180003484  lea     rcx, [rbp+57h+String]; String
0x180003488  call    cs:__imp_RpcStringFreeW
0x18000348e  mov     eax, ebx
0x180003490  jmp     loc_1800035E6
0x180003495  mov     rcx, [rbp+57h+var_70]; StringBinding
0x180003499  lea     rdx, [rbp+57h+Binding]; Binding
0x18000349d  mov     [rbp+57h+Binding], 0
0x1800034a5  call    cs:__imp_RpcBindingFromStringBindingW
0x1800034ab  mov     ebx, eax
0x1800034ad  test    eax, eax
0x1800034af  jz      short loc_1800034D5
0x1800034b1  jle     short loc_1800034BC
0x1800034b3  movzx   ebx, ax
0x1800034b6  or      ebx, 80070000h
0x1800034bc  mov     rcx, [rbp+57h+Binding]
0x1800034c0  test    rcx, rcx
0x1800034c3  jz      short loc_180003477
0x1800034c5  mov     [rbp+57h+String], rcx
0x1800034c9  lea     rcx, [rbp+57h+String]; Binding
0x1800034cd  call    cs:__imp_RpcBindingFree
0x1800034d3  jmp     short loc_180003477
0x1800034d5  lea     r8, [rbp+57h+var_68]
0x1800034d9  mov     [rbp+57h+var_68], 0
0x1800034e1  mov     rdx, rsi
0x1800034e4  mov     ecx, 9
0x1800034e9  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x1800034ef  mov     ebx, eax
0x1800034f1  test    eax, eax
0x1800034f3  jns     short loc_18000350A
0x1800034f5  bts     ebx, 1Ch
0x1800034f9  mov     rcx, [rbp+57h+var_68]
0x1800034fd  test    rcx, rcx
0x180003500  jz      short loc_1800034BC
0x180003502  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180003508  jmp     short loc_1800034BC
0x18000350a  mov     rax, [rbp+57h+var_68]
0x18000350e  xor     edx, edx; ServerPrincName
0x180003510  mov     rcx, [rbp+57h+Binding]; Binding
0x180003514  xorps   xmm0, xmm0
0x180003517  mov     [rbp+57h+var_28], rax
0x18000351b  xorps   xmm1, xmm1
0x18000351e  lea     rax, [rbp+57h+var_58]
0x180003522  mov     qword ptr [rbp+57h+var_58.Version], 5
0x18000352a  mov     [rsp+0B0h+SecurityQOS], rax; SecurityQOS
0x18000352f  lea     r9d, [rdx+0Ah]; AuthnSvc
0x180003533  mov     dword ptr [rsp+0B0h+StringBinding], 0; AuthzSvc
0x18000353b  lea     r8d, [rdx+6]; AuthnLevel
0x18000353f  mov     [rsp+0B0h+Options], 0; AuthIdentity
0x180003548  movdqu  [rbp+57h+var_48], xmm0
0x18000354d  mov     [rbp+57h+var_58.IdentityTracking], 0
0x180003554  movdqu  [rbp+57h+var_38], xmm1
0x180003559  mov     [rbp+57h+var_58.ImpersonationType], 2
0x180003560  call    cs:__imp_RpcBindingSetAuthInfoExW
0x180003566  mov     ebx, eax
0x180003568  test    eax, eax
0x18000356a  jz      short loc_180003579
0x18000356c  jle     short loc_1800034F9
0x18000356e  movzx   ebx, ax
0x180003571  or      ebx, 80070000h
0x180003577  jmp     short loc_1800034F9
0x180003579  mov     rbx, [rbp+57h+Binding]
0x18000357d  xor     eax, eax
0x18000357f  mov     rcx, [rdi+8]
0x180003583  mov     [rbp+57h+Binding], rax
0x180003587  cmp     rbx, rcx
0x18000358a  jz      short loc_1800035A7
0x18000358c  test    rcx, rcx
0x18000358f  jz      short loc_1800035A3
0x180003591  mov     [rbp+57h+String], rcx
0x180003595  lea     rcx, [rbp+57h+String]; Binding
0x180003599  call    cs:__imp_RpcBindingFree
0x18000359f  mov     rax, [rbp+57h+Binding]
0x1800035a3  mov     [rdi+8], rbx
0x1800035a7  mov     rcx, [rbp+57h+var_68]
0x1800035ab  test    rcx, rcx
0x1800035ae  jz      short loc_1800035BA
0x1800035b0  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800035b6  mov     rax, [rbp+57h+Binding]
0x1800035ba  test    rax, rax
0x1800035bd  jz      short loc_1800035CD
0x1800035bf  lea     rcx, [rbp+57h+String]; Binding
0x1800035c3  mov     [rbp+57h+String], rax
0x1800035c7  call    cs:__imp_RpcBindingFree
0x1800035cd  mov     rax, [rbp+57h+var_70]
0x1800035d1  test    rax, rax
0x1800035d4  jz      short loc_1800035E4
0x1800035d6  lea     rcx, [rbp+57h+String]; String
0x1800035da  mov     [rbp+57h+String], rax
0x1800035de  call    cs:__imp_RpcStringFreeW
0x1800035e4  xor     eax, eax
0x1800035e6  add     rsp, 98h
0x1800035ed  pop     rdi
0x1800035ee  pop     rsi
0x1800035ef  pop     rbx
0x1800035f0  pop     rbp
0x1800035f1  retn
```
