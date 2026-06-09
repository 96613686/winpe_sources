# web::http::http_pipeline::~http_pipeline(void)

- ea: `0x1800340c8`
- end: `0x18003412a`
- name: `??1http_pipeline@http@web@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(web::http::http_pipeline *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x180034ed8`

## callees

- `0x180007330`
- `0x1800106b8`
- `0x1800148ac`
- `0x1800340c8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800340d5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800340d5`

## pseudocode

```c
void __fastcall web::http::http_pipeline::~http_pipeline(web::http::http_pipeline *this)
{
  std::_Ref_count_base *v2; // rcx

  DeleteCriticalSection((LPCRITICAL_SECTION)this + 1);
  v2 = (std::_Ref_count_base *)*((_QWORD *)this + 4);
  if ( v2 )
    std::_Ref_count_base::_Decref(v2);
  if ( *(_QWORD *)this )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<pplx::details::_Task_impl<unsigned char>>>>(
      *(_QWORD *)this,
      *((_QWORD *)this + 1));
    std::_Deallocate<16>(*(void **)this, (*((_QWORD *)this + 2) - *(_QWORD *)this) & 0xFFFFFFFFFFFFFFF0uLL);
    *(_QWORD *)this = 0;
    *((_QWORD *)this + 1) = 0;
    *((_QWORD *)this + 2) = 0;
  }
}

```

## disassembly

```asm
0x1800340c8  push    rbx
0x1800340ca  sub     rsp, 20h
0x1800340ce  mov     rbx, rcx
0x1800340d1  add     rcx, 28h ; '('; lpCriticalSection
0x1800340d5  call    cs:__imp_DeleteCriticalSection
0x1800340db  mov     rcx, [rbx+20h]; this
0x1800340df  test    rcx, rcx
0x1800340e2  jz      short loc_1800340E9
0x1800340e4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800340e9  mov     rcx, [rbx]
0x1800340ec  test    rcx, rcx
0x1800340ef  jz      short loc_180034124
0x1800340f1  mov     rdx, [rbx+8]
0x1800340f5  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@U?$_Task_impl@E@details@pplx@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@U?$_Task_impl@E@details@pplx@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@U?$_Task_impl@E@details@pplx@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<pplx::details::_Task_impl<uchar>>>>(std::shared_ptr<pplx::details::_Task_impl<uchar>> *,std::shared_ptr<pplx::details::_Task_impl<uchar>> * const,std::allocator<std::shared_ptr<pplx::details::_Task_impl<uchar>>> &)
0x1800340fa  mov     rdx, [rbx+10h]
0x1800340fe  sub     rdx, [rbx]
0x180034101  mov     rcx, [rbx]
0x180034104  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180034108  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18003410d  mov     qword ptr [rbx], 0
0x180034114  mov     qword ptr [rbx+8], 0
0x18003411c  mov     qword ptr [rbx+10h], 0
0x180034124  add     rsp, 20h
0x180034128  pop     rbx
0x180034129  retn
```
