# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(_GUID const &,void * *)

- ea: `0x180008680`
- end: `0x18000870f`
- name: `?QueryInterface@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAJAEBU_GUID@@PEAPEAX@Z`
- size: `143`
- prototype: `__int64 __fastcall(__int64, _DWORD *, __int64 *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180008720`
- `0x180008730`
- `0x1800089a0`

## callees

- `0x180007520`
- `0x180008680`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::QueryInterface(
        __int64 a1,
        _DWORD *a2,
        __int64 *a3)
{
  int v3; // eax
  int CanCastTo; // ebx
  _QWORD *v5; // r8

  *a3 = 0;
  if ( *a2 )
  {
    if ( *a2 != -1350114592
      || a2[1] != *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
      || a2[2] != *(_DWORD *)GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4 )
    {
      goto LABEL_11;
    }
    v3 = *(_DWORD *)&GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4[4];
  }
  else
  {
    if ( a2[1] != *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data2
      || a2[2] != *(_DWORD *)GUID_00000000_0000_0000_c000_000000000046.Data4 )
    {
      goto LABEL_11;
    }
    v3 = *(_DWORD *)&GUID_00000000_0000_0000_c000_000000000046.Data4[4];
  }
  if ( a2[3] == v3 )
  {
    *a3 = a1;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a1 + 8LL))(a1);
    return 0;
  }
LABEL_11:
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
                a1,
                a2,
                a3);
  if ( CanCastTo >= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  return (unsigned int)CanCastTo;
}

```

## disassembly

```asm
0x180008680  push    rbx
0x180008682  sub     rsp, 20h
0x180008686  mov     qword ptr [r8], 0
0x18000868d  cmp     dword ptr [rdx], 0
0x180008690  jnz     short loc_1800086B0
0x180008692  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data2
0x180008698  cmp     [rdx+4], eax
0x18000869b  jnz     short loc_1800086EC
0x18000869d  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4
0x1800086a3  cmp     [rdx+8], eax
0x1800086a6  jnz     short loc_1800086EC
0x1800086a8  mov     eax, dword ptr cs:_GUID_00000000_0000_0000_c000_000000000046.Data4+4
0x1800086ae  jmp     short loc_1800086D4
0x1800086b0  cmp     dword ptr [rdx], 0AF86E2E0h
0x1800086b6  jnz     short loc_1800086EC
0x1800086b8  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data2
0x1800086be  cmp     [rdx+4], eax
0x1800086c1  jnz     short loc_1800086EC
0x1800086c3  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4
0x1800086c9  cmp     [rdx+8], eax
0x1800086cc  jnz     short loc_1800086EC
0x1800086ce  mov     eax, dword ptr cs:_GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90.Data4+4
0x1800086d4  cmp     [rdx+0Ch], eax
0x1800086d7  jnz     short loc_1800086EC
0x1800086d9  mov     [r8], rcx
0x1800086dc  mov     rax, [rcx]
0x1800086df  mov     rax, [rax+8]
0x1800086e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086e8  xor     ebx, ebx
0x1800086ea  jmp     short loc_180008707
0x1800086ec  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x1800086f1  mov     ebx, eax
0x1800086f3  test    eax, eax
0x1800086f5  js      short loc_180008707
0x1800086f7  mov     rcx, [r8]
0x1800086fa  mov     rdx, [rcx]
0x1800086fd  mov     rax, [rdx+8]
0x180008701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008706  nop
0x180008707  mov     eax, ebx
0x180008709  add     rsp, 20h
0x18000870d  pop     rbx
0x18000870e  retn
```
