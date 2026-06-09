# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>(void)

- ea: `0x180011cc4`
- end: `0x180011d55`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `145`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000fa98`
- `0x18000fbc0`
- `0x18000fce8`
- `0x180024fe0`

## callees

- `0x180009fc0`
- `0x180011cc4`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180011d0b`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180011d0b`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>(
        _QWORD *a1)
{
  _QWORD *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *a1 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>::`vftable';
  a1[1] = &Microsoft::WRL::FtmBase::`vftable';
  v2 = a1 + 4;
  a1[4] = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, _QWORD *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  return a1;
}

```

## disassembly

```asm
0x180011cc4  push    rbx
0x180011cc6  push    rsi
0x180011cc7  push    rdi
0x180011cc8  push    r14
0x180011cca  sub     rsp, 28h
0x180011cce  mov     rsi, rcx
0x180011cd1  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>::`vftable'
0x180011cd8  mov     [rcx], rax
0x180011cdb  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180011ce2  mov     [rcx+8], rax
0x180011ce6  lea     r14, [rcx+20h]
0x180011cea  mov     qword ptr [r14], 0
0x180011cf1  mov     [rsp+48h+ppunkMarshal], 0
0x180011cfa  lea     rcx, [rsp+48h+ppunkMarshal]
0x180011cff  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011d04  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180011d09  xor     ecx, ecx; punkOuter
0x180011d0b  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180011d11  test    eax, eax
0x180011d13  js      short loc_180011D3E
0x180011d15  mov     rbx, [rsp+48h+ppunkMarshal]
0x180011d1a  mov     rax, [rbx]
0x180011d1d  mov     rdi, [rax]
0x180011d20  mov     rcx, r14
0x180011d23  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011d28  mov     r8, r14
0x180011d2b  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180011d32  mov     rcx, rbx
0x180011d35  mov     rax, rdi
0x180011d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d3d  nop
0x180011d3e  lea     rcx, [rsp+48h+ppunkMarshal]
0x180011d43  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180011d48  mov     rax, rsi
0x180011d4b  add     rsp, 28h
0x180011d4f  pop     r14
0x180011d51  pop     rdi
0x180011d52  pop     rsi
0x180011d53  pop     rbx
0x180011d54  retn
```
