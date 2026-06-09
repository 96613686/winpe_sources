# Microsoft::WRL::Details::CreateActivationFactory<Windows::System::Diagnostics::DiagnosticInvokerStatics>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180006680`
- end: `0x18000681b`
- name: `??$CreateActivationFactory@VDiagnosticInvokerStatics@Diagnostics@System@Windows@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `411`
- prototype: `__int64 __fastcall(_BYTE *, __int64, _DWORD *, _QWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800022fc`
- `0x180002ac8`
- `0x180006680`
- `0x180007700`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<Windows::System::Diagnostics::DiagnosticInvokerStatics>(
        _BYTE *a1,
        __int64 a2,
        _DWORD *a3,
        _QWORD *a4)
{
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  int v10; // esi
  __int64 v11; // rax
  _DWORD *v13; // rcx
  signed __int32 v14; // eax

  v8 = operator new(0xB8u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
    return (unsigned int)-2147024882;
  v8[5] = 1;
  *(_QWORD *)v8 = &Microsoft::WRL::ActivationFactory<Windows::System::Diagnostics::IDiagnosticInvokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `IActivationFactory'};
  *((_QWORD *)v8 + 1) = &Microsoft::WRL::ActivationFactory<Windows::System::Diagnostics::IDiagnosticInvokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Windows::System::Diagnostics::IDiagnosticInvokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  *((_QWORD *)v8 + 4) = 0;
  v8[10] = 4;
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v9 = &Windows::System::Diagnostics::DiagnosticInvokerStatics::`vftable'{for `IActivationFactory'};
  *((_QWORD *)v9 + 1) = &Windows::System::Diagnostics::DiagnosticInvokerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Windows::System::Diagnostics::IDiagnosticInvokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  *((_BYTE *)v9 + 48) = 0;
  memset_0((char *)v9 + 50, 0, 0x81u);
  v10 = Windows::System::Diagnostics::DiagnosticInvokerStatics::RuntimeClassInitialize((Windows::System::Diagnostics::DiagnosticInvokerStatics *)v9);
  v11 = *(_QWORD *)v9;
  if ( v10 < 0 )
  {
    (*(void (__fastcall **)(_DWORD *))(v11 + 16))(v9);
    return (unsigned int)v10;
  }
  (*(void (__fastcall **)(_DWORD *))(v11 + 8))(v9);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
  if ( *a3 != 53 )
  {
    if ( *a3 == 1559943390
      && a3[1] == *(_DWORD *)&GUID_5cfad8de_f15c_4554_a813_c113c3881b09.Data2
      && a3[2] == *(_DWORD *)GUID_5cfad8de_f15c_4554_a813_c113c3881b09.Data4
      && a3[3] == *(_DWORD *)&GUID_5cfad8de_f15c_4554_a813_c113c3881b09.Data4[4] )
    {
      v13 = v9;
      v9 += 2;
      goto LABEL_18;
    }
LABEL_23:
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
    return 2147500034LL;
  }
  if ( a3[1] != *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data2
    || a3[2] != *(_DWORD *)GUID_00000035_0000_0000_c000_000000000046.Data4
    || a3[3] != *(_DWORD *)&GUID_00000035_0000_0000_c000_000000000046.Data4[4] )
  {
    goto LABEL_23;
  }
  v13 = v9;
LABEL_18:
  *a4 = v9;
  if ( (*a1 & 4) == 0 )
  {
    do
      v14 = v13[5];
    while ( v14 != 0x7FFFFFFF && v14 != _InterlockedCompareExchange(v13 + 5, v14 + 1, v14) );
  }
  v13[10] = *(_DWORD *)a1;
  *((_QWORD *)v13 + 4) = a2;
  return 0;
}

```

## disassembly

```asm
0x180006680  push    rbx
0x180006682  push    rbp
0x180006683  push    rsi
0x180006684  push    rdi
0x180006685  push    r14
0x180006687  push    r15
0x180006689  sub     rsp, 28h
0x18000668d  mov     r14, r9
0x180006690  mov     rdi, r8
0x180006693  mov     rbp, rdx
0x180006696  mov     r15, rcx
0x180006699  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800066a0  mov     ecx, 0B8h; unsigned __int64
0x1800066a5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800066aa  mov     rbx, rax
0x1800066ad  test    rax, rax
0x1800066b0  jnz     short loc_1800066BC
0x1800066b2  mov     esi, 8007000Eh
0x1800066b7  jmp     loc_180006749
0x1800066bc  mov     dword ptr [rax+14h], 1
0x1800066c3  lea     rax, ??_7?$ActivationFactory@UIDiagnosticInvokerStatics@Diagnostics@System@Windows@@VNil@Details@WRL@Microsoft@@V5678@$0A@@WRL@Microsoft@@6BIActivationFactory@@@; const Microsoft::WRL::ActivationFactory<Windows::System::Diagnostics::IDiagnosticInvokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `IActivationFactory'}
0x1800066ca  mov     [rbx], rax
0x1800066cd  lea     rax, ??_7?$ActivationFactory@UIDiagnosticInvokerStatics@Diagnostics@System@Windows@@VNil@Details@WRL@Microsoft@@V5678@$0A@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00UIDiagnosticInvokerStatics@Diagnostics@System@Windows@@VNil@Details@23@V8923@V8923@@Details@12@@; const Microsoft::WRL::ActivationFactory<Windows::System::Diagnostics::IDiagnosticInvokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Windows::System::Diagnostics::IDiagnosticInvokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x1800066d4  mov     [rbx+8], rax
0x1800066d8  mov     qword ptr [rbx+20h], 0
0x1800066e0  mov     dword ptr [rbx+28h], 4
0x1800066e7  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800066ee  test    rcx, rcx
0x1800066f1  jz      short loc_180006700
0x1800066f3  mov     rax, [rcx]
0x1800066f6  mov     rax, [rax+8]
0x1800066fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066ff  nop
0x180006700  lea     rax, ??_7DiagnosticInvokerStatics@Diagnostics@System@Windows@@6BIActivationFactory@@@; const Windows::System::Diagnostics::DiagnosticInvokerStatics::`vftable'{for `IActivationFactory'}
0x180006707  mov     [rbx], rax
0x18000670a  lea     rax, ??_7DiagnosticInvokerStatics@Diagnostics@System@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$00UIDiagnosticInvokerStatics@Diagnostics@System@Windows@@VNil@Details@23@V8923@V8923@@Details@WRL@Microsoft@@@; const Windows::System::Diagnostics::DiagnosticInvokerStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,1,Windows::System::Diagnostics::IDiagnosticInvokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180006711  mov     [rbx+8], rax
0x180006715  mov     byte ptr [rbx+30h], 0
0x180006719  lea     rcx, [rbx+32h]; void *
0x18000671d  xor     edx, edx; Val
0x18000671f  mov     r8d, 81h; Size
0x180006725  call    memset_0
0x18000672a  nop
0x18000672b  mov     rcx, rbx; this
0x18000672e  call    ?RuntimeClassInitialize@DiagnosticInvokerStatics@Diagnostics@System@Windows@@QEAAJXZ; Windows::System::Diagnostics::DiagnosticInvokerStatics::RuntimeClassInitialize(void)
0x180006733  mov     esi, eax
0x180006735  mov     rax, [rbx]
0x180006738  test    esi, esi
0x18000673a  jns     short loc_180006750
0x18000673c  mov     rcx, rbx
0x18000673f  mov     rax, [rax+10h]
0x180006743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006748  nop
0x180006749  mov     eax, esi
0x18000674b  jmp     loc_18000680E
0x180006750  mov     rcx, rbx
0x180006753  mov     rax, [rax+8]
0x180006757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000675c  nop
0x18000675d  mov     rax, [rbx]
0x180006760  mov     rcx, rbx
0x180006763  mov     rax, [rax+10h]
0x180006767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000676c  nop
0x18000676d  cmp     dword ptr [rdi], 35h ; '5'
0x180006770  jnz     short loc_180006798
0x180006772  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data2
0x180006778  cmp     [rdi+4], eax
0x18000677b  jnz     short loc_1800067F9
0x18000677d  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4
0x180006783  cmp     [rdi+8], eax
0x180006786  jnz     short loc_1800067F9
0x180006788  mov     eax, dword ptr cs:_GUID_00000035_0000_0000_c000_000000000046.Data4+4
0x18000678e  cmp     [rdi+0Ch], eax
0x180006791  jnz     short loc_1800067F9
0x180006793  mov     rcx, rbx
0x180006796  jmp     short loc_1800067C8
0x180006798  cmp     dword ptr [rdi], 5CFAD8DEh
0x18000679e  jnz     short loc_1800067F9
0x1800067a0  mov     eax, dword ptr cs:_GUID_5cfad8de_f15c_4554_a813_c113c3881b09.Data2
0x1800067a6  cmp     [rdi+4], eax
0x1800067a9  jnz     short loc_1800067F9
0x1800067ab  mov     eax, dword ptr cs:_GUID_5cfad8de_f15c_4554_a813_c113c3881b09.Data4
0x1800067b1  cmp     [rdi+8], eax
0x1800067b4  jnz     short loc_1800067F9
0x1800067b6  mov     eax, dword ptr cs:_GUID_5cfad8de_f15c_4554_a813_c113c3881b09.Data4+4
0x1800067bc  cmp     [rdi+0Ch], eax
0x1800067bf  jnz     short loc_1800067F9
0x1800067c1  mov     rcx, rbx
0x1800067c4  add     rbx, 8
0x1800067c8  mov     [r14], rbx
0x1800067cb  test    byte ptr [r15], 4
0x1800067cf  jnz     short loc_1800067EB
0x1800067d1  mov     r8d, 7FFFFFFFh
0x1800067d7  jmp     short loc_1800067E3
0x1800067d9  lea     edx, [rax+1]
0x1800067dc  lock cmpxchg [rcx+14h], edx
0x1800067e1  jz      short loc_1800067EB
0x1800067e3  mov     eax, [rcx+14h]
0x1800067e6  cmp     eax, r8d
0x1800067e9  jnz     short loc_1800067D9
0x1800067eb  mov     eax, [r15]
0x1800067ee  mov     [rcx+28h], eax
0x1800067f1  mov     [rcx+20h], rbp
0x1800067f5  xor     eax, eax
0x1800067f7  jmp     short loc_18000680E
0x1800067f9  mov     rax, [rbx]
0x1800067fc  mov     rcx, rbx
0x1800067ff  mov     rax, [rax+10h]
0x180006803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006808  nop
0x180006809  mov     eax, 80004002h
0x18000680e  add     rsp, 28h
0x180006812  pop     r15
0x180006814  pop     r14
0x180006816  pop     rdi
0x180006817  pop     rsi
0x180006818  pop     rbp
0x180006819  pop     rbx
0x18000681a  retn
```
