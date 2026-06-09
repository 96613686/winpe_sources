# MtfPlatformTelemetry::UpdateAllDataSource::~UpdateAllDataSource(void)

- ea: `0x1800147f0`
- end: `0x180014815`
- name: `??1UpdateAllDataSource@MtfPlatformTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(MtfPlatformTelemetry::UpdateAllDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18002d7b8`

## callees

- `0x180014258`
- `0x180016a08`

## pseudocode

```c
void __fastcall MtfPlatformTelemetry::UpdateAllDataSource::~UpdateAllDataSource(
        MtfPlatformTelemetry::UpdateAllDataSource *this)
{
  *(_QWORD *)this = &MtfPlatformTelemetry::UpdateAllDataSource::`vftable';
  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(this);
  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x1800147f0  push    rbx
0x1800147f2  sub     rsp, 20h
0x1800147f6  lea     rax, ??_7UpdateAllDataSource@MtfPlatformTelemetry@@6B@; const MtfPlatformTelemetry::UpdateAllDataSource::`vftable'
0x1800147fd  mov     rbx, rcx
0x180014800  mov     [rcx], rax
0x180014803  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180014808  mov     rcx, rbx
0x18001480b  add     rsp, 20h
0x18001480f  pop     rbx
0x180014810  jmp     ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
