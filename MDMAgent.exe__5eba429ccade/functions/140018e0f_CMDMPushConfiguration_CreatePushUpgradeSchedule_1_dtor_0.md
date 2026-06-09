# _CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$0

- ea: `0x140018e0f`
- end: `0x140018e1b`
- name: `_CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140012a60`

## pseudocode

```c
void __fastcall CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  MDMPushProvider::CreatePushUpgradeScheduleActivity::~CreatePushUpgradeScheduleActivity((MDMPushProvider::CreatePushUpgradeScheduleActivity *)(a2 + 432));
}

```

## disassembly

```asm
0x140018e0f  lea     rcx, [rdx+1B0h]; this
0x140018e16  jmp     ??1CreatePushUpgradeScheduleActivity@MDMPushProvider@@QEAA@XZ; MDMPushProvider::CreatePushUpgradeScheduleActivity::~CreatePushUpgradeScheduleActivity(void)
```
