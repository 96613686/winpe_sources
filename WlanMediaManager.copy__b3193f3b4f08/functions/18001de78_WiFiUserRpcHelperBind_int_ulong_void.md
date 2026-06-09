# WiFiUserRpcHelperBind(int,ulong,void * *)

- ea: `0x18001de78`
- end: `0x18001df7f`
- name: `?WiFiUserRpcHelperBind@@YAKHKPEAPEAX@Z`
- size: `263`
- prototype: `unsigned int(int, unsigned int, void **)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001d7dc`
- `0x18001d860`
- `0x18001d9a8`
- `0x18001dcb8`
- `0x180073be8`

## callees

- `0x180003ed0`
- `0x18001de78`
- `0x18001df88`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x18001df28`
- `RPCRT4!RpcBindingCreateW` at `0x18001df28`
- `RPCRT4!RpcBindingBind` at `0x18001df40`
- `RPCRT4!RpcBindingBind` at `0x18001df40`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18001df56`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18001df56`

## pseudocode

```c
__int64 __fastcall WiFiUserRpcHelperBind(__int64 a1, __int64 a2, void **a3)
{
  unsigned int v4; // ebx
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+20h] [rbp-49h] BYREF
  __int64 v7; // [rsp+48h] [rbp-21h] BYREF
  int v8; // [rsp+50h] [rbp-19h]
  __int64 v9; // [rsp+54h] [rbp-15h]
  int v10; // [rsp+5Ch] [rbp-Dh]
  __int128 v11; // [rsp+60h] [rbp-9h]
  __int64 v12; // [rsp+70h] [rbp+7h]
  __int64 v13; // [rsp+78h] [rbp+Fh]
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+80h] [rbp+17h] BYREF

  *(_QWORD *)&Template.ProtocolSequence = 3;
  v10 = 0;
  v12 = 0;
  Security.ServerPrincName = 0;
  Security.AuthIdentity = 0;
  *(_QWORD *)&Template.Version = 1;
  v8 = 1;
  *(_QWORD *)&Security.Version = 1;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v7;
  memset(&Template.NetworkAddress, 0, 40);
  v7 = 5;
  v9 = 2;
  v11 = 0;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  v13 = 0;
  v4 = RpcBindingCreateW(&Template, &Security, 0, a3);
  if ( v4 || (v4 = RpcBindingBind(0, *a3, qword_180095740)) != 0 )
    WiFiUserRpcHelperUnbind(a3);
  FreeTransientObjectSecurityDescriptor(0);
  return v4;
}

```

## disassembly

```asm
0x18001de78  mov     [rsp-8+arg_0], rbx
0x18001de7d  mov     [rsp-8+arg_8], rdi
0x18001de82  push    rbp
0x18001de83  lea     rbp, [rsp-57h]
0x18001de88  sub     rsp, 0C0h
0x18001de8f  mov     rax, cs:__security_cookie
0x18001de96  xor     rax, rsp
0x18001de99  mov     [rbp+57h+var_8], rax
0x18001de9d  xor     eax, eax
0x18001de9f  mov     qword ptr [rbp+57h+Template.ProtocolSequence], 3
0x18001dea7  mov     ecx, 1
0x18001deac  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data2], rax
0x18001deb0  xorps   xmm0, xmm0
0x18001deb3  mov     dword ptr [rbp+57h+Template.ObjectUuid.Data4+4], eax
0x18001deb6  mov     [rbp+57h+var_64], eax
0x18001deb9  lea     rdx, [rbp+57h+Security]; Security
0x18001debd  mov     [rbp+57h+var_50], rax
0x18001dec1  mov     rdi, r8
0x18001dec4  mov     [rbp+57h+Security.ServerPrincName], rax
0x18001dec8  mov     r9, r8; Binding
0x18001decb  mov     [rbp+57h+Security.AuthIdentity], rax
0x18001decf  xor     r8d, r8d; Options
0x18001ded2  lea     rax, [rbp+57h+var_78]
0x18001ded6  mov     qword ptr [rbp+57h+Template.Version], rcx
0x18001deda  mov     [rbp+57h+var_70], ecx
0x18001dedd  mov     qword ptr [rbp+57h+Security.Version], rcx
0x18001dee1  lea     rcx, [rbp+57h+Template]; Template
0x18001dee5  mov     [rbp+57h+Security.SecurityQos], rax
0x18001dee9  movdqu  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x18001deee  mov     qword ptr [rbp+57h+Template.u1], 0
0x18001def6  mov     [rbp+57h+Template.ObjectUuid.Data1], 0
0x18001defd  mov     [rbp+57h+var_78], 5
0x18001df05  mov     [rbp+57h+var_6C], 2
0x18001df0d  movdqu  [rbp+57h+var_60], xmm0
0x18001df12  mov     [rbp+57h+Security.AuthnLevel], 6
0x18001df19  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x18001df20  mov     [rbp+57h+var_48], 0
0x18001df28  call    cs:__imp_RpcBindingCreateW
0x18001df2e  mov     ebx, eax
0x18001df30  test    eax, eax
0x18001df32  jnz     short loc_18001DF4C
0x18001df34  mov     rdx, [rdi]; Binding
0x18001df37  lea     r8, qword_180095740; IfSpec
0x18001df3e  xor     ecx, ecx; pAsync
0x18001df40  call    cs:__imp_RpcBindingBind
0x18001df46  mov     ebx, eax
0x18001df48  test    eax, eax
0x18001df4a  jz      short loc_18001DF54
0x18001df4c  mov     rcx, rdi; void **
0x18001df4f  call    ?WiFiUserRpcHelperUnbind@@YAKPEAPEAX@Z; WiFiUserRpcHelperUnbind(void * *)
0x18001df54  xor     ecx, ecx
0x18001df56  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18001df5c  mov     eax, ebx
0x18001df5e  mov     rcx, [rbp+57h+var_8]
0x18001df62  xor     rcx, rsp; StackCookie
0x18001df65  call    __security_check_cookie
0x18001df6a  lea     r11, [rsp+0C0h+var_s0]
0x18001df72  mov     rbx, [r11+10h]
0x18001df76  mov     rdi, [r11+18h]
0x18001df7a  mov     rsp, r11
0x18001df7d  pop     rbp
0x18001df7e  retn
```
