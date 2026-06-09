# MtfPlatformTelemetry::SuggestionReady::~SuggestionReady(void)

- ea: `0x180014718`
- end: `0x18001473d`
- name: `??1SuggestionReady@MtfPlatformTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(MtfPlatformTelemetry::SuggestionReady *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002d4e2`

## callees

- `0x180014258`
- `0x180016a08`

## pseudocode

```c
void __fastcall MtfPlatformTelemetry::SuggestionReady::~SuggestionReady(MtfPlatformTelemetry::SuggestionReady *this)
{
  *(_QWORD *)this = &MtfPlatformTelemetry::SuggestionReady::`vftable';
  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(this);
  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x180014718  push    rbx
0x18001471a  sub     rsp, 20h
0x18001471e  lea     rax, ??_7SuggestionReady@MtfPlatformTelemetry@@6B@; const MtfPlatformTelemetry::SuggestionReady::`vftable'
0x180014725  mov     rbx, rcx
0x180014728  mov     [rcx], rax
0x18001472b  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180014730  mov     rcx, rbx
0x180014733  add     rsp, 20h
0x180014737  pop     rbx
0x180014738  jmp     ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
