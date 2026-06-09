# Concurrency::task_options::~task_options(void)

- ea: `0x18001e47c`
- end: `0x18001e4c5`
- name: `??1task_options@Concurrency@@QEAA@XZ`
- size: `73`
- prototype: `void __fastcall(Concurrency::task_options *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18001d428`
- `0x18001d4c0`
- `0x18001d558`
- `0x180026942`

## callees

- `0x18001e47c`
- `0x180022f00`
- `0x180023dbc`
- `0x180024360`

## import_xrefs

- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18001e493`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x18001e493`

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
0x18001e47c  push    rbx
0x18001e47e  sub     rsp, 20h
0x18001e482  mov     rbx, rcx
0x18001e485  add     rcx, 40h ; '@'
0x18001e489  call    ?_Tidy@?$vector@PEAXV?$allocator@PEAX@std@@@std@@AEAAXXZ; std::vector<void *>::_Tidy(void)
0x18001e48e  nop
0x18001e48f  lea     rcx, [rbx+20h]
0x18001e493  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x18001e499  nop
0x18001e49a  mov     rcx, [rbx+18h]; this
0x18001e49e  test    rcx, rcx
0x18001e4a1  jz      short loc_18001E4A8
0x18001e4a3  call    ?_Release@_RefCounter@details@Concurrency@@QEAAJXZ; Concurrency::details::_RefCounter::_Release(void)
0x18001e4a8  mov     qword ptr [rbx+18h], 0
0x18001e4b0  mov     rcx, [rbx+8]; this
0x18001e4b4  test    rcx, rcx
0x18001e4b7  jz      short loc_18001E4BF
0x18001e4b9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001e4be  nop
0x18001e4bf  add     rsp, 20h
0x18001e4c3  pop     rbx
0x18001e4c4  retn
```
