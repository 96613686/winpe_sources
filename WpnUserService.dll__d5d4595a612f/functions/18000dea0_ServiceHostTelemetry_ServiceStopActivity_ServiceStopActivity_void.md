# ServiceHostTelemetry::ServiceStopActivity::~ServiceStopActivity(void)

- ea: `0x18000dea0`
- end: `0x18000dec5`
- name: `??1ServiceStopActivity@ServiceHostTelemetry@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(ServiceHostTelemetry::ServiceStopActivity *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18001115b`

## callees

- `0x18000dcdc`
- `0x18000e2ec`

## pseudocode

```c
void __fastcall ServiceHostTelemetry::ServiceStopActivity::~ServiceStopActivity(
        ServiceHostTelemetry::ServiceStopActivity *this)
{
  *(_QWORD *)this = &ServiceHostTelemetry::ServiceStopActivity::`vftable';
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy();
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>((__int64)this);
}

```

## disassembly

```asm
0x18000dea0  push    rbx
0x18000dea2  sub     rsp, 20h
0x18000dea6  lea     rax, ??_7ServiceStopActivity@ServiceHostTelemetry@@6B@; const ServiceHostTelemetry::ServiceStopActivity::`vftable'
0x18000dead  mov     rbx, rcx
0x18000deb0  mov     [rcx], rax
0x18000deb3  call    ?Destroy@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x18000deb8  mov     rcx, rbx
0x18000debb  add     rsp, 20h
0x18000debf  pop     rbx
0x18000dec0  jmp     ??1?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
```
