# Concurrency::task_unsigned_char_::_TaskInitWithFunctor_void__lambda_41663189713a77324ef99cfbd1e71423___

- ea: `0x18001cf8c`
- end: `0x18001d02b`
- name: `Concurrency::task_unsigned_char_::_TaskInitWithFunctor_void__lambda_41663189713a77324ef99cfbd1e71423___`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001c39c`

## callees

- `0x180003b84`
- `0x18001cf8c`
- `0x18001d990`
- `0x18002411c`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18001cfc2`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18001cfc2`

## pseudocode

```c
void __fastcall Concurrency::task_unsigned_char_::_TaskInitWithFunctor_void__lambda_41663189713a77324ef99cfbd1e71423___(
        Concurrency::details::_Task_impl_base **a1,
        _QWORD *a2)
{
  __int64 i; // r8
  Concurrency::details::_Task_impl_base *v5; // rdi
  _QWORD *v6; // r9
  __int64 v7; // r9

  for ( i = 0; i != 2; ++i )
    *((_BYTE *)*a1 + i + 12) = 0;
  Concurrency::details::_TaskEventLogger::_LogScheduleTask(
    (Concurrency::details::_Task_impl_base *)((char *)*a1 + 352),
    0);
  v5 = *a1;
  v6 = operator new(0x20u);
  if ( v6 )
  {
    *v6 = &off_180029080;
    std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
      v6 + 1,
      a1);
    *(_QWORD *)v7 = &off_180029070;
    *(_QWORD *)(v7 + 24) = *a2;
  }
  else
  {
    v7 = 0;
  }
  Concurrency::details::_Task_impl_base::_ScheduleTask(v5, (__int64 (__fastcall ***)(_QWORD, __int64))v7, 0);
}

```

## disassembly

```asm
0x18001cf8c  mov     [rsp+arg_8], rbx
0x18001cf91  mov     [rsp+arg_10], rsi
0x18001cf96  push    rdi
0x18001cf97  sub     rsp, 20h
0x18001cf9b  mov     rsi, rdx
0x18001cf9e  mov     rbx, rcx
0x18001cfa1  xor     r8d, r8d
0x18001cfa4  mov     rax, [rcx]
0x18001cfa7  mov     byte ptr [rax+r8+0Ch], 0
0x18001cfad  inc     r8
0x18001cfb0  cmp     r8, 2
0x18001cfb4  jnz     short loc_18001CFA4
0x18001cfb6  mov     rcx, [rcx]
0x18001cfb9  xor     edx, edx
0x18001cfbb  add     rcx, 160h
0x18001cfc2  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x18001cfc8  mov     rdi, [rbx]
0x18001cfcb  mov     ecx, 20h ; ' '; Size
0x18001cfd0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001cfd5  mov     [rsp+28h+arg_0], rax
0x18001cfda  mov     r9, rax
0x18001cfdd  test    rax, rax
0x18001cfe0  jz      short loc_18001D00B
0x18001cfe2  lea     rax, off_180029080
0x18001cfe9  mov     rdx, rbx
0x18001cfec  lea     rcx, [r9+8]
0x18001cff0  mov     [r9], rax
0x18001cff3  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18001cff8  lea     rcx, off_180029070
0x18001cfff  mov     [r9], rcx
0x18001d002  mov     rax, [rsi]
0x18001d005  mov     [r9+18h], rax
0x18001d009  jmp     short loc_18001D00E
0x18001d00b  xor     r9d, r9d
0x18001d00e  xor     r8d, r8d
0x18001d011  mov     rdx, r9
0x18001d014  mov     rcx, rdi
0x18001d017  mov     rbx, [rsp+28h+arg_8]
0x18001d01c  mov     rsi, [rsp+28h+arg_10]
0x18001d021  add     rsp, 20h
0x18001d025  pop     rdi
0x18001d026  jmp     ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
```
