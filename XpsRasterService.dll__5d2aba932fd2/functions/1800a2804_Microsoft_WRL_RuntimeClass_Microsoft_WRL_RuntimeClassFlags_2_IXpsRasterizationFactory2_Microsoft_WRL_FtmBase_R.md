# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>(void)

- ea: `0x1800a2804`
- end: `0x1800a28bf`
- name: `??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIXpsRasterizationFactory2@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ`
- size: `187`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a1c5c`

## callees

- `0x1800a0de8`
- `0x1800a2804`
- `0x1800c3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800a2841`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800a2841`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>(
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
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>::`vftable'{for `IXpsRasterizationFactory2'};
  *(_QWORD *)(a1 + 8) = &xpsras::CRasterizerFactory2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return a1;
}

```

## disassembly

```asm
0x1800a2804  push    rbx
0x1800a2806  push    rsi
0x1800a2807  push    rdi
0x1800a2808  push    r14
0x1800a280a  sub     rsp, 28h
0x1800a280e  mov     rsi, rcx
0x1800a2811  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800a2818  mov     [rcx+8], rax
0x1800a281c  lea     r14, [rcx+20h]
0x1800a2820  mov     qword ptr [r14], 0
0x1800a2827  mov     [rsp+48h+ppunkMarshal], 0
0x1800a2830  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800a2835  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a283a  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800a283f  xor     ecx, ecx; punkOuter
0x1800a2841  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800a2847  test    eax, eax
0x1800a2849  js      short loc_1800A2874
0x1800a284b  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800a2850  mov     rax, [rbx]
0x1800a2853  mov     rdi, [rax]
0x1800a2856  mov     rcx, r14
0x1800a2859  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a285e  mov     r8, r14
0x1800a2861  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800a2868  mov     rcx, rbx
0x1800a286b  mov     rax, rdi
0x1800a286e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2873  nop
0x1800a2874  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800a2879  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a287e  mov     dword ptr [rsi+2Ch], 1
0x1800a2885  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIXpsRasterizationFactory2@@VFtmBase@23@@WRL@Microsoft@@6BIXpsRasterizationFactory2@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory2,Microsoft::WRL::FtmBase>::`vftable'{for `IXpsRasterizationFactory2'}
0x1800a288c  mov     [rsi], rax
0x1800a288f  lea     rax, ??_7CRasterizerFactory2@xpsras@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const xpsras::CRasterizerFactory2::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800a2896  mov     [rsi+8], rax
0x1800a289a  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800a28a1  test    rcx, rcx
0x1800a28a4  jz      short loc_1800A28B2
0x1800a28a6  mov     rax, [rcx]
0x1800a28a9  mov     rax, [rax+8]
0x1800a28ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a28b2  mov     rax, rsi
0x1800a28b5  add     rsp, 28h
0x1800a28b9  pop     r14
0x1800a28bb  pop     rdi
0x1800a28bc  pop     rsi
0x1800a28bd  pop     rbx
0x1800a28be  retn
```
