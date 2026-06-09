# Concurrency::details::_Schedule_chore(Concurrency::details::_Threadpool_chore *)

- ea: `0x14001deac`
- end: `0x14001dee9`
- name: `?_Schedule_chore@details@Concurrency@@YAHPEAU_Threadpool_chore@12@@Z`
- size: `61`
- prototype: `__int64 __fastcall(Concurrency::details *__hidden this, struct Concurrency::details::_Threadpool_chore *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x14008cf58`

## callees

- `0x14001de74`
- `0x14001deac`

## import_xrefs

- `KERNEL32!CreateThreadpoolWork` at `0x14001dec2`
- `KERNEL32!CreateThreadpoolWork` at `0x14001dec2`
- `KERNEL32!GetLastError` at `0x14001dee2`

## pseudocode

```c
DWORD __fastcall Concurrency::details::_Schedule_chore(
        Concurrency::details *this,
        struct Concurrency::details::_Threadpool_chore *a2)
{
  PTP_WORK ThreadpoolWork; // rax
  const struct Concurrency::details::_Threadpool_chore *v4; // rdx

  ThreadpoolWork = CreateThreadpoolWork(Concurrency::details::_anonymous_namespace_::_Task_scheduler_callback, this, 0);
  *(_QWORD *)this = ThreadpoolWork;
  if ( ThreadpoolWork )
    return Concurrency::details::_Reschedule_chore((LPCWSTR *)this, v4);
  else
    return GetLastError();
}

```

## disassembly

```asm
0x14001deac  push    rbx
0x14001deae  sub     rsp, 20h
0x14001deb2  mov     rbx, rcx
0x14001deb5  mov     rdx, rcx; pv
0x14001deb8  lea     rcx, Concurrency__details___anonymous_namespace____Task_scheduler_callback; pfnwk
0x14001debf  xor     r8d, r8d; pcbe
0x14001dec2  call    cs:__imp_CreateThreadpoolWork
0x14001dec8  mov     [rbx], rax
0x14001decb  test    rax, rax
0x14001dece  jz      short loc_14001DEDD
0x14001ded0  mov     rcx, rbx; this
0x14001ded3  add     rsp, 20h
0x14001ded7  pop     rbx
0x14001ded8  jmp     ?_Reschedule_chore@details@Concurrency@@YAHPEBU_Threadpool_chore@12@@Z
0x14001dedd  add     rsp, 20h
0x14001dee1  pop     rbx
0x14001dee2  jmp     cs:__imp_GetLastError
```
