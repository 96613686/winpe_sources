# Broker::BackgroundTaskCapabilityWrapper::~BackgroundTaskCapabilityWrapper(void)

- ea: `0x180014ea8`
- end: `0x180014ec1`
- name: `??1BackgroundTaskCapabilityWrapper@Broker@@QEAA@XZ`
- size: `25`
- prototype: `void __fastcall(Broker::BackgroundTaskCapabilityWrapper *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800110a0`
- `0x180016950`
- `0x18001c662`
- `0x18001cc9a`

## callees

- `0x18001e010`

## pseudocode

```c
void __fastcall Broker::BackgroundTaskCapabilityWrapper::~BackgroundTaskCapabilityWrapper(
        Broker::BackgroundTaskCapabilityWrapper *this)
{
  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 16LL))(*(_QWORD *)this);
}

```

## disassembly

```asm
0x180014ea8  sub     rsp, 28h
0x180014eac  mov     rcx, [rcx]
0x180014eaf  mov     rax, [rcx]
0x180014eb2  mov     rax, [rax+10h]
0x180014eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ebb  nop
0x180014ebc  add     rsp, 28h
0x180014ec0  retn
```
