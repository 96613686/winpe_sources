# Concurrency::get_ambient_scheduler(void)

- ea: `0x14008cbf0`
- end: `0x14008ccc1`
- name: `?get_ambient_scheduler@Concurrency@@YAAEBV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ`
- size: `209`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x1400866cc`
- `0x14008c5ec`

## callees

- `0x14001dd90`
- `0x14003a360`
- `0x14003a3c0`
- `0x14003a430`
- `0x14003a5c0`
- `0x14004f9a8`
- `0x14008cbf0`

## import_xrefs

- `KERNEL32!InitOnceComplete` at `0x14008cc63`
- `KERNEL32!InitOnceComplete` at `0x14008cc63`
- `KERNEL32!InitOnceBeginInitialize` at `0x14008cc1c`
- `KERNEL32!InitOnceBeginInitialize` at `0x14008cc1c`

## pseudocode

```c
__int64 Concurrency::get_ambient_scheduler()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  WINBOOL fPending; // [rsp+30h] [rbp-18h] BYREF

  fPending = 0;
  if ( !__std_init_once_begin_initialize(
          &`Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_Flag,
          0,
          &fPending,
          0) )
    abort();
  if ( fPending )
  {
    if ( __TSS0__1___GetStaticAmbientSchedulerStorage_details_Concurrency__YAPEAV__shared_ptr_Uscheduler_interface_Concurrency___std__XZ_4HA > *(_DWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 4LL) )
    {
      Init_thread_header(&__TSS0__1___GetStaticAmbientSchedulerStorage_details_Concurrency__YAPEAV__shared_ptr_Uscheduler_interface_Concurrency___std__XZ_4HA);
      if ( __TSS0__1___GetStaticAmbientSchedulerStorage_details_Concurrency__YAPEAV__shared_ptr_Uscheduler_interface_Concurrency___std__XZ_4HA == -1 )
      {
        atexit(`Concurrency::details::_GetStaticAmbientSchedulerStorage'::`2'::`dynamic atexit destructor for '_S_scheduler'');
        Init_thread_footer(&__TSS0__1___GetStaticAmbientSchedulerStorage_details_Concurrency__YAPEAV__shared_ptr_Uscheduler_interface_Concurrency___std__XZ_4HA);
      }
    }
    `Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_S_scheduler_address = (__int64)&`Concurrency::details::_GetStaticAmbientSchedulerStorage'::`2'::_S_scheduler;
    if ( !InitOnceComplete(&`Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_Flag, 0, 0) )
      _std_init_once_link_alternate_names_and_abort(v1, v0);
  }
  return `Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_S_scheduler_address;
}

```

## disassembly

```asm
0x14008cbf0  sub     rsp, 48h
0x14008cbf4  mov     rax, cs:__security_cookie
0x14008cbfb  xor     rax, rsp
0x14008cbfe  mov     [rsp+48h+var_10], rax
0x14008cc03  xor     r9d, r9d; lpContext
0x14008cc06  mov     [rsp+48h+fPending], 0
0x14008cc0e  lea     r8, [rsp+48h+fPending]; fPending
0x14008cc13  xor     edx, edx; dwFlags
0x14008cc15  lea     rcx, ?_Flag@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4Uonce_flag@5@A; lpInitOnce
0x14008cc1c  call    cs:__imp___std_init_once_begin_initialize
0x14008cc22  test    eax, eax
0x14008cc24  jz      short loc_14008CC8C
0x14008cc26  cmp     [rsp+48h+fPending], 0
0x14008cc2b  jz      short loc_14008CC6D
0x14008cc2d  mov     rax, gs:58h
0x14008cc36  mov     ecx, 4
0x14008cc3b  mov     rax, [rax]
0x14008cc3e  mov     eax, [rcx+rax]
0x14008cc41  cmp     cs:?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA, eax
0x14008cc47  jg      short loc_14008CC92
0x14008cc49  lea     rax, ?_S_scheduler@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4V45@A; std::shared_ptr<Concurrency::scheduler_interface> `Concurrency::details::_GetStaticAmbientSchedulerStorage(void)'::`2'::_S_scheduler
0x14008cc50  xor     r8d, r8d; lpContext
0x14008cc53  xor     edx, edx; dwFlags
0x14008cc55  mov     cs:?_S_scheduler_address@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4PEAV45@EA, rax; std::shared_ptr<Concurrency::scheduler_interface> * `Concurrency::details::_GetStaticAmbientSchedulerRef(void)'::`2'::_S_scheduler_address
0x14008cc5c  lea     rcx, ?_Flag@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4Uonce_flag@5@A; lpInitOnce
0x14008cc63  call    cs:__imp_InitOnceComplete
0x14008cc69  test    eax, eax
0x14008cc6b  jz      short loc_14008CC86
0x14008cc6d  mov     rax, cs:?_S_scheduler_address@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4PEAV45@EA; std::shared_ptr<Concurrency::scheduler_interface> * `Concurrency::details::_GetStaticAmbientSchedulerRef(void)'::`2'::_S_scheduler_address
0x14008cc74  mov     rcx, [rsp+48h+var_10]
0x14008cc79  xor     rcx, rsp; StackCookie
0x14008cc7c  call    __security_check_cookie
0x14008cc81  add     rsp, 48h
0x14008cc85  retn
0x14008cc86  call    __std_init_once_link_alternate_names_and_abort
0x14008cc8c  call    abort
0x14008cc92  lea     rcx, ?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA
0x14008cc99  call    _Init_thread_header
0x14008cc9e  cmp     cs:?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA, 0FFFFFFFFh
0x14008cca5  jnz     short loc_14008CC49
0x14008cca7  lea     rcx, ??__F_S_scheduler@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@YAXXZ; void (__cdecl *)()
0x14008ccae  call    atexit
0x14008ccb3  lea     rcx, ?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA
0x14008ccba  call    _Init_thread_footer
0x14008ccbf  jmp     short loc_14008CC49
```
