# Concurrency::get_ambient_scheduler(void)

- ea: `0x18002c978`
- end: `0x18002ca50`
- name: `?get_ambient_scheduler@Concurrency@@YAAEBV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ`
- size: `216`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001a67c`
- `0x18001a8cc`
- `0x180029d08`

## callees

- `0x18002c978`
- `0x180037fa0`
- `0x1800563c8`
- `0x180056500`
- `0x1800569e8`
- `0x180056b80`
- `0x180056be8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002c9f2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18002c9f2`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002c9a4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002c9a4`

## pseudocode

```c
__int64 Concurrency::get_ambient_scheduler()
{
  __int64 v0; // rdx
  __int64 v1; // rcx
  BOOL fPending; // [rsp+30h] [rbp-18h] BYREF

  fPending = 0;
  if ( !__std_init_once_begin_initialize(
          &`Concurrency::details::_GetStaticAmbientSchedulerRef'::`2'::_Flag,
          0,
          &fPending,
          0) )
    abort();
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
0x18002c978  sub     rsp, 48h
0x18002c97c  mov     rax, cs:__security_cookie
0x18002c983  xor     rax, rsp
0x18002c986  mov     [rsp+48h+var_10], rax
0x18002c98b  xor     r9d, r9d; lpContext
0x18002c98e  mov     [rsp+48h+fPending], 0
0x18002c996  lea     r8, [rsp+48h+fPending]; fPending
0x18002c99b  xor     edx, edx; dwFlags
0x18002c99d  lea     rcx, ?_Flag@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4Uonce_flag@5@A; lpInitOnce
0x18002c9a4  call    cs:__imp___std_init_once_begin_initialize
0x18002c9aa  test    eax, eax
0x18002c9ac  jz      short loc_18002CA1B
0x18002c9ae  cmp     [rsp+48h+fPending], 0
0x18002c9b3  jz      short loc_18002C9FC
0x18002c9b5  mov     ecx, cs:_tls_index
0x18002c9bb  mov     rax, gs:58h
0x18002c9c4  mov     edx, 4
0x18002c9c9  mov     rax, [rax+rcx*8]
0x18002c9cd  mov     eax, [rdx+rax]
0x18002c9d0  cmp     cs:?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA, eax
0x18002c9d6  jg      short loc_18002CA21
0x18002c9d8  lea     rax, ?_S_scheduler@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4V45@A; std::shared_ptr<Concurrency::scheduler_interface> `Concurrency::details::_GetStaticAmbientSchedulerStorage(void)'::`2'::_S_scheduler
0x18002c9df  xor     r8d, r8d; lpContext
0x18002c9e2  xor     edx, edx; dwFlags
0x18002c9e4  mov     cs:?_S_scheduler_address@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4PEAV45@EA, rax; std::shared_ptr<Concurrency::scheduler_interface> * `Concurrency::details::_GetStaticAmbientSchedulerRef(void)'::`2'::_S_scheduler_address
0x18002c9eb  lea     rcx, ?_Flag@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4Uonce_flag@5@A; lpInitOnce
0x18002c9f2  call    cs:__imp_InitOnceComplete
0x18002c9f8  test    eax, eax
0x18002c9fa  jz      short loc_18002CA15
0x18002c9fc  mov     rax, cs:?_S_scheduler_address@?1??_GetStaticAmbientSchedulerRef@details@Concurrency@@YAAEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4PEAV45@EA; std::shared_ptr<Concurrency::scheduler_interface> * `Concurrency::details::_GetStaticAmbientSchedulerRef(void)'::`2'::_S_scheduler_address
0x18002ca03  mov     rcx, [rsp+48h+var_10]
0x18002ca08  xor     rcx, rsp; StackCookie
0x18002ca0b  call    __security_check_cookie
0x18002ca10  add     rsp, 48h
0x18002ca14  retn
0x18002ca15  call    __std_init_once_link_alternate_names_and_abort
0x18002ca1b  call    abort
0x18002ca21  lea     rcx, ?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA
0x18002ca28  call    _Init_thread_header
0x18002ca2d  cmp     cs:?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA, 0FFFFFFFFh
0x18002ca34  jnz     short loc_18002C9D8
0x18002ca36  lea     rcx, ??__F_S_scheduler@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@YAXXZ; void (__cdecl *)()
0x18002ca3d  call    atexit
0x18002ca42  lea     rcx, ?$TSS0@?1??_GetStaticAmbientSchedulerStorage@details@Concurrency@@YAPEAV?$shared_ptr@Uscheduler_interface@Concurrency@@@std@@XZ@4HA
0x18002ca49  call    _Init_thread_footer
0x18002ca4e  jmp     short loc_18002C9D8
```
