# MtfPlatformTelemetry::UpdateDataSource::~UpdateDataSource(void)

- ea: `0x18001481c`
- end: `0x180014841`
- name: `??1UpdateDataSource@MtfPlatformTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(MtfPlatformTelemetry::UpdateDataSource *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18002d809`

## callees

- `0x180014258`
- `0x180016a08`

## pseudocode

```c
void __fastcall MtfPlatformTelemetry::UpdateDataSource::~UpdateDataSource(MtfPlatformTelemetry::UpdateDataSource *this)
{
  *(_QWORD *)this = &MtfPlatformTelemetry::UpdateDataSource::`vftable';
  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(this);
  wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(this);
}

```

## disassembly

```asm
0x18001481c  push    rbx
0x18001481e  sub     rsp, 20h
0x180014822  lea     rax, ??_7UpdateDataSource@MtfPlatformTelemetry@@6B@; const MtfPlatformTelemetry::UpdateDataSource::`vftable'
0x180014829  mov     rbx, rcx
0x18001482c  mov     [rcx], rax
0x18001482f  call    ?Destroy@?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180014834  mov     rcx, rbx
0x180014837  add     rsp, 20h
0x18001483b  pop     rbx
0x18001483c  jmp     ??1?$ActivityBase@VMtfPlatformTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<MtfPlatformTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
```
