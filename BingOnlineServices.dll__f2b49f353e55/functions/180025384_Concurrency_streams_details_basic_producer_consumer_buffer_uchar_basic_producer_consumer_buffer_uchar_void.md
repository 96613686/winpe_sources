# Concurrency::streams::details::basic_producer_consumer_buffer<uchar>::~basic_producer_consumer_buffer<uchar>(void)

- ea: `0x180025384`
- end: `0x180025413`
- name: `??1?$basic_producer_consumer_buffer@E@details@streams@Concurrency@@UEAA@XZ`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180026d40`

## callees

- `0x180012430`
- `0x1800148ac`
- `0x180025384`
- `0x18002541c`
- `0x18002544c`
- `0x1800254c0`
- `0x18002a2c0`
- `0x18002a5d0`
- `0x18002a620`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800253ed`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800253ed`

## pseudocode

```c
__int64 __fastcall Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::~basic_producer_consumer_buffer<unsigned char>(
        __int64 a1)
{
  std::_Ref_count_base *v2; // rcx
  _BYTE v4[24]; // [rsp+20h] [rbp-18h] BYREF

  *(_QWORD *)a1 = &Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::`vftable';
  Concurrency::streams::details::streambuf_state_manager<unsigned char>::_close_read(a1, v4);
  pplx::task<long>::~task<long>(v4);
  Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::_close_write(a1, v4);
  pplx::task<long>::~task<long>(v4);
  std::deque<std::shared_ptr<web::http::client::details::request_context>>::_Tidy(a1 + 176);
  std::deque<Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::_request,std::allocator<Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::_request>>::~deque<Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::_request,std::allocator<Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::_request>>(a1 + 216);
  std::deque<std::shared_ptr<Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::_block>>::~deque<std::shared_ptr<Concurrency::streams::details::basic_producer_consumer_buffer<unsigned char>::_block>>(a1 + 176);
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 112));
  v2 = *(std::_Ref_count_base **)(a1 + 72);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  return Concurrency::streams::details::streambuf_state_manager<unsigned char>::~streambuf_state_manager<unsigned char>(a1);
}

```

## disassembly

```asm
0x180025384  mov     [rsp+arg_0], rbx
0x180025389  push    rdi
0x18002538a  sub     rsp, 30h
0x18002538e  mov     rdi, rcx
0x180025391  lea     rax, ??_7?$basic_producer_consumer_buffer@E@details@streams@Concurrency@@6B@; const Concurrency::streams::details::basic_producer_consumer_buffer<uchar>::`vftable'
0x180025398  mov     [rcx], rax
0x18002539b  lea     rdx, [rsp+38h+var_18]
0x1800253a0  call    ?_close_read@?$streambuf_state_manager@E@details@streams@Concurrency@@MEAA?AV?$task@X@pplx@@XZ; Concurrency::streams::details::streambuf_state_manager<uchar>::_close_read(void)
0x1800253a5  lea     rcx, [rsp+38h+var_18]; void *
0x1800253aa  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x1800253af  lea     rdx, [rsp+38h+var_18]
0x1800253b4  mov     rcx, rdi
0x1800253b7  call    ?_close_write@?$basic_producer_consumer_buffer@E@details@streams@Concurrency@@EEAA?AV?$task@X@pplx@@XZ; Concurrency::streams::details::basic_producer_consumer_buffer<uchar>::_close_write(void)
0x1800253bc  lea     rcx, [rsp+38h+var_18]; void *
0x1800253c1  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x1800253c6  lea     rbx, [rdi+0B0h]
0x1800253cd  mov     rcx, rbx
0x1800253d0  call    ?_Tidy@?$deque@V?$shared_ptr@Vrequest_context@details@client@http@web@@@std@@V?$allocator@V?$shared_ptr@Vrequest_context@details@client@http@web@@@std@@@2@@std@@AEAAXXZ; std::deque<std::shared_ptr<web::http::client::details::request_context>>::_Tidy(void)
0x1800253d5  lea     rcx, [rdi+0D8h]
0x1800253dc  call    ??1?$deque@V_request@?$basic_producer_consumer_buffer@E@details@streams@Concurrency@@V?$allocator@V_request@?$basic_producer_consumer_buffer@E@details@streams@Concurrency@@@std@@@std@@QEAA@XZ; std::deque<Concurrency::streams::details::basic_producer_consumer_buffer<uchar>::_request,std::allocator<Concurrency::streams::details::basic_producer_consumer_buffer<uchar>::_request>>::~deque<Concurrency::streams::details::basic_producer_consumer_buffer<uchar>::_request,std::allocator<Concurrency::streams::details::basic_producer_consumer_buffer<uchar>::_request>>(void)
0x1800253e1  mov     rcx, rbx
0x1800253e4  call    ??1?$deque@V?$shared_ptr@V_block@?$basic_producer_consumer_buffer@E@details@streams@Concurrency@@@std@@V?$allocator@V?$shared_ptr@V_block@?$basic_producer_consumer_buffer@E@details@streams@Concurrency@@@std@@@2@@std@@QEAA@XZ; std::deque<std::shared_ptr<Concurrency::streams::details::basic_producer_consumer_buffer<uchar>::_block>>::~deque<std::shared_ptr<Concurrency::streams::details::basic_producer_consumer_buffer<uchar>::_block>>(void)
0x1800253e9  lea     rcx, [rdi+70h]; lpCriticalSection
0x1800253ed  call    cs:__imp_DeleteCriticalSection
0x1800253f3  mov     rcx, [rdi+48h]; this
0x1800253f7  test    rcx, rcx
0x1800253fa  jz      short loc_180025401
0x1800253fc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180025401  mov     rcx, rdi
0x180025404  mov     rbx, [rsp+38h+arg_0]
0x180025409  add     rsp, 30h
0x18002540d  pop     rdi
0x18002540e  jmp     ??1?$streambuf_state_manager@E@details@streams@Concurrency@@UEAA@XZ; Concurrency::streams::details::streambuf_state_manager<uchar>::~streambuf_state_manager<uchar>(void)
```
