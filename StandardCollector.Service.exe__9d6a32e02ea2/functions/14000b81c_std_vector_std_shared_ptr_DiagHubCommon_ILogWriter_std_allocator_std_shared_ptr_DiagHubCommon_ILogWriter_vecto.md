# std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>::~vector<std::shared_ptr<DiagHubCommon::ILogWriter>,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(void)

- ea: `0x14000b81c`
- end: `0x14000b821`
- name: `??1?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@QEAA@XZ`
- size: `5`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `31`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140015332`
- `0x14001534a`
- `0x140015366`
- `0x140015382`
- `0x1400153a1`
- `0x1400153b9`
- `0x1400154d3`
- `0x1400154df`
- `0x1400154eb`
- `0x1400154f7`
- `0x140015503`
- `0x14001552f`
- `0x14001553b`
- `0x140015553`
- `0x14001556b`
- `0x140015577`
- `0x14001558f`
- `0x1400155a7`
- `0x1400155b3`
- `0x1400155cb`
- `0x1400155e3`
- `0x1400155ef`
- `0x140015607`
- `0x14001561f`
- `0x14001562b`
- `0x140015643`
- `0x140015815`
- `0x14001582d`
- `0x140015849`
- `0x140015865`
- `0x140015884`

## callees

- `0x14000d484`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::~vector<std::shared_ptr<DiagHubCommon::ILogWriter>>(
        __int64 a1)
{
  return std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(a1);
}

```

## disassembly

```asm
0x14000b81c  jmp     ?_Tidy@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Tidy(void)
```
