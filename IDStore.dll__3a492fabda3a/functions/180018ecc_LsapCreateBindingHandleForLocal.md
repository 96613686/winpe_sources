# LsapCreateBindingHandleForLocal

- ea: `0x180018ecc`
- end: `0x180018f8e`
- name: `LsapCreateBindingHandleForLocal`
- size: `194`
- prototype: `int __fastcall(unsigned __int16 *, void *, _QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180018b9c`
- `0x180018ca0`
- `0x180018dc8`

## callees

- `0x180018ecc`
- `0x180019750`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180018f5b`
- `RPCRT4!RpcBindingFree` at `0x180018f5b`
- `RPCRT4!I_RpcMapWin32Status` at `0x180018f6c`
- `RPCRT4!I_RpcMapWin32Status` at `0x180018f6c`
- `RPCRT4!RpcBindingBind` at `0x180018f45`
- `RPCRT4!RpcBindingBind` at `0x180018f45`
- `RPCRT4!RpcBindingCreateW` at `0x180018f30`
- `RPCRT4!RpcBindingCreateW` at `0x180018f30`

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
0x180018ecc  mov     [rsp-18h+arg_18], rbx
0x180018ed1  push    rbp
0x180018ed2  push    rsi
0x180018ed3  push    rdi
0x180018ed4  mov     rbp, rsp
0x180018ed7  sub     rsp, 70h
0x180018edb  mov     rax, cs:__security_cookie
0x180018ee2  xor     rax, rsp
0x180018ee5  mov     [rbp+var_10], rax
0x180018ee9  xorps   xmm0, xmm0
0x180018eec  mov     [rbp+Binding], 0
0x180018ef4  movups  xmmword ptr [rbp+Template.Version], xmm0
0x180018ef8  mov     rsi, r8
0x180018efb  mov     rdi, rdx
0x180018efe  movups  xmmword ptr [rbp+Template.NetworkAddress], xmm0
0x180018f02  mov     [rbp+Template.StringEndpoint], rcx
0x180018f06  lea     r9, [rbp+Binding]; Binding
0x180018f0a  xor     eax, eax
0x180018f0c  mov     [rbp+Template.Version], 1
0x180018f13  lea     rcx, [rbp+Template]; Template
0x180018f17  mov     qword ptr [rbp+Template.ObjectUuid.Data4], rax
0x180018f1b  xor     r8d, r8d; Options
0x180018f1e  mov     [rbp+Template.ProtocolSequence], 3
0x180018f25  lea     rdx, g_LsapBindingHandleSecurity; Security
0x180018f2c  movups  xmmword ptr [rbp+Template.u1], xmm0
0x180018f30  call    cs:__imp_RpcBindingCreateW
0x180018f36  mov     ebx, eax
0x180018f38  test    eax, eax
0x180018f3a  jnz     short loc_180018F57
0x180018f3c  mov     rdx, [rbp+Binding]; Binding
0x180018f40  mov     r8, rdi; IfSpec
0x180018f43  xor     ecx, ecx; pAsync
0x180018f45  call    cs:__imp_RpcBindingBind
0x180018f4b  mov     ebx, eax
0x180018f4d  test    eax, eax
0x180018f4f  jnz     short loc_180018F57
0x180018f51  mov     rax, [rbp+Binding]
0x180018f55  jmp     short loc_180018F67
0x180018f57  lea     rcx, [rbp+Binding]; Binding
0x180018f5b  call    cs:__imp_RpcBindingFree
0x180018f61  xor     eax, eax
0x180018f63  mov     [rbp+Binding], rax
0x180018f67  mov     ecx, ebx; Status
0x180018f69  mov     [rsi], rax
0x180018f6c  call    cs:__imp_I_RpcMapWin32Status
0x180018f72  mov     rcx, [rbp+var_10]
0x180018f76  xor     rcx, rsp; StackCookie
0x180018f79  call    __security_check_cookie
0x180018f7e  mov     rbx, [rsp+70h+arg_18]
0x180018f86  add     rsp, 70h
0x180018f8a  pop     rdi
0x180018f8b  pop     rsi
0x180018f8c  pop     rbp
0x180018f8d  retn
```
