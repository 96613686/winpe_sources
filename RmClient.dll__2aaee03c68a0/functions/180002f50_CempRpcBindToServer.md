# CempRpcBindToServer

- ea: `0x180002f50`
- end: `0x180003090`
- name: `CempRpcBindToServer`
- size: `320`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE IfSpec, RPC_BINDING_HANDLE *)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800011a0`
- `0x180001a70`
- `0x180001b80`
- `0x180001d40`
- `0x180002750`
- `0x180002860`
- `0x180004b30`
- `0x180004bd0`
- `0x180013314`
- `0x1800152f0`
- `0x180015390`
- `0x180015430`
- `0x1800154d0`
- `0x180015570`
- `0x180015630`
- `0x1800156f0`
- `0x1800157b0`
- `0x180015860`
- `0x180019b10`
- `0x180019fa0`
- `0x18001ab9c`

## callees

- `0x180002f50`
- `0x18001aec0`

## import_xrefs

- `RPCRT4!RpcBindingCreateW` at `0x18000301e`
- `RPCRT4!RpcBindingCreateW` at `0x18000301e`
- `RPCRT4!RpcBindingBind` at `0x180003033`
- `RPCRT4!RpcBindingBind` at `0x180003033`
- `RPCRT4!RpcBindingFree` at `0x180003086`
- `RPCRT4!RpcBindingFree` at `0x180003086`

## pseudocode

```c
__int64 __fastcall CempRpcBindToServer(RPC_IF_HANDLE IfSpec, RPC_BINDING_HANDLE *a2)
{
  RPC_STATUS v4; // eax
  unsigned int v5; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-79h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+28h] [rbp-71h] BYREF
  __int64 v9; // [rsp+50h] [rbp-49h] BYREF
  int v10; // [rsp+58h] [rbp-41h]
  int v11; // [rsp+5Ch] [rbp-3Dh]
  __int128 v12; // [rsp+60h] [rbp-39h]
  __int128 v13; // [rsp+70h] [rbp-29h]
  __int64 v14; // [rsp+80h] [rbp-19h]
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+88h] [rbp-11h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+98h] [rbp-1h] BYREF

  *(_QWORD *)&Options.ComTimeout = 5;
  Options.Version = 1;
  Binding = 0;
  memset(&Template, 0, sizeof(Template));
  v14 = 0;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v9;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  Template.Version = 1;
  Template.ProtocolSequence = 3;
  Options.Flags = 1;
  v9 = 5;
  v12 = 0;
  v10 = 1;
  v13 = 0;
  v11 = 3;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  v4 = RpcBindingCreateW(&Template, &Security, &Options, &Binding);
  v5 = v4;
  if ( v4 )
  {
    if ( v4 <= 0 )
      goto LABEL_8;
    goto LABEL_7;
  }
  v4 = RpcBindingBind(0, Binding, IfSpec);
  v5 = v4;
  if ( !v4 )
  {
    *a2 = Binding;
    return 0;
  }
  if ( v4 > 0 )
LABEL_7:
    v5 = (unsigned __int16)v4 | 0xC0070000;
LABEL_8:
  if ( Binding )
    RpcBindingFree(&Binding);
  return v5;
}

```

## disassembly

```asm
0x180002f50  mov     [rsp-8+arg_10], rbx
0x180002f55  mov     [rsp-8+arg_18], rsi
0x180002f5a  push    rbp
0x180002f5b  push    rdi
0x180002f5c  push    r14
0x180002f5e  lea     rbp, [rsp-47h]
0x180002f63  sub     rsp, 0E0h
0x180002f6a  mov     rax, cs:__security_cookie
0x180002f71  xor     rax, rsp
0x180002f74  mov     [rbp+57h+var_20], rax
0x180002f78  xorps   xmm0, xmm0
0x180002f7b  mov     qword ptr [rbp+57h+Options.ComTimeout], 5
0x180002f83  xor     r14d, r14d
0x180002f86  mov     [rbp+57h+Options.Version], 1
0x180002f8d  xor     eax, eax
0x180002f8f  mov     [rbp+57h+Binding], r14
0x180002f93  movups  xmmword ptr [rbp+57h+Template.Version], xmm0
0x180002f97  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x180002f9b  lea     r9, [rbp+57h+Binding]; Binding
0x180002f9f  lea     rax, [rbp+57h+var_A0]
0x180002fa3  mov     [rbp+57h+var_70], r14
0x180002fa7  mov     rdi, rdx
0x180002faa  mov     [rbp+57h+Security.SecurityQos], rax
0x180002fae  mov     rsi, rcx
0x180002fb1  mov     qword ptr [rbp+57h+Security+4], r14
0x180002fb5  xorps   xmm1, xmm1
0x180002fb8  mov     dword ptr [rbp+57h+Security.ServerPrincName+4], r14d
0x180002fbc  lea     r8, [rbp+57h+Options]; Options
0x180002fc0  mov     [rbp+57h+Security.AuthIdentity], r14
0x180002fc4  lea     rdx, [rbp+57h+Security]; Security
0x180002fc8  mov     [rbp+57h+Template.Version], 1
0x180002fcf  lea     rcx, [rbp+57h+Template]; Template
0x180002fd3  mov     [rbp+57h+Template.ProtocolSequence], 3
0x180002fda  movups  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x180002fde  mov     [rbp+57h+Options.Flags], 1
0x180002fe5  movups  xmmword ptr [rbp+57h+Template.u1], xmm0
0x180002fe9  mov     [rbp+57h+var_A0], 5
0x180002ff1  movdqu  [rbp+57h+var_90], xmm0
0x180002ff6  mov     [rbp+57h+var_98], 1
0x180002ffd  movdqu  [rbp+57h+var_80], xmm1
0x180003002  mov     [rbp+57h+var_94], 3
0x180003009  mov     [rbp+57h+Security.Version], 1
0x180003010  mov     [rbp+57h+Security.AuthnLevel], 6
0x180003017  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x18000301e  call    cs:__imp_RpcBindingCreateW
0x180003024  mov     ebx, eax
0x180003026  test    eax, eax
0x180003028  jnz     short loc_18000306D
0x18000302a  mov     rdx, [rbp+57h+Binding]; Binding
0x18000302e  mov     r8, rsi; IfSpec
0x180003031  xor     ecx, ecx; pAsync
0x180003033  call    cs:__imp_RpcBindingBind
0x180003039  mov     ebx, eax
0x18000303b  test    eax, eax
0x18000303d  jnz     short loc_180003071
0x18000303f  mov     rax, [rbp+57h+Binding]
0x180003043  mov     [rdi], rax
0x180003046  mov     eax, r14d
0x180003049  mov     rcx, [rbp+57h+var_20]
0x18000304d  xor     rcx, rsp; StackCookie
0x180003050  call    __security_check_cookie
0x180003055  lea     r11, [rsp+0F0h+var_10]
0x18000305d  mov     rbx, [r11+30h]
0x180003061  mov     rsi, [r11+38h]
0x180003065  mov     rsp, r11
0x180003068  pop     r14
0x18000306a  pop     rdi
0x18000306b  pop     rbp
0x18000306c  retn
0x18000306d  jg      short loc_180003073
0x18000306f  jmp     short loc_18000307C
0x180003071  jle     short loc_18000307C
0x180003073  movzx   ebx, ax
0x180003076  or      ebx, 0C0070000h
0x18000307c  cmp     [rbp+57h+Binding], r14
0x180003080  jz      short loc_18000308C
0x180003082  lea     rcx, [rbp+57h+Binding]; Binding
0x180003086  call    cs:__imp_RpcBindingFree
0x18000308c  mov     eax, ebx
0x18000308e  jmp     short loc_180003049
```
