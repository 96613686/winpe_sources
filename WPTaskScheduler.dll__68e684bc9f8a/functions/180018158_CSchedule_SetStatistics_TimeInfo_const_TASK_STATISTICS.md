# CSchedule::SetStatistics(TimeInfo const &,_TASK_STATISTICS *)

- ea: `0x180018158`
- end: `0x180018201`
- name: `?SetStatistics@CSchedule@@QEAAJAEBVTimeInfo@@PEAU_TASK_STATISTICS@@@Z`
- size: `169`
- prototype: `__int64 __fastcall(CSchedule *__hidden this, const struct TimeInfo *, struct _TASK_STATISTICS *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x180019610`

## callees

- `0x18000c540`
- `0x18000f760`
- `0x180018158`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CSchedule::SetStatistics(CSchedule *this, const struct TimeInfo *a2, struct _TASK_STATISTICS *a3)
{
  __int64 result; // rax

  if ( !a3 )
    return 2147500035LL;
  if ( !*((_QWORD *)this + 27) )
    return 2194604296LL;
  if ( !*((_QWORD *)this + 25) )
    return 2194604325LL;
  TimeValue::Set((CSchedule *)((char *)this + 152), (const struct _SYSTEMTIME *)((char *)a3 + 24));
  *((_DWORD *)this + 36) = *(_DWORD *)a3;
  CSchedule::UpdateState(this, a2);
  result = (*(__int64 (__fastcall **)(_QWORD, struct _TASK_STATISTICS *))(**((_QWORD **)this + 25) + 88LL))(
             *((_QWORD *)this + 25),
             a3);
  if ( (int)result >= 0 )
    return (*(__int64 (__fastcall **)(_QWORD, struct _TASK_STATISTICS *))(**((_QWORD **)this + 27) + 48LL))(
             *((_QWORD *)this + 27),
             a3);
  return result;
}

```

## disassembly

```asm
0x180018158  mov     [rsp+arg_0], rbx
0x18001815d  mov     [rsp+arg_8], rsi
0x180018162  push    rdi
0x180018163  sub     rsp, 20h
0x180018167  mov     rdi, r8
0x18001816a  mov     rsi, rdx
0x18001816d  mov     rbx, rcx
0x180018170  test    r8, r8
0x180018173  jnz     short loc_18001817C
0x180018175  mov     eax, 80004003h
0x18001817a  jmp     short loc_1800181F1
0x18001817c  cmp     qword ptr [rcx+0D8h], 0
0x180018184  jnz     short loc_18001818D
0x180018186  mov     eax, 82CF0108h
0x18001818b  jmp     short loc_1800181F1
0x18001818d  cmp     qword ptr [rcx+0C8h], 0
0x180018195  jnz     short loc_18001819E
0x180018197  mov     eax, 82CF0125h
0x18001819c  jmp     short loc_1800181F1
0x18001819e  lea     rdx, [r8+18h]; struct _SYSTEMTIME *
0x1800181a2  add     rcx, 98h; this
0x1800181a9  call    ?Set@TimeValue@@QEAAHAEBU_SYSTEMTIME@@@Z; TimeValue::Set(_SYSTEMTIME const &)
0x1800181ae  mov     eax, [rdi]
0x1800181b0  mov     rdx, rsi; struct TimeInfo *
0x1800181b3  mov     rcx, rbx; this
0x1800181b6  mov     [rbx+90h], eax
0x1800181bc  call    ?UpdateState@CSchedule@@AEAAXAEBVTimeInfo@@@Z; CSchedule::UpdateState(TimeInfo const &)
0x1800181c1  mov     rcx, [rbx+0C8h]
0x1800181c8  mov     rdx, rdi
0x1800181cb  mov     rax, [rcx]
0x1800181ce  mov     rax, [rax+58h]
0x1800181d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181d7  test    eax, eax
0x1800181d9  js      short loc_1800181F1
0x1800181db  mov     rcx, [rbx+0D8h]
0x1800181e2  mov     rdx, rdi
0x1800181e5  mov     rax, [rcx]
0x1800181e8  mov     rax, [rax+30h]
0x1800181ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800181f1  mov     rbx, [rsp+28h+arg_0]
0x1800181f6  mov     rsi, [rsp+28h+arg_8]
0x1800181fb  add     rsp, 20h
0x1800181ff  pop     rdi
0x180018200  retn
```
