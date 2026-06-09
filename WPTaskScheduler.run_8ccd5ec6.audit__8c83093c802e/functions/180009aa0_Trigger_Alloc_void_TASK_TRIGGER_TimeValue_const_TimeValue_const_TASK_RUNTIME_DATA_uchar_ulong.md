# Trigger::Alloc(void *,_TASK_TRIGGER *,TimeValue const &,TimeValue const &,_TASK_RUNTIME_DATA *,uchar,ulong)

- ea: `0x180009aa0`
- end: `0x180009f0c`
- name: `?Alloc@Trigger@@SAPEAV1@PEAXPEAU_TASK_TRIGGER@@AEBVTimeValue@@2PEAU_TASK_RUNTIME_DATA@@EK@Z`
- size: `1132`
- prototype: `struct Trigger *__fastcall(void *, struct _TASK_TRIGGER *, const struct TimeValue *, const struct TimeValue *, struct _TASK_RUNTIME_DATA *, char, unsigned int)`
- caller_count: `5`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180003fa0`
- `0x180009740`
- `0x1800098a0`
- `0x18001bc80`
- `0x18001cf90`

## callees

- `0x180009aa0`
- `0x180009f20`
- `0x18000e970`
- `0x180010094`
- `0x18001b558`
- `0x18001b5b8`
- `0x18001b654`
- `0x18001b6c4`
- `0x18001b710`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009b55`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180009b55`

## pseudocode

```c
struct Trigger *__fastcall Trigger::Alloc(
        __int64 a1,
        struct _TASK_TRIGGER *a2,
        const struct TimeValue *a3,
        const struct TimeValue *a4,
        struct _TASK_RUNTIME_DATA *a5,
        char a6,
        unsigned int a7)
{
  int v11; // ecx
  char *v12; // rax
  PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *v13; // rdi
  __int64 v14; // rcx
  PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *v16; // rax
  int v17; // ecx
  PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate *v18; // rax
  void (__fastcall ***v19)(_QWORD, __int64); // r15
  __int64 v20; // rax
  __int64 v21; // rcx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicEx *v25; // rax
  __int64 v26; // rax
  PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm *v27; // rax
  PRIVATE_NAMESPACE_Triggers_H::TriggerCEAggregate *v28; // rax
  PRIVATE_NAMESPACE_Triggers_H::TriggerSystemEvent *v29; // rax

  if ( !a2 )
    return 0;
  if ( (byte_180030D03 & 8) != 0 )
    McTemplateU0q_EventWriteTransfer(
      a1,
      (const EVENT_DESCRIPTOR *)ScheduleTriggerType,
      *(unsigned int *)&a2->cbTriggerSize);
  v11 = *(_DWORD *)&a2->cbTriggerSize;
  if ( *(_DWORD *)&a2->cbTriggerSize == 1 )
  {
    v12 = (char *)operator new(0x120u, (const struct std::nothrow_t *)&std::nothrow);
    v13 = (PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *)v12;
    if ( v12 )
    {
      *(_QWORD *)v12 = &Trigger::`vftable';
      *((_QWORD *)v12 + 7) = 0;
      *((_DWORD *)v12 + 16) = 0;
      *(_OWORD *)(v12 + 24) = 0;
      *((_QWORD *)v12 + 5) = 0;
      *((_QWORD *)v12 + 6) = 0;
      *((_QWORD *)v12 + 13) = 0;
      *((_DWORD *)v12 + 28) = 0;
      *(_OWORD *)(v12 + 72) = 0;
      *((_QWORD *)v12 + 11) = 0;
      *((_QWORD *)v12 + 12) = 0;
      *((_QWORD *)v12 + 22) = 0;
      *((_DWORD *)v12 + 46) = 0;
      InitializeCriticalSection((LPCRITICAL_SECTION)v12 + 3);
      *((_QWORD *)v13 + 2) = (char *)v13 + 8;
      *((_QWORD *)v13 + 1) = (char *)v13 + 8;
      *((_OWORD *)v13 + 10) = 0;
      *(_QWORD *)v13 = &PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::`vftable';
      *((_DWORD *)v13 + 48) = 0;
      *((_QWORD *)v13 + 25) = 0;
      *((_QWORD *)v13 + 32) = 0;
      *((_QWORD *)v13 + 33) = 0;
      *((_OWORD *)v13 + 13) = 0;
      *((_OWORD *)v13 + 14) = 0;
      *((_OWORD *)v13 + 15) = 0;
      *((_QWORD *)v13 + 34) = 0;
      *((_QWORD *)v13 + 35) = 0;
      *((_DWORD *)v13 + 40) = 1;
      *((_QWORD *)v13 + 21) = (char *)v13 + 208;
      if ( (*(int (__fastcall **)(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *, __int64, struct _TASK_TRIGGER *, struct _TASK_RUNTIME_DATA *, const struct TimeValue *, const struct TimeValue *, _BYTE, unsigned int))(*(_QWORD *)v13 + 16LL))(
             v13,
             a1,
             a2,
             a5,
             a3,
             a4,
             0,
             a7) >= 0 )
        return v13;
      if ( (byte_180030D02 & 0x40) == 0 )
        goto LABEL_13;
LABEL_12:
      McTemplateU0q_EventWriteTransfer(v14, (const EVENT_DESCRIPTOR *)L"5", *(unsigned int *)&a2->cbTriggerSize);
LABEL_13:
      (**(void (__fastcall ***)(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *, __int64))v13)(v13, 1);
      return 0;
    }
    return 0;
  }
  if ( !v11 )
  {
    v16 = (PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *)operator new(
                                                                 0x300u,
                                                                 (const struct std::nothrow_t *)&std::nothrow);
    v13 = v16;
    if ( v16 )
    {
      PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::TriggerPeriodicBase(v16);
      *(_QWORD *)v13 = &PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodic::`vftable';
      *(_OWORD *)((char *)v13 + 744) = 0;
      *((_QWORD *)v13 + 95) = 0;
      *((_DWORD *)v13 + 40) = 0;
      *((_QWORD *)v13 + 21) = (char *)v13 + 744;
      if ( (*(int (__fastcall **)(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *, __int64, struct _TASK_TRIGGER *, struct _TASK_RUNTIME_DATA *, const struct TimeValue *, const struct TimeValue *, _BYTE, unsigned int))(*(_QWORD *)v13 + 16LL))(
             v13,
             a1,
             a2,
             a5,
             a3,
             a4,
             0,
             a7) >= 0 )
        return v13;
      if ( (byte_180030D02 & 0x40) == 0 )
        goto LABEL_13;
      goto LABEL_12;
    }
    return 0;
  }
  v17 = v11 - 2;
  if ( !v17 )
  {
    v18 = (PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate *)operator new(
                                                              0xE0u,
                                                              (const struct std::nothrow_t *)&std::nothrow);
    if ( !v18 )
      return 0;
    v20 = PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate::TriggerAggregate(v18);
    v19 = (void (__fastcall ***)(_QWORD, __int64))v20;
    if ( !v20
      || (*(int (__fastcall **)(__int64, __int64, struct _TASK_TRIGGER *, struct _TASK_RUNTIME_DATA *, const struct TimeValue *, const struct TimeValue *, char, unsigned int))(*(_QWORD *)v20 + 16LL))(
           v20,
           a1,
           a2,
           a5,
           a3,
           a4,
           a6,
           a7) >= 0 )
    {
      return (struct Trigger *)v19;
    }
    if ( (byte_180030D02 & 0x40) == 0 )
    {
LABEL_41:
      (**v19)(v19, 1);
      return 0;
    }
LABEL_40:
    McTemplateU0q_EventWriteTransfer(v21, (const EVENT_DESCRIPTOR *)L"5", *(unsigned int *)&a2->cbTriggerSize);
    goto LABEL_41;
  }
  v22 = v17 - 1;
  if ( !v22 )
  {
    v29 = (PRIVATE_NAMESPACE_Triggers_H::TriggerSystemEvent *)operator new(
                                                                0xD8u,
                                                                (const struct std::nothrow_t *)&std::nothrow);
    if ( !v29 )
      return 0;
    v26 = PRIVATE_NAMESPACE_Triggers_H::TriggerSystemEvent::TriggerSystemEvent(v29);
    goto LABEL_35;
  }
  v23 = v22 - 1;
  if ( !v23 )
  {
    v28 = (PRIVATE_NAMESPACE_Triggers_H::TriggerCEAggregate *)operator new(
                                                                0x100u,
                                                                (const struct std::nothrow_t *)&std::nothrow);
    if ( !v28 )
      return 0;
    v26 = PRIVATE_NAMESPACE_Triggers_H::TriggerCEAggregate::TriggerCEAggregate(v28);
    goto LABEL_35;
  }
  v24 = v23 - 1;
  if ( !v24 )
  {
    v27 = (PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm *)operator new(
                                                          0x140u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
    if ( !v27 )
      return 0;
    v26 = PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::TriggerAlarm(v27);
    goto LABEL_35;
  }
  if ( v24 == 1 )
  {
    v25 = (PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicEx *)operator new(
                                                               0x300u,
                                                               (const struct std::nothrow_t *)&std::nothrow);
    if ( !v25 )
      return 0;
    v26 = PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicEx::TriggerPeriodicEx(v25);
LABEL_35:
    v19 = (void (__fastcall ***)(_QWORD, __int64))v26;
    if ( !v26
      || (*(int (__fastcall **)(__int64, __int64, struct _TASK_TRIGGER *, struct _TASK_RUNTIME_DATA *, const struct TimeValue *, const struct TimeValue *, _BYTE, unsigned int))(*(_QWORD *)v26 + 16LL))(
           v26,
           a1,
           a2,
           a5,
           a3,
           a4,
           0,
           a7) >= 0 )
    {
      return (struct Trigger *)v19;
    }
    if ( (byte_180030D02 & 0x40) == 0 )
      goto LABEL_41;
    goto LABEL_40;
  }
  return 0;
}

```

## disassembly

```asm
0x180009aa0  mov     [rsp+arg_18], rbx
0x180009aa5  push    rbp
0x180009aa6  push    rsi
0x180009aa7  push    r14
0x180009aa9  sub     rsp, 50h
0x180009aad  mov     rsi, r9
0x180009ab0  mov     rbp, r8
0x180009ab3  mov     rbx, rdx
0x180009ab6  mov     r14, rcx
0x180009ab9  test    rdx, rdx
0x180009abc  jz      loc_180009D98
0x180009ac2  test    cs:byte_180030D03, 8
0x180009ac9  jnz     loc_180009D9F
0x180009acf  mov     ecx, [rbx]
0x180009ad1  mov     [rsp+68h+arg_0], rdi
0x180009ad6  mov     [rsp+68h+arg_10], r15
0x180009ade  cmp     ecx, 1
0x180009ae1  jnz     loc_180009C31
0x180009ae7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009aee  mov     ecx, 120h; unsigned __int64
0x180009af3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009af8  mov     [rsp+68h+arg_8], rax
0x180009afd  mov     rdi, rax
0x180009b00  test    rax, rax
0x180009b03  jz      loc_180009D06
0x180009b09  xor     r15d, r15d
0x180009b0c  lea     rax, ??_7Trigger@@6B@; const Trigger::`vftable'
0x180009b13  mov     [rdi], rax
0x180009b16  lea     rcx, [rdi+78h]; lpCriticalSection
0x180009b1a  mov     [rdi+38h], r15
0x180009b1e  xor     eax, eax
0x180009b20  mov     [rdi+40h], r15d
0x180009b24  xorps   xmm0, xmm0
0x180009b27  movups  xmmword ptr [rdi+18h], xmm0
0x180009b2b  mov     [rdi+28h], rax
0x180009b2f  mov     [rdi+30h], rax
0x180009b33  mov     [rdi+68h], r15
0x180009b37  mov     [rdi+70h], r15d
0x180009b3b  movups  xmmword ptr [rdi+48h], xmm0
0x180009b3f  mov     [rdi+58h], rax
0x180009b43  mov     [rdi+60h], rax
0x180009b47  mov     [rdi+0B0h], r15
0x180009b4e  mov     [rdi+0B8h], r15d
0x180009b55  call    cs:__imp_InitializeCriticalSection
0x180009b5b  xorps   xmm0, xmm0
0x180009b5e  lea     rax, [rdi+8]
0x180009b62  mov     [rdi+10h], rax
0x180009b66  xor     ecx, ecx
0x180009b68  mov     [rax], rax
0x180009b6b  lea     rax, ??_7TriggerWNF@PRIVATE_NAMESPACE_Triggers_H@@6B@; const PRIVATE_NAMESPACE_Triggers_H::TriggerWNF::`vftable'
0x180009b72  movups  xmmword ptr [rdi+0A0h], xmm0
0x180009b79  mov     [rdi], rax
0x180009b7c  lea     rax, [rdi+0D0h]
0x180009b83  mov     [rdi+0C0h], r15d
0x180009b8a  mov     [rdi+0C8h], r15
0x180009b91  mov     [rdi+100h], r15
0x180009b98  mov     [rdi+108h], r15
0x180009b9f  movups  xmmword ptr [rax], xmm0
0x180009ba2  movups  xmmword ptr [rax+10h], xmm0
0x180009ba6  movups  xmmword ptr [rdi+0F0h], xmm0
0x180009bad  mov     [rdi+110h], rcx
0x180009bb4  mov     [rdi+118h], rcx
0x180009bbb  mov     dword ptr [rdi+0A0h], 1
0x180009bc5  mov     [rdi+0A8h], rax
0x180009bcc  test    rdi, rdi
0x180009bcf  jz      short loc_180009C10
0x180009bd1  mov     rax, [rdi]
0x180009bd4  mov     r8, rbx
0x180009bd7  mov     ecx, [rsp+68h+arg_30]
0x180009bde  mov     rdx, r14
0x180009be1  mov     r9, [rsp+68h+arg_20]
0x180009be9  mov     [rsp+68h+var_30], ecx
0x180009bed  mov     rcx, rdi
0x180009bf0  mov     rax, [rax+10h]
0x180009bf4  mov     [rsp+68h+var_38], r15b
0x180009bf9  mov     [rsp+68h+var_40], rsi
0x180009bfe  mov     [rsp+68h+var_48], rbp
0x180009c03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c08  test    eax, eax
0x180009c0a  js      loc_180009EFA
0x180009c10  mov     rax, rdi
0x180009c13  mov     rdi, [rsp+68h+arg_0]
0x180009c18  mov     r15, [rsp+68h+arg_10]
0x180009c20  mov     rbx, [rsp+68h+arg_18]
0x180009c28  add     rsp, 50h
0x180009c2c  pop     r14
0x180009c2e  pop     rsi
0x180009c2f  pop     rbp
0x180009c30  retn
0x180009c31  test    ecx, ecx
0x180009c33  jnz     loc_180009D11
0x180009c39  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009c40  mov     ecx, 300h; unsigned __int64
0x180009c45  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009c4a  mov     [rsp+68h+arg_8], rax
0x180009c4f  mov     rdi, rax
0x180009c52  test    rax, rax
0x180009c55  jz      loc_180009D06
0x180009c5b  mov     rcx, rax; this
0x180009c5e  call    ??0TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@AEAA@XZ; PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::TriggerPeriodicBase(void)
0x180009c63  lea     rax, ??_7TriggerPeriodic@PRIVATE_NAMESPACE_Triggers_H@@6B@; const PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodic::`vftable'
0x180009c6a  xor     ecx, ecx
0x180009c6c  mov     [rdi], rax
0x180009c6f  xor     r15d, r15d
0x180009c72  lea     rax, [rdi+2E8h]
0x180009c79  xorps   xmm0, xmm0
0x180009c7c  movups  xmmword ptr [rax], xmm0
0x180009c7f  mov     [rax+10h], rcx
0x180009c83  mov     [rdi+0A0h], r15d
0x180009c8a  mov     [rdi+0A8h], rax
0x180009c91  test    rdi, rdi
0x180009c94  jz      loc_180009C10
0x180009c9a  mov     rax, [rdi]
0x180009c9d  mov     r8, rbx
0x180009ca0  mov     ecx, [rsp+68h+arg_30]
0x180009ca7  mov     rdx, r14
0x180009caa  mov     r9, [rsp+68h+arg_20]
0x180009cb2  mov     [rsp+68h+var_30], ecx
0x180009cb6  mov     rcx, rdi
0x180009cb9  mov     rax, [rax+10h]
0x180009cbd  mov     [rsp+68h+var_38], r15b
0x180009cc2  mov     [rsp+68h+var_40], rsi
0x180009cc7  mov     [rsp+68h+var_48], rbp
0x180009ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cd1  test    eax, eax
0x180009cd3  jns     loc_180009C10
0x180009cd9  test    cs:byte_180030D02, 40h
0x180009ce0  jz      short loc_180009CF1
0x180009ce2  mov     r8d, [rbx]
0x180009ce5  lea     rdx, TriggerCreationError; "5"
0x180009cec  call    McTemplateU0q_EventWriteTransfer
0x180009cf1  mov     rax, [rdi]
0x180009cf4  mov     edx, 1
0x180009cf9  mov     rcx, rdi
0x180009cfc  mov     rax, [rax]
0x180009cff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d04  jmp     short loc_180009D09
0x180009d06  xor     r15d, r15d
0x180009d09  mov     rdi, r15
0x180009d0c  jmp     loc_180009C10
0x180009d11  sub     ecx, 2
0x180009d14  jnz     loc_180009DB3
0x180009d1a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009d21  mov     ecx, 0E0h; unsigned __int64
0x180009d26  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009d2b  mov     [rsp+68h+arg_8], rax
0x180009d30  test    rax, rax
0x180009d33  jnz     short loc_180009D3A
0x180009d35  xor     r15d, r15d
0x180009d38  jmp     short loc_180009D90
0x180009d3a  mov     rcx, rax; this
0x180009d3d  call    ??0TriggerAggregate@PRIVATE_NAMESPACE_Triggers_H@@AEAA@XZ; PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate::TriggerAggregate(void)
0x180009d42  mov     r15, rax
0x180009d45  test    rax, rax
0x180009d48  jz      short loc_180009D90
0x180009d4a  mov     ecx, [rsp+68h+arg_30]
0x180009d51  mov     r8, rbx
0x180009d54  mov     rax, [rax]
0x180009d57  mov     rdx, r14
0x180009d5a  mov     r9, [rsp+68h+arg_20]
0x180009d62  mov     [rsp+68h+var_30], ecx
0x180009d66  movzx   ecx, [rsp+68h+arg_28]
0x180009d6e  mov     rax, [rax+10h]
0x180009d72  mov     [rsp+68h+var_38], cl
0x180009d76  mov     rcx, r15
0x180009d79  mov     [rsp+68h+var_40], rsi
0x180009d7e  mov     [rsp+68h+var_48], rbp
0x180009d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d88  test    eax, eax
0x180009d8a  js      loc_180009ECA
0x180009d90  mov     rax, r15
0x180009d93  jmp     loc_180009C13
0x180009d98  xor     eax, eax
0x180009d9a  jmp     loc_180009C20
0x180009d9f  mov     r8d, [rdx]
0x180009da2  lea     rdx, ScheduleTriggerType
0x180009da9  call    McTemplateU0q_EventWriteTransfer
0x180009dae  jmp     loc_180009ACF
0x180009db3  sub     ecx, 1
0x180009db6  jz      loc_180009E4D
0x180009dbc  sub     ecx, 1
0x180009dbf  jz      short loc_180009E24
0x180009dc1  sub     ecx, 1
0x180009dc4  jz      short loc_180009DFB
0x180009dc6  cmp     ecx, 1
0x180009dc9  jz      short loc_180009DD2
0x180009dcb  xor     eax, eax
0x180009dcd  jmp     loc_180009C13
0x180009dd2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009dd9  mov     ecx, 300h; unsigned __int64
0x180009dde  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009de3  mov     [rsp+68h+arg_8], rax
0x180009de8  test    rax, rax
0x180009deb  jz      loc_180009D35
0x180009df1  mov     rcx, rax; this
0x180009df4  call    ??0TriggerPeriodicEx@PRIVATE_NAMESPACE_Triggers_H@@AEAA@XZ; PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicEx::TriggerPeriodicEx(void)
0x180009df9  jmp     short loc_180009E74
0x180009dfb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009e02  mov     ecx, 140h; unsigned __int64
0x180009e07  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009e0c  mov     [rsp+68h+arg_8], rax
0x180009e11  test    rax, rax
0x180009e14  jz      loc_180009D35
0x180009e1a  mov     rcx, rax; this
0x180009e1d  call    ??0TriggerAlarm@PRIVATE_NAMESPACE_Triggers_H@@AEAA@XZ; PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::TriggerAlarm(void)
0x180009e22  jmp     short loc_180009E74
0x180009e24  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009e2b  mov     ecx, 100h; unsigned __int64
0x180009e30  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009e35  mov     [rsp+68h+arg_8], rax
0x180009e3a  test    rax, rax
0x180009e3d  jz      loc_180009D35
0x180009e43  mov     rcx, rax; this
0x180009e46  call    ??0TriggerCEAggregate@PRIVATE_NAMESPACE_Triggers_H@@AEAA@XZ; PRIVATE_NAMESPACE_Triggers_H::TriggerCEAggregate::TriggerCEAggregate(void)
0x180009e4b  jmp     short loc_180009E74
0x180009e4d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009e54  mov     ecx, 0D8h; unsigned __int64
0x180009e59  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009e5e  mov     [rsp+68h+arg_8], rax
0x180009e63  test    rax, rax
0x180009e66  jz      loc_180009D35
0x180009e6c  mov     rcx, rax; this
0x180009e6f  call    ??0TriggerSystemEvent@PRIVATE_NAMESPACE_Triggers_H@@AEAA@XZ; PRIVATE_NAMESPACE_Triggers_H::TriggerSystemEvent::TriggerSystemEvent(void)
0x180009e74  mov     r15, rax
0x180009e77  test    rax, rax
0x180009e7a  jz      loc_180009D90
0x180009e80  mov     rax, [rax]
0x180009e83  mov     r8, rbx
0x180009e86  mov     ecx, [rsp+68h+arg_30]
0x180009e8d  mov     rdx, r14
0x180009e90  mov     r9, [rsp+68h+arg_20]
0x180009e98  mov     [rsp+68h+var_30], ecx
0x180009e9c  mov     rcx, r15
0x180009e9f  mov     rax, [rax+10h]
0x180009ea3  mov     [rsp+68h+var_38], 0
0x180009ea8  mov     [rsp+68h+var_40], rsi
0x180009ead  mov     [rsp+68h+var_48], rbp
0x180009eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009eb7  test    eax, eax
0x180009eb9  jns     loc_180009D90
0x180009ebf  test    cs:byte_180030D02, 40h
0x180009ec6  jnz     short loc_180009ED3
0x180009ec8  jmp     short loc_180009EE2
0x180009eca  test    cs:byte_180030D02, 40h
0x180009ed1  jz      short loc_180009EE2
0x180009ed3  mov     r8d, [rbx]
0x180009ed6  lea     rdx, TriggerCreationError; "5"
0x180009edd  call    McTemplateU0q_EventWriteTransfer
0x180009ee2  mov     rax, [r15]
0x180009ee5  mov     edx, 1
0x180009eea  mov     rcx, r15
0x180009eed  mov     rax, [rax]
0x180009ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ef5  jmp     loc_180009D35
0x180009efa  test    cs:byte_180030D02, 40h
0x180009f01  jz      loc_180009CF1
0x180009f07  jmp     loc_180009CE2
```
