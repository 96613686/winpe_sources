# arrow::compute::ExecSetLookup

- ea: `0x18025d060`
- end: `0x18025d875`
- name: `arrow::compute::ExecSetLookup`
- size: `2069`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18025d880`
- `0x18025d9d0`

## callees

- `0x180010860`
- `0x18001b360`
- `0x18001bdb0`
- `0x18001ccf0`
- `0x18001f200`
- `0x18001f8c0`
- `0x180043030`
- `0x1800460f0`
- `0x180059010`
- `0x180086ed0`
- `0x18009a010`
- `0x1800a60e0`
- `0x1800ca2c0`
- `0x1800ca330`
- `0x1800ca470`
- `0x1800ca590`
- `0x1800ccad0`
- `0x1800cdda0`
- `0x1800d3280`
- `0x18025d060`
- `0x18030c180`
- `0x18030c200`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall arrow::compute::ExecSetLookup(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        arrow::Datum *a4,
        char a5,
        __int64 a6)
{
  char v9; // si
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned __int64 v12; // rdx
  _BYTE *v13; // rcx
  __int64 v14; // rbx
  _QWORD *v15; // rax
  bool v16; // r12
  volatile signed __int32 *v17; // rbx
  volatile signed __int32 *v18; // rbx
  __int64 v19; // rbx
  __int64 v20; // rdi
  _QWORD *v21; // rbx
  _QWORD *v22; // rdi
  __int64 v23; // rax
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // r8
  unsigned __int64 v28; // rdx
  _BYTE *v29; // rcx
  unsigned __int64 v30; // rdx
  _BYTE *v31; // rcx
  volatile signed __int32 *v32; // rbx
  volatile signed __int32 *v33; // rbx
  unsigned __int64 v34; // r8
  void *v35; // rdx
  size_t v36; // r8
  __int64 v37; // r8
  __int64 v38; // rdx
  unsigned __int64 v39; // rdx
  _BYTE *v40; // rcx
  unsigned __int64 v41; // rdx
  void *v42; // rcx
  unsigned __int8 v43; // cl
  __int64 v44; // rax
  arrow::Status::State *v45; // rcx
  void *v46; // rcx
  unsigned __int64 v47; // rdx
  unsigned __int8 v49; // [rsp+34h] [rbp-CCh] BYREF
  char v50; // [rsp+35h] [rbp-CBh] BYREF
  char v51; // [rsp+36h] [rbp-CAh] BYREF
  char v52; // [rsp+37h] [rbp-C9h] BYREF
  _BYTE v53[24]; // [rsp+38h] [rbp-C8h] BYREF
  char v54[8]; // [rsp+50h] [rbp-B0h] BYREF
  arrow::Status::State *v55; // [rsp+58h] [rbp-A8h]
  _QWORD v56[3]; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int8 v57; // [rsp+78h] [rbp-88h]
  __int64 v58; // [rsp+80h] [rbp-80h]
  __int64 v59; // [rsp+88h] [rbp-78h]
  _BYTE v60[24]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int8 v61; // [rsp+A8h] [rbp-58h]
  char v62; // [rsp+B0h] [rbp-50h]
  char v63[8]; // [rsp+B8h] [rbp-48h] BYREF
  arrow::Status::State *v64; // [rsp+C0h] [rbp-40h]
  _QWORD v65[3]; // [rsp+C8h] [rbp-38h] BYREF
  char v66; // [rsp+E0h] [rbp-20h]
  _QWORD v67[2]; // [rsp+E8h] [rbp-18h] BYREF
  char v68[8]; // [rsp+F8h] [rbp-8h] BYREF
  volatile signed __int32 *v69; // [rsp+100h] [rbp+0h]
  char v70[8]; // [rsp+108h] [rbp+8h] BYREF
  volatile signed __int32 *v71; // [rsp+110h] [rbp+10h]
  char v72[8]; // [rsp+118h] [rbp+18h] BYREF
  volatile signed __int32 *v73; // [rsp+120h] [rbp+20h]
  char v74[8]; // [rsp+128h] [rbp+28h] BYREF
  volatile signed __int32 *v75; // [rsp+130h] [rbp+30h]
  _BYTE v76[16]; // [rsp+140h] [rbp+40h] BYREF
  char v77[32]; // [rsp+150h] [rbp+50h] BYREF
  void **v78; // [rsp+170h] [rbp+70h]
  void **v79; // [rsp+178h] [rbp+78h]
  _QWORD *v80; // [rsp+190h] [rbp+90h]
  unsigned __int64 *v81; // [rsp+198h] [rbp+98h]
  int *v82; // [rsp+1A8h] [rbp+A8h]
  unsigned __int64 v83; // [rsp+1C0h] [rbp+C0h]
  __int64 v84; // [rsp+1C8h] [rbp+C8h]
  _QWORD v85[2]; // [rsp+240h] [rbp+140h] BYREF
  __m128i v86; // [rsp+250h] [rbp+150h]
  _BYTE *v87; // [rsp+260h] [rbp+160h] BYREF
  __m128i si128; // [rsp+270h] [rbp+170h]
  _BYTE *v89; // [rsp+280h] [rbp+180h] BYREF
  __m128i v90; // [rsp+290h] [rbp+190h]
  _BYTE *v91; // [rsp+2A0h] [rbp+1A0h] BYREF
  __m128i v92; // [rsp+2B0h] [rbp+1B0h]
  _BYTE *v93; // [rsp+2C0h] [rbp+1C0h] BYREF
  __m128i v94; // [rsp+2D0h] [rbp+1D0h]
  char v95; // [rsp+2E0h] [rbp+1E0h] BYREF
  arrow::Status::State *v96; // [rsp+2E8h] [rbp+1E8h]
  char v97[24]; // [rsp+2F0h] [rbp+1F0h] BYREF
  unsigned __int8 v98; // [rsp+308h] [rbp+208h]

  v67[0] = -2;
  v59 = a2;
  v67[1] = a1;
  v58 = a6;
  v9 = 0;
  if ( (unsigned int)arrow::Datum::kind(a4) != 2 && (unsigned int)arrow::Datum::kind(a4) != 3 )
  {
    v10 = arrow::util::StringBuilder<char const (&)[13]>(&v87, "Set lookup value set must be Array or ChunkedArray");
    LOBYTE(v11) = 4;
    arrow::Status::Status(v63, v11, v10);
    if ( si128.m128i_i64[1] >= 0x10uLL )
    {
      v12 = si128.m128i_i64[1] + 1;
      v13 = v87;
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v12 = si128.m128i_i64[1] + 40;
        v13 = (_BYTE *)*((_QWORD *)v87 - 1);
        if ( (unsigned __int64)(v87 - v13 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v13, v12);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v87) = 0;
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a1, v63);
    if ( v64 )
      arrow::Status::State::`scalar deleting destructor'(v64, 1u);
    return a1;
  }
  v16 = 0;
  if ( arrow::Datum::length(a4) > 0 )
  {
    v14 = arrow::Datum::type(a4, v70);
    v15 = (_QWORD *)arrow::Datum::type(a3, v68);
    v9 = 6;
    if ( !(unsigned __int8)arrow::DataType::Equals(*v15, v14) )
      v16 = 1;
  }
  if ( (v9 & 4) != 0 )
  {
    v9 &= ~4u;
    v17 = v69;
    if ( v69 )
    {
      if ( _InterlockedExchangeAdd(v69 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
        if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
      }
    }
  }
  if ( (v9 & 2) != 0 )
  {
    v18 = v71;
    if ( v71 )
    {
      if ( _InterlockedExchangeAdd(v71 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
        if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
      }
    }
  }
  if ( v16 )
  {
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(
      v76,
      3,
      1);
    v19 = *(_QWORD *)arrow::Datum::type(a4, v74);
    v20 = *(_QWORD *)arrow::Datum::type(a3, v72);
    v21 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE **))(*(_QWORD *)v19 + 24LL))(v19, &v91);
    v22 = (_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE **))(*(_QWORD *)v20 + 24LL))(v20, &v89);
    v23 = std::operator<<<std::char_traits<char>>(v77, "Array type didn't match type of values set: ");
    v24 = v22[2];
    if ( v22[3] >= 0x10u )
      v22 = (_QWORD *)*v22;
    v25 = std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v23, v22, v24);
    v26 = std::operator<<<std::char_traits<char>>(v25, " vs ");
    v27 = v21[2];
    if ( v21[3] >= 0x10u )
      v21 = (_QWORD *)*v21;
    std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(v26, v21, v27);
    if ( v90.m128i_i64[1] >= 0x10uLL )
    {
      v28 = v90.m128i_i64[1] + 1;
      v29 = v89;
      if ( (unsigned __int64)(v90.m128i_i64[1] + 1) >= 0x1000 )
      {
        v28 = v90.m128i_i64[1] + 40;
        v29 = (_BYTE *)*((_QWORD *)v89 - 1);
        if ( (unsigned __int64)(v89 - v29 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v29, v28);
    }
    v90 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v89) = 0;
    if ( v92.m128i_i64[1] >= 0x10uLL )
    {
      v30 = v92.m128i_i64[1] + 1;
      v31 = v91;
      if ( (unsigned __int64)(v92.m128i_i64[1] + 1) >= 0x1000 )
      {
        v30 = v92.m128i_i64[1] + 40;
        v31 = (_BYTE *)*((_QWORD *)v91 - 1);
        if ( (unsigned __int64)(v91 - v31 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v31, v30);
    }
    v92 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v91) = 0;
    v32 = v73;
    if ( v73 )
    {
      if ( _InterlockedExchangeAdd(v73 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
        if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
      }
    }
    v33 = v75;
    if ( v75 )
    {
      if ( _InterlockedExchangeAdd(v75 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
        if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
      }
    }
    v86 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v85[0]) = 0;
    if ( (v84 & 2) != 0 || (v34 = *v81) == 0 )
    {
      if ( (v84 & 4) != 0 || !*v80 )
        goto LABEL_53;
      v35 = *v78;
      v36 = *v80 + *v82 - (_QWORD)*v78;
    }
    else
    {
      v35 = *v79;
      if ( v34 < v83 )
        v34 = v83;
      v36 = v34 - (_QWORD)v35;
    }
    std::string::assign(v85, v35, v36);
LABEL_53:
    v37 = arrow::util::StringBuilder<std::string>(&v93, v85);
    LOBYTE(v38) = 4;
    arrow::Status::Status(v54, v38, v37);
    if ( v94.m128i_i64[1] >= 0x10uLL )
    {
      v39 = v94.m128i_i64[1] + 1;
      v40 = v93;
      if ( (unsigned __int64)(v94.m128i_i64[1] + 1) >= 0x1000 )
      {
        v39 = v94.m128i_i64[1] + 40;
        v40 = (_BYTE *)*((_QWORD *)v93 - 1);
        if ( (unsigned __int64)(v93 - v40 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v40, v39);
    }
    v94 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v93) = 0;
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a1, v54);
    if ( v55 )
    {
      arrow::Status::State::`scalar deleting destructor'(v55, 1u);
      v55 = 0;
    }
    if ( v86.m128i_i64[1] >= 0x10uLL )
    {
      v41 = v86.m128i_i64[1] + 1;
      v42 = (void *)v85[0];
      if ( (unsigned __int64)(v86.m128i_i64[1] + 1) >= 0x1000 )
      {
        v41 = v86.m128i_i64[1] + 40;
        v42 = *(void **)(v85[0] - 8LL);
        if ( (unsigned __int64)(v85[0] - (_QWORD)v42 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v42, v41);
    }
    v86 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v85[0]) = 0;
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(v76);
    return a1;
  }
  v56[0] = 0;
  v57 = 0;
  mpark::variant<std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>>::operator=(
    v56,
    a4);
  v60[0] = 0;
  v61 = -1;
  v43 = v57;
  if ( v57 != 0xFF )
  {
    v50 = 0;
    ((void (__fastcall *)(char *, _BYTE *, _QWORD *))mpark::detail::visitation::fdiagonal<_lambda_d7c3167c4daf4a4518bfae687c15ae74_ &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &&>::value[v57])(
      &v50,
      v60,
      v56);
    v43 = v57;
    v61 = v57;
  }
  v62 = a5 ^ 1;
  if ( v43 != 0xFF )
  {
    v51 = 0;
    ((void (__fastcall *)(char *, _QWORD *))*(&mpark::detail::visitation::fmatrix<mpark::detail::dtor &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &>::value
                                            + v43))(
      &v51,
      v56);
  }
  v57 = -1;
  v65[0] = 0;
  v66 = 0;
  mpark::variant<std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>>::operator=(
    v65,
    a3);
  memset(v53, 0, sizeof(v53));
  std::vector<arrow::Datum>::_Range_construct_or_tidy<arrow::Datum const *>(v53, v65, v67, v49);
  v44 = arrow::compute::CallFunction((unsigned int)&v95, v59, (unsigned int)v53, (unsigned int)v60, v58);
  arrow::Result<arrow::Datum>::Result<arrow::Datum>(a1, v44);
  v45 = v96;
  if ( v96 )
    goto LABEL_72;
  if ( v98 != 0xFF )
  {
    v52 = (char)v96;
    ((void (__fastcall *)(char *, char *))*(&mpark::detail::visitation::fmatrix<mpark::detail::dtor &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &>::value
                                          + v98))(
      &v52,
      v97);
    v45 = v96;
  }
  v98 = -1;
  if ( v45 )
  {
LABEL_72:
    arrow::Status::State::`scalar deleting destructor'(v45, 1u);
    v96 = 0;
  }
  if ( *(_QWORD *)v53 )
  {
    std::_Destroy_range<std::allocator<arrow::Datum>>(*(_QWORD *)v53, *(_QWORD *)&v53[8], v53);
    v46 = *(void **)v53;
    v47 = (*(_QWORD *)&v53[16] - *(_QWORD *)v53) & 0xFFFFFFFFFFFFFFE0uLL;
    if ( v47 >= 0x1000 )
    {
      v47 += 39LL;
      v46 = *(void **)(*(_QWORD *)v53 - 8LL);
      if ( (unsigned __int64)(*(_QWORD *)v53 - (_QWORD)v46 - 8LL) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v46, v47);
    memset(v53, 0, sizeof(v53));
  }
  `eh vector destructor iterator'(v65, 0x20u, 1u, (void (*)(void *))arrow::Datum::~Datum);
  if ( v61 != 0xFF )
  {
    v49 = 0;
    ((void (__fastcall *)(unsigned __int8 *, _BYTE *))*(&mpark::detail::visitation::fmatrix<mpark::detail::dtor &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &>::value
                                                      + v61))(
      &v49,
      v60);
  }
  return a1;
}

```

## disassembly

```asm
0x18025d060  push    rbp
0x18025d062  push    rbx
0x18025d063  push    rsi
0x18025d064  push    rdi
0x18025d065  push    r12
0x18025d067  push    r13
0x18025d069  push    r14
0x18025d06b  push    r15
0x18025d06d  lea     rbp, [rsp-228h]
0x18025d075  sub     rsp, 328h
0x18025d07c  mov     [rbp+260h+var_278], 0FFFFFFFFFFFFFFFEh
0x18025d084  mov     rax, cs:__security_cookie
0x18025d08b  xor     rax, rsp
0x18025d08e  mov     [rbp+260h+var_50], rax
0x18025d095  mov     rdi, r9
0x18025d098  mov     r13, r8
0x18025d09b  mov     [rbp+260h+var_2D8], rdx
0x18025d09f  mov     r15, rcx
0x18025d0a2  mov     [rbp+260h+var_270], rcx
0x18025d0a6  mov     rax, [rbp+260h+arg_28]
0x18025d0ad  mov     [rbp+260h+var_2E0], rax
0x18025d0b1  xor     esi, esi
0x18025d0b3  mov     [rsp+360h+var_330], esi
0x18025d0b7  mov     rcx, r9
0x18025d0ba  call    ?kind@Datum@arrow@@QEBA?AW4Kind@12@XZ; arrow::Datum::kind(void)
0x18025d0bf  cmp     eax, 2
0x18025d0c2  jz      loc_18025D185
0x18025d0c8  mov     rcx, rdi
0x18025d0cb  call    ?kind@Datum@arrow@@QEBA?AW4Kind@12@XZ; arrow::Datum::kind(void)
0x18025d0d0  cmp     eax, 3
0x18025d0d3  jz      loc_18025D185
0x18025d0d9  lea     rdx, aSetLookupValue; "Set lookup value set must be Array or C"...
0x18025d0e0  lea     rcx, [rbp+260h+var_100]
0x18025d0e7  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x18025d0ec  nop
0x18025d0ed  mov     r8, rax
0x18025d0f0  mov     dl, 4
0x18025d0f2  lea     rcx, [rbp+260h+var_2A8]
0x18025d0f6  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x18025d0fb  nop
0x18025d0fc  mov     rdx, [rbp+260h+var_E8]
0x18025d103  cmp     rdx, 10h
0x18025d107  jb      short loc_18025D13D
0x18025d109  inc     rdx
0x18025d10c  mov     rcx, [rbp+260h+var_100]
0x18025d113  mov     rax, rcx
0x18025d116  cmp     rdx, 1000h
0x18025d11d  jb      short loc_18025D138
0x18025d11f  add     rdx, 27h ; '''; unsigned __int64
0x18025d123  mov     rcx, [rcx-8]; void *
0x18025d127  sub     rax, rcx
0x18025d12a  add     rax, 0FFFFFFFFFFFFFFF8h
0x18025d12e  cmp     rax, 1Fh
0x18025d132  ja      loc_18025D857
0x18025d138  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18025d13d  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18025d145  movdqu  xmmword ptr [rbp+170h], xmm0
0x18025d14d  mov     byte ptr [rbp+260h+var_100], 0
0x18025d154  mov     [rsp+360h+var_330], 18h
0x18025d15c  lea     rdx, [rbp+260h+var_2A8]
0x18025d160  mov     rcx, r15
0x18025d163  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x18025d168  nop
0x18025d169  mov     rcx, [rbp+260h+var_2A0]; this
0x18025d16d  test    rcx, rcx
0x18025d170  jz      loc_18025D82B
0x18025d176  mov     edx, 1; unsigned int
0x18025d17b  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18025d180  jmp     loc_18025D82B
0x18025d185  mov     rcx, rdi; this
0x18025d188  call    ?length@Datum@arrow@@QEBA_JXZ; arrow::Datum::length(void)
0x18025d18d  test    rax, rax
0x18025d190  jle     short loc_18025D1D3
0x18025d192  lea     rdx, [rbp+260h+var_258]
0x18025d196  mov     rcx, rdi
0x18025d199  call    ?type@Datum@arrow@@QEBA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::Datum::type(void)
0x18025d19e  mov     rbx, rax
0x18025d1a1  mov     [rsp+360h+var_330], 2
0x18025d1a9  lea     rdx, [rbp+260h+var_268]
0x18025d1ad  mov     rcx, r13
0x18025d1b0  call    ?type@Datum@arrow@@QEBA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::Datum::type(void)
0x18025d1b5  nop
0x18025d1b6  mov     esi, 6
0x18025d1bb  mov     [rsp+360h+var_330], esi
0x18025d1bf  mov     rdx, rbx
0x18025d1c2  mov     rcx, [rax]
0x18025d1c5  call    ?Equals@DataType@arrow@@QEBA_NAEBV?$shared_ptr@VDataType@arrow@@@std@@@Z; arrow::DataType::Equals(std::shared_ptr<arrow::DataType> const &)
0x18025d1ca  test    al, al
0x18025d1cc  jnz     short loc_18025D1D3
0x18025d1ce  mov     r12b, 1
0x18025d1d1  jmp     short loc_18025D1D6
0x18025d1d3  xor     r12b, r12b
0x18025d1d6  mov     r14d, 0FFFFFFFFh
0x18025d1dc  test    sil, 4
0x18025d1e0  jz      short loc_18025D22F
0x18025d1e2  and     esi, 0FFFFFFFBh
0x18025d1e5  mov     [rsp+360h+var_330], esi
0x18025d1e9  mov     rbx, [rbp+260h+var_260]
0x18025d1ed  test    rbx, rbx
0x18025d1f0  jz      short loc_18025D22F
0x18025d1f2  mov     eax, r14d
0x18025d1f5  lock xadd [rbx+8], eax
0x18025d1fa  cmp     eax, 1
0x18025d1fd  jnz     short loc_18025D22B
0x18025d1ff  mov     rax, [rbx]
0x18025d202  mov     rcx, rbx
0x18025d205  mov     rax, [rax]
0x18025d208  call    cs:__guard_dispatch_icall_fptr
0x18025d20e  mov     eax, r14d
0x18025d211  lock xadd [rbx+0Ch], eax
0x18025d216  cmp     eax, 1
0x18025d219  jnz     short loc_18025D22B
0x18025d21b  mov     rax, [rbx]
0x18025d21e  mov     rcx, rbx
0x18025d221  mov     rax, [rax+8]
0x18025d225  call    cs:__guard_dispatch_icall_fptr
0x18025d22b  mov     esi, [rsp+360h+var_330]
0x18025d22f  test    sil, 2
0x18025d233  jz      short loc_18025D282
0x18025d235  and     esi, 0FFFFFFFDh
0x18025d238  mov     [rsp+360h+var_330], esi
0x18025d23c  mov     rbx, [rbp+260h+var_250]
0x18025d240  test    rbx, rbx
0x18025d243  jz      short loc_18025D282
0x18025d245  mov     eax, r14d
0x18025d248  lock xadd [rbx+8], eax
0x18025d24d  cmp     eax, 1
0x18025d250  jnz     short loc_18025D27E
0x18025d252  mov     rax, [rbx]
0x18025d255  mov     rcx, rbx
0x18025d258  mov     rax, [rax]
0x18025d25b  call    cs:__guard_dispatch_icall_fptr
0x18025d261  mov     eax, r14d
0x18025d264  lock xadd [rbx+0Ch], eax
0x18025d269  cmp     eax, 1
0x18025d26c  jnz     short loc_18025D27E
0x18025d26e  mov     rax, [rbx]
0x18025d271  mov     rcx, rbx
0x18025d274  mov     rax, [rax+8]
0x18025d278  call    cs:__guard_dispatch_icall_fptr
0x18025d27e  mov     esi, [rsp+360h+var_330]
0x18025d282  test    r12b, r12b
0x18025d285  jz      loc_18025D62D
0x18025d28b  mov     edx, 3
0x18025d290  lea     r8d, [rdx-2]
0x18025d294  lea     rcx, [rbp+260h+var_220]
0x18025d298  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@H@Z; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(int)
0x18025d29d  nop
0x18025d29e  lea     rdx, [rbp+260h+var_238]
0x18025d2a2  mov     rcx, rdi
0x18025d2a5  call    ?type@Datum@arrow@@QEBA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::Datum::type(void)
0x18025d2aa  nop
0x18025d2ab  mov     rbx, [rax]
0x18025d2ae  lea     rdx, [rbp+260h+var_248]
0x18025d2b2  mov     rcx, r13
0x18025d2b5  call    ?type@Datum@arrow@@QEBA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::Datum::type(void)
0x18025d2ba  nop
0x18025d2bb  mov     rdi, [rax]
0x18025d2be  mov     rax, [rbx]
0x18025d2c1  lea     rdx, [rbp+260h+var_C0]
0x18025d2c8  mov     rcx, rbx
0x18025d2cb  mov     rax, [rax+18h]
0x18025d2cf  call    cs:__guard_dispatch_icall_fptr
0x18025d2d5  mov     rbx, rax
0x18025d2d8  mov     rax, [rdi]
0x18025d2db  lea     rdx, [rbp+260h+var_E0]
0x18025d2e2  mov     rcx, rdi
0x18025d2e5  mov     rax, [rax+18h]
0x18025d2e9  call    cs:__guard_dispatch_icall_fptr
0x18025d2ef  mov     rdi, rax
0x18025d2f2  lea     rdx, aArrayTypeDidnT; "Array type didn't match type of values "...
0x18025d2f9  lea     rcx, [rbp+260h+var_210]
0x18025d2fd  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18025d302  mov     r8, [rdi+10h]
0x18025d306  cmp     qword ptr [rdi+18h], 10h
0x18025d30b  jb      short loc_18025D310
0x18025d30d  mov     rdi, [rdi]
0x18025d310  mov     rdx, rdi
0x18025d313  mov     rcx, rax
0x18025d316  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18025d31b  lea     rdx, aVs; " vs "
0x18025d322  mov     rcx, rax
0x18025d325  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18025d32a  mov     r8, [rbx+10h]
0x18025d32e  cmp     qword ptr [rbx+18h], 10h
0x18025d333  jb      short loc_18025D338
0x18025d335  mov     rbx, [rbx]
0x18025d338  mov     rdx, rbx
0x18025d33b  mov     rcx, rax
0x18025d33e  call    ??$_Insert_string@DU?$char_traits@D@std@@_K@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@QEBD_K@Z; std::_Insert_string<char,std::char_traits<char>,unsigned __int64>(std::ostream &,char const * const,unsigned __int64)
0x18025d343  nop
0x18025d344  mov     rdx, [rbp+260h+var_C8]
0x18025d34b  cmp     rdx, 10h
0x18025d34f  jb      short loc_18025D385
0x18025d351  inc     rdx
0x18025d354  mov     rcx, [rbp+260h+var_E0]
0x18025d35b  mov     rax, rcx
0x18025d35e  cmp     rdx, 1000h
0x18025d365  jb      short loc_18025D380
0x18025d367  add     rdx, 27h ; '''; unsigned __int64
0x18025d36b  mov     rcx, [rcx-8]; void *
0x18025d36f  sub     rax, rcx
0x18025d372  add     rax, 0FFFFFFFFFFFFFFF8h
0x18025d376  cmp     rax, 1Fh
0x18025d37a  ja      loc_18025D85D
0x18025d380  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18025d385  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18025d38d  movdqu  xmmword ptr [rbp+190h], xmm0
0x18025d395  mov     byte ptr [rbp+260h+var_E0], 0
0x18025d39c  mov     rdx, [rbp+260h+var_A8]
0x18025d3a3  cmp     rdx, 10h
0x18025d3a7  jb      short loc_18025D3DD
0x18025d3a9  inc     rdx
0x18025d3ac  mov     rcx, [rbp+260h+var_C0]
0x18025d3b3  mov     rax, rcx
0x18025d3b6  cmp     rdx, 1000h
0x18025d3bd  jb      short loc_18025D3D8
0x18025d3bf  add     rdx, 27h ; '''; unsigned __int64
0x18025d3c3  mov     rcx, [rcx-8]; void *
0x18025d3c7  sub     rax, rcx
0x18025d3ca  add     rax, 0FFFFFFFFFFFFFFF8h
0x18025d3ce  cmp     rax, 1Fh
0x18025d3d2  ja      loc_18025D863
0x18025d3d8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18025d3dd  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18025d3e5  movdqu  xmmword ptr [rbp+1B0h], xmm0
0x18025d3ed  mov     byte ptr [rbp+260h+var_C0], 0
0x18025d3f4  mov     rbx, [rbp+260h+var_240]
0x18025d3f8  test    rbx, rbx
0x18025d3fb  jz      short loc_18025D43A
0x18025d3fd  mov     eax, r14d
0x18025d400  lock xadd [rbx+8], eax
0x18025d405  cmp     eax, 1
0x18025d408  jnz     short loc_18025D436
0x18025d40a  mov     rax, [rbx]
0x18025d40d  mov     rcx, rbx
0x18025d410  mov     rax, [rax]
0x18025d413  call    cs:__guard_dispatch_icall_fptr
0x18025d419  mov     eax, r14d
0x18025d41c  lock xadd [rbx+0Ch], eax
0x18025d421  cmp     eax, 1
0x18025d424  jnz     short loc_18025D436
0x18025d426  mov     rax, [rbx]
0x18025d429  mov     rcx, rbx
0x18025d42c  mov     rax, [rax+8]
0x18025d430  call    cs:__guard_dispatch_icall_fptr
0x18025d436  mov     esi, [rsp+360h+var_330]
0x18025d43a  mov     rbx, [rbp+260h+var_230]
0x18025d43e  test    rbx, rbx
0x18025d441  jz      short loc_18025D47F
0x18025d443  mov     eax, r14d
0x18025d446  lock xadd [rbx+8], eax
0x18025d44b  cmp     eax, 1
0x18025d44e  jnz     short loc_18025D47B
0x18025d450  mov     rax, [rbx]
0x18025d453  mov     rcx, rbx
0x18025d456  mov     rax, [rax]
0x18025d459  call    cs:__guard_dispatch_icall_fptr
0x18025d45f  lock xadd [rbx+0Ch], r14d
0x18025d465  cmp     r14d, 1
0x18025d469  jnz     short loc_18025D47B
0x18025d46b  mov     rax, [rbx]
0x18025d46e  mov     rcx, rbx
0x18025d471  mov     rax, [rax+8]
0x18025d475  call    cs:__guard_dispatch_icall_fptr
0x18025d47b  mov     esi, [rsp+360h+var_330]
0x18025d47f  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18025d487  movdqu  [rbp+260h+var_110], xmm0
0x18025d48f  mov     byte ptr [rbp+260h+var_120], 0
0x18025d496  or      esi, 40h
0x18025d499  mov     [rsp+360h+var_330], esi
0x18025d49d  mov     rcx, [rbp+260h+var_198]
0x18025d4a4  test    cl, 2
0x18025d4a7  jnz     short loc_18025D4D3
0x18025d4a9  mov     rax, [rbp+260h+var_1C8]
0x18025d4b0  mov     r8, [rax]
0x18025d4b3  test    r8, r8
0x18025d4b6  jz      short loc_18025D4D3
0x18025d4b8  mov     rax, [rbp+260h+var_1E8]
0x18025d4bc  mov     rdx, [rax]
0x18025d4bf  cmp     r8, [rbp+260h+var_1A0]
0x18025d4c6  cmovb   r8, [rbp+260h+var_1A0]
0x18025d4ce  sub     r8, rdx
0x18025d4d1  jmp     short loc_18025D4FE
0x18025d4d3  test    cl, 4
0x18025d4d6  jnz     short loc_18025D50A
0x18025d4d8  mov     rax, [rbp+260h+var_1D0]
0x18025d4df  mov     rcx, [rax]
0x18025d4e2  test    rcx, rcx
0x18025d4e5  jz      short loc_18025D50A
0x18025d4e7  mov     rax, [rbp+260h+var_1F0]
0x18025d4eb  mov     rdx, [rax]; Src
0x18025d4ee  mov     rax, [rbp+260h+var_1B8]
0x18025d4f5  movsxd  r8, dword ptr [rax]
0x18025d4f8  sub     r8, rdx
0x18025d4fb  add     r8, rcx; Size
0x18025d4fe  lea     rcx, [rbp+260h+var_120]; void *
0x18025d505  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x18025d50a  and     esi, 0FFFFFFBFh
0x18025d50d  mov     ebx, esi
  ... truncated ...
```
