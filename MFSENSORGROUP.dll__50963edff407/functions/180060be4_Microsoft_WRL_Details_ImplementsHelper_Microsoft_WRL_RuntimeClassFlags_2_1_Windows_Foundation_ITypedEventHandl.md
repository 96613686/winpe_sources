# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::Internal::System::RelativePanelDirectionTracker *,IInspectable *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::Internal::System::RelativePanelDirectionTracker *,IInspectable *>,Microsoft::WRL::FtmBase>(void)

- ea: `0x180060be4`
- end: `0x180060c74`
- name: `??0?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ITypedEventHandler@PEAVRelativePanelDirectionTracker@System@Internal@Windows@@PEAUIInspectable@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@QEAA@XZ`
- size: `144`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18006088c`
- `0x180060964`

## callees

- `0x180046f7c`
- `0x180060be4`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180060c2b`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x180060c2b`

## pseudocode

```c
_QWORD *__fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::Internal::System::RelativePanelDirectionTracker *,IInspectable *>,Microsoft::WRL::FtmBase>::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Windows::Foundation::ITypedEventHandler<Windows::Internal::System::RelativePanelDirectionTracker *,IInspectable *>,Microsoft::WRL::FtmBase>(
        _QWORD *a1)
{
  _QWORD *v1; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  v1 = a1 + 4;
  ppunkMarshal = 0;
  *a1 = &Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::System::RelativePanelDirectionTracker *>::`vftable';
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
0x180060be4  push    rbx
0x180060be6  push    rsi
0x180060be7  push    rdi
0x180060be8  push    r14
0x180060bea  sub     rsp, 28h
0x180060bee  lea     r14, [rcx+20h]
0x180060bf2  mov     [rsp+48h+ppunkMarshal], 0
0x180060bfb  lea     rax, ??_7?$IAsyncOperationCompletedHandler@PEAVRelativePanelDirectionTracker@System@Internal@Windows@@@Foundation@Windows@@6B@; const Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Internal::System::RelativePanelDirectionTracker *>::`vftable'
0x180060c02  mov     rsi, rcx
0x180060c05  mov     [rcx], rax
0x180060c08  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x180060c0f  mov     [rcx+8], rax
0x180060c13  lea     rcx, [rsp+48h+ppunkMarshal]
0x180060c18  mov     qword ptr [r14], 0
0x180060c1f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060c24  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x180060c29  xor     ecx, ecx; punkOuter
0x180060c2b  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x180060c31  test    eax, eax
0x180060c33  js      short loc_180060C5D
0x180060c35  mov     rbx, [rsp+48h+ppunkMarshal]
0x180060c3a  mov     rcx, r14
0x180060c3d  mov     rax, [rbx]
0x180060c40  mov     rdi, [rax]
0x180060c43  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060c48  mov     r8, r14
0x180060c4b  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x180060c52  mov     rcx, rbx
0x180060c55  mov     rax, rdi
0x180060c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060c5d  lea     rcx, [rsp+48h+ppunkMarshal]
0x180060c62  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180060c67  mov     rax, rsi
0x180060c6a  add     rsp, 28h
0x180060c6e  pop     r14
0x180060c70  pop     rdi
0x180060c71  pop     rsi
0x180060c72  pop     rbx
0x180060c73  retn
```
