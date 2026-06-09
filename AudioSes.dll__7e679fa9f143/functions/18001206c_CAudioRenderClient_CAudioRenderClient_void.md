# CAudioRenderClient::~CAudioRenderClient(void)

- ea: `0x18001206c`
- end: `0x180012122`
- name: `??1CAudioRenderClient@@UEAA@XZ`
- size: `182`
- prototype: `void __fastcall(CAudioRenderClient *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012030`

## callees

- `0x180007f00`
- `0x18001206c`
- `0x180012128`
- `0x180012158`
- `0x180123010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001210f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001210f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800120bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800120d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800120bc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800120d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAudioRenderClient::~CAudioRenderClient(CAudioRenderClient *this)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &CAudioRenderClient::`vftable'{for `IInspectable'};
  *((_QWORD *)this + 1) = &CAudioRenderClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IAudioRenderClient,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &CAudioRenderClient::`vftable'{for `IAudioRenderClient'};
  *((_QWORD *)this + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IInspectable,IAudioRenderClient,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  CAudioRenderClient::Cleanup(this);
  v2 = (void *)*((_QWORD *)this + 22);
  *((_QWORD *)this + 22) = 0;
  if ( v2 )
    CoTaskMemFree(v2);
  v3 = (void *)*((_QWORD *)this + 20);
  *((_QWORD *)this + 20) = 0;
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = *((_QWORD *)this + 16);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 120);
  wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>((char *)this + 112);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Media::Audio::IAudioEffectsPackConfiguration,Windows::Media::Audio::IAudioEffectsPackChangedInternal,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Media::Audio::IAudioEffectsPackConfiguration,Windows::Media::Audio::IAudioEffectsPackChangedInternal,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x18001206c  push    rbx
0x18001206e  sub     rsp, 20h
0x180012072  mov     rbx, rcx
0x180012075  lea     rax, ??_7CAudioRenderClient@@6BIInspectable@@@; const CAudioRenderClient::`vftable'{for `IInspectable'}
0x18001207c  mov     [rcx], rax
0x18001207f  lea     rax, ??_7CAudioRenderClient@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@UIAudioRenderClient@@VFtmBase@23@@Details@WRL@Microsoft@@@; const CAudioRenderClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,IAudioRenderClient,Microsoft::WRL::FtmBase>'}
0x180012086  mov     [rcx+8], rax
0x18001208a  lea     rax, ??_7CAudioRenderClient@@6BIAudioRenderClient@@@; const CAudioRenderClient::`vftable'{for `IAudioRenderClient'}
0x180012091  mov     [rcx+10h], rax
0x180012095  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIInspectable@@UIAudioRenderClient@@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IInspectable,IAudioRenderClient,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001209c  mov     [rcx+18h], rax
0x1800120a0  call    ?Cleanup@CAudioRenderClient@@QEAAXXZ; CAudioRenderClient::Cleanup(void)
0x1800120a5  mov     rcx, [rbx+0B0h]; pv
0x1800120ac  mov     qword ptr [rbx+0B0h], 0
0x1800120b7  test    rcx, rcx
0x1800120ba  jz      short loc_1800120C2
0x1800120bc  call    cs:__imp_CoTaskMemFree
0x1800120c2  mov     rcx, [rbx+0A0h]; pv
0x1800120c9  mov     qword ptr [rbx+0A0h], 0
0x1800120d4  test    rcx, rcx
0x1800120d7  jz      short loc_1800120E0
0x1800120d9  call    cs:__imp_CoTaskMemFree
0x1800120df  nop
0x1800120e0  mov     rcx, [rbx+80h]
0x1800120e7  test    rcx, rcx
0x1800120ea  jz      short loc_1800120F9
0x1800120ec  mov     rax, [rcx]
0x1800120ef  mov     rax, [rax+10h]
0x1800120f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120f8  nop
0x1800120f9  lea     rcx, [rbx+78h]; void *
0x1800120fd  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x180012102  lea     rcx, [rbx+70h]; void *
0x180012106  call    ??1?$com_ptr_t@UIAudioClient3@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioClient3,wil::err_returncode_policy>::~com_ptr_t<IAudioClient3,wil::err_returncode_policy>(void)
0x18001210b  lea     rcx, [rbx+48h]; lpCriticalSection
0x18001210f  call    cs:__imp_DeleteCriticalSection
0x180012115  mov     rcx, rbx
0x180012118  add     rsp, 20h
0x18001211c  pop     rbx
0x18001211d  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIAudioEffectsPackConfiguration@Audio@Media@Windows@@UIAudioEffectsPackChangedInternal@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Media::Audio::IAudioEffectsPackConfiguration,Windows::Media::Audio::IAudioEffectsPackChangedInternal,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Media::Audio::IAudioEffectsPackConfiguration,Windows::Media::Audio::IAudioEffectsPackChangedInternal,Microsoft::WRL::FtmBase>(void)
```
