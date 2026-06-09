# Concurrency::task_unsigned_char_::_TaskInitWithFunctor_void__lambda_74fff73db5622b7bcf36501e7db7f309___

- ea: `0x18001d034`
- end: `0x18001d0d3`
- name: `Concurrency::task_unsigned_char_::_TaskInitWithFunctor_void__lambda_74fff73db5622b7bcf36501e7db7f309___`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001c49c`

## callees

- `0x180003b84`
- `0x18001d034`
- `0x18001d990`
- `0x18002411c`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18001d06a`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18001d06a`

## pseudocode

```c
void __fastcall Concurrency::task_unsigned_char_::_TaskInitWithFunctor_void__lambda_74fff73db5622b7bcf36501e7db7f309___(
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
    *v6 = &off_180029040;
    std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
      v6 + 1,
      a1);
    *(_QWORD *)v7 = &off_180029030;
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
0x18001d034  mov     [rsp+arg_8], rbx
0x18001d039  mov     [rsp+arg_10], rsi
0x18001d03e  push    rdi
0x18001d03f  sub     rsp, 20h
0x18001d043  mov     rsi, rdx
0x18001d046  mov     rbx, rcx
0x18001d049  xor     r8d, r8d
0x18001d04c  mov     rax, [rcx]
0x18001d04f  mov     byte ptr [rax+r8+0Ch], 0
0x18001d055  inc     r8
0x18001d058  cmp     r8, 2
0x18001d05c  jnz     short loc_18001D04C
0x18001d05e  mov     rcx, [rcx]
0x18001d061  xor     edx, edx
0x18001d063  add     rcx, 160h
0x18001d06a  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x18001d070  mov     rdi, [rbx]
0x18001d073  mov     ecx, 20h ; ' '; Size
0x18001d078  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d07d  mov     [rsp+28h+arg_0], rax
0x18001d082  mov     r9, rax
0x18001d085  test    rax, rax
0x18001d088  jz      short loc_18001D0B3
0x18001d08a  lea     rax, off_180029040
0x18001d091  mov     rdx, rbx
0x18001d094  lea     rcx, [r9+8]
0x18001d098  mov     [r9], rax
0x18001d09b  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18001d0a0  lea     rcx, off_180029030
0x18001d0a7  mov     [r9], rcx
0x18001d0aa  mov     rax, [rsi]
0x18001d0ad  mov     [r9+18h], rax
0x18001d0b1  jmp     short loc_18001D0B6
0x18001d0b3  xor     r9d, r9d
0x18001d0b6  xor     r8d, r8d
0x18001d0b9  mov     rdx, r9
0x18001d0bc  mov     rcx, rdi
0x18001d0bf  mov     rbx, [rsp+28h+arg_8]
0x18001d0c4  mov     rsi, [rsp+28h+arg_10]
0x18001d0c9  add     rsp, 20h
0x18001d0cd  pop     rdi
0x18001d0ce  jmp     ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
```
