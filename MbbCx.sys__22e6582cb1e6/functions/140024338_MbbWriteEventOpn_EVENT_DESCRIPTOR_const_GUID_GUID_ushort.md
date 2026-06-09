# MbbWriteEventOpn(_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,...)

- ea: `0x140024338`
- end: `0x140024374`
- name: `?MbbWriteEventOpn@@YAXPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@1GZZ`
- size: `60`
- prototype: `void(PCEVENT_DESCRIPTOR EventDescriptor, LPCGUID ActivityId, LPCGUID RelatedActivityId, unsigned __int16, ...)`
- caller_count: `10`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000f6c0`
- `0x140012a2c`
- `0x140012c90`
- `0x1400178e0`
- `0x140017aa0`
- `0x140017c80`
- `0x14001e250`
- `0x14001fcf4`
- `0x1400206cc`
- `0x140020c18`

## callees

- `0x1400416a8`

## pseudocode

```c
void MbbWriteEventOpn(
        PCEVENT_DESCRIPTOR EventDescriptor,
        LPCGUID ActivityId,
        LPCGUID RelatedActivityId,
        unsigned __int16 a4,
        ...)
{
  va_list va; // [rsp+70h] [rbp+28h] BYREF

  va_start(va, a4);
  MbbWriteEventCommon(
    (REGHANDLE)WPP_MAIN_CB.Dpc.DpcListEntry.Next,
    EventDescriptor,
    ActivityId,
    RelatedActivityId,
    a4,
    va);
}

```

## disassembly

```asm
0x140024338  mov     r11, rsp
0x14002433b  mov     [r11+20h], r9w
0x140024340  sub     rsp, 48h
0x140024344  lea     rax, [r11+28h]
0x140024348  mov     qword ptr [r11-18h], 0
0x140024350  mov     [r11-20h], rax
0x140024354  mov     [r11-28h], r9w
0x140024359  mov     r9, r8; RelatedActivityId
0x14002435c  mov     r8, rdx; ActivityId
0x14002435f  mov     rdx, rcx; EventDescriptor
0x140024362  mov     rcx, cs:WPP_MAIN_CB.Dpc.DpcListEntry.Next; RegHandle
0x140024369  call    ?MbbWriteEventCommon@@YAX_KPEBU_EVENT_DESCRIPTOR@@PEAU_GUID@@2GPEAD@Z; MbbWriteEventCommon(unsigned __int64,_EVENT_DESCRIPTOR const *,_GUID *,_GUID *,ushort,char *)
0x14002436e  add     rsp, 48h
0x140024372  retn
```
