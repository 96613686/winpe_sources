# CImmersiveWindowFactoryBase::~CImmersiveWindowFactoryBase(void)

- ea: `0x180043bf4`
- end: `0x180043c71`
- name: `??1CImmersiveWindowFactoryBase@@MEAA@XZ`
- size: `125`
- prototype: `void __fastcall(CImmersiveWindowFactoryBase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180043b74`
- `0x180043d00`

## callees

- `0x1800067b0`
- `0x180043bf4`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043c3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043c3a`

## pseudocode

```c
void __fastcall CImmersiveWindowFactoryBase::~CImmersiveWindowFactoryBase(CImmersiveWindowFactoryBase *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CImmersiveWindowFactoryBase::`vftable';
  *((_QWORD *)this + 1) = &CImmersiveWindowFactoryBase::`vftable'{for `Microsoft::WRL::Details::Selector<CWrlLightweightHandlerBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<CWrlLightweightHandlerBase>,Microsoft::WRL::CloakedIid<IStdMarshalInfo>>>'};
  *((_QWORD *)this + 6) = &CImmersiveWindowFactoryBase::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::CloakedIid<IStdMarshalInfo>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<CWrlLightweightHandlerBase>,Microsoft::WRL::CloakedIid<IStdMarshalInfo>>>'};
  *((_QWORD *)this + 9) = &CImmersiveWindowFactoryBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IConfigureWindowFactory>'};
  *((_QWORD *)this + 10) = &CImmersiveWindowFactoryBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ICoreWindowFactoryPriv>>'};
  CoTaskMemFree(*((LPVOID *)this + 17));
  v2 = *((_QWORD *)this + 20);
  if ( v2 )
  {
    *((_QWORD *)this + 20) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease((char *)this + 40);
}

```

## disassembly

```asm
0x180043bf4  push    rbx
0x180043bf6  sub     rsp, 20h
0x180043bfa  lea     rax, ??_7CImmersiveWindowFactoryBase@@6B@; const CImmersiveWindowFactoryBase::`vftable'
0x180043c01  mov     rbx, rcx
0x180043c04  mov     [rcx], rax
0x180043c07  lea     rax, ??_7CImmersiveWindowFactoryBase@@6B?$Selector@VCWrlLightweightHandlerBase@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VCWrlLightweightHandlerBase@@@Details@23@U?$CloakedIid@UIStdMarshalInfo@@@23@@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@@; const CImmersiveWindowFactoryBase::`vftable'{for `Microsoft::WRL::Details::Selector<CWrlLightweightHandlerBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<CWrlLightweightHandlerBase>,Microsoft::WRL::CloakedIid<IStdMarshalInfo>>>'}
0x180043c0e  mov     [rcx+8], rax
0x180043c12  lea     rax, ??_7CImmersiveWindowFactoryBase@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$CloakedIid@UIStdMarshalInfo@@@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VCWrlLightweightHandlerBase@@@Details@23@U?$CloakedIid@UIStdMarshalInfo@@@23@@234@@Details@WRL@Microsoft@@@; const CImmersiveWindowFactoryBase::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::CloakedIid<IStdMarshalInfo>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<CWrlLightweightHandlerBase>,Microsoft::WRL::CloakedIid<IStdMarshalInfo>>>'}
0x180043c19  mov     [rcx+30h], rax
0x180043c1d  lea     rax, ??_7CImmersiveWindowFactoryBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIConfigureWindowFactory@@@Details@WRL@Microsoft@@@; const CImmersiveWindowFactoryBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IConfigureWindowFactory>'}
0x180043c24  mov     [rcx+48h], rax
0x180043c28  lea     rax, ??_7CImmersiveWindowFactoryBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UICoreWindowFactoryPriv@@@23@@Details@WRL@Microsoft@@@; const CImmersiveWindowFactoryBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ICoreWindowFactoryPriv>>'}
0x180043c2f  mov     [rcx+50h], rax
0x180043c33  mov     rcx, [rcx+88h]; pv
0x180043c3a  call    cs:__imp_CoTaskMemFree
0x180043c40  mov     rcx, [rbx+0A0h]
0x180043c47  test    rcx, rcx
0x180043c4a  jz      short loc_180043C63
0x180043c4c  mov     qword ptr [rbx+0A0h], 0
0x180043c57  mov     rax, [rcx]
0x180043c5a  mov     rax, [rax+10h]
0x180043c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043c63  lea     rcx, [rbx+28h]
0x180043c67  add     rsp, 20h
0x180043c6b  pop     rbx
0x180043c6c  jmp     ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
```
