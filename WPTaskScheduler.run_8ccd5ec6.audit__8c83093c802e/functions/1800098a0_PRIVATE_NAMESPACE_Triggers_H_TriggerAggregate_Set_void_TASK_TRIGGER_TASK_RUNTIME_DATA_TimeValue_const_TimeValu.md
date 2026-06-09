# PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate::Set(void *,_TASK_TRIGGER *,_TASK_RUNTIME_DATA *,TimeValue const &,TimeValue const &,uchar,ulong)

- ea: `0x1800098a0`
- end: `0x180009a8d`
- name: `?Set@TriggerAggregate@PRIVATE_NAMESPACE_Triggers_H@@EEAAJPEAXPEAU_TASK_TRIGGER@@PEAU_TASK_RUNTIME_DATA@@AEBVTimeValue@@3EK@Z`
- size: `493`
- prototype: `int(PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate *__hidden this, void *, struct _TASK_TRIGGER *, struct _TASK_RUNTIME_DATA *, const struct TimeValue *, const struct TimeValue *, unsigned __int8, unsigned int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x1800098a0`
- `0x180009aa0`
- `0x18000e970`
- `0x18000e9c8`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate::Set(
        PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate *this,
        void *a2,
        struct _TASK_TRIGGER *a3,
        struct _TASK_RUNTIME_DATA *a4,
        const struct TimeValue *a5,
        const struct TimeValue *a6,
        unsigned __int8 a7,
        unsigned int a8)
{
  PRIVATE_NAMESPACE_Triggers_H::TriggerAggregate *v9; // rbx
  unsigned int *v10; // r14
  unsigned int v11; // r15d
  __int64 v13; // r8
  struct _TASK_TRIGGER *v14; // rdi
  unsigned int v15; // esi
  char v16; // al
  struct Trigger *v17; // r8
  __int64 v18; // rax

  v9 = this;
  if ( !a3 || !a2 )
    return 2147500035LL;
  v10 = *(unsigned int **)&a3->wBeginDay;
  if ( v10 )
  {
    if ( (int)*v10 >= 2 )
    {
      return (unsigned int)-2100362983;
    }
    else
    {
      v11 = 0;
      *((_QWORD *)this + 22) = a2;
      v13 = *v10;
      *((_DWORD *)this + 48) = v13;
      *((_BYTE *)this + 220) = a7;
      if ( (byte_180030D04 & 0x20) != 0 )
        McTemplateU0qqq_EventWriteTransfer((__int64)this, (const EVENT_DESCRIPTOR *)"c", v13, a7, v10[1]);
      if ( v10[1] )
      {
        v14 = (struct _TASK_TRIGGER *)*((_QWORD *)v10 + 1);
        if ( v14 )
        {
          v15 = 0;
          while ( v15 < v10[1] )
          {
            v16 = *((_BYTE *)v9 + 220);
            if ( v16 == 4 && *(_DWORD *)&v14->cbTriggerSize == 2 )
            {
              if ( (byte_180030D04 & 0x40) != 0 )
                McTemplateU0q_EventWriteTransfer(
                  (__int64)this,
                  (const EVENT_DESCRIPTOR *)TooManyAggregateLevelsError,
                  4);
              return (unsigned int)-2100362996;
            }
            if ( *(_DWORD *)&v14->cbTriggerSize == 5 )
            {
              if ( (byte_180030D04 & 0x40) != 0 )
                McTemplateU0q_EventWriteTransfer(
                  (__int64)this,
                  (const EVENT_DESCRIPTOR *)TriggerUnsupportedInAggregate,
                  5);
              return (unsigned int)-2147467259;
            }
            v17 = Trigger::Alloc(*((_QWORD *)v9 + 22), v14, a5, a6, a4, v16 + 1, a8);
            if ( !v17 )
              return (unsigned int)-2147024882;
            ++*((_DWORD *)v9 + 54);
            v18 = *((_QWORD *)v9 + 25);
            this = (struct Trigger *)((char *)v17 + 8);
            *((_QWORD *)v17 + 1) = v18;
            ++v15;
            *((_QWORD *)v17 + 2) = (char *)v9 + 200;
            v14 = (struct _TASK_TRIGGER *)((char *)v14 + 16);
            *(_QWORD *)(v18 + 8) = (char *)v17 + 8;
            *((_QWORD *)v9 + 25) = (char *)v17 + 8;
          }
        }
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v11;
}

```

## disassembly

```asm
0x1800098a0  push    rbx
0x1800098a2  push    rbp
0x1800098a3  sub     rsp, 58h
0x1800098a7  mov     rbp, r9
0x1800098aa  mov     rbx, rcx
0x1800098ad  test    r8, r8
0x1800098b0  jz      loc_180009A2A
0x1800098b6  test    rdx, rdx
0x1800098b9  jz      loc_180009A2A
0x1800098bf  mov     [rsp+68h+var_20], r14
0x1800098c4  mov     r14, [r8+8]
0x1800098c8  mov     [rsp+68h+var_28], r15
0x1800098cd  test    r14, r14
0x1800098d0  jnz     short loc_1800098EC
0x1800098d2  mov     r15d, 80070057h
0x1800098d8  mov     r14, [rsp+68h+var_20]
0x1800098dd  mov     eax, r15d
0x1800098e0  mov     r15, [rsp+68h+var_28]
0x1800098e5  add     rsp, 58h
0x1800098e9  pop     rbp
0x1800098ea  pop     rbx
0x1800098eb  retn
0x1800098ec  cmp     dword ptr [r14], 2
0x1800098f0  jge     loc_180009A34
0x1800098f6  movzx   eax, [rsp+68h+arg_30]
0x1800098fe  xor     r15d, r15d
0x180009901  mov     [rcx+0B0h], rdx
0x180009908  mov     r8d, [r14]
0x18000990b  mov     [rcx+0C0h], r8d
0x180009912  mov     [rcx+0DCh], al
0x180009918  test    cs:byte_180030D04, 20h
0x18000991f  jnz     loc_180009A0E
0x180009925  cmp     [r14+4], r15d
0x180009929  jz      short loc_1800098D8
0x18000992b  mov     [rsp+68h+arg_8], rdi
0x180009930  mov     rdi, [r14+8]
0x180009934  test    rdi, rdi
0x180009937  jz      loc_180009A04
0x18000993d  mov     [rsp+68h+arg_0], rsi
0x180009942  xor     esi, esi
0x180009944  mov     [rsp+68h+arg_10], r12
0x18000994c  mov     r12d, [rsp+68h+arg_38]
0x180009954  mov     [rsp+68h+var_18], r13
0x180009959  mov     r13, [rsp+68h+arg_28]
0x180009961  cmp     esi, [r14+4]
0x180009965  jnb     loc_1800099F2
0x18000996b  movzx   eax, byte ptr [rbx+0DCh]
0x180009972  cmp     al, 4
0x180009974  jz      loc_180009A3F
0x18000997a  cmp     dword ptr [rdi], 5
0x18000997d  jz      short loc_1800099DF
0x18000997f  mov     r8, [rsp+68h+arg_20]; struct TimeValue *
0x180009987  inc     al
0x180009989  mov     rcx, [rbx+0B0h]; void *
0x180009990  mov     r9, r13; struct TimeValue *
0x180009993  mov     [rsp+68h+var_38], r12d; unsigned int
0x180009998  mov     rdx, rdi; struct _TASK_TRIGGER *
0x18000999b  mov     [rsp+68h+var_40], al; char
0x18000999f  mov     [rsp+68h+var_48], rbp; struct _TASK_RUNTIME_DATA *
0x1800099a4  call    ?Alloc@Trigger@@SAPEAV1@PEAXPEAU_TASK_TRIGGER@@AEBVTimeValue@@2PEAU_TASK_RUNTIME_DATA@@EK@Z; Trigger::Alloc(void *,_TASK_TRIGGER *,TimeValue const &,TimeValue const &,_TASK_RUNTIME_DATA *,uchar,ulong)
0x1800099a9  mov     r8, rax
0x1800099ac  test    rax, rax
0x1800099af  jz      loc_180009A6B
0x1800099b5  inc     dword ptr [rbx+0D8h]
0x1800099bb  lea     rdx, [rbx+0C8h]
0x1800099c2  mov     rax, [rdx]
0x1800099c5  lea     rcx, [r8+8]
0x1800099c9  mov     [rcx], rax
0x1800099cc  inc     esi
0x1800099ce  mov     [r8+10h], rdx
0x1800099d2  add     rdi, 10h
0x1800099d6  mov     [rax+8], rcx
0x1800099da  mov     [rdx], rcx
0x1800099dd  jmp     short loc_180009961
0x1800099df  test    cs:byte_180030D04, 40h
0x1800099e6  jnz     loc_180009A76
0x1800099ec  mov     r15d, 80004005h
0x1800099f2  mov     r12, [rsp+68h+arg_10]
0x1800099fa  mov     rsi, [rsp+68h+arg_0]
0x1800099ff  mov     r13, [rsp+68h+var_18]
0x180009a04  mov     rdi, [rsp+68h+arg_8]
0x180009a09  jmp     loc_1800098D8
0x180009a0e  mov     r9d, eax
0x180009a11  lea     rdx, AggregateTriggerSet; "c"
0x180009a18  mov     eax, [r14+4]
0x180009a1c  mov     dword ptr [rsp+68h+var_48], eax
0x180009a20  call    McTemplateU0qqq_EventWriteTransfer
0x180009a25  jmp     loc_180009925
0x180009a2a  mov     eax, 80004003h
0x180009a2f  jmp     loc_1800098E5
0x180009a34  mov     r15d, 82CF0119h
0x180009a3a  jmp     loc_1800098D8
0x180009a3f  cmp     dword ptr [rdi], 2
0x180009a42  jnz     loc_18000997A
0x180009a48  test    cs:byte_180030D04, 40h
0x180009a4f  jz      short loc_180009A63
0x180009a51  mov     r8d, 4
0x180009a57  lea     rdx, TooManyAggregateLevelsError
0x180009a5e  call    McTemplateU0q_EventWriteTransfer
0x180009a63  mov     r15d, 82CF010Ch
0x180009a69  jmp     short loc_1800099F2
0x180009a6b  mov     r15d, 8007000Eh
0x180009a71  jmp     loc_1800099F2
0x180009a76  mov     r8d, 5
0x180009a7c  lea     rdx, TriggerUnsupportedInAggregate
0x180009a83  call    McTemplateU0q_EventWriteTransfer
0x180009a88  jmp     loc_1800099EC
```
