# OnDemandBrokerServerProxy::CompleteSession(void *,ulong)

- ea: `0x180003250`
- end: `0x180003459`
- name: `?CompleteSession@OnDemandBrokerServerProxy@@UEAAJPEAXK@Z`
- size: `521`
- prototype: `__int64 __fastcall(OnDemandBrokerServerProxy *this, void *, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003250`
- `0x180006570`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x180003432`
- `RPCRT4!I_RpcMapWin32Status` at `0x180003432`
- `RPCRT4!RpcBindingFree` at `0x180003404`
- `RPCRT4!RpcBindingFree` at `0x18000344e`
- `RPCRT4!RpcBindingFree` at `0x180003404`
- `RPCRT4!RpcBindingFree` at `0x18000344e`
- `RPCRT4!RpcBindingCreateW` at `0x180003367`
- `RPCRT4!RpcBindingCreateW` at `0x180003367`
- `RPCRT4!NdrClientCall3` at `0x1800033d1`
- `RPCRT4!NdrClientCall3` at `0x1800033d1`
- `RPCRT4!RpcBindingBind` at `0x180003383`
- `RPCRT4!RpcBindingBind` at `0x180003383`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800066be`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800066be`
- `ntdll!RtlLengthSid` at `0x1800033a5`
- `ntdll!RtlLengthSid` at `0x1800033a5`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerServerProxy::CompleteSession(OnDemandBrokerServerProxy *this, void *a2, int a3)
{
  RPC_STATUS v5; // eax
  int Pointer; // ebx
  ULONG v7; // eax
  CLIENT_CALL_RETURN v8; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-E8h] BYREF
  RPC_BINDING_HANDLE v11; // [rsp+48h] [rbp-E0h] BYREF
  int v12; // [rsp+50h] [rbp-D8h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+58h] [rbp-D0h] BYREF
  _DWORD v14[4]; // [rsp+80h] [rbp-A8h] BYREF
  __int128 v15; // [rsp+90h] [rbp-98h]
  _DWORD *v16; // [rsp+A0h] [rbp-88h]
  _DWORD v17[4]; // [rsp+A8h] [rbp-80h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 v18; // [rsp+B8h] [rbp-70h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W v19; // [rsp+C8h] [rbp-60h] BYREF

  v11 = 0;
  *(_QWORD *)&v18.ComTimeout = 5;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  v15 = 0;
  memset(&v19, 0, sizeof(v19));
  v17[0] = 257;
  v17[1] = 83886080;
  v17[2] = 18;
  Binding = 0;
  v19.Version = 1;
  v19.ProtocolSequence = 3;
  *(_QWORD *)&v18.Version = 0x100000001LL;
  v14[0] = 3;
  v14[1] = 1;
  v14[2] = 1;
  v14[3] = 3;
  v16 = v17;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v14;
  v5 = RpcBindingCreateW(&v19, &Security, &v18, &Binding);
  if ( v5 || (v5 = RpcBindingBind(0, Binding, qword_180008210)) != 0 )
  {
    Pointer = I_RpcMapWin32Status(v5) | 0x10000000;
    if ( Binding )
      RpcBindingFree(&Binding);
  }
  else
  {
    Pointer = 0;
    v11 = Binding;
  }
  if ( Pointer >= 0 )
  {
    v7 = RtlLengthSid(a2);
    Binding = 0;
    v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 1u, 0, v11, v7, a2, a3).Pointer;
    Pointer = (int)v8.Pointer;
    Binding = (RPC_BINDING_HANDLE)v8.Simple;
    v12 = (int)v8.Pointer;
  }
  if ( v11 )
    RpcBindingFree(&v11);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180003250  mov     r11, rsp
0x180003253  mov     [r11+8], rbx
0x180003257  push    rsi
0x180003258  push    rdi
0x180003259  push    r14
0x18000325b  sub     rsp, 110h
0x180003262  mov     rax, cs:__security_cookie
0x180003269  xor     rax, rsp
0x18000326c  mov     [rsp+128h+var_28], rax
0x180003274  mov     esi, r8d
0x180003277  mov     rdi, rdx
0x18000327a  xor     r14d, r14d
0x18000327d  mov     [rsp+128h+var_E0], r14
0x180003282  mov     qword ptr [r11-68h], 5
0x18000328a  mov     qword ptr [rsp+128h+Security+4], r14
0x18000328f  mov     dword ptr [rsp+128h+Security.ServerPrincName+4], r14d
0x180003294  mov     [rsp+128h+Security.AuthIdentity], r14
0x180003299  xorps   xmm0, xmm0
0x18000329c  movdqu  [rsp+128h+var_98], xmm0
0x1800032a5  xorps   xmm1, xmm1
0x1800032a8  xor     eax, eax
0x1800032aa  movups  xmmword ptr [r11-60h], xmm1
0x1800032af  movups  xmmword ptr [r11-50h], xmm1
0x1800032b4  movups  xmmword ptr [r11-40h], xmm1
0x1800032b9  mov     [r11-30h], rax
0x1800032bd  mov     dword ptr [r11-80h], 101h
0x1800032c5  mov     dword ptr [r11-7Ch], 5000000h
0x1800032cd  mov     dword ptr [r11-78h], 12h
0x1800032d5  mov     [rsp+128h+Binding], r14
0x1800032da  mov     dword ptr [r11-60h], 1
0x1800032e2  mov     dword ptr [r11-58h], 3
0x1800032ea  mov     dword ptr [r11-70h], 1
0x1800032f2  mov     dword ptr [r11-6Ch], 1
0x1800032fa  mov     [rsp+128h+var_A8], 3
0x180003305  mov     [rsp+128h+var_A4], 1
0x180003310  mov     [rsp+128h+var_A0], 1
0x18000331b  mov     [rsp+128h+var_9C], 3
0x180003326  lea     rax, [r11-80h]
0x18000332a  mov     [r11-88h], rax
0x180003331  mov     [rsp+128h+Security.Version], 1
0x180003339  mov     [rsp+128h+Security.AuthnLevel], 6
0x180003341  mov     [rsp+128h+Security.AuthnSvc], 14h
0x180003349  lea     rax, [r11-0A8h]
0x180003350  mov     [rsp+128h+Security.SecurityQos], rax
0x180003355  lea     r9, [rsp+128h+Binding]; Binding
0x18000335a  lea     r8, [r11-70h]; Options
0x18000335e  lea     rdx, [rsp+128h+Security]; Security
0x180003363  lea     rcx, [r11-60h]; Template
0x180003367  call    cs:__imp_RpcBindingCreateW
0x18000336d  test    eax, eax
0x18000336f  jnz     loc_180003430
0x180003375  lea     r8, qword_180008210; IfSpec
0x18000337c  mov     rdx, [rsp+128h+Binding]; Binding
0x180003381  xor     ecx, ecx; pAsync
0x180003383  call    cs:__imp_RpcBindingBind
0x180003389  test    eax, eax
0x18000338b  jnz     loc_180003430
0x180003391  mov     ebx, r14d
0x180003394  mov     rax, [rsp+128h+Binding]
0x180003399  mov     [rsp+128h+var_E0], rax
0x18000339e  test    ebx, ebx
0x1800033a0  js      short loc_1800033F7
0x1800033a2  mov     rcx, rdi; Sid
0x1800033a5  call    cs:__imp_RtlLengthSid
0x1800033ab  mov     [rsp+128h+Binding], r14
0x1800033b0  mov     [rsp+128h+var_F8], esi
0x1800033b4  mov     [rsp+128h+var_100], rdi
0x1800033b9  mov     [rsp+128h+var_108], eax
0x1800033bd  mov     r9, [rsp+128h+var_E0]
0x1800033c2  xor     r8d, r8d; pReturnValue
0x1800033c5  mov     edx, 1; nProcNum
0x1800033ca  lea     rcx, pProxyInfo; pProxyInfo
0x1800033d1  call    cs:__imp_NdrClientCall3
0x1800033d7  mov     rbx, rax
0x1800033da  mov     [rsp+128h+Binding], rax
0x1800033df  mov     [rsp+128h+var_D8], eax
0x1800033e3  jmp     short loc_1800033F7
0x1800033e5  test    eax, eax
0x1800033e7  jle     short loc_1800033F1
0x1800033e9  movzx   eax, ax
0x1800033ec  or      eax, 80070000h
0x1800033f1  mov     ebx, eax
0x1800033f3  mov     [rsp+128h+var_D8], eax
0x1800033f7  cmp     [rsp+128h+var_E0], 0
0x1800033fd  jz      short loc_18000340A
0x1800033ff  lea     rcx, [rsp+128h+var_E0]; Binding
0x180003404  call    cs:__imp_RpcBindingFree
0x18000340a  mov     eax, ebx
0x18000340c  mov     rcx, [rsp+128h+var_28]
0x180003414  xor     rcx, rsp; StackCookie
0x180003417  call    __security_check_cookie
0x18000341c  mov     rbx, [rsp+128h+arg_0]
0x180003424  add     rsp, 110h
0x18000342b  pop     r14
0x18000342d  pop     rdi
0x18000342e  pop     rsi
0x18000342f  retn
0x180003430  mov     ecx, eax; Status
0x180003432  call    cs:__imp_I_RpcMapWin32Status
0x180003438  mov     ebx, eax
0x18000343a  bts     ebx, 1Ch
0x18000343e  cmp     [rsp+128h+Binding], r14
0x180003443  jz      loc_18000339E
0x180003449  lea     rcx, [rsp+128h+Binding]; Binding
0x18000344e  call    cs:__imp_RpcBindingFree
0x180003454  jmp     loc_18000339E
0x1800066b0  push    rbp
0x1800066b2  sub     rsp, 40h
0x1800066b6  mov     rbp, rdx
0x1800066b9  mov     rcx, [rcx]
0x1800066bc  mov     ecx, [rcx]; ExceptionCode
0x1800066be  call    cs:__imp_I_RpcExceptionFilter
0x1800066c4  nop
0x1800066c5  add     rsp, 40h
0x1800066c9  pop     rbp
0x1800066ca  retn
```
