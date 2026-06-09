# Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions::PlatformDiagnosticActions(void)

- ea: `0x180006e30`
- end: `0x180006f57`
- name: `??0PlatformDiagnosticActions@TraceReporting@Diagnostics@System@Windows@@QEAA@XZ`
- size: `295`
- prototype: `Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions *__fastcall(Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006730`

## callees

- `0x180006e30`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180006e62`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180006e62`

## pseudocode

```c
Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions *__fastcall Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions::PlatformDiagnosticActions(
        Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions *this)
{
  __int64 *v2; // rsi
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v5; // rcx
  LPUNKNOWN v6; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *((_QWORD *)this + 1) = &Microsoft::WRL::FtmBase::`vftable';
  v2 = (__int64 *)((char *)this + 32);
  *((_QWORD *)this + 4) = 0;
  ppunkMarshal = 0;
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    v5 = *v2;
    if ( *v2 )
    {
      *v2 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
    }
    ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64 *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  v6 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v6->lpVtbl->Release)(v6);
  }
  *((_DWORD *)this + 17) = 1;
  *(_QWORD *)this = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable';
  *((_QWORD *)this + 1) = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>>'};
  *((_QWORD *)this + 5) = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>>'};
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 22) = 4;
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions::`vftable';
  *((_QWORD *)this + 1) = &Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>>'};
  *((_QWORD *)this + 5) = &Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>>'};
  *((_QWORD *)this + 13) = 0;
  *((_QWORD *)this + 12) = &Microsoft::Diagnostics::UtcWrapperBase::`vftable';
  return this;
}

```

## disassembly

```asm
0x180006e30  push    rbx
0x180006e32  push    rbp
0x180006e33  push    rsi
0x180006e34  push    rdi
0x180006e35  sub     rsp, 28h
0x180006e39  mov     rdi, rcx
0x180006e3c  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180006e43  mov     [rcx+8], rax
0x180006e47  lea     rsi, [rcx+20h]
0x180006e4b  mov     qword ptr [rsi], 0
0x180006e52  mov     [rsp+48h+ppunkMarshal], 0
0x180006e5b  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180006e60  xor     ecx, ecx; punkOuter
0x180006e62  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180006e68  test    eax, eax
0x180006e6a  js      short loc_180006EA9
0x180006e6c  mov     rbx, [rsp+48h+ppunkMarshal]
0x180006e71  mov     rax, [rbx]
0x180006e74  mov     rbp, [rax]
0x180006e77  mov     rcx, [rsi]
0x180006e7a  test    rcx, rcx
0x180006e7d  jz      short loc_180006E93
0x180006e7f  mov     qword ptr [rsi], 0
0x180006e86  mov     rdx, [rcx]
0x180006e89  mov     rax, [rdx+10h]
0x180006e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e92  nop
0x180006e93  mov     r8, rsi
0x180006e96  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180006e9d  mov     rcx, rbx
0x180006ea0  mov     rax, rbp
0x180006ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea8  nop
0x180006ea9  mov     rcx, [rsp+48h+ppunkMarshal]
0x180006eae  test    rcx, rcx
0x180006eb1  jz      short loc_180006EC9
0x180006eb3  mov     [rsp+48h+ppunkMarshal], 0
0x180006ebc  mov     rax, [rcx]
0x180006ebf  mov     rax, [rax+10h]
0x180006ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ec8  nop
0x180006ec9  mov     dword ptr [rdi+44h], 1
0x180006ed0  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x180006ed7  mov     [rdi], rax
0x180006eda  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@Details@23@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>>'}
0x180006ee1  mov     [rdi+8], rax
0x180006ee5  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@234@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>>'}
0x180006eec  mov     [rdi+28h], rax
0x180006ef0  mov     qword ptr [rdi+50h], 0
0x180006ef8  mov     dword ptr [rdi+58h], 4
0x180006eff  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180006f06  test    rcx, rcx
0x180006f09  jz      short loc_180006F18
0x180006f0b  mov     rax, [rcx]
0x180006f0e  mov     rax, [rax+8]
0x180006f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f17  nop
0x180006f18  lea     rax, ??_7PlatformDiagnosticActions@TraceReporting@Diagnostics@System@Windows@@6B@; const Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions::`vftable'
0x180006f1f  mov     [rdi], rax
0x180006f22  lea     rax, ??_7PlatformDiagnosticActions@TraceReporting@Diagnostics@System@Windows@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>>'}
0x180006f29  mov     [rdi+8], rax
0x180006f2d  lea     rax, ??_7PlatformDiagnosticActions@TraceReporting@Diagnostics@System@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@234@@Details@WRL@Microsoft@@@; const Windows::System::Diagnostics::TraceReporting::PlatformDiagnosticActions::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>>'}
0x180006f34  mov     [rdi+28h], rax
0x180006f38  mov     qword ptr [rdi+68h], 0
0x180006f40  lea     rax, ??_7UtcWrapperBase@Diagnostics@Microsoft@@6B@; const Microsoft::Diagnostics::UtcWrapperBase::`vftable'
0x180006f47  mov     [rdi+60h], rax
0x180006f4b  mov     rax, rdi
0x180006f4e  add     rsp, 28h
0x180006f52  pop     rdi
0x180006f53  pop     rsi
0x180006f54  pop     rbp
0x180006f55  pop     rbx
0x180006f56  retn
```
