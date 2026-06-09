# Microsoft::WRL::FtmBase::FtmBase(void)

- ea: `0x1800695e4`
- end: `0x180069680`
- name: `??0FtmBase@WRL@Microsoft@@QEAA@XZ`
- size: `156`
- prototype: `__int64 __fastcall(Microsoft::WRL::FtmBase *__hidden this)`
- caller_count: `8`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180068304`
- `0x180068c84`
- `0x1800691b8`
- `0x1800695c0`
- `0x18006b16c`
- `0x1800c5258`
- `0x1800c5304`
- `0x1800c6280`

## callees

- `0x18001df58`
- `0x1800695e4`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180069620`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180069620`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
Microsoft::WRL::FtmBase *__fastcall Microsoft::WRL::FtmBase::FtmBase(Microsoft::WRL::FtmBase *this)
{
  char *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN v5; // rcx
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)this = &Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&wchar_t const near * const Windows::System::DispatcherQueueAsyncHelperName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&wchar_t const near * const Windows::System::DispatcherQueueAsyncHelperName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'};
  v2 = (char *)this + 24;
  *((_QWORD *)this + 3) = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, char *))QueryInterface)(v3, &GUID_00000003_0000_0000_c000_000000000046, v2);
  }
  v5 = ppunkMarshal;
  if ( ppunkMarshal )
  {
    ppunkMarshal = 0;
    ((void (__fastcall *)(LPUNKNOWN))v5->lpVtbl->Release)(v5);
  }
  return this;
}

```

## disassembly

```asm
0x1800695e4  push    rbx
0x1800695e6  push    rsi
0x1800695e7  push    rdi
0x1800695e8  push    r14
0x1800695ea  sub     rsp, 28h
0x1800695ee  mov     rsi, rcx
0x1800695f1  lea     rax, ??_7?$AsyncBaseFTM@UIAsyncActionCompletedHandler@Foundation@Windows@@$00U?$AsyncCausalityOptions@$1?DispatcherQueueAsyncHelperName@System@Windows@@3QB_WB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@WRL@Microsoft@@@Internal@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@V?$AsyncBase@UIAsyncActionCompletedHandler@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncCausalityOptions@$1?DispatcherQueueAsyncHelperName@System@Windows@@3QB_WB$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@@Details@23@VFtmBase@23@@234@@Details@WRL@Microsoft@@@; const Windows::Internal::AsyncBaseFTM<Windows::Foundation::IAsyncActionCompletedHandler,1,Microsoft::WRL::AsyncCausalityOptions<&wchar_t const near * const Windows::System::DispatcherQueueAsyncHelperName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncCausalityOptions<&wchar_t const near * const Windows::System::DispatcherQueueAsyncHelperName,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>>,Microsoft::WRL::FtmBase>>'}
0x1800695f8  mov     [rcx], rax
0x1800695fb  lea     r14, [rcx+18h]
0x1800695ff  mov     qword ptr [r14], 0
0x180069606  mov     [rsp+48h+ppunkMarshal], 0
0x18006960f  lea     rcx, [rsp+48h+ppunkMarshal]
0x180069614  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180069619  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18006961e  xor     ecx, ecx; punkOuter
0x180069620  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180069626  test    eax, eax
0x180069628  js      short loc_180069653
0x18006962a  mov     rbx, [rsp+48h+ppunkMarshal]
0x18006962f  mov     rax, [rbx]
0x180069632  mov     rdi, [rax]
0x180069635  mov     rcx, r14
0x180069638  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18006963d  mov     r8, r14
0x180069640  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180069647  mov     rcx, rbx
0x18006964a  mov     rax, rdi
0x18006964d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069652  nop
0x180069653  mov     rcx, [rsp+48h+ppunkMarshal]
0x180069658  test    rcx, rcx
0x18006965b  jz      short loc_180069673
0x18006965d  mov     [rsp+48h+ppunkMarshal], 0
0x180069666  mov     rax, [rcx]
0x180069669  mov     rax, [rax+10h]
0x18006966d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069672  nop
0x180069673  mov     rax, rsi
0x180069676  add     rsp, 28h
0x18006967a  pop     r14
0x18006967c  pop     rdi
0x18006967d  pop     rsi
0x18006967e  pop     rbx
0x18006967f  retn
```
