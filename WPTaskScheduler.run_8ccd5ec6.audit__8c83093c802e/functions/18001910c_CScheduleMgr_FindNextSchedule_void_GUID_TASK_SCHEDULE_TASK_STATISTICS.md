# CScheduleMgr::FindNextSchedule(void *,_GUID *,_TASK_SCHEDULE * *,_TASK_STATISTICS * *)

- ea: `0x18001910c`
- end: `0x1800192e3`
- name: `?FindNextSchedule@CScheduleMgr@@QEAAJPEAXPEAU_GUID@@PEAPEAU_TASK_SCHEDULE@@PEAPEAU_TASK_STATISTICS@@@Z`
- size: `471`
- prototype: `__int64 __fastcall(CScheduleMgr *__hidden this, void *, struct _GUID *, struct _TASK_SCHEDULE **, struct _TASK_STATISTICS **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017680`

## callees

- `0x180002f00`
- `0x18000e970`
- `0x18000ea40`
- `0x18001910c`
- `0x1800192ec`
- `0x18001ffc0`
- `0x180020a2c`
- `0x180020a48`
- `0x180020c30`

## pseudocode

```c
__int64 __fastcall CScheduleMgr::FindNextSchedule(
        CScheduleMgr *this,
        unsigned int *a2,
        struct _GUID *a3,
        struct _TASK_SCHEDULE **a4,
        struct _TASK_STATISTICS **a5)
{
  __int64 v9; // r8
  unsigned __int16 *v10; // rcx
  int v11; // ebx
  const struct _GUID *v12; // r15
  struct _TASK_SCHEDULE *Ptr; // rcx
  struct _TASK_STATISTICS *v14; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v15; // [rsp+38h] [rbp-40h] BYREF

  if ( !a2 )
    return 2147942406LL;
  if ( a3 )
  {
    if ( *(_QWORD *)a2 )
    {
      v9 = a2[3];
      if ( (unsigned int)v9 < a2[2] )
      {
        if ( (byte_180030D05 & 8) != 0 )
          McTemplateU0q_EventWriteTransfer((__int64)this, (const EVENT_DESCRIPTOR *)FindIndexIs, v9);
        v15.Ptr = 0;
        v14 = 0;
        if ( TsiCheckCallerCapabilities((const unsigned __int16 *)this) >= 0
          || (v11 = 0, TsiCheckCallerCapabilities(v10) >= 0) )
        {
          v11 = 1;
        }
        while ( 1 )
        {
          v12 = (const struct _GUID *)(*(_QWORD *)a2 + 16LL * a2[3]++);
          if ( (v11 || (int)CScheduleMgr::IsCallerScheduleOwner((CScheduleMgr *)v10, v12) >= 0)
            && (int)CScheduleMgr::GetSchedule(
                      (CScheduleMgr *)&g_ScheduleMgr,
                      v12,
                      (struct _TASK_SCHEDULE **)&v15,
                      &v14,
                      0) >= 0 )
          {
            break;
          }
          if ( a2[3] >= a2[2] )
            return 2194604302LL;
        }
        Ptr = (struct _TASK_SCHEDULE *)v15.Ptr;
        if ( v15.Ptr )
        {
          *a3 = *(struct _GUID *)*(_QWORD *)v15.Ptr;
          if ( a4 )
            *a4 = Ptr;
          else
            TaskSchedulerFreeSchedule(Ptr);
        }
        if ( a5 )
          *a5 = v14;
        else
          TaskSchedulerFreeScheduleStatistics(v14);
        return 0;
      }
      else
      {
        if ( (byte_180030D05 & 0x20) != 0 )
          McGenEventWrite_EventWriteTransfer(
            (__int64)this,
            (const EVENT_DESCRIPTOR *)FindOperationIsCompleted,
            v9,
            1u,
            &v15);
        return 2194604302LL;
      }
    }
    else
    {
      if ( (byte_180030D05 & 0x20) != 0 )
        McGenEventWrite_EventWriteTransfer(
          (__int64)this,
          (const EVENT_DESCRIPTOR *)FindOperationNotStarted,
          (__int64)a3,
          1u,
          &v15);
      return 2194604303LL;
    }
  }
  else
  {
    if ( (byte_180030D04 & 1) != 0 )
      McGenEventWrite_EventWriteTransfer((__int64)this, (const EVENT_DESCRIPTOR *)ErrorNullPointer, 0, 1u, &v15);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18001910c  mov     [rsp+arg_0], rbx
0x180019111  push    rbp
0x180019112  push    rsi
0x180019113  push    rdi
0x180019114  push    r14
0x180019116  push    r15
0x180019118  sub     rsp, 50h
0x18001911c  mov     rax, cs:__security_cookie
0x180019123  xor     rax, rsp
0x180019126  mov     [rsp+78h+var_30], rax
0x18001912b  mov     rsi, [rsp+78h+arg_20]
0x180019133  mov     r14, r9
0x180019136  mov     rbp, r8
0x180019139  mov     rdi, rdx
0x18001913c  test    rdx, rdx
0x18001913f  jnz     short loc_18001914B
0x180019141  mov     eax, 80070006h
0x180019146  jmp     loc_1800192C2
0x18001914b  test    rbp, rbp
0x18001914e  jnz     short loc_18001917E
0x180019150  lea     ebx, [rbp+1]
0x180019153  test    cs:byte_180030D04, bl
0x180019159  jz      short loc_180019174
0x18001915b  lea     rax, [rsp+78h+var_40]
0x180019160  mov     r9d, ebx
0x180019163  lea     rdx, ErrorNullPointer
0x18001916a  mov     [rsp+78h+var_58], rax
0x18001916f  call    McGenEventWrite_EventWriteTransfer
0x180019174  mov     eax, 80004003h
0x180019179  jmp     loc_1800192C2
0x18001917e  cmp     qword ptr [rdx], 0
0x180019182  jnz     short loc_1800191B3
0x180019184  test    cs:byte_180030D05, 20h
0x18001918b  jz      short loc_1800191A9
0x18001918d  lea     rax, [rsp+78h+var_40]
0x180019192  mov     r9d, 1
0x180019198  lea     rdx, FindOperationNotStarted
0x18001919f  mov     [rsp+78h+var_58], rax
0x1800191a4  call    McGenEventWrite_EventWriteTransfer
0x1800191a9  mov     eax, 82CF010Fh
0x1800191ae  jmp     loc_1800192C2
0x1800191b3  mov     r8d, [rdx+0Ch]
0x1800191b7  cmp     r8d, [rdx+8]
0x1800191bb  jb      short loc_1800191EB
0x1800191bd  test    cs:byte_180030D05, 20h
0x1800191c4  jz      loc_18001927C
0x1800191ca  lea     rax, [rsp+78h+var_40]
0x1800191cf  mov     r9d, 1
0x1800191d5  lea     rdx, FindOperationIsCompleted
0x1800191dc  mov     [rsp+78h+var_58], rax
0x1800191e1  call    McGenEventWrite_EventWriteTransfer
0x1800191e6  jmp     loc_18001927C
0x1800191eb  test    cs:byte_180030D05, 8
0x1800191f2  jz      short loc_180019200
0x1800191f4  lea     rdx, FindIndexIs
0x1800191fb  call    McTemplateU0q_EventWriteTransfer
0x180019200  mov     qword ptr [rsp+78h+var_40], 0
0x180019209  mov     [rsp+78h+var_48], 0
0x180019212  call    ?TsiCheckCallerCapabilities@@YAJPEBG@Z; TsiCheckCallerCapabilities(ushort const *)
0x180019217  test    eax, eax
0x180019219  jns     short loc_180019226
0x18001921b  xor     ebx, ebx
0x18001921d  call    ?TsiCheckCallerCapabilities@@YAJPEBG@Z; TsiCheckCallerCapabilities(ushort const *)
0x180019222  test    eax, eax
0x180019224  js      short loc_18001922B
0x180019226  mov     ebx, 1
0x18001922b  mov     edx, [rdi+0Ch]
0x18001922e  mov     r15d, edx
0x180019231  shl     r15, 4
0x180019235  add     r15, [rdi]
0x180019238  lea     eax, [rdx+1]
0x18001923b  mov     [rdi+0Ch], eax
0x18001923e  test    ebx, ebx
0x180019240  jnz     short loc_18001924E
0x180019242  mov     rdx, r15; struct _GUID *
0x180019245  call    ?IsCallerScheduleOwner@CScheduleMgr@@QEAA?BJPEBU_GUID@@@Z; CScheduleMgr::IsCallerScheduleOwner(_GUID const *)
0x18001924a  test    eax, eax
0x18001924c  js      short loc_180019274
0x18001924e  lea     r9, [rsp+78h+var_48]; struct _TASK_STATISTICS **
0x180019253  mov     [rsp+78h+var_58], 0; struct _TASK_RUNTIME_DATA **
0x18001925c  lea     r8, [rsp+78h+var_40]; struct _TASK_SCHEDULE **
0x180019261  mov     rdx, r15; struct _GUID *
0x180019264  lea     rcx, ?g_ScheduleMgr@@3VCScheduleMgr@@A; this
0x18001926b  call    ?GetSchedule@CScheduleMgr@@QEAAJPEBU_GUID@@PEAPEAU_TASK_SCHEDULE@@PEAPEAU_TASK_STATISTICS@@PEAPEAU_TASK_RUNTIME_DATA@@@Z; CScheduleMgr::GetSchedule(_GUID const *,_TASK_SCHEDULE * *,_TASK_STATISTICS * *,_TASK_RUNTIME_DATA * *)
0x180019270  test    eax, eax
0x180019272  jns     short loc_180019283
0x180019274  mov     eax, [rdi+8]
0x180019277  cmp     [rdi+0Ch], eax
0x18001927a  jb      short loc_18001922B
0x18001927c  mov     eax, 82CF010Eh
0x180019281  jmp     short loc_1800192C2
0x180019283  mov     rcx, qword ptr [rsp+78h+var_40]
0x180019288  test    rcx, rcx
0x18001928b  jz      short loc_1800192A7
0x18001928d  mov     rax, [rcx]
0x180019290  movups  xmm0, xmmword ptr [rax]
0x180019293  movdqu  xmmword ptr [rbp+0], xmm0
0x180019298  test    r14, r14
0x18001929b  jz      short loc_1800192A2
0x18001929d  mov     [r14], rcx
0x1800192a0  jmp     short loc_1800192A7
0x1800192a2  call    TaskSchedulerFreeSchedule
0x1800192a7  test    rsi, rsi
0x1800192aa  jz      short loc_1800192B6
0x1800192ac  mov     rax, [rsp+78h+var_48]
0x1800192b1  mov     [rsi], rax
0x1800192b4  jmp     short loc_1800192C0
0x1800192b6  mov     rcx, [rsp+78h+var_48]
0x1800192bb  call    TaskSchedulerFreeScheduleStatistics
0x1800192c0  xor     eax, eax
0x1800192c2  mov     rcx, [rsp+78h+var_30]
0x1800192c7  xor     rcx, rsp; StackCookie
0x1800192ca  call    __security_check_cookie
0x1800192cf  mov     rbx, [rsp+78h+arg_0]
0x1800192d7  add     rsp, 50h
0x1800192db  pop     r15
0x1800192dd  pop     r14
0x1800192df  pop     rdi
0x1800192e0  pop     rsi
0x1800192e1  pop     rbp
0x1800192e2  retn
```
