# Concurrency::get_ambient_scheduler(void)

- ea: `0x18001a6a8`
- end: `0x18001a763`
- name: `?get_ambient_scheduler@Concurrency@@YAAEBV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ`
- size: `187`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001510c`
- `0x180019d44`

## callees

- `0x1800025d8`
- `0x180003a5c`
- `0x180003b90`
- `0x180003bf8`
- `0x18001a6a8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001a718`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001a718`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001a6c5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001a6c5`

## pseudocode

```c
__int64 Concurrency::get_ambient_scheduler()
{
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
      _std_init_once_link_alternate_names_and_abort();
  }
  return `Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_S_scheduler_address;
}

```

## disassembly

```asm
0x18001a6a8  sub     rsp, 38h
0x18001a6ac  xor     r9d, r9d; lpContext
0x18001a6af  mov     [rsp+38h+fPending], 0
0x18001a6b7  lea     r8, [rsp+38h+fPending]; fPending
0x18001a6bc  xor     edx, edx; dwFlags
0x18001a6be  lea     rcx, ?_Flag@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4Uonce_flag@5@A; lpInitOnce
0x18001a6c5  call    cs:__imp___std_init_once_begin_initialize
0x18001a6cb  test    eax, eax
0x18001a6cd  jnz     short loc_18001A6D4
0x18001a6cf  lea     ecx, [rax+5]
0x18001a6d2  int     29h; Win8: RtlFailFast(ecx)
0x18001a6d4  cmp     [rsp+38h+fPending], 0
0x18001a6d9  jz      short loc_18001A722
0x18001a6db  mov     ecx, cs:_tls_index
0x18001a6e1  mov     rax, gs:58h
0x18001a6ea  mov     edx, 4
0x18001a6ef  mov     rax, [rax+rcx*8]
0x18001a6f3  mov     eax, [rdx+rax]
0x18001a6f6  cmp     cs:?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA, eax
0x18001a6fc  jg      short loc_18001A734
0x18001a6fe  lea     rax, ?_S_scheduler@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4V45@A; std::shared_ptr<Concurrency::scheduler_interface> `Concurrency::details::_GetStaticAmbientSchedulerStorage(void)'::`2'::_S_scheduler
0x18001a705  xor     r8d, r8d; lpContext
0x18001a708  xor     edx, edx; dwFlags
0x18001a70a  mov     cs:?_S_scheduler_address@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4PEAV45@EA, rax; std::shared_ptr<Concurrency::scheduler_interface> * `Concurrency::details::_GetStaticAmbientSchedulerRef(void)'::`2'::_S_scheduler_address
0x18001a711  lea     rcx, ?_Flag@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4Uonce_flag@5@A; lpInitOnce
0x18001a718  call    cs:__imp_InitOnceComplete
0x18001a71e  test    eax, eax
0x18001a720  jz      short loc_18001A72E
0x18001a722  mov     rax, cs:?_S_scheduler_address@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4PEAV45@EA; std::shared_ptr<Concurrency::scheduler_interface> * `Concurrency::details::_GetStaticAmbientSchedulerRef(void)'::`2'::_S_scheduler_address
0x18001a729  add     rsp, 38h
0x18001a72d  retn
0x18001a72e  call    __std_init_once_link_alternate_names_and_abort
0x18001a734  lea     rcx, ?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA
0x18001a73b  call    _Init_thread_header
0x18001a740  cmp     cs:?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA, 0FFFFFFFFh
0x18001a747  jnz     short loc_18001A6FE
0x18001a749  lea     rcx, ??__F_S_scheduler@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@YAXXZ; void (__cdecl *)()
0x18001a750  call    atexit
0x18001a755  lea     rcx, ?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA
0x18001a75c  call    _Init_thread_footer
0x18001a761  jmp     short loc_18001A6FE
```
