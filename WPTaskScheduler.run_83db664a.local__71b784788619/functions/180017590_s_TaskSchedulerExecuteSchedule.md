# s_TaskSchedulerExecuteSchedule

- ea: `0x180017590`
- end: `0x1800175df`
- name: `s_TaskSchedulerExecuteSchedule`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x180001dd0`
- `0x180017370`
- `0x180017590`
- `0x180018c94`

## pseudocode

```c
RPC_STATUS __fastcall s_TaskSchedulerExecuteSchedule(__int64 a1, struct _GUID *a2, int a3)
{
  RPC_STATUS result; // eax
  CScheduleMgr *v6; // rcx

  if ( (byte_180030D03 & 0x10) != 0 )
    McTemplateU0j_EventWriteTransfer(a1, (const EVENT_DESCRIPTOR *)APIExecuteSchedule, (__int64)a2);
  result = CallerHasAccess(a2, 1);
  if ( result >= 0 )
    return CScheduleMgr::ExecuteSchedule(v6, a2, a3);
  return result;
}

```

## disassembly

```asm
0x180017590  mov     [rsp+arg_0], rbx
0x180017595  push    rdi
0x180017596  sub     rsp, 20h
0x18001759a  test    cs:byte_180030D03, 10h
0x1800175a1  mov     edi, r8d
0x1800175a4  mov     rbx, rdx
0x1800175a7  jz      short loc_1800175B8
0x1800175a9  mov     r8, rdx
0x1800175ac  lea     rdx, APIExecuteSchedule
0x1800175b3  call    McTemplateU0j_EventWriteTransfer
0x1800175b8  mov     edx, 1
0x1800175bd  mov     rcx, rbx; struct _GUID *
0x1800175c0  call    CallerHasAccess
0x1800175c5  test    eax, eax
0x1800175c7  js      short loc_1800175D4
0x1800175c9  mov     r8d, edi; int
0x1800175cc  mov     rdx, rbx; struct _GUID *
0x1800175cf  call    ?ExecuteSchedule@CScheduleMgr@@QEAAJPEBU_GUID@@H@Z; CScheduleMgr::ExecuteSchedule(_GUID const *,int)
0x1800175d4  mov     rbx, [rsp+28h+arg_0]
0x1800175d9  add     rsp, 20h
0x1800175dd  pop     rdi
0x1800175de  retn
```
