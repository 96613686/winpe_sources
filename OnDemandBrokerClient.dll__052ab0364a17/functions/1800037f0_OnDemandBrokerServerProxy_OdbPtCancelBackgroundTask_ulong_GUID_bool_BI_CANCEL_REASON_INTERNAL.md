# OnDemandBrokerServerProxy::OdbPtCancelBackgroundTask(ulong,_GUID,bool,_BI_CANCEL_REASON_INTERNAL)

- ea: `0x1800037f0`
- end: `0x180003a1a`
- name: `?OdbPtCancelBackgroundTask@OnDemandBrokerServerProxy@@UEAAJKU_GUID@@_NW4_BI_CANCEL_REASON_INTERNAL@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(__int64, int, RPC_BINDING_HANDLE_OPTIONS_V1 *, unsigned __int8, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800037f0`
- `0x180006570`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x1800039e6`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800039e6`
- `RPCRT4!RpcBindingFree` at `0x180003a02`
- `RPCRT4!RpcBindingFree` at `0x180003a12`
- `RPCRT4!RpcBindingFree` at `0x180003a02`
- `RPCRT4!RpcBindingFree` at `0x180003a12`
- `RPCRT4!RpcBindingCreateW` at `0x180003915`
- `RPCRT4!RpcBindingCreateW` at `0x180003915`
- `RPCRT4!NdrClientCall3` at `0x180003995`
- `RPCRT4!NdrClientCall3` at `0x180003995`
- `RPCRT4!RpcBindingBind` at `0x180003931`
- `RPCRT4!RpcBindingBind` at `0x180003931`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000671e`
- `RPCRT4!I_RpcExceptionFilter` at `0x18000671e`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerServerProxy::OdbPtCancelBackgroundTask(
        __int64 a1,
        int a2,
        RPC_BINDING_HANDLE_OPTIONS_V1 *a3,
        unsigned __int8 a4,
        int a5)
{
  int v5; // r14d
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
  _DWORD v19[6]; // [rsp+A8h] [rbp-90h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 v20; // [rsp+C0h] [rbp-78h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W v21; // [rsp+D0h] [rbp-68h] BYREF

  v5 = a4;
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
    Binding = 0;
    v20 = *a3;
    v10.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800083C0, 3u, 0, v13, a2, &v20, v5, a5, 0).Pointer;
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
0x1800037f0  mov     r11, rsp
0x1800037f3  push    rbx
0x1800037f4  push    rsi
0x1800037f5  push    rdi
0x1800037f6  push    r14
0x1800037f8  push    r15
0x1800037fa  sub     rsp, 110h
0x180003801  mov     rax, cs:__security_cookie
0x180003808  xor     rax, rsp
0x18000380b  mov     [rsp+138h+var_30], rax
0x180003813  movzx   r14d, r9b
0x180003817  mov     rsi, r8
0x18000381a  mov     edi, edx
0x18000381c  xor     r15d, r15d
0x18000381f  mov     [rsp+138h+var_F0], r15
0x180003824  mov     qword ptr [r11-70h], 5
0x18000382c  mov     qword ptr [rsp+138h+Security+4], r15
0x180003831  mov     dword ptr [rsp+138h+Security.ServerPrincName+4], r15d
0x180003836  mov     [rsp+138h+Security.AuthIdentity], r15
0x18000383b  xorps   xmm0, xmm0
0x18000383e  movdqu  [rsp+138h+var_A8], xmm0
0x180003847  xorps   xmm1, xmm1
0x18000384a  xor     eax, eax
0x18000384c  movups  xmmword ptr [r11-68h], xmm1
0x180003851  movups  xmmword ptr [r11-58h], xmm1
0x180003856  movups  xmmword ptr [r11-48h], xmm1
0x18000385b  mov     [r11-38h], rax
0x18000385f  mov     [rsp+138h+var_90], 101h
0x18000386a  mov     [rsp+138h+var_8C], 5000000h
0x180003875  mov     [rsp+138h+var_88], 12h
0x180003880  mov     [rsp+138h+Binding], r15
0x180003885  mov     dword ptr [r11-68h], 1
0x18000388d  mov     dword ptr [r11-60h], 3
0x180003895  mov     dword ptr [r11-78h], 1
0x18000389d  mov     dword ptr [r11-74h], 1
0x1800038a5  mov     [rsp+138h+var_B8], 3
0x1800038b0  mov     [rsp+138h+var_B4], 1
0x1800038bb  mov     [rsp+138h+var_B0], 1
0x1800038c6  mov     [rsp+138h+var_AC], 3
0x1800038d1  lea     rax, [r11-90h]
0x1800038d8  mov     [r11-98h], rax
0x1800038df  mov     [rsp+138h+Security.Version], 1
0x1800038e7  mov     [rsp+138h+Security.AuthnLevel], 6
0x1800038ef  mov     [rsp+138h+Security.AuthnSvc], 14h
0x1800038f7  lea     rax, [r11-0B8h]
0x1800038fe  mov     [rsp+138h+Security.SecurityQos], rax
0x180003903  lea     r9, [rsp+138h+Binding]; Binding
0x180003908  lea     r8, [r11-78h]; Options
0x18000390c  lea     rdx, [rsp+138h+Security]; Security
0x180003911  lea     rcx, [r11-68h]; Template
0x180003915  call    cs:__imp_RpcBindingCreateW
0x18000391b  test    eax, eax
0x18000391d  jnz     loc_1800039E4
0x180003923  lea     r8, qword_180008360; IfSpec
0x18000392a  mov     rdx, [rsp+138h+Binding]; Binding
0x18000392f  xor     ecx, ecx; pAsync
0x180003931  call    cs:__imp_RpcBindingBind
0x180003937  test    eax, eax
0x180003939  jnz     loc_1800039E4
0x18000393f  mov     ebx, r15d
0x180003942  mov     rax, [rsp+138h+Binding]
0x180003947  mov     [rsp+138h+var_F0], rax
0x18000394c  test    ebx, ebx
0x18000394e  js      short loc_1800039BB
0x180003950  mov     [rsp+138h+Binding], r15
0x180003955  movups  xmm0, xmmword ptr [rsi]
0x180003958  movaps  [rsp+138h+var_78], xmm0
0x180003960  mov     eax, [rsp+138h+arg_20]
0x180003967  mov     [rsp+138h+var_100], eax
0x18000396b  mov     [rsp+138h+var_108], r14d
0x180003970  lea     rax, [rsp+138h+var_78]
0x180003978  mov     [rsp+138h+var_110], rax
0x18000397d  mov     [rsp+138h+var_118], edi
0x180003981  mov     r9, [rsp+138h+var_F0]
0x180003986  xor     r8d, r8d; pReturnValue
0x180003989  mov     edx, 3; nProcNum
0x18000398e  lea     rcx, stru_1800083C0; pProxyInfo
0x180003995  call    cs:__imp_NdrClientCall3
0x18000399b  mov     rbx, rax
0x18000399e  mov     [rsp+138h+Binding], rax
0x1800039a3  mov     [rsp+138h+var_E8], eax
0x1800039a7  jmp     short loc_1800039BB
0x1800039a9  test    eax, eax
0x1800039ab  jle     short loc_1800039B5
0x1800039ad  movzx   eax, ax
0x1800039b0  or      eax, 80070000h
0x1800039b5  mov     ebx, eax
0x1800039b7  mov     [rsp+138h+var_E8], eax
0x1800039bb  cmp     [rsp+138h+var_F0], 0
0x1800039c1  jnz     short loc_180003A0D
0x1800039c3  mov     eax, ebx
0x1800039c5  mov     rcx, [rsp+138h+var_30]
0x1800039cd  xor     rcx, rsp; StackCookie
0x1800039d0  call    __security_check_cookie
0x1800039d5  add     rsp, 110h
0x1800039dc  pop     r15
0x1800039de  pop     r14
0x1800039e0  pop     rdi
0x1800039e1  pop     rsi
0x1800039e2  pop     rbx
0x1800039e3  retn
0x1800039e4  mov     ecx, eax; Status
0x1800039e6  call    cs:__imp_I_RpcMapWin32Status
0x1800039ec  mov     ebx, eax
0x1800039ee  bts     ebx, 1Ch
0x1800039f2  cmp     [rsp+138h+Binding], r15
0x1800039f7  jz      loc_18000394C
0x1800039fd  lea     rcx, [rsp+138h+Binding]; Binding
0x180003a02  call    cs:__imp_RpcBindingFree
0x180003a08  jmp     loc_18000394C
0x180003a0d  lea     rcx, [rsp+138h+var_F0]; Binding
0x180003a12  call    cs:__imp_RpcBindingFree
0x180003a18  jmp     short loc_1800039C3
0x180006710  push    rbp
0x180006712  sub     rsp, 40h
0x180006716  mov     rbp, rdx
0x180006719  mov     rcx, [rcx]
0x18000671c  mov     ecx, [rcx]; ExceptionCode
0x18000671e  call    cs:__imp_I_RpcExceptionFilter
0x180006724  nop
0x180006725  add     rsp, 40h
0x180006729  pop     rbp
0x18000672a  retn
```
