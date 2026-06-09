# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>(void)

- ea: `0x14000aa7c`
- end: `0x14000ab0c`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14000a250`

## callees

- `0x1400068e8`
- `0x14000aa7c`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x14000aac3`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x14000aac3`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>,Microsoft::WRL::FtmBase>(
        _QWORD *a1)
{
  _QWORD *v1; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  v1 = a1 + 4;
  ppunkMarshal = 0;
  *a1 = &Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>::`vftable';
  a1[1] = &Microsoft::WRL::FtmBase::`vftable';
  a1[4] = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v1);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, _QWORD *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v1);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  return a1;
}

```

## disassembly

```asm
0x14000aa7c  push    rbx
0x14000aa7e  push    rsi
0x14000aa7f  push    rdi
0x14000aa80  push    r14
0x14000aa82  sub     rsp, 28h
0x14000aa86  lea     r14, [rcx+20h]
0x14000aa8a  mov     [rsp+48h+ppunkMarshal], 0
0x14000aa93  lea     rax, ??_7?$ITypedEventHandler@PEAVUserWatcher@System@Windows@@PEAVUserChangedEventArgs@23@@Foundation@Windows@@6B@; const Windows::Foundation::ITypedEventHandler<Windows::System::UserWatcher *,Windows::System::UserChangedEventArgs *>::`vftable'
0x14000aa9a  mov     rsi, rcx
0x14000aa9d  mov     [rcx], rax
0x14000aaa0  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x14000aaa7  mov     [rcx+8], rax
0x14000aaab  lea     rcx, [rsp+48h+ppunkMarshal]
0x14000aab0  mov     qword ptr [r14], 0
0x14000aab7  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000aabc  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x14000aac1  xor     ecx, ecx; punkOuter
0x14000aac3  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x14000aac9  test    eax, eax
0x14000aacb  js      short loc_14000AAF5
0x14000aacd  mov     rbx, [rsp+48h+ppunkMarshal]
0x14000aad2  mov     rcx, r14
0x14000aad5  mov     rax, [rbx]
0x14000aad8  mov     rdi, [rax]
0x14000aadb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000aae0  mov     r8, r14
0x14000aae3  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x14000aaea  mov     rcx, rbx
0x14000aaed  mov     rax, rdi
0x14000aaf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aaf5  lea     rcx, [rsp+48h+ppunkMarshal]
0x14000aafa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x14000aaff  mov     rax, rsi
0x14000ab02  add     rsp, 28h
0x14000ab06  pop     r14
0x14000ab08  pop     rdi
0x14000ab09  pop     rsi
0x14000ab0a  pop     rbx
0x14000ab0b  retn
```
