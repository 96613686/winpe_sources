# Concurrency::details::_Task_impl_base::~_Task_impl_base(void)

- ea: `0x180010008`
- end: `0x1800100e0`
- name: `??1_Task_impl_base@details@Concurrency@@UEAA@XZ`
- size: `216`
- prototype: `void __fastcall(Concurrency::details::_Task_impl_base *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000fb74`
- `0x180010820`

## callees

- `0x18000fd1c`
- `0x180010008`
- `0x180019010`

## pseudocode

```c
void __fastcall Concurrency::details::_Task_impl_base::~_Task_impl_base(Concurrency::details::_Task_impl_base *this)
{
  volatile signed __int32 *v2; // rcx
  volatile signed __int32 *v3; // rbx
  volatile signed __int32 *v4; // rbx

  *(_QWORD *)this = &Concurrency::details::_Task_impl_base::`vftable';
  v2 = (volatile signed __int32 *)*((_QWORD *)this + 15);
  if ( v2 != (volatile signed __int32 *)2 && _InterlockedExchangeAdd(v2 + 2, 0xFFFFFFFF) == 1 )
    (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v2 + 8LL))(v2);
  std::vector<void *>::~vector<void *>((char **)this + 41);
  v3 = (volatile signed __int32 *)*((_QWORD *)this + 37);
  if ( v3 )
  {
    if ( !_InterlockedDecrement(v3 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
      if ( !_InterlockedDecrement(v3 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
    }
  }
  v4 = (volatile signed __int32 *)*((_QWORD *)this + 3);
  if ( v4 && !_InterlockedDecrement(v4 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
    if ( !_InterlockedDecrement(v4 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
  }
}

```

## disassembly

```asm
0x180010008  mov     [rsp+arg_8], rbx
0x18001000d  mov     [rsp+arg_10], rsi
0x180010012  push    rdi
0x180010013  sub     rsp, 20h
0x180010017  mov     rdi, rcx
0x18001001a  lea     rax, ??_7_Task_impl_base@details@Concurrency@@6B@; const Concurrency::details::_Task_impl_base::`vftable'
0x180010021  mov     [rcx], rax
0x180010024  mov     rcx, [rcx+78h]
0x180010028  or      esi, 0FFFFFFFFh
0x18001002b  cmp     rcx, 2
0x18001002f  jz      short loc_180010048
0x180010031  mov     eax, esi
0x180010033  lock xadd [rcx+8], eax
0x180010038  add     eax, esi
0x18001003a  jnz     short loc_180010048
0x18001003c  mov     rax, [rcx]
0x18001003f  mov     rax, [rax+8]
0x180010043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010048  lea     rcx, [rdi+148h]
0x18001004f  call    ??1?$vector@PEAXV?$allocator@PEAX@std@@@std@@QEAA@XZ; std::vector<void *>::~vector<void *>(void)
0x180010054  mov     rbx, [rdi+128h]
0x18001005b  test    rbx, rbx
0x18001005e  jz      short loc_180010093
0x180010060  mov     eax, esi
0x180010062  lock xadd [rbx+8], eax
0x180010067  add     eax, esi
0x180010069  jnz     short loc_180010093
0x18001006b  mov     rax, [rbx]
0x18001006e  mov     rcx, rbx
0x180010071  mov     rax, [rax]
0x180010074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010079  mov     eax, esi
0x18001007b  lock xadd [rbx+0Ch], eax
0x180010080  add     eax, esi
0x180010082  jnz     short loc_180010093
0x180010084  mov     rax, [rbx]
0x180010087  mov     rcx, rbx
0x18001008a  mov     rax, [rax+8]
0x18001008e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010093  mov     rbx, [rdi+18h]
0x180010097  test    rbx, rbx
0x18001009a  jz      short loc_1800100D0
0x18001009c  mov     eax, esi
0x18001009e  lock xadd [rbx+8], eax
0x1800100a3  add     eax, esi
0x1800100a5  jnz     short loc_1800100D0
0x1800100a7  mov     rax, [rbx]
0x1800100aa  mov     rcx, rbx
0x1800100ad  mov     rax, [rax]
0x1800100b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100b5  mov     eax, esi
0x1800100b7  lock xadd [rbx+0Ch], eax
0x1800100bc  add     eax, esi
0x1800100be  jnz     short loc_1800100D0
0x1800100c0  mov     rax, [rbx]
0x1800100c3  mov     rcx, rbx
0x1800100c6  mov     rax, [rax+8]
0x1800100ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100cf  nop
0x1800100d0  mov     rbx, [rsp+28h+arg_8]
0x1800100d5  mov     rsi, [rsp+28h+arg_10]
0x1800100da  add     rsp, 20h
0x1800100de  pop     rdi
0x1800100df  retn
```
