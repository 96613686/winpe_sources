# TaskSchedulerFreeScheduleStatistics

- ea: `0x180020a48`
- end: `0x180020a5c`
- name: `TaskSchedulerFreeScheduleStatistics`
- size: `20`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180017e48`
- `0x18001910c`
- `0x18001efc8`
- `0x18001f3ec`
- `0x18001f87c`

## callees

- `0x180020a48`

## import_xrefs

- `msvcrt!free` at `0x180020a51`
- `msvcrt!free` at `0x180020a51`

## pseudocode

```c
void __fastcall TaskSchedulerFreeScheduleStatistics(void *a1)
{
  if ( a1 )
    free(a1);
}

```

## disassembly

```asm
0x180020a48  sub     rsp, 28h
0x180020a4c  test    rcx, rcx
0x180020a4f  jz      short loc_180020A57
0x180020a51  call    cs:__imp_free
0x180020a57  add     rsp, 28h
0x180020a5b  retn
```
