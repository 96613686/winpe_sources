# TaskSchedulerFreeSchedule

- ea: `0x180020a2c`
- end: `0x180020a3f`
- name: `TaskSchedulerFreeSchedule`
- size: `19`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180017e48`
- `0x18001910c`
- `0x18001efc8`
- `0x18001f3ec`
- `0x18001f7e0`

## callees

- `0x180020900`
- `0x180020a2c`

## pseudocode

```c
void __fastcall TaskSchedulerFreeSchedule(void **a1, void (*a2)(void *))
{
  if ( a1 )
    TaskSchedulerFreeScheduleWithFunc(a1, a2);
}

```

## disassembly

```asm
0x180020a2c  sub     rsp, 28h
0x180020a30  test    rcx, rcx
0x180020a33  jz      short loc_180020A3A
0x180020a35  call    ?TaskSchedulerFreeScheduleWithFunc@@YAXPEAU_TASK_SCHEDULE@@P6AXPEAX@Z@Z; TaskSchedulerFreeScheduleWithFunc(_TASK_SCHEDULE *,void (*)(void *))
0x180020a3a  add     rsp, 28h
0x180020a3e  retn
```
