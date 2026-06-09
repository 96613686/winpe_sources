# Concurrency::task_options::~task_options(void)

- ea: `0x1800120a4`
- end: `0x1800120ed`
- name: `??1task_options@Concurrency@@QEAA@XZ`
- size: `73`
- prototype: `void __fastcall(Concurrency::task_options *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000e624`
- `0x18000ee28`
- `0x18002361e`
- `0x180023712`

## callees

- `0x1800120a4`
- `0x18001cc40`
- `0x18001d7a0`
- `0x18001dd48`

## import_xrefs

- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x1800120bb`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x1800120bb`

## pseudocode

```c
void __fastcall Concurrency::task_options::~task_options(Concurrency::task_options *this)
{
  Concurrency::details::_RefCounter *v2; // rcx
  std::_Ref_count_base *v3; // rcx

  std::vector<void *>::_Tidy((char *)this + 64);
  Concurrency::details::_ContextCallback::_Reset((Concurrency::task_options *)((char *)this + 32));
  v2 = (Concurrency::details::_RefCounter *)*((_QWORD *)this + 3);
  if ( v2 )
    Concurrency::details::_RefCounter::_Release(v2);
  *((_QWORD *)this + 3) = 0;
  v3 = (std::_Ref_count_base *)*((_QWORD *)this + 1);
  if ( v3 )
    std::_Ref_count_base::_Decref(v3);
}

```

## disassembly

```asm
0x1800120a4  push    rbx
0x1800120a6  sub     rsp, 20h
0x1800120aa  mov     rbx, rcx
0x1800120ad  add     rcx, 40h ; '@'
0x1800120b1  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x1800120b6  nop
0x1800120b7  lea     rcx, [rbx+20h]
0x1800120bb  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x1800120c1  nop
0x1800120c2  mov     rcx, [rbx+18h]; this
0x1800120c6  test    rcx, rcx
0x1800120c9  jz      short loc_1800120D0
0x1800120cb  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x1800120d0  mov     qword ptr [rbx+18h], 0
0x1800120d8  mov     rcx, [rbx+8]; this
0x1800120dc  test    rcx, rcx
0x1800120df  jz      short loc_1800120E7
0x1800120e1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800120e6  nop
0x1800120e7  add     rsp, 20h
0x1800120eb  pop     rbx
0x1800120ec  retn
```
