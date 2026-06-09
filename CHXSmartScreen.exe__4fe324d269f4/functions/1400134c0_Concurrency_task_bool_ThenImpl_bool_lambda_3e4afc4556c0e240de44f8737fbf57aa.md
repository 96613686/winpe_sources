# Concurrency::task_bool_::_ThenImpl_bool__lambda_3e4afc4556c0e240de44f8737fbf57aa___

- ea: `0x1400134c0`
- end: `0x14001377d`
- name: `Concurrency::task_bool_::_ThenImpl_bool__lambda_3e4afc4556c0e240de44f8737fbf57aa___`
- size: `701`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x140013a2c`

## callees

- `0x140003330`
- `0x1400134c0`
- `0x140013784`
- `0x14001471c`
- `0x140015024`
- `0x140035010`

## string_xrefs

- `0x14001375c`: `then() cannot be called on a default constructed task.`

## pseudocode

```c
volatile signed __int32 *__fastcall Concurrency::task_bool_::_ThenImpl_bool__lambda_3e4afc4556c0e240de44f8737fbf57aa___(
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
  Concurrency::task_bool_::_ThenImpl_bool__lambda_3e4afc4556c0e240de44f8737fbf57aa____0(
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
0x1400134c0  push    rbp
0x1400134c2  push    rbx
0x1400134c3  push    rsi
0x1400134c4  push    rdi
0x1400134c5  push    r12
0x1400134c7  push    r13
0x1400134c9  push    r14
0x1400134cb  push    r15
0x1400134cd  lea     rbp, [rsp-18h]
0x1400134d2  sub     rsp, 118h
0x1400134d9  mov     r14, r9
0x1400134dc  mov     [rsp+150h+var_E0], r8
0x1400134e1  mov     r13, rdx
0x1400134e4  mov     rax, rcx
0x1400134e7  mov     [rsp+150h+var_108], rcx
0x1400134ec  mov     [rsp+150h+var_D8], rdx
0x1400134f1  xor     ebx, ebx
0x1400134f3  mov     edi, ebx
0x1400134f5  mov     [rsp+150h+var_110], ebx
0x1400134f9  cmp     [rcx], rbx
0x1400134fc  jz      loc_14001375C
0x140013502  lea     esi, [rbx+2]
0x140013505  cmp     [r9+28h], bl
0x140013509  jz      short loc_140013529
0x14001350b  mov     rcx, [r9+18h]
0x14001350f  test    rcx, rcx
0x140013512  jz      short loc_140013518
0x140013514  lock inc dword ptr [rcx+8]
0x140013518  mov     edi, 1
0x14001351d  mov     r12, rcx
0x140013520  test    rcx, rcx
0x140013523  cmovz   r12, rsi
0x140013527  jmp     short loc_140013531
0x140013529  mov     r12, rbx
0x14001352c  mov     rcx, [rsp+150h+var_D8]
0x140013531  test    dil, 1
0x140013535  jz      short loc_140013561
0x140013537  and     edi, 0FFFFFFFEh
0x14001353a  mov     [rsp+150h+var_110], edi
0x14001353e  test    rcx, rcx
0x140013541  jz      short loc_140013561
0x140013543  or      eax, 0FFFFFFFFh
0x140013546  lock xadd [rcx+8], eax
0x14001354b  cmp     eax, 1
0x14001354e  jnz     short loc_14001355C
0x140013550  mov     rax, [rcx]
0x140013553  mov     rax, [rax+8]
0x140013557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001355c  mov     rax, [rsp+150h+var_108]
0x140013561  cmp     [r14+29h], bl
0x140013565  jz      short loc_140013583
0x140013567  mov     rdx, r14
0x14001356a  lea     rcx, [rbp+50h+var_B8]
0x14001356e  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x140013573  mov     rax, [r14+10h]
0x140013577  mov     [rbp+50h+var_A8], rax
0x14001357b  lea     rcx, [rbp+50h+var_B8]
0x14001357f  or      edi, esi
0x140013581  jmp     short loc_1400135AA
0x140013583  mov     rbx, [rax]
0x140013586  lea     rdx, [rbx+80h]
0x14001358d  lea     rcx, [rbp+50h+var_D0]
0x140013591  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x140013596  mov     rax, [rbx+90h]
0x14001359d  mov     [rbp+50h+var_C0], rax
0x1400135a1  lea     rcx, [rbp+50h+var_D0]
0x1400135a5  or      edi, 4
0x1400135a8  xor     ebx, ebx
0x1400135aa  mov     [rsp+150h+var_110], edi
0x1400135ae  xorps   xmm0, xmm0
0x1400135b1  movdqu  [rsp+150h+var_100], xmm0
0x1400135b7  lea     rax, [rsp+150h+var_100]
0x1400135bc  cmp     rax, rcx
0x1400135bf  jz      short loc_1400135DB
0x1400135c1  mov     rsi, [rcx+8]
0x1400135c5  mov     qword ptr [rsp+150h+var_100+8], rsi
0x1400135ca  mov     [rcx+8], rbx
0x1400135ce  mov     rax, [rcx]
0x1400135d1  mov     qword ptr [rsp+150h+var_100], rax
0x1400135d6  mov     [rcx], rbx
0x1400135d9  jmp     short loc_1400135E0
0x1400135db  mov     rsi, qword ptr [rsp+150h+var_100+8]
0x1400135e0  mov     r15, [rcx+10h]
0x1400135e4  mov     [rsp+150h+var_F0], r15
0x1400135e9  test    dil, 4
0x1400135ed  jz      short loc_140013637
0x1400135ef  and     edi, 0FFFFFFFBh
0x1400135f2  mov     [rsp+150h+var_110], edi
0x1400135f6  mov     rbx, [rbp+50h+var_C8]
0x1400135fa  test    rbx, rbx
0x1400135fd  jz      short loc_140013637
0x1400135ff  or      eax, 0FFFFFFFFh
0x140013602  lock xadd [rbx+8], eax
0x140013607  cmp     eax, 1
0x14001360a  jnz     short loc_140013637
0x14001360c  mov     rax, [rbx]
0x14001360f  mov     rcx, rbx
0x140013612  mov     rax, [rax]
0x140013615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001361a  or      eax, 0FFFFFFFFh
0x14001361d  lock xadd [rbx+0Ch], eax
0x140013622  cmp     eax, 1
0x140013625  jnz     short loc_140013637
0x140013627  mov     rax, [rbx]
0x14001362a  mov     rcx, rbx
0x14001362d  mov     rax, [rax+8]
0x140013631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013636  nop
0x140013637  test    dil, 2
0x14001363b  jz      short loc_140013685
0x14001363d  and     edi, 0FFFFFFFDh
0x140013640  mov     [rsp+150h+var_110], edi
0x140013644  mov     rbx, [rbp+50h+var_B0]
0x140013648  test    rbx, rbx
0x14001364b  jz      short loc_140013685
0x14001364d  or      eax, 0FFFFFFFFh
0x140013650  lock xadd [rbx+8], eax
0x140013655  cmp     eax, 1
0x140013658  jnz     short loc_140013685
0x14001365a  mov     rax, [rbx]
0x14001365d  mov     rcx, rbx
0x140013660  mov     rax, [rax]
0x140013663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013668  or      eax, 0FFFFFFFFh
0x14001366b  lock xadd [rbx+0Ch], eax
0x140013670  cmp     eax, 1
0x140013673  jnz     short loc_140013685
0x140013675  mov     rax, [rbx]
0x140013678  mov     rcx, rbx
0x14001367b  mov     rax, [rax+8]
0x14001367f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013684  nop
0x140013685  lea     rax, [rbp+50h+var_A0]
0x140013689  mov     [rbp+50h+var_88], rax
0x14001368d  lea     rdx, [rsp+150h+var_100]
0x140013692  lea     rcx, [rbp+50h+var_A0]
0x140013696  call    ??0?$shared_ptr@U?$_Task_impl@E@details@Concurrency@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Concurrency::details::_Task_impl<uchar>>::shared_ptr<Concurrency::details::_Task_impl<uchar>>(std::shared_ptr<Concurrency::details::_Task_impl<uchar>> const &)
0x14001369b  mov     [rbp+50h+var_90], r15
0x14001369f  mov     rbx, [r14+20h]
0x1400136a3  mov     [rsp+150h+var_E8], rbx
0x1400136a8  cmp     rbx, 2
0x1400136ac  jb      short loc_1400136BD
0x1400136ae  mov     rax, [rbx]
0x1400136b1  mov     rcx, rbx
0x1400136b4  mov     rax, [rax+8]
0x1400136b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400136bd  or      edi, 10h
0x1400136c0  mov     [rsp+150h+var_110], edi
0x1400136c4  lea     rax, [rbp+50h+var_A0]
0x1400136c8  mov     [rsp+150h+var_128], rax
0x1400136cd  lea     rax, [rsp+150h+var_E8]
0x1400136d2  mov     [rsp+150h+var_130], rax
0x1400136d7  mov     r9, r12
0x1400136da  mov     r8, [rsp+150h+var_E0]
0x1400136df  mov     rdx, r13
0x1400136e2  mov     rcx, [rsp+150h+var_108]
0x1400136e7  call    Concurrency__task_bool____ThenImpl_bool__lambda_3e4afc4556c0e240de44f8737fbf57aa____0
0x1400136ec  or      edi, 8
0x1400136ef  mov     [rsp+150h+var_110], edi
0x1400136f3  cmp     rbx, 2
0x1400136f7  jb      short loc_140013709
0x1400136f9  mov     rax, [rbx]
0x1400136fc  mov     rcx, rbx
0x1400136ff  mov     rax, [rax+10h]
0x140013703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013708  nop
0x140013709  test    rsi, rsi
0x14001370c  jz      short loc_140013745
0x14001370e  or      ebx, 0FFFFFFFFh
0x140013711  mov     eax, ebx
0x140013713  lock xadd [rsi+8], eax
0x140013718  add     eax, ebx
0x14001371a  jnz     short loc_140013745
0x14001371c  mov     rax, [rsi]
0x14001371f  mov     rcx, rsi
0x140013722  mov     rax, [rax]
0x140013725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001372a  mov     edx, ebx
0x14001372c  lock xadd [rsi+0Ch], edx
0x140013731  add     edx, ebx
0x140013733  jnz     short loc_140013745
0x140013735  mov     rdx, [rsi]
0x140013738  mov     rcx, rsi
0x14001373b  mov     rax, [rdx+8]
0x14001373f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013744  nop
0x140013745  mov     rax, r13
0x140013748  add     rsp, 118h
0x14001374f  pop     r15
0x140013751  pop     r14
0x140013753  pop     r13
0x140013755  pop     r12
0x140013757  pop     rdi
0x140013758  pop     rsi
0x140013759  pop     rbx
0x14001375a  pop     rbp
0x14001375b  retn
0x14001375c  lea     rdx, aThenCannotBeCa; "then() cannot be called on a default co"...
0x140013763  lea     rcx, [rbp+50h+pExceptionObject]; this
0x140013767  call    ??0invalid_operation@pplx@@QEAA@PEBD@Z; pplx::invalid_operation::invalid_operation(char const *)
0x14001376c  lea     rdx, _TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x140013773  lea     rcx, [rbp+50h+pExceptionObject]; pExceptionObject
0x140013777  call    _CxxThrowException_0
```
