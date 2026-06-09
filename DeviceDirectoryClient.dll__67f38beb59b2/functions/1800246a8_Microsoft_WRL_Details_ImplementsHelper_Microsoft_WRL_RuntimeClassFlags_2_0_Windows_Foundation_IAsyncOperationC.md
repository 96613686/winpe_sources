# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>(void)

- ea: `0x1800246a8`
- end: `0x180024739`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$IAsyncOperationCompletedHandler@PEAVWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `145`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800243d8`
- `0x180025584`
- `0x1800256b8`
- `0x1800257ec`

## callees

- `0x180004060`
- `0x1800246a8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800246ef`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800246ef`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Security::Authentication::Web::Core::WebTokenRequestResult *>,Microsoft::WRL::FtmBase>(
        _QWORD *a1)
{
  _QWORD *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *a1 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>::`vftable';
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
0x1800246a8  push    rbx
0x1800246aa  push    rsi
0x1800246ab  push    rdi
0x1800246ac  push    r14
0x1800246ae  sub     rsp, 28h
0x1800246b2  mov     rsi, rcx
0x1800246b5  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVUserHostIdentity@WebAuthentication@Security@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::Security::WebAuthentication::UserHostIdentity *>::`vftable'
0x1800246bc  mov     [rcx], rax
0x1800246bf  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800246c6  mov     [rcx+8], rax
0x1800246ca  lea     r14, [rcx+20h]
0x1800246ce  mov     qword ptr [r14], 0
0x1800246d5  mov     [rsp+48h+ppunkMarshal], 0
0x1800246de  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800246e3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800246e8  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800246ed  xor     ecx, ecx; punkOuter
0x1800246ef  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800246f5  test    eax, eax
0x1800246f7  js      short loc_180024722
0x1800246f9  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800246fe  mov     rax, [rbx]
0x180024701  mov     rdi, [rax]
0x180024704  mov     rcx, r14
0x180024707  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002470c  mov     r8, r14
0x18002470f  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180024716  mov     rcx, rbx
0x180024719  mov     rax, rdi
0x18002471c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024721  nop
0x180024722  lea     rcx, [rsp+48h+ppunkMarshal]
0x180024727  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002472c  mov     rax, rsi
0x18002472f  add     rsp, 28h
0x180024733  pop     r14
0x180024735  pop     rdi
0x180024736  pop     rsi
0x180024737  pop     rbx
0x180024738  retn
```
