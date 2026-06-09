# _CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$0

- ea: `0x1400199b7`
- end: `0x1400199c3`
- name: `_CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x14001336c`

## pseudocode

```c
void __fastcall CMDMPushConfiguration::CreatePushLaunchSchedule_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  MDMPushProvider::CreatePushLaunchScheduleActivity::~CreatePushLaunchScheduleActivity((MDMPushProvider::CreatePushLaunchScheduleActivity *)(a2 + 448));
}

```

## disassembly

```asm
0x1400199b7  lea     rcx, [rdx+1C0h]; this
0x1400199be  jmp     ??1CreatePushLaunchScheduleActivity@MDMPushProvider@@QEAA@XZ; MDMPushProvider::CreatePushLaunchScheduleActivity::~CreatePushLaunchScheduleActivity(void)
```
