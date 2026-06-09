# OnDemandBrokerServerProxy::CompleteSession(ulong)

- ea: `0x180003df0`
- end: `0x180003fd3`
- name: `?CompleteSession@OnDemandBrokerServerProxy@@UEAAJK@Z`
- size: `483`
- prototype: `__int64 __fastcall(OnDemandBrokerServerProxy *this, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003df0`
- `0x180006570`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x180003fac`
- `RPCRT4!I_RpcMapWin32Status` at `0x180003fac`
- `RPCRT4!RpcBindingFree` at `0x180003f38`
- `RPCRT4!RpcBindingFree` at `0x180003fc8`
- `RPCRT4!RpcBindingFree` at `0x180003f38`
- `RPCRT4!RpcBindingFree` at `0x180003fc8`
- `RPCRT4!RpcBindingCreateW` at `0x180003ef1`
- `RPCRT4!RpcBindingCreateW` at `0x180003ef1`
- `RPCRT4!NdrClientCall3` at `0x180003f82`
- `RPCRT4!NdrClientCall3` at `0x180003f82`
- `RPCRT4!RpcBindingBind` at `0x180003f0d`
- `RPCRT4!RpcBindingBind` at `0x180003f0d`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000677e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000677e`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerServerProxy::CompleteSession(OnDemandBrokerServerProxy *this, int a2)
{
  RPC_STATUS v3; // eax
  int Pointer; // ebx
  CLIENT_CALL_RETURN v6; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-D8h] BYREF
  RPC_BINDING_HANDLE v8; // [rsp+38h] [rbp-D0h] BYREF
  int v9; // [rsp+40h] [rbp-C8h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+48h] [rbp-C0h] BYREF
  _DWORD v11[4]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v12; // [rsp+80h] [rbp-88h]
  _DWORD *v13; // [rsp+90h] [rbp-78h]
  _DWORD v14[4]; // [rsp+98h] [rbp-70h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 v15; // [rsp+A8h] [rbp-60h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W v16; // [rsp+B8h] [rbp-50h] BYREF

  v8 = 0;
  *(_QWORD *)&v15.ComTimeout = 5;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  v12 = 0;
  memset(&v16, 0, sizeof(v16));
  v14[0] = 257;
  v14[1] = 83886080;
  v14[2] = 18;
  Binding = 0;
  v16.Version = 1;
  v16.ProtocolSequence = 3;
  *(_QWORD *)&v15.Version = 0x100000001LL;
  v11[0] = 3;
  v11[1] = 1;
  v11[2] = 1;
  v11[3] = 3;
  v13 = v14;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v11;
  v3 = RpcBindingCreateW(&v16, &Security, &v15, &Binding);
  if ( v3 || (v3 = RpcBindingBind(0, Binding, qword_180008360)) != 0 )
  {
    Pointer = I_RpcMapWin32Status(v3) | 0x10000000;
    if ( Binding )
      RpcBindingFree(&Binding);
  }
  else
  {
    Pointer = 0;
    v8 = Binding;
  }
  if ( Pointer >= 0 )
  {
    Binding = 0;
    v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800083C0, 1u, 0, v8, a2).Pointer;
    Pointer = (int)v6.Pointer;
    Binding = (RPC_BINDING_HANDLE)v6.Simple;
    v9 = (int)v6.Pointer;
  }
  if ( v8 )
    RpcBindingFree(&v8);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180003df0  mov     r11, rsp
0x180003df3  mov     [r11+8], rbx
0x180003df7  mov     [r11+18h], rsi
0x180003dfb  push    rdi
0x180003dfc  sub     rsp, 100h
0x180003e03  mov     rax, cs:__security_cookie
0x180003e0a  xor     rax, rsp
0x180003e0d  mov     [rsp+108h+var_18], rax
0x180003e15  mov     edi, edx
0x180003e17  xor     esi, esi
0x180003e19  mov     [rsp+108h+var_D0], rsi
0x180003e1e  mov     qword ptr [r11-58h], 5
0x180003e26  mov     qword ptr [rsp+108h+Security+4], rsi
0x180003e2b  mov     dword ptr [rsp+108h+Security.ServerPrincName+4], esi
0x180003e2f  mov     [rsp+108h+Security.AuthIdentity], rsi
0x180003e34  xorps   xmm0, xmm0
0x180003e37  movdqu  [rsp+108h+var_88], xmm0
0x180003e40  xorps   xmm1, xmm1
0x180003e43  xor     eax, eax
0x180003e45  movups  xmmword ptr [r11-50h], xmm1
0x180003e4a  movups  xmmword ptr [r11-40h], xmm1
0x180003e4f  movups  xmmword ptr [r11-30h], xmm1
0x180003e54  mov     [r11-20h], rax
0x180003e58  mov     dword ptr [r11-70h], 101h
0x180003e60  mov     dword ptr [r11-6Ch], 5000000h
0x180003e68  mov     dword ptr [r11-68h], 12h
0x180003e70  mov     [rsp+108h+Binding], rsi
0x180003e75  mov     dword ptr [r11-50h], 1
0x180003e7d  mov     dword ptr [r11-48h], 3
0x180003e85  mov     dword ptr [r11-60h], 1
0x180003e8d  mov     dword ptr [r11-5Ch], 1
0x180003e95  mov     [rsp+108h+var_98], 3
0x180003e9d  mov     [rsp+108h+var_94], 1
0x180003ea5  mov     [rsp+108h+var_90], 1
0x180003ead  mov     [rsp+108h+var_8C], 3
0x180003eb5  lea     rax, [r11-70h]
0x180003eb9  mov     [r11-78h], rax
0x180003ebd  mov     [rsp+108h+Security.Version], 1
0x180003ec5  mov     [rsp+108h+Security.AuthnLevel], 6
0x180003ecd  mov     [rsp+108h+Security.AuthnSvc], 14h
0x180003ed5  lea     rax, [rsp+108h+var_98]
0x180003eda  mov     [rsp+108h+Security.SecurityQos], rax
0x180003edf  lea     r9, [rsp+108h+Binding]; Binding
0x180003ee4  lea     r8, [r11-60h]; Options
0x180003ee8  lea     rdx, [rsp+108h+Security]; Security
0x180003eed  lea     rcx, [r11-50h]; Template
0x180003ef1  call    cs:__imp_RpcBindingCreateW
0x180003ef7  test    eax, eax
0x180003ef9  jnz     loc_180003FAA
0x180003eff  lea     r8, qword_180008360; IfSpec
0x180003f06  mov     rdx, [rsp+108h+Binding]; Binding
0x180003f0b  xor     ecx, ecx; pAsync
0x180003f0d  call    cs:__imp_RpcBindingBind
0x180003f13  test    eax, eax
0x180003f15  jnz     loc_180003FAA
0x180003f1b  mov     ebx, esi
0x180003f1d  mov     rax, [rsp+108h+Binding]
0x180003f22  mov     [rsp+108h+var_D0], rax
0x180003f27  test    ebx, ebx
0x180003f29  jns     short loc_180003F65
0x180003f2b  cmp     [rsp+108h+var_D0], 0
0x180003f31  jz      short loc_180003F3E
0x180003f33  lea     rcx, [rsp+108h+var_D0]; Binding
0x180003f38  call    cs:__imp_RpcBindingFree
0x180003f3e  mov     eax, ebx
0x180003f40  mov     rcx, [rsp+108h+var_18]
0x180003f48  xor     rcx, rsp; StackCookie
0x180003f4b  call    __security_check_cookie
0x180003f50  lea     r11, [rsp+108h+var_8]
0x180003f58  mov     rbx, [r11+10h]
0x180003f5c  mov     rsi, [r11+20h]
0x180003f60  mov     rsp, r11
0x180003f63  pop     rdi
0x180003f64  retn
0x180003f65  mov     [rsp+108h+Binding], rsi
0x180003f6a  mov     [rsp+108h+var_E8], edi
0x180003f6e  mov     r9, [rsp+108h+var_D0]
0x180003f73  xor     r8d, r8d; pReturnValue
0x180003f76  mov     edx, 1; nProcNum
0x180003f7b  lea     rcx, stru_1800083C0; pProxyInfo
0x180003f82  call    cs:__imp_NdrClientCall3
0x180003f88  mov     rbx, rax
0x180003f8b  mov     [rsp+108h+Binding], rax
0x180003f90  mov     [rsp+108h+var_C8], eax
0x180003f94  jmp     short loc_180003F2B
0x180003f96  test    eax, eax
0x180003f98  jle     short loc_180003FA2
0x180003f9a  movzx   eax, ax
0x180003f9d  or      eax, 80070000h
0x180003fa2  mov     ebx, eax
0x180003fa4  mov     [rsp+108h+var_C8], eax
0x180003fa8  jmp     short loc_180003F2B
0x180003faa  mov     ecx, eax; Status
0x180003fac  call    cs:__imp_I_RpcMapWin32Status
0x180003fb2  mov     ebx, eax
0x180003fb4  bts     ebx, 1Ch
0x180003fb8  cmp     [rsp+108h+Binding], rsi
0x180003fbd  jz      loc_180003F27
0x180003fc3  lea     rcx, [rsp+108h+Binding]; Binding
0x180003fc8  call    cs:__imp_RpcBindingFree
0x180003fce  jmp     loc_180003F27
0x180006770  push    rbp
0x180006772  sub     rsp, 30h
0x180006776  mov     rbp, rdx
0x180006779  mov     rcx, [rcx]
0x18000677c  mov     ecx, [rcx]; ExceptionCode
0x18000677e  call    cs:__imp_I_RpcExceptionFilter
0x180006784  nop
0x180006785  add     rsp, 30h
0x180006789  pop     rbp
0x18000678a  retn
```
