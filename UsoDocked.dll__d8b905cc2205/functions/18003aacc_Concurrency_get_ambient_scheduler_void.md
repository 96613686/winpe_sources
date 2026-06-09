# Concurrency::get_ambient_scheduler(void)

- ea: `0x18003aacc`
- end: `0x18003ab87`
- name: `?get_ambient_scheduler@Concurrency@@YAAEBV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ`
- size: `187`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18002b0e4`
- `0x180039e74`

## callees

- `0x180007238`
- `0x1800077a0`
- `0x180007808`
- `0x180007da0`
- `0x18003aacc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003aae9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18003aae9`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003ab3c`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18003ab3c`

## pseudocode

```c
__int64 Concurrency::get_ambient_scheduler()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  WINBOOL fPending; // [rsp+40h] [rbp+8h] BYREF

  fPending = 0;
  if ( !__std_init_once_begin_initialize(
          &`Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_Flag,
          0,
          &fPending,
          0) )
    __fastfail(5u);
  if ( fPending )
  {
    if ( __TSS0__1___GetStaticAmbientSchedulerStorage_details_Concurrency__YAPEAV__shared_ptr_Uscheduler_interface_Concurrency___std__XZ_4HA > *(_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL) )
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
0x18003aacc  sub     rsp, 38h
0x18003aad0  xor     r9d, r9d; lpContext
0x18003aad3  mov     [rsp+38h+fPending], 0
0x18003aadb  lea     r8, [rsp+38h+fPending]; fPending
0x18003aae0  xor     edx, edx; dwFlags
0x18003aae2  lea     rcx, ?_Flag@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4Uonce_flag@5@A; lpInitOnce
0x18003aae9  call    cs:__imp___std_init_once_begin_initialize
0x18003aaef  test    eax, eax
0x18003aaf1  jnz     short loc_18003AAF8
0x18003aaf3  lea     ecx, [rax+5]
0x18003aaf6  int     29h; Win8: RtlFailFast(ecx)
0x18003aaf8  cmp     [rsp+38h+fPending], 0
0x18003aafd  jz      short loc_18003AB46
0x18003aaff  mov     ecx, cs:_tls_index
0x18003ab05  mov     rax, gs:58h
0x18003ab0e  mov     edx, 4
0x18003ab13  mov     rax, [rax+rcx*8]
0x18003ab17  mov     eax, [rdx+rax]
0x18003ab1a  cmp     cs:?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA, eax
0x18003ab20  jg      short loc_18003AB58
0x18003ab22  lea     rax, ?_S_scheduler@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4V45@A; std::shared_ptr<Concurrency::scheduler_interface> `Concurrency::details::_GetStaticAmbientSchedulerStorage(void)'::`2'::_S_scheduler
0x18003ab29  xor     r8d, r8d; lpContext
0x18003ab2c  xor     edx, edx; dwFlags
0x18003ab2e  mov     cs:?_S_scheduler_address@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4PEAV45@EA, rax; std::shared_ptr<Concurrency::scheduler_interface> * `Concurrency::details::_GetStaticAmbientSchedulerRef(void)'::`2'::_S_scheduler_address
0x18003ab35  lea     rcx, ?_Flag@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4Uonce_flag@5@A; lpInitOnce
0x18003ab3c  call    cs:__imp_InitOnceComplete
0x18003ab42  test    eax, eax
0x18003ab44  jz      short loc_18003AB52
0x18003ab46  mov     rax, cs:?_S_scheduler_address@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4PEAV45@EA; std::shared_ptr<Concurrency::scheduler_interface> * `Concurrency::details::_GetStaticAmbientSchedulerRef(void)'::`2'::_S_scheduler_address
0x18003ab4d  add     rsp, 38h
0x18003ab51  retn
0x18003ab52  call    __std_init_once_link_alternate_names_and_abort
0x18003ab58  lea     rcx, ?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA
0x18003ab5f  call    _Init_thread_header
0x18003ab64  cmp     cs:?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA, 0FFFFFFFFh
0x18003ab6b  jnz     short loc_18003AB22
0x18003ab6d  lea     rcx, ??__F_S_scheduler@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@YAXXZ; void (__cdecl *)()
0x18003ab74  call    atexit
0x18003ab79  lea     rcx, ?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA
0x18003ab80  call    _Init_thread_footer
0x18003ab85  jmp     short loc_18003AB22
```
