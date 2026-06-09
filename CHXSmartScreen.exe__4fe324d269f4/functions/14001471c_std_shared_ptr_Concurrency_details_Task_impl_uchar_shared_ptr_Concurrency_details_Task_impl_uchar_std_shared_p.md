# std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)

- ea: `0x14001471c`
- end: `0x14001479a`
- name: `??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z`
- size: `126`
- prototype: ``
- caller_count: `17`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140012328`
- `0x140012420`
- `0x140012518`
- `0x1400128b8`
- `0x1400129fc`
- `0x140013080`
- `0x140013344`
- `0x1400134c0`
- `0x140013784`
- `0x140014460`
- `0x1400145c4`
- `0x140014aac`
- `0x14001ac88`
- `0x14001b758`
- `0x14001b8f4`
- `0x14001bec0`
- `0x140023fa8`

## callees

- `0x14001471c`
- `0x140035010`

## pseudocode

```c
_QWORD *__fastcall std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
        _QWORD *a1,
        __int64 *a2)
{
  __int64 v3; // rsi
  __int64 v4; // rbp
  volatile signed __int32 *v5; // rbx

  *a1 = 0;
  a1[1] = 0;
  v3 = a2[1];
  v4 = *a2;
  if ( v3 )
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 8));
  v5 = (volatile signed __int32 *)a1[1];
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  a1[1] = v3;
  *a1 = v4;
  return a1;
}

```

## disassembly

```asm
0x14001471c  push    rbx
0x14001471e  push    rbp
0x14001471f  push    rsi
0x140014720  push    rdi
0x140014721  sub     rsp, 28h
0x140014725  mov     rdi, rcx
0x140014728  mov     qword ptr [rcx], 0
0x14001472f  mov     qword ptr [rcx+8], 0
0x140014737  mov     rsi, [rdx+8]
0x14001473b  mov     rbp, [rdx]
0x14001473e  test    rsi, rsi
0x140014741  jz      short loc_140014747
0x140014743  lock inc dword ptr [rsi+8]
0x140014747  mov     rbx, [rcx+8]
0x14001474b  test    rbx, rbx
0x14001474e  jz      short loc_140014787
0x140014750  or      eax, 0FFFFFFFFh
0x140014753  lock xadd [rbx+8], eax
0x140014758  cmp     eax, 1
0x14001475b  jnz     short loc_140014787
0x14001475d  mov     rax, [rbx]
0x140014760  mov     rcx, rbx
0x140014763  mov     rax, [rax]
0x140014766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001476b  or      eax, 0FFFFFFFFh
0x14001476e  lock xadd [rbx+0Ch], eax
0x140014773  cmp     eax, 1
0x140014776  jnz     short loc_140014787
0x140014778  mov     rax, [rbx]
0x14001477b  mov     rcx, rbx
0x14001477e  mov     rax, [rax+8]
0x140014782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014787  mov     [rdi+8], rsi
0x14001478b  mov     [rdi], rbp
0x14001478e  mov     rax, rdi
0x140014791  add     rsp, 28h
0x140014795  pop     rdi
0x140014796  pop     rsi
0x140014797  pop     rbp
0x140014798  pop     rbx
0x140014799  retn
```
