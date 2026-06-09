# s_TaskSchedulerFindFirstSchedule

- ea: `0x1800175f0`
- end: `0x18001766e`
- name: `s_TaskSchedulerFindFirstSchedule`
- size: `126`
- prototype: `__int64 __fastcall(CScheduleMgr *, void **, struct _GUID *, struct _TASK_SCHEDULE **, struct _TASK_STATISTICS **)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18000ea40`
- `0x1800175f0`
- `0x180018dac`
- `0x180020c30`

## pseudocode

```c
__int64 __fastcall s_TaskSchedulerFindFirstSchedule(
        CScheduleMgr *a1,
        void **a2,
        struct _GUID *a3,
        struct _TASK_SCHEDULE **a4,
        struct _TASK_STATISTICS **a5)
{
  _BYTE v9[16]; // [rsp+30h] [rbp-38h] BYREF

  if ( (byte_180030D03 & 0x10) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, APIFindFirstSchedule, a3, 1, v9);
  return CScheduleMgr::FindFirstSchedule(a1, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x1800175f0  mov     [rsp+arg_0], rbx
0x1800175f5  push    rbp
0x1800175f6  push    rsi
0x1800175f7  push    rdi
0x1800175f8  sub     rsp, 50h
0x1800175fc  mov     rax, cs:__security_cookie
0x180017603  xor     rax, rsp
0x180017606  mov     [rsp+68h+var_28], rax
0x18001760b  test    cs:byte_180030D03, 10h
0x180017612  mov     rsi, r9
0x180017615  mov     rbp, [rsp+68h+arg_20]
0x18001761d  mov     rdi, r8
0x180017620  mov     rbx, rdx
0x180017623  jz      short loc_180017641
0x180017625  lea     rax, [rsp+68h+var_38]
0x18001762a  mov     r9d, 1
0x180017630  lea     rdx, APIFindFirstSchedule
0x180017637  mov     [rsp+68h+var_48], rax
0x18001763c  call    McGenEventWrite_EventWriteTransfer
0x180017641  mov     r9, rsi; struct _TASK_SCHEDULE **
0x180017644  mov     [rsp+68h+var_48], rbp; struct _TASK_STATISTICS **
0x180017649  mov     r8, rdi; struct _GUID *
0x18001764c  mov     rdx, rbx; void **
0x18001764f  call    ?FindFirstSchedule@CScheduleMgr@@QEAAJPEAPEAXPEAU_GUID@@PEAPEAU_TASK_SCHEDULE@@PEAPEAU_TASK_STATISTICS@@@Z; CScheduleMgr::FindFirstSchedule(void * *,_GUID *,_TASK_SCHEDULE * *,_TASK_STATISTICS * *)
0x180017654  mov     rcx, [rsp+68h+var_28]
0x180017659  xor     rcx, rsp; StackCookie
0x18001765c  call    __security_check_cookie
0x180017661  mov     rbx, [rsp+68h+arg_0]
0x180017666  add     rsp, 50h
0x18001766a  pop     rdi
0x18001766b  pop     rsi
0x18001766c  pop     rbp
0x18001766d  retn
```
