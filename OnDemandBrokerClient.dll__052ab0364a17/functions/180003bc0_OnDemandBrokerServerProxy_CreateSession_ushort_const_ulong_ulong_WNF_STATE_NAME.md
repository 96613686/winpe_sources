# OnDemandBrokerServerProxy::CreateSession(ushort const *,ulong,ulong *,_WNF_STATE_NAME *)

- ea: `0x180003bc0`
- end: `0x180003de2`
- name: `?CreateSession@OnDemandBrokerServerProxy@@UEAAJPEBGKPEAKPEAU_WNF_STATE_NAME@@@Z`
- size: `546`
- prototype: `__int64 __fastcall(OnDemandBrokerServerProxy *this, const unsigned __int16 *, int, unsigned int *, struct _WNF_STATE_NAME *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003bc0`
- `0x180006570`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x180003dbb`
- `RPCRT4!I_RpcMapWin32Status` at `0x180003dbb`
- `RPCRT4!RpcBindingFree` at `0x180003d89`
- `RPCRT4!RpcBindingFree` at `0x180003dd7`
- `RPCRT4!RpcBindingFree` at `0x180003d89`
- `RPCRT4!RpcBindingFree` at `0x180003dd7`
- `RPCRT4!RpcBindingCreateW` at `0x180003cf2`
- `RPCRT4!RpcBindingCreateW` at `0x180003cf2`
- `RPCRT4!NdrClientCall3` at `0x180003d56`
- `RPCRT4!NdrClientCall3` at `0x180003d56`
- `RPCRT4!RpcBindingBind` at `0x180003d0e`
- `RPCRT4!RpcBindingBind` at `0x180003d0e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000674e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000674e`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerServerProxy::CreateSession(
        OnDemandBrokerServerProxy *this,
        const unsigned __int16 *a2,
        int a3,
        unsigned int *a4,
        struct _WNF_STATE_NAME *a5)
{
  RPC_STATUS v8; // eax
  int Pointer; // ebx
  CLIENT_CALL_RETURN v10; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-F8h] BYREF
  RPC_BINDING_HANDLE v13; // [rsp+48h] [rbp-F0h] BYREF
  int v14; // [rsp+50h] [rbp-E8h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+58h] [rbp-E0h] BYREF
  _DWORD v16[4]; // [rsp+80h] [rbp-B8h] BYREF
  __int128 v17; // [rsp+90h] [rbp-A8h]
  _DWORD *v18; // [rsp+A0h] [rbp-98h]
  _DWORD v19[4]; // [rsp+A8h] [rbp-90h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 v20; // [rsp+B8h] [rbp-80h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W v21; // [rsp+C8h] [rbp-70h] BYREF

  v13 = 0;
  *(_QWORD *)&v20.ComTimeout = 5;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  v17 = 0;
  memset(&v21, 0, sizeof(v21));
  v19[0] = 257;
  v19[1] = 83886080;
  v19[2] = 18;
  Binding = 0;
  v21.Version = 1;
  v21.ProtocolSequence = 3;
  *(_QWORD *)&v20.Version = 0x100000001LL;
  v16[0] = 3;
  v16[1] = 1;
  v16[2] = 1;
  v16[3] = 3;
  v18 = v19;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v16;
  v8 = RpcBindingCreateW(&v21, &Security, &v20, &Binding);
  if ( v8 || (v8 = RpcBindingBind(0, Binding, qword_180008360)) != 0 )
  {
    Pointer = I_RpcMapWin32Status(v8) | 0x10000000;
    if ( Binding )
      RpcBindingFree(&Binding);
  }
  else
  {
    Pointer = 0;
    v13 = Binding;
  }
  if ( Pointer >= 0 )
  {
    v10.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800083C0, 0, 0, v13, a2, a3, a4, a5, 0).Pointer;
    Pointer = (int)v10.Pointer;
    Binding = (RPC_BINDING_HANDLE)v10.Simple;
    v14 = (int)v10.Pointer;
  }
  if ( v13 )
    RpcBindingFree(&v13);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180003bc0  mov     r11, rsp
0x180003bc3  mov     [r11+8], rbx
0x180003bc7  push    rsi
0x180003bc8  push    rdi
0x180003bc9  push    r12
0x180003bcb  push    r14
0x180003bcd  push    r15
0x180003bcf  sub     rsp, 110h
0x180003bd6  mov     rax, cs:__security_cookie
0x180003bdd  xor     rax, rsp
0x180003be0  mov     [rsp+138h+var_38], rax
0x180003be8  mov     r14, r9
0x180003beb  mov     esi, r8d
0x180003bee  mov     rdi, rdx
0x180003bf1  mov     r15, [rsp+138h+arg_20]
0x180003bf9  xor     r12d, r12d
0x180003bfc  mov     [rsp+138h+var_F0], r12
0x180003c01  mov     qword ptr [r11-78h], 5
0x180003c09  mov     qword ptr [rsp+138h+Security+4], r12
0x180003c0e  mov     dword ptr [rsp+138h+Security.ServerPrincName+4], r12d
0x180003c13  mov     [rsp+138h+Security.AuthIdentity], r12
0x180003c18  xorps   xmm0, xmm0
0x180003c1b  movdqu  [rsp+138h+var_A8], xmm0
0x180003c24  xorps   xmm1, xmm1
0x180003c27  xor     eax, eax
0x180003c29  movups  xmmword ptr [r11-70h], xmm1
0x180003c2e  movups  xmmword ptr [r11-60h], xmm1
0x180003c33  movups  xmmword ptr [r11-50h], xmm1
0x180003c38  mov     [r11-40h], rax
0x180003c3c  mov     [rsp+138h+var_90], 101h
0x180003c47  mov     [rsp+138h+var_8C], 5000000h
0x180003c52  mov     [rsp+138h+var_88], 12h
0x180003c5d  mov     [rsp+138h+Binding], r12
0x180003c62  mov     dword ptr [r11-70h], 1
0x180003c6a  mov     dword ptr [r11-68h], 3
0x180003c72  mov     dword ptr [r11-80h], 1
0x180003c7a  mov     dword ptr [r11-7Ch], 1
0x180003c82  mov     [rsp+138h+var_B8], 3
0x180003c8d  mov     [rsp+138h+var_B4], 1
0x180003c98  mov     [rsp+138h+var_B0], 1
0x180003ca3  mov     [rsp+138h+var_AC], 3
0x180003cae  lea     rax, [r11-90h]
0x180003cb5  mov     [r11-98h], rax
0x180003cbc  mov     [rsp+138h+Security.Version], 1
0x180003cc4  mov     [rsp+138h+Security.AuthnLevel], 6
0x180003ccc  mov     [rsp+138h+Security.AuthnSvc], 14h
0x180003cd4  lea     rax, [r11-0B8h]
0x180003cdb  mov     [rsp+138h+Security.SecurityQos], rax
0x180003ce0  lea     r9, [rsp+138h+Binding]; Binding
0x180003ce5  lea     r8, [r11-80h]; Options
0x180003ce9  lea     rdx, [rsp+138h+Security]; Security
0x180003cee  lea     rcx, [r11-70h]; Template
0x180003cf2  call    cs:__imp_RpcBindingCreateW
0x180003cf8  test    eax, eax
0x180003cfa  jnz     loc_180003DB9
0x180003d00  lea     r8, qword_180008360; IfSpec
0x180003d07  mov     rdx, [rsp+138h+Binding]; Binding
0x180003d0c  xor     ecx, ecx; pAsync
0x180003d0e  call    cs:__imp_RpcBindingBind
0x180003d14  test    eax, eax
0x180003d16  jnz     loc_180003DB9
0x180003d1c  mov     ebx, r12d
0x180003d1f  mov     rax, [rsp+138h+Binding]
0x180003d24  mov     [rsp+138h+var_F0], rax
0x180003d29  test    ebx, ebx
0x180003d2b  js      short loc_180003D7C
0x180003d2d  mov     [rsp+138h+Binding], r12
0x180003d32  mov     [rsp+138h+var_100], r15
0x180003d37  mov     [rsp+138h+var_108], r14
0x180003d3c  mov     [rsp+138h+var_110], esi
0x180003d40  mov     [rsp+138h+var_118], rdi
0x180003d45  mov     r9, [rsp+138h+var_F0]
0x180003d4a  xor     r8d, r8d; pReturnValue
0x180003d4d  xor     edx, edx; nProcNum
0x180003d4f  lea     rcx, stru_1800083C0; pProxyInfo
0x180003d56  call    cs:__imp_NdrClientCall3
0x180003d5c  mov     rbx, rax
0x180003d5f  mov     [rsp+138h+Binding], rax
0x180003d64  mov     [rsp+138h+var_E8], eax
0x180003d68  jmp     short loc_180003D7C
0x180003d6a  test    eax, eax
0x180003d6c  jle     short loc_180003D76
0x180003d6e  movzx   eax, ax
0x180003d71  or      eax, 80070000h
0x180003d76  mov     ebx, eax
0x180003d78  mov     [rsp+138h+var_E8], eax
0x180003d7c  cmp     [rsp+138h+var_F0], 0
0x180003d82  jz      short loc_180003D8F
0x180003d84  lea     rcx, [rsp+138h+var_F0]; Binding
0x180003d89  call    cs:__imp_RpcBindingFree
0x180003d8f  mov     eax, ebx
0x180003d91  mov     rcx, [rsp+138h+var_38]
0x180003d99  xor     rcx, rsp; StackCookie
0x180003d9c  call    __security_check_cookie
0x180003da1  mov     rbx, [rsp+138h+arg_0]
0x180003da9  add     rsp, 110h
0x180003db0  pop     r15
0x180003db2  pop     r14
0x180003db4  pop     r12
0x180003db6  pop     rdi
0x180003db7  pop     rsi
0x180003db8  retn
0x180003db9  mov     ecx, eax; Status
0x180003dbb  call    cs:__imp_I_RpcMapWin32Status
0x180003dc1  mov     ebx, eax
0x180003dc3  bts     ebx, 1Ch
0x180003dc7  cmp     [rsp+138h+Binding], r12
0x180003dcc  jz      loc_180003D29
0x180003dd2  lea     rcx, [rsp+138h+Binding]; Binding
0x180003dd7  call    cs:__imp_RpcBindingFree
0x180003ddd  jmp     loc_180003D29
0x180006740  push    rbp
0x180006742  sub     rsp, 40h
0x180006746  mov     rbp, rdx
0x180006749  mov     rcx, [rcx]
0x18000674c  mov     ecx, [rcx]; ExceptionCode
0x18000674e  call    cs:__imp_I_RpcExceptionFilter
0x180006754  nop
0x180006755  add     rsp, 40h
0x180006759  pop     rbp
0x18000675a  retn
```
