# KnrNrpCreateBinding

- ea: `0x140031598`
- end: `0x1400316f7`
- name: `KnrNrpCreateBinding`
- size: `351`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400314d0`

## callees

- `0x140031598`
- `0x14003fa9c`
- `0x1400726a0`

## import_xrefs

- `ntoskrnl!SeExports` at `0x1400315f5`
- `msrpc!RpcBindingSetOption` at `0x140031693`
- `msrpc!RpcBindingSetOption` at `0x140031693`
- `msrpc!RpcBindingCreateW` at `0x140031677`
- `msrpc!RpcBindingCreateW` at `0x140031677`
- `msrpc!RpcBindingFree` at `0x1400316e5`
- `msrpc!RpcBindingFree` at `0x1400316e5`

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
0x140031598  mov     [rsp-8+arg_10], rbx
0x14003159d  push    rbp
0x14003159e  push    rdi
0x14003159f  push    r14
0x1400315a1  lea     rbp, [rsp-47h]
0x1400315a6  sub     rsp, 0C0h
0x1400315ad  mov     rax, cs:__security_cookie
0x1400315b4  xor     rax, rsp
0x1400315b7  mov     [rbp+57h+var_20], rax
0x1400315bb  xor     eax, eax
0x1400315bd  xorps   xmm0, xmm0
0x1400315c0  mov     dword ptr [rbp+57h+Security.SecurityQos], eax
0x1400315c3  mov     rdi, rcx
0x1400315c6  mov     [rbp+57h+Binding], rax
0x1400315ca  movups  xmmword ptr [rbp+57h+Security.Version], xmm0
0x1400315ce  movups  xmmword ptr [rbp+57h+Security.AuthnLevel], xmm0
0x1400315d2  test    rcx, rcx
0x1400315d5  jz      loc_1400316CF
0x1400315db  lea     r14d, [rax+1]
0x1400315df  mov     [rcx], rax
0x1400315e2  mov     [rbp+57h+var_60], 0
0x1400315ea  lea     eax, [r14+2]
0x1400315ee  mov     [rbp+57h+var_80], eax
0x1400315f1  lea     r9, [rbp+57h+Binding]; Binding
0x1400315f5  mov     rax, cs:__imp_SeExports
0x1400315fc  xorps   xmm1, xmm1
0x1400315ff  mov     [rbp+57h+var_74], edx
0x140031602  xor     r8d, r8d; Options
0x140031605  mov     qword ptr [rbp+57h+Template.ProtocolSequence], 3
0x14003160d  lea     rdx, [rbp+57h+Security]; Security
0x140031611  movdqu  xmmword ptr [rbp+57h+Template.ObjectUuid.Data1], xmm0
0x140031616  mov     rcx, [rax]
0x140031619  mov     qword ptr [rbp+57h+Template.Version], r14
0x14003161d  movdqu  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x140031622  mov     qword ptr [rbp+57h+Template.u1], 0
0x14003162a  movdqu  [rbp+57h+var_70], xmm1
0x14003162f  mov     [rbp+57h+var_7C], r14d
0x140031633  mov     [rbp+57h+var_78], r14d
0x140031637  mov     rax, [rcx+188h]
0x14003163e  lea     rcx, [rbp+57h+Template]; Template
0x140031642  mov     [rbp+57h+var_60], rax
0x140031646  lea     rax, [rbp+57h+var_80]
0x14003164a  mov     [rbp+57h+Security.SecurityQos], rax
0x14003164e  mov     qword ptr [rbp+57h+Security+4], 0
0x140031656  mov     dword ptr [rbp+57h+Security.ServerPrincName+4], 0
0x14003165d  mov     [rbp+57h+Security.AuthIdentity], 0
0x140031665  mov     [rbp+57h+Security.Version], r14d
0x140031669  mov     [rbp+57h+Security.AuthnLevel], 6
0x140031670  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x140031677  call    cs:__imp_RpcBindingCreateW
0x14003167e  nop     dword ptr [rax+rax+00h]
0x140031683  mov     ebx, eax
0x140031685  test    eax, eax
0x140031687  jnz     short loc_1400316D6
0x140031689  mov     rcx, [rbp+57h+Binding]; hBinding
0x14003168d  lea     edx, [rax+9]; option
0x140031690  mov     r8d, r14d; optionValue
0x140031693  call    cs:__imp_RpcBindingSetOption
0x14003169a  nop     dword ptr [rax+rax+00h]
0x14003169f  mov     ebx, eax
0x1400316a1  test    eax, eax
0x1400316a3  jnz     short loc_1400316D6
0x1400316a5  mov     rax, [rbp+57h+Binding]
0x1400316a9  mov     [rdi], rax
0x1400316ac  xor     eax, eax
0x1400316ae  mov     rcx, [rbp+57h+var_20]
0x1400316b2  xor     rcx, rsp; StackCookie
0x1400316b5  call    __security_check_cookie
0x1400316ba  mov     rbx, [rsp+0D0h+arg_10]
0x1400316c2  add     rsp, 0C0h
0x1400316c9  pop     r14
0x1400316cb  pop     rdi
0x1400316cc  pop     rbp
0x1400316cd  retn
0x1400316cf  mov     eax, 0C000000Dh
0x1400316d4  jmp     short loc_1400316AE
0x1400316d6  cmp     [rbp+57h+Binding], 0
0x1400316db  jz      loc_140078E72
0x1400316e1  lea     rcx, [rbp+57h+Binding]; Binding
0x1400316e5  call    cs:__imp_RpcBindingFree
0x1400316ec  nop     dword ptr [rax+rax+00h]
0x1400316f1  nop
0x1400316f2  jmp     loc_140078E72
0x140078e72  mov     ecx, ebx
0x140078e74  call    RpcStatusToNrpNtStatus
0x140078e79  nop
0x140078e7a  jmp     loc_1400316AE
```
