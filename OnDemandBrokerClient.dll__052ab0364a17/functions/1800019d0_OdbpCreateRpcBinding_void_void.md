# OdbpCreateRpcBinding(void *,void * *)

- ea: `0x1800019d0`
- end: `0x180001b19`
- name: `?OdbpCreateRpcBinding@@YAJPEAXPEAPEAX@Z`
- size: `329`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE IfSpec, void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004db0`

## callees

- `0x1800019d0`
- `0x180006570`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x180001af7`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001af7`
- `RPCRT4!RpcBindingFree` at `0x180001b11`
- `RPCRT4!RpcBindingFree` at `0x180001b11`
- `RPCRT4!RpcBindingCreateW` at `0x180001ab0`
- `RPCRT4!RpcBindingCreateW` at `0x180001ab0`
- `RPCRT4!RpcBindingBind` at `0x180001ac3`
- `RPCRT4!RpcBindingBind` at `0x180001ac3`

## pseudocode

```c
__int64 __fastcall OdbpCreateRpcBinding(RPC_IF_HANDLE IfSpec, void **a2)
{
  RPC_STATUS v4; // eax
  __int64 result; // rax
  unsigned int v6; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-79h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+28h] [rbp-71h] BYREF
  _DWORD v9[4]; // [rsp+50h] [rbp-49h] BYREF
  __int128 v10; // [rsp+60h] [rbp-39h]
  _DWORD *v11; // [rsp+70h] [rbp-29h]
  _DWORD v12[4]; // [rsp+78h] [rbp-21h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+88h] [rbp-11h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+98h] [rbp-1h] BYREF

  *(_QWORD *)&Options.ComTimeout = 5;
  v12[0] = 257;
  memset(&Template, 0, sizeof(Template));
  *(_QWORD *)(&Security.Version + 1) = 0;
  v11 = v12;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v9;
  Security.AuthIdentity = 0;
  v12[1] = 83886080;
  v12[2] = 18;
  Binding = 0;
  Template.Version = 1;
  v10 = 0;
  Template.ProtocolSequence = 3;
  Options.Version = 1;
  Options.Flags = 1;
  v9[0] = 3;
  v9[1] = 1;
  v9[2] = 1;
  v9[3] = 3;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  v4 = RpcBindingCreateW(&Template, &Security, &Options, &Binding);
  if ( v4 || (v4 = RpcBindingBind(0, Binding, IfSpec)) != 0 )
  {
    v6 = I_RpcMapWin32Status(v4) | 0x10000000;
    if ( Binding )
      RpcBindingFree(&Binding);
    return v6;
  }
  else
  {
    result = 0;
    *a2 = Binding;
  }
  return result;
}

```

## disassembly

```asm
0x1800019d0  mov     [rsp-8+arg_10], rbx
0x1800019d5  push    rbp
0x1800019d6  push    rsi
0x1800019d7  push    rdi
0x1800019d8  lea     rbp, [rsp-47h]
0x1800019dd  sub     rsp, 0E0h
0x1800019e4  mov     rax, cs:__security_cookie
0x1800019eb  xor     rax, rsp
0x1800019ee  mov     [rbp+57h+var_20], rax
0x1800019f2  xor     eax, eax
0x1800019f4  mov     qword ptr [rbp+57h+Options.ComTimeout], 5
0x1800019fc  xorps   xmm1, xmm1
0x1800019ff  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x180001a03  xor     esi, esi
0x180001a05  mov     [rbp+57h+var_78], 101h
0x180001a0c  movups  xmmword ptr [rbp+57h+Template.Version], xmm1
0x180001a10  lea     rax, [rbp+57h+var_78]
0x180001a14  mov     qword ptr [rbp+57h+Security+4], rsi
0x180001a18  mov     [rbp+57h+var_80], rax
0x180001a1c  lea     r9, [rbp+57h+Binding]; Binding
0x180001a20  lea     rax, [rbp+57h+var_A0]
0x180001a24  mov     dword ptr [rbp+57h+Security.ServerPrincName+4], esi
0x180001a27  mov     rbx, rdx
0x180001a2a  mov     [rbp+57h+Security.SecurityQos], rax
0x180001a2e  mov     rdi, rcx
0x180001a31  mov     [rbp+57h+Security.AuthIdentity], rsi
0x180001a35  xorps   xmm0, xmm0
0x180001a38  mov     [rbp+57h+var_74], 5000000h
0x180001a3f  lea     r8, [rbp+57h+Options]; Options
0x180001a43  mov     [rbp+57h+var_70], 12h
0x180001a4a  lea     rdx, [rbp+57h+Security]; Security
0x180001a4e  mov     [rbp+57h+Binding], rsi
0x180001a52  lea     rcx, [rbp+57h+Template]; Template
0x180001a56  mov     [rbp+57h+Template.Version], 1
0x180001a5d  movdqu  [rbp+57h+var_90], xmm0
0x180001a62  mov     [rbp+57h+Template.ProtocolSequence], 3
0x180001a69  movups  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm1
0x180001a6d  mov     [rbp+57h+Options.Version], 1
0x180001a74  movups  xmmword ptr [rbp+57h+Template.u1], xmm1
0x180001a78  mov     [rbp+57h+Options.Flags], 1
0x180001a7f  mov     [rbp+57h+var_A0], 3
0x180001a86  mov     [rbp+57h+var_9C], 1
0x180001a8d  mov     [rbp+57h+var_98], 1
0x180001a94  mov     [rbp+57h+var_94], 3
0x180001a9b  mov     [rbp+57h+Security.Version], 1
0x180001aa2  mov     [rbp+57h+Security.AuthnLevel], 6
0x180001aa9  mov     [rbp+57h+Security.AuthnSvc], 14h
0x180001ab0  call    cs:__imp_RpcBindingCreateW
0x180001ab6  test    eax, eax
0x180001ab8  jnz     short loc_180001AF5
0x180001aba  mov     rdx, [rbp+57h+Binding]; Binding
0x180001abe  mov     r8, rdi; IfSpec
0x180001ac1  xor     ecx, ecx; pAsync
0x180001ac3  call    cs:__imp_RpcBindingBind
0x180001ac9  test    eax, eax
0x180001acb  jnz     short loc_180001AF5
0x180001acd  mov     rcx, [rbp+57h+Binding]
0x180001ad1  mov     eax, esi
0x180001ad3  mov     [rbx], rcx
0x180001ad6  mov     rcx, [rbp+57h+var_20]
0x180001ada  xor     rcx, rsp; StackCookie
0x180001add  call    __security_check_cookie
0x180001ae2  mov     rbx, [rsp+0F0h+arg_10]
0x180001aea  add     rsp, 0E0h
0x180001af1  pop     rdi
0x180001af2  pop     rsi
0x180001af3  pop     rbp
0x180001af4  retn
0x180001af5  mov     ecx, eax; Status
0x180001af7  call    cs:__imp_I_RpcMapWin32Status
0x180001afd  mov     ebx, eax
0x180001aff  bts     ebx, 1Ch
0x180001b03  cmp     [rbp+57h+Binding], rsi
0x180001b07  jnz     short loc_180001B0D
0x180001b09  mov     eax, ebx
0x180001b0b  jmp     short loc_180001AD6
0x180001b0d  lea     rcx, [rbp+57h+Binding]; Binding
0x180001b11  call    cs:__imp_RpcBindingFree
0x180001b17  jmp     short loc_180001B09
```
