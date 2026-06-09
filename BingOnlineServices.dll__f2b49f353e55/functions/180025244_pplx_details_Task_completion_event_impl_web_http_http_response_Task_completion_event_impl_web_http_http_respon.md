# pplx::details::_Task_completion_event_impl<web::http::http_response>::~_Task_completion_event_impl<web::http::http_response>(void)

- ea: `0x180025244`
- end: `0x1800252c7`
- name: `??1?$_Task_completion_event_impl@Vhttp_response@http@web@@@details@pplx@@QEAA@XZ`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028bb0`

## callees

- `0x180007330`
- `0x1800106b8`
- `0x180012430`
- `0x180013f74`
- `0x1800148ac`
- `0x180025244`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025287`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180025287`

## pseudocode

```c
void __fastcall pplx::details::_Task_completion_event_impl<web::http::http_response>::~_Task_completion_event_impl<web::http::http_response>(
        __int64 a1)
{
  pplx::details::_Task_impl_base **i; // rbx
  std::_Ref_count_base *v3; // rcx

  for ( i = *(pplx::details::_Task_impl_base ***)a1; i != *(pplx::details::_Task_impl_base ***)(a1 + 8); i += 2 )
    pplx::details::_Task_impl_base::_Cancel(*i, 1);
  v3 = *(std::_Ref_count_base **)(a1 + 112);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  pplx::task<long>::~task<long>((void *)(a1 + 88));
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
0x180025244  mov     [rsp+arg_0], rbx
0x180025249  push    rdi
0x18002524a  sub     rsp, 20h
0x18002524e  mov     rdi, rcx
0x180025251  mov     rbx, [rcx]
0x180025254  cmp     rbx, [rdi+8]
0x180025258  jz      short loc_18002526A
0x18002525a  mov     dl, 1; bool
0x18002525c  mov     rcx, [rbx]; this
0x18002525f  call    ?_Cancel@_Task_impl_base@details@pplx@@QEAA_N_N@Z; pplx::details::_Task_impl_base::_Cancel(bool)
0x180025264  add     rbx, 10h
0x180025268  jmp     short loc_180025254
0x18002526a  mov     rcx, [rdi+70h]; this
0x18002526e  xor     ebx, ebx
0x180025270  test    rcx, rcx
0x180025273  jz      short loc_18002527A
0x180025275  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002527a  lea     rcx, [rdi+58h]; void *
0x18002527e  call    ??1?$task@J@pplx@@QEAA@XZ; pplx::task<long>::~task<long>(void)
0x180025283  lea     rcx, [rdi+18h]; lpCriticalSection
0x180025287  call    cs:__imp_DeleteCriticalSection
0x18002528d  mov     rcx, [rdi]
0x180025290  test    rcx, rcx
0x180025293  jz      short loc_1800252BC
0x180025295  mov     rdx, [rdi+8]
0x180025299  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@U?$_Task_impl@E@details@pplx@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@U?$_Task_impl@E@details@pplx@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@U?$_Task_impl@E@details@pplx@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<pplx::details::_Task_impl<uchar>>>>(std::shared_ptr<pplx::details::_Task_impl<uchar>> *,std::shared_ptr<pplx::details::_Task_impl<uchar>> * const,std::allocator<std::shared_ptr<pplx::details::_Task_impl<uchar>>> &)
0x18002529e  mov     rdx, [rdi+10h]
0x1800252a2  sub     rdx, [rdi]
0x1800252a5  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1800252a9  mov     rcx, [rdi]
0x1800252ac  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1800252b1  mov     [rdi], rbx
0x1800252b4  mov     [rdi+8], rbx
0x1800252b8  mov     [rdi+10h], rbx
0x1800252bc  mov     rbx, [rsp+28h+arg_0]
0x1800252c1  add     rsp, 20h
0x1800252c5  pop     rdi
0x1800252c6  retn
```
