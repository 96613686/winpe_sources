# Concurrency::get_ambient_scheduler(void)

- ea: `0x180012e78`
- end: `0x180012f33`
- name: `?get_ambient_scheduler@Concurrency@@YAAEBV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ`
- size: `187`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000eab0`
- `0x180012924`

## callees

- `0x180001c18`
- `0x18000248c`
- `0x1800025c0`
- `0x180002628`
- `0x180012e78`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180012e95`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180012e95`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180012ee8`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180012ee8`

## pseudocode

```c
__int64 Concurrency::get_ambient_scheduler()
{
  BOOL fPending; // [rsp+40h] [rbp+8h] BYREF

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
0x180012e78  sub     rsp, 38h
0x180012e7c  xor     r9d, r9d; lpContext
0x180012e7f  mov     [rsp+38h+fPending], 0
0x180012e87  lea     r8, [rsp+38h+fPending]; fPending
0x180012e8c  xor     edx, edx; dwFlags
0x180012e8e  lea     rcx, ?_Flag@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4Uonce_flag@5@A; lpInitOnce
0x180012e95  call    cs:__imp___std_init_once_begin_initialize
0x180012e9b  test    eax, eax
0x180012e9d  jnz     short loc_180012EA4
0x180012e9f  lea     ecx, [rax+5]
0x180012ea2  int     29h; Win8: RtlFailFast(ecx)
0x180012ea4  cmp     [rsp+38h+fPending], 0
0x180012ea9  jz      short loc_180012EF2
0x180012eab  mov     ecx, cs:_tls_index
0x180012eb1  mov     rax, gs:58h
0x180012eba  mov     edx, 4
0x180012ebf  mov     rax, [rax+rcx*8]
0x180012ec3  mov     eax, [rdx+rax]
0x180012ec6  cmp     cs:?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA, eax
0x180012ecc  jg      short loc_180012F04
0x180012ece  lea     rax, ?_S_scheduler@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4V45@A; std::shared_ptr<Concurrency::scheduler_interface> `Concurrency::details::_GetStaticAmbientSchedulerStorage(void)'::`2'::_S_scheduler
0x180012ed5  xor     r8d, r8d; lpContext
0x180012ed8  xor     edx, edx; dwFlags
0x180012eda  mov     cs:?_S_scheduler_address@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4PEAV45@EA, rax; std::shared_ptr<Concurrency::scheduler_interface> * `Concurrency::details::_GetStaticAmbientSchedulerRef(void)'::`2'::_S_scheduler_address
0x180012ee1  lea     rcx, ?_Flag@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4Uonce_flag@5@A; lpInitOnce
0x180012ee8  call    cs:__imp_InitOnceComplete
0x180012eee  test    eax, eax
0x180012ef0  jz      short loc_180012EFE
0x180012ef2  mov     rax, cs:?_S_scheduler_address@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4PEAV45@EA; std::shared_ptr<Concurrency::scheduler_interface> * `Concurrency::details::_GetStaticAmbientSchedulerRef(void)'::`2'::_S_scheduler_address
0x180012ef9  add     rsp, 38h
0x180012efd  retn
0x180012efe  call    __std_init_once_link_alternate_names_and_abort
0x180012f04  lea     rcx, ?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA
0x180012f0b  call    _Init_thread_header
0x180012f10  cmp     cs:?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA, 0FFFFFFFFh
0x180012f17  jnz     short loc_180012ECE
0x180012f19  lea     rcx, ??__F_S_scheduler@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@YAXXZ; void (__cdecl *)()
0x180012f20  call    atexit
0x180012f25  lea     rcx, ?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA
0x180012f2c  call    _Init_thread_footer
0x180012f31  jmp     short loc_180012ECE
```
