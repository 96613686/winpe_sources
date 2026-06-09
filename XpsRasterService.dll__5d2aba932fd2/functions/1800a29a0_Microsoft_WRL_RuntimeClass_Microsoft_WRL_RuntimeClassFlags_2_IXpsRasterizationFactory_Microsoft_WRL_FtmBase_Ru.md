# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,Microsoft::WRL::FtmBase>(void)

- ea: `0x1800a29a0`
- end: `0x1800a2a5b`
- name: `??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIXpsRasterizationFactory@@VFtmBase@23@@WRL@Microsoft@@QEAA@XZ`
- size: `187`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800a1d40`

## callees

- `0x1800a0de8`
- `0x1800a29a0`
- `0x1800c3010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800a29dd`
- `api-ms-win-core-com-l1-1-0!CoCreateFreeThreadedMarshaler` at `0x1800a29dd`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,Microsoft::WRL::FtmBase>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,Microsoft::WRL::FtmBase>(
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
  *(_QWORD *)a1 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,Microsoft::WRL::FtmBase>::`vftable'{for `IXpsRasterizationFactory'};
  *(_QWORD *)(a1 + 8) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return a1;
}

```

## disassembly

```asm
0x1800a29a0  push    rbx
0x1800a29a2  push    rsi
0x1800a29a3  push    rdi
0x1800a29a4  push    r14
0x1800a29a6  sub     rsp, 28h
0x1800a29aa  mov     rsi, rcx
0x1800a29ad  lea     rax, ??_7FtmBase@WRL@Microsoft@@6B@; const Microsoft::WRL::FtmBase::`vftable'
0x1800a29b4  mov     [rcx+8], rax
0x1800a29b8  lea     r14, [rcx+20h]
0x1800a29bc  mov     qword ptr [r14], 0
0x1800a29c3  mov     [rsp+48h+ppunkMarshal], 0
0x1800a29cc  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800a29d1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a29d6  lea     rdx, [rsp+48h+ppunkMarshal]; ppunkMarshal
0x1800a29db  xor     ecx, ecx; punkOuter
0x1800a29dd  call    cs:__imp_CoCreateFreeThreadedMarshaler
0x1800a29e3  test    eax, eax
0x1800a29e5  js      short loc_1800A2A10
0x1800a29e7  mov     rbx, [rsp+48h+ppunkMarshal]
0x1800a29ec  mov     rax, [rbx]
0x1800a29ef  mov     rdi, [rax]
0x1800a29f2  mov     rcx, r14
0x1800a29f5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a29fa  mov     r8, r14
0x1800a29fd  lea     rdx, _GUID_00000003_0000_0000_c000_000000000046
0x1800a2a04  mov     rcx, rbx
0x1800a2a07  mov     rax, rdi
0x1800a2a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2a0f  nop
0x1800a2a10  lea     rcx, [rsp+48h+ppunkMarshal]
0x1800a2a15  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800a2a1a  mov     dword ptr [rsi+2Ch], 1
0x1800a2a21  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIXpsRasterizationFactory@@VFtmBase@23@@WRL@Microsoft@@6BIXpsRasterizationFactory@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,Microsoft::WRL::FtmBase>::`vftable'{for `IXpsRasterizationFactory'}
0x1800a2a28  mov     [rsi], rax
0x1800a2a2b  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIXpsRasterizationFactory@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IXpsRasterizationFactory,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x1800a2a32  mov     [rsi+8], rax
0x1800a2a36  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800a2a3d  test    rcx, rcx
0x1800a2a40  jz      short loc_1800A2A4E
0x1800a2a42  mov     rax, [rcx]
0x1800a2a45  mov     rax, [rax+8]
0x1800a2a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2a4e  mov     rax, rsi
0x1800a2a51  add     rsp, 28h
0x1800a2a55  pop     r14
0x1800a2a57  pop     rdi
0x1800a2a58  pop     rsi
0x1800a2a59  pop     rbx
0x1800a2a5a  retn
```
