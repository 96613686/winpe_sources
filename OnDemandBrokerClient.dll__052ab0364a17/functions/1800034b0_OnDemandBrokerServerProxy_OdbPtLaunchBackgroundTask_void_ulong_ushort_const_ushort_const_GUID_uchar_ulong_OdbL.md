# OnDemandBrokerServerProxy::OdbPtLaunchBackgroundTask(void *,ulong,ushort const *,ushort const *,_GUID *,uchar *,ulong,_OdbLaunchInfo *,_GUID *,_GUID *)

- ea: `0x1800034b0`
- end: `0x1800037ea`
- name: `?OdbPtLaunchBackgroundTask@OnDemandBrokerServerProxy@@UEAAJPEAXKPEBG1PEAU_GUID@@PEAEKPEAU_OdbLaunchInfo@@22@Z`
- size: `826`
- prototype: `__int64 __fastcall(OnDemandBrokerServerProxy *this, void *, int, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *, unsigned __int8 *, unsigned int, struct _OdbLaunchInfo *, struct _GUID *, struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800034b0`
- `0x180006570`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x1800037ac`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800037ac`
- `RPCRT4!RpcBindingFree` at `0x18000377f`
- `RPCRT4!RpcBindingFree` at `0x1800037cf`
- `RPCRT4!RpcBindingFree` at `0x18000377f`
- `RPCRT4!RpcBindingFree` at `0x1800037cf`
- `RPCRT4!RpcBindingCreateW` at `0x180003679`
- `RPCRT4!RpcBindingCreateW` at `0x180003679`
- `RPCRT4!NdrClientCall3` at `0x18000373d`
- `RPCRT4!NdrClientCall3` at `0x18000373d`
- `RPCRT4!RpcBindingBind` at `0x180003698`
- `RPCRT4!RpcBindingBind` at `0x180003698`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800066f1`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800066f1`
- `ntdll!RtlLengthSid` at `0x1800037dd`
- `ntdll!RtlLengthSid` at `0x1800037dd`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerServerProxy::OdbPtLaunchBackgroundTask(
        OnDemandBrokerServerProxy *this,
        void *a2,
        int a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        struct _GUID *a6,
        unsigned __int8 *a7,
        unsigned int a8,
        struct _OdbLaunchInfo *a9,
        struct _GUID *a10,
        struct _GUID *a11)
{
  int Pointer; // ebx
  ULONG v15; // esi
  RPC_STATUS v16; // eax
  CLIENT_CALL_RETURN v17; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+80h] [rbp-128h] BYREF
  RPC_BINDING_HANDLE v20; // [rsp+88h] [rbp-120h] BYREF
  int v21; // [rsp+90h] [rbp-118h]
  struct _GUID *v22; // [rsp+98h] [rbp-110h]
  struct _GUID *v23; // [rsp+A0h] [rbp-108h]
  struct _OdbLaunchInfo *v24; // [rsp+A8h] [rbp-100h]
  unsigned __int8 *v25; // [rsp+B0h] [rbp-F8h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+B8h] [rbp-F0h] BYREF
  _DWORD v27[4]; // [rsp+E0h] [rbp-C8h] BYREF
  __int128 v28; // [rsp+F0h] [rbp-B8h]
  _DWORD *v29; // [rsp+100h] [rbp-A8h]
  _DWORD v30[4]; // [rsp+108h] [rbp-A0h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+118h] [rbp-90h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+128h] [rbp-80h] BYREF

  v25 = a7;
  v24 = a9;
  v23 = a10;
  v22 = a11;
  Pointer = 0;
  v20 = 0;
  v15 = 0;
  if ( a2 )
    v15 = RtlLengthSid(a2);
  *(_QWORD *)&Options.ComTimeout = 5;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  v28 = 0;
  memset(&Template, 0, sizeof(Template));
  v30[0] = 257;
  v30[1] = 83886080;
  v30[2] = 18;
  Binding = 0;
  Template.Version = 1;
  Template.ProtocolSequence = 3;
  Options.Version = 1;
  Options.Flags = 1;
  v27[0] = 3;
  v27[1] = 1;
  v27[2] = 1;
  v27[3] = 3;
  v29 = v30;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v27;
  v16 = RpcBindingCreateW(&Template, &Security, &Options, &Binding);
  if ( v16 || (v16 = RpcBindingBind(0, Binding, qword_180008360)) != 0 )
  {
    Pointer = I_RpcMapWin32Status(v16) | 0x10000000;
    if ( Binding )
      RpcBindingFree(&Binding);
  }
  else
  {
    v20 = Binding;
  }
  if ( Pointer >= 0 )
  {
    Binding = 0;
    v17.Pointer = NdrClientCall3(
                    (MIDL_STUBLESS_PROXY_INFO *)&stru_1800083C0,
                    2u,
                    0,
                    v20,
                    v15,
                    a2,
                    a3,
                    a4,
                    a5,
                    a6,
                    v25,
                    a8,
                    v24,
                    v23,
                    v22).Pointer;
    Pointer = (int)v17.Pointer;
    Binding = (RPC_BINDING_HANDLE)v17.Simple;
    v21 = (int)v17.Pointer;
  }
  if ( v20 )
    RpcBindingFree(&v20);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x1800034b0  push    rbx
0x1800034b2  push    rsi
0x1800034b3  push    rdi
0x1800034b4  push    r12
0x1800034b6  push    r13
0x1800034b8  push    r14
0x1800034ba  push    r15
0x1800034bc  sub     rsp, 170h
0x1800034c3  mov     rax, cs:__security_cookie
0x1800034ca  xor     rax, rsp
0x1800034cd  mov     [rsp+1A8h+var_48], rax
0x1800034d5  mov     r15, r9
0x1800034d8  mov     r14d, r8d
0x1800034db  mov     rdi, rdx
0x1800034de  mov     r12, [rsp+1A8h+arg_20]
0x1800034e6  mov     r13, [rsp+1A8h+arg_28]
0x1800034ee  mov     rax, [rsp+1A8h+arg_30]
0x1800034f6  mov     [rsp+1A8h+var_F8], rax
0x1800034fe  mov     rax, [rsp+1A8h+arg_40]
0x180003506  mov     [rsp+1A8h+var_100], rax
0x18000350e  mov     rax, [rsp+1A8h+arg_48]
0x180003516  mov     [rsp+1A8h+var_108], rax
0x18000351e  mov     rax, [rsp+1A8h+arg_50]
0x180003526  mov     [rsp+1A8h+var_110], rax
0x18000352e  xor     ebx, ebx
0x180003530  mov     [rsp+1A8h+var_120], rbx
0x180003538  mov     esi, ebx
0x18000353a  test    rdx, rdx
0x18000353d  jnz     loc_1800037DA
0x180003543  mov     qword ptr [rsp+1A8h+Options.ComTimeout], 5
0x18000354f  mov     qword ptr [rsp+1A8h+Security+4], rbx
0x180003557  mov     dword ptr [rsp+1A8h+Security.ServerPrincName+4], ebx
0x18000355e  mov     [rsp+1A8h+Security.AuthIdentity], rbx
0x180003566  xorps   xmm0, xmm0
0x180003569  movdqu  [rsp+1A8h+var_B8], xmm0
0x180003572  xorps   xmm1, xmm1
0x180003575  xor     eax, eax
0x180003577  movups  xmmword ptr [rsp+1A8h+Template.Version], xmm1
0x18000357f  movups  xmmword ptr [rsp+1A8h+Template.NetworkAddress], xmm1
0x180003587  movups  xmmword ptr [rsp+1A8h+Template.u1], xmm1
0x18000358f  mov     qword ptr [rsp+1A8h+Template.ObjectUuid.Data4], rax
0x180003597  mov     [rsp+1A8h+var_A0], 101h
0x1800035a2  mov     [rsp+1A8h+var_9C], 5000000h
0x1800035ad  mov     [rsp+1A8h+var_98], 12h
0x1800035b8  mov     [rsp+1A8h+Binding], rbx
0x1800035c0  mov     [rsp+1A8h+Template.Version], 1
0x1800035cb  mov     [rsp+1A8h+Template.ProtocolSequence], 3
0x1800035d6  mov     [rsp+1A8h+Options.Version], 1
0x1800035e1  mov     [rsp+1A8h+Options.Flags], 1
0x1800035ec  mov     [rsp+1A8h+var_C8], 3
0x1800035f7  mov     [rsp+1A8h+var_C4], 1
0x180003602  mov     [rsp+1A8h+var_C0], 1
0x18000360d  mov     [rsp+1A8h+var_BC], 3
0x180003618  lea     rax, [rsp+1A8h+var_A0]
0x180003620  mov     [rsp+1A8h+var_A8], rax
0x180003628  mov     [rsp+1A8h+Security.Version], 1
0x180003633  mov     [rsp+1A8h+Security.AuthnLevel], 6
0x18000363e  mov     [rsp+1A8h+Security.AuthnSvc], 14h
0x180003649  lea     rax, [rsp+1A8h+var_C8]
0x180003651  mov     [rsp+1A8h+Security.SecurityQos], rax
0x180003659  lea     r9, [rsp+1A8h+Binding]; Binding
0x180003661  lea     r8, [rsp+1A8h+Options]; Options
0x180003669  lea     rdx, [rsp+1A8h+Security]; Security
0x180003671  lea     rcx, [rsp+1A8h+Template]; Template
0x180003679  call    cs:__imp_RpcBindingCreateW
0x18000367f  test    eax, eax
0x180003681  jnz     loc_1800037AA
0x180003687  lea     r8, qword_180008360; IfSpec
0x18000368e  mov     rdx, [rsp+1A8h+Binding]; Binding
0x180003696  xor     ecx, ecx; pAsync
0x180003698  call    cs:__imp_RpcBindingBind
0x18000369e  test    eax, eax
0x1800036a0  jnz     loc_1800037AA
0x1800036a6  mov     rax, [rsp+1A8h+Binding]
0x1800036ae  mov     [rsp+1A8h+var_120], rax
0x1800036b6  test    ebx, ebx
0x1800036b8  js      loc_18000376C
0x1800036be  mov     [rsp+1A8h+Binding], 0
0x1800036ca  mov     rax, [rsp+1A8h+var_110]
0x1800036d2  mov     [rsp+1A8h+var_138], rax
0x1800036d7  mov     rax, [rsp+1A8h+var_108]
0x1800036df  mov     [rsp+1A8h+var_140], rax
0x1800036e4  mov     rax, [rsp+1A8h+var_100]
0x1800036ec  mov     [rsp+1A8h+var_148], rax
0x1800036f1  mov     eax, [rsp+1A8h+arg_38]
0x1800036f8  mov     [rsp+1A8h+var_150], eax
0x1800036fc  mov     rax, [rsp+1A8h+var_F8]
0x180003704  mov     [rsp+1A8h+var_158], rax
0x180003709  mov     [rsp+1A8h+var_160], r13
0x18000370e  mov     [rsp+1A8h+var_168], r12
0x180003713  mov     [rsp+1A8h+var_170], r15
0x180003718  mov     [rsp+1A8h+var_178], r14d
0x18000371d  mov     [rsp+1A8h+var_180], rdi
0x180003722  mov     [rsp+1A8h+var_188], esi
0x180003726  mov     r9, [rsp+1A8h+var_120]
0x18000372e  xor     r8d, r8d; pReturnValue
0x180003731  mov     edx, 2; nProcNum
0x180003736  lea     rcx, stru_1800083C0; pProxyInfo
0x18000373d  call    cs:__imp_NdrClientCall3
0x180003743  mov     rbx, rax
0x180003746  mov     [rsp+1A8h+Binding], rax
0x18000374e  mov     [rsp+1A8h+var_118], eax
0x180003755  jmp     short loc_18000376C
0x180003757  test    eax, eax
0x180003759  jle     short loc_180003763
0x18000375b  movzx   eax, ax
0x18000375e  or      eax, 80070000h
0x180003763  mov     ebx, eax
0x180003765  mov     [rsp+1A8h+var_118], eax
0x18000376c  cmp     [rsp+1A8h+var_120], 0
0x180003775  jz      short loc_180003785
0x180003777  lea     rcx, [rsp+1A8h+var_120]; Binding
0x18000377f  call    cs:__imp_RpcBindingFree
0x180003785  mov     eax, ebx
0x180003787  mov     rcx, [rsp+1A8h+var_48]
0x18000378f  xor     rcx, rsp; StackCookie
0x180003792  call    __security_check_cookie
0x180003797  add     rsp, 170h
0x18000379e  pop     r15
0x1800037a0  pop     r14
0x1800037a2  pop     r13
0x1800037a4  pop     r12
0x1800037a6  pop     rdi
0x1800037a7  pop     rsi
0x1800037a8  pop     rbx
0x1800037a9  retn
0x1800037aa  mov     ecx, eax; Status
0x1800037ac  call    cs:__imp_I_RpcMapWin32Status
0x1800037b2  mov     ebx, eax
0x1800037b4  bts     ebx, 1Ch
0x1800037b8  cmp     [rsp+1A8h+Binding], 0
0x1800037c1  jz      loc_1800036B6
0x1800037c7  lea     rcx, [rsp+1A8h+Binding]; Binding
0x1800037cf  call    cs:__imp_RpcBindingFree
0x1800037d5  jmp     loc_1800036B6
0x1800037da  mov     rcx, rdi; Sid
0x1800037dd  call    cs:__imp_RtlLengthSid
0x1800037e3  mov     esi, eax
0x1800037e5  jmp     loc_180003543
0x1800066e0  push    rbp
0x1800066e2  sub     rsp, 80h
0x1800066e9  mov     rbp, rdx
0x1800066ec  mov     rcx, [rcx]
0x1800066ef  mov     ecx, [rcx]; ExceptionCode
0x1800066f1  call    cs:__imp_I_RpcExceptionFilter
0x1800066f7  nop
0x1800066f8  add     rsp, 80h
0x1800066ff  pop     rbp
0x180006700  retn
```
