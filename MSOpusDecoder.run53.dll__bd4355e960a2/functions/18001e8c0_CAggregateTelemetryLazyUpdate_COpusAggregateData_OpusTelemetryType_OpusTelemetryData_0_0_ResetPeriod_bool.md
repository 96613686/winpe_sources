# CAggregateTelemetryLazyUpdate<COpusAggregateData,OpusTelemetryType,OpusTelemetryData,0,0>::ResetPeriod(bool)

- ea: `0x18001e8c0`
- end: `0x18001e8d4`
- name: `?ResetPeriod@?$CAggregateTelemetryLazyUpdate@VCOpusAggregateData@@W4OpusTelemetryType@@TOpusTelemetryData@@$0A@$0A@@@UEAAX_N@Z`
- size: `20`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18001b048`

## callees

- `0x180024010`

## pseudocode

```c
__int64 __fastcall CAggregateTelemetryLazyUpdate<COpusAggregateData,enum OpusTelemetryType,OpusTelemetryData,0,0>::ResetPeriod(
        __int64 *a1)
{
  __int64 v1; // rax

  v1 = *a1;
  a1[4] = 0;
  return (*(__int64 (**)(void))(v1 + 16))();
}

```

## disassembly

```asm
0x18001e8c0  mov     rax, [rcx]
0x18001e8c3  mov     qword ptr [rcx+20h], 0
0x18001e8cb  mov     rax, [rax+10h]
0x18001e8cf  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
