# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>(void)

- ea: `0x18000f41c`
- end: `0x18000f4ad`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIBufferByteAccess@Streams@Storage@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `145`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000fb1c`

## callees

- `0x18000f41c`
- `0x180015c48`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000f463`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000f463`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>(
        _QWORD *a1)
{
  _QWORD *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *a1 = &Windows::Storage::Streams::IBufferByteAccess::`vftable';
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
0x18000f41c  push    rbx
0x18000f41e  push    rsi
0x18000f41f  push    rdi
0x18000f420  push    r14
0x18000f422  sub     rsp, 28h
0x18000f426  mov     rsi, rcx
0x18000f429  lea     rax, ??_7IBufferByteAccess@Streams@Storage@Windows@@6B@; const Windows::Storage::Streams::IBufferByteAccess::`vftable'
0x18000f430  mov     [rcx], rax
0x18000f433  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000f43a  mov     [rcx+8], rax
0x18000f43e  lea     r14, [rcx+20h]
0x18000f442  mov     qword ptr [r14], 0
0x18000f449  mov     [rsp+48h+ppunkMarshal], 0
0x18000f452  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000f457  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f45c  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18000f461  xor     ecx, ecx; punkOuter
0x18000f463  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000f469  test    eax, eax
0x18000f46b  js      short loc_18000F496
0x18000f46d  mov     rbx, [rsp+48h+ppunkMarshal]
0x18000f472  mov     rax, [rbx]
0x18000f475  mov     rdi, [rax]
0x18000f478  mov     rcx, r14
0x18000f47b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f480  mov     r8, r14
0x18000f483  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000f48a  mov     rcx, rbx
0x18000f48d  mov     rax, rdi
0x18000f490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f495  nop
0x18000f496  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000f49b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000f4a0  mov     rax, rsi
0x18000f4a3  add     rsp, 28h
0x18000f4a7  pop     r14
0x18000f4a9  pop     rdi
0x18000f4aa  pop     rsi
0x18000f4ab  pop     rbx
0x18000f4ac  retn
```
