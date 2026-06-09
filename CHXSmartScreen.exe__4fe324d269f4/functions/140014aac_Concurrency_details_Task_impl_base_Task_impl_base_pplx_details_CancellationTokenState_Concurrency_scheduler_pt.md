# Concurrency::details::_Task_impl_base::_Task_impl_base(pplx::details::_CancellationTokenState *,Concurrency::scheduler_ptr)

- ea: `0x140014aac`
- end: `0x140014bea`
- name: `??0_Task_impl_base@details@Concurrency@@QEAA@PEAV_CancellationTokenState@1pplx@@Uscheduler_ptr@2@@Z`
- size: `318`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x140012328`
- `0x140012420`

## callees

- `0x14001471c`
- `0x140014aac`
- `0x140023bd8`
- `0x140035010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140014b04`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x140014b04`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Concurrency::details::_Task_impl_base::_Task_impl_base(__int64 a1, __int64 a2, __int64 *a3)
{
  __int64 v6; // rbx
  volatile signed __int32 *v7; // rbx
  volatile signed __int32 *v8; // rbx
  __int64 v10; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v11; // [rsp+28h] [rbp-30h]
  __int64 v12; // [rsp+30h] [rbp-28h]

  *(_QWORD *)a1 = &Concurrency::details::_Task_impl_base::`vftable';
  pplx::details::event_impl::event_impl((pplx::details::event_impl *)(a1 + 8));
  *(_DWORD *)(a1 + 16) = 0;
  *(_WORD *)(a1 + 20) = 0;
  *(_BYTE *)(a1 + 22) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)(a1 + 40), 0, 0);
  *(_QWORD *)(a1 + 104) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    &v10,
    a3);
  v12 = a3[2];
  v6 = v12;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    (_QWORD *)(a1 + 128),
    &v10);
  *(_QWORD *)(a1 + 144) = v6;
  v7 = v11;
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  *(_QWORD *)(a1 + 112) = a2;
  if ( a2 != 2 )
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 8));
  v8 = (volatile signed __int32 *)a3[1];
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x140014aac  mov     [rsp+arg_8], rbx
0x140014ab1  mov     [rsp+arg_18], rbp
0x140014ab6  push    rsi
0x140014ab7  push    rdi
0x140014ab8  push    r14
0x140014aba  sub     rsp, 40h
0x140014abe  mov     r14, r8
0x140014ac1  mov     rbp, rdx
0x140014ac4  mov     rsi, rcx
0x140014ac7  lea     rax, ??_7_Task_impl_base@details@Concurrency@@6B@; const Concurrency::details::_Task_impl_base::`vftable'
0x140014ace  mov     [rcx], rax
0x140014ad1  add     rcx, 8; this
0x140014ad5  call    ??0event_impl@details@pplx@@QEAA@XZ; pplx::details::event_impl::event_impl(void)
0x140014ada  mov     dword ptr [rsi+10h], 0
0x140014ae1  mov     word ptr [rsi+14h], 0
0x140014ae7  mov     byte ptr [rsi+16h], 0
0x140014aeb  mov     qword ptr [rsi+18h], 0
0x140014af3  mov     qword ptr [rsi+20h], 0
0x140014afb  lea     rcx, [rsi+28h]; lpCriticalSection
0x140014aff  xor     r8d, r8d; Flags
0x140014b02  xor     edx, edx; dwSpinCount
0x140014b04  call    cs:__imp_InitializeCriticalSectionEx
0x140014b0a  mov     qword ptr [rsi+68h], 0
0x140014b12  mov     qword ptr [rsi+78h], 0
0x140014b1a  lea     rdi, [rsi+80h]
0x140014b21  mov     rdx, r14
0x140014b24  lea     rcx, [rsp+58h+var_38]
0x140014b29  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x140014b2e  mov     rbx, [r14+10h]
0x140014b32  mov     [rsp+58h+var_28], rbx
0x140014b37  lea     rdx, [rsp+58h+var_38]
0x140014b3c  mov     rcx, rdi
0x140014b3f  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x140014b44  mov     [rdi+10h], rbx
0x140014b48  mov     rbx, [rsp+58h+var_30]
0x140014b4d  or      edi, 0FFFFFFFFh
0x140014b50  test    rbx, rbx
0x140014b53  jz      short loc_140014B89
0x140014b55  mov     eax, edi
0x140014b57  lock xadd [rbx+8], eax
0x140014b5c  add     eax, edi
0x140014b5e  jnz     short loc_140014B89
0x140014b60  mov     rax, [rbx]
0x140014b63  mov     rcx, rbx
0x140014b66  mov     rax, [rax]
0x140014b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014b6e  mov     eax, edi
0x140014b70  lock xadd [rbx+0Ch], eax
0x140014b75  add     eax, edi
0x140014b77  jnz     short loc_140014B89
0x140014b79  mov     rax, [rbx]
0x140014b7c  mov     rcx, rbx
0x140014b7f  mov     rax, [rax+8]
0x140014b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014b88  nop
0x140014b89  mov     [rsi+70h], rbp
0x140014b8d  cmp     rbp, 2
0x140014b91  jz      short loc_140014B97
0x140014b93  lock inc dword ptr [rbp+8]
0x140014b97  mov     rbx, [r14+8]
0x140014b9b  test    rbx, rbx
0x140014b9e  jz      short loc_140014BD4
0x140014ba0  mov     eax, edi
0x140014ba2  lock xadd [rbx+8], eax
0x140014ba7  add     eax, edi
0x140014ba9  jnz     short loc_140014BD4
0x140014bab  mov     rax, [rbx]
0x140014bae  mov     rcx, rbx
0x140014bb1  mov     rax, [rax]
0x140014bb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014bb9  mov     edx, edi
0x140014bbb  lock xadd [rbx+0Ch], edx
0x140014bc0  add     edx, edi
0x140014bc2  jnz     short loc_140014BD4
0x140014bc4  mov     rdx, [rbx]
0x140014bc7  mov     rcx, rbx
0x140014bca  mov     rax, [rdx+8]
0x140014bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014bd3  nop
0x140014bd4  mov     rax, rsi
0x140014bd7  mov     rbx, [rsp+58h+arg_8]
0x140014bdc  mov     rbp, [rsp+58h+arg_18]
0x140014be1  add     rsp, 40h
0x140014be5  pop     r14
0x140014be7  pop     rdi
0x140014be8  pop     rsi
0x140014be9  retn
```
