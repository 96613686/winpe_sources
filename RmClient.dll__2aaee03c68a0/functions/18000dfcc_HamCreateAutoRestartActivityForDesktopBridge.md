# HamCreateAutoRestartActivityForDesktopBridge

- ea: `0x18000dfcc`
- end: `0x18000e1a3`
- name: `HamCreateAutoRestartActivityForDesktopBridge`
- size: `471`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180019fa0`

## callees

- `0x18000dfcc`
- `0x18001aec0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e11c`
- `RPCRT4!NdrClientCall3` at `0x18000e11c`
- `RPCRT4!RpcBindingCreateW` at `0x18000e0a5`
- `RPCRT4!RpcBindingCreateW` at `0x18000e0a5`
- `RPCRT4!RpcBindingBind` at `0x18000e0c3`
- `RPCRT4!RpcBindingBind` at `0x18000e0c3`
- `RPCRT4!RpcBindingFree` at `0x18000e151`
- `RPCRT4!RpcBindingFree` at `0x18000e198`
- `RPCRT4!RpcBindingFree` at `0x18000e151`
- `RPCRT4!RpcBindingFree` at `0x18000e198`
- `RPCRT4!RpcExceptionFilter` at `0x18001b480`
- `RPCRT4!RpcExceptionFilter` at `0x18001b480`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000e132`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000e132`

## pseudocode

```c
__int64 __fastcall HamCreateAutoRestartActivityForDesktopBridge(__int64 a1, __int64 a2)
{
  RPC_STATUS v4; // eax
  signed int Pointer; // ebx
  bool v6; // cc
  CLIENT_CALL_RETURN v7; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-D8h] BYREF
  RPC_BINDING_HANDLE v10; // [rsp+38h] [rbp-D0h] BYREF
  int v11; // [rsp+40h] [rbp-C8h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v13[2]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v14; // [rsp+80h] [rbp-88h]
  __int128 v15; // [rsp+90h] [rbp-78h]
  __int64 v16; // [rsp+A0h] [rbp-68h]
  RPC_BINDING_HANDLE_OPTIONS_V1 v17; // [rsp+A8h] [rbp-60h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W v18; // [rsp+B8h] [rbp-50h] BYREF

  v10 = 0;
  Binding = 0;
  memset(&v18, 0, sizeof(v18));
  *(_QWORD *)&v17.ComTimeout = 5;
  v14 = 0;
  v15 = 0;
  v16 = 0;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  v18.Version = 1;
  v18.ProtocolSequence = 3;
  *(_QWORD *)&v17.Version = 0x100000001LL;
  v13[0] = 5;
  v13[1] = 0x300000001LL;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v13;
  v4 = RpcBindingCreateW(&v18, &Security, &v17, &Binding);
  Pointer = v4;
  v6 = v4 <= 0;
  if ( v4 || (v4 = RpcBindingBind(0, Binding, qword_18001DC80), Pointer = v4, v6 = v4 <= 0, v4) )
  {
    if ( !v6 )
      Pointer = (unsigned __int16)v4 | 0xC0070000;
  }
  else
  {
    v10 = Binding;
    Binding = 0;
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( Pointer >= 0 )
  {
    v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 6u, 0, v10, a1, a2, 0).Pointer;
    Pointer = (signed int)v7.Pointer;
    Binding = (RPC_BINDING_HANDLE)v7.Simple;
    v11 = (int)v7.Pointer;
    if ( SLODWORD(v7.Simple) >= 0 )
      Pointer = 0;
  }
  if ( v10 )
    RpcBindingFree(&v10);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18000dfcc  mov     r11, rsp
0x18000dfcf  mov     [r11+18h], rbx
0x18000dfd3  mov     [r11+20h], rsi
0x18000dfd7  push    r14
0x18000dfd9  sub     rsp, 100h
0x18000dfe0  mov     rax, cs:__security_cookie
0x18000dfe7  xor     rax, rsp
0x18000dfea  mov     [rsp+108h+var_18], rax
0x18000dff2  mov     r14, rdx
0x18000dff5  mov     rsi, rcx
0x18000dff8  mov     [rsp+108h+var_D0], 0
0x18000e001  mov     [rsp+108h+Binding], 0
0x18000e00a  xorps   xmm0, xmm0
0x18000e00d  xor     eax, eax
0x18000e00f  movups  xmmword ptr [r11-50h], xmm0
0x18000e014  movups  xmmword ptr [r11-40h], xmm0
0x18000e019  movups  xmmword ptr [r11-30h], xmm0
0x18000e01e  mov     [r11-20h], rax
0x18000e022  mov     qword ptr [r11-58h], 5
0x18000e02a  movups  [rsp+108h+var_98], xmm0
0x18000e02f  movups  [rsp+108h+var_88], xmm0
0x18000e037  movups  xmmword ptr [r11-78h], xmm0
0x18000e03c  mov     [r11-68h], rax
0x18000e040  mov     qword ptr [rsp+108h+Security+4], rax
0x18000e045  mov     dword ptr [rsp+108h+Security.ServerPrincName+4], eax
0x18000e049  mov     [rsp+108h+Security.AuthIdentity], rax
0x18000e04e  lea     edx, [rax+1]
0x18000e051  mov     [r11-50h], edx
0x18000e055  lea     ecx, [rax+3]
0x18000e058  mov     [r11-48h], ecx
0x18000e05c  mov     [r11-60h], edx
0x18000e060  mov     [r11-5Ch], edx
0x18000e064  mov     qword ptr [rsp+108h+var_98], 5
0x18000e06d  mov     dword ptr [rsp+108h+var_98+8], edx
0x18000e071  mov     dword ptr [rsp+108h+var_98+0Ch], ecx
0x18000e075  mov     [rsp+108h+Security.Version], edx
0x18000e079  mov     [rsp+108h+Security.AuthnLevel], 6
0x18000e081  mov     [rsp+108h+Security.AuthnSvc], 0Ah
0x18000e089  lea     rax, [rsp+108h+var_98]
0x18000e08e  mov     [rsp+108h+Security.SecurityQos], rax
0x18000e093  lea     r9, [rsp+108h+Binding]; Binding
0x18000e098  lea     r8, [r11-60h]; Options
0x18000e09c  lea     rdx, [rsp+108h+Security]; Security
0x18000e0a1  lea     rcx, [r11-50h]; Template
0x18000e0a5  call    cs:__imp_RpcBindingCreateW
0x18000e0ab  mov     ebx, eax
0x18000e0ad  test    eax, eax
0x18000e0af  jnz     loc_18000E17F
0x18000e0b5  lea     r8, qword_18001DC80; IfSpec
0x18000e0bc  mov     rdx, [rsp+108h+Binding]; Binding
0x18000e0c1  xor     ecx, ecx; pAsync
0x18000e0c3  call    cs:__imp_RpcBindingBind
0x18000e0c9  mov     ebx, eax
0x18000e0cb  test    eax, eax
0x18000e0cd  jnz     loc_18000E17F
0x18000e0d3  mov     rax, [rsp+108h+Binding]
0x18000e0d8  mov     [rsp+108h+var_D0], rax
0x18000e0dd  mov     [rsp+108h+Binding], 0
0x18000e0e6  cmp     [rsp+108h+Binding], 0
0x18000e0ec  jnz     loc_18000E193
0x18000e0f2  test    ebx, ebx
0x18000e0f4  js      short loc_18000E144
0x18000e0f6  mov     [rsp+108h+Binding], 0
0x18000e0ff  mov     [rsp+108h+var_E0], r14
0x18000e104  mov     [rsp+108h+var_E8], rsi
0x18000e109  mov     r9, [rsp+108h+var_D0]
0x18000e10e  xor     r8d, r8d; pReturnValue
0x18000e111  lea     edx, [r8+6]; nProcNum
0x18000e115  lea     rcx, pProxyInfo; pProxyInfo
0x18000e11c  call    cs:__imp_NdrClientCall3
0x18000e122  mov     rbx, rax
0x18000e125  mov     [rsp+108h+Binding], rax
0x18000e12a  mov     [rsp+108h+var_C8], eax
0x18000e12e  jmp     short loc_18000E13E
0x18000e130  mov     ecx, eax; Status
0x18000e132  call    cs:__imp_I_RpcMapWin32Status
0x18000e138  mov     ebx, eax
0x18000e13a  mov     [rsp+108h+var_C8], eax
0x18000e13e  test    ebx, ebx
0x18000e140  js      short loc_18000E144
0x18000e142  xor     ebx, ebx
0x18000e144  cmp     [rsp+108h+var_D0], 0
0x18000e14a  jz      short loc_18000E157
0x18000e14c  lea     rcx, [rsp+108h+var_D0]; Binding
0x18000e151  call    cs:__imp_RpcBindingFree
0x18000e157  mov     eax, ebx
0x18000e159  mov     rcx, [rsp+108h+var_18]
0x18000e161  xor     rcx, rsp; StackCookie
0x18000e164  call    __security_check_cookie
0x18000e169  lea     r11, [rsp+108h+var_8]
0x18000e171  mov     rbx, [r11+20h]
0x18000e175  mov     rsi, [r11+28h]
0x18000e179  mov     rsp, r11
0x18000e17c  pop     r14
0x18000e17e  retn
0x18000e17f  jle     loc_18000E0E6
0x18000e185  movzx   ebx, ax
0x18000e188  or      ebx, 0C0070000h
0x18000e18e  jmp     loc_18000E0E6
0x18000e193  lea     rcx, [rsp+108h+Binding]; Binding
0x18000e198  call    cs:__imp_RpcBindingFree
0x18000e19e  jmp     loc_18000E0F2
0x18001b472  push    rbp
0x18001b474  sub     rsp, 30h
0x18001b478  mov     rbp, rdx
0x18001b47b  mov     rcx, [rcx]
0x18001b47e  mov     ecx, [rcx]; ExceptionCode
0x18001b480  call    cs:__imp_RpcExceptionFilter
0x18001b486  nop
0x18001b487  add     rsp, 30h
0x18001b48b  pop     rbp
0x18001b48c  retn
```
