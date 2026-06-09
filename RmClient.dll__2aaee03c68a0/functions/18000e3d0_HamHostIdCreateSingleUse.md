# HamHostIdCreateSingleUse

- ea: `0x18000e3d0`
- end: `0x18000e59a`
- name: `HamHostIdCreateSingleUse`
- size: `458`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e3d0`
- `0x18001aec0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000e549`
- `RPCRT4!NdrClientCall3` at `0x18000e549`
- `RPCRT4!RpcBindingCreateW` at `0x18000e4a1`
- `RPCRT4!RpcBindingCreateW` at `0x18000e4a1`
- `RPCRT4!RpcBindingBind` at `0x18000e4bf`
- `RPCRT4!RpcBindingBind` at `0x18000e4bf`
- `RPCRT4!RpcBindingFree` at `0x18000e4ff`
- `RPCRT4!RpcBindingFree` at `0x18000e58f`
- `RPCRT4!RpcBindingFree` at `0x18000e4ff`
- `RPCRT4!RpcBindingFree` at `0x18000e58f`
- `RPCRT4!RpcExceptionFilter` at `0x18001b4a2`
- `RPCRT4!RpcExceptionFilter` at `0x18001b4a2`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000e55f`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000e55f`

## pseudocode

```c
__int64 __fastcall HamHostIdCreateSingleUse(__int64 a1)
{
  RPC_STATUS v2; // eax
  signed int Pointer; // ebx
  bool v4; // cc
  CLIENT_CALL_RETURN v6; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+30h] [rbp-D8h] BYREF
  RPC_BINDING_HANDLE v8; // [rsp+38h] [rbp-D0h] BYREF
  int v9; // [rsp+40h] [rbp-C8h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v11[2]; // [rsp+70h] [rbp-98h] BYREF
  __int128 v12; // [rsp+80h] [rbp-88h]
  __int128 v13; // [rsp+90h] [rbp-78h]
  __int64 v14; // [rsp+A0h] [rbp-68h]
  RPC_BINDING_HANDLE_OPTIONS_V1 v15; // [rsp+A8h] [rbp-60h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W v16; // [rsp+B8h] [rbp-50h] BYREF

  v8 = 0;
  Binding = 0;
  memset(&v16, 0, sizeof(v16));
  *(_QWORD *)&v15.ComTimeout = 5;
  v12 = 0;
  v13 = 0;
  v14 = 0;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  v16.Version = 1;
  v16.ProtocolSequence = 3;
  *(_QWORD *)&v15.Version = 0x100000001LL;
  v11[0] = 5;
  v11[1] = 0x300000001LL;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v11;
  v2 = RpcBindingCreateW(&v16, &Security, &v15, &Binding);
  Pointer = v2;
  v4 = v2 <= 0;
  if ( v2 || (v2 = RpcBindingBind(0, Binding, qword_18001DBC0), Pointer = v2, v4 = v2 <= 0, v2) )
  {
    if ( !v4 )
      Pointer = (unsigned __int16)v2 | 0xC0070000;
  }
  else
  {
    v8 = Binding;
    Binding = 0;
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( Pointer >= 0 )
  {
    Binding = 0;
    v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DC20, 2u, 0, v8, a1).Pointer;
    Pointer = (signed int)v6.Pointer;
    Binding = (RPC_BINDING_HANDLE)v6.Simple;
    v9 = (int)v6.Pointer;
    if ( SLODWORD(v6.Simple) >= 0 )
      Pointer = 0;
  }
  if ( v8 )
    RpcBindingFree(&v8);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x18000e3d0  mov     r11, rsp
0x18000e3d3  mov     [r11+10h], rbx
0x18000e3d7  push    rsi
0x18000e3d8  sub     rsp, 100h
0x18000e3df  mov     rax, cs:__security_cookie
0x18000e3e6  xor     rax, rsp
0x18000e3e9  mov     [rsp+108h+var_18], rax
0x18000e3f1  mov     rsi, rcx
0x18000e3f4  mov     [rsp+108h+var_D0], 0
0x18000e3fd  mov     [rsp+108h+Binding], 0
0x18000e406  xorps   xmm0, xmm0
0x18000e409  xor     eax, eax
0x18000e40b  movups  xmmword ptr [r11-50h], xmm0
0x18000e410  movups  xmmword ptr [r11-40h], xmm0
0x18000e415  movups  xmmword ptr [r11-30h], xmm0
0x18000e41a  mov     [r11-20h], rax
0x18000e41e  mov     qword ptr [r11-58h], 5
0x18000e426  movups  [rsp+108h+var_98], xmm0
0x18000e42b  movups  [rsp+108h+var_88], xmm0
0x18000e433  movups  xmmword ptr [r11-78h], xmm0
0x18000e438  mov     [r11-68h], rax
0x18000e43c  mov     qword ptr [rsp+108h+Security+4], rax
0x18000e441  mov     dword ptr [rsp+108h+Security.ServerPrincName+4], eax
0x18000e445  mov     [rsp+108h+Security.AuthIdentity], rax
0x18000e44a  lea     edx, [rax+1]
0x18000e44d  mov     [r11-50h], edx
0x18000e451  lea     ecx, [rax+3]
0x18000e454  mov     [r11-48h], ecx
0x18000e458  mov     [r11-60h], edx
0x18000e45c  mov     [r11-5Ch], edx
0x18000e460  mov     qword ptr [rsp+108h+var_98], 5
0x18000e469  mov     dword ptr [rsp+108h+var_98+8], edx
0x18000e46d  mov     dword ptr [rsp+108h+var_98+0Ch], ecx
0x18000e471  mov     [rsp+108h+Security.Version], edx
0x18000e475  mov     [rsp+108h+Security.AuthnLevel], 6
0x18000e47d  mov     [rsp+108h+Security.AuthnSvc], 0Ah
0x18000e485  lea     rax, [rsp+108h+var_98]
0x18000e48a  mov     [rsp+108h+Security.SecurityQos], rax
0x18000e48f  lea     r9, [rsp+108h+Binding]; Binding
0x18000e494  lea     r8, [r11-60h]; Options
0x18000e498  lea     rdx, [rsp+108h+Security]; Security
0x18000e49d  lea     rcx, [r11-50h]; Template
0x18000e4a1  call    cs:__imp_RpcBindingCreateW
0x18000e4a7  mov     ebx, eax
0x18000e4a9  test    eax, eax
0x18000e4ab  jnz     loc_18000E576
0x18000e4b1  lea     r8, qword_18001DBC0; IfSpec
0x18000e4b8  mov     rdx, [rsp+108h+Binding]; Binding
0x18000e4bd  xor     ecx, ecx; pAsync
0x18000e4bf  call    cs:__imp_RpcBindingBind
0x18000e4c5  mov     ebx, eax
0x18000e4c7  test    eax, eax
0x18000e4c9  jnz     loc_18000E576
0x18000e4cf  mov     rax, [rsp+108h+Binding]
0x18000e4d4  mov     [rsp+108h+var_D0], rax
0x18000e4d9  mov     [rsp+108h+Binding], 0
0x18000e4e2  cmp     [rsp+108h+Binding], 0
0x18000e4e8  jnz     loc_18000E58A
0x18000e4ee  test    ebx, ebx
0x18000e4f0  jns     short loc_18000E528
0x18000e4f2  cmp     [rsp+108h+var_D0], 0
0x18000e4f8  jz      short loc_18000E505
0x18000e4fa  lea     rcx, [rsp+108h+var_D0]; Binding
0x18000e4ff  call    cs:__imp_RpcBindingFree
0x18000e505  mov     eax, ebx
0x18000e507  mov     rcx, [rsp+108h+var_18]
0x18000e50f  xor     rcx, rsp; StackCookie
0x18000e512  call    __security_check_cookie
0x18000e517  mov     rbx, [rsp+108h+arg_8]
0x18000e51f  add     rsp, 100h
0x18000e526  pop     rsi
0x18000e527  retn
0x18000e528  mov     [rsp+108h+Binding], 0
0x18000e531  mov     [rsp+108h+var_E8], rsi
0x18000e536  mov     r9, [rsp+108h+var_D0]
0x18000e53b  xor     r8d, r8d; pReturnValue
0x18000e53e  lea     edx, [r8+2]; nProcNum
0x18000e542  lea     rcx, stru_18001DC20; pProxyInfo
0x18000e549  call    cs:__imp_NdrClientCall3
0x18000e54f  mov     rbx, rax
0x18000e552  mov     [rsp+108h+Binding], rax
0x18000e557  mov     [rsp+108h+var_C8], eax
0x18000e55b  jmp     short loc_18000E56B
0x18000e55d  mov     ecx, eax; Status
0x18000e55f  call    cs:__imp_I_RpcMapWin32Status
0x18000e565  mov     ebx, eax
0x18000e567  mov     [rsp+108h+var_C8], eax
0x18000e56b  test    ebx, ebx
0x18000e56d  js      short loc_18000E4F2
0x18000e56f  xor     ebx, ebx
0x18000e571  jmp     loc_18000E4F2
0x18000e576  jle     loc_18000E4E2
0x18000e57c  movzx   ebx, ax
0x18000e57f  or      ebx, 0C0070000h
0x18000e585  jmp     loc_18000E4E2
0x18000e58a  lea     rcx, [rsp+108h+Binding]; Binding
0x18000e58f  call    cs:__imp_RpcBindingFree
0x18000e595  jmp     loc_18000E4EE
0x18001b494  push    rbp
0x18001b496  sub     rsp, 30h
0x18001b49a  mov     rbp, rdx
0x18001b49d  mov     rcx, [rcx]
0x18001b4a0  mov     ecx, [rcx]; ExceptionCode
0x18001b4a2  call    cs:__imp_RpcExceptionFilter
0x18001b4a8  nop
0x18001b4a9  add     rsp, 30h
0x18001b4ad  pop     rbp
0x18001b4ae  retn
```
