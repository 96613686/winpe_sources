# s_TaskSchedulerEnableSchedule

- ea: `0x180017530`
- end: `0x18001757c`
- name: `s_TaskSchedulerEnableSchedule`
- size: `76`
- prototype: `int __fastcall(__int64, struct _GUID *, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180001dd0`
- `0x180017370`
- `0x180017530`
- `0x180018bc4`

## pseudocode

```c
int __fastcall s_TaskSchedulerEnableSchedule(__int64 a1, struct _GUID *a2, int a3)
{
  int result; // eax
  CScheduleMgr *v6; // rcx

  if ( (byte_180030D03 & 0x10) != 0 )
    McTemplateU0j_EventWriteTransfer(a1, APIEnableSchedule, a2);
  result = CallerHasAccess(a2, 0);
  if ( result >= 0 )
    return CScheduleMgr::EnableSchedule(v6, a2, a3);
  return result;
}

```

## disassembly

```asm
0x180017530  mov     [rsp+arg_0], rbx
0x180017535  push    rdi
0x180017536  sub     rsp, 20h
0x18001753a  test    cs:byte_180030D03, 10h
0x180017541  mov     edi, r8d
0x180017544  mov     rbx, rdx
0x180017547  jz      short loc_180017558
0x180017549  mov     r8, rdx
0x18001754c  lea     rdx, APIEnableSchedule
0x180017553  call    McTemplateU0j_EventWriteTransfer
0x180017558  xor     edx, edx
0x18001755a  mov     rcx, rbx; struct _GUID *
0x18001755d  call    CallerHasAccess
0x180017562  test    eax, eax
0x180017564  js      short loc_180017571
0x180017566  mov     r8d, edi; int
0x180017569  mov     rdx, rbx; struct _GUID *
0x18001756c  call    ?EnableSchedule@CScheduleMgr@@QEAAJPEBU_GUID@@H@Z; CScheduleMgr::EnableSchedule(_GUID const *,int)
0x180017571  mov     rbx, [rsp+28h+arg_0]
0x180017576  add     rsp, 20h
0x18001757a  pop     rdi
0x18001757b  retn
```
