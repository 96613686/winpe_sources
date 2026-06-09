# ServiceHostTelemetry::ServiceStartActivity::~ServiceStartActivity(void)

- ea: `0x18000de74`
- end: `0x18000de99`
- name: `??1ServiceStartActivity@ServiceHostTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(ServiceHostTelemetry::ServiceStartActivity *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180011137`

## callees

- `0x18000dcdc`
- `0x18000e2ec`

## pseudocode

```c
void __fastcall ServiceHostTelemetry::ServiceStartActivity::~ServiceStartActivity(
        ServiceHostTelemetry::ServiceStartActivity *this)
{
  *(_QWORD *)this = &ServiceHostTelemetry::ServiceStartActivity::`vftable';
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x18000de74  push    rbx
0x18000de76  sub     rsp, 20h
0x18000de7a  lea     rax, ??_7ServiceStartActivity@ServiceHostTelemetry@@6B@; const ServiceHostTelemetry::ServiceStartActivity::`vftable'
0x18000de81  mov     rbx, rcx
0x18000de84  mov     [rcx], rax
0x18000de87  call    ?Destroy@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000de8c  mov     rcx, rbx
0x18000de8f  add     rsp, 20h
0x18000de93  pop     rbx
0x18000de94  jmp     ??1?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
```
