# MbbWriteEvent(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,...)

- ea: `0x140041664`
- end: `0x1400416a0`
- name: `?MbbWriteEvent@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1GZZ`
- size: `60`
- prototype: `void(PCEVENT_DESCRIPTOR EventDescriptor, LPCGUID ActivityId, LPCGUID RelatedActivityId, unsigned __int16, ...)`
- caller_count: `15`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000a660`
- `0x14000a9d0`
- `0x14000ada0`
- `0x14000ca94`
- `0x140011e94`
- `0x1400124a0`
- `0x140012a2c`
- `0x140013220`
- `0x14001e250`
- `0x14001fcf4`
- `0x14001ffa4`
- `0x140020330`
- `0x1400206cc`
- `0x140033970`
- `0x14003f994`

## callees

- `0x1400416a8`

## pseudocode

```c
void MbbWriteEvent(
        PCEVENT_DESCRIPTOR EventDescriptor,
        LPCGUID ActivityId,
        LPCGUID RelatedActivityId,
        unsigned __int16 a4,
        ...)
{
  va_list va; // [rsp+70h] [rbp+28h] BYREF

  va_start(va, a4);
  MbbWriteEventCommon(*(_QWORD *)&WPP_MAIN_CB.DeviceQueue.32, EventDescriptor, ActivityId, RelatedActivityId, a4, va);
}

```

## disassembly

```asm
0x140041664  mov     r11, rsp
0x140041667  mov     [r11+20h], r9w
0x14004166c  sub     rsp, 48h
0x140041670  lea     rax, [r11+28h]
0x140041674  mov     qword ptr [r11-18h], 0
0x14004167c  mov     [r11-20h], rax
0x140041680  mov     [r11-28h], r9w
0x140041685  mov     r9, r8; RelatedActivityId
0x140041688  mov     r8, rdx; ActivityId
0x14004168b  mov     rdx, rcx; EventDescriptor
0x14004168e  mov     rcx, qword ptr cs:WPP_MAIN_CB.DeviceQueue.20h; RegHandle
0x140041695  call    ?MbbWriteEventCommon@@YAX_KPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@2GPEAD@Z; MbbWriteEventCommon(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,char *)
0x14004169a  add     rsp, 48h
0x14004169e  retn
```
