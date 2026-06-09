# arrow::compute::internal::UnpackDictionary(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *)

- ea: `0x180257d30`
- end: `0x180258251`
- name: `?UnpackDictionary@internal@compute@arrow@@YAXPEAVKernelContext@23@AEBUExecBatch@23@PEAUDatum@3@@Z`
- size: `1313`
- prototype: `void __fastcall(arrow::compute::internal *__hidden this, struct arrow::compute::KernelContext *, const struct arrow::compute::ExecBatch *, struct arrow::Datum *)`
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180010640`
- `0x18001e1f0`
- `0x18001f8c0`
- `0x1800491d0`
- `0x180049340`
- `0x18009a010`
- `0x18009a530`
- `0x1800a60e0`
- `0x1800aaf30`
- `0x1800c5350`
- `0x1800c9580`
- `0x1800c9640`
- `0x1800c9770`
- `0x1800ccad0`
- `0x180125360`
- `0x180128400`
- `0x180257d30`
- `0x18025dd50`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x180257e89`: ` incompatible with dictionary type `

## pseudocode

```c
// Hidden C++ exception states: #wind=21
void __fastcall arrow::compute::internal::UnpackDictionary(
        arrow::compute::internal *this,
        struct arrow::compute::KernelContext *a2,
        const struct arrow::compute::ExecBatch *a3,
        struct arrow::Datum *a4)
{
  __int64 v6; // rdx
  __int64 v7; // r15
  __int64 *v8; // rax
  volatile signed __int32 *v9; // rbx
  __int64 v10; // rsi
  volatile signed __int32 *v11; // rbx
  __int64 v12; // rdi
  __int64 v13; // rbx
  int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  _BYTE *v18; // rcx
  unsigned __int64 v19; // rdx
  _BYTE *v20; // rcx
  unsigned __int64 v21; // rdx
  _BYTE *v22; // rcx
  __int64 v23; // rdx
  int v24; // ebx
  __int64 v25; // rdx
  int v26; // eax
  __int64 v27; // rcx
  const struct arrow::Status *v28; // rax
  _QWORD *v29; // rsi
  unsigned __int8 v30; // al
  unsigned __int8 v31; // cl
  arrow::Status::State *v32; // rcx
  volatile signed __int32 *v33; // rbx
  char v34; // [rsp+30h] [rbp-D0h] BYREF
  char v35; // [rsp+31h] [rbp-CFh] BYREF
  char v36; // [rsp+32h] [rbp-CEh] BYREF
  char v37; // [rsp+33h] [rbp-CDh] BYREF
  char v38; // [rsp+34h] [rbp-CCh] BYREF
  char v39[3]; // [rsp+35h] [rbp-CBh] BYREF
  char v40[8]; // [rsp+38h] [rbp-C8h] BYREF
  arrow::Status::State *v41; // [rsp+40h] [rbp-C0h]
  _BYTE v42[24]; // [rsp+48h] [rbp-B8h] BYREF
  char v43; // [rsp+60h] [rbp-A0h]
  __int64 v44; // [rsp+68h] [rbp-98h]
  char v45[8]; // [rsp+70h] [rbp-90h] BYREF
  volatile signed __int32 *v46; // [rsp+78h] [rbp-88h]
  char v47[8]; // [rsp+80h] [rbp-80h] BYREF
  volatile signed __int32 *v48; // [rsp+88h] [rbp-78h]
  char v49[8]; // [rsp+90h] [rbp-70h] BYREF
  std::_Ref_count_base *v50; // [rsp+98h] [rbp-68h]
  _BYTE v51[24]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int8 v52; // [rsp+B8h] [rbp-48h]
  char v53[8]; // [rsp+C0h] [rbp-40h] BYREF
  char v54[32]; // [rsp+C8h] [rbp-38h] BYREF
  char v55[16]; // [rsp+E8h] [rbp-18h] BYREF
  char v56[24]; // [rsp+F8h] [rbp-8h] BYREF
  _BYTE v57[32]; // [rsp+110h] [rbp+10h] BYREF
  char v58[8]; // [rsp+130h] [rbp+30h] BYREF
  __int64 v59; // [rsp+138h] [rbp+38h]
  _BYTE v60[24]; // [rsp+140h] [rbp+40h] BYREF
  char v61; // [rsp+158h] [rbp+58h]
  _BYTE *v62; // [rsp+160h] [rbp+60h] BYREF
  __m128i si128; // [rsp+170h] [rbp+70h]
  _BYTE *v64; // [rsp+180h] [rbp+80h] BYREF
  __m128i v65; // [rsp+190h] [rbp+90h]
  char v66; // [rsp+1A0h] [rbp+A0h] BYREF
  arrow::Status::State *v67; // [rsp+1A8h] [rbp+A8h]
  char v68[24]; // [rsp+1B0h] [rbp+B0h] BYREF
  unsigned __int8 v69; // [rsp+1C8h] [rbp+C8h]
  _BYTE *v70; // [rsp+1D0h] [rbp+D0h] BYREF
  unsigned __int64 v71; // [rsp+1E8h] [rbp+E8h]

  v44 = -2;
  v6 = *(_QWORD *)a2;
  if ( *(_BYTE *)(v6 + 24) != 2 )
    mpark::throw_bad_variant_access(this);
  arrow::DictionaryArray::DictionaryArray(v53, v6, a3, a4);
  v7 = *((_QWORD *)this + 3);
  v8 = *(__int64 **)(*(_QWORD *)arrow::DictionaryArray::dictionary(v53, v45) + 8LL);
  v9 = (volatile signed __int32 *)v8[1];
  if ( v9 )
  {
    _InterlockedIncrement(v9 + 2);
    v9 = (volatile signed __int32 *)v8[1];
  }
  v10 = *v8;
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  v11 = v46;
  if ( v46 )
  {
    if ( _InterlockedExchangeAdd(v46 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
      if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    }
  }
  if ( (unsigned __int8)arrow::DataType::Equals(v10, v7 + 8) )
  {
    v23 = arrow::DictionaryArray::indices(v53, v49);
    v24 = arrow::Datum::Datum(v57, v23);
    v25 = arrow::DictionaryArray::dictionary(v53, v47);
    v26 = arrow::Datum::Datum(v51, v25);
    v27 = *(_QWORD *)this;
    v34 = 1;
    v28 = (const struct arrow::Status *)arrow::compute::Take((unsigned int)&v66, v26, v24, (unsigned int)&v34, v27);
    v59 = 0;
    if ( *((_QWORD *)v28 + 1) )
    {
      arrow::Status::CopyFrom((arrow::Status *)v58, v28);
    }
    else
    {
      v59 = 0;
      *((_QWORD *)v28 + 1) = 0;
      v29 = (_QWORD *)((char *)v28 + 16);
      v42[0] = 0;
      v30 = -1;
      v43 = -1;
      v31 = *((_BYTE *)v29 + 24);
      if ( v31 != 0xFF )
      {
        v35 = 0;
        ((void (__fastcall *)(char *, _BYTE *, _QWORD *))mpark::detail::visitation::fdiagonal<_lambda_d7c3167c4daf4a4518bfae687c15ae74_ &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &&>::value[v31])(
          &v35,
          v42,
          v29);
        v30 = *((_BYTE *)v29 + 24);
        v43 = v30;
      }
      v60[0] = 0;
      v61 = -1;
      if ( v30 != 0xFF )
      {
        v36 = 0;
        ((void (__fastcall *)(char *, _BYTE *, _BYTE *))mpark::detail::visitation::fdiagonal<_lambda_d7c3167c4daf4a4518bfae687c15ae74_ &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &&>::value[v30])(
          &v36,
          v60,
          v42);
        v30 = v43;
        v61 = v43;
      }
      if ( v30 != 0xFF )
      {
        v37 = 0;
        ((void (__fastcall *)(char *, _BYTE *))*(&mpark::detail::visitation::fmatrix<mpark::detail::dtor &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &>::value
                                               + v30))(
          &v37,
          v42);
      }
    }
    v32 = v67;
    if ( v67 )
      goto LABEL_40;
    if ( v69 != 0xFF )
    {
      v38 = (char)v67;
      ((void (__fastcall *)(char *, char *))*(&mpark::detail::visitation::fmatrix<mpark::detail::dtor &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &>::value
                                            + v69))(
        &v38,
        v68);
      v32 = v67;
    }
    v69 = -1;
    if ( v32 )
    {
LABEL_40:
      arrow::Status::State::`scalar deleting destructor'(v32, 1u);
      v67 = 0;
    }
    if ( v52 != 0xFF )
    {
      v39[0] = 0;
      ((void (__fastcall *)(char *, _BYTE *))*(&mpark::detail::visitation::fmatrix<mpark::detail::dtor &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &>::value
                                             + v52))(
        v39,
        v51);
    }
    v52 = -1;
    v33 = v48;
    if ( v48 )
    {
      if ( _InterlockedExchangeAdd(v48 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
        if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
      }
    }
    arrow::Datum::~Datum((arrow::Datum *)v57);
    if ( v50 )
      std::_Ref_count_base::_Decref(v50);
    if ( v59 )
      arrow::compute::KernelContext::SetStatus(this, (const struct arrow::Status *)v58);
    else
      mpark::variant<std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>>::operator=(
        a3,
        v60);
    arrow::Result<arrow::Datum>::~Result<arrow::Datum>(v58);
  }
  else
  {
    v12 = *(_QWORD *)(v7 + 8);
    v13 = (*(__int64 (__fastcall **)(__int64, _BYTE **))(*(_QWORD *)v10 + 24LL))(v10, &v70);
    v14 = (*(__int64 (__fastcall **)(__int64, _BYTE **))(*(_QWORD *)v12 + 24LL))(v12, &v64);
    v15 = arrow::util::StringBuilder<char const (&)[10],std::string const &,char const (&)[37],std::string>(
            (unsigned int)&v62,
            (unsigned int)"Cast type ",
            v14,
            (unsigned int)" incompatible with dictionary type ",
            v13);
    LOBYTE(v16) = 4;
    arrow::Status::Status(v40, v16, v15);
    if ( si128.m128i_i64[1] >= 0x10uLL )
    {
      v17 = si128.m128i_i64[1] + 1;
      v18 = v62;
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v17 = si128.m128i_i64[1] + 40;
        v18 = (_BYTE *)*((_QWORD *)v62 - 1);
        if ( (unsigned __int64)(v62 - v18 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v18, v17);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v62) = 0;
    arrow::compute::KernelContext::SetStatus(this, (const struct arrow::Status *)v40);
    if ( v41 )
    {
      arrow::Status::State::`scalar deleting destructor'(v41, 1u);
      v41 = 0;
    }
    if ( v65.m128i_i64[1] >= 0x10uLL )
    {
      v19 = v65.m128i_i64[1] + 1;
      v20 = v64;
      if ( (unsigned __int64)(v65.m128i_i64[1] + 1) >= 0x1000 )
      {
        v19 = v65.m128i_i64[1] + 40;
        v20 = (_BYTE *)*((_QWORD *)v64 - 1);
        if ( (unsigned __int64)(v64 - v20 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v20, v19);
    }
    v65 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v64) = 0;
    if ( v71 >= 0x10 )
    {
      v21 = v71 + 1;
      v22 = v70;
      if ( v71 + 1 >= 0x1000 )
      {
        v21 = v71 + 40;
        v22 = (_BYTE *)*((_QWORD *)v70 - 1);
        if ( (unsigned __int64)(v70 - v22 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v22, v21);
    }
  }
  arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v56);
  arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v55);
  arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v54);
}

```

## disassembly

```asm
0x180257d30  push    rbp
0x180257d32  push    rbx
0x180257d33  push    rsi
0x180257d34  push    rdi
0x180257d35  push    r12
0x180257d37  push    r14
0x180257d39  push    r15
0x180257d3b  lea     rbp, [rsp-100h]
0x180257d43  sub     rsp, 200h
0x180257d4a  mov     [rsp+230h+var_1C8], 0FFFFFFFFFFFFFFFEh
0x180257d53  mov     rax, cs:__security_cookie
0x180257d5a  xor     rax, rsp
0x180257d5d  mov     [rbp+130h+var_40], rax
0x180257d64  mov     r12, r8
0x180257d67  mov     r14, rcx
0x180257d6a  mov     rdx, [rdx]
0x180257d6d  movzx   eax, byte ptr [rdx+18h]
0x180257d71  cmp     al, 0FFh
0x180257d73  jz      loc_18025823F
0x180257d79  cmp     al, 2
0x180257d7b  jnz     loc_18025823F
0x180257d81  lea     rcx, [rbp+130h+var_170]
0x180257d85  call    ??0DictionaryArray@arrow@@QEAA@AEBV?$shared_ptr@UArrayData@arrow@@@std@@@Z; arrow::DictionaryArray::DictionaryArray(std::shared_ptr<arrow::ArrayData> const &)
0x180257d8a  nop
0x180257d8b  mov     r15, [r14+18h]
0x180257d8f  lea     rdx, [rsp+230h+var_1C0]
0x180257d94  lea     rcx, [rbp+130h+var_170]
0x180257d98  call    ?dictionary@DictionaryArray@arrow@@QEBA?AV?$shared_ptr@VArray@arrow@@@std@@XZ; arrow::DictionaryArray::dictionary(void)
0x180257d9d  mov     rcx, [rax]
0x180257da0  mov     rax, [rcx+8]
0x180257da4  mov     rbx, [rax+8]
0x180257da8  test    rbx, rbx
0x180257dab  jz      short loc_180257DB5
0x180257dad  lock inc dword ptr [rbx+8]
0x180257db1  mov     rbx, [rax+8]
0x180257db5  mov     rsi, [rax]
0x180257db8  mov     edi, 0FFFFFFFFh
0x180257dbd  test    rbx, rbx
0x180257dc0  jz      short loc_180257DF9
0x180257dc2  mov     eax, edi
0x180257dc4  lock xadd [rbx+8], eax
0x180257dc9  cmp     eax, 1
0x180257dcc  jnz     short loc_180257DF9
0x180257dce  mov     rax, [rbx]
0x180257dd1  mov     rcx, rbx
0x180257dd4  mov     rax, [rax]
0x180257dd7  call    cs:__guard_dispatch_icall_fptr
0x180257ddd  mov     eax, edi
0x180257ddf  lock xadd [rbx+0Ch], eax
0x180257de4  cmp     eax, 1
0x180257de7  jnz     short loc_180257DF9
0x180257de9  mov     rax, [rbx]
0x180257dec  mov     rcx, rbx
0x180257def  mov     rax, [rax+8]
0x180257df3  call    cs:__guard_dispatch_icall_fptr
0x180257df9  mov     rbx, [rsp+230h+var_1B8]
0x180257dfe  test    rbx, rbx
0x180257e01  jz      short loc_180257E3A
0x180257e03  mov     eax, edi
0x180257e05  lock xadd [rbx+8], eax
0x180257e0a  cmp     eax, 1
0x180257e0d  jnz     short loc_180257E3A
0x180257e0f  mov     rax, [rbx]
0x180257e12  mov     rcx, rbx
0x180257e15  mov     rax, [rax]
0x180257e18  call    cs:__guard_dispatch_icall_fptr
0x180257e1e  mov     eax, edi
0x180257e20  lock xadd [rbx+0Ch], eax
0x180257e25  cmp     eax, 1
0x180257e28  jnz     short loc_180257E3A
0x180257e2a  mov     rax, [rbx]
0x180257e2d  mov     rcx, rbx
0x180257e30  mov     rax, [rax+8]
0x180257e34  call    cs:__guard_dispatch_icall_fptr
0x180257e3a  lea     rdx, [r15+8]
0x180257e3e  mov     rcx, rsi
0x180257e41  call    ?Equals@DataType@arrow@@QEBA_NAEBV?$shared_ptr@VDataType@arrow@@@std@@@Z; arrow::DataType::Equals(std::shared_ptr<arrow::DataType> const &)
0x180257e46  test    al, al
0x180257e48  jnz     loc_180257FCB
0x180257e4e  mov     rdi, [r15+8]
0x180257e52  mov     rax, [rsi]
0x180257e55  lea     rdx, [rbp+130h+var_60]
0x180257e5c  mov     rcx, rsi
0x180257e5f  mov     rax, [rax+18h]
0x180257e63  call    cs:__guard_dispatch_icall_fptr
0x180257e69  mov     rbx, rax
0x180257e6c  mov     rcx, [rdi]
0x180257e6f  mov     rax, [rcx+18h]
0x180257e73  lea     rdx, [rbp+130h+var_B0]
0x180257e7a  mov     rcx, rdi
0x180257e7d  call    cs:__guard_dispatch_icall_fptr
0x180257e83  nop
0x180257e84  mov     [rsp+230h+var_210], rbx
0x180257e89  lea     r9, aIncompatibleWi; " incompatible with dictionary type "
0x180257e90  mov     r8, rax
0x180257e93  lea     rdx, aCastType; "Cast type "
0x180257e9a  lea     rcx, [rbp+130h+var_D0]
0x180257e9e  call    ??$StringBuilder@AEAY09$$CBDAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0CF@$$CBDV12@@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY09$$CBDAEBV23@AEAY0CF@$$CBD$$QEAV23@@Z; arrow::util::StringBuilder<char const (&)[10],std::string const &,char const (&)[37],std::string>(char const (&)[10],std::string const &,char const (&)[37],std::string &&)
0x180257ea3  nop
0x180257ea4  mov     r8, rax
0x180257ea7  mov     dl, 4
0x180257ea9  lea     rcx, [rsp+230h+var_1F8]
0x180257eae  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x180257eb3  nop
0x180257eb4  mov     rdx, [rbp+130h+var_B8]
0x180257eb8  cmp     rdx, 10h
0x180257ebc  jb      short loc_180257EEF
0x180257ebe  inc     rdx
0x180257ec1  mov     rcx, [rbp+130h+var_D0]
0x180257ec5  mov     rax, rcx
0x180257ec8  cmp     rdx, 1000h
0x180257ecf  jb      short loc_180257EEA
0x180257ed1  add     rdx, 27h ; '''; unsigned __int64
0x180257ed5  mov     rcx, [rcx-8]; void *
0x180257ed9  sub     rax, rcx
0x180257edc  add     rax, 0FFFFFFFFFFFFFFF8h
0x180257ee0  cmp     rax, 1Fh
0x180257ee4  ja      loc_180258245
0x180257eea  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180257eef  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180257ef7  movdqu  xmmword ptr [rbp+70h], xmm0
0x180257efc  mov     byte ptr [rbp+130h+var_D0], 0
0x180257f00  lea     rdx, [rsp+230h+var_1F8]; struct arrow::Status *
0x180257f05  mov     rcx, r14; this
0x180257f08  call    ?SetStatus@KernelContext@compute@arrow@@QEAAXAEBVStatus@3@@Z; arrow::compute::KernelContext::SetStatus(arrow::Status const &)
0x180257f0d  nop
0x180257f0e  mov     rcx, [rsp+230h+var_1F0]; this
0x180257f13  test    rcx, rcx
0x180257f16  jz      short loc_180257F29
0x180257f18  mov     edx, 1; unsigned int
0x180257f1d  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x180257f22  xor     ebx, ebx
0x180257f24  mov     [rsp+230h+var_1F0], rbx
0x180257f29  mov     rdx, [rbp+130h+var_98]
0x180257f30  cmp     rdx, 10h
0x180257f34  jb      short loc_180257F6A
0x180257f36  inc     rdx
0x180257f39  mov     rcx, [rbp+130h+var_B0]
0x180257f40  mov     rax, rcx
0x180257f43  cmp     rdx, 1000h
0x180257f4a  jb      short loc_180257F65
0x180257f4c  add     rdx, 27h ; '''; unsigned __int64
0x180257f50  mov     rcx, [rcx-8]; void *
0x180257f54  sub     rax, rcx
0x180257f57  add     rax, 0FFFFFFFFFFFFFFF8h
0x180257f5b  cmp     rax, 1Fh
0x180257f5f  ja      loc_18025824B
0x180257f65  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180257f6a  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180257f72  movdqu  xmmword ptr [rbp+90h], xmm0
0x180257f7a  mov     byte ptr [rbp+130h+var_B0], 0
0x180257f81  mov     rdx, [rbp+130h+var_48]
0x180257f88  cmp     rdx, 10h
0x180257f8c  jb      loc_1802581FD
0x180257f92  inc     rdx
0x180257f95  mov     rcx, [rbp+130h+var_60]
0x180257f9c  mov     rax, rcx
0x180257f9f  cmp     rdx, 1000h
0x180257fa6  jb      short loc_180257FC1
0x180257fa8  add     rdx, 27h ; '''; unsigned __int64
0x180257fac  mov     rcx, [rcx-8]; void *
0x180257fb0  sub     rax, rcx
0x180257fb3  add     rax, 0FFFFFFFFFFFFFFF8h
0x180257fb7  cmp     rax, 1Fh
0x180257fbb  ja      loc_180258239
0x180257fc1  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180257fc6  jmp     loc_1802581FD
0x180257fcb  lea     rdx, [rbp+130h+var_1A0]
0x180257fcf  lea     rcx, [rbp+130h+var_170]
0x180257fd3  call    ?indices@DictionaryArray@arrow@@QEBA?AV?$shared_ptr@VArray@arrow@@@std@@XZ; arrow::DictionaryArray::indices(void)
0x180257fd8  nop
0x180257fd9  mov     rdx, rax
0x180257fdc  lea     rcx, [rbp+130h+var_120]
0x180257fe0  call    ??0Datum@arrow@@QEAA@AEBV?$shared_ptr@VArray@arrow@@@std@@@Z; arrow::Datum::Datum(std::shared_ptr<arrow::Array> const &)
0x180257fe5  mov     rbx, rax
0x180257fe8  lea     rdx, [rbp+130h+var_1B0]
0x180257fec  lea     rcx, [rbp+130h+var_170]
0x180257ff0  call    ?dictionary@DictionaryArray@arrow@@QEBA?AV?$shared_ptr@VArray@arrow@@@std@@XZ; arrow::DictionaryArray::dictionary(void)
0x180257ff5  nop
0x180257ff6  mov     rdx, rax
0x180257ff9  lea     rcx, [rbp+130h+var_190]
0x180257ffd  call    ??0Datum@arrow@@QEAA@AEBV?$shared_ptr@VArray@arrow@@@std@@@Z; arrow::Datum::Datum(std::shared_ptr<arrow::Array> const &)
0x180258002  nop
0x180258003  mov     rcx, [r14]
0x180258006  mov     [rsp+230h+var_200], 1
0x18025800b  mov     [rsp+230h+var_210], rcx
0x180258010  lea     r9, [rsp+230h+var_200]
0x180258015  mov     r8, rbx
0x180258018  mov     rdx, rax
0x18025801b  lea     rcx, [rbp+130h+var_90]
0x180258022  call    ?Take@compute@arrow@@YA?AV?$Result@UDatum@arrow@@@2@AEBUDatum@2@0AEBUTakeOptions@12@PEAVExecContext@12@@Z; arrow::compute::Take(arrow::Datum const &,arrow::Datum const &,arrow::compute::TakeOptions const &,arrow::compute::ExecContext *)
0x180258027  nop
0x180258028  xor     ebx, ebx
0x18025802a  mov     [rbp+130h+var_F8], rbx
0x18025802e  lea     r15, cs:180000000h
0x180258035  cmp     [rax+8], rbx
0x180258039  jnz     loc_1802580E6
0x18025803f  mov     [rbp+130h+var_F8], rbx
0x180258043  mov     [rax+8], rbx
0x180258047  lea     rsi, [rax+10h]
0x18025804b  mov     [rsp+230h+var_1E8], bl
0x18025804f  mov     al, 0FFh
0x180258051  mov     [rsp+230h+var_1D0], al
0x180258055  movzx   ecx, byte ptr [rsi+18h]
0x180258059  cmp     cl, al
0x18025805b  jz      short loc_180258087
0x18025805d  mov     [rsp+230h+var_1FF], bl
0x180258061  movzx   eax, cl
0x180258064  mov     r8, rsi
0x180258067  lea     rdx, [rsp+230h+var_1E8]
0x18025806c  lea     rcx, [rsp+230h+var_1FF]
0x180258071  mov     rax, ds:rva ?value@?$fdiagonal@$$QEAV_lambda_d7c3167c4daf4a4518bfae687c15ae74_@@AEAV?$base@$00$$TV?$shared_ptr@UScalar@arrow@@@std@@V?$shared_ptr@UArrayData@arrow@@@2@V?$shared_ptr@VChunkedArray@arrow@@@2@V?$shared_ptr@VRecordBatch@arrow@@@2@V?$shared_ptr@VTable@arrow@@@2@V?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@2@@detail@mpark@@$$QEAV234@@visitation@detail@mpark@@2U?$array@P6AX$$QEAV_lambda_d7c3167c4daf4a4518bfae687c15ae74_@@AEAV?$base@$00$$TV?$shared_ptr@UScalar@arrow@@@std@@V?$shared_ptr@UArrayData@arrow@@@2@V?$shared_ptr@VChunkedArray@arrow@@@2@V?$shared_ptr@VRecordBatch@arrow@@@2@V?$shared_ptr@VTable@arrow@@@2@V?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@2@@detail@mpark@@$$QEAV234@@Z$06@cpp14@lib@4@B[r15+rax*8]; mpark::lib::cpp14::array<void (*)(_lambda_d7c3167c4daf4a4518bfae687c15ae74_ &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &&),7> const mpark::detail::visitation::fdiagonal<_lambda_d7c3167c4daf4a4518bfae687c15ae74_ &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &&>::value ...
0x180258079  call    cs:__guard_dispatch_icall_fptr
0x18025807f  movzx   eax, byte ptr [rsi+18h]
0x180258083  mov     [rsp+230h+var_1D0], al
0x180258087  mov     [rbp+130h+var_F0], 0
0x18025808b  mov     [rbp+130h+var_D8], 0FFh
0x18025808f  cmp     al, 0FFh
0x180258091  jz      short loc_1802580BF
0x180258093  mov     [rsp+230h+var_1FE], 0
0x180258098  movzx   eax, al
0x18025809b  lea     r8, [rsp+230h+var_1E8]
0x1802580a0  lea     rdx, [rbp+130h+var_F0]
0x1802580a4  lea     rcx, [rsp+230h+var_1FE]
0x1802580a9  mov     rax, ds:rva ?value@?$fdiagonal@$$QEAV_lambda_d7c3167c4daf4a4518bfae687c15ae74_@@AEAV?$base@$00$$TV?$shared_ptr@UScalar@arrow@@@std@@V?$shared_ptr@UArrayData@arrow@@@2@V?$shared_ptr@VChunkedArray@arrow@@@2@V?$shared_ptr@VRecordBatch@arrow@@@2@V?$shared_ptr@VTable@arrow@@@2@V?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@2@@detail@mpark@@$$QEAV234@@visitation@detail@mpark@@2U?$array@P6AX$$QEAV_lambda_d7c3167c4daf4a4518bfae687c15ae74_@@AEAV?$base@$00$$TV?$shared_ptr@UScalar@arrow@@@std@@V?$shared_ptr@UArrayData@arrow@@@2@V?$shared_ptr@VChunkedArray@arrow@@@2@V?$shared_ptr@VRecordBatch@arrow@@@2@V?$shared_ptr@VTable@arrow@@@2@V?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@2@@detail@mpark@@$$QEAV234@@Z$06@cpp14@lib@4@B[r15+rax*8]; mpark::lib::cpp14::array<void (*)(_lambda_d7c3167c4daf4a4518bfae687c15ae74_ &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &&),7> const mpark::detail::visitation::fdiagonal<_lambda_d7c3167c4daf4a4518bfae687c15ae74_ &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &&>::value ...
0x1802580b1  call    cs:__guard_dispatch_icall_fptr
0x1802580b7  movzx   eax, [rsp+230h+var_1D0]
0x1802580bc  mov     [rbp+130h+var_D8], al
0x1802580bf  cmp     al, 0FFh
0x1802580c1  jz      short loc_1802580E4
0x1802580c3  mov     [rsp+230h+var_1FD], 0
0x1802580c8  movzx   eax, al
0x1802580cb  lea     rdx, [rsp+230h+var_1E8]
0x1802580d0  lea     rcx, [rsp+230h+var_1FD]
0x1802580d5  mov     rax, ds:rva ?value@?$fmatrix@$$QEAUdtor@detail@mpark@@AEAV?$base@$00$$TV?$shared_ptr@UScalar@arrow@@@std@@V?$shared_ptr@UArrayData@arrow@@@2@V?$shared_ptr@VChunkedArray@arrow@@@2@V?$shared_ptr@VRecordBatch@arrow@@@2@V?$shared_ptr@VTable@arrow@@@2@V?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@2@@23@@visitation@detail@mpark@@2U?$array@P6AX$$QEAUdtor@detail@mpark@@AEAV?$base@$00$$TV?$shared_ptr@UScalar@arrow@@@std@@V?$shared_ptr@UArrayData@arrow@@@2@V?$shared_ptr@VChunkedArray@arrow@@@2@V?$shared_ptr@VRecordBatch@arrow@@@2@V?$shared_ptr@VTable@arrow@@@2@V?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@2@@23@@Z$06@cpp14@lib@4@B[r15+rax*8]; mpark::lib::cpp14::array<void (*)(mpark::detail::dtor &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &),7> const mpark::detail::visitation::fmatrix<mpark::detail::dtor &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &>::value ...
0x1802580dd  call    cs:__guard_dispatch_icall_fptr
0x1802580e3  nop
0x1802580e4  jmp     short loc_1802580F3
0x1802580e6  mov     rdx, rax; struct arrow::Status *
0x1802580e9  lea     rcx, [rbp+130h+var_100]; this
0x1802580ed  call    ?CopyFrom@Status@arrow@@AEAAXAEBV12@@Z; arrow::Status::CopyFrom(arrow::Status const &)
0x1802580f2  nop
0x1802580f3  mov     rcx, [rbp+130h+var_88]
0x1802580fa  test    rcx, rcx
0x1802580fd  jnz     short loc_18025813E
0x1802580ff  movzx   eax, [rbp+130h+var_68]
0x180258106  cmp     al, 0FFh
0x180258108  jz      short loc_180258132
0x18025810a  mov     [rsp+230h+var_1FC], cl
0x18025810e  movzx   eax, al
0x180258111  lea     rdx, [rbp+130h+var_80]
0x180258118  lea     rcx, [rsp+230h+var_1FC]
0x18025811d  mov     rax, ds:rva ?value@?$fmatrix@$$QEAUdtor@detail@mpark@@AEAV?$base@$00$$TV?$shared_ptr@UScalar@arrow@@@std@@V?$shared_ptr@UArrayData@arrow@@@2@V?$shared_ptr@VChunkedArray@arrow@@@2@V?$shared_ptr@VRecordBatch@arrow@@@2@V?$shared_ptr@VTable@arrow@@@2@V?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@2@@23@@visitation@detail@mpark@@2U?$array@P6AX$$QEAUdtor@detail@mpark@@AEAV?$base@$00$$TV?$shared_ptr@UScalar@arrow@@@std@@V?$shared_ptr@UArrayData@arrow@@@2@V?$shared_ptr@VChunkedArray@arrow@@@2@V?$shared_ptr@VRecordBatch@arrow@@@2@V?$shared_ptr@VTable@arrow@@@2@V?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@2@@23@@Z$06@cpp14@lib@4@B[r15+rax*8]; mpark::lib::cpp14::array<void (*)(mpark::detail::dtor &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &),7> const mpark::detail::visitation::fmatrix<mpark::detail::dtor &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &>::value ...
0x180258125  call    cs:__guard_dispatch_icall_fptr
0x18025812b  mov     rcx, [rbp+130h+var_88]; this
0x180258132  mov     [rbp+130h+var_68], 0FFh
0x180258139  test    rcx, rcx
0x18025813c  jz      short loc_18025814F
0x18025813e  mov     edx, 1; unsigned int
0x180258143  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x180258148  mov     [rbp+130h+var_88], rbx
0x18025814f  movzx   eax, [rbp+130h+var_178]
0x180258153  cmp     al, 0FFh
0x180258155  jz      short loc_180258176
0x180258157  mov     [rsp+230h+var_1FB], 0
0x18025815c  movzx   eax, al
0x18025815f  lea     rdx, [rbp+130h+var_190]
0x180258163  lea     rcx, [rsp+230h+var_1FB]
0x180258168  mov     rax, ds:rva ?value@?$fmatrix@$$QEAUdtor@detail@mpark@@AEAV?$base@$00$$TV?$shared_ptr@UScalar@arrow@@@std@@V?$shared_ptr@UArrayData@arrow@@@2@V?$shared_ptr@VChunkedArray@arrow@@@2@V?$shared_ptr@VRecordBatch@arrow@@@2@V?$shared_ptr@VTable@arrow@@@2@V?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@2@@23@@visitation@detail@mpark@@2U?$array@P6AX$$QEAUdtor@detail@mpark@@AEAV?$base@$00$$TV?$shared_ptr@UScalar@arrow@@@std@@V?$shared_ptr@UArrayData@arrow@@@2@V?$shared_ptr@VChunkedArray@arrow@@@2@V?$shared_ptr@VRecordBatch@arrow@@@2@V?$shared_ptr@VTable@arrow@@@2@V?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@2@@23@@Z$06@cpp14@lib@4@B[r15+rax*8]; mpark::lib::cpp14::array<void (*)(mpark::detail::dtor &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &),7> const mpark::detail::visitation::fmatrix<mpark::detail::dtor &&,mpark::detail::base<1,std::nullptr_t,std::shared_ptr<arrow::Scalar>,std::shared_ptr<arrow::ArrayData>,std::shared_ptr<arrow::ChunkedArray>,std::shared_ptr<arrow::RecordBatch>,std::shared_ptr<arrow::Table>,std::vector<arrow::Datum>> &>::value ...
0x180258170  call    cs:__guard_dispatch_icall_fptr
0x180258176  mov     [rbp+130h+var_178], 0FFh
0x18025817a  mov     rbx, [rbp+130h+var_1A8]
0x18025817e  test    rbx, rbx
0x180258181  jz      short loc_1802581B9
0x180258183  mov     eax, edi
0x180258185  lock xadd [rbx+8], eax
0x18025818a  cmp     eax, 1
0x18025818d  jnz     short loc_1802581B9
0x18025818f  mov     rax, [rbx]
0x180258192  mov     rcx, rbx
0x180258195  mov     rax, [rax]
0x180258198  call    cs:__guard_dispatch_icall_fptr
0x18025819e  lock xadd [rbx+0Ch], edi
0x1802581a3  cmp     edi, 1
0x1802581a6  jnz     short loc_1802581B9
0x1802581a8  mov     rax, [rbx]
0x1802581ab  mov     rcx, rbx
0x1802581ae  mov     rax, [rax+8]
0x1802581b2  call    cs:__guard_dispatch_icall_fptr
0x1802581b8  nop
0x1802581b9  lea     rcx, [rbp+130h+var_120]; this
0x1802581bd  call    ??1Datum@arrow@@QEAA@XZ; arrow::Datum::~Datum(void)
0x1802581c2  nop
0x1802581c3  mov     rcx, [rbp+130h+var_198]; this
0x1802581c7  test    rcx, rcx
0x1802581ca  jz      short loc_1802581D1
0x1802581cc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1802581d1  cmp     [rbp+130h+var_F8], 0
0x1802581d6  jz      short loc_1802581E6
0x1802581d8  lea     rdx, [rbp+130h+var_100]; struct arrow::Status *
  ... truncated ...
```
