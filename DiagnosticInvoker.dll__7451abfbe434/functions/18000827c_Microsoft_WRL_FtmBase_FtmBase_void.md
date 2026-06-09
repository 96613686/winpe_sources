# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x18000827c`
- end: `0x180008320`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `164`
- prototype: `Microsoft::WRL::FtmBase *__fastcall(Microsoft::WRL::FtmBase *this)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180007efc`
- `0x1800081c4`
- `0x18000edf0`

## callees

- `0x18000827c`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800082ad`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800082ad`

## pseudocode

```c
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  __int64 *v2; // rdi
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbp
  __int64 v5; // rcx
  LPUNKNOWN v6; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,enum Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  v2 = (__int64 *)((char *)this + 24);
  *((_QWORD *)this + 3) = 0;
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
  return this;
}

```

## disassembly

```asm
0x18000827c  push    rbx
0x18000827e  push    rbp
0x18000827f  push    rsi
0x180008280  push    rdi
0x180008281  sub     rsp, 28h
0x180008285  mov     rsi, rcx
0x180008288  lea     rax, ??_7?$AsyncBaseFTM@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@U?$IAsyncOperationWithProgressCompletedHandler@PEAVDiagnosticActionResult@Diagnostics@System@Windows@@W4DiagnosticActionState@234@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::System::Diagnostics::DiagnosticActionResult *,Windows::System::Diagnostics::DiagnosticActionState>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x18000828f  mov     [rcx], rax
0x180008292  lea     rdi, [rcx+18h]
0x180008296  mov     qword ptr [rdi], 0
0x18000829d  mov     [rsp+48h+ppunkMarshal], 0
0x1800082a6  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800082ab  xor     ecx, ecx; punkOuter
0x1800082ad  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800082b3  test    eax, eax
0x1800082b5  js      short loc_1800082F4
0x1800082b7  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800082bc  mov     rax, [rbx]
0x1800082bf  mov     rbp, [rax]
0x1800082c2  mov     rcx, [rdi]
0x1800082c5  test    rcx, rcx
0x1800082c8  jz      short loc_1800082DE
0x1800082ca  mov     qword ptr [rdi], 0
0x1800082d1  mov     rdx, [rcx]
0x1800082d4  mov     rax, [rdx+10h]
0x1800082d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082dd  nop
0x1800082de  mov     r8, rdi
0x1800082e1  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800082e8  mov     rcx, rbx
0x1800082eb  mov     rax, rbp
0x1800082ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082f3  nop
0x1800082f4  mov     rcx, [rsp+48h+ppunkMarshal]
0x1800082f9  test    rcx, rcx
0x1800082fc  jz      short loc_180008314
0x1800082fe  mov     [rsp+48h+ppunkMarshal], 0
0x180008307  mov     rax, [rcx]
0x18000830a  mov     rax, [rax+10h]
0x18000830e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008313  nop
0x180008314  mov     rax, rsi
0x180008317  add     rsp, 28h
0x18000831b  pop     rdi
0x18000831c  pop     rsi
0x18000831d  pop     rbp
0x18000831e  pop     rbx
0x18000831f  retn
```
