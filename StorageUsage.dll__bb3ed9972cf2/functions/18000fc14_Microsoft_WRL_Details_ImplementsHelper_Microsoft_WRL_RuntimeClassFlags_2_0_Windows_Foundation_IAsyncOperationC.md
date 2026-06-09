# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>(void)

- ea: `0x18000fc14`
- end: `0x18000fca5`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$0A@U?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `145`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000dd98`

## callees

- `0x18000fc14`
- `0x180013ae4`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000fc5b`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x18000fc5b`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>,Microsoft::WRL::FtmBase>(
        _QWORD *a1)
{
  _QWORD *v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *a1 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>::`vftable';
  a1[1] = &Microsoft::WRL::FtmBase::`vftable';
  v2 = a1 + 4;
  a1[4] = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, _QWORD *))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppunkMarshal);
  return a1;
}

```

## disassembly

```asm
0x18000fc14  push    rbx
0x18000fc16  push    rsi
0x18000fc17  push    rdi
0x18000fc18  push    r14
0x18000fc1a  sub     rsp, 28h
0x18000fc1e  mov     rsi, rcx
0x18000fc21  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAU?$IVectorView@PEAVUser@System@Windows@@@Collections@Foundation@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Foundation::Collections::IVectorView<Windows::System::User *> *>::`vftable'
0x18000fc28  mov     [rcx], rax
0x18000fc2b  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x18000fc32  mov     [rcx+8], rax
0x18000fc36  lea     r14, [rcx+20h]
0x18000fc3a  mov     qword ptr [r14], 0
0x18000fc41  mov     [rsp+48h+ppunkMarshal], 0
0x18000fc4a  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000fc4f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000fc54  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x18000fc59  xor     ecx, ecx; punkOuter
0x18000fc5b  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x18000fc61  test    eax, eax
0x18000fc63  js      short loc_18000FC8E
0x18000fc65  mov     rbx, [rsp+48h+ppunkMarshal]
0x18000fc6a  mov     rax, [rbx]
0x18000fc6d  mov     rdi, [rax]
0x18000fc70  mov     rcx, r14
0x18000fc73  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000fc78  mov     r8, r14
0x18000fc7b  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x18000fc82  mov     rcx, rbx
0x18000fc85  mov     rax, rdi
0x18000fc88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc8d  nop
0x18000fc8e  lea     rcx, [rsp+48h+ppunkMarshal]
0x18000fc93  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18000fc98  mov     rax, rsi
0x18000fc9b  add     rsp, 28h
0x18000fc9f  pop     r14
0x18000fca1  pop     rdi
0x18000fca2  pop     rsi
0x18000fca3  pop     rbx
0x18000fca4  retn
```
