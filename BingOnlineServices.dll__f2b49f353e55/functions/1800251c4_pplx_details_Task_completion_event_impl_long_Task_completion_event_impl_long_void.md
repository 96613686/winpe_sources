# pplx::details::_Task_completion_event_impl<long>::~_Task_completion_event_impl<long>(void)

- ea: `0x1800251c4`
- end: `0x18002523e`
- name: `??1?$_Task_completion_event_impl@J@details@pplx@@QEAA@XZ`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180028ba0`

## callees

- `0x180007330`
- `0x1800106b8`
- `0x180013f74`
- `0x1800148ac`
- `0x1800251c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800251fe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800251fe`

## pseudocode

```c
void __fastcall pplx::details::_Task_completion_event_impl<long>::~_Task_completion_event_impl<long>(__int64 a1)
{
  pplx::details::_Task_impl_base **i; // rbx
  std::_Ref_count_base *v3; // rcx

  for ( i = *(pplx::details::_Task_impl_base ***)a1; i != *(pplx::details::_Task_impl_base ***)(a1 + 8); i += 2 )
    pplx::details::_Task_impl_base::_Cancel(*i, 1);
  v3 = *(std::_Ref_count_base **)(a1 + 104);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
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
0x1800251c4  mov     [rsp+arg_0], rbx
0x1800251c9  push    rdi
0x1800251ca  sub     rsp, 20h
0x1800251ce  mov     rdi, rcx
0x1800251d1  mov     rbx, [rcx]
0x1800251d4  cmp     rbx, [rdi+8]
0x1800251d8  jz      short loc_1800251EA
0x1800251da  mov     dl, 1; bool
0x1800251dc  mov     rcx, [rbx]; this
0x1800251df  call    ?_Cancel@_Task_impl_base@details@pplx@@QEAA_N_N@Z; pplx::details::_Task_impl_base::_Cancel(bool)
0x1800251e4  add     rbx, 10h
0x1800251e8  jmp     short loc_1800251D4
0x1800251ea  mov     rcx, [rdi+68h]; this
0x1800251ee  xor     ebx, ebx
0x1800251f0  test    rcx, rcx
0x1800251f3  jz      short loc_1800251FA
0x1800251f5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800251fa  lea     rcx, [rdi+18h]; lpCriticalSection
0x1800251fe  call    cs:__imp_DeleteCriticalSection
0x180025204  mov     rcx, [rdi]
0x180025207  test    rcx, rcx
0x18002520a  jz      short loc_180025233
0x18002520c  mov     rdx, [rdi+8]
0x180025210  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@U?$_Task_impl@E@details@pplx@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@U?$_Task_impl@E@details@pplx@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@U?$_Task_impl@E@details@pplx@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<pplx::details::_Task_impl<uchar>>>>(std::shared_ptr<pplx::details::_Task_impl<uchar>> *,std::shared_ptr<pplx::details::_Task_impl<uchar>> * const,std::allocator<std::shared_ptr<pplx::details::_Task_impl<uchar>>> &)
0x180025215  mov     rdx, [rdi+10h]
0x180025219  sub     rdx, [rdi]
0x18002521c  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180025220  mov     rcx, [rdi]
0x180025223  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180025228  mov     [rdi], rbx
0x18002522b  mov     [rdi+8], rbx
0x18002522f  mov     [rdi+10h], rbx
0x180025233  mov     rbx, [rsp+28h+arg_0]
0x180025238  add     rsp, 20h
0x18002523c  pop     rdi
0x18002523d  retn
```
