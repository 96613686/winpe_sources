# CAggregateTelemetryLazyUpdate<COpusAggregateData,OpusTelemetryType,OpusTelemetryData,0,0>::~CAggregateTelemetryLazyUpdate<COpusAggregateData,OpusTelemetryType,OpusTelemetryData,0,0>(void)

- ea: `0x18001b304`
- end: `0x18001b313`
- name: `??1?$CAggregateTelemetryLazyUpdate@VCOpusAggregateData@@W4OpusTelemetryType@@TOpusTelemetryData@@$0A@$0A@@@UEAA@XZ`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180022fa1`

## callees

- `0x18001b258`

## pseudocode

```c
void __fastcall CAggregateTelemetryLazyUpdate<COpusAggregateData,enum OpusTelemetryType,OpusTelemetryData,0,0>::~CAggregateTelemetryLazyUpdate<COpusAggregateData,enum OpusTelemetryType,OpusTelemetryData,0,0>(
        __int64 a1,
        __int64 a2)
{
  *(_QWORD *)a1 = &COpusDecTlmAggregator::`vftable';
  CAggregateTelemetry<COpusAggregateData,enum OpusTelemetryType,OpusTelemetryData,0,0>::~CAggregateTelemetry<COpusAggregateData,enum OpusTelemetryType,OpusTelemetryData,0,0>(
    a1,
    a2);
}

```

## disassembly

```asm
0x18001b304  lea     rax, ??_7COpusDecTlmAggregator@@6B@; const COpusDecTlmAggregator::`vftable'
0x18001b30b  mov     [rcx], rax
0x18001b30e  jmp     ??1?$CAggregateTelemetry@VCOpusAggregateData@@W4OpusTelemetryType@@TOpusTelemetryData@@$0A@$0A@@@UEAA@XZ; CAggregateTelemetry<COpusAggregateData,OpusTelemetryType,OpusTelemetryData,0,0>::~CAggregateTelemetry<COpusAggregateData,OpusTelemetryType,OpusTelemetryData,0,0>(void)
```
