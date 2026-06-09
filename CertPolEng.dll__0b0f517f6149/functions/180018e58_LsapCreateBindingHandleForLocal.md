# LsapCreateBindingHandleForLocal

- ea: `0x180018e58`
- end: `0x180018f1a`
- name: `LsapCreateBindingHandleForLocal`
- size: `194`
- prototype: `int __fastcall(unsigned __int16 *, void *, _QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018c5c`
- `0x180018d08`
- `0x180018db0`

## callees

- `0x180018e58`
- `0x18001a380`

## import_xrefs

- `RPCRT4!RpcBindingBind` at `0x180018ed1`
- `RPCRT4!RpcBindingBind` at `0x180018ed1`
- `RPCRT4!RpcBindingCreateW` at `0x180018ebc`
- `RPCRT4!RpcBindingCreateW` at `0x180018ebc`
- `RPCRT4!I_RpcMapWin32Status` at `0x180018ef8`
- `RPCRT4!I_RpcMapWin32Status` at `0x180018ef8`
- `RPCRT4!RpcBindingFree` at `0x180018ee7`
- `RPCRT4!RpcBindingFree` at `0x180018ee7`

## pseudocode

```c
int __fastcall LsapCreateBindingHandleForLocal(unsigned __int16 *a1, void *a2, _QWORD *a3)
{
  RPC_STATUS v5; // ebx
  RPC_BINDING_HANDLE v6; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-50h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+28h] [rbp-48h] BYREF

  Binding = 0;
  memset(&Template, 0, 24);
  Template.StringEndpoint = a1;
  Template.Version = 1;
  Template.ProtocolSequence = 3;
  memset(&Template.u1, 0, 24);
  v5 = RpcBindingCreateW(&Template, (RPC_BINDING_HANDLE_SECURITY_V1_W *)&g_LsapBindingHandleSecurity, 0, &Binding);
  if ( v5 || (v5 = RpcBindingBind(0, Binding, a2)) != 0 )
  {
    RpcBindingFree(&Binding);
    v6 = 0;
    Binding = 0;
  }
  else
  {
    v6 = Binding;
  }
  *a3 = v6;
  return I_RpcMapWin32Status(v5);
}

```

## disassembly

```asm
0x180018e58  mov     [rsp-18h+arg_18], rbx
0x180018e5d  push    rbp
0x180018e5e  push    rsi
0x180018e5f  push    rdi
0x180018e60  mov     rbp, rsp
0x180018e63  sub     rsp, 70h
0x180018e67  mov     rax, cs:__security_cookie
0x180018e6e  xor     rax, rsp
0x180018e71  mov     [rbp+var_10], rax
0x180018e75  xorps   xmm0, xmm0
0x180018e78  mov     [rbp+Binding], 0
0x180018e80  movups  xmmword ptr [rbp+Template.Version], xmm0
0x180018e84  mov     rsi, r8
0x180018e87  mov     rdi, rdx
0x180018e8a  movups  xmmword ptr [rbp+Template.NetworkAddress], xmm0
0x180018e8e  mov     [rbp+Template.StringEndpoint], rcx
0x180018e92  lea     r9, [rbp+Binding]; Binding
0x180018e96  xor     eax, eax
0x180018e98  mov     [rbp+Template.Version], 1
0x180018e9f  lea     rcx, [rbp+Template]; Template
0x180018ea3  mov     qword ptr [rbp+Template.ObjectUuid.Data4], rax
0x180018ea7  xor     r8d, r8d; Options
0x180018eaa  mov     [rbp+Template.ProtocolSequence], 3
0x180018eb1  lea     rdx, g_LsapBindingHandleSecurity; Security
0x180018eb8  movups  xmmword ptr [rbp+Template.u1], xmm0
0x180018ebc  call    cs:__imp_RpcBindingCreateW
0x180018ec2  mov     ebx, eax
0x180018ec4  test    eax, eax
0x180018ec6  jnz     short loc_180018EE3
0x180018ec8  mov     rdx, [rbp+Binding]; Binding
0x180018ecc  mov     r8, rdi; IfSpec
0x180018ecf  xor     ecx, ecx; pAsync
0x180018ed1  call    cs:__imp_RpcBindingBind
0x180018ed7  mov     ebx, eax
0x180018ed9  test    eax, eax
0x180018edb  jnz     short loc_180018EE3
0x180018edd  mov     rax, [rbp+Binding]
0x180018ee1  jmp     short loc_180018EF3
0x180018ee3  lea     rcx, [rbp+Binding]; Binding
0x180018ee7  call    cs:__imp_RpcBindingFree
0x180018eed  xor     eax, eax
0x180018eef  mov     [rbp+Binding], rax
0x180018ef3  mov     ecx, ebx; Status
0x180018ef5  mov     [rsi], rax
0x180018ef8  call    cs:__imp_I_RpcMapWin32Status
0x180018efe  mov     rcx, [rbp+var_10]
0x180018f02  xor     rcx, rsp; StackCookie
0x180018f05  call    __security_check_cookie
0x180018f0a  mov     rbx, [rsp+70h+arg_18]
0x180018f12  add     rsp, 70h
0x180018f16  pop     rdi
0x180018f17  pop     rsi
0x180018f18  pop     rbp
0x180018f19  retn
```
