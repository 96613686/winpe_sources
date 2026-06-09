# Concurrency::task_options::~task_options(void)

- ea: `0x1800168b0`
- end: `0x18001693f`
- name: `??1task_options@Concurrency@@QEAA@XZ`
- size: `143`
- prototype: `void __fastcall(Concurrency::task_options *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180015488`
- `0x18002ad9a`

## callees

- `0x1800165e8`
- `0x1800168b0`
- `0x18002d010`

## import_xrefs

- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x1800168c7`
- `msvcp_win!?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ` at `0x1800168c7`

## pseudocode

```c
void __fastcall Concurrency::task_options::~task_options(Concurrency::task_options *this)
{
  volatile signed __int32 *v2; // rcx
  volatile signed __int32 *v3; // rbx

  std::vector<void *>::~vector<void *>((char *)this + 64);
  Concurrency::details::_ContextCallback::_Reset((Concurrency::task_options *)((char *)this + 32));
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 3);
  if ( v2 && _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
  *((_QWORD *)this + 3) = 0;
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  if ( v3 && _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
    if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
  }
}

```

## disassembly

```asm
0x1800168b0  push    rbx
0x1800168b2  sub     rsp, 20h
0x1800168b6  mov     rbx, rcx
0x1800168b9  add     rcx, 40h ; '@'
0x1800168bd  call    ??1?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::~vector<void *>(void)
0x1800168c2  nop
0x1800168c3  lea     rcx, [rbx+20h]
0x1800168c7  call    cs:__imp_?_Reset@_ContextCallback@details@Concurrency@@AEAAXXZ; Concurrency::details::_ContextCallback::_Reset(void)
0x1800168cd  nop
0x1800168ce  mov     rcx, [rbx+18h]
0x1800168d2  test    rcx, rcx
0x1800168d5  jz      short loc_1800168F0
0x1800168d7  or      eax, 0FFFFFFFFh
0x1800168da  lock xadd [rcx+8], eax
0x1800168df  cmp     eax, 1
0x1800168e2  jnz     short loc_1800168F0
0x1800168e4  mov     rax, [rcx]
0x1800168e7  mov     rax, [rax+8]
0x1800168eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168f0  mov     qword ptr [rbx+18h], 0
0x1800168f8  mov     rbx, [rbx+8]
0x1800168fc  test    rbx, rbx
0x1800168ff  jz      short loc_180016939
0x180016901  or      eax, 0FFFFFFFFh
0x180016904  lock xadd [rbx+8], eax
0x180016909  cmp     eax, 1
0x18001690c  jnz     short loc_180016939
0x18001690e  mov     rax, [rbx]
0x180016911  mov     rcx, rbx
0x180016914  mov     rax, [rax]
0x180016917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001691c  or      eax, 0FFFFFFFFh
0x18001691f  lock xadd [rbx+0Ch], eax
0x180016924  cmp     eax, 1
0x180016927  jnz     short loc_180016939
0x180016929  mov     rax, [rbx]
0x18001692c  mov     rcx, rbx
0x18001692f  mov     rax, [rax+8]
0x180016933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016938  nop
0x180016939  add     rsp, 20h
0x18001693d  pop     rbx
0x18001693e  retn
```
