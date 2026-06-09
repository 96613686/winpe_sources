# WcmKOpenHandle(void * *)

- ea: `0x140009ff8`
- end: `0x14000a16a`
- name: `?WcmKOpenHandle@@YAJPEAPEAX@Z`
- size: `370`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140005034`
- `0x140006cc4`
- `0x140006e28`

## callees

- `0x140009ef8`
- `0x140009ff8`
- `0x14000a680`

## import_xrefs

- `ntoskrnl!SeExports` at `0x14000a06c`
- `msrpc!RpcBindingFree` at `0x14000a112`
- `msrpc!RpcBindingFree` at `0x14000a112`
- `msrpc!RpcBindingCreateW` at `0x14000a0d0`
- `msrpc!RpcBindingCreateW` at `0x14000a0d0`
- `msrpc!RpcBindingSetOption` at `0x14000a0f5`
- `msrpc!RpcBindingSetOption` at `0x14000a0f5`
- `msrpc!RpcBindingBind` at `0x14000a12f`
- `msrpc!RpcBindingBind` at `0x14000a12f`

## pseudocode

```c
__int64 __fastcall WcmKOpenHandle(void **a1)
{
  RPC_STATUS v3; // eax
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-49h] BYREF
  _DWORD v7[4]; // [rsp+28h] [rbp-41h] BYREF
  __int128 v8; // [rsp+38h] [rbp-31h]
  PSID SeLocalServiceSid; // [rsp+48h] [rbp-21h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+50h] [rbp-19h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+78h] [rbp+Fh] BYREF

  if ( !a1 )
    return 3221225485LL;
  *a1 = 0;
  memset(&Template, 0, sizeof(Template));
  SeLocalServiceSid = 0;
  v7[3] = 2;
  Template.Version = 1;
  Template.ProtocolSequence = 3;
  v7[0] = 3;
  v7[1] = 1;
  v8 = 0;
  v7[2] = 1;
  SeLocalServiceSid = SeExports->SeLocalServiceSid;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v7;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Binding = 0;
  v3 = RpcBindingCreateW(&Template, &Security, 0, &Binding);
  if ( v3 )
    return RpcStatusToNtStatus(v3);
  v4 = RpcBindingSetOption(Binding, 9u, 1u);
  if ( v4 || (v4 = RpcBindingBind(0, Binding, qword_14000C590)) != 0 )
  {
    v5 = RpcStatusToNtStatus(v4);
    RpcBindingFree(&Binding);
    return v5;
  }
  else
  {
    *a1 = Binding;
    return 0;
  }
}

```

## disassembly

```asm
0x140009ff8  mov     [rsp-8+arg_8], rbx
0x140009ffd  mov     [rsp-8+arg_10], rsi
0x14000a002  push    rbp
0x14000a003  lea     rbp, [rsp-57h]
0x14000a008  sub     rsp, 0C0h
0x14000a00f  mov     rax, cs:__security_cookie
0x14000a016  xor     rax, rsp
0x14000a019  mov     [rbp+57h+var_10], rax
0x14000a01d  mov     rbx, rcx
0x14000a020  test    rcx, rcx
0x14000a023  jnz     short loc_14000A02F
0x14000a025  mov     eax, 0C000000Dh
0x14000a02a  jmp     loc_14000A148
0x14000a02f  xor     eax, eax
0x14000a031  mov     qword ptr [rcx], 0
0x14000a038  xorps   xmm0, xmm0
0x14000a03b  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x14000a03f  movups  xmmword ptr [rbp+57h+Template.Version], xmm0
0x14000a043  mov     [rbp+57h+var_78], 0
0x14000a04b  lea     r9, [rbp+57h+Binding]; Binding
0x14000a04f  lea     esi, [rax+1]
0x14000a052  mov     [rbp+57h+var_8C], 2
0x14000a059  lea     eax, [rsi+2]
0x14000a05c  mov     [rbp+57h+Template.Version], esi
0x14000a05f  mov     [rbp+57h+Template.ProtocolSequence], eax
0x14000a062  lea     rdx, [rbp+57h+Security]; Security
0x14000a066  mov     [rbp+57h+var_98], eax
0x14000a069  xor     r8d, r8d; Options
0x14000a06c  mov     rax, cs:__imp_SeExports
0x14000a073  movups  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x14000a077  mov     [rbp+57h+var_94], esi
0x14000a07a  movups  xmmword ptr [rbp+57h+Template.u1], xmm0
0x14000a07e  mov     rcx, [rax]
0x14000a081  movdqu  [rbp+57h+var_88], xmm0
0x14000a086  mov     [rbp+57h+var_90], esi
0x14000a089  mov     rax, [rcx+180h]
0x14000a090  lea     rcx, [rbp+57h+Template]; Template
0x14000a094  mov     [rbp+57h+var_78], rax
0x14000a098  lea     rax, [rbp+57h+var_98]
0x14000a09c  mov     [rbp+57h+Security.SecurityQos], rax
0x14000a0a0  mov     qword ptr [rbp+57h+Security+4], 0
0x14000a0a8  mov     dword ptr [rbp+57h+Security.ServerPrincName+4], 0
0x14000a0af  mov     [rbp+57h+Security.AuthIdentity], 0
0x14000a0b7  mov     [rbp+57h+Security.Version], esi
0x14000a0ba  mov     [rbp+57h+Security.AuthnLevel], 6
0x14000a0c1  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x14000a0c8  mov     [rbp+57h+Binding], 0
0x14000a0d0  call    cs:__imp_RpcBindingCreateW
0x14000a0d7  nop     dword ptr [rax+rax+00h]
0x14000a0dc  test    eax, eax
0x14000a0de  jz      short loc_14000A0E9
0x14000a0e0  mov     ecx, eax; int
0x14000a0e2  call    ?RpcStatusToNtStatus@@YAJJ@Z; RpcStatusToNtStatus(long)
0x14000a0e7  jmp     short loc_14000A148
0x14000a0e9  mov     rcx, [rbp+57h+Binding]; hBinding
0x14000a0ed  mov     r8, rsi; optionValue
0x14000a0f0  mov     edx, 9; option
0x14000a0f5  call    cs:__imp_RpcBindingSetOption
0x14000a0fc  nop     dword ptr [rax+rax+00h]
0x14000a101  test    eax, eax
0x14000a103  jz      short loc_14000A122
0x14000a105  mov     ecx, eax; int
0x14000a107  call    ?RpcStatusToNtStatus@@YAJJ@Z; RpcStatusToNtStatus(long)
0x14000a10c  lea     rcx, [rbp+57h+Binding]; Binding
0x14000a110  mov     ebx, eax
0x14000a112  call    cs:__imp_RpcBindingFree
0x14000a119  nop     dword ptr [rax+rax+00h]
0x14000a11e  mov     eax, ebx
0x14000a120  jmp     short loc_14000A148
0x14000a122  mov     rdx, [rbp+57h+Binding]; Binding
0x14000a126  lea     r8, qword_14000C590; IfSpec
0x14000a12d  xor     ecx, ecx; pAsync
0x14000a12f  call    cs:__imp_RpcBindingBind
0x14000a136  nop     dword ptr [rax+rax+00h]
0x14000a13b  test    eax, eax
0x14000a13d  jnz     short loc_14000A105
0x14000a13f  mov     rax, [rbp+57h+Binding]
0x14000a143  mov     [rbx], rax
0x14000a146  xor     eax, eax
0x14000a148  mov     rcx, [rbp+57h+var_10]
0x14000a14c  xor     rcx, rsp; StackCookie
0x14000a14f  call    __security_check_cookie
0x14000a154  lea     r11, [rsp+0C0h+var_s0]
0x14000a15c  mov     rbx, [r11+18h]
0x14000a160  mov     rsi, [r11+20h]
0x14000a164  mov     rsp, r11
0x14000a167  pop     rbp
0x14000a168  retn
```
