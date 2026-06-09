# Concurrency::task_unsigned_char_::_TaskInitWithFunctor_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0___

- ea: `0x18001d0dc`
- end: `0x18001d17b`
- name: `Concurrency::task_unsigned_char_::_TaskInitWithFunctor_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0___`
- size: `159`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001c59c`

## callees

- `0x180003b84`
- `0x18001d0dc`
- `0x18001d990`
- `0x18002411c`

## import_xrefs

- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18001d112`
- `msvcp_win!?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z` at `0x18001d112`

## pseudocode

```c
void __fastcall Concurrency::task_unsigned_char_::_TaskInitWithFunctor_void__lambda_c963b5d210f208ea3e93fc35ff6adcb0___(
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
    *v6 = &off_180029060;
    std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
      v6 + 1,
      a1);
    *(_QWORD *)v7 = &off_180029050;
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
0x18001d0dc  mov     [rsp+arg_8], rbx
0x18001d0e1  mov     [rsp+arg_10], rsi
0x18001d0e6  push    rdi
0x18001d0e7  sub     rsp, 20h
0x18001d0eb  mov     rsi, rdx
0x18001d0ee  mov     rbx, rcx
0x18001d0f1  xor     r8d, r8d
0x18001d0f4  mov     rax, [rcx]
0x18001d0f7  mov     byte ptr [rax+r8+0Ch], 0
0x18001d0fd  inc     r8
0x18001d100  cmp     r8, 2
0x18001d104  jnz     short loc_18001D0F4
0x18001d106  mov     rcx, [rcx]
0x18001d109  xor     edx, edx
0x18001d10b  add     rcx, 160h
0x18001d112  call    cs:__imp_?_LogScheduleTask@_TaskEventLogger@details@Concurrency@@QEAAX_N@Z; Concurrency::details::_TaskEventLogger::_LogScheduleTask(bool)
0x18001d118  mov     rdi, [rbx]
0x18001d11b  mov     ecx, 20h ; ' '; Size
0x18001d120  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001d125  mov     [rsp+28h+arg_0], rax
0x18001d12a  mov     r9, rax
0x18001d12d  test    rax, rax
0x18001d130  jz      short loc_18001D15B
0x18001d132  lea     rax, off_180029060
0x18001d139  mov     rdx, rbx
0x18001d13c  lea     rcx, [r9+8]
0x18001d140  mov     [r9], rax
0x18001d143  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x18001d148  lea     rcx, off_180029050
0x18001d14f  mov     [r9], rcx
0x18001d152  mov     rax, [rsi]
0x18001d155  mov     [r9+18h], rax
0x18001d159  jmp     short loc_18001D15E
0x18001d15b  xor     r9d, r9d
0x18001d15e  xor     r8d, r8d
0x18001d161  mov     rdx, r9
0x18001d164  mov     rcx, rdi
0x18001d167  mov     rbx, [rsp+28h+arg_8]
0x18001d16c  mov     rsi, [rsp+28h+arg_10]
0x18001d171  add     rsp, 20h
0x18001d175  pop     rdi
0x18001d176  jmp     ?_ScheduleTask@_Task_impl_base@details@Concurrency@@QEAAXPEAU_TaskProcHandle@23@W4_TaskInliningMode@23@@Z; Concurrency::details::_Task_impl_base::_ScheduleTask(Concurrency::details::_TaskProcHandle *,Concurrency::details::_TaskInliningMode)
```
