# _CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$1

- ea: `0x140018c68`
- end: `0x140018c74`
- name: `_CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor$1`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140012948`

## pseudocode

```c
__int64 __fastcall CMDMPushConfiguration::CreatePushUpgradeSchedule_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  return wil::details::ScopeExitFn__lambda_a5850cbe37682a2c7f3cfac37b5c52a1___::_ScopeExitFn__lambda_a5850cbe37682a2c7f3cfac37b5c52a1___(a2 + 80);
}

```

## disassembly

```asm
0x140018c68  lea     rcx, [rdx+50h]
0x140018c6f  jmp     wil__details__ScopeExitFn__lambda_a5850cbe37682a2c7f3cfac37b5c52a1______ScopeExitFn__lambda_a5850cbe37682a2c7f3cfac37b5c52a1___
```
