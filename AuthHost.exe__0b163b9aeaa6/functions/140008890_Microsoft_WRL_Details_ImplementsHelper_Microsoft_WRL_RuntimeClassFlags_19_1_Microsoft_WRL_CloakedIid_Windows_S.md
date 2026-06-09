# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>(void)

- ea: `0x140008890`
- end: `0x140008921`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `145`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400087b8`

## callees

- `0x140003a8c`
- `0x140008890`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1400088d7`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1400088d7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>(
        _QWORD *a1)
{
  _QWORD *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *a1 = &Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowActivatedEventArgs *>::`vftable';
  a1[2] = &Microsoft::WRL::FtmBase::`vftable';
  v2 = a1 + 5;
  a1[5] = 0;
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
0x140008890  push    rbx
0x140008892  push    rsi
0x140008893  push    rdi
0x140008894  push    r14
0x140008896  sub     rsp, 28h
0x14000889a  mov     rsi, rcx
0x14000889d  lea     rax, ??_7?$ITypedEventHandler@PEAVCoreWindow@Core@UI@Windows@@PEAVWindowActivatedEventArgs@234@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::UI::Core::CoreWindow *,Windows::UI::Core::WindowActivatedEventArgs *>::`vftable'
0x1400088a4  mov     [rcx], rax
0x1400088a7  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1400088ae  mov     [rcx+10h], rax
0x1400088b2  lea     r14, [rcx+28h]
0x1400088b6  mov     qword ptr [r14], 0
0x1400088bd  mov     [rsp+48h+ppunkMarshal], 0
0x1400088c6  lea     rcx, [rsp+48h+ppunkMarshal]
0x1400088cb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400088d0  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1400088d5  xor     ecx, ecx; punkOuter
0x1400088d7  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1400088dd  test    eax, eax
0x1400088df  js      short loc_14000890A
0x1400088e1  mov     rbx, [rsp+48h+ppunkMarshal]
0x1400088e6  mov     rax, [rbx]
0x1400088e9  mov     rdi, [rax]
0x1400088ec  mov     rcx, r14
0x1400088ef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1400088f4  mov     r8, r14
0x1400088f7  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1400088fe  mov     rcx, rbx
0x140008901  mov     rax, rdi
0x140008904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008909  nop
0x14000890a  lea     rcx, [rsp+48h+ppunkMarshal]
0x14000890f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x140008914  mov     rax, rsi
0x140008917  add     rsp, 28h
0x14000891b  pop     r14
0x14000891d  pop     rdi
0x14000891e  pop     rsi
0x14000891f  pop     rbx
0x140008920  retn
```
