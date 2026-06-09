# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPassthroughRasterVerifier,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPassthroughRasterVerifier,Microsoft::WRL::FtmBase>(void)

- ea: `0x1800a06dc`
- end: `0x1800a0797`
- name: `??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPassthroughRasterVerifier@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a05e8`

## callees

- `0x1800a06dc`
- `0x1800a0de8`
- `0x1800c3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800a0719`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800a0719`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPassthroughRasterVerifier,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPassthroughRasterVerifier,Microsoft::WRL::FtmBase>(
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
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPassthroughRasterVerifier,Microsoft::WRL::FtmBase>::`vftable'{for `IPassthroughRasterVerifier'};
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPassthroughRasterVerifier,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return a1;
}

```

## disassembly

```asm
0x1800a06dc  push    rbx
0x1800a06de  push    rsi
0x1800a06df  push    rdi
0x1800a06e0  push    r14
0x1800a06e2  sub     rsp, 28h
0x1800a06e6  mov     rsi, rcx
0x1800a06e9  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800a06f0  mov     [rcx+8], rax
0x1800a06f4  lea     r14, [rcx+20h]
0x1800a06f8  mov     qword ptr [r14], 0
0x1800a06ff  mov     [rsp+48h+ppunkMarshal], 0
0x1800a0708  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800a070d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a0712  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800a0717  xor     ecx, ecx; punkOuter
0x1800a0719  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800a071f  test    eax, eax
0x1800a0721  js      short loc_1800A074C
0x1800a0723  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800a0728  mov     rax, [rbx]
0x1800a072b  mov     rdi, [rax]
0x1800a072e  mov     rcx, r14
0x1800a0731  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a0736  mov     r8, r14
0x1800a0739  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800a0740  mov     rcx, rbx
0x1800a0743  mov     rax, rdi
0x1800a0746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a074b  nop
0x1800a074c  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800a0751  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a0756  mov     dword ptr [rsi+2Ch], 1
0x1800a075d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPassthroughRasterVerifier@@VFtmBase@23@@WRL@Microsoft@@6BIPassthroughRasterVerifier@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPassthroughRasterVerifier,Microsoft::WRL::FtmBase>::`vftable'{for `IPassthroughRasterVerifier'}
0x1800a0764  mov     [rsi], rax
0x1800a0767  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIPassthroughRasterVerifier@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IPassthroughRasterVerifier,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800a076e  mov     [rsi+8], rax
0x1800a0772  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800a0779  test    rcx, rcx
0x1800a077c  jz      short loc_1800A078A
0x1800a077e  mov     rax, [rcx]
0x1800a0781  mov     rax, [rax+8]
0x1800a0785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a078a  mov     rax, rsi
0x1800a078d  add     rsp, 28h
0x1800a0791  pop     r14
0x1800a0793  pop     rdi
0x1800a0794  pop     rsi
0x1800a0795  pop     rbx
0x1800a0796  retn
```
