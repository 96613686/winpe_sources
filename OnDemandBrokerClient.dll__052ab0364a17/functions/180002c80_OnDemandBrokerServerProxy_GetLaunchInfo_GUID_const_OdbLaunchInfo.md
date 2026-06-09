# OnDemandBrokerServerProxy::GetLaunchInfo(_GUID const *,_OdbLaunchInfo * *)

- ea: `0x180002c80`
- end: `0x180002e6c`
- name: `?GetLaunchInfo@OnDemandBrokerServerProxy@@UEAAJPEBU_GUID@@PEAPEAU_OdbLaunchInfo@@@Z`
- size: `492`
- prototype: `__int64 __fastcall(OnDemandBrokerServerProxy *__hidden this, const struct _GUID *, struct _OdbLaunchInfo **)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002c80`
- `0x180006570`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x180002e45`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002e45`
- `RPCRT4!RpcBindingFree` at `0x180002e17`
- `RPCRT4!RpcBindingFree` at `0x180002e61`
- `RPCRT4!RpcBindingFree` at `0x180002e17`
- `RPCRT4!RpcBindingFree` at `0x180002e61`
- `RPCRT4!RpcBindingCreateW` at `0x180002d89`
- `RPCRT4!RpcBindingCreateW` at `0x180002d89`
- `RPCRT4!NdrClientCall3` at `0x180002de4`
- `RPCRT4!NdrClientCall3` at `0x180002de4`
- `RPCRT4!RpcBindingBind` at `0x180002da5`
- `RPCRT4!RpcBindingBind` at `0x180002da5`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000665e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000665e`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerServerProxy::GetLaunchInfo(
        OnDemandBrokerServerProxy *this,
        const struct _GUID *a2,
        struct _OdbLaunchInfo **a3)
{
  RPC_STATUS v5; // eax
  int Pointer; // ebx
  CLIENT_CALL_RETURN v7; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-E8h] BYREF
  RPC_BINDING_HANDLE v10; // [rsp+38h] [rbp-E0h] BYREF
  int v11; // [rsp+40h] [rbp-D8h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+48h] [rbp-D0h] BYREF
  _DWORD v13[4]; // [rsp+70h] [rbp-A8h] BYREF
  __int128 v14; // [rsp+80h] [rbp-98h]
  _DWORD *v15; // [rsp+90h] [rbp-88h]
  _DWORD v16[4]; // [rsp+98h] [rbp-80h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 v17; // [rsp+A8h] [rbp-70h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W v18; // [rsp+B8h] [rbp-60h] BYREF

  v10 = 0;
  *(_QWORD *)&v17.ComTimeout = 5;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  v14 = 0;
  memset(&v18, 0, sizeof(v18));
  v16[0] = 257;
  v16[1] = 83886080;
  v16[2] = 18;
  Binding = 0;
  v18.Version = 1;
  v18.ProtocolSequence = 3;
  *(_QWORD *)&v17.Version = 0x100000001LL;
  v13[0] = 3;
  v13[1] = 1;
  v13[2] = 1;
  v13[3] = 3;
  v15 = v16;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v13;
  v5 = RpcBindingCreateW(&v18, &Security, &v17, &Binding);
  if ( v5 || (v5 = RpcBindingBind(0, Binding, qword_1800082D0)) != 0 )
  {
    Pointer = I_RpcMapWin32Status(v5) | 0x10000000;
    if ( Binding )
      RpcBindingFree(&Binding);
  }
  else
  {
    Pointer = 0;
    v10 = Binding;
  }
  if ( Pointer >= 0 )
  {
    v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800082A0, 0, 0, v10, a2, a3, 0).Pointer;
    Pointer = (int)v7.Pointer;
    Binding = (RPC_BINDING_HANDLE)v7.Simple;
    v11 = (int)v7.Pointer;
  }
  if ( v10 )
    RpcBindingFree(&v10);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002c80  mov     r11, rsp
0x180002c83  mov     [r11+8], rbx
0x180002c87  push    rsi
0x180002c88  push    rdi
0x180002c89  push    r14
0x180002c8b  sub     rsp, 100h
0x180002c92  mov     rax, cs:__security_cookie
0x180002c99  xor     rax, rsp
0x180002c9c  mov     [rsp+118h+var_28], rax
0x180002ca4  mov     rsi, r8
0x180002ca7  mov     rdi, rdx
0x180002caa  xor     r14d, r14d
0x180002cad  mov     [rsp+118h+var_E0], r14
0x180002cb2  mov     qword ptr [r11-68h], 5
0x180002cba  mov     qword ptr [rsp+118h+Security+4], r14
0x180002cbf  mov     dword ptr [rsp+118h+Security.ServerPrincName+4], r14d
0x180002cc4  mov     [rsp+118h+Security.AuthIdentity], r14
0x180002cc9  xorps   xmm0, xmm0
0x180002ccc  movdqu  [rsp+118h+var_98], xmm0
0x180002cd5  xorps   xmm1, xmm1
0x180002cd8  xor     eax, eax
0x180002cda  movups  xmmword ptr [r11-60h], xmm1
0x180002cdf  movups  xmmword ptr [r11-50h], xmm1
0x180002ce4  movups  xmmword ptr [r11-40h], xmm1
0x180002ce9  mov     [r11-30h], rax
0x180002ced  mov     dword ptr [r11-80h], 101h
0x180002cf5  mov     dword ptr [r11-7Ch], 5000000h
0x180002cfd  mov     dword ptr [r11-78h], 12h
0x180002d05  mov     [rsp+118h+Binding], r14
0x180002d0a  mov     dword ptr [r11-60h], 1
0x180002d12  mov     dword ptr [r11-58h], 3
0x180002d1a  mov     dword ptr [r11-70h], 1
0x180002d22  mov     dword ptr [r11-6Ch], 1
0x180002d2a  mov     [rsp+118h+var_A8], 3
0x180002d32  mov     [rsp+118h+var_A4], 1
0x180002d3a  mov     [rsp+118h+var_A0], 1
0x180002d42  mov     [rsp+118h+var_9C], 3
0x180002d4a  lea     rax, [r11-80h]
0x180002d4e  mov     [r11-88h], rax
0x180002d55  mov     [rsp+118h+Security.Version], 1
0x180002d5d  mov     [rsp+118h+Security.AuthnLevel], 6
0x180002d65  mov     [rsp+118h+Security.AuthnSvc], 14h
0x180002d6d  lea     rax, [rsp+118h+var_A8]
0x180002d72  mov     [rsp+118h+Security.SecurityQos], rax
0x180002d77  lea     r9, [rsp+118h+Binding]; Binding
0x180002d7c  lea     r8, [r11-70h]; Options
0x180002d80  lea     rdx, [rsp+118h+Security]; Security
0x180002d85  lea     rcx, [r11-60h]; Template
0x180002d89  call    cs:__imp_RpcBindingCreateW
0x180002d8f  test    eax, eax
0x180002d91  jnz     loc_180002E43
0x180002d97  lea     r8, qword_1800082D0; IfSpec
0x180002d9e  mov     rdx, [rsp+118h+Binding]; Binding
0x180002da3  xor     ecx, ecx; pAsync
0x180002da5  call    cs:__imp_RpcBindingBind
0x180002dab  test    eax, eax
0x180002dad  jnz     loc_180002E43
0x180002db3  mov     ebx, r14d
0x180002db6  mov     rax, [rsp+118h+Binding]
0x180002dbb  mov     [rsp+118h+var_E0], rax
0x180002dc0  test    ebx, ebx
0x180002dc2  js      short loc_180002E0A
0x180002dc4  mov     [rsp+118h+Binding], r14
0x180002dc9  mov     [rsp+118h+var_F0], rsi
0x180002dce  mov     [rsp+118h+var_F8], rdi
0x180002dd3  mov     r9, [rsp+118h+var_E0]
0x180002dd8  xor     r8d, r8d; pReturnValue
0x180002ddb  xor     edx, edx; nProcNum
0x180002ddd  lea     rcx, stru_1800082A0; pProxyInfo
0x180002de4  call    cs:__imp_NdrClientCall3
0x180002dea  mov     rbx, rax
0x180002ded  mov     [rsp+118h+Binding], rax
0x180002df2  mov     [rsp+118h+var_D8], eax
0x180002df6  jmp     short loc_180002E0A
0x180002df8  test    eax, eax
0x180002dfa  jle     short loc_180002E04
0x180002dfc  movzx   eax, ax
0x180002dff  or      eax, 80070000h
0x180002e04  mov     ebx, eax
0x180002e06  mov     [rsp+118h+var_D8], eax
0x180002e0a  cmp     [rsp+118h+var_E0], 0
0x180002e10  jz      short loc_180002E1D
0x180002e12  lea     rcx, [rsp+118h+var_E0]; Binding
0x180002e17  call    cs:__imp_RpcBindingFree
0x180002e1d  mov     eax, ebx
0x180002e1f  mov     rcx, [rsp+118h+var_28]
0x180002e27  xor     rcx, rsp; StackCookie
0x180002e2a  call    __security_check_cookie
0x180002e2f  mov     rbx, [rsp+118h+arg_0]
0x180002e37  add     rsp, 100h
0x180002e3e  pop     r14
0x180002e40  pop     rdi
0x180002e41  pop     rsi
0x180002e42  retn
0x180002e43  mov     ecx, eax; Status
0x180002e45  call    cs:__imp_I_RpcMapWin32Status
0x180002e4b  mov     ebx, eax
0x180002e4d  bts     ebx, 1Ch
0x180002e51  cmp     [rsp+118h+Binding], r14
0x180002e56  jz      loc_180002DC0
0x180002e5c  lea     rcx, [rsp+118h+Binding]; Binding
0x180002e61  call    cs:__imp_RpcBindingFree
0x180002e67  jmp     loc_180002DC0
0x180006650  push    rbp
0x180006652  sub     rsp, 30h
0x180006656  mov     rbp, rdx
0x180006659  mov     rcx, [rcx]
0x18000665c  mov     ecx, [rcx]; ExceptionCode
0x18000665e  call    cs:__imp_I_RpcExceptionFilter
0x180006664  nop
0x180006665  add     rsp, 30h
0x180006669  pop     rbp
0x18000666a  retn
```
