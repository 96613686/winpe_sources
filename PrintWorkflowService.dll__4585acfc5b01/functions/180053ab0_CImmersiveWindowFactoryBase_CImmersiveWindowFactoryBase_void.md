# CImmersiveWindowFactoryBase::~CImmersiveWindowFactoryBase(void)

- ea: `0x180053ab0`
- end: `0x180053b30`
- name: `??1CImmersiveWindowFactoryBase@@MEAA@XZ`
- size: `128`
- prototype: `void __fastcall(CImmersiveWindowFactoryBase *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180053a30`
- `0x180053bc0`

## callees

- `0x18000dfd0`
- `0x180053ab0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053af6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053af6`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall CImmersiveWindowFactoryBase::~CImmersiveWindowFactoryBase(CImmersiveWindowFactoryBase *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CImmersiveWindowFactoryBase::`vftable';
  *((_QWORD *)this + 1) = &CImmersiveWindowFactoryBase::`vftable'{for `Microsoft::WRL::Details::Selector<CWrlLightweightHandlerBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<CWrlLightweightHandlerBase>,Microsoft::WRL::CloakedIid<IStdMarshalInfo>>>'};
  *((_QWORD *)this + 6) = &CWrlLightweightHandlerServer::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::CloakedIid<IStdMarshalInfo>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<CWrlLightweightHandlerBase>,Microsoft::WRL::CloakedIid<IStdMarshalInfo>>>'};
  *((_QWORD *)this + 9) = &CImmersiveWindowFactoryBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IConfigureWindowFactory>'};
  *((_QWORD *)this + 10) = &CImmersiveWindowFactoryBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ICoreWindowFactoryPriv>>'};
  CoTaskMemFree(*((LPVOID *)this + 17));
  v2 = *((_QWORD *)this + 20);
  if ( v2 )
  {
    *((_QWORD *)this + 20) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease((char *)this + 40);
}

```

## disassembly

```asm
0x180053ab0  push    rbx
0x180053ab2  sub     rsp, 20h
0x180053ab6  mov     rbx, rcx
0x180053ab9  lea     rax, ??_7CImmersiveWindowFactoryBase@@6B@; const CImmersiveWindowFactoryBase::`vftable'
0x180053ac0  mov     [rcx], rax
0x180053ac3  lea     rax, ??_7CImmersiveWindowFactoryBase@@6B?$Selector@VCWrlLightweightHandlerBase@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VCWrlLightweightHandlerBase@@@Details@23@U?$CloakedIid@UIStdMarshalInfo@@@23@@Details@WRL@Microsoft@@@Details@WRL@Microsoft@@@; const CImmersiveWindowFactoryBase::`vftable'{for `Microsoft::WRL::Details::Selector<CWrlLightweightHandlerBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<CWrlLightweightHandlerBase>,Microsoft::WRL::CloakedIid<IStdMarshalInfo>>>'}
0x180053aca  mov     [rcx+8], rax
0x180053ace  lea     rax, ??_7CWrlLightweightHandlerServer@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$CloakedIid@UIStdMarshalInfo@@@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VCWrlLightweightHandlerBase@@@Details@23@U?$CloakedIid@UIStdMarshalInfo@@@23@@234@@Details@WRL@Microsoft@@@; const CWrlLightweightHandlerServer::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::CloakedIid<IStdMarshalInfo>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<CWrlLightweightHandlerBase>,Microsoft::WRL::CloakedIid<IStdMarshalInfo>>>'}
0x180053ad5  mov     [rcx+30h], rax
0x180053ad9  lea     rax, ??_7CImmersiveWindowFactoryBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIConfigureWindowFactory@@@Details@WRL@Microsoft@@@; const CImmersiveWindowFactoryBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IConfigureWindowFactory>'}
0x180053ae0  mov     [rcx+48h], rax
0x180053ae4  lea     rax, ??_7CImmersiveWindowFactoryBase@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$CloakedIid@UICoreWindowFactoryPriv@@@23@@Details@WRL@Microsoft@@@; const CImmersiveWindowFactoryBase::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::CloakedIid<ICoreWindowFactoryPriv>>'}
0x180053aeb  mov     [rcx+50h], rax
0x180053aef  mov     rcx, [rcx+88h]; pv
0x180053af6  call    cs:__imp_CoTaskMemFree
0x180053afc  mov     rcx, [rbx+0A0h]
0x180053b03  test    rcx, rcx
0x180053b06  jz      short loc_180053B20
0x180053b08  mov     qword ptr [rbx+0A0h], 0
0x180053b13  mov     rax, [rcx]
0x180053b16  mov     rax, [rax+10h]
0x180053b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b1f  nop
0x180053b20  lea     rcx, [rbx+28h]
0x180053b24  call    ?InternalRelease@?$ComPtr@UIModalExperienceManagerStatic@ModalExperience@Shell@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::Shell::ModalExperience::IModalExperienceManagerStatic>::InternalRelease(void)
0x180053b29  nop
0x180053b2a  add     rsp, 20h
0x180053b2e  pop     rbx
0x180053b2f  retn
```
