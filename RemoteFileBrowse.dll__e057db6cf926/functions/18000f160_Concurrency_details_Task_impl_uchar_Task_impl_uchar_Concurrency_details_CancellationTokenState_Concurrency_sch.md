# Concurrency::details::_Task_impl<uchar>::_Task_impl<uchar>(Concurrency::details::_CancellationTokenState *,Concurrency::scheduler_ptr)

- ea: `0x18000f160`
- end: `0x18000f39a`
- name: `??0?$_Task_impl@E@details@Concurrency@@QEAA@PEAV_CancellationTokenState@12@Uscheduler_ptr@2@@Z`
- size: `570`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x18000e664`

## callees

- `0x18000f160`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Concurrency::details::_Task_impl<unsigned char>::_Task_impl<unsigned char>(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rax
  volatile signed __int32 *v7; // rdi
  __int64 v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  volatile signed __int32 *v11; // rdi

  v3 = a3[1];
  if ( v3 )
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 8));
  v7 = (volatile signed __int32 *)a3[1];
  v8 = *a3;
  v9 = a3[2];
  *(_QWORD *)a1 = &Concurrency::details::_Task_impl_base::`vftable';
  *(_QWORD *)(a1 + 16) = 0;
  v10 = (__int64)(v7 + 2);
  *(_QWORD *)(a1 + 24) = 0;
  *(_DWORD *)(a1 + 8) = 0;
  *(_WORD *)(a1 + 12) = 0;
  *(_QWORD *)(a1 + 32) = 2;
  *(_OWORD *)(a1 + 56) = 0;
  *(_OWORD *)(a1 + 72) = 0;
  *(_OWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_DWORD *)(a1 + 104) = -1;
  *(_DWORD *)(a1 + 108) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)v10);
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  *(_OWORD *)(a1 + 152) = 0;
  *(_OWORD *)(a1 + 168) = 0;
  *(_OWORD *)(a1 + 184) = 0;
  *(_QWORD *)(a1 + 200) = 0;
  *(_QWORD *)(a1 + 208) = 2;
  *(_OWORD *)(a1 + 232) = 0;
  *(_OWORD *)(a1 + 248) = 0;
  *(_OWORD *)(a1 + 264) = 0;
  *(_QWORD *)(a1 + 216) = 0;
  *(_QWORD *)(a1 + 224) = 0;
  *(_DWORD *)(a1 + 280) = -1;
  *(_DWORD *)(a1 + 284) = 0;
  *(_QWORD *)(a1 + 288) = 0;
  *(_QWORD *)(a1 + 296) = 0;
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)v10);
  else
    v10 = 8;
  *(_QWORD *)(a1 + 288) = v8;
  *(_QWORD *)(a1 + 296) = v7;
  *(_QWORD *)(a1 + 304) = v9;
  *(_DWORD *)(a1 + 312) = 0;
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v10, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  *(_QWORD *)(a1 + 328) = 0;
  *(_QWORD *)(a1 + 336) = 0;
  *(_QWORD *)(a1 + 344) = 0;
  *(_QWORD *)(a1 + 320) = 0;
  *(_QWORD *)(a1 + 352) = a1;
  *(_WORD *)(a1 + 360) = 0;
  *(_QWORD *)(a1 + 120) = a2;
  if ( a2 != 2 )
    _InterlockedIncrement((volatile signed __int32 *)(a2 + 8));
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  *(_QWORD *)a1 = &Concurrency::details::_Task_impl<unsigned char>::`vftable';
  *(_QWORD *)(a1 + 432) = 0;
  v11 = (volatile signed __int32 *)a3[1];
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18000f160  push    rbx
0x18000f162  push    rbp
0x18000f163  push    rsi
0x18000f164  push    rdi
0x18000f165  push    r14
0x18000f167  push    r15
0x18000f169  sub     rsp, 28h
0x18000f16d  mov     rax, [r8+8]
0x18000f171  xor     ebp, ebp
0x18000f173  mov     r14, r8
0x18000f176  mov     rsi, rdx
0x18000f179  mov     rbx, rcx
0x18000f17c  test    rax, rax
0x18000f17f  jz      short loc_18000F185
0x18000f181  lock inc dword ptr [rax+8]
0x18000f185  mov     rdi, [r8+8]
0x18000f189  lea     rcx, ??_7_Task_impl_base@details@Concurrency@@6B@; const Concurrency::details::_Task_impl_base::`vftable'
0x18000f190  mov     rax, [r8]
0x18000f193  xorps   xmm0, xmm0
0x18000f196  mov     rdx, [r8+10h]
0x18000f19a  or      r15d, 0FFFFFFFFh
0x18000f19e  mov     [rbx], rcx
0x18000f1a1  mov     [rbx+10h], rbp
0x18000f1a5  lea     rcx, [rdi+8]
0x18000f1a9  mov     [rbx+18h], rbp
0x18000f1ad  mov     [rbx+8], ebp
0x18000f1b0  mov     [rbx+0Ch], bp
0x18000f1b4  mov     qword ptr [rbx+20h], 2
0x18000f1bc  movups  xmmword ptr [rbx+38h], xmm0
0x18000f1c0  movups  xmmword ptr [rbx+48h], xmm0
0x18000f1c4  movups  xmmword ptr [rbx+58h], xmm0
0x18000f1c8  mov     [rbx+28h], rbp
0x18000f1cc  mov     [rbx+30h], rbp
0x18000f1d0  mov     [rbx+68h], r15d
0x18000f1d4  mov     [rbx+6Ch], ebp
0x18000f1d7  mov     [rbx+70h], rbp
0x18000f1db  mov     [rbx+80h], rbp
0x18000f1e2  test    rdi, rdi
0x18000f1e5  jz      short loc_18000F1EA
0x18000f1e7  lock inc dword ptr [rcx]
0x18000f1ea  mov     [rbx+88h], rbp
0x18000f1f1  xor     r8d, r8d
0x18000f1f4  mov     [rbx+90h], rbp
0x18000f1fb  movups  xmmword ptr [rbx+98h], xmm0
0x18000f202  movups  xmmword ptr [rbx+0A8h], xmm0
0x18000f209  movups  xmmword ptr [rbx+0B8h], xmm0
0x18000f210  mov     [rbx+0C8h], r8
0x18000f217  mov     qword ptr [rbx+0D0h], 2
0x18000f222  movups  xmmword ptr [rbx+0E8h], xmm0
0x18000f229  movups  xmmword ptr [rbx+0F8h], xmm0
0x18000f230  movups  xmmword ptr [rbx+108h], xmm0
0x18000f237  mov     [rbx+0D8h], rbp
0x18000f23e  mov     [rbx+0E0h], rbp
0x18000f245  mov     [rbx+118h], r15d
0x18000f24c  mov     [rbx+11Ch], ebp
0x18000f252  mov     [rbx+120h], rbp
0x18000f259  mov     [rbx+128h], rbp
0x18000f260  test    rdi, rdi
0x18000f263  jz      short loc_18000F26A
0x18000f265  lock inc dword ptr [rcx]
0x18000f268  jmp     short loc_18000F26F
0x18000f26a  mov     ecx, 8
0x18000f26f  mov     [rbx+120h], rax
0x18000f276  mov     [rbx+128h], rdi
0x18000f27d  mov     [rbx+130h], rdx
0x18000f284  mov     [rbx+138h], ebp
0x18000f28a  test    rdi, rdi
0x18000f28d  jz      short loc_18000F2C5
0x18000f28f  mov     eax, r15d
0x18000f292  lock xadd [rcx], eax
0x18000f296  add     eax, r15d
0x18000f299  jnz     short loc_18000F2C5
0x18000f29b  mov     rax, [rdi]
0x18000f29e  mov     rcx, rdi
0x18000f2a1  mov     rax, [rax]
0x18000f2a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2a9  mov     eax, r15d
0x18000f2ac  lock xadd [rdi+0Ch], eax
0x18000f2b1  add     eax, r15d
0x18000f2b4  jnz     short loc_18000F2C5
0x18000f2b6  mov     rax, [rdi]
0x18000f2b9  mov     rcx, rdi
0x18000f2bc  mov     rax, [rax+8]
0x18000f2c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f2c5  mov     [rbx+148h], rbp
0x18000f2cc  mov     [rbx+150h], rbp
0x18000f2d3  mov     [rbx+158h], rbp
0x18000f2da  mov     [rbx+140h], rbp
0x18000f2e1  mov     [rbx+160h], rbx
0x18000f2e8  mov     [rbx+168h], bp
0x18000f2ef  mov     [rbx+78h], rsi
0x18000f2f3  cmp     rsi, 2
0x18000f2f7  jz      short loc_18000F2FD
0x18000f2f9  lock inc dword ptr [rsi+8]
0x18000f2fd  test    rdi, rdi
0x18000f300  jz      short loc_18000F339
0x18000f302  mov     eax, r15d
0x18000f305  lock xadd [rdi+8], eax
0x18000f30a  add     eax, r15d
0x18000f30d  jnz     short loc_18000F339
0x18000f30f  mov     rax, [rdi]
0x18000f312  mov     rcx, rdi
0x18000f315  mov     rax, [rax]
0x18000f318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f31d  mov     eax, r15d
0x18000f320  lock xadd [rdi+0Ch], eax
0x18000f325  add     eax, r15d
0x18000f328  jnz     short loc_18000F339
0x18000f32a  mov     rax, [rdi]
0x18000f32d  mov     rcx, rdi
0x18000f330  mov     rax, [rax+8]
0x18000f334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f339  lea     rax, ??_7?$_Task_impl@E@details@Concurrency@@6B@; const Concurrency::details::_Task_impl<uchar>::`vftable'
0x18000f340  mov     [rbx], rax
0x18000f343  mov     [rbx+1B0h], rbp
0x18000f34a  mov     rdi, [r14+8]
0x18000f34e  test    rdi, rdi
0x18000f351  jz      short loc_18000F38A
0x18000f353  mov     eax, r15d
0x18000f356  lock xadd [rdi+8], eax
0x18000f35b  add     eax, r15d
0x18000f35e  jnz     short loc_18000F38A
0x18000f360  mov     rax, [rdi]
0x18000f363  mov     rcx, rdi
0x18000f366  mov     rax, [rax]
0x18000f369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f36e  mov     eax, r15d
0x18000f371  lock xadd [rdi+0Ch], eax
0x18000f376  add     eax, r15d
0x18000f379  jnz     short loc_18000F38A
0x18000f37b  mov     rax, [rdi]
0x18000f37e  mov     rcx, rdi
0x18000f381  mov     rax, [rax+8]
0x18000f385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f38a  mov     rax, rbx
0x18000f38d  add     rsp, 28h
0x18000f391  pop     r15
0x18000f393  pop     r14
0x18000f395  pop     rdi
0x18000f396  pop     rsi
0x18000f397  pop     rbp
0x18000f398  pop     rbx
0x18000f399  retn
```
