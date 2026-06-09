# KnrNrpCreateBinding

- ea: `0x1400315b8`
- end: `0x140031717`
- name: `KnrNrpCreateBinding`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400314f0`

## callees

- `0x1400315b8`
- `0x14003fabc`
- `0x140072840`

## import_xrefs

- `ntoskrnl!SeExports` at `0x140031615`
- `msrpc!RpcBindingSetOption` at `0x1400316b3`
- `msrpc!RpcBindingSetOption` at `0x1400316b3`
- `msrpc!RpcBindingCreateW` at `0x140031697`
- `msrpc!RpcBindingCreateW` at `0x140031697`
- `msrpc!RpcBindingFree` at `0x140031705`
- `msrpc!RpcBindingFree` at `0x140031705`

## pseudocode

```c
__int64 __fastcall KnrNrpCreateBinding(RPC_BINDING_HANDLE *a1, int a2)
{
  unsigned int v3; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-59h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+28h] [rbp-51h] BYREF
  _DWORD v7[4]; // [rsp+50h] [rbp-29h] BYREF
  __int128 v8; // [rsp+60h] [rbp-19h]
  PSID SeNetworkServiceSid; // [rsp+70h] [rbp-9h]
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+78h] [rbp-1h] BYREF

  Binding = 0;
  memset(&Security, 0, 36);
  if ( !a1 )
    return 3221225485LL;
  *a1 = 0;
  SeNetworkServiceSid = 0;
  v7[0] = 3;
  v7[3] = a2;
  *(_QWORD *)&Template.ProtocolSequence = 3;
  *(_QWORD *)&Template.Version = 1;
  memset(&Template.NetworkAddress, 0, 40);
  v8 = 0;
  v7[1] = 1;
  v7[2] = 1;
  SeNetworkServiceSid = SeExports->SeNetworkServiceSid;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v7;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  v3 = RpcBindingCreateW(&Template, &Security, 0, &Binding);
  if ( v3 || (v3 = RpcBindingSetOption(Binding, 9u, 1u)) != 0 )
  {
    if ( Binding )
      RpcBindingFree(&Binding);
    return RpcStatusToNrpNtStatus(v3);
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
0x1400315b8  mov     [rsp-8+arg_10], rbx
0x1400315bd  push    rbp
0x1400315be  push    rdi
0x1400315bf  push    r14
0x1400315c1  lea     rbp, [rsp-47h]
0x1400315c6  sub     rsp, 0C0h
0x1400315cd  mov     rax, cs:__security_cookie
0x1400315d4  xor     rax, rsp
0x1400315d7  mov     [rbp+57h+var_20], rax
0x1400315db  xor     eax, eax
0x1400315dd  xorps   xmm0, xmm0
0x1400315e0  mov     dword ptr [rbp+57h+Security.SecurityQos], eax
0x1400315e3  mov     rdi, rcx
0x1400315e6  mov     [rbp+57h+Binding], rax
0x1400315ea  movups  xmmword ptr [rbp+57h+Security.Version], xmm0
0x1400315ee  movups  xmmword ptr [rbp+57h+Security.AuthnLevel], xmm0
0x1400315f2  test    rcx, rcx
0x1400315f5  jz      loc_1400316EF
0x1400315fb  lea     r14d, [rax+1]
0x1400315ff  mov     [rcx], rax
0x140031602  mov     [rbp+57h+var_60], 0
0x14003160a  lea     eax, [r14+2]
0x14003160e  mov     [rbp+57h+var_80], eax
0x140031611  lea     r9, [rbp+57h+Binding]; Binding
0x140031615  mov     rax, cs:__imp_SeExports
0x14003161c  xorps   xmm1, xmm1
0x14003161f  mov     [rbp+57h+var_74], edx
0x140031622  xor     r8d, r8d; Options
0x140031625  mov     qword ptr [rbp+57h+Template.ProtocolSequence], 3
0x14003162d  lea     rdx, [rbp+57h+Security]; Security
0x140031631  movdqu  xmmword ptr [rbp+57h+Template.ObjectUuid.Data1], xmm0
0x140031636  mov     rcx, [rax]
0x140031639  mov     qword ptr [rbp+57h+Template.Version], r14
0x14003163d  movdqu  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x140031642  mov     qword ptr [rbp+57h+Template.u1], 0
0x14003164a  movdqu  [rbp+57h+var_70], xmm1
0x14003164f  mov     [rbp+57h+var_7C], r14d
0x140031653  mov     [rbp+57h+var_78], r14d
0x140031657  mov     rax, [rcx+188h]
0x14003165e  lea     rcx, [rbp+57h+Template]; Template
0x140031662  mov     [rbp+57h+var_60], rax
0x140031666  lea     rax, [rbp+57h+var_80]
0x14003166a  mov     [rbp+57h+Security.SecurityQos], rax
0x14003166e  mov     qword ptr [rbp+57h+Security+4], 0
0x140031676  mov     dword ptr [rbp+57h+Security.ServerPrincName+4], 0
0x14003167d  mov     [rbp+57h+Security.AuthIdentity], 0
0x140031685  mov     [rbp+57h+Security.Version], r14d
0x140031689  mov     [rbp+57h+Security.AuthnLevel], 6
0x140031690  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x140031697  call    cs:__imp_RpcBindingCreateW
0x14003169e  nop     dword ptr [rax+rax+00h]
0x1400316a3  mov     ebx, eax
0x1400316a5  test    eax, eax
0x1400316a7  jnz     short loc_1400316F6
0x1400316a9  mov     rcx, [rbp+57h+Binding]; hBinding
0x1400316ad  lea     edx, [rax+9]; option
0x1400316b0  mov     r8d, r14d; optionValue
0x1400316b3  call    cs:__imp_RpcBindingSetOption
0x1400316ba  nop     dword ptr [rax+rax+00h]
0x1400316bf  mov     ebx, eax
0x1400316c1  test    eax, eax
0x1400316c3  jnz     short loc_1400316F6
0x1400316c5  mov     rax, [rbp+57h+Binding]
0x1400316c9  mov     [rdi], rax
0x1400316cc  xor     eax, eax
0x1400316ce  mov     rcx, [rbp+57h+var_20]
0x1400316d2  xor     rcx, rsp; StackCookie
0x1400316d5  call    __security_check_cookie
0x1400316da  mov     rbx, [rsp+0D0h+arg_10]
0x1400316e2  add     rsp, 0C0h
0x1400316e9  pop     r14
0x1400316eb  pop     rdi
0x1400316ec  pop     rbp
0x1400316ed  retn
0x1400316ef  mov     eax, 0C000000Dh
0x1400316f4  jmp     short loc_1400316CE
0x1400316f6  cmp     [rbp+57h+Binding], 0
0x1400316fb  jz      loc_140078FF2
0x140031701  lea     rcx, [rbp+57h+Binding]; Binding
0x140031705  call    cs:__imp_RpcBindingFree
0x14003170c  nop     dword ptr [rax+rax+00h]
0x140031711  nop
0x140031712  jmp     loc_140078FF2
0x140078ff2  mov     ecx, ebx
0x140078ff4  call    RpcStatusToNrpNtStatus
0x140078ff9  nop
0x140078ffa  jmp     loc_1400316CE
```
