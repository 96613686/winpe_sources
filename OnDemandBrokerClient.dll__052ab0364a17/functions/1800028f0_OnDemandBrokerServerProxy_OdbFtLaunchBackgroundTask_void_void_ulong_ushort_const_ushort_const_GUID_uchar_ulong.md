# OnDemandBrokerServerProxy::OdbFtLaunchBackgroundTask(void *,void *,ulong,ushort const *,ushort const *,_GUID *,uchar *,ulong,_OdbLaunchInfo *,_GUID *,_GUID *)

- ea: `0x1800028f0`
- end: `0x180002c76`
- name: `?OdbFtLaunchBackgroundTask@OnDemandBrokerServerProxy@@UEAAJPEAX0KPEBG1PEAU_GUID@@PEAEKPEAU_OdbLaunchInfo@@22@Z`
- size: `902`
- prototype: `__int64 __fastcall(OnDemandBrokerServerProxy *this, void *, void *, int, const unsigned __int16 *, const unsigned __int16 *, struct _GUID *, unsigned __int8 *, unsigned int, struct _OdbLaunchInfo *, struct _GUID *, struct _GUID *)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800028f0`
- `0x180006570`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x180002c37`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002c37`
- `RPCRT4!RpcBindingFree` at `0x180002c0a`
- `RPCRT4!RpcBindingFree` at `0x180002c5a`
- `RPCRT4!RpcBindingFree` at `0x180002c0a`
- `RPCRT4!RpcBindingFree` at `0x180002c5a`
- `RPCRT4!RpcBindingCreateW` at `0x180002ae6`
- `RPCRT4!RpcBindingCreateW` at `0x180002ae6`
- `RPCRT4!NdrClientCall3` at `0x180002bc8`
- `RPCRT4!NdrClientCall3` at `0x180002bc8`
- `RPCRT4!RpcBindingBind` at `0x180002b05`
- `RPCRT4!RpcBindingBind` at `0x180002b05`
- `RPCRT4!I_RpcExceptionFilter` at `0x180006631`
- `RPCRT4!I_RpcExceptionFilter` at `0x180006631`
- `ntdll!RtlLengthSid` at `0x18000299e`
- `ntdll!RtlLengthSid` at `0x180002c68`
- `ntdll!RtlLengthSid` at `0x18000299e`
- `ntdll!RtlLengthSid` at `0x180002c68`

## pseudocode

```c
__int64 __fastcall OnDemandBrokerServerProxy::OdbFtLaunchBackgroundTask(
        OnDemandBrokerServerProxy *this,
        void *a2,
        void *a3,
        int a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        struct _GUID *a7,
        unsigned __int8 *a8,
        unsigned int a9,
        struct _OdbLaunchInfo *a10,
        struct _GUID *a11,
        struct _GUID *a12)
{
  int Pointer; // ebx
  ULONG v16; // r14d
  ULONG v17; // r15d
  RPC_STATUS v18; // eax
  CLIENT_CALL_RETURN v19; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+90h] [rbp-138h] BYREF
  RPC_BINDING_HANDLE v22; // [rsp+98h] [rbp-130h] BYREF
  int v23; // [rsp+A0h] [rbp-128h]
  struct _GUID *v24; // [rsp+A8h] [rbp-120h]
  struct _GUID *v25; // [rsp+B0h] [rbp-118h]
  struct _OdbLaunchInfo *v26; // [rsp+B8h] [rbp-110h]
  unsigned __int8 *v27; // [rsp+C0h] [rbp-108h]
  struct _GUID *v28; // [rsp+C8h] [rbp-100h]
  const unsigned __int16 *v29; // [rsp+D0h] [rbp-F8h]
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+D8h] [rbp-F0h] BYREF
  _DWORD v31[4]; // [rsp+100h] [rbp-C8h] BYREF
  __int128 v32; // [rsp+110h] [rbp-B8h]
  _DWORD *v33; // [rsp+120h] [rbp-A8h]
  _DWORD v34[4]; // [rsp+128h] [rbp-A0h] BYREF
  RPC_BINDING_HANDLE_OPTIONS_V1 Options; // [rsp+138h] [rbp-90h] BYREF
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+148h] [rbp-80h] BYREF

  v29 = a6;
  v28 = a7;
  v27 = a8;
  v26 = a10;
  v25 = a11;
  v24 = a12;
  Pointer = 0;
  v22 = 0;
  v16 = 0;
  v17 = 0;
  if ( a2 )
    v16 = RtlLengthSid(a2);
  if ( a3 )
    v17 = RtlLengthSid(a3);
  *(_QWORD *)&Options.ComTimeout = 5;
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  Security.AuthIdentity = 0;
  v32 = 0;
  memset(&Template, 0, sizeof(Template));
  v34[0] = 257;
  v34[1] = 83886080;
  v34[2] = 18;
  Binding = 0;
  Template.Version = 1;
  Template.ProtocolSequence = 3;
  Options.Version = 1;
  Options.Flags = 1;
  v31[0] = 3;
  v31[1] = 1;
  v31[2] = 1;
  v31[3] = 3;
  v33 = v34;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 20;
  Security.SecurityQos = (RPC_SECURITY_QOS *)v31;
  v18 = RpcBindingCreateW(&Template, &Security, &Options, &Binding);
  if ( v18 || (v18 = RpcBindingBind(0, Binding, qword_180008210)) != 0 )
  {
    Pointer = I_RpcMapWin32Status(v18) | 0x10000000;
    if ( Binding )
      RpcBindingFree(&Binding);
  }
  else
  {
    v22 = Binding;
  }
  if ( Pointer >= 0 )
  {
    Binding = 0;
    v19.Pointer = NdrClientCall3(
                    (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                    2u,
                    0,
                    v22,
                    v16,
                    a2,
                    v17,
                    a3,
                    a4,
                    a5,
                    v29,
                    v28,
                    v27,
                    a9,
                    v26,
                    v25,
                    v24).Pointer;
    Pointer = (int)v19.Pointer;
    Binding = (RPC_BINDING_HANDLE)v19.Simple;
    v23 = (int)v19.Pointer;
  }
  if ( v22 )
    RpcBindingFree(&v22);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x1800028f0  push    rbx
0x1800028f2  push    rsi
0x1800028f3  push    rdi
0x1800028f4  push    r12
0x1800028f6  push    r13
0x1800028f8  push    r14
0x1800028fa  push    r15
0x1800028fc  sub     rsp, 190h
0x180002903  mov     rax, cs:__security_cookie
0x18000290a  xor     rax, rsp
0x18000290d  mov     [rsp+1C8h+var_48], rax
0x180002915  mov     r12d, r9d
0x180002918  mov     rsi, r8
0x18000291b  mov     rdi, rdx
0x18000291e  mov     r13, [rsp+1C8h+arg_20]
0x180002926  mov     rax, [rsp+1C8h+arg_28]
0x18000292e  mov     [rsp+1C8h+var_F8], rax
0x180002936  mov     rax, [rsp+1C8h+arg_30]
0x18000293e  mov     [rsp+1C8h+var_100], rax
0x180002946  mov     rax, [rsp+1C8h+arg_38]
0x18000294e  mov     [rsp+1C8h+var_108], rax
0x180002956  mov     rax, [rsp+1C8h+arg_48]
0x18000295e  mov     [rsp+1C8h+var_110], rax
0x180002966  mov     rax, [rsp+1C8h+arg_50]
0x18000296e  mov     [rsp+1C8h+var_118], rax
0x180002976  mov     rax, [rsp+1C8h+arg_58]
0x18000297e  mov     [rsp+1C8h+var_120], rax
0x180002986  xor     ebx, ebx
0x180002988  mov     [rsp+1C8h+var_130], rbx
0x180002990  mov     r14d, ebx
0x180002993  mov     r15d, ebx
0x180002996  test    rdx, rdx
0x180002999  jz      short loc_1800029A7
0x18000299b  mov     rcx, rdx; Sid
0x18000299e  call    cs:__imp_RtlLengthSid
0x1800029a4  mov     r14d, eax
0x1800029a7  test    rsi, rsi
0x1800029aa  jnz     loc_180002C65
0x1800029b0  mov     qword ptr [rsp+1C8h+Options.ComTimeout], 5
0x1800029bc  mov     qword ptr [rsp+1C8h+Security+4], rbx
0x1800029c4  mov     dword ptr [rsp+1C8h+Security.ServerPrincName+4], ebx
0x1800029cb  mov     [rsp+1C8h+Security.AuthIdentity], rbx
0x1800029d3  xorps   xmm0, xmm0
0x1800029d6  movdqu  [rsp+1C8h+var_B8], xmm0
0x1800029df  xorps   xmm1, xmm1
0x1800029e2  xor     eax, eax
0x1800029e4  movups  xmmword ptr [rsp+1C8h+Template.Version], xmm1
0x1800029ec  movups  xmmword ptr [rsp+1C8h+Template.NetworkAddress], xmm1
0x1800029f4  movups  xmmword ptr [rsp+1C8h+Template.u1], xmm1
0x1800029fc  mov     qword ptr [rsp+1C8h+Template.ObjectUuid.Data4], rax
0x180002a04  mov     [rsp+1C8h+var_A0], 101h
0x180002a0f  mov     [rsp+1C8h+var_9C], 5000000h
0x180002a1a  mov     [rsp+1C8h+var_98], 12h
0x180002a25  mov     [rsp+1C8h+Binding], rbx
0x180002a2d  mov     [rsp+1C8h+Template.Version], 1
0x180002a38  mov     [rsp+1C8h+Template.ProtocolSequence], 3
0x180002a43  mov     [rsp+1C8h+Options.Version], 1
0x180002a4e  mov     [rsp+1C8h+Options.Flags], 1
0x180002a59  mov     [rsp+1C8h+var_C8], 3
0x180002a64  mov     [rsp+1C8h+var_C4], 1
0x180002a6f  mov     [rsp+1C8h+var_C0], 1
0x180002a7a  mov     [rsp+1C8h+var_BC], 3
0x180002a85  lea     rax, [rsp+1C8h+var_A0]
0x180002a8d  mov     [rsp+1C8h+var_A8], rax
0x180002a95  mov     [rsp+1C8h+Security.Version], 1
0x180002aa0  mov     [rsp+1C8h+Security.AuthnLevel], 6
0x180002aab  mov     [rsp+1C8h+Security.AuthnSvc], 14h
0x180002ab6  lea     rax, [rsp+1C8h+var_C8]
0x180002abe  mov     [rsp+1C8h+Security.SecurityQos], rax
0x180002ac6  lea     r9, [rsp+1C8h+Binding]; Binding
0x180002ace  lea     r8, [rsp+1C8h+Options]; Options
0x180002ad6  lea     rdx, [rsp+1C8h+Security]; Security
0x180002ade  lea     rcx, [rsp+1C8h+Template]; Template
0x180002ae6  call    cs:__imp_RpcBindingCreateW
0x180002aec  test    eax, eax
0x180002aee  jnz     loc_180002C35
0x180002af4  lea     r8, qword_180008210; IfSpec
0x180002afb  mov     rdx, [rsp+1C8h+Binding]; Binding
0x180002b03  xor     ecx, ecx; pAsync
0x180002b05  call    cs:__imp_RpcBindingBind
0x180002b0b  test    eax, eax
0x180002b0d  jnz     loc_180002C35
0x180002b13  mov     rax, [rsp+1C8h+Binding]
0x180002b1b  mov     [rsp+1C8h+var_130], rax
0x180002b23  test    ebx, ebx
0x180002b25  js      loc_180002BF7
0x180002b2b  mov     [rsp+1C8h+Binding], 0
0x180002b37  mov     rax, [rsp+1C8h+var_120]
0x180002b3f  mov     [rsp+1C8h+var_148], rax
0x180002b47  mov     rax, [rsp+1C8h+var_118]
0x180002b4f  mov     [rsp+1C8h+var_150], rax
0x180002b54  mov     rax, [rsp+1C8h+var_110]
0x180002b5c  mov     [rsp+1C8h+var_158], rax
0x180002b61  mov     eax, [rsp+1C8h+arg_40]
0x180002b68  mov     [rsp+1C8h+var_160], eax
0x180002b6c  mov     rax, [rsp+1C8h+var_108]
0x180002b74  mov     [rsp+1C8h+var_168], rax
0x180002b79  mov     rax, [rsp+1C8h+var_100]
0x180002b81  mov     [rsp+1C8h+var_170], rax
0x180002b86  mov     rax, [rsp+1C8h+var_F8]
0x180002b8e  mov     [rsp+1C8h+var_178], rax
0x180002b93  mov     [rsp+1C8h+var_180], r13
0x180002b98  mov     [rsp+1C8h+var_188], r12d
0x180002b9d  mov     [rsp+1C8h+var_190], rsi
0x180002ba2  mov     [rsp+1C8h+var_198], r15d
0x180002ba7  mov     [rsp+1C8h+var_1A0], rdi
0x180002bac  mov     [rsp+1C8h+var_1A8], r14d
0x180002bb1  mov     r9, [rsp+1C8h+var_130]
0x180002bb9  xor     r8d, r8d; pReturnValue
0x180002bbc  mov     edx, 2; nProcNum
0x180002bc1  lea     rcx, pProxyInfo; pProxyInfo
0x180002bc8  call    cs:__imp_NdrClientCall3
0x180002bce  mov     rbx, rax
0x180002bd1  mov     [rsp+1C8h+Binding], rax
0x180002bd9  mov     [rsp+1C8h+var_128], eax
0x180002be0  jmp     short loc_180002BF7
0x180002be2  test    eax, eax
0x180002be4  jle     short loc_180002BEE
0x180002be6  movzx   eax, ax
0x180002be9  or      eax, 80070000h
0x180002bee  mov     ebx, eax
0x180002bf0  mov     [rsp+1C8h+var_128], eax
0x180002bf7  cmp     [rsp+1C8h+var_130], 0
0x180002c00  jz      short loc_180002C10
0x180002c02  lea     rcx, [rsp+1C8h+var_130]; Binding
0x180002c0a  call    cs:__imp_RpcBindingFree
0x180002c10  mov     eax, ebx
0x180002c12  mov     rcx, [rsp+1C8h+var_48]
0x180002c1a  xor     rcx, rsp; StackCookie
0x180002c1d  call    __security_check_cookie
0x180002c22  add     rsp, 190h
0x180002c29  pop     r15
0x180002c2b  pop     r14
0x180002c2d  pop     r13
0x180002c2f  pop     r12
0x180002c31  pop     rdi
0x180002c32  pop     rsi
0x180002c33  pop     rbx
0x180002c34  retn
0x180002c35  mov     ecx, eax; Status
0x180002c37  call    cs:__imp_I_RpcMapWin32Status
0x180002c3d  mov     ebx, eax
0x180002c3f  bts     ebx, 1Ch
0x180002c43  cmp     [rsp+1C8h+Binding], 0
0x180002c4c  jz      loc_180002B23
0x180002c52  lea     rcx, [rsp+1C8h+Binding]; Binding
0x180002c5a  call    cs:__imp_RpcBindingFree
0x180002c60  jmp     loc_180002B23
0x180002c65  mov     rcx, rsi; Sid
0x180002c68  call    cs:__imp_RtlLengthSid
0x180002c6e  mov     r15d, eax
0x180002c71  jmp     loc_1800029B0
0x180006620  push    rbp
0x180006622  sub     rsp, 90h
0x180006629  mov     rbp, rdx
0x18000662c  mov     rcx, [rcx]
0x18000662f  mov     ecx, [rcx]; ExceptionCode
0x180006631  call    cs:__imp_I_RpcExceptionFilter
0x180006637  nop
0x180006638  add     rsp, 90h
0x18000663f  pop     rbp
0x180006640  retn
```
