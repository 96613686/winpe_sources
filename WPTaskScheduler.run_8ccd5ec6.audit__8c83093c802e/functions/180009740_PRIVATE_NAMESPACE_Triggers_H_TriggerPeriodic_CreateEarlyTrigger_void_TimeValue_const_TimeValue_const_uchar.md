# PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodic::CreateEarlyTrigger(void *,TimeValue const &,TimeValue const &,uchar)

- ea: `0x180009740`
- end: `0x180009897`
- name: `?CreateEarlyTrigger@TriggerPeriodic@PRIVATE_NAMESPACE_Triggers_H@@EEAAJPEAXAEBVTimeValue@@1E@Z`
- size: `343`
- prototype: `int(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodic *__hidden this, void *, const struct TimeValue *, const struct TimeValue *, unsigned __int8)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x180009740`
- `0x180009aa0`
- `0x18000ea40`
- `0x18001dd84`
- `0x180020c30`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodic::CreateEarlyTrigger(
        PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodic *this,
        __int64 a2,
        const struct TimeValue *a3,
        const struct TimeValue *a4,
        unsigned __int8 a5)
{
  __int64 v9; // rcx
  __int64 result; // rax
  int v11; // edx
  struct Trigger *v12; // rcx
  __int64 v13; // r8
  _TASK_TRIGGER v14; // [rsp+40h] [rbp-68h] BYREF

  if ( (byte_180030D04 & 2) != 0 )
    McTemplateU0t_EventWriteTransfer(this, a2, *((_QWORD *)this + 95) != 0);
  v9 = *((_QWORD *)this + 95);
  if ( !v9 )
    return 0;
  *(_QWORD *)&v14.cbTriggerSize = 1;
  *(_QWORD *)&v14.wBeginDay = v9;
  v11 = *(_DWORD *)(v9 + 28);
  if ( (v11 & 1) == 0 )
  {
    *(_DWORD *)(v9 + 28) = v11 | 1;
    if ( byte_180030D03 < 0 )
      McGenEventWrite_EventWriteTransfer(
        v9,
        (const EVENT_DESCRIPTOR *)LevelWnfStateEarlyTriggerOverride,
        (__int64)a3,
        1u,
        (PEVENT_DATA_DESCRIPTOR)&v14.wStartHour);
  }
  if ( *(_DWORD *)(*((_QWORD *)this + 95) + 24LL) )
  {
    if ( (byte_180030D04 & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        v9,
        (const EVENT_DESCRIPTOR *)DelayedEarlyTriggerError,
        (__int64)a3,
        1u,
        (PEVENT_DATA_DESCRIPTOR)&v14.wStartHour);
    return 2194604295LL;
  }
  else
  {
    v12 = Trigger::Alloc(a2, &v14, a3, a4, 0, a5 + 1, 0);
    if ( v12 )
    {
      result = 0;
      *((_QWORD *)this + 51) = v12;
    }
    else
    {
      if ( (byte_180030D04 & 8) != 0 )
        McGenEventWrite_EventWriteTransfer(
          0,
          (const EVENT_DESCRIPTOR *)FailedCreateEarlyTriggerError,
          v13,
          1u,
          (PEVENT_DATA_DESCRIPTOR)&v14.wStartHour);
      return 2147942414LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180009740  push    rbx
0x180009742  push    rbp
0x180009743  push    rsi
0x180009744  push    rdi
0x180009745  push    r14
0x180009747  push    r15
0x180009749  sub     rsp, 78h
0x18000974d  mov     rax, cs:__security_cookie
0x180009754  xor     rax, rsp
0x180009757  mov     qword ptr [rsp+0A8h+var_68.TriggerType], rax
0x18000975c  xor     r15d, r15d
0x18000975f  mov     r14, r9
0x180009762  test    cs:byte_180030D04, 2
0x180009769  mov     rbp, r8
0x18000976c  mov     rsi, rdx
0x18000976f  mov     rdi, rcx
0x180009772  jz      short loc_180009787
0x180009774  mov     r8d, r15d
0x180009777  cmp     [rcx+2F8h], r8
0x18000977e  setnz   r8b
0x180009782  call    McTemplateU0t_EventWriteTransfer
0x180009787  mov     rcx, [rdi+2F8h]
0x18000978e  test    rcx, rcx
0x180009791  jnz     short loc_18000979A
0x180009793  xor     eax, eax
0x180009795  jmp     loc_18000987D
0x18000979a  mov     qword ptr [rsp+0A8h+var_68.cbTriggerSize], 1
0x1800097a3  mov     qword ptr [rsp+0A8h+var_68.wBeginDay], rcx
0x1800097a8  mov     edx, [rcx+1Ch]
0x1800097ab  test    dl, 1
0x1800097ae  jnz     short loc_1800097DB
0x1800097b0  or      edx, 1
0x1800097b3  mov     [rcx+1Ch], edx
0x1800097b6  cmp     cs:byte_180030D03, r15b
0x1800097bd  jge     short loc_1800097DB
0x1800097bf  lea     rax, [rsp+0A8h+var_68.wStartHour]
0x1800097c4  mov     r9d, 1
0x1800097ca  lea     rdx, LevelWnfStateEarlyTriggerOverride
0x1800097d1  mov     [rsp+0A8h+var_88], rax
0x1800097d6  call    McGenEventWrite_EventWriteTransfer
0x1800097db  mov     rax, [rdi+2F8h]
0x1800097e2  cmp     [rax+18h], r15d
0x1800097e6  jbe     short loc_180009814
0x1800097e8  test    cs:byte_180030D04, 1
0x1800097ef  jz      short loc_18000980D
0x1800097f1  lea     rax, [rsp+0A8h+var_68.wStartHour]
0x1800097f6  mov     r9d, 1
0x1800097fc  lea     rdx, DelayedEarlyTriggerError
0x180009803  mov     [rsp+0A8h+var_88], rax
0x180009808  call    McGenEventWrite_EventWriteTransfer
0x18000980d  mov     eax, 82CF0107h
0x180009812  jmp     short loc_18000987D
0x180009814  movzx   eax, [rsp+0A8h+arg_20]
0x18000981c  lea     rdx, [rsp+0A8h+var_68]; struct _TASK_TRIGGER *
0x180009821  inc     al
0x180009823  mov     [rsp+0A8h+var_78], r15d; unsigned int
0x180009828  mov     [rsp+0A8h+var_80], al; char
0x18000982c  mov     r9, r14; struct TimeValue *
0x18000982f  mov     r8, rbp; struct TimeValue *
0x180009832  mov     [rsp+0A8h+var_88], r15; struct _TASK_RUNTIME_DATA *
0x180009837  mov     rcx, rsi; void *
0x18000983a  call    ?Alloc@Trigger@@SAPEAV1@PEAXPEAU_TASK_TRIGGER@@AEBVTimeValue@@2PEAU_TASK_RUNTIME_DATA@@EK@Z; Trigger::Alloc(void *,_TASK_TRIGGER *,TimeValue const &,TimeValue const &,_TASK_RUNTIME_DATA *,uchar,ulong)
0x18000983f  mov     rcx, rax
0x180009842  test    rax, rax
0x180009845  jnz     short loc_180009873
0x180009847  test    cs:byte_180030D04, 8
0x18000984e  jz      short loc_18000986C
0x180009850  lea     rax, [rsp+0A8h+var_68.wStartHour]
0x180009855  mov     r9d, 1
0x18000985b  lea     rdx, FailedCreateEarlyTriggerError
0x180009862  mov     [rsp+0A8h+var_88], rax
0x180009867  call    McGenEventWrite_EventWriteTransfer
0x18000986c  mov     eax, 8007000Eh
0x180009871  jmp     short loc_18000987D
0x180009873  mov     eax, r15d
0x180009876  mov     [rdi+198h], rcx
0x18000987d  mov     rcx, qword ptr [rsp+0A8h+var_68.TriggerType]
0x180009882  xor     rcx, rsp; StackCookie
0x180009885  call    __security_check_cookie
0x18000988a  add     rsp, 78h
0x18000988e  pop     r15
0x180009890  pop     r14
0x180009892  pop     rdi
0x180009893  pop     rsi
0x180009894  pop     rbp
0x180009895  pop     rbx
0x180009896  retn
```
