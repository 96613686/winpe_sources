# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory1,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory1,Microsoft::WRL::FtmBase>(void)

- ea: `0x1800a2740`
- end: `0x1800a27fb`
- name: `??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIXpsRasterizationFactory1@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ`
- size: `187`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a1b74`

## callees

- `0x1800a0de8`
- `0x1800a2740`
- `0x1800c3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800a277d`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800a277d`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory1,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory1,Microsoft::WRL::FtmBase>(
        __int64 a1)
{
  __int64 v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::FtmBase::`vftable';
  v2 = a1 + 32;
  *(_QWORD *)(a1 + 32) = 0;
  ppunkMarshal = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  if ( CoCreateFreeThreadedMarshaler(0, &ppunkMarshal) >= 0 )
  {
    v3 = ppunkMarshal;
    QueryInterface = ppunkMarshal->lpVtbl->QueryInterface;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v2);
    ((void (__fastcall *)(LPUNKNOWN, GUID *, __int64))QueryInterface)(
      v3,
      &GUID_00000003_0000_0000_c000_000000000046,
      v2);
  }
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&ppunkMarshal);
  *(_DWORD *)(a1 + 44) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory1,Microsoft::WRL::FtmBase>::`vftable'{for `IXpsRasterizationFactory1'};
  *(_QWORD *)(a1 + 8) = &xpsras::CRasterizerFactory1::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return a1;
}

```

## disassembly

```asm
0x1800a2740  push    rbx
0x1800a2742  push    rsi
0x1800a2743  push    rdi
0x1800a2744  push    r14
0x1800a2746  sub     rsp, 28h
0x1800a274a  mov     rsi, rcx
0x1800a274d  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800a2754  mov     [rcx+8], rax
0x1800a2758  lea     r14, [rcx+20h]
0x1800a275c  mov     qword ptr [r14], 0
0x1800a2763  mov     [rsp+48h+ppunkMarshal], 0
0x1800a276c  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800a2771  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a2776  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800a277b  xor     ecx, ecx; punkOuter
0x1800a277d  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800a2783  test    eax, eax
0x1800a2785  js      short loc_1800A27B0
0x1800a2787  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800a278c  mov     rax, [rbx]
0x1800a278f  mov     rdi, [rax]
0x1800a2792  mov     rcx, r14
0x1800a2795  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a279a  mov     r8, r14
0x1800a279d  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800a27a4  mov     rcx, rbx
0x1800a27a7  mov     rax, rdi
0x1800a27aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a27af  nop
0x1800a27b0  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800a27b5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a27ba  mov     dword ptr [rsi+2Ch], 1
0x1800a27c1  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIXpsRasterizationFactory1@@VFtmBase@23@@WRL@Microsoft@@6BIXpsRasterizationFactory1@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory1,Microsoft::WRL::FtmBase>::`vftable'{for `IXpsRasterizationFactory1'}
0x1800a27c8  mov     [rsi], rax
0x1800a27cb  lea     rax, ??_7CRasterizerFactory1@xpsras@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const xpsras::CRasterizerFactory1::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800a27d2  mov     [rsi+8], rax
0x1800a27d6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800a27dd  test    rcx, rcx
0x1800a27e0  jz      short loc_1800A27EE
0x1800a27e2  mov     rax, [rcx]
0x1800a27e5  mov     rax, [rax+8]
0x1800a27e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a27ee  mov     rax, rsi
0x1800a27f1  add     rsp, 28h
0x1800a27f5  pop     r14
0x1800a27f7  pop     rdi
0x1800a27f8  pop     rsi
0x1800a27f9  pop     rbx
0x1800a27fa  retn
```
