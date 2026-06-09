# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>(void)

- ea: `0x140009a84`
- end: `0x140009b15`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$IAsyncOperationWithProgressCompletedHandler@PEAVHttpResponseMessage@Http@Web@Windows@@UHttpProgress@234@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `145`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140008850`
- `0x140008984`

## callees

- `0x140009a84`
- `0x14000d49c`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140009acb`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x140009acb`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<Windows::Web::Http::HttpResponseMessage *,Windows::Web::Http::HttpProgress>,Microsoft::WRL::FtmBase>(
        _QWORD *a1)
{
  _QWORD *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *a1 = &Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>::`vftable';
  a1[1] = &Microsoft::WRL::FtmBase::`vftable';
  v2 = a1 + 4;
  a1[4] = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, _QWORD *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(&ppunkMarshal);
  return a1;
}

```

## disassembly

```asm
0x140009a84  push    rbx
0x140009a86  push    rsi
0x140009a87  push    rdi
0x140009a88  push    r14
0x140009a8a  sub     rsp, 28h
0x140009a8e  mov     rsi, rcx
0x140009a91  lea     rax, ??_7?$IAsyncOperationWithProgressCompletedHandler@PEAUHSTRING__@@_K@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationWithProgressCompletedHandler<HSTRING__ *,unsigned __int64>::`vftable'
0x140009a98  mov     [rcx], rax
0x140009a9b  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x140009aa2  mov     [rcx+8], rax
0x140009aa6  lea     r14, [rcx+20h]
0x140009aaa  mov     qword ptr [r14], 0
0x140009ab1  mov     [rsp+48h+ppunkMarshal], 0
0x140009aba  lea     rcx, [rsp+48h+ppunkMarshal]
0x140009abf  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x140009ac4  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x140009ac9  xor     ecx, ecx; punkOuter
0x140009acb  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x140009ad1  test    eax, eax
0x140009ad3  js      short loc_140009AFE
0x140009ad5  mov     rbx, [rsp+48h+ppunkMarshal]
0x140009ada  mov     rax, [rbx]
0x140009add  mov     rdi, [rax]
0x140009ae0  mov     rcx, r14
0x140009ae3  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x140009ae8  mov     r8, r14
0x140009aeb  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x140009af2  mov     rcx, rbx
0x140009af5  mov     rax, rdi
0x140009af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009afd  nop
0x140009afe  lea     rcx, [rsp+48h+ppunkMarshal]
0x140009b03  call    ?InternalRelease@?$ComPtr@UIDynamicAppUriHandler@StateRepository@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IDynamicAppUriHandler>::InternalRelease(void)
0x140009b08  mov     rax, rsi
0x140009b0b  add     rsp, 28h
0x140009b0f  pop     r14
0x140009b11  pop     rdi
0x140009b12  pop     rsi
0x140009b13  pop     rbx
0x140009b14  retn
```
