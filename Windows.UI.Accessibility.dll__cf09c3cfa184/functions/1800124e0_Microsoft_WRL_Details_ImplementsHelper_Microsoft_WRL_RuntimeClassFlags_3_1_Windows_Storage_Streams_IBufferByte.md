# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>(void)

- ea: `0x1800124e0`
- end: `0x180012571`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIBufferByteAccess@Streams@Storage@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012988`

## callees

- `0x18000a6e0`
- `0x1800124e0`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180012527`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180012527`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800124e0  push    rbx
0x1800124e2  push    rsi
0x1800124e3  push    rdi
0x1800124e4  push    r14
0x1800124e6  sub     rsp, 28h
0x1800124ea  mov     rsi, rcx
0x1800124ed  lea     rax, ??_7IBufferByteAccess@Streams@Storage@Windows@@6B@; const Windows::Storage::Streams::IBufferByteAccess::`vftable'
0x1800124f4  mov     [rcx], rax
0x1800124f7  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800124fe  mov     [rcx+8], rax
0x180012502  lea     r14, [rcx+20h]
0x180012506  mov     qword ptr [r14], 0
0x18001250d  mov     [rsp+48h+ppunkMarshal], 0
0x180012516  lea     rcx, [rsp+48h+ppunkMarshal]
0x18001251b  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012520  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180012525  xor     ecx, ecx; punkOuter
0x180012527  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18001252d  test    eax, eax
0x18001252f  js      short loc_18001255A
0x180012531  mov     rbx, [rsp+48h+ppunkMarshal]
0x180012536  mov     rax, [rbx]
0x180012539  mov     rdi, [rax]
0x18001253c  mov     rcx, r14
0x18001253f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012544  mov     r8, r14
0x180012547  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18001254e  mov     rcx, rbx
0x180012551  mov     rax, rdi
0x180012554  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012559  nop
0x18001255a  lea     rcx, [rsp+48h+ppunkMarshal]
0x18001255f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180012564  mov     rax, rsi
0x180012567  add     rsp, 28h
0x18001256b  pop     r14
0x18001256d  pop     rdi
0x18001256e  pop     rsi
0x18001256f  pop     rbx
0x180012570  retn
```
