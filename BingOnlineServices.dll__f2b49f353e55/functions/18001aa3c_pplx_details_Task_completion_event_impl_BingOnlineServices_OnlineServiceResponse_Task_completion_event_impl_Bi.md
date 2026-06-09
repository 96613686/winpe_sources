# pplx::details::_Task_completion_event_impl<BingOnlineServices::OnlineServiceResponse>::~_Task_completion_event_impl<BingOnlineServices::OnlineServiceResponse>(void)

- ea: `0x18001aa3c`
- end: `0x18001aac2`
- name: `??1?$_Task_completion_event_impl@UOnlineServiceResponse@BingOnlineServices@@@details@pplx@@QEAA@XZ`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001d130`

## callees

- `0x180007330`
- `0x1800106b8`
- `0x180012990`
- `0x180013f74`
- `0x1800148ac`
- `0x18001aa3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001aa82`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001aa82`

## pseudocode

```c
void __fastcall pplx::details::_Task_completion_event_impl<BingOnlineServices::OnlineServiceResponse>::~_Task_completion_event_impl<BingOnlineServices::OnlineServiceResponse>(
        __int64 a1)
{
  pplx::details::_Task_impl_base **i; // rbx
  std::_Ref_count_base *v3; // rcx

  for ( i = *(pplx::details::_Task_impl_base ***)a1; i != *(pplx::details::_Task_impl_base ***)(a1 + 8); i += 2 )
    pplx::details::_Task_impl_base::_Cancel(*i, 1);
  v3 = *(std::_Ref_count_base **)(a1 + 232);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  BingOnlineServices::OnlineServiceResponse::~OnlineServiceResponse((BingOnlineServices::OnlineServiceResponse *)(a1 + 88));
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  if ( *(_QWORD *)a1 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<pplx::details::_Task_impl<unsigned char>>>>(
      *(_QWORD *)a1,
      *(_QWORD *)(a1 + 8));
    std::_Deallocate<16>(*(void **)a1, (*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFF0uLL);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
}

```

## disassembly

```asm
0x18001aa3c  mov     [rsp+arg_0], rbx
0x18001aa41  push    rdi
0x18001aa42  sub     rsp, 20h
0x18001aa46  mov     rdi, rcx
0x18001aa49  mov     rbx, [rcx]
0x18001aa4c  cmp     rbx, [rdi+8]
0x18001aa50  jz      short loc_18001AA62
0x18001aa52  mov     dl, 1; bool
0x18001aa54  mov     rcx, [rbx]; this
0x18001aa57  call    ?_Cancel@_Task_impl_base@details@pplx@@QEAA_N_N@Z; pplx::details::_Task_impl_base::_Cancel(bool)
0x18001aa5c  add     rbx, 10h
0x18001aa60  jmp     short loc_18001AA4C
0x18001aa62  mov     rcx, [rdi+0E8h]; this
0x18001aa69  xor     ebx, ebx
0x18001aa6b  test    rcx, rcx
0x18001aa6e  jz      short loc_18001AA75
0x18001aa70  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001aa75  lea     rcx, [rdi+58h]; this
0x18001aa79  call    ??1OnlineServiceResponse@BingOnlineServices@@QEAA@XZ; BingOnlineServices::OnlineServiceResponse::~OnlineServiceResponse(void)
0x18001aa7e  lea     rcx, [rdi+18h]; lpCriticalSection
0x18001aa82  call    cs:__imp_DeleteCriticalSection
0x18001aa88  mov     rcx, [rdi]
0x18001aa8b  test    rcx, rcx
0x18001aa8e  jz      short loc_18001AAB7
0x18001aa90  mov     rdx, [rdi+8]
0x18001aa94  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@U?$_Task_impl@E@details@pplx@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@U?$_Task_impl@E@details@pplx@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@U?$_Task_impl@E@details@pplx@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<pplx::details::_Task_impl<uchar>>>>(std::shared_ptr<pplx::details::_Task_impl<uchar>> *,std::shared_ptr<pplx::details::_Task_impl<uchar>> * const,std::allocator<std::shared_ptr<pplx::details::_Task_impl<uchar>>> &)
0x18001aa99  mov     rdx, [rdi+10h]
0x18001aa9d  sub     rdx, [rdi]
0x18001aaa0  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001aaa4  mov     rcx, [rdi]
0x18001aaa7  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001aaac  mov     [rdi], rbx
0x18001aaaf  mov     [rdi+8], rbx
0x18001aab3  mov     [rdi+10h], rbx
0x18001aab7  mov     rbx, [rsp+28h+arg_0]
0x18001aabc  add     rsp, 20h
0x18001aac0  pop     rdi
0x18001aac1  retn
```
