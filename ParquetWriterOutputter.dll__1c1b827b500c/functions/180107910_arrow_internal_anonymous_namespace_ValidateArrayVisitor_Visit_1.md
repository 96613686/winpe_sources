# arrow::internal::_anonymous_namespace_::ValidateArrayVisitor::Visit_1

- ea: `0x180107910`
- end: `0x180107dde`
- name: `arrow::internal::_anonymous_namespace_::ValidateArrayVisitor::Visit_1`
- size: `1230`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1801058e0`

## callees

- `0x18009a010`
- `0x1800a60d0`
- `0x180100b50`
- `0x180105c00`
- `0x180107910`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x180107b7d`: `' has storage array of incompatible type '`
- `0x180107b87`: `Extension array of type '`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall arrow::internal::_anonymous_namespace_::ValidateArrayVisitor::Visit_1(
        __int64 a1,
        __int64 a2,
        _QWORD *a3)
{
  __int64 *v5; // rdi
  volatile signed __int32 *v6; // rbx
  __int64 v7; // rdi
  volatile signed __int32 *v8; // rbx
  const struct arrow::DataType *v9; // rdx
  volatile signed __int32 *v10; // rdi
  __int64 v11; // rcx
  volatile signed __int32 *v12; // r14
  bool v13; // r12
  volatile signed __int32 *v14; // r14
  __int64 *v15; // rcx
  volatile signed __int32 *v16; // r15
  __int64 v17; // rcx
  __int64 *v18; // rdi
  volatile signed __int32 *v19; // r12
  __int64 v20; // rbx
  int v21; // eax
  __int64 v22; // r8
  __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  _BYTE *v25; // rcx
  unsigned __int64 v26; // rdx
  _BYTE *v27; // rcx
  unsigned __int64 v28; // rdx
  _BYTE *v29; // rcx
  volatile signed __int32 *v31; // rbx
  __int64 v33; // [rsp+90h] [rbp-70h]
  _BYTE *v34; // [rsp+B0h] [rbp-50h] BYREF
  __m128i si128; // [rsp+C0h] [rbp-40h]
  _BYTE *v36; // [rsp+D0h] [rbp-30h] BYREF
  __m128i v37; // [rsp+E0h] [rbp-20h]
  _BYTE *v38; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v39; // [rsp+108h] [rbp+8h]

  v5 = (__int64 *)a3[1];
  v6 = (volatile signed __int32 *)v5[1];
  if ( v6 )
  {
    _InterlockedIncrement(v6 + 2);
    v6 = (volatile signed __int32 *)v5[1];
  }
  v7 = *v5;
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  v8 = *(volatile signed __int32 **)(v7 + 64);
  if ( v8 )
  {
    _InterlockedIncrement(v8 + 2);
    v8 = *(volatile signed __int32 **)(v7 + 64);
  }
  v9 = *(const struct arrow::DataType **)(v7 + 56);
  v10 = (volatile signed __int32 *)a3[5];
  if ( v10 )
  {
    _InterlockedIncrement(v10 + 2);
    v10 = (volatile signed __int32 *)a3[5];
  }
  v11 = *(_QWORD *)(a3[4] + 8LL);
  v12 = *(volatile signed __int32 **)(v11 + 8);
  if ( v12 )
  {
    _InterlockedIncrement(v12 + 2);
    v12 = *(volatile signed __int32 **)(v11 + 8);
  }
  v13 = !arrow::DataType::Equals(*(arrow::DataType **)v11, v9, 0);
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  if ( v10 )
  {
    if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  if ( v13 )
  {
    v14 = (volatile signed __int32 *)a3[5];
    if ( v14 )
    {
      _InterlockedIncrement(v14 + 2);
      v14 = (volatile signed __int32 *)a3[5];
    }
    v15 = *(__int64 **)(a3[4] + 8LL);
    v16 = (volatile signed __int32 *)v15[1];
    if ( v16 )
    {
      _InterlockedIncrement(v16 + 2);
      v16 = (volatile signed __int32 *)v15[1];
    }
    v17 = *v15;
    v18 = (__int64 *)a3[1];
    v19 = (volatile signed __int32 *)v18[1];
    if ( v19 )
    {
      _InterlockedIncrement(v19 + 2);
      v19 = (volatile signed __int32 *)v18[1];
    }
    v33 = *v18;
    v20 = (*(__int64 (__fastcall **)(__int64, _BYTE **))(*(_QWORD *)v17 + 24LL))(v17, &v36);
    v21 = (*(__int64 (__fastcall **)(__int64, _BYTE **))(*(_QWORD *)v33 + 24LL))(v33, &v34);
    v22 = arrow::util::StringBuilder<char const (&)[26],std::string,char const (&)[43],std::string,char const (&)[2]>(
            (unsigned int)&v38,
            (unsigned int)"Extension array of type '",
            v21,
            (unsigned int)"' has storage array of incompatible type '",
            v20,
            (__int64)"'");
    LOBYTE(v23) = 4;
    arrow::Status::Status(a2, v23, v22);
    if ( v39 >= 0x10 )
    {
      v24 = v39 + 1;
      v25 = v38;
      if ( v39 + 1 >= 0x1000 )
      {
        v24 = v39 + 40;
        v25 = (_BYTE *)*((_QWORD *)v38 - 1);
        if ( (unsigned __int64)(v38 - v25 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v25, v24);
    }
    if ( si128.m128i_i64[1] >= 0x10uLL )
    {
      v26 = si128.m128i_i64[1] + 1;
      v27 = v34;
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v26 = si128.m128i_i64[1] + 40;
        v27 = (_BYTE *)*((_QWORD *)v34 - 1);
        if ( (unsigned __int64)(v34 - v27 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v27, v26);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v34) = 0;
    if ( v37.m128i_i64[1] >= 0x10uLL )
    {
      v28 = v37.m128i_i64[1] + 1;
      v29 = v36;
      if ( (unsigned __int64)(v37.m128i_i64[1] + 1) >= 0x1000 )
      {
        v28 = v37.m128i_i64[1] + 40;
        v29 = (_BYTE *)*((_QWORD *)v36 - 1);
        if ( (unsigned __int64)(v36 - v29 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v29, v28);
    }
    v37 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v36) = 0;
    if ( v19 )
    {
      if ( _InterlockedExchangeAdd(v19 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v19)(v19);
        if ( _InterlockedExchangeAdd(v19 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v19 + 8LL))(v19);
      }
    }
    if ( v16 )
    {
      if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    if ( v14 && _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
    return a2;
  }
  else
  {
    v31 = (volatile signed __int32 *)a3[5];
    if ( v31 )
    {
      _InterlockedIncrement(v31 + 2);
      v31 = (volatile signed __int32 *)a3[5];
    }
    arrow::internal::ValidateArray(a2);
    if ( v31 )
    {
      if ( _InterlockedExchangeAdd(v31 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
        if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
      }
    }
    return a2;
  }
}

```

## disassembly

```asm
0x180107910  push    rbp
0x180107912  push    rsi
0x180107913  push    rdi
0x180107914  push    r12
0x180107916  push    r13
0x180107918  push    r14
0x18010791a  push    r15
0x18010791c  lea     rbp, [rsp-20h]
0x180107921  sub     rsp, 120h
0x180107928  mov     [rsp+150h+var_108], 0FFFFFFFFFFFFFFFEh
0x180107931  mov     [rsp+150h+arg_0], rbx
0x180107939  mov     rax, cs:__security_cookie
0x180107940  xor     rax, rsp
0x180107943  mov     [rbp+50h+var_40], rax
0x180107947  mov     r13, r8
0x18010794a  mov     r15, rdx
0x18010794d  mov     [rsp+150h+var_120], rdx
0x180107952  mov     [rsp+150h+var_118], rdx
0x180107957  mov     rdi, [r8+8]
0x18010795b  mov     rbx, [rdi+8]
0x18010795f  test    rbx, rbx
0x180107962  jz      short loc_18010796C
0x180107964  lock inc dword ptr [rbx+8]
0x180107968  mov     rbx, [rdi+8]
0x18010796c  mov     rdi, [rdi]
0x18010796f  mov     esi, 0FFFFFFFFh
0x180107974  test    rbx, rbx
0x180107977  jz      short loc_1801079B0
0x180107979  mov     eax, esi
0x18010797b  lock xadd [rbx+8], eax
0x180107980  cmp     eax, 1
0x180107983  jnz     short loc_1801079B0
0x180107985  mov     rax, [rbx]
0x180107988  mov     rcx, rbx
0x18010798b  mov     rax, [rax]
0x18010798e  call    cs:__guard_dispatch_icall_fptr
0x180107994  mov     eax, esi
0x180107996  lock xadd [rbx+0Ch], eax
0x18010799b  cmp     eax, 1
0x18010799e  jnz     short loc_1801079B0
0x1801079a0  mov     rax, [rbx]
0x1801079a3  mov     rcx, rbx
0x1801079a6  mov     rax, [rax+8]
0x1801079aa  call    cs:__guard_dispatch_icall_fptr
0x1801079b0  mov     rbx, [rdi+40h]
0x1801079b4  test    rbx, rbx
0x1801079b7  jz      short loc_1801079C1
0x1801079b9  lock inc dword ptr [rbx+8]
0x1801079bd  mov     rbx, [rdi+40h]
0x1801079c1  mov     rdx, [rdi+38h]; struct arrow::DataType *
0x1801079c5  mov     [rsp+150h+var_118], rdx
0x1801079ca  mov     [rsp+150h+var_110], rbx
0x1801079cf  mov     rdi, [r13+28h]
0x1801079d3  test    rdi, rdi
0x1801079d6  jz      short loc_1801079E0
0x1801079d8  lock inc dword ptr [rdi+8]
0x1801079dc  mov     rdi, [r13+28h]
0x1801079e0  mov     rax, [r13+20h]
0x1801079e4  mov     [rsp+150h+var_100], rax
0x1801079e9  mov     [rsp+150h+var_F8], rdi
0x1801079ee  mov     rcx, [rax+8]
0x1801079f2  mov     r14, [rcx+8]
0x1801079f6  test    r14, r14
0x1801079f9  jz      short loc_180107A04
0x1801079fb  lock inc dword ptr [r14+8]
0x180107a00  mov     r14, [rcx+8]
0x180107a04  mov     rcx, [rcx]; this
0x180107a07  mov     [rsp+150h+var_F0], rcx
0x180107a0c  mov     [rsp+150h+var_E8], r14
0x180107a11  xor     r8d, r8d; bool
0x180107a14  call    ?Equals@DataType@arrow@@QEBA_NAEBV12@_N@Z; arrow::DataType::Equals(arrow::DataType const &,bool)
0x180107a19  test    al, al
0x180107a1b  setz    r12b
0x180107a1f  test    r14, r14
0x180107a22  jz      short loc_180107A5E
0x180107a24  mov     eax, esi
0x180107a26  lock xadd [r14+8], eax
0x180107a2c  cmp     eax, 1
0x180107a2f  jnz     short loc_180107A5E
0x180107a31  mov     rax, [r14]
0x180107a34  mov     rcx, r14
0x180107a37  mov     rax, [rax]
0x180107a3a  call    cs:__guard_dispatch_icall_fptr
0x180107a40  mov     eax, esi
0x180107a42  lock xadd [r14+0Ch], eax
0x180107a48  cmp     eax, 1
0x180107a4b  jnz     short loc_180107A5E
0x180107a4d  mov     rax, [r14]
0x180107a50  mov     rcx, r14
0x180107a53  mov     rax, [rax+8]
0x180107a57  call    cs:__guard_dispatch_icall_fptr
0x180107a5d  nop
0x180107a5e  test    rdi, rdi
0x180107a61  jz      short loc_180107A9B
0x180107a63  mov     eax, esi
0x180107a65  lock xadd [rdi+8], eax
0x180107a6a  cmp     eax, 1
0x180107a6d  jnz     short loc_180107A9B
0x180107a6f  mov     rax, [rdi]
0x180107a72  mov     rcx, rdi
0x180107a75  mov     rax, [rax]
0x180107a78  call    cs:__guard_dispatch_icall_fptr
0x180107a7e  mov     eax, esi
0x180107a80  lock xadd [rdi+0Ch], eax
0x180107a85  cmp     eax, 1
0x180107a88  jnz     short loc_180107A9B
0x180107a8a  mov     rax, [rdi]
0x180107a8d  mov     rcx, rdi
0x180107a90  mov     rax, [rax+8]
0x180107a94  call    cs:__guard_dispatch_icall_fptr
0x180107a9a  nop
0x180107a9b  test    rbx, rbx
0x180107a9e  jz      short loc_180107AD7
0x180107aa0  mov     eax, esi
0x180107aa2  lock xadd [rbx+8], eax
0x180107aa7  cmp     eax, 1
0x180107aaa  jnz     short loc_180107AD7
0x180107aac  mov     rax, [rbx]
0x180107aaf  mov     rcx, rbx
0x180107ab2  mov     rax, [rax]
0x180107ab5  call    cs:__guard_dispatch_icall_fptr
0x180107abb  mov     eax, esi
0x180107abd  lock xadd [rbx+0Ch], eax
0x180107ac2  cmp     eax, 1
0x180107ac5  jnz     short loc_180107AD7
0x180107ac7  mov     rax, [rbx]
0x180107aca  mov     rcx, rbx
0x180107acd  mov     rax, [rax+8]
0x180107ad1  call    cs:__guard_dispatch_icall_fptr
0x180107ad7  test    r12b, r12b
0x180107ada  jz      loc_180107D42
0x180107ae0  mov     r14, [r13+28h]
0x180107ae4  test    r14, r14
0x180107ae7  jz      short loc_180107AF2
0x180107ae9  lock inc dword ptr [r14+8]
0x180107aee  mov     r14, [r13+28h]
0x180107af2  mov     rax, [r13+20h]
0x180107af6  mov     [rsp+150h+var_E0], rax
0x180107afb  mov     [rsp+150h+var_D8], r14
0x180107b00  mov     rcx, [rax+8]
0x180107b04  mov     r15, [rcx+8]
0x180107b08  test    r15, r15
0x180107b0b  jz      short loc_180107B16
0x180107b0d  lock inc dword ptr [r15+8]
0x180107b12  mov     r15, [rcx+8]
0x180107b16  mov     rcx, [rcx]
0x180107b19  mov     [rbp+50h+var_D0], rcx
0x180107b1d  mov     [rbp+50h+var_C8], r15
0x180107b21  mov     rdi, [r13+8]
0x180107b25  mov     r12, [rdi+8]
0x180107b29  test    r12, r12
0x180107b2c  jz      short loc_180107B38
0x180107b2e  lock inc dword ptr [r12+8]
0x180107b34  mov     r12, [rdi+8]
0x180107b38  mov     rdi, [rdi]
0x180107b3b  mov     [rbp+50h+var_C0], rdi
0x180107b3f  mov     [rbp+50h+var_B8], r12
0x180107b43  mov     rax, [rcx]
0x180107b46  lea     rdx, [rbp+50h+var_80]
0x180107b4a  mov     rax, [rax+18h]
0x180107b4e  call    cs:__guard_dispatch_icall_fptr
0x180107b54  mov     rbx, rax
0x180107b57  mov     rax, [rdi]
0x180107b5a  lea     rdx, [rbp+50h+var_A0]
0x180107b5e  mov     rcx, rdi
0x180107b61  mov     rax, [rax+18h]
0x180107b65  call    cs:__guard_dispatch_icall_fptr
0x180107b6b  nop
0x180107b6c  lea     rcx, asc_1803822B8; "'"
0x180107b73  mov     [rsp+150h+var_128], rcx
0x180107b78  mov     [rsp+150h+var_130], rbx
0x180107b7d  lea     r9, aHasStorageArra; "' has storage array of incompatible typ"...
0x180107b84  mov     r8, rax
0x180107b87  lea     rdx, aExtensionArray; "Extension array of type '"
0x180107b8e  lea     rcx, [rbp+50h+var_60]
0x180107b92  call    ??$StringBuilder@AEAY0BK@$$CBDV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0CL@$$CBDV12@AEAY01$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0BK@$$CBD$$QEAV23@AEAY0CL@$$CBD1AEAY01$$CBD@Z; arrow::util::StringBuilder<char const (&)[26],std::string,char const (&)[43],std::string,char const (&)[2]>(char const (&)[26],std::string &&,char const (&)[43],std::string &&,char const (&)[2])
0x180107b97  nop
0x180107b98  mov     r8, rax
0x180107b9b  mov     dl, 4
0x180107b9d  mov     rbx, [rsp+150h+var_120]
0x180107ba2  mov     rcx, rbx
0x180107ba5  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x180107baa  nop
0x180107bab  mov     rdx, [rbp+50h+var_48]
0x180107baf  cmp     rdx, 10h
0x180107bb3  jb      short loc_180107BE7
0x180107bb5  inc     rdx
0x180107bb8  mov     rcx, [rbp+50h+var_60]
0x180107bbc  mov     rax, rcx
0x180107bbf  cmp     rdx, 1000h
0x180107bc6  jb      short loc_180107BE1
0x180107bc8  add     rdx, 27h ; '''; unsigned __int64
0x180107bcc  mov     rcx, [rcx-8]; void *
0x180107bd0  sub     rax, rcx
0x180107bd3  add     rax, 0FFFFFFFFFFFFFFF8h
0x180107bd7  cmp     rax, 1Fh
0x180107bdb  ja      loc_180107DD2
0x180107be1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180107be6  nop
0x180107be7  mov     rdx, [rbp+50h+var_88]
0x180107beb  cmp     rdx, 10h
0x180107bef  jb      short loc_180107C22
0x180107bf1  inc     rdx
0x180107bf4  mov     rcx, [rbp+50h+var_A0]
0x180107bf8  mov     rax, rcx
0x180107bfb  cmp     rdx, 1000h
0x180107c02  jb      short loc_180107C1D
0x180107c04  add     rdx, 27h ; '''; unsigned __int64
0x180107c08  mov     rcx, [rcx-8]; void *
0x180107c0c  sub     rax, rcx
0x180107c0f  add     rax, 0FFFFFFFFFFFFFFF8h
0x180107c13  cmp     rax, 1Fh
0x180107c17  ja      loc_180107DD8
0x180107c1d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180107c22  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180107c2a  movdqu  xmmword ptr [rbp-40h], xmm0
0x180107c2f  mov     byte ptr [rbp+50h+var_A0], 0
0x180107c33  mov     rdx, [rbp+50h+var_68]
0x180107c37  cmp     rdx, 10h
0x180107c3b  jb      short loc_180107C6E
0x180107c3d  inc     rdx
0x180107c40  mov     rcx, [rbp+50h+var_80]
0x180107c44  mov     rax, rcx
0x180107c47  cmp     rdx, 1000h
0x180107c4e  jb      short loc_180107C69
0x180107c50  add     rdx, 27h ; '''; unsigned __int64
0x180107c54  mov     rcx, [rcx-8]; void *
0x180107c58  sub     rax, rcx
0x180107c5b  add     rax, 0FFFFFFFFFFFFFFF8h
0x180107c5f  cmp     rax, 1Fh
0x180107c63  ja      loc_180107DCC
0x180107c69  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180107c6e  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180107c76  movdqu  xmmword ptr [rbp-20h], xmm0
0x180107c7b  mov     byte ptr [rbp+50h+var_80], 0
0x180107c7f  test    r12, r12
0x180107c82  jz      short loc_180107CC2
0x180107c84  mov     eax, esi
0x180107c86  lock xadd [r12+8], eax
0x180107c8d  cmp     eax, 1
0x180107c90  jnz     short loc_180107CC2
0x180107c92  mov     rax, [r12]
0x180107c96  mov     rcx, r12
0x180107c99  mov     rax, [rax]
0x180107c9c  call    cs:__guard_dispatch_icall_fptr
0x180107ca2  mov     eax, esi
0x180107ca4  lock xadd [r12+0Ch], eax
0x180107cab  cmp     eax, 1
0x180107cae  jnz     short loc_180107CC2
0x180107cb0  mov     rax, [r12]
0x180107cb4  mov     rcx, r12
0x180107cb7  mov     rax, [rax+8]
0x180107cbb  call    cs:__guard_dispatch_icall_fptr
0x180107cc1  nop
0x180107cc2  test    r15, r15
0x180107cc5  jz      short loc_180107D01
0x180107cc7  mov     eax, esi
0x180107cc9  lock xadd [r15+8], eax
0x180107ccf  cmp     eax, 1
0x180107cd2  jnz     short loc_180107D01
0x180107cd4  mov     rax, [r15]
0x180107cd7  mov     rcx, r15
0x180107cda  mov     rax, [rax]
0x180107cdd  call    cs:__guard_dispatch_icall_fptr
0x180107ce3  mov     eax, esi
0x180107ce5  lock xadd [r15+0Ch], eax
0x180107ceb  cmp     eax, 1
0x180107cee  jnz     short loc_180107D01
0x180107cf0  mov     rax, [r15]
0x180107cf3  mov     rcx, r15
0x180107cf6  mov     rax, [rax+8]
0x180107cfa  call    cs:__guard_dispatch_icall_fptr
0x180107d00  nop
0x180107d01  test    r14, r14
0x180107d04  jz      short loc_180107D3D
0x180107d06  mov     eax, esi
0x180107d08  lock xadd [r14+8], eax
0x180107d0e  cmp     eax, 1
0x180107d11  jnz     short loc_180107D3D
0x180107d13  mov     rax, [r14]
0x180107d16  mov     rcx, r14
0x180107d19  mov     rax, [rax]
0x180107d1c  call    cs:__guard_dispatch_icall_fptr
0x180107d22  lock xadd [r14+0Ch], esi
0x180107d28  cmp     esi, 1
0x180107d2b  jnz     short loc_180107D3D
0x180107d2d  mov     rdx, [r14]
0x180107d30  mov     rcx, r14
0x180107d33  mov     rax, [rdx+8]
0x180107d37  call    cs:__guard_dispatch_icall_fptr
0x180107d3d  mov     rax, rbx
0x180107d40  jmp     short loc_180107DA5
0x180107d42  mov     rbx, [r13+28h]
0x180107d46  test    rbx, rbx
0x180107d49  jz      short loc_180107D53
0x180107d4b  lock inc dword ptr [rbx+8]
0x180107d4f  mov     rbx, [r13+28h]
0x180107d53  mov     rdx, [r13+20h]
0x180107d57  mov     [rbp+50h+var_B0], rdx
0x180107d5b  mov     [rbp+50h+var_A8], rbx
  ... truncated ...
```
