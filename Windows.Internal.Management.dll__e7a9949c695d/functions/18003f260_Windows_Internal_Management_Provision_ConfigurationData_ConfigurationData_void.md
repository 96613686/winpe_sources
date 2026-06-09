# Windows::Internal::Management::Provision::ConfigurationData::~ConfigurationData(void)

- ea: `0x18003f260`
- end: `0x18003f2aa`
- name: `??1ConfigurationData@Provision@Management@Internal@Windows@@UEAA@XZ`
- size: `74`
- prototype: `void __fastcall(Windows::Internal::Management::Provision::ConfigurationData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003f330`

## callees

- `0x18000d69c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003f28d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003f28d`
- `OLEAUT32!__imp_VariantClear` at `0x18003f297`
- `OLEAUT32!__imp_VariantClear` at `0x18003f297`

## pseudocode

```c
void __fastcall Windows::Internal::Management::Provision::ConfigurationData::~ConfigurationData(
        Windows::Internal::Management::Provision::ConfigurationData *this)
{
  *(_QWORD *)this = &Windows::Internal::Management::Provision::ConfigurationData::`vftable';
  *((_QWORD *)this + 1) = &Windows::Internal::Management::Provision::ConfigurationData::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Windows::Internal::Management::Provision::ConfigurationData::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  VariantClear((VARIANTARG *)this + 3);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18003f260  push    rbx
0x18003f262  sub     rsp, 20h
0x18003f266  lea     rax, ??_7ConfigurationData@Provision@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provision::ConfigurationData::`vftable'
0x18003f26d  mov     rbx, rcx
0x18003f270  mov     [rcx], rax
0x18003f273  lea     rax, ??_7ConfigurationData@Provision@Management@Internal@Windows@@6BIWeakReferenceSource@@@; const Windows::Internal::Management::Provision::ConfigurationData::`vftable'{for `IWeakReferenceSource'}
0x18003f27a  mov     [rcx+8], rax
0x18003f27e  lea     rax, ??_7ConfigurationData@Provision@Management@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Internal::Management::Provision::ConfigurationData::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003f285  mov     [rcx+10h], rax
0x18003f289  add     rcx, 68h ; 'h'; lpCriticalSection
0x18003f28d  call    cs:__imp_DeleteCriticalSection
0x18003f293  lea     rcx, [rbx+48h]; pvarg
0x18003f297  call    cs:__imp_VariantClear
0x18003f29d  mov     rcx, rbx
0x18003f2a0  add     rsp, 20h
0x18003f2a4  pop     rbx
0x18003f2a5  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIConfigurationData@Provision@Management@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>(void)
```
