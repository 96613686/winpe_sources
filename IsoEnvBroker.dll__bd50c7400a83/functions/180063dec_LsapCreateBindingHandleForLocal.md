# LsapCreateBindingHandleForLocal

- ea: `0x180063dec`
- end: `0x180063eb4`
- name: `LsapCreateBindingHandleForLocal`
- size: `200`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18006369c`
- `0x18006374c`
- `0x1800637fc`
- `0x18006389c`
- `0x180063ec0`
- `0x180063f20`
- `0x180063f60`

## callees

- `0x180002520`
- `0x180063dec`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180063e7f`
- `RPCRT4!RpcBindingFree` at `0x180063e7f`
- `RPCRT4!RpcBindingBind` at `0x180063e69`
- `RPCRT4!RpcBindingBind` at `0x180063e69`
- `RPCRT4!I_RpcMapWin32Status` at `0x180063e90`
- `RPCRT4!I_RpcMapWin32Status` at `0x180063e90`
- `RPCRT4!RpcBindingCreateW` at `0x180063e50`
- `RPCRT4!RpcBindingCreateW` at `0x180063e50`

## pseudocode

```c
int __fastcall LsapCreateBindingHandleForLocal(unsigned __int16 *a1, __int64 a2, _QWORD *a3)
{
  RPC_STATUS v4; // ebx
  RPC_BINDING_HANDLE v5; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-50h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+28h] [rbp-48h] BYREF

  Binding = 0;
  memset(&Template, 0, 24);
  Template.StringEndpoint = a1;
  Template.Version = 1;
  Template.ProtocolSequence = 3;
  memset(&Template.u1, 0, 24);
  v4 = RpcBindingCreateW(&Template, (RPC_BINDING_HANDLE_SECURITY_V1_W *)&g_LsapBindingHandleSecurity, 0, &Binding);
  if ( v4 || (v4 = RpcBindingBind(0, Binding, qword_18006FBE0)) != 0 )
  {
    RpcBindingFree(&Binding);
    v5 = 0;
    Binding = 0;
  }
  else
  {
    v5 = Binding;
  }
  *a3 = v5;
  return I_RpcMapWin32Status(v4);
}

```

## disassembly

```asm
0x180063dec  mov     [rsp-8+arg_8], rbx
0x180063df1  mov     [rsp-8+arg_18], rdi
0x180063df6  push    rbp
0x180063df7  mov     rbp, rsp
0x180063dfa  sub     rsp, 70h
0x180063dfe  mov     rax, cs:__security_cookie
0x180063e05  xor     rax, rsp
0x180063e08  mov     [rbp+var_10], rax
0x180063e0c  xorps   xmm0, xmm0
0x180063e0f  mov     [rbp+Binding], 0
0x180063e17  movups  xmmword ptr [rbp+Template.Version], xmm0
0x180063e1b  mov     rdi, r8
0x180063e1e  xor     eax, eax
0x180063e20  movups  xmmword ptr [rbp+Template.NetworkAddress], xmm0
0x180063e24  mov     [rbp+Template.StringEndpoint], rcx
0x180063e28  lea     r9, [rbp+Binding]; Binding
0x180063e2c  lea     rcx, [rbp+Template]; Template
0x180063e30  mov     qword ptr [rbp+Template.ObjectUuid.Data4], rax
0x180063e34  xor     r8d, r8d; Options
0x180063e37  mov     [rbp+Template.Version], 1
0x180063e3e  lea     rdx, g_LsapBindingHandleSecurity; Security
0x180063e45  mov     [rbp+Template.ProtocolSequence], 3
0x180063e4c  movups  xmmword ptr [rbp+Template.u1], xmm0
0x180063e50  call    cs:__imp_RpcBindingCreateW
0x180063e56  mov     ebx, eax
0x180063e58  test    eax, eax
0x180063e5a  jnz     short loc_180063E7B
0x180063e5c  mov     rdx, [rbp+Binding]; Binding
0x180063e60  lea     r8, qword_18006FBE0; IfSpec
0x180063e67  xor     ecx, ecx; pAsync
0x180063e69  call    cs:__imp_RpcBindingBind
0x180063e6f  mov     ebx, eax
0x180063e71  test    eax, eax
0x180063e73  jnz     short loc_180063E7B
0x180063e75  mov     rax, [rbp+Binding]
0x180063e79  jmp     short loc_180063E8B
0x180063e7b  lea     rcx, [rbp+Binding]; Binding
0x180063e7f  call    cs:__imp_RpcBindingFree
0x180063e85  xor     eax, eax
0x180063e87  mov     [rbp+Binding], rax
0x180063e8b  mov     ecx, ebx; Status
0x180063e8d  mov     [rdi], rax
0x180063e90  call    cs:__imp_I_RpcMapWin32Status
0x180063e96  mov     rcx, [rbp+var_10]
0x180063e9a  xor     rcx, rsp; StackCookie
0x180063e9d  call    __security_check_cookie
0x180063ea2  lea     r11, [rsp+70h+var_s0]
0x180063ea7  mov     rbx, [r11+18h]
0x180063eab  mov     rdi, [r11+28h]
0x180063eaf  mov     rsp, r11
0x180063eb2  pop     rbp
0x180063eb3  retn
```
