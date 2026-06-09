# OnDemandBrokerServerProxy::CreateSession(void *,ushort const *,ulong,ulong *,_WNF_STATE_NAME *)

- ea: `0x180002e80`
- end: `0x1800030c7`
- name: `?CreateSession@OnDemandBrokerServerProxy@@UEAAJPEAXPEBGKPEAKPEAU_WNF_STATE_NAME@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(OnDemandBrokerServerProxy *this, void *, const unsigned __int16 *, int, unsigned int *, struct _WNF_STATE_NAME *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002e80`
- `0x180006570`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x1800030a0`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800030a0`
- `RPCRT4!RpcBindingFree` at `0x180003073`
- `RPCRT4!RpcBindingFree` at `0x1800030bc`
- `RPCRT4!RpcBindingFree` at `0x180003073`
- `RPCRT4!RpcBindingFree` at `0x1800030bc`
- `RPCRT4!RpcBindingCreateW` at `0x180002fc9`
- `RPCRT4!RpcBindingCreateW` at `0x180002fc9`
- `RPCRT4!NdrClientCall3` at `0x180003040`
- `RPCRT4!NdrClientCall3` at `0x180003040`
- `RPCRT4!RpcBindingBind` at `0x180002fe5`
- `RPCRT4!RpcBindingBind` at `0x180002fe5`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000668e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000668e`
- `ntdll!RtlLengthSid` at `0x180003007`
- `ntdll!RtlLengthSid` at `0x180003007`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerServerProxy::CreateSession(
        OnDemandBrokerServerProxy *this,
        void *a2,
        const unsigned __int16 *a3,
        int a4,
        unsigned int *a5,
        struct _WNF_STATE_NAME *a6)
{
  RPC_STATUS v9; // eax
  int Pointer; // ebx
  CLIENT_CALL_RETURN v11; // rax
  ULONG v13; // [rsp+20h] [rbp-138h]
  RPC_BINDING_HANDLE Binding; // [rsp+50h] [rbp-108h] BYREF
  RPC_BINDING_HANDLE v15; // [rsp+58h] [rbp-100h] BYREF
  int v16; // [rsp+60h] [rbp-F8h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+68h] [rbp-F0h] BYREF
  _DWORD v18[4]; // [rsp+90h] [rbp-C8h] BYREF
  __int128 v19; // [rsp+A0h] [rbp-B8h]
  _DWORD *v20; // [rsp+B0h] [rbp-A8h]
  _DWORD v21[4]; // [rsp+B8h] [rbp-A0h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 v22; // [rsp+C8h] [rbp-90h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W v23; // [rsp+D8h] [rbp-80h] BYREF

  v15 = 0;
  *(_QWORD *)&v22.ComTimeout = 5;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  v19 = 0;
  memset(&v23, 0, sizeof(v23));
  v21[0] = 257;
  v21[1] = 83886080;
  v21[2] = 18;
  Binding = 0;
  v23.Version = 1;
  v23.ProtocolSequence = 3;
  v22.Version = 1;
  v22.Flags = 1;
  v18[0] = 3;
  v18[1] = 1;
  v18[2] = 1;
  v18[3] = 3;
  v20 = v21;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v18;
  v9 = RpcBindingCreateW(&v23, &Security, &v22, &Binding);
  if ( v9 || (v9 = RpcBindingBind(0, Binding, qword_180008210)) != 0 )
  {
    Pointer = I_RpcMapWin32Status(v9) | 0x10000000;
    if ( Binding )
      RpcBindingFree(&Binding);
  }
  else
  {
    Pointer = 0;
    v15 = Binding;
  }
  if ( Pointer >= 0 )
  {
    v13 = RtlLengthSid(a2);
    v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, v15, v13, a2, a3, a4, a5, a6, 0).Pointer;
    Pointer = (int)v11.Pointer;
    Binding = (RPC_BINDING_HANDLE)v11.Simple;
    v16 = (int)v11.Pointer;
  }
  if ( v15 )
    RpcBindingFree(&v15);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002e80  mov     r11, rsp
0x180002e83  push    rbx
0x180002e84  push    rsi
0x180002e85  push    rdi
0x180002e86  push    r12
0x180002e88  push    r13
0x180002e8a  push    r14
0x180002e8c  push    r15
0x180002e8e  sub     rsp, 120h
0x180002e95  mov     rax, cs:__security_cookie
0x180002e9c  xor     rax, rsp
0x180002e9f  mov     [rsp+158h+var_48], rax
0x180002ea7  mov     r14d, r9d
0x180002eaa  mov     rsi, r8
0x180002ead  mov     rdi, rdx
0x180002eb0  mov     r15, [rsp+158h+arg_20]
0x180002eb8  mov     r12, [rsp+158h+arg_28]
0x180002ec0  xor     r13d, r13d
0x180002ec3  mov     [rsp+158h+var_100], r13
0x180002ec8  mov     qword ptr [r11-88h], 5
0x180002ed3  mov     qword ptr [rsp+158h+Security+4], r13
0x180002ed8  mov     dword ptr [rsp+158h+Security.ServerPrincName+4], r13d
0x180002edd  mov     [r11-0D8h], r13
0x180002ee4  xorps   xmm0, xmm0
0x180002ee7  movdqu  [rsp+158h+var_B8], xmm0
0x180002ef0  xorps   xmm1, xmm1
0x180002ef3  xor     eax, eax
0x180002ef5  movups  xmmword ptr [r11-80h], xmm1
0x180002efa  movups  xmmword ptr [r11-70h], xmm1
0x180002eff  movups  xmmword ptr [r11-60h], xmm1
0x180002f04  mov     [r11-50h], rax
0x180002f08  mov     [rsp+158h+var_A0], 101h
0x180002f13  mov     [rsp+158h+var_9C], 5000000h
0x180002f1e  mov     [rsp+158h+var_98], 12h
0x180002f29  mov     [rsp+158h+Binding], r13
0x180002f2e  mov     dword ptr [r11-80h], 1
0x180002f36  mov     dword ptr [r11-78h], 3
0x180002f3e  mov     [rsp+158h+var_90], 1
0x180002f49  mov     [rsp+158h+var_8C], 1
0x180002f54  mov     [rsp+158h+var_C8], 3
0x180002f5f  mov     [rsp+158h+var_C4], 1
0x180002f6a  mov     [rsp+158h+var_C0], 1
0x180002f75  mov     [rsp+158h+var_BC], 3
0x180002f80  lea     rax, [r11-0A0h]
0x180002f87  mov     [r11-0A8h], rax
0x180002f8e  mov     [rsp+158h+Security.Version], 1
0x180002f96  mov     [rsp+158h+Security.AuthnLevel], 6
0x180002f9e  mov     [rsp+158h+Security.AuthnSvc], 14h
0x180002fa6  lea     rax, [r11-0C8h]
0x180002fad  mov     [r11-0D0h], rax
0x180002fb4  lea     r9, [rsp+158h+Binding]; Binding
0x180002fb9  lea     r8, [r11-90h]; Options
0x180002fc0  lea     rdx, [rsp+158h+Security]; Security
0x180002fc5  lea     rcx, [r11-80h]; Template
0x180002fc9  call    cs:__imp_RpcBindingCreateW
0x180002fcf  test    eax, eax
0x180002fd1  jnz     loc_18000309E
0x180002fd7  lea     r8, qword_180008210; IfSpec
0x180002fde  mov     rdx, [rsp+158h+Binding]; Binding
0x180002fe3  xor     ecx, ecx; pAsync
0x180002fe5  call    cs:__imp_RpcBindingBind
0x180002feb  test    eax, eax
0x180002fed  jnz     loc_18000309E
0x180002ff3  mov     ebx, r13d
0x180002ff6  mov     rax, [rsp+158h+Binding]
0x180002ffb  mov     [rsp+158h+var_100], rax
0x180003000  test    ebx, ebx
0x180003002  js      short loc_180003066
0x180003004  mov     rcx, rdi; Sid
0x180003007  call    cs:__imp_RtlLengthSid
0x18000300d  mov     [rsp+158h+Binding], r13
0x180003012  mov     [rsp+158h+var_110], r12
0x180003017  mov     [rsp+158h+var_118], r15
0x18000301c  mov     [rsp+158h+var_120], r14d
0x180003021  mov     [rsp+158h+var_128], rsi
0x180003026  mov     [rsp+158h+var_130], rdi
0x18000302b  mov     [rsp+158h+var_138], eax
0x18000302f  mov     r9, [rsp+158h+var_100]
0x180003034  xor     r8d, r8d; pReturnValue
0x180003037  xor     edx, edx; nProcNum
0x180003039  lea     rcx, pProxyInfo; pProxyInfo
0x180003040  call    cs:__imp_NdrClientCall3
0x180003046  mov     rbx, rax
0x180003049  mov     [rsp+158h+Binding], rax
0x18000304e  mov     [rsp+158h+var_F8], eax
0x180003052  jmp     short loc_180003066
0x180003054  test    eax, eax
0x180003056  jle     short loc_180003060
0x180003058  movzx   eax, ax
0x18000305b  or      eax, 80070000h
0x180003060  mov     ebx, eax
0x180003062  mov     [rsp+158h+var_F8], eax
0x180003066  cmp     [rsp+158h+var_100], 0
0x18000306c  jz      short loc_180003079
0x18000306e  lea     rcx, [rsp+158h+var_100]; Binding
0x180003073  call    cs:__imp_RpcBindingFree
0x180003079  mov     eax, ebx
0x18000307b  mov     rcx, [rsp+158h+var_48]
0x180003083  xor     rcx, rsp; StackCookie
0x180003086  call    __security_check_cookie
0x18000308b  add     rsp, 120h
0x180003092  pop     r15
0x180003094  pop     r14
0x180003096  pop     r13
0x180003098  pop     r12
0x18000309a  pop     rdi
0x18000309b  pop     rsi
0x18000309c  pop     rbx
0x18000309d  retn
0x18000309e  mov     ecx, eax; Status
0x1800030a0  call    cs:__imp_I_RpcMapWin32Status
0x1800030a6  mov     ebx, eax
0x1800030a8  bts     ebx, 1Ch
0x1800030ac  cmp     [rsp+158h+Binding], r13
0x1800030b1  jz      loc_180003000
0x1800030b7  lea     rcx, [rsp+158h+Binding]; Binding
0x1800030bc  call    cs:__imp_RpcBindingFree
0x1800030c2  jmp     loc_180003000
0x180006680  push    rbp
0x180006682  sub     rsp, 50h
0x180006686  mov     rbp, rdx
0x180006689  mov     rcx, [rcx]
0x18000668c  mov     ecx, [rcx]; ExceptionCode
0x18000668e  call    cs:__imp_I_RpcExceptionFilter
0x180006694  nop
0x180006695  add     rsp, 50h
0x180006699  pop     rbp
0x18000669a  retn
```
