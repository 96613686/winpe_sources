# HamHostIdFindOrCreate

- ea: `0x18000b020`
- end: `0x18000b216`
- name: `HamHostIdFindOrCreate`
- size: `502`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000b020`
- `0x18001aec0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000b17b`
- `RPCRT4!NdrClientCall3` at `0x18000b17b`
- `RPCRT4!RpcBindingCreateW` at `0x18000b10a`
- `RPCRT4!RpcBindingCreateW` at `0x18000b10a`
- `RPCRT4!RpcBindingBind` at `0x18000b128`
- `RPCRT4!RpcBindingBind` at `0x18000b128`
- `RPCRT4!RpcBindingFree` at `0x18000b1b2`
- `RPCRT4!RpcBindingFree` at `0x18000b20b`
- `RPCRT4!RpcBindingFree` at `0x18000b1b2`
- `RPCRT4!RpcBindingFree` at `0x18000b20b`
- `RPCRT4!RpcExceptionFilter` at `0x18001b2ce`
- `RPCRT4!RpcExceptionFilter` at `0x18001b2ce`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000b191`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000b191`

## pseudocode

```c
__int64 __fastcall HamHostIdFindOrCreate(__int64 a1, __int64 a2)
{
  RPC_STATUS v4; // eax
  signed int Pointer; // ebx
  RPC_STATUS v6; // eax
  CLIENT_CALL_RETURN v7; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-E8h] BYREF
  RPC_BINDING_HANDLE v10; // [rsp+38h] [rbp-E0h] BYREF
  int v11; // [rsp+40h] [rbp-D8h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+48h] [rbp-D0h] BYREF
  __int64 v13; // [rsp+70h] [rbp-A8h] BYREF
  int v14; // [rsp+78h] [rbp-A0h]
  int v15; // [rsp+7Ch] [rbp-9Ch]
  __int128 v16; // [rsp+80h] [rbp-98h]
  __int128 v17; // [rsp+90h] [rbp-88h]
  __int64 v18; // [rsp+A0h] [rbp-78h]
  RPC_BINDING_HANDLE_OPTIONS_V1 v19; // [rsp+A8h] [rbp-70h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W v20; // [rsp+B8h] [rbp-60h] BYREF

  v10 = 0;
  Binding = 0;
  memset(&v20, 0, sizeof(v20));
  *(_QWORD *)&v19.ComTimeout = 5;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  v20.Version = 1;
  v20.ProtocolSequence = 3;
  *(_QWORD *)&v19.Version = 0x100000001LL;
  v13 = 5;
  v14 = 1;
  v15 = 3;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v13;
  v4 = RpcBindingCreateW(&v20, &Security, &v19, &Binding);
  Pointer = v4;
  if ( v4 )
  {
    if ( v4 > 0 )
      Pointer = (unsigned __int16)v4 | 0xC0070000;
  }
  else
  {
    v6 = RpcBindingBind(0, Binding, qword_18001DBC0);
    Pointer = v6;
    if ( v6 )
    {
      if ( v6 > 0 )
        Pointer = (unsigned __int16)v6 | 0xC0070000;
    }
    else
    {
      v10 = Binding;
      Binding = 0;
      Pointer = 0;
    }
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( Pointer >= 0 )
  {
    v7.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DC20, 1u, 0, v10, a1, a2, 0).Pointer;
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
0x18000b020  mov     r11, rsp
0x18000b023  mov     [r11+18h], rbx
0x18000b027  push    rsi
0x18000b028  push    rdi
0x18000b029  push    r14
0x18000b02b  sub     rsp, 100h
0x18000b032  mov     rax, cs:__security_cookie
0x18000b039  xor     rax, rsp
0x18000b03c  mov     [rsp+118h+var_28], rax
0x18000b044  mov     r14, rdx
0x18000b047  mov     rsi, rcx
0x18000b04a  xor     edi, edi
0x18000b04c  mov     [rsp+118h+var_E0], rdi
0x18000b051  mov     [rsp+118h+Binding], rdi
0x18000b056  xorps   xmm0, xmm0
0x18000b059  xor     eax, eax
0x18000b05b  movups  xmmword ptr [r11-60h], xmm0
0x18000b060  movups  xmmword ptr [r11-50h], xmm0
0x18000b065  movups  xmmword ptr [r11-40h], xmm0
0x18000b06a  mov     [r11-30h], rax
0x18000b06e  mov     qword ptr [r11-68h], 5
0x18000b076  movdqu  [rsp+118h+var_98], xmm0
0x18000b07f  xorps   xmm1, xmm1
0x18000b082  movdqu  [rsp+118h+var_88], xmm1
0x18000b08b  mov     [r11-78h], rdi
0x18000b08f  mov     qword ptr [rsp+118h+Security+4], rdi
0x18000b094  mov     dword ptr [rsp+118h+Security.ServerPrincName+4], edi
0x18000b098  mov     [rsp+118h+Security.AuthIdentity], rdi
0x18000b09d  mov     dword ptr [r11-60h], 1
0x18000b0a5  mov     dword ptr [r11-58h], 3
0x18000b0ad  mov     dword ptr [r11-70h], 1
0x18000b0b5  mov     dword ptr [r11-6Ch], 1
0x18000b0bd  mov     [rsp+118h+var_A8], 5
0x18000b0c6  mov     [rsp+118h+var_A0], 1
0x18000b0ce  mov     [rsp+118h+var_9C], 3
0x18000b0d6  mov     [rsp+118h+Security.Version], 1
0x18000b0de  mov     [rsp+118h+Security.AuthnLevel], 6
0x18000b0e6  mov     [rsp+118h+Security.AuthnSvc], 0Ah
0x18000b0ee  lea     rax, [rsp+118h+var_A8]
0x18000b0f3  mov     [rsp+118h+Security.SecurityQos], rax
0x18000b0f8  lea     r9, [rsp+118h+Binding]; Binding
0x18000b0fd  lea     r8, [r11-70h]; Options
0x18000b101  lea     rdx, [rsp+118h+Security]; Security
0x18000b106  lea     rcx, [r11-60h]; Template
0x18000b10a  call    cs:__imp_RpcBindingCreateW
0x18000b110  mov     ebx, eax
0x18000b112  test    eax, eax
0x18000b114  jnz     loc_18000B1DE
0x18000b11a  lea     r8, qword_18001DBC0; IfSpec
0x18000b121  mov     rdx, [rsp+118h+Binding]; Binding
0x18000b126  xor     ecx, ecx; pAsync
0x18000b128  call    cs:__imp_RpcBindingBind
0x18000b12e  mov     ebx, eax
0x18000b130  test    eax, eax
0x18000b132  jnz     loc_18000B1F2
0x18000b138  mov     rax, [rsp+118h+Binding]
0x18000b13d  mov     [rsp+118h+var_E0], rax
0x18000b142  mov     [rsp+118h+Binding], rdi
0x18000b147  mov     ebx, edi
0x18000b149  cmp     [rsp+118h+Binding], rdi
0x18000b14e  jnz     loc_18000B206
0x18000b154  test    ebx, ebx
0x18000b156  js      short loc_18000B1A5
0x18000b158  mov     [rsp+118h+Binding], rdi
0x18000b15d  mov     [rsp+118h+var_F0], r14
0x18000b162  mov     [rsp+118h+var_F8], rsi
0x18000b167  mov     r9, [rsp+118h+var_E0]
0x18000b16c  xor     r8d, r8d; pReturnValue
0x18000b16f  mov     edx, 1; nProcNum
0x18000b174  lea     rcx, stru_18001DC20; pProxyInfo
0x18000b17b  call    cs:__imp_NdrClientCall3
0x18000b181  mov     rbx, rax
0x18000b184  mov     [rsp+118h+Binding], rax
0x18000b189  mov     [rsp+118h+var_D8], eax
0x18000b18d  jmp     short loc_18000B19F
0x18000b18f  mov     ecx, eax; Status
0x18000b191  call    cs:__imp_I_RpcMapWin32Status
0x18000b197  mov     ebx, eax
0x18000b199  mov     [rsp+118h+var_D8], eax
0x18000b19d  xor     edi, edi
0x18000b19f  test    ebx, ebx
0x18000b1a1  js      short loc_18000B1A5
0x18000b1a3  mov     ebx, edi
0x18000b1a5  cmp     [rsp+118h+var_E0], 0
0x18000b1ab  jz      short loc_18000B1B8
0x18000b1ad  lea     rcx, [rsp+118h+var_E0]; Binding
0x18000b1b2  call    cs:__imp_RpcBindingFree
0x18000b1b8  mov     eax, ebx
0x18000b1ba  mov     rcx, [rsp+118h+var_28]
0x18000b1c2  xor     rcx, rsp; StackCookie
0x18000b1c5  call    __security_check_cookie
0x18000b1ca  mov     rbx, [rsp+118h+arg_10]
0x18000b1d2  add     rsp, 100h
0x18000b1d9  pop     r14
0x18000b1db  pop     rdi
0x18000b1dc  pop     rsi
0x18000b1dd  retn
0x18000b1de  jle     loc_18000B149
0x18000b1e4  movzx   ebx, ax
0x18000b1e7  or      ebx, 0C0070000h
0x18000b1ed  jmp     loc_18000B149
0x18000b1f2  jle     loc_18000B149
0x18000b1f8  movzx   ebx, ax
0x18000b1fb  or      ebx, 0C0070000h
0x18000b201  jmp     loc_18000B149
0x18000b206  lea     rcx, [rsp+118h+Binding]; Binding
0x18000b20b  call    cs:__imp_RpcBindingFree
0x18000b211  jmp     loc_18000B154
0x18001b2c0  push    rbp
0x18001b2c2  sub     rsp, 30h
0x18001b2c6  mov     rbp, rdx
0x18001b2c9  mov     rcx, [rcx]
0x18001b2cc  mov     ecx, [rcx]; ExceptionCode
0x18001b2ce  call    cs:__imp_RpcExceptionFilter
0x18001b2d4  nop
0x18001b2d5  add     rsp, 30h
0x18001b2d9  pop     rbp
0x18001b2da  retn
```
