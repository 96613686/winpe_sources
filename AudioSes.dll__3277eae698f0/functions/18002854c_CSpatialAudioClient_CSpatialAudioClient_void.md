# CSpatialAudioClient::~CSpatialAudioClient(void)

- ea: `0x18002854c`
- end: `0x1800285b1`
- name: `??1CSpatialAudioClient@@UEAA@XZ`
- size: `101`
- prototype: `void __fastcall(CSpatialAudioClient *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180028510`

## callees

- `0x180007f00`
- `0x18000d11c`
- `0x18002854c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028596`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180028596`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028573`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180028573`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002857d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002857d`

## pseudocode

```c
void __fastcall CSpatialAudioClient::~CSpatialAudioClient(CSpatialAudioClient *this)
{
  void *v2; // rcx

  *(_QWORD *)this = &CSpatialAudioClient::`vftable'{for `Microsoft::WRL::ChainInterfaces<ISpatialAudioClient2,ISpatialAudioClient,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'};
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<ISpatialAudioClient2,ISpatialAudioClient,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  v2 = (void *)*((_QWORD *)this + 9);
  if ( v2 )
    CoTaskMemFree(v2);
  PropVariantClear((PROPVARIANT *)this + 15);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 232);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 144));
  *((_DWORD *)this + 11) = -1073741823;
  Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease((char *)this + 32);
}

```

## disassembly

```asm
0x18002854c  push    rbx
0x18002854e  sub     rsp, 20h
0x180028552  lea     rax, ??_7CSpatialAudioClient@@6B?$ChainInterfaces@UISpatialAudioClient2@@UISpatialAudioClient@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@WRL@Microsoft@@@; const CSpatialAudioClient::`vftable'{for `Microsoft::WRL::ChainInterfaces<ISpatialAudioClient2,ISpatialAudioClient,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>'}
0x180028559  mov     rbx, rcx
0x18002855c  mov     [rcx], rax
0x18002855f  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@U?$ChainInterfaces@UISpatialAudioClient2@@UISpatialAudioClient@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,Microsoft::WRL::ChainInterfaces<ISpatialAudioClient2,ISpatialAudioClient,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x180028566  mov     [rcx+8], rax
0x18002856a  mov     rcx, [rcx+48h]; pv
0x18002856e  test    rcx, rcx
0x180028571  jz      short loc_180028579
0x180028573  call    cs:__imp_CoTaskMemFree
0x180028579  lea     rcx, [rbx+78h]; pvar
0x18002857d  call    cs:__imp_PropVariantClear
0x180028583  lea     rcx, [rbx+0E8h]; void *
0x18002858a  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18002858f  lea     rcx, [rbx+90h]; lpCriticalSection
0x180028596  call    cs:__imp_DeleteCriticalSection
0x18002859c  lea     rcx, [rbx+20h]
0x1800285a0  mov     dword ptr [rbx+2Ch], 0C0000001h
0x1800285a7  add     rsp, 20h
0x1800285ab  pop     rbx
0x1800285ac  jmp     ?InternalRelease@?$ComPtr@UISpatialAudioPositionCalc@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISpatialAudioPositionCalc>::InternalRelease(void)
```
