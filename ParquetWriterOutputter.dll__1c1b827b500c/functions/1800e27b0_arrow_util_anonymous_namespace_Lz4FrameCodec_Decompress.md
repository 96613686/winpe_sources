# arrow::util::_anonymous_namespace_::Lz4FrameCodec::Decompress

- ea: `0x1800e27b0`
- end: `0x1800e2dba`
- name: `arrow::util::_anonymous_namespace_::Lz4FrameCodec::Decompress`
- size: `1546`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001d5b0`
- `0x18001f8c0`
- `0x180037220`
- `0x180059010`
- `0x180086ed0`
- `0x18009a010`
- `0x18009a530`
- `0x1800e27b0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x1800e2b5e`: `Lz4 decompression buffer too small`
- `0x1800e2ac1`: `Lz4 compressed input contains less than one frame`
- `0x1800e2c8f`: `Lz4 compressed input contains more than one frame`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall arrow::util::_anonymous_namespace_::Lz4FrameCodec::Decompress(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  const struct arrow::Status *v8; // rax
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // rcx
  arrow::Status::State *v11; // rcx
  volatile signed __int32 *v12; // rbx
  arrow::Status::State *v13; // rcx
  volatile signed __int32 *v14; // rbx
  __int64 v15; // r13
  unsigned __int128 v16; // kr00_16
  __int64 v17; // r12
  __int64 v18; // rsi
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // rdx
  unsigned __int64 v22; // rdx
  _BYTE *v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rdx
  unsigned __int64 v26; // rdx
  _BYTE *v27; // rcx
  __int64 v28; // r8
  __int64 v29; // rdx
  unsigned __int64 v30; // rdx
  _BYTE *v31; // rcx
  volatile signed __int32 *v33; // [rsp+48h] [rbp-B8h]
  char v37[8]; // [rsp+70h] [rbp-90h] BYREF
  arrow::Status::State *v38; // [rsp+78h] [rbp-88h]
  char v39[8]; // [rsp+80h] [rbp-80h] BYREF
  arrow::Status::State *v40; // [rsp+88h] [rbp-78h]
  char v41[8]; // [rsp+90h] [rbp-70h] BYREF
  arrow::Status::State *v42; // [rsp+98h] [rbp-68h]
  char v43[8]; // [rsp+A0h] [rbp-60h] BYREF
  arrow::Status::State *v44; // [rsp+A8h] [rbp-58h]
  char v45[8]; // [rsp+B0h] [rbp-50h] BYREF
  arrow::Status::State *v46; // [rsp+B8h] [rbp-48h]
  __int64 v47; // [rsp+C0h] [rbp-40h]
  char v48[8]; // [rsp+C8h] [rbp-38h] BYREF
  arrow::Status::State *v49; // [rsp+D0h] [rbp-30h]
  unsigned __int128 v50; // [rsp+D8h] [rbp-28h]
  char v51[8]; // [rsp+E8h] [rbp-18h] BYREF
  arrow::Status::State *v52; // [rsp+F0h] [rbp-10h]
  __int128 v53; // [rsp+F8h] [rbp-8h]
  __int64 v54; // [rsp+108h] [rbp+8h]
  char v55[8]; // [rsp+110h] [rbp+10h] BYREF
  arrow::Status::State *v56; // [rsp+118h] [rbp+18h]
  volatile signed __int32 *v57; // [rsp+128h] [rbp+28h]
  _BYTE *v58; // [rsp+130h] [rbp+30h] BYREF
  __m128i si128; // [rsp+140h] [rbp+40h]
  _BYTE *v60; // [rsp+150h] [rbp+50h] BYREF
  __m128i v61; // [rsp+160h] [rbp+60h]
  _BYTE *v62; // [rsp+170h] [rbp+70h] BYREF
  __m128i v63; // [rsp+180h] [rbp+80h]
  char v64[8]; // [rsp+190h] [rbp+90h] BYREF
  arrow::Status::State *v65; // [rsp+198h] [rbp+98h]

  v47 = -2;
  v8 = (const struct arrow::Status *)(*(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)a1 + 40LL))(a1, v55);
  v49 = 0;
  if ( *((_QWORD *)v8 + 1) )
  {
    arrow::Status::CopyFrom((arrow::Status *)v48, v8);
  }
  else
  {
    v49 = 0;
    *((_QWORD *)v8 + 1) = 0;
    v9 = *((_QWORD *)v8 + 2);
    v10 = *((_QWORD *)v8 + 3);
    *((_QWORD *)v8 + 2) = 0;
    *((_QWORD *)v8 + 3) = 0;
    v50 = __PAIR128__(v10, v9);
  }
  v11 = v56;
  if ( v56 )
    goto LABEL_10;
  v12 = v57;
  if ( v57 )
  {
    if ( _InterlockedExchangeAdd(v57 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
    v11 = v56;
    if ( v56 )
    {
LABEL_10:
      arrow::Status::State::`scalar deleting destructor'(v11, 1u);
      v56 = 0;
    }
  }
  arrow::Status::Status((arrow::Status *)v37, (const struct arrow::Status *)v48);
  if ( v38 )
  {
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v37);
    if ( v38 )
    {
      arrow::Status::State::`scalar deleting destructor'(v38, 1u);
      v38 = 0;
    }
LABEL_14:
    v13 = v49;
    if ( v49 )
      goto LABEL_20;
    v14 = (volatile signed __int32 *)*((_QWORD *)&v50 + 1);
    if ( *((_QWORD *)&v50 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v50 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
      v13 = v49;
      if ( v49 )
LABEL_20:
        arrow::Status::State::`scalar deleting destructor'(v13, 1u);
    }
    return a2;
  }
  v15 = v50;
  v16 = v50;
  v33 = (volatile signed __int32 *)*((_QWORD *)&v50 + 1);
  v50 = 0;
  v17 = 0;
  v18 = v16;
  if ( !(*(unsigned __int8 (__fastcall **)(_QWORD))(*(_QWORD *)v16 + 16LL))(v16) )
  {
    while ( 1 )
    {
      if ( !a3 )
        goto LABEL_33;
      v19 = (*(__int64 (__fastcall **)(__int64, char *, __int64, __int64, __int64, __int64))(*(_QWORD *)v18 + 8LL))(
              v18,
              v64,
              a3,
              a4,
              a5,
              a6);
      v52 = 0;
      if ( *(_QWORD *)(v19 + 8) )
      {
        arrow::Status::CopyFrom((arrow::Status *)v51, (const struct arrow::Status *)v19);
      }
      else
      {
        v52 = 0;
        *(_QWORD *)(v19 + 8) = 0;
        v53 = *(_OWORD *)(v19 + 16);
        v54 = *(_QWORD *)(v19 + 32);
      }
      if ( v65 )
      {
        arrow::Status::State::`scalar deleting destructor'(v65, 1u);
        v65 = 0;
      }
      arrow::Status::Status((arrow::Status *)v39, (const struct arrow::Status *)v51);
      if ( v40 )
        break;
      a4 += v53;
      a3 -= v53;
      a6 += *((_QWORD *)&v53 + 1);
      a5 -= *((_QWORD *)&v53 + 1);
      v17 += *((_QWORD *)&v53 + 1);
      if ( (_BYTE)v54 )
      {
        v24 = arrow::util::StringBuilder<char const (&)[13]>(&v58, "Lz4 decompression buffer too small");
        LOBYTE(v25) = 5;
        arrow::Status::Status(v41, v25, v24);
        if ( si128.m128i_i64[1] >= 0x10uLL )
        {
          v26 = si128.m128i_i64[1] + 1;
          v27 = v58;
          if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
          {
            v26 = si128.m128i_i64[1] + 40;
            v27 = (_BYTE *)*((_QWORD *)v58 - 1);
            if ( (unsigned __int64)(v58 - v27 - 8) > 0x1F )
              invalid_parameter_noinfo_noreturn();
          }
          operator delete(v27, v26);
        }
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOBYTE(v58) = 0;
        arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v41);
        if ( v42 )
        {
          arrow::Status::State::`scalar deleting destructor'(v42, 1u);
          v42 = 0;
        }
LABEL_46:
        if ( v52 )
        {
          arrow::Status::State::`scalar deleting destructor'(v52, 1u);
          v52 = 0;
        }
        goto LABEL_48;
      }
      if ( v52 )
        arrow::Status::State::`scalar deleting destructor'(v52, 1u);
      v18 = v15;
      if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15) )
        goto LABEL_33;
    }
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v39);
    if ( v40 )
    {
      arrow::Status::State::`scalar deleting destructor'(v40, 1u);
      v40 = 0;
    }
    goto LABEL_46;
  }
LABEL_33:
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18) )
  {
    v20 = arrow::util::StringBuilder<char const (&)[13]>(&v60, "Lz4 compressed input contains less than one frame");
    LOBYTE(v21) = 5;
    arrow::Status::Status(v43, v21, v20);
    if ( v61.m128i_i64[1] >= 0x10uLL )
    {
      v22 = v61.m128i_i64[1] + 1;
      v23 = v60;
      if ( (unsigned __int64)(v61.m128i_i64[1] + 1) >= 0x1000 )
      {
        v22 = v61.m128i_i64[1] + 40;
        v23 = (_BYTE *)*((_QWORD *)v60 - 1);
        if ( (unsigned __int64)(v60 - v23 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v23, v22);
    }
    v61 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v60) = 0;
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v43);
    if ( v44 )
    {
      arrow::Status::State::`scalar deleting destructor'(v44, 1u);
      v44 = 0;
    }
LABEL_48:
    if ( *((_QWORD *)&v16 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
        if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
      }
    }
    goto LABEL_14;
  }
  if ( a3 )
  {
    v28 = arrow::util::StringBuilder<char const (&)[13]>(&v62, "Lz4 compressed input contains more than one frame");
    LOBYTE(v29) = 5;
    arrow::Status::Status(v45, v29, v28);
    if ( v63.m128i_i64[1] >= 0x10uLL )
    {
      v30 = v63.m128i_i64[1] + 1;
      v31 = v62;
      if ( (unsigned __int64)(v63.m128i_i64[1] + 1) >= 0x1000 )
      {
        v30 = v63.m128i_i64[1] + 40;
        v31 = (_BYTE *)*((_QWORD *)v62 - 1);
        if ( (unsigned __int64)(v62 - v31 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v31, v30);
    }
    v63 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v62) = 0;
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v45);
    if ( v46 )
    {
      arrow::Status::State::`scalar deleting destructor'(v46, 1u);
      v46 = 0;
    }
  }
  else
  {
    *(_QWORD *)(a2 + 8) = 0;
    *(_QWORD *)(a2 + 16) = v17;
  }
  if ( *((_QWORD *)&v16 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
      if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
    }
  }
  arrow::Result<std::shared_ptr<arrow::Scalar>>::~Result<std::shared_ptr<arrow::Scalar>>(v48);
  return a2;
}

```

## disassembly

```asm
0x1800e27b0  push    rbp
0x1800e27b2  push    rbx
0x1800e27b3  push    rsi
0x1800e27b4  push    rdi
0x1800e27b5  push    r12
0x1800e27b7  push    r13
0x1800e27b9  push    r14
0x1800e27bb  push    r15
0x1800e27bd  lea     rbp, [rsp-0C8h]
0x1800e27c5  sub     rsp, 1C8h
0x1800e27cc  mov     [rbp+100h+var_140], 0FFFFFFFFFFFFFFFEh
0x1800e27d4  mov     rax, cs:__security_cookie
0x1800e27db  xor     rax, rsp
0x1800e27de  mov     [rbp+100h+var_48], rax
0x1800e27e5  mov     [rsp+200h+var_1B0], r9
0x1800e27ea  mov     r14, r8
0x1800e27ed  mov     r15, rdx
0x1800e27f0  mov     [rsp+200h+var_198], rdx
0x1800e27f5  mov     rax, [rbp+100h+arg_20]
0x1800e27fc  mov     [rsp+200h+var_1A0], rax
0x1800e2801  mov     rax, [rbp+100h+arg_28]
0x1800e2808  mov     [rsp+200h+var_1A8], rax
0x1800e280d  mov     rax, [rcx]
0x1800e2810  lea     rdx, [rbp+100h+var_F0]
0x1800e2814  mov     rax, [rax+28h]
0x1800e2818  call    cs:__guard_dispatch_icall_fptr
0x1800e281e  nop
0x1800e281f  xor     esi, esi
0x1800e2821  mov     [rbp+100h+var_130], rsi
0x1800e2825  cmp     [rax+8], rsi
0x1800e2829  jnz     short loc_1800E284D
0x1800e282b  mov     [rbp+100h+var_130], rsi
0x1800e282f  mov     [rax+8], rsi
0x1800e2833  mov     rdx, [rax+10h]
0x1800e2837  mov     rcx, [rax+18h]
0x1800e283b  mov     [rax+10h], rsi
0x1800e283f  mov     [rax+18h], rsi
0x1800e2843  mov     qword ptr [rbp+100h+var_128], rdx
0x1800e2847  mov     qword ptr [rbp+100h+var_128+8], rcx
0x1800e284b  jmp     short loc_1800E285A
0x1800e284d  mov     rdx, rax; struct arrow::Status *
0x1800e2850  lea     rcx, [rbp+100h+var_138]; this
0x1800e2854  call    ?CopyFrom@Status@arrow@@AEAAXAEBV12@@Z; arrow::Status::CopyFrom(arrow::Status const &)
0x1800e2859  nop
0x1800e285a  mov     edi, 0FFFFFFFFh
0x1800e285f  mov     rcx, [rbp+100h+var_E8]
0x1800e2863  test    rcx, rcx
0x1800e2866  jnz     short loc_1800E28B1
0x1800e2868  mov     rbx, [rbp+100h+var_D8]
0x1800e286c  test    rbx, rbx
0x1800e286f  jz      short loc_1800E28BF
0x1800e2871  mov     eax, edi
0x1800e2873  lock xadd [rbx+8], eax
0x1800e2878  cmp     eax, 1
0x1800e287b  jnz     short loc_1800E28A8
0x1800e287d  mov     rax, [rbx]
0x1800e2880  mov     rcx, rbx
0x1800e2883  mov     rax, [rax]
0x1800e2886  call    cs:__guard_dispatch_icall_fptr
0x1800e288c  mov     eax, edi
0x1800e288e  lock xadd [rbx+0Ch], eax
0x1800e2893  cmp     eax, 1
0x1800e2896  jnz     short loc_1800E28A8
0x1800e2898  mov     rax, [rbx]
0x1800e289b  mov     rcx, rbx
0x1800e289e  mov     rax, [rax+8]
0x1800e28a2  call    cs:__guard_dispatch_icall_fptr
0x1800e28a8  mov     rcx, [rbp+100h+var_E8]; this
0x1800e28ac  test    rcx, rcx
0x1800e28af  jz      short loc_1800E28BF
0x1800e28b1  mov     edx, 1; unsigned int
0x1800e28b6  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e28bb  mov     [rbp+100h+var_E8], rsi
0x1800e28bf  lea     rdx, [rbp+100h+var_138]; struct arrow::Status *
0x1800e28c3  lea     rcx, [rsp+200h+var_190]; this
0x1800e28c8  call    ??0Status@arrow@@QEAA@AEBV01@@Z; arrow::Status::Status(arrow::Status const &)
0x1800e28cd  nop
0x1800e28ce  cmp     [rsp+200h+var_188], 0
0x1800e28d4  jz      loc_1800E2968
0x1800e28da  lea     rdx, [rsp+200h+var_190]
0x1800e28df  mov     rcx, r15
0x1800e28e2  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e28e7  nop
0x1800e28e8  mov     rcx, [rsp+200h+var_188]; this
0x1800e28ed  test    rcx, rcx
0x1800e28f0  jz      short loc_1800E2901
0x1800e28f2  mov     edx, 1; unsigned int
0x1800e28f7  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e28fc  mov     [rsp+200h+var_188], rsi
0x1800e2901  mov     rcx, [rbp+100h+var_130]
0x1800e2905  test    rcx, rcx
0x1800e2908  jnz     short loc_1800E2959
0x1800e290a  mov     rbx, qword ptr [rbp+100h+var_128+8]
0x1800e290e  test    rbx, rbx
0x1800e2911  jz      loc_1800E2D82
0x1800e2917  mov     eax, edi
0x1800e2919  lock xadd [rbx+8], eax
0x1800e291e  cmp     eax, 1
0x1800e2921  jnz     short loc_1800E294C
0x1800e2923  mov     rax, [rbx]
0x1800e2926  mov     rcx, rbx
0x1800e2929  mov     rax, [rax]
0x1800e292c  call    cs:__guard_dispatch_icall_fptr
0x1800e2932  lock xadd [rbx+0Ch], edi
0x1800e2937  cmp     edi, 1
0x1800e293a  jnz     short loc_1800E294C
0x1800e293c  mov     rax, [rbx]
0x1800e293f  mov     rcx, rbx
0x1800e2942  mov     rax, [rax+8]
0x1800e2946  call    cs:__guard_dispatch_icall_fptr
0x1800e294c  mov     rcx, [rbp+100h+var_130]; this
0x1800e2950  test    rcx, rcx
0x1800e2953  jz      loc_1800E2D82
0x1800e2959  mov     edx, 1; unsigned int
0x1800e295e  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e2963  jmp     loc_1800E2D82
0x1800e2968  mov     r13, qword ptr [rbp+100h+var_128]
0x1800e296c  mov     [rsp+200h+var_1C0], r13
0x1800e2971  mov     rbx, qword ptr [rbp+100h+var_128+8]
0x1800e2975  mov     [rsp+200h+var_1B8], rbx
0x1800e297a  xorps   xmm0, xmm0
0x1800e297d  movdqu  [rbp+100h+var_128], xmm0
0x1800e2982  mov     r12, rsi
0x1800e2985  mov     [rsp+200h+var_198], rsi
0x1800e298a  mov     rsi, r13
0x1800e298d  mov     rax, [r13+0]
0x1800e2991  mov     rcx, r13
0x1800e2994  mov     rax, [rax+10h]
0x1800e2998  call    cs:__guard_dispatch_icall_fptr
0x1800e299e  test    al, al
0x1800e29a0  jnz     loc_1800E2AA9
0x1800e29a6  test    r14, r14
0x1800e29a9  jz      loc_1800E2AA9
0x1800e29af  mov     rax, [rsi]
0x1800e29b2  mov     rcx, [rsp+200h+var_1A8]
0x1800e29b7  mov     [rsp+200h+var_1D8], rcx
0x1800e29bc  mov     rcx, [rsp+200h+var_1A0]
0x1800e29c1  mov     [rsp+200h+var_1E0], rcx
0x1800e29c6  mov     r9, [rsp+200h+var_1B0]
0x1800e29cb  mov     r8, r14
0x1800e29ce  lea     rdx, [rbp+100h+var_70]
0x1800e29d5  mov     rcx, rsi
0x1800e29d8  mov     rax, [rax+8]
0x1800e29dc  call    cs:__guard_dispatch_icall_fptr
0x1800e29e2  nop
0x1800e29e3  xor     esi, esi
0x1800e29e5  mov     [rbp+100h+var_110], rsi
0x1800e29e9  cmp     [rax+8], rsi
0x1800e29ed  jnz     short loc_1800E2A0B
0x1800e29ef  mov     [rbp+100h+var_110], rsi
0x1800e29f3  mov     [rax+8], rsi
0x1800e29f7  movups  xmm0, xmmword ptr [rax+10h]
0x1800e29fb  movups  [rbp+100h+var_108], xmm0
0x1800e29ff  movsd   xmm1, qword ptr [rax+20h]
0x1800e2a04  movsd   [rbp+100h+var_F8], xmm1
0x1800e2a09  jmp     short loc_1800E2A18
0x1800e2a0b  mov     rdx, rax; struct arrow::Status *
0x1800e2a0e  lea     rcx, [rbp+100h+var_118]; this
0x1800e2a12  call    ?CopyFrom@Status@arrow@@AEAAXAEBV12@@Z; arrow::Status::CopyFrom(arrow::Status const &)
0x1800e2a17  nop
0x1800e2a18  mov     rcx, [rbp+100h+var_68]; this
0x1800e2a1f  test    rcx, rcx
0x1800e2a22  jz      short loc_1800E2A35
0x1800e2a24  mov     edx, 1; unsigned int
0x1800e2a29  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e2a2e  mov     [rbp+100h+var_68], rsi
0x1800e2a35  lea     rdx, [rbp+100h+var_118]; struct arrow::Status *
0x1800e2a39  lea     rcx, [rbp+100h+var_180]; this
0x1800e2a3d  call    ??0Status@arrow@@QEAA@AEBV01@@Z; arrow::Status::Status(arrow::Status const &)
0x1800e2a42  nop
0x1800e2a43  cmp     [rbp+100h+var_178], 0
0x1800e2a48  jnz     loc_1800E2C59
0x1800e2a4e  mov     rax, qword ptr [rbp+100h+var_108]
0x1800e2a52  add     [rsp+200h+var_1B0], rax
0x1800e2a57  sub     r14, rax
0x1800e2a5a  mov     rax, qword ptr [rbp+100h+var_108+8]
0x1800e2a5e  add     [rsp+200h+var_1A8], rax
0x1800e2a63  sub     [rsp+200h+var_1A0], rax
0x1800e2a68  add     r12, rax
0x1800e2a6b  mov     [rsp+200h+var_198], r12
0x1800e2a70  cmp     byte ptr [rbp+100h+var_F8], 0
0x1800e2a74  jnz     loc_1800E2B5E
0x1800e2a7a  mov     rcx, [rbp+100h+var_110]; this
0x1800e2a7e  test    rcx, rcx
0x1800e2a81  jz      short loc_1800E2A8D
0x1800e2a83  mov     edx, 1; unsigned int
0x1800e2a88  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e2a8d  mov     rsi, r13
0x1800e2a90  mov     rax, [r13+0]
0x1800e2a94  mov     rcx, r13
0x1800e2a97  mov     rax, [rax+10h]
0x1800e2a9b  call    cs:__guard_dispatch_icall_fptr
0x1800e2aa1  test    al, al
0x1800e2aa3  jz      loc_1800E29A6
0x1800e2aa9  mov     rax, [rsi]
0x1800e2aac  mov     rcx, rsi
0x1800e2aaf  mov     rax, [rax+10h]
0x1800e2ab3  call    cs:__guard_dispatch_icall_fptr
0x1800e2ab9  test    al, al
0x1800e2abb  jnz     loc_1800E2C86
0x1800e2ac1  lea     rdx, aLz4CompressedI; "Lz4 compressed input contains less than"...
0x1800e2ac8  lea     rcx, [rbp+100h+var_B0]
0x1800e2acc  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1800e2ad1  nop
0x1800e2ad2  mov     r8, rax
0x1800e2ad5  mov     dl, 5
0x1800e2ad7  lea     rcx, [rbp+100h+var_160]
0x1800e2adb  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800e2ae0  nop
0x1800e2ae1  mov     rdx, [rbp+100h+var_98]
0x1800e2ae5  cmp     rdx, 10h
0x1800e2ae9  jb      short loc_1800E2B1C
0x1800e2aeb  inc     rdx
0x1800e2aee  mov     rcx, [rbp+100h+var_B0]
0x1800e2af2  mov     rax, rcx
0x1800e2af5  cmp     rdx, 1000h
0x1800e2afc  jb      short loc_1800E2B17
0x1800e2afe  add     rdx, 27h ; '''; unsigned __int64
0x1800e2b02  mov     rcx, [rcx-8]; void *
0x1800e2b06  sub     rax, rcx
0x1800e2b09  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800e2b0d  cmp     rax, 1Fh
0x1800e2b11  ja      loc_1800E2DAE
0x1800e2b17  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e2b1c  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800e2b24  movdqu  xmmword ptr [rbp+60h], xmm0
0x1800e2b29  mov     byte ptr [rbp+100h+var_B0], 0
0x1800e2b2d  lea     rdx, [rbp+100h+var_160]
0x1800e2b31  mov     rcx, r15
0x1800e2b34  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e2b39  nop
0x1800e2b3a  mov     rcx, [rbp+100h+var_158]; this
0x1800e2b3e  test    rcx, rcx
0x1800e2b41  jz      loc_1800E2C05
0x1800e2b47  mov     edx, 1; unsigned int
0x1800e2b4c  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e2b51  mov     [rbp+100h+var_158], 0
0x1800e2b59  jmp     loc_1800E2C05
0x1800e2b5e  lea     rdx, aLz4Decompressi; "Lz4 decompression buffer too small"
0x1800e2b65  lea     rcx, [rbp+100h+var_D0]
0x1800e2b69  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1800e2b6e  nop
0x1800e2b6f  mov     r8, rax
0x1800e2b72  mov     dl, 5
0x1800e2b74  lea     rcx, [rbp+100h+var_170]
0x1800e2b78  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800e2b7d  nop
0x1800e2b7e  mov     rdx, [rbp+100h+var_B8]
0x1800e2b82  cmp     rdx, 10h
0x1800e2b86  jb      short loc_1800E2BB9
0x1800e2b88  inc     rdx
0x1800e2b8b  mov     rcx, [rbp+100h+var_D0]
0x1800e2b8f  mov     rax, rcx
0x1800e2b92  cmp     rdx, 1000h
0x1800e2b99  jb      short loc_1800E2BB4
0x1800e2b9b  add     rdx, 27h ; '''; unsigned __int64
0x1800e2b9f  mov     rcx, [rcx-8]; void *
0x1800e2ba3  sub     rax, rcx
0x1800e2ba6  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800e2baa  cmp     rax, 1Fh
0x1800e2bae  ja      loc_1800E2DB4
0x1800e2bb4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e2bb9  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800e2bc1  movdqu  xmmword ptr [rbp+40h], xmm0
0x1800e2bc6  mov     byte ptr [rbp+100h+var_D0], 0
0x1800e2bca  lea     rdx, [rbp+100h+var_170]
0x1800e2bce  mov     rcx, r15
0x1800e2bd1  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e2bd6  nop
0x1800e2bd7  mov     rcx, [rbp+100h+var_168]; this
0x1800e2bdb  test    rcx, rcx
0x1800e2bde  jz      short loc_1800E2BEE
0x1800e2be0  mov     edx, 1; unsigned int
0x1800e2be5  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e2bea  mov     [rbp+100h+var_168], rsi
0x1800e2bee  mov     rcx, [rbp+100h+var_110]; this
0x1800e2bf2  test    rcx, rcx
0x1800e2bf5  jz      short loc_1800E2C05
0x1800e2bf7  mov     edx, 1; unsigned int
0x1800e2bfc  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e2c01  mov     [rbp+100h+var_110], rsi
0x1800e2c05  test    rbx, rbx
0x1800e2c08  jz      loc_1800E2901
0x1800e2c0e  mov     eax, edi
0x1800e2c10  lock xadd [rbx+8], eax
0x1800e2c15  cmp     eax, 1
0x1800e2c18  jnz     loc_1800E2901
0x1800e2c1e  mov     rbx, [rsp+200h+var_1B8]
0x1800e2c23  mov     rax, [rbx]
0x1800e2c26  mov     rcx, rbx
0x1800e2c29  mov     rax, [rax]
0x1800e2c2c  call    cs:__guard_dispatch_icall_fptr
0x1800e2c32  mov     eax, edi
0x1800e2c34  lock xadd [rbx+0Ch], eax
0x1800e2c39  cmp     eax, 1
0x1800e2c3c  jnz     loc_1800E2901
0x1800e2c42  mov     rcx, [rsp+200h+var_1B8]
0x1800e2c47  mov     rax, [rcx]
0x1800e2c4a  mov     rax, [rax+8]
0x1800e2c4e  call    cs:__guard_dispatch_icall_fptr
  ... truncated ...
```
