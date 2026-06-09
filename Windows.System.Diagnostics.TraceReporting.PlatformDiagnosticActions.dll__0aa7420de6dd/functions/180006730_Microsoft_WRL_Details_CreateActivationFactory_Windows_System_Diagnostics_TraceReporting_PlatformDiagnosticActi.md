# Microsoft::WRL::Details::CreateActivationFactory<Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180006730`
- end: `0x1800068f1`
- name: `??$CreateActivationFactory@VPlatformDiagnosticActions@TraceReporting@Diagnostics@System@Windows@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `449`
- prototype: `__int64 __fastcall(_BYTE *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800016a0`
- `0x1800021c4`
- `0x180006730`
- `0x180006e30`
- `0x180007520`
- `0x180008a30`
- `0x18000b010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000679d`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18000679d`
- `RPCRT4!RpcStringFreeW` at `0x180006808`
- `RPCRT4!RpcStringFreeW` at `0x180006808`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800067f1`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x1800067f1`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800067cc`
- `RPCRT4!RpcStringBindingComposeW` at `0x1800067cc`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions>(
        _BYTE *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions *v8; // rax
  signed int v9; // ebx
  __int64 v10; // rdi
  RPC_STATUS v11; // eax
  RPC_STATUS v12; // eax
  __int64 v14; // rbx
  int CanCastTo; // edi
  signed __int32 v16; // edx
  int v17; // edx
  signed __int32 v18; // eax
  RPC_WSTR String; // [rsp+30h] [rbp-68h] BYREF
  unsigned __int16 ProtSeq[20]; // [rsp+38h] [rbp-60h] BYREF

  v8 = (Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions *)operator new(
                                                                                    0x70u,
                                                                                    (const struct std::nothrow_t *)&std::nothrow);
  if ( !v8 )
    return (unsigned int)-2147024882;
  v10 = Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions::PlatformDiagnosticActions(v8);
  _o_wcscpy_s(ProtSeq, 20, L"ncalrpc");
  String = 0;
  v11 = RpcStringBindingComposeW(0, ProtSeq, 0, 0, 0, &String);
  v9 = v11;
  if ( v11 > 0 )
    v9 = (unsigned __int16)v11 | 0x80070000;
  if ( v9 < 0 )
    goto LABEL_9;
  v12 = RpcBindingFromStringBindingW(String, (RPC_BINDING_HANDLE *)(v10 + 104));
  v9 = v12;
  if ( v12 > 0 )
    v9 = (unsigned __int16)v12 | 0x80070000;
  RpcStringFreeW(&String);
  if ( v9 < 0 )
  {
LABEL_9:
    if ( v10 )
      Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(v10);
    return (unsigned int)v9;
  }
  if ( !v10 )
    goto LABEL_13;
  do
  {
    v16 = *(_DWORD *)(v10 + 68);
    if ( v16 == 0x7FFFFFFF )
    {
      v17 = 0x7FFFFFFF;
      goto LABEL_22;
    }
  }
  while ( v16 != _InterlockedCompareExchange((volatile signed __int32 *)(v10 + 68), v16 + 1, v16) );
  v17 = v16 + 1;
LABEL_22:
  if ( (*(_BYTE *)(v10 + 88) & 4) == 0 && v17 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
  {
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    v14 = v10;
  }
  else
  {
LABEL_13:
    v14 = v10;
    if ( !v10 )
      goto LABEL_15;
  }
  Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(v10);
LABEL_15:
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
                v14,
                a3,
                a4);
  if ( CanCastTo >= 0 )
  {
    if ( (*a1 & 4) == 0 )
    {
      do
        v18 = *(_DWORD *)(v14 + 68);
      while ( v18 != 0x7FFFFFFF
           && v18 != _InterlockedCompareExchange((volatile signed __int32 *)(v14 + 68), v18 + 1, v18) );
    }
    *(_DWORD *)(v14 + 88) = *(_DWORD *)a1;
    *(_QWORD *)(v14 + 80) = a2;
    return 0;
  }
  else
  {
    if ( v14 )
      Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(v14);
    return (unsigned int)CanCastTo;
  }
}

```

## disassembly

```asm
0x180006730  mov     [rsp+arg_8], rbx
0x180006735  mov     [rsp+arg_10], rbp
0x18000673a  push    rsi
0x18000673b  push    rdi
0x18000673c  push    r12
0x18000673e  push    r14
0x180006740  push    r15
0x180006742  sub     rsp, 70h
0x180006746  mov     rax, cs:__security_cookie
0x18000674d  xor     rax, rsp
0x180006750  mov     [rsp+98h+var_38], rax
0x180006755  mov     r15, r9
0x180006758  mov     r14, r8
0x18000675b  mov     rbp, rdx
0x18000675e  mov     rsi, rcx
0x180006761  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180006768  mov     ecx, 70h ; 'p'; unsigned __int64
0x18000676d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006772  test    rax, rax
0x180006775  jnz     short loc_180006781
0x180006777  mov     ebx, 8007000Eh
0x18000677c  jmp     loc_18000681F
0x180006781  mov     rcx, rax; this
0x180006784  call    ??0PlatformDiagnosticActions@TraceReporting@Diagnostics@System@Windows@@QEAA@XZ; Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions::PlatformDiagnosticActions(void)
0x180006789  mov     rdi, rax
0x18000678c  lea     r8, aNcalrpc; "ncalrpc"
0x180006793  mov     edx, 14h
0x180006798  lea     rcx, [rsp+98h+ProtSeq]
0x18000679d  call    cs:__imp__o_wcscpy_s
0x1800067a3  mov     [rsp+98h+String], 0
0x1800067ac  lea     rax, [rsp+98h+String]
0x1800067b1  mov     [rsp+98h+StringBinding], rax; StringBinding
0x1800067b6  mov     [rsp+98h+Options], 0; Options
0x1800067bf  xor     r9d, r9d; Endpoint
0x1800067c2  xor     r8d, r8d; NetworkAddr
0x1800067c5  lea     rdx, [rsp+98h+ProtSeq]; ProtSeq
0x1800067ca  xor     ecx, ecx; ObjUuid
0x1800067cc  call    cs:__imp_RpcStringBindingComposeW
0x1800067d2  mov     ebx, eax
0x1800067d4  mov     r12d, 80070000h
0x1800067da  test    eax, eax
0x1800067dc  jle     short loc_1800067E4
0x1800067de  movzx   ebx, ax
0x1800067e1  or      ebx, r12d
0x1800067e4  test    ebx, ebx
0x1800067e6  js      short loc_180006812
0x1800067e8  lea     rdx, [rdi+68h]; Binding
0x1800067ec  mov     rcx, [rsp+98h+String]; StringBinding
0x1800067f1  call    cs:__imp_RpcBindingFromStringBindingW
0x1800067f7  mov     ebx, eax
0x1800067f9  test    eax, eax
0x1800067fb  jle     short loc_180006803
0x1800067fd  movzx   ebx, ax
0x180006800  or      ebx, r12d
0x180006803  lea     rcx, [rsp+98h+String]; String
0x180006808  call    cs:__imp_RpcStringFreeW
0x18000680e  test    ebx, ebx
0x180006810  jns     short loc_180006826
0x180006812  test    rdi, rdi
0x180006815  jz      short loc_18000681F
0x180006817  mov     rcx, rdi
0x18000681a  call    ?Release@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x18000681f  mov     eax, ebx
0x180006821  jmp     loc_1800068CB
0x180006826  mov     r12d, 7FFFFFFFh
0x18000682c  test    rdi, rdi
0x18000682f  jnz     short loc_180006872
0x180006831  mov     rbx, rdi
0x180006834  test    rdi, rdi
0x180006837  jz      short loc_180006841
0x180006839  mov     rcx, rdi
0x18000683c  call    ?Release@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180006841  mov     r8, r15
0x180006844  mov     rdx, r14
0x180006847  mov     rcx, rbx
0x18000684a  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x18000684f  mov     edi, eax
0x180006851  test    eax, eax
0x180006853  jns     short loc_1800068A9
0x180006855  test    rbx, rbx
0x180006858  jz      short loc_180006862
0x18000685a  mov     rcx, rbx
0x18000685d  call    ?Release@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180006862  mov     eax, edi
0x180006864  jmp     short loc_1800068CB
0x180006866  lea     ecx, [rdx+1]
0x180006869  mov     eax, edx
0x18000686b  lock cmpxchg [rdi+44h], ecx
0x180006870  jz      short loc_1800068A5
0x180006872  mov     edx, [rdi+44h]
0x180006875  cmp     edx, r12d
0x180006878  jnz     short loc_180006866
0x18000687a  mov     edx, r12d
0x18000687d  test    byte ptr [rdi+58h], 4
0x180006881  jnz     short loc_180006831
0x180006883  cmp     edx, 2
0x180006886  jnz     short loc_180006831
0x180006888  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000688f  test    rcx, rcx
0x180006892  jz      short loc_180006831
0x180006894  mov     rax, [rcx]
0x180006897  mov     rax, [rax+8]
0x18000689b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068a0  mov     rbx, rdi
0x1800068a3  jmp     short loc_180006839
0x1800068a5  inc     edx
0x1800068a7  jmp     short loc_18000687D
0x1800068a9  test    byte ptr [rsi], 4
0x1800068ac  jnz     short loc_1800068C0
0x1800068ae  mov     eax, [rbx+44h]
0x1800068b1  cmp     eax, r12d
0x1800068b4  jz      short loc_1800068C0
0x1800068b6  lea     ecx, [rax+1]
0x1800068b9  lock cmpxchg [rbx+44h], ecx
0x1800068be  jnz     short loc_1800068AE
0x1800068c0  mov     eax, [rsi]
0x1800068c2  mov     [rbx+58h], eax
0x1800068c5  mov     [rbx+50h], rbp
0x1800068c9  xor     eax, eax
0x1800068cb  mov     rcx, [rsp+98h+var_38]
0x1800068d0  xor     rcx, rsp; StackCookie
0x1800068d3  call    __security_check_cookie
0x1800068d8  lea     r11, [rsp+98h+var_28]
0x1800068dd  mov     rbx, [r11+38h]
0x1800068e1  mov     rbp, [r11+40h]
0x1800068e5  mov     rsp, r11
0x1800068e8  pop     r15
0x1800068ea  pop     r14
0x1800068ec  pop     r12
0x1800068ee  pop     rdi
0x1800068ef  pop     rsi
0x1800068f0  retn
```
