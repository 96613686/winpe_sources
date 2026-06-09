# Windows::Internal::Management::Provision::ConfigurationData::~ConfigurationData(void)

- ea: `0x18003ec64`
- end: `0x18003ecba`
- name: `??1ConfigurationData@Provision@Management@Internal@Windows@@UEAA@XZ`
- size: `86`
- prototype: `void __fastcall(Windows::Internal::Management::Provision::ConfigurationData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003ed40`

## callees

- `0x18000db88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003ec91`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003ec91`
- `OLEAUT32!__imp_VariantClear` at `0x18003eca1`
- `OLEAUT32!__imp_VariantClear` at `0x18003eca1`

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
0x18003ec64  push    rbx
0x18003ec66  sub     rsp, 20h
0x18003ec6a  lea     rax, ??_7ConfigurationData@Provision@Management@Internal@Windows@@6B@; const Windows::Internal::Management::Provision::ConfigurationData::`vftable'
0x18003ec71  mov     rbx, rcx
0x18003ec74  mov     [rcx], rax
0x18003ec77  lea     rax, ??_7ConfigurationData@Provision@Management@Internal@Windows@@6BIWeakReferenceSource@@@; const Windows::Internal::Management::Provision::ConfigurationData::`vftable'{for `IWeakReferenceSource'}
0x18003ec7e  mov     [rcx+8], rax
0x18003ec82  lea     rax, ??_7ConfigurationData@Provision@Management@Internal@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@WRL@Microsoft@@@; const Windows::Internal::Management::Provision::ConfigurationData::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18003ec89  mov     [rcx+10h], rax
0x18003ec8d  add     rcx, 68h ; 'h'; lpCriticalSection
0x18003ec91  call    cs:__imp_DeleteCriticalSection
0x18003ec98  nop     dword ptr [rax+rax+00h]
0x18003ec9d  lea     rcx, [rbx+48h]; pvarg
0x18003eca1  call    cs:__imp_VariantClear
0x18003eca8  nop     dword ptr [rax+rax+00h]
0x18003ecad  mov     rcx, rbx
0x18003ecb0  add     rsp, 20h
0x18003ecb4  pop     rbx
0x18003ecb5  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIConfigurationData@Provision@Management@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Management::Provision::IConfigurationData,Microsoft::WRL::FtmBase>(void)
```
