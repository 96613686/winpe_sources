# pplx::details::_Task_impl_base::~_Task_impl_base(void)

- ea: `0x180012b64`
- end: `0x180012bba`
- name: `??1_Task_impl_base@details@pplx@@UEAA@XZ`
- size: `86`
- prototype: `void __fastcall(pplx::details::_Task_impl_base *__hidden this)`
- caller_count: `12`
- callee_count: `5`
- tags: `service_task`

## callers

- `0x1800126b8`
- `0x1800126e4`
- `0x180013570`
- `0x18001aac8`
- `0x18001ab00`
- `0x18001ab38`
- `0x1800252d0`
- `0x1800252fc`
- `0x180033f1c`
- `0x180048900`
- `0x18004892c`
- `0x180059ae0`

## callees

- `0x180012b28`
- `0x180012b64`
- `0x1800148ac`
- `0x180015320`
- `0x1800157f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012b9f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180012b9f`

## pseudocode

```c
void __fastcall pplx::details::_Task_impl_base::~_Task_impl_base(pplx::details::_Task_impl_base *this)
{
  pplx::details::_RefCounter *v2; // rcx
  std::_Ref_count_base *v3; // rcx

  *(_QWORD *)this = &pplx::details::_Task_impl_base::`vftable';
  v2 = (pplx::details::_RefCounter *)*((_QWORD *)this + 12);
  if ( v2 != (pplx::details::_RefCounter *)2 )
    pplx::details::_RefCounter::_Release(v2);
  std::vector<void *>::_Tidy((char *)this + 160);
  pplx::details::_TaskCollectionImpl::~_TaskCollectionImpl((pplx::details::_Task_impl_base *)((char *)this + 120));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 3);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
}

```

## disassembly

```asm
0x180012b64  push    rbx
0x180012b66  sub     rsp, 20h
0x180012b6a  mov     rbx, rcx
0x180012b6d  lea     rax, ??_7_Task_impl_base@details@pplx@@6B@; const pplx::details::_Task_impl_base::`vftable'
0x180012b74  mov     [rcx], rax
0x180012b77  mov     rcx, [rcx+60h]; this
0x180012b7b  cmp     rcx, 2
0x180012b7f  jz      short loc_180012B86
0x180012b81  call    ?_Release@_RefCounter@details@pplx@@QEAAJXZ; pplx::details::_RefCounter::_Release(void)
0x180012b86  lea     rcx, [rbx+0A0h]
0x180012b8d  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x180012b92  lea     rcx, [rbx+78h]; this
0x180012b96  call    ??1_TaskCollectionImpl@details@pplx@@QEAA@XZ; pplx::details::_TaskCollectionImpl::~_TaskCollectionImpl(void)
0x180012b9b  lea     rcx, [rbx+20h]; lpCriticalSection
0x180012b9f  call    cs:__imp_DeleteCriticalSection
0x180012ba5  mov     rcx, [rbx+18h]; this
0x180012ba9  test    rcx, rcx
0x180012bac  jz      short loc_180012BB4
0x180012bae  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012bb3  nop
0x180012bb4  add     rsp, 20h
0x180012bb8  pop     rbx
0x180012bb9  retn
```
