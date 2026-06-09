# Concurrency::task_unsigned_char_::_ThenImpl_void__lambda_adeb8e53dab3f7987a96779045d09c19___

- ea: `0x140013080`
- end: `0x14001333d`
- name: `Concurrency::task_unsigned_char_::_ThenImpl_void__lambda_adeb8e53dab3f7987a96779045d09c19___`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140013ac0`

## callees

- `0x140003330`
- `0x140013080`
- `0x140013344`
- `0x14001471c`
- `0x140015024`
- `0x140035010`

## string_xrefs

- `0x14001331c`: `then() cannot be called on a default constructed task.`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
volatile signed __int32 *__fastcall Concurrency::task_unsigned_char_::_ThenImpl_void__lambda_adeb8e53dab3f7987a96779045d09c19___(
        Concurrency::details::_Task_impl_base **a1,
        volatile signed __int32 *a2,
        __int64 a3,
        __int64 a4)
{
  Concurrency::details::_Task_impl_base **v6; // rax
  char v7; // di
  volatile signed __int32 *v8; // rcx
  __int64 v9; // r12
  char *v10; // rcx
  char v11; // di
  Concurrency::details::_Task_impl_base *v12; // rbx
  volatile signed __int32 *v13; // rsi
  __int64 v14; // r15
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // rbx
  unsigned __int64 v17; // rbx
  __int128 v20; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v21; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v22; // [rsp+68h] [rbp-98h] BYREF
  __int64 v23; // [rsp+70h] [rbp-90h]
  volatile signed __int32 *v24; // [rsp+78h] [rbp-88h]
  char v25[8]; // [rsp+80h] [rbp-80h] BYREF
  volatile signed __int32 *v26; // [rsp+88h] [rbp-78h]
  __int64 v27; // [rsp+90h] [rbp-70h]
  char v28[8]; // [rsp+98h] [rbp-68h] BYREF
  volatile signed __int32 *v29; // [rsp+A0h] [rbp-60h]
  __int64 v30; // [rsp+A8h] [rbp-58h]
  _BYTE v31[16]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v32; // [rsp+C0h] [rbp-40h]
  _BYTE *v33; // [rsp+C8h] [rbp-38h]
  _BYTE pExceptionObject[128]; // [rsp+D0h] [rbp-30h] BYREF

  v23 = a3;
  v6 = a1;
  v24 = a2;
  v7 = 0;
  if ( !*a1 )
  {
    pplx::invalid_operation::invalid_operation(
      (pplx::invalid_operation *)pExceptionObject,
      "then() cannot be called on a default constructed task.");
    throw (pplx::invalid_operation *)pExceptionObject;
  }
  if ( *(_BYTE *)(a4 + 40) )
  {
    v8 = *(volatile signed __int32 **)(a4 + 24);
    if ( v8 )
      _InterlockedIncrement(v8 + 2);
    v7 = 1;
    v9 = (__int64)v8;
    if ( !v8 )
      v9 = 2;
  }
  else
  {
    v9 = 0;
    v8 = v24;
  }
  if ( (v7 & 1) != 0 )
  {
    v7 &= ~1u;
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      v6 = a1;
    }
  }
  if ( *(_BYTE *)(a4 + 41) )
  {
    std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
      v28,
      a4);
    v30 = *(_QWORD *)(a4 + 16);
    v10 = v28;
    v11 = v7 | 2;
  }
  else
  {
    v12 = *v6;
    std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
      v25,
      (char *)*v6 + 128);
    v27 = *((_QWORD *)v12 + 18);
    v10 = v25;
    v11 = v7 | 4;
  }
  v20 = 0;
  if ( &v20 == (__int128 *)v10 )
  {
    v13 = (volatile signed __int32 *)*((_QWORD *)&v20 + 1);
  }
  else
  {
    v13 = (volatile signed __int32 *)*((_QWORD *)v10 + 1);
    *((_QWORD *)&v20 + 1) = v13;
    *((_QWORD *)v10 + 1) = 0;
    *(_QWORD *)&v20 = *(_QWORD *)v10;
    *(_QWORD *)v10 = 0;
  }
  v14 = *((_QWORD *)v10 + 2);
  v21 = v14;
  if ( (v11 & 4) != 0 )
  {
    v11 &= ~4u;
    v15 = v26;
    if ( v26 )
    {
      if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
  }
  if ( (v11 & 2) != 0 )
  {
    v16 = v29;
    if ( v29 )
    {
      if ( _InterlockedExchangeAdd(v29 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
  }
  v33 = v31;
  std::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>::shared_ptr<Concurrency::details::_Task_impl<unsigned char>>(
    v31,
    &v20);
  v32 = v14;
  v17 = *(_QWORD *)(a4 + 32);
  v22 = v17;
  if ( v17 >= 2 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v17 + 8LL))(v17);
  Concurrency::task_unsigned_char_::_ThenImpl_void__lambda_adeb8e53dab3f7987a96779045d09c19____0(
    a1,
    a2,
    v23,
    v9,
    (__int64)&v22,
    (__int64)v31);
  if ( v17 >= 2 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v17 + 16LL))(v17);
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x140013080  push    rbp
0x140013082  push    rbx
0x140013083  push    rsi
0x140013084  push    rdi
0x140013085  push    r12
0x140013087  push    r13
0x140013089  push    r14
0x14001308b  push    r15
0x14001308d  lea     rbp, [rsp-18h]
0x140013092  sub     rsp, 118h
0x140013099  mov     r14, r9
0x14001309c  mov     [rsp+150h+var_E0], r8
0x1400130a1  mov     r13, rdx
0x1400130a4  mov     rax, rcx
0x1400130a7  mov     [rsp+150h+var_108], rcx
0x1400130ac  mov     [rsp+150h+var_D8], rdx
0x1400130b1  xor     ebx, ebx
0x1400130b3  mov     edi, ebx
0x1400130b5  mov     [rsp+150h+var_110], ebx
0x1400130b9  cmp     [rcx], rbx
0x1400130bc  jz      loc_14001331C
0x1400130c2  lea     esi, [rbx+2]
0x1400130c5  cmp     [r9+28h], bl
0x1400130c9  jz      short loc_1400130E9
0x1400130cb  mov     rcx, [r9+18h]
0x1400130cf  test    rcx, rcx
0x1400130d2  jz      short loc_1400130D8
0x1400130d4  lock inc dword ptr [rcx+8]
0x1400130d8  mov     edi, 1
0x1400130dd  mov     r12, rcx
0x1400130e0  test    rcx, rcx
0x1400130e3  cmovz   r12, rsi
0x1400130e7  jmp     short loc_1400130F1
0x1400130e9  mov     r12, rbx
0x1400130ec  mov     rcx, [rsp+150h+var_D8]
0x1400130f1  test    dil, 1
0x1400130f5  jz      short loc_140013121
0x1400130f7  and     edi, 0FFFFFFFEh
0x1400130fa  mov     [rsp+150h+var_110], edi
0x1400130fe  test    rcx, rcx
0x140013101  jz      short loc_140013121
0x140013103  or      eax, 0FFFFFFFFh
0x140013106  lock xadd [rcx+8], eax
0x14001310b  cmp     eax, 1
0x14001310e  jnz     short loc_14001311C
0x140013110  mov     rax, [rcx]
0x140013113  mov     rax, [rax+8]
0x140013117  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001311c  mov     rax, [rsp+150h+var_108]
0x140013121  cmp     [r14+29h], bl
0x140013125  jz      short loc_140013143
0x140013127  mov     rdx, r14
0x14001312a  lea     rcx, [rbp+50h+var_B8]
0x14001312e  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x140013133  mov     rax, [r14+10h]
0x140013137  mov     [rbp+50h+var_A8], rax
0x14001313b  lea     rcx, [rbp+50h+var_B8]
0x14001313f  or      edi, esi
0x140013141  jmp     short loc_14001316A
0x140013143  mov     rbx, [rax]
0x140013146  lea     rdx, [rbx+80h]
0x14001314d  lea     rcx, [rbp+50h+var_D0]
0x140013151  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x140013156  mov     rax, [rbx+90h]
0x14001315d  mov     [rbp+50h+var_C0], rax
0x140013161  lea     rcx, [rbp+50h+var_D0]
0x140013165  or      edi, 4
0x140013168  xor     ebx, ebx
0x14001316a  mov     [rsp+150h+var_110], edi
0x14001316e  xorps   xmm0, xmm0
0x140013171  movdqu  [rsp+150h+var_100], xmm0
0x140013177  lea     rax, [rsp+150h+var_100]
0x14001317c  cmp     rax, rcx
0x14001317f  jz      short loc_14001319B
0x140013181  mov     rsi, [rcx+8]
0x140013185  mov     qword ptr [rsp+150h+var_100+8], rsi
0x14001318a  mov     [rcx+8], rbx
0x14001318e  mov     rax, [rcx]
0x140013191  mov     qword ptr [rsp+150h+var_100], rax
0x140013196  mov     [rcx], rbx
0x140013199  jmp     short loc_1400131A0
0x14001319b  mov     rsi, qword ptr [rsp+150h+var_100+8]
0x1400131a0  mov     r15, [rcx+10h]
0x1400131a4  mov     [rsp+150h+var_F0], r15
0x1400131a9  test    dil, 4
0x1400131ad  jz      short loc_1400131F7
0x1400131af  and     edi, 0FFFFFFFBh
0x1400131b2  mov     [rsp+150h+var_110], edi
0x1400131b6  mov     rbx, [rbp+50h+var_C8]
0x1400131ba  test    rbx, rbx
0x1400131bd  jz      short loc_1400131F7
0x1400131bf  or      eax, 0FFFFFFFFh
0x1400131c2  lock xadd [rbx+8], eax
0x1400131c7  cmp     eax, 1
0x1400131ca  jnz     short loc_1400131F7
0x1400131cc  mov     rax, [rbx]
0x1400131cf  mov     rcx, rbx
0x1400131d2  mov     rax, [rax]
0x1400131d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400131da  or      eax, 0FFFFFFFFh
0x1400131dd  lock xadd [rbx+0Ch], eax
0x1400131e2  cmp     eax, 1
0x1400131e5  jnz     short loc_1400131F7
0x1400131e7  mov     rax, [rbx]
0x1400131ea  mov     rcx, rbx
0x1400131ed  mov     rax, [rax+8]
0x1400131f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400131f6  nop
0x1400131f7  test    dil, 2
0x1400131fb  jz      short loc_140013245
0x1400131fd  and     edi, 0FFFFFFFDh
0x140013200  mov     [rsp+150h+var_110], edi
0x140013204  mov     rbx, [rbp+50h+var_B0]
0x140013208  test    rbx, rbx
0x14001320b  jz      short loc_140013245
0x14001320d  or      eax, 0FFFFFFFFh
0x140013210  lock xadd [rbx+8], eax
0x140013215  cmp     eax, 1
0x140013218  jnz     short loc_140013245
0x14001321a  mov     rax, [rbx]
0x14001321d  mov     rcx, rbx
0x140013220  mov     rax, [rax]
0x140013223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013228  or      eax, 0FFFFFFFFh
0x14001322b  lock xadd [rbx+0Ch], eax
0x140013230  cmp     eax, 1
0x140013233  jnz     short loc_140013245
0x140013235  mov     rax, [rbx]
0x140013238  mov     rcx, rbx
0x14001323b  mov     rax, [rax+8]
0x14001323f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013244  nop
0x140013245  lea     rax, [rbp+50h+var_A0]
0x140013249  mov     [rbp+50h+var_88], rax
0x14001324d  lea     rdx, [rsp+150h+var_100]
0x140013252  lea     rcx, [rbp+50h+var_A0]
0x140013256  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x14001325b  mov     [rbp+50h+var_90], r15
0x14001325f  mov     rbx, [r14+20h]
0x140013263  mov     [rsp+150h+var_E8], rbx
0x140013268  cmp     rbx, 2
0x14001326c  jb      short loc_14001327D
0x14001326e  mov     rax, [rbx]
0x140013271  mov     rcx, rbx
0x140013274  mov     rax, [rax+8]
0x140013278  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001327d  or      edi, 10h
0x140013280  mov     [rsp+150h+var_110], edi
0x140013284  lea     rax, [rbp+50h+var_A0]
0x140013288  mov     [rsp+150h+var_128], rax
0x14001328d  lea     rax, [rsp+150h+var_E8]
0x140013292  mov     [rsp+150h+var_130], rax
0x140013297  mov     r9, r12
0x14001329a  mov     r8, [rsp+150h+var_E0]
0x14001329f  mov     rdx, r13
0x1400132a2  mov     rcx, [rsp+150h+var_108]
0x1400132a7  call    Concurrency__task_unsigned_char____ThenImpl_void__lambda_adeb8e53dab3f7987a96779045d09c19____0
0x1400132ac  or      edi, 8
0x1400132af  mov     [rsp+150h+var_110], edi
0x1400132b3  cmp     rbx, 2
0x1400132b7  jb      short loc_1400132C9
0x1400132b9  mov     rax, [rbx]
0x1400132bc  mov     rcx, rbx
0x1400132bf  mov     rax, [rax+10h]
0x1400132c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400132c8  nop
0x1400132c9  test    rsi, rsi
0x1400132cc  jz      short loc_140013305
0x1400132ce  or      ebx, 0FFFFFFFFh
0x1400132d1  mov     eax, ebx
0x1400132d3  lock xadd [rsi+8], eax
0x1400132d8  add     eax, ebx
0x1400132da  jnz     short loc_140013305
0x1400132dc  mov     rax, [rsi]
0x1400132df  mov     rcx, rsi
0x1400132e2  mov     rax, [rax]
0x1400132e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400132ea  mov     edx, ebx
0x1400132ec  lock xadd [rsi+0Ch], edx
0x1400132f1  add     edx, ebx
0x1400132f3  jnz     short loc_140013305
0x1400132f5  mov     rdx, [rsi]
0x1400132f8  mov     rcx, rsi
0x1400132fb  mov     rax, [rdx+8]
0x1400132ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013304  nop
0x140013305  mov     rax, r13
0x140013308  add     rsp, 118h
0x14001330f  pop     r15
0x140013311  pop     r14
0x140013313  pop     r13
0x140013315  pop     r12
0x140013317  pop     rdi
0x140013318  pop     rsi
0x140013319  pop     rbx
0x14001331a  pop     rbp
0x14001331b  retn
0x14001331c  lea     rdx, aThenCannotBeCa; "then() cannot be called on a default co"...
0x140013323  lea     rcx, [rbp+50h+pExceptionObject]; this
0x140013327  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x14001332c  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x140013333  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x140013337  call    _CxxThrowException_0
```
