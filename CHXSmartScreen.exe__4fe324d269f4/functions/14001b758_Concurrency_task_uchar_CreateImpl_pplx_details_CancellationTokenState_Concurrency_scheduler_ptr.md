# Concurrency::task<uchar>::_CreateImpl(pplx::details::_CancellationTokenState *,Concurrency::scheduler_ptr)

- ea: `0x14001b758`
- end: `0x14001b8ec`
- name: `?_CreateImpl@?$task@E@Concurrency@@QEAAXPEAV_CancellationTokenState@details@pplx@@Uscheduler_ptr@2@@Z`
- size: `404`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x1400129fc`
- `0x14001b8f4`

## callees

- `0x1400017a0`
- `0x140012328`
- `0x14001471c`
- `0x14001b758`
- `0x14001cafc`
- `0x140035010`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Concurrency::task<unsigned char>::_CreateImpl(__int64 a1, __int64 a2, __int64 *a3)
{
  void *v6; // rax
  __int64 v7; // rdi
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 *v9; // rbx
  volatile signed __int32 *v10; // rbx
  __int64 v11; // [rsp+28h] [rbp-48h] BYREF
  __int128 v12; // [rsp+30h] [rbp-40h]
  __int64 v13; // [rsp+40h] [rbp-30h] BYREF
  volatile signed __int32 *v14; // [rsp+48h] [rbp-28h]
  __int64 v15; // [rsp+50h] [rbp-20h]
  __int64 *v16; // [rsp+58h] [rbp-18h]
  __int64 *v17; // [rsp+60h] [rbp-10h]

  v16 = a3;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    &v13,
    a3);
  v15 = a3[2];
  v17 = &v13;
  v11 = a2;
  v6 = operator new(0xC8u);
  *(_QWORD *)&v12 = v6;
  if ( v6 )
    v7 = std::_Ref_count_obj<Concurrency::details::_Task_impl<unsigned char>>::_Ref_count_obj<Concurrency::details::_Task_impl<unsigned char>>(
           v6,
           &v11,
           &v13);
  else
    v7 = 0;
  *((_QWORD *)&v12 + 1) = v7;
  *(_QWORD *)&v12 = v7 + 16;
  v8 = v14;
  if ( v14 )
  {
    if ( !_InterlockedDecrement(v14 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( !_InterlockedDecrement(v8 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  v12 = 0u;
  v9 = *(volatile signed __int32 **)(a1 + 8);
  *(_QWORD *)(a1 + 8) = v7;
  *(_QWORD *)a1 = v7 + 16;
  if ( v9 )
  {
    if ( !_InterlockedDecrement(v9 + 2) )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( !_InterlockedDecrement(v9 + 3) )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  if ( a2 != 2 )
    Concurrency::details::_Task_impl_base::_RegisterCancellation(*(Concurrency::details::_Task_impl_base **)a1);
  v10 = (volatile signed __int32 *)a3[1];
  if ( v10 && !_InterlockedDecrement(v10 + 2) )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
    if ( !_InterlockedDecrement(v10 + 3) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
  }
}

```

## disassembly

```asm
0x14001b758  mov     [rsp-38h+arg_18], rbx
0x14001b75d  push    rbp
0x14001b75e  push    rsi
0x14001b75f  push    rdi
0x14001b760  push    r12
0x14001b762  push    r13
0x14001b764  push    r14
0x14001b766  push    r15
0x14001b768  mov     rbp, rsp
0x14001b76b  sub     rsp, 70h
0x14001b76f  mov     r15, r8
0x14001b772  mov     r12, rdx
0x14001b775  mov     rsi, rcx
0x14001b778  mov     [rbp+var_18], r8
0x14001b77c  mov     [rbp+var_50], 0
0x14001b783  mov     rdx, r8
0x14001b786  lea     rcx, [rbp+var_30]
0x14001b78a  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x14001b78f  mov     rax, [r15+10h]
0x14001b793  mov     [rbp+var_20], rax
0x14001b797  lea     rax, [rbp+var_30]
0x14001b79b  mov     [rbp+var_10], rax
0x14001b79f  mov     [rbp+var_48], r12
0x14001b7a3  mov     ecx, 0C8h; Size
0x14001b7a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14001b7ad  mov     qword ptr [rbp+var_40], rax
0x14001b7b1  test    rax, rax
0x14001b7b4  jz      short loc_14001B7CB
0x14001b7b6  lea     r8, [rbp+var_30]
0x14001b7ba  lea     rdx, [rbp+var_48]
0x14001b7be  mov     rcx, rax
0x14001b7c1  call    ??$?0AEAPEAV_CancellationTokenState@details@pplx@@AEAUscheduler_ptr@Concurrency@@@?$_Ref_count_obj@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEAPEAV_CancellationTokenState@details@pplx@@AEAUscheduler_ptr@Concurrency@@@Z; std::_Ref_count_obj<Concurrency::details::_Task_impl<uchar>>::_Ref_count_obj<Concurrency::details::_Task_impl<uchar>>(pplx::details::_CancellationTokenState * &,Concurrency::scheduler_ptr &)
0x14001b7c6  mov     rdi, rax
0x14001b7c9  jmp     short loc_14001B7CD
0x14001b7cb  xor     edi, edi
0x14001b7cd  xorps   xmm0, xmm0
0x14001b7d0  movups  [rbp+var_40], xmm0
0x14001b7d4  mov     qword ptr [rbp+var_40+8], rdi
0x14001b7d8  lea     r14, [rdi+10h]
0x14001b7dc  mov     qword ptr [rbp+var_40], r14
0x14001b7e0  mov     [rbp+var_50], 1
0x14001b7e7  mov     rbx, [rbp+var_28]
0x14001b7eb  or      r13d, 0FFFFFFFFh
0x14001b7ef  test    rbx, rbx
0x14001b7f2  jz      short loc_14001B82C
0x14001b7f4  mov     eax, r13d
0x14001b7f7  lock xadd [rbx+8], eax
0x14001b7fc  add     eax, r13d
0x14001b7ff  jnz     short loc_14001B82C
0x14001b801  mov     rax, [rbx]
0x14001b804  mov     rcx, rbx
0x14001b807  mov     rax, [rax]
0x14001b80a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b80f  mov     eax, r13d
0x14001b812  lock xadd [rbx+0Ch], eax
0x14001b817  add     eax, r13d
0x14001b81a  jnz     short loc_14001B82C
0x14001b81c  mov     rax, [rbx]
0x14001b81f  mov     rcx, rbx
0x14001b822  mov     rax, [rax+8]
0x14001b826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b82b  nop
0x14001b82c  mov     qword ptr [rbp+var_40+8], 0
0x14001b834  mov     qword ptr [rbp+var_40], 0
0x14001b83c  mov     rbx, [rsi+8]
0x14001b840  mov     [rsi+8], rdi
0x14001b844  mov     [rsi], r14
0x14001b847  test    rbx, rbx
0x14001b84a  jz      short loc_14001B884
0x14001b84c  mov     eax, r13d
0x14001b84f  lock xadd [rbx+8], eax
0x14001b854  add     eax, r13d
0x14001b857  jnz     short loc_14001B884
0x14001b859  mov     rax, [rbx]
0x14001b85c  mov     rcx, rbx
0x14001b85f  mov     rax, [rax]
0x14001b862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b867  mov     eax, r13d
0x14001b86a  lock xadd [rbx+0Ch], eax
0x14001b86f  add     eax, r13d
0x14001b872  jnz     short loc_14001B884
0x14001b874  mov     rax, [rbx]
0x14001b877  mov     rcx, rbx
0x14001b87a  mov     rax, [rax+8]
0x14001b87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b883  nop
0x14001b884  cmp     r12, 2
0x14001b888  jz      short loc_14001B893
0x14001b88a  mov     rcx, [rsi]; this
0x14001b88d  call    ?_RegisterCancellation@_Task_impl_base@details@Concurrency@@QEAAXXZ; Concurrency::details::_Task_impl_base::_RegisterCancellation(void)
0x14001b892  nop
0x14001b893  mov     rbx, [r15+8]
0x14001b897  test    rbx, rbx
0x14001b89a  jz      short loc_14001B8D4
0x14001b89c  mov     eax, r13d
0x14001b89f  lock xadd [rbx+8], eax
0x14001b8a4  add     eax, r13d
0x14001b8a7  jnz     short loc_14001B8D4
0x14001b8a9  mov     rax, [rbx]
0x14001b8ac  mov     rcx, rbx
0x14001b8af  mov     rax, [rax]
0x14001b8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b8b7  mov     eax, r13d
0x14001b8ba  lock xadd [rbx+0Ch], eax
0x14001b8bf  add     eax, r13d
0x14001b8c2  jnz     short loc_14001B8D4
0x14001b8c4  mov     rax, [rbx]
0x14001b8c7  mov     rcx, rbx
0x14001b8ca  mov     rax, [rax+8]
0x14001b8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001b8d3  nop
0x14001b8d4  mov     rbx, [rsp+70h+arg_18]
0x14001b8dc  add     rsp, 70h
0x14001b8e0  pop     r15
0x14001b8e2  pop     r14
0x14001b8e4  pop     r13
0x14001b8e6  pop     r12
0x14001b8e8  pop     rdi
0x14001b8e9  pop     rsi
0x14001b8ea  pop     rbp
0x14001b8eb  retn
```
