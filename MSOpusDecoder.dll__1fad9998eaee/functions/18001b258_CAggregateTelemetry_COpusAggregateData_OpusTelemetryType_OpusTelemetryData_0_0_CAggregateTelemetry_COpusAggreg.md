# CAggregateTelemetry<COpusAggregateData,OpusTelemetryType,OpusTelemetryData,0,0>::~CAggregateTelemetry<COpusAggregateData,OpusTelemetryType,OpusTelemetryData,0,0>(void)

- ea: `0x18001b258`
- end: `0x18001b2fc`
- name: `??1?$CAggregateTelemetry@VCOpusAggregateData@@W4OpusTelemetryType@@TOpusTelemetryData@@$0A@$0A@@@UEAA@XZ`
- size: `164`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18001b304`
- `0x18001b45c`
- `0x18001b570`
- `0x18001b5b0`

## callees

- `0x180001914`
- `0x18001b258`
- `0x18001d4f0`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b288`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b288`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAggregateTelemetry<COpusAggregateData,enum OpusTelemetryType,OpusTelemetryData,0,0>::~CAggregateTelemetry<COpusAggregateData,enum OpusTelemetryType,OpusTelemetryData,0,0>(
        __int64 a1,
        __int64 a2)
{
  void *v3; // rdi
  _QWORD *v4; // rdi
  __int64 v5; // rcx

  *(_QWORD *)a1 = &CAggregateTelemetry<COpusAggregateData,enum OpusTelemetryType,OpusTelemetryData,0,0>::`vftable';
  if ( *(_BYTE *)(a1 + 16) )
  {
    LOBYTE(a2) = 1;
    CAggregateTelemetry<COpusAggregateData,enum OpusTelemetryType,OpusTelemetryData,0,0>::Log(a1, a2);
  }
  v3 = *(void **)(a1 + 24);
  if ( v3 )
  {
    DeleteCriticalSection(*(LPCRITICAL_SECTION *)(a1 + 24));
    operator delete(v3);
    *(_QWORD *)(a1 + 24) = 0;
  }
  if ( *(_BYTE *)(a1 + 17) )
  {
    v4 = *(_QWORD **)(a1 + 8);
    if ( v4 )
    {
      *v4 = &COpusAggregateData::`vftable';
      v5 = v4[5];
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      *v4 = &CAggregateValuesBase<enum OpusTelemetryType,OpusTelemetryData>::`vftable';
      operator delete(v4);
      *(_QWORD *)(a1 + 8) = 0;
    }
  }
}

```

## disassembly

```asm
0x18001b258  mov     [rsp+arg_0], rbx
0x18001b25d  push    rdi
0x18001b25e  sub     rsp, 20h
0x18001b262  mov     rbx, rcx
0x18001b265  lea     rax, ??_7?$CAggregateTelemetry@VCOpusAggregateData@@W4OpusTelemetryType@@TOpusTelemetryData@@$0A@$0A@@@6B@; const CAggregateTelemetry<COpusAggregateData,OpusTelemetryType,OpusTelemetryData,0,0>::`vftable'
0x18001b26c  mov     [rcx], rax
0x18001b26f  cmp     byte ptr [rcx+10h], 0
0x18001b273  jz      short loc_18001B27C
0x18001b275  mov     dl, 1
0x18001b277  call    ?Log@?$CAggregateTelemetry@VCOpusAggregateData@@W4OpusTelemetryType@@TOpusTelemetryData@@$0A@$0A@@@UEAAX_N@Z; CAggregateTelemetry<COpusAggregateData,OpusTelemetryType,OpusTelemetryData,0,0>::Log(bool)
0x18001b27c  mov     rdi, [rbx+18h]
0x18001b280  test    rdi, rdi
0x18001b283  jz      short loc_18001B2A3
0x18001b285  mov     rcx, rdi; lpCriticalSection
0x18001b288  call    cs:__imp_DeleteCriticalSection
0x18001b28e  mov     edx, 28h ; '('
0x18001b293  mov     rcx, rdi; Block
0x18001b296  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b29b  mov     qword ptr [rbx+18h], 0
0x18001b2a3  cmp     byte ptr [rbx+11h], 0
0x18001b2a7  jz      short loc_18001B2F1
0x18001b2a9  mov     rdi, [rbx+8]
0x18001b2ad  test    rdi, rdi
0x18001b2b0  jz      short loc_18001B2F1
0x18001b2b2  lea     rax, ??_7COpusAggregateData@@6B@; const COpusAggregateData::`vftable'
0x18001b2b9  mov     [rdi], rax
0x18001b2bc  mov     rcx, [rdi+28h]
0x18001b2c0  test    rcx, rcx
0x18001b2c3  jz      short loc_18001B2D2
0x18001b2c5  mov     rax, [rcx]
0x18001b2c8  mov     rax, [rax+10h]
0x18001b2cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2d1  nop
0x18001b2d2  lea     rax, ??_7?$CAggregateValuesBase@W4OpusTelemetryType@@TOpusTelemetryData@@@@6B@; const CAggregateValuesBase<OpusTelemetryType,OpusTelemetryData>::`vftable'
0x18001b2d9  mov     [rdi], rax
0x18001b2dc  mov     edx, 30h ; '0'
0x18001b2e1  mov     rcx, rdi; Block
0x18001b2e4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001b2e9  mov     qword ptr [rbx+8], 0
0x18001b2f1  mov     rbx, [rsp+28h+arg_0]
0x18001b2f6  add     rsp, 20h
0x18001b2fa  pop     rdi
0x18001b2fb  retn
```
