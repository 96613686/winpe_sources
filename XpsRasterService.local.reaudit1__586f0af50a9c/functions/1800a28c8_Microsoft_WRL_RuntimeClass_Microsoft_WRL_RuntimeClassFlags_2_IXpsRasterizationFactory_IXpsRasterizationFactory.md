# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,IXpsRasterizationFactory1,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,IXpsRasterizationFactory1,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>(void)

- ea: `0x1800a28c8`
- end: `0x1800a2999`
- name: `??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIXpsRasterizationFactory@@UIXpsRasterizationFactory1@@UIXpsRasterizationFactory2@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a1e28`

## callees

- `0x1800a0de8`
- `0x1800a28c8`
- `0x1800c3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800a2905`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800a2905`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,IXpsRasterizationFactory1,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,IXpsRasterizationFactory1,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>(
        __int64 a1)
{
  __int64 v2; // r14
  LPUNKNOWN v3; // rbx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rdi
  LPUNKNOWN ppunkMarshal; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)(a1 + 24) = &Microsoft::WRL::FtmBase::`vftable';
  v2 = a1 + 48;
  *(_QWORD *)(a1 + 48) = 0;
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
  *(_DWORD *)(a1 + 60) = 1;
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,IXpsRasterizationFactory1,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>::`vftable'{for `IXpsRasterizationFactory'};
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,IXpsRasterizationFactory1,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IXpsRasterizationFactory1,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>'};
  *(_QWORD *)(a1 + 16) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,IXpsRasterizationFactory1,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>::`vftable'{for `IXpsRasterizationFactory2'};
  *(_QWORD *)(a1 + 24) = &xpsras::XpsRasterizerFactory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return a1;
}

```

## disassembly

```asm
0x1800a28c8  push    rbx
0x1800a28ca  push    rsi
0x1800a28cb  push    rdi
0x1800a28cc  push    r14
0x1800a28ce  sub     rsp, 28h
0x1800a28d2  mov     rsi, rcx
0x1800a28d5  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800a28dc  mov     [rcx+18h], rax
0x1800a28e0  lea     r14, [rcx+30h]
0x1800a28e4  mov     qword ptr [r14], 0
0x1800a28eb  mov     [rsp+48h+ppunkMarshal], 0
0x1800a28f4  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800a28f9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a28fe  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800a2903  xor     ecx, ecx; punkOuter
0x1800a2905  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800a290b  test    eax, eax
0x1800a290d  js      short loc_1800A2938
0x1800a290f  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800a2914  mov     rax, [rbx]
0x1800a2917  mov     rdi, [rax]
0x1800a291a  mov     rcx, r14
0x1800a291d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a2922  mov     r8, r14
0x1800a2925  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800a292c  mov     rcx, rbx
0x1800a292f  mov     rax, rdi
0x1800a2932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2937  nop
0x1800a2938  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800a293d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a2942  mov     dword ptr [rsi+3Ch], 1
0x1800a2949  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIXpsRasterizationFactory@@UIXpsRasterizationFactory1@@UIXpsRasterizationFactory2@@VFtmBase@23@@WRL@Microsoft@@6BIXpsRasterizationFactory@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,IXpsRasterizationFactory1,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>::`vftable'{for `IXpsRasterizationFactory'}
0x1800a2950  mov     [rsi], rax
0x1800a2953  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIXpsRasterizationFactory@@UIXpsRasterizationFactory1@@UIXpsRasterizationFactory2@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIXpsRasterizationFactory1@@UIXpsRasterizationFactory2@@VFtmBase@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,IXpsRasterizationFactory1,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IXpsRasterizationFactory1,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>'}
0x1800a295a  mov     [rsi+8], rax
0x1800a295e  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIXpsRasterizationFactory@@UIXpsRasterizationFactory1@@UIXpsRasterizationFactory2@@VFtmBase@23@@WRL@Microsoft@@6BIXpsRasterizationFactory2@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,IXpsRasterizationFactory1,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>::`vftable'{for `IXpsRasterizationFactory2'}
0x1800a2965  mov     [rsi+10h], rax
0x1800a2969  lea     rax, ??_7XpsRasterizerFactory@xpsras@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const xpsras::XpsRasterizerFactory::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800a2970  mov     [rsi+18h], rax
0x1800a2974  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800a297b  test    rcx, rcx
0x1800a297e  jz      short loc_1800A298C
0x1800a2980  mov     rax, [rcx]
0x1800a2983  mov     rax, [rax+8]
0x1800a2987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a298c  mov     rax, rsi
0x1800a298f  add     rsp, 28h
0x1800a2993  pop     r14
0x1800a2995  pop     rdi
0x1800a2996  pop     rsi
0x1800a2997  pop     rbx
0x1800a2998  retn
```
