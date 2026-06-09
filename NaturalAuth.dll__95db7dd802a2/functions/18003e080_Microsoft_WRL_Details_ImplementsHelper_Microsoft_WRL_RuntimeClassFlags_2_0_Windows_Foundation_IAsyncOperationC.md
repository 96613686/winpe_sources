# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>(void)

- ea: `0x18003e080`
- end: `0x18003e111`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `145`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18003d9f8`

## callees

- `0x180014e7c`
- `0x18003e080`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18003e0c7`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18003e0c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>,Microsoft::WRL::FtmBase>(
        _QWORD *a1)
{
  _QWORD *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *a1 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>::`vftable';
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
0x18003e080  push    rbx
0x18003e082  push    rsi
0x18003e083  push    rdi
0x18003e084  push    r14
0x18003e086  sub     rsp, 28h
0x18003e08a  mov     rsi, rcx
0x18003e08d  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVGeoposition@Geolocation@Devices@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Devices::Geolocation::Geoposition *>::`vftable'
0x18003e094  mov     [rcx], rax
0x18003e097  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18003e09e  mov     [rcx+8], rax
0x18003e0a2  lea     r14, [rcx+20h]
0x18003e0a6  mov     qword ptr [r14], 0
0x18003e0ad  mov     [rsp+48h+ppunkMarshal], 0
0x18003e0b6  lea     rcx, [rsp+48h+ppunkMarshal]
0x18003e0bb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e0c0  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18003e0c5  xor     ecx, ecx; punkOuter
0x18003e0c7  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18003e0cd  test    eax, eax
0x18003e0cf  js      short loc_18003E0FA
0x18003e0d1  mov     rbx, [rsp+48h+ppunkMarshal]
0x18003e0d6  mov     rax, [rbx]
0x18003e0d9  mov     rdi, [rax]
0x18003e0dc  mov     rcx, r14
0x18003e0df  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e0e4  mov     r8, r14
0x18003e0e7  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18003e0ee  mov     rcx, rbx
0x18003e0f1  mov     rax, rdi
0x18003e0f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003e0f9  nop
0x18003e0fa  lea     rcx, [rsp+48h+ppunkMarshal]
0x18003e0ff  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003e104  mov     rax, rsi
0x18003e107  add     rsp, 28h
0x18003e10b  pop     r14
0x18003e10d  pop     rdi
0x18003e10e  pop     rsi
0x18003e10f  pop     rbx
0x18003e110  retn
```
