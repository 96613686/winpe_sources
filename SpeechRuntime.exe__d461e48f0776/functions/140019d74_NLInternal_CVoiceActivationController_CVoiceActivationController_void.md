# NLInternal::CVoiceActivationController::~CVoiceActivationController(void)

- ea: `0x140019d74`
- end: `0x140019df3`
- name: `??1CVoiceActivationController@NLInternal@@UEAA@XZ`
- size: `127`
- prototype: `void __fastcall(NLInternal::CVoiceActivationController *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140019f10`

## callees

- `0x14000c32c`
- `0x140019d38`
- `0x14001ac50`
- `0x14001c224`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140019db6`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140019db6`

## pseudocode

```c
void __fastcall NLInternal::CVoiceActivationController::~CVoiceActivationController(
        NLInternal::CVoiceActivationController *this)
{
  *(_QWORD *)this = &NLInternal::CVoiceActivationController::`vftable'{for `NLInternal::ISpeechDummy'};
  *((_QWORD *)this + 1) = &NLInternal::CVoiceActivationController::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<NLInternal::IVoiceActivationController>,Microsoft::WRL::FtmBase>'};
  *((_QWORD *)this + 2) = &NLInternal::CVoiceActivationController::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,NLInternal::IVoiceActivationController>'};
  *((_QWORD *)this + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,NLInternal::ISpeechDummy,Microsoft::WRL::CloakedIid<NLInternal::IVoiceActivationController>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
  NLInternal::CVoiceActivationController::SetAudioOrchestratorTrainingMode(this, 0);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 176);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 168);
  NLInternal::CAudioPolicyWrapper::~CAudioPolicyWrapper((NLInternal::CVoiceActivationController *)((char *)this + 120));
  NLInternal::CAudioPolicyWrapper::~CAudioPolicyWrapper((NLInternal::CVoiceActivationController *)((char *)this + 72));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,NLInternal::ISpeechDummy,Microsoft::WRL::CloakedIid<NLInternal::IVoiceActivationController>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,NLInternal::ISpeechDummy,Microsoft::WRL::CloakedIid<NLInternal::IVoiceActivationController>,Microsoft::WRL::FtmBase>(this);
}

```

## disassembly

```asm
0x140019d74  push    rbx
0x140019d76  sub     rsp, 20h
0x140019d7a  mov     rbx, rcx
0x140019d7d  lea     rax, ??_7CVoiceActivationController@NLInternal@@6BISpeechDummy@1@@; const NLInternal::CVoiceActivationController::`vftable'{for `NLInternal::ISpeechDummy'}
0x140019d84  mov     [rcx], rax
0x140019d87  lea     rax, ??_7CVoiceActivationController@NLInternal@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIVoiceActivationController@NLInternal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@@; const NLInternal::CVoiceActivationController::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<NLInternal::IVoiceActivationController>,Microsoft::WRL::FtmBase>'}
0x140019d8e  mov     [rcx+8], rax
0x140019d92  lea     rax, ??_7CVoiceActivationController@NLInternal@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIVoiceActivationController@NLInternal@@@Details@WRL@Microsoft@@@; const NLInternal::CVoiceActivationController::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,NLInternal::IVoiceActivationController>'}
0x140019d99  mov     [rcx+10h], rax
0x140019d9d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UISpeechDummy@NLInternal@@U?$CloakedIid@UIVoiceActivationController@NLInternal@@@23@VFtmBase@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,NLInternal::ISpeechDummy,Microsoft::WRL::CloakedIid<NLInternal::IVoiceActivationController>,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x140019da4  mov     [rcx+18h], rax
0x140019da8  xor     edx, edx; int
0x140019daa  call    ?SetAudioOrchestratorTrainingMode@CVoiceActivationController@NLInternal@@AEAAJH@Z; NLInternal::CVoiceActivationController::SetAudioOrchestratorTrainingMode(int)
0x140019daf  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x140019db6  call    cs:__imp_DeleteCriticalSection
0x140019dbc  lea     rcx, [rbx+0B0h]
0x140019dc3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140019dc8  lea     rcx, [rbx+0A8h]
0x140019dcf  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x140019dd4  lea     rcx, [rbx+78h]; this
0x140019dd8  call    ??1CAudioPolicyWrapper@NLInternal@@QEAA@XZ; NLInternal::CAudioPolicyWrapper::~CAudioPolicyWrapper(void)
0x140019ddd  lea     rcx, [rbx+48h]; this
0x140019de1  call    ??1CAudioPolicyWrapper@NLInternal@@QEAA@XZ; NLInternal::CAudioPolicyWrapper::~CAudioPolicyWrapper(void)
0x140019de6  mov     rcx, rbx
0x140019de9  add     rsp, 20h
0x140019ded  pop     rbx
0x140019dee  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UISpeechDummy@NLInternal@@U?$CloakedIid@UIVoiceActivationController@NLInternal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,NLInternal::ISpeechDummy,Microsoft::WRL::CloakedIid<NLInternal::IVoiceActivationController>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,NLInternal::ISpeechDummy,Microsoft::WRL::CloakedIid<NLInternal::IVoiceActivationController>,Microsoft::WRL::FtmBase>(void)
```
