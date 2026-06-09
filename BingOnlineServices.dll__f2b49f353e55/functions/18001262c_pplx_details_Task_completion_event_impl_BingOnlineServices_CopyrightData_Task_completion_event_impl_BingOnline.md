# pplx::details::_Task_completion_event_impl<BingOnlineServices::CopyrightData>::~_Task_completion_event_impl<BingOnlineServices::CopyrightData>(void)

- ea: `0x18001262c`
- end: `0x1800126b2`
- name: `??1?$_Task_completion_event_impl@VCopyrightData@BingOnlineServices@@@details@pplx@@QEAA@XZ`
- size: `134`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180014b30`

## callees

- `0x180007330`
- `0x180009fe0`
- `0x1800106b8`
- `0x18001262c`
- `0x180013f74`
- `0x1800148ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012672`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012672`

## pseudocode

```c
void __fastcall pplx::details::_Task_completion_event_impl<BingOnlineServices::CopyrightData>::~_Task_completion_event_impl<BingOnlineServices::CopyrightData>(
        __int64 a1)
{
  pplx::details::_Task_impl_base **i; // rbx
  std::_Ref_count_base *v3; // rcx

  for ( i = *(pplx::details::_Task_impl_base ***)a1; i != *(pplx::details::_Task_impl_base ***)(a1 + 8); i += 2 )
    pplx::details::_Task_impl_base::_Cancel(*i, 1);
  v3 = *(std::_Ref_count_base **)(a1 + 240);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
  BingOnlineServices::CopyrightData::~CopyrightData((BingOnlineServices::CopyrightData *)(a1 + 88));
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
0x18001262c  mov     [rsp+arg_0], rbx
0x180012631  push    rdi
0x180012632  sub     rsp, 20h
0x180012636  mov     rdi, rcx
0x180012639  mov     rbx, [rcx]
0x18001263c  cmp     rbx, [rdi+8]
0x180012640  jz      short loc_180012652
0x180012642  mov     dl, 1; bool
0x180012644  mov     rcx, [rbx]; this
0x180012647  call    ?_Cancel@_Task_impl_base@details@pplx@@QEAA_N_N@Z; pplx::details::_Task_impl_base::_Cancel(bool)
0x18001264c  add     rbx, 10h
0x180012650  jmp     short loc_18001263C
0x180012652  mov     rcx, [rdi+0F0h]; this
0x180012659  xor     ebx, ebx
0x18001265b  test    rcx, rcx
0x18001265e  jz      short loc_180012665
0x180012660  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012665  lea     rcx, [rdi+58h]; this
0x180012669  call    ??1CopyrightData@BingOnlineServices@@UEAA@XZ; BingOnlineServices::CopyrightData::~CopyrightData(void)
0x18001266e  lea     rcx, [rdi+18h]; lpCriticalSection
0x180012672  call    cs:__imp_DeleteCriticalSection
0x180012678  mov     rcx, [rdi]
0x18001267b  test    rcx, rcx
0x18001267e  jz      short loc_1800126A7
0x180012680  mov     rdx, [rdi+8]
0x180012684  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@U?$_Task_impl@E@details@pplx@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@U?$_Task_impl@E@details@pplx@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@U?$_Task_impl@E@details@pplx@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<pplx::details::_Task_impl<uchar>>>>(std::shared_ptr<pplx::details::_Task_impl<uchar>> *,std::shared_ptr<pplx::details::_Task_impl<uchar>> * const,std::allocator<std::shared_ptr<pplx::details::_Task_impl<uchar>>> &)
0x180012689  mov     rdx, [rdi+10h]
0x18001268d  sub     rdx, [rdi]
0x180012690  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180012694  mov     rcx, [rdi]
0x180012697  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001269c  mov     [rdi], rbx
0x18001269f  mov     [rdi+8], rbx
0x1800126a3  mov     [rdi+10h], rbx
0x1800126a7  mov     rbx, [rsp+28h+arg_0]
0x1800126ac  add     rsp, 20h
0x1800126b0  pop     rdi
0x1800126b1  retn
```
