# SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::~CreateInstance(void)

- ea: `0x180007828`
- end: `0x18000784d`
- name: `??1CreateInstance@SmdTraceProvider@SpeechMicDiagnostic@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(SpeechMicDiagnostic::SmdTraceProvider::CreateInstance *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010720`

## callees

- `0x180007510`
- `0x180007f18`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::~CreateInstance(
        SpeechMicDiagnostic::SmdTraceProvider::CreateInstance *this)
{
  *(_QWORD *)this = &SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::`vftable';
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(this);
  wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x180007828  push    rbx
0x18000782a  sub     rsp, 20h
0x18000782e  lea     rax, ??_7CreateInstance@SmdTraceProvider@SpeechMicDiagnostic@@6B@; const SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::`vftable'
0x180007835  mov     rbx, rcx
0x180007838  mov     [rcx], rax
0x18000783b  call    ?Destroy@?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180007840  mov     rcx, rbx
0x180007843  add     rsp, 20h
0x180007847  pop     rbx
0x180007848  jmp     ??1?$ActivityBase@VSmdTraceProvider@SpeechMicDiagnostic@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<SpeechMicDiagnostic::SmdTraceProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
