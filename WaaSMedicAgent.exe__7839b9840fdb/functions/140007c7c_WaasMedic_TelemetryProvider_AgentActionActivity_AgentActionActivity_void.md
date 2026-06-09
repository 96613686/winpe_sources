# WaasMedic::TelemetryProvider::AgentActionActivity::~AgentActionActivity(void)

- ea: `0x140007c7c`
- end: `0x140007ca1`
- name: `??1AgentActionActivity@TelemetryProvider@WaasMedic@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::AgentActionActivity *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update`

## callers

- `0x1400121a2`

## callees

- `0x140007a38`
- `0x140007e1c`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::AgentActionActivity::~AgentActionActivity(
        WaasMedic::TelemetryProvider::AgentActionActivity *this)
{
  *(_QWORD *)this = &WaasMedic::TelemetryProvider::AgentActionActivity::`vftable';
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(this);
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x140007c7c  push    rbx
0x140007c7e  sub     rsp, 20h
0x140007c82  lea     rax, ??_7AgentActionActivity@TelemetryProvider@WaasMedic@@6B@; const WaasMedic::TelemetryProvider::AgentActionActivity::`vftable'
0x140007c89  mov     rbx, rcx
0x140007c8c  mov     [rcx], rax
0x140007c8f  call    ?Destroy@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x140007c94  mov     rcx, rbx
0x140007c97  add     rsp, 20h
0x140007c9b  pop     rbx
0x140007c9c  jmp     ??1?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
```
