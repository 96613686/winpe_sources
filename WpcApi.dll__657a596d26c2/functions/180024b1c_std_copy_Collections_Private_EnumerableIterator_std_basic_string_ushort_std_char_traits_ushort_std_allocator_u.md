# std::copy<Collections::Private::EnumerableIterator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::back_insert_iterator<std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>(Collections::Private::EnumerableIterator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,Collections::Private::EnumerableIterator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::back_insert_iterator<std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>)

- ea: `0x180024b1c`
- end: `0x180024d70`
- name: `??$copy@V?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@Collections@@V?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@std@@@std@@YA?AV?$back_insert_iterator@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@0@V?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@Collections@@0V10@@Z`
- size: `596`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180025cf4`

## callees

- `0x180005a04`
- `0x180016804`
- `0x180024814`
- `0x180024b1c`
- `0x180024d78`
- `0x18002c010`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall std::copy<Collections::Private::EnumerableIterator<std::wstring>,std::back_insert_iterator<std::vector<std::wstring>>>(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD *v8; // rsi
  _QWORD *i; // rdi
  __int64 v10; // rax
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rdi
  volatile signed __int32 *v13; // rdi
  volatile signed __int32 *v14; // rbx
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // rbx
  volatile signed __int32 *v17; // rbx
  _BYTE v19[8]; // [rsp+28h] [rbp-50h] BYREF
  volatile signed __int32 *v20; // [rsp+30h] [rbp-48h]
  _BYTE v21[8]; // [rsp+38h] [rbp-40h] BYREF
  volatile signed __int32 *v22; // [rsp+40h] [rbp-38h]
  _BYTE v23[16]; // [rsp+48h] [rbp-30h] BYREF
  _BYTE v24[32]; // [rsp+58h] [rbp-20h] BYREF

  Collections::Private::EnumerableIterator<std::wstring>::EnumerableIterator<std::wstring>(v21);
  Collections::Private::EnumerableIterator<std::wstring>::EnumerableIterator<std::wstring>(v19);
  v8 = (_QWORD *)Collections::Private::EnumerableIterator<std::wstring>::EnumerableIterator<std::wstring>(v23);
  for ( i = (_QWORD *)Collections::Private::EnumerableIterator<std::wstring>::EnumerableIterator<std::wstring>(v24);
        *i != *v8;
        Collections::Private::EnumerableIterator<std::wstring>::operator++(i) )
  {
    v10 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*i + 16LL))(*i);
    v11 = *(_QWORD *)(a4 + 8);
    if ( v11 == *(_QWORD *)(a4 + 16) )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(a4, *(_QWORD *)(a4 + 8), v10);
    }
    else
    {
      std::wstring::wstring(v11, v10);
      *(_QWORD *)(a4 + 8) += 32LL;
    }
  }
  v12 = (volatile signed __int32 *)i[1];
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  v13 = (volatile signed __int32 *)v8[1];
  if ( v13 )
  {
    if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  *a1 = a4;
  v14 = v20;
  if ( v20 )
  {
    if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  v15 = v22;
  if ( v22 )
  {
    if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  v16 = *(volatile signed __int32 **)(a2 + 8);
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  v17 = *(volatile signed __int32 **)(a3 + 8);
  if ( v17 )
  {
    if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180024b1c  mov     [rsp-40h+arg_10], r8
0x180024b21  mov     [rsp-40h+arg_8], rdx
0x180024b26  push    rbp
0x180024b27  push    rbx
0x180024b28  push    rsi
0x180024b29  push    rdi
0x180024b2a  push    r12
0x180024b2c  push    r13
0x180024b2e  push    r14
0x180024b30  push    r15
0x180024b32  mov     rbp, rsp
0x180024b35  sub     rsp, 78h
0x180024b39  mov     rbx, r9
0x180024b3c  mov     r13, r8
0x180024b3f  mov     r15, rdx
0x180024b42  mov     r14, rcx
0x180024b45  lea     rcx, [rbp+var_40]
0x180024b49  call    ??0?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@Collections@@QEAA@AEBV012@@Z; Collections::Private::EnumerableIterator<std::wstring>::EnumerableIterator<std::wstring>(Collections::Private::EnumerableIterator<std::wstring> const &)
0x180024b4e  nop
0x180024b4f  mov     rdx, r13
0x180024b52  lea     rcx, [rbp+var_50]
0x180024b56  call    ??0?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@Collections@@QEAA@AEBV012@@Z; Collections::Private::EnumerableIterator<std::wstring>::EnumerableIterator<std::wstring>(Collections::Private::EnumerableIterator<std::wstring> const &)
0x180024b5b  nop
0x180024b5c  lea     rax, [rbp+var_30]
0x180024b60  mov     [rbp+arg_0], rax
0x180024b64  lea     rdx, [rbp+var_50]
0x180024b68  lea     rcx, [rbp+var_30]
0x180024b6c  call    ??0?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@Collections@@QEAA@AEBV012@@Z; Collections::Private::EnumerableIterator<std::wstring>::EnumerableIterator<std::wstring>(Collections::Private::EnumerableIterator<std::wstring> const &)
0x180024b71  mov     rsi, rax
0x180024b74  mov     [rbp+arg_18], rax
0x180024b78  lea     rdx, [rbp+var_40]
0x180024b7c  lea     rcx, [rbp+var_20]
0x180024b80  call    ??0?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@Collections@@QEAA@AEBV012@@Z; Collections::Private::EnumerableIterator<std::wstring>::EnumerableIterator<std::wstring>(Collections::Private::EnumerableIterator<std::wstring> const &)
0x180024b85  mov     rdi, rax
0x180024b88  mov     [rbp+arg_0], rax
0x180024b8c  mov     rcx, [rdi]
0x180024b8f  cmp     rcx, [rsi]
0x180024b92  jz      short loc_180024BD1
0x180024b94  mov     rdx, [rcx]
0x180024b97  mov     rax, [rdx+10h]
0x180024b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ba0  mov     rcx, [rbx+8]
0x180024ba4  cmp     rcx, [rbx+10h]
0x180024ba8  jz      short loc_180024BB9
0x180024baa  mov     rdx, rax
0x180024bad  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180024bb2  add     qword ptr [rbx+8], 20h ; ' '
0x180024bb7  jmp     short loc_180024BC7
0x180024bb9  mov     r8, rax
0x180024bbc  mov     rdx, rcx
0x180024bbf  mov     rcx, rbx
0x180024bc2  call    ??$_Emplace_reallocate@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAPEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@QEAV21@AEBV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring const &>(std::wstring * const,std::wstring const &)
0x180024bc7  mov     rcx, rdi
0x180024bca  call    ??E?$EnumerableIterator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Private@Collections@@QEAAAEAV012@XZ; Collections::Private::EnumerableIterator<std::wstring>::operator++(void)
0x180024bcf  jmp     short loc_180024B8C
0x180024bd1  mov     rdi, [rdi+8]
0x180024bd5  or      r12d, 0FFFFFFFFh
0x180024bd9  test    rdi, rdi
0x180024bdc  jz      short loc_180024C16
0x180024bde  mov     eax, r12d
0x180024be1  lock xadd [rdi+8], eax
0x180024be6  add     eax, r12d
0x180024be9  jnz     short loc_180024C16
0x180024beb  mov     rax, [rdi]
0x180024bee  mov     rcx, rdi
0x180024bf1  mov     rax, [rax]
0x180024bf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024bf9  mov     eax, r12d
0x180024bfc  lock xadd [rdi+0Ch], eax
0x180024c01  add     eax, r12d
0x180024c04  jnz     short loc_180024C16
0x180024c06  mov     rax, [rdi]
0x180024c09  mov     rcx, rdi
0x180024c0c  mov     rax, [rax+8]
0x180024c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c15  nop
0x180024c16  mov     rdi, [rsi+8]
0x180024c1a  test    rdi, rdi
0x180024c1d  jz      short loc_180024C56
0x180024c1f  mov     eax, r12d
0x180024c22  lock xadd [rdi+8], eax
0x180024c27  add     eax, r12d
0x180024c2a  jnz     short loc_180024C56
0x180024c2c  mov     rax, [rdi]
0x180024c2f  mov     rcx, rdi
0x180024c32  mov     rax, [rax]
0x180024c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c3a  mov     eax, r12d
0x180024c3d  lock xadd [rdi+0Ch], eax
0x180024c42  add     eax, r12d
0x180024c45  jnz     short loc_180024C56
0x180024c47  mov     rax, [rdi]
0x180024c4a  mov     rcx, rdi
0x180024c4d  mov     rax, [rax+8]
0x180024c51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c56  mov     [r14], rbx
0x180024c59  mov     rbx, [rbp+var_48]
0x180024c5d  test    rbx, rbx
0x180024c60  jz      short loc_180024C9A
0x180024c62  mov     eax, r12d
0x180024c65  lock xadd [rbx+8], eax
0x180024c6a  add     eax, r12d
0x180024c6d  jnz     short loc_180024C9A
0x180024c6f  mov     rax, [rbx]
0x180024c72  mov     rcx, rbx
0x180024c75  mov     rax, [rax]
0x180024c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c7d  mov     eax, r12d
0x180024c80  lock xadd [rbx+0Ch], eax
0x180024c85  add     eax, r12d
0x180024c88  jnz     short loc_180024C9A
0x180024c8a  mov     rax, [rbx]
0x180024c8d  mov     rcx, rbx
0x180024c90  mov     rax, [rax+8]
0x180024c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c99  nop
0x180024c9a  mov     rbx, [rbp+var_38]
0x180024c9e  test    rbx, rbx
0x180024ca1  jz      short loc_180024CDB
0x180024ca3  mov     eax, r12d
0x180024ca6  lock xadd [rbx+8], eax
0x180024cab  add     eax, r12d
0x180024cae  jnz     short loc_180024CDB
0x180024cb0  mov     rax, [rbx]
0x180024cb3  mov     rcx, rbx
0x180024cb6  mov     rax, [rax]
0x180024cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cbe  mov     eax, r12d
0x180024cc1  lock xadd [rbx+0Ch], eax
0x180024cc6  add     eax, r12d
0x180024cc9  jnz     short loc_180024CDB
0x180024ccb  mov     rax, [rbx]
0x180024cce  mov     rcx, rbx
0x180024cd1  mov     rax, [rax+8]
0x180024cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cda  nop
0x180024cdb  mov     rbx, [r15+8]
0x180024cdf  test    rbx, rbx
0x180024ce2  jz      short loc_180024D1C
0x180024ce4  mov     eax, r12d
0x180024ce7  lock xadd [rbx+8], eax
0x180024cec  add     eax, r12d
0x180024cef  jnz     short loc_180024D1C
0x180024cf1  mov     rax, [rbx]
0x180024cf4  mov     rcx, rbx
0x180024cf7  mov     rax, [rax]
0x180024cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cff  mov     eax, r12d
0x180024d02  lock xadd [rbx+0Ch], eax
0x180024d07  add     eax, r12d
0x180024d0a  jnz     short loc_180024D1C
0x180024d0c  mov     rax, [rbx]
0x180024d0f  mov     rcx, rbx
0x180024d12  mov     rax, [rax+8]
0x180024d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d1b  nop
0x180024d1c  mov     rbx, [r13+8]
0x180024d20  test    rbx, rbx
0x180024d23  jz      short loc_180024D5C
0x180024d25  mov     eax, r12d
0x180024d28  lock xadd [rbx+8], eax
0x180024d2d  add     eax, r12d
0x180024d30  jnz     short loc_180024D5C
0x180024d32  mov     rax, [rbx]
0x180024d35  mov     rcx, rbx
0x180024d38  mov     rax, [rax]
0x180024d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d40  mov     eax, r12d
0x180024d43  lock xadd [rbx+0Ch], eax
0x180024d48  add     eax, r12d
0x180024d4b  jnz     short loc_180024D5C
0x180024d4d  mov     rax, [rbx]
0x180024d50  mov     rcx, rbx
0x180024d53  mov     rax, [rax+8]
0x180024d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d5c  mov     rax, r14
0x180024d5f  add     rsp, 78h
0x180024d63  pop     r15
0x180024d65  pop     r14
0x180024d67  pop     r13
0x180024d69  pop     r12
0x180024d6b  pop     rdi
0x180024d6c  pop     rsi
0x180024d6d  pop     rbx
0x180024d6e  pop     rbp
0x180024d6f  retn
```
