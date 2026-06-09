# arrow::compute::internal::RegisterScalarAggregateBasic(arrow::compute::FunctionRegistry *)

- ea: `0x180240d20`
- end: `0x180241782`
- name: `?RegisterScalarAggregateBasic@internal@compute@arrow@@YAXPEAVFunctionRegistry@23@@Z`
- size: `2658`
- prototype: `void __fastcall(arrow::compute::internal *__hidden this, struct arrow::compute::FunctionRegistry *)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18012d690`

## callees

- `0x180010860`
- `0x18001b890`
- `0x18001f8c0`
- `0x180049a90`
- `0x1800a8dd0`
- `0x1800a9760`
- `0x1800a9af0`
- `0x1800ab370`
- `0x1800d3af0`
- `0x1801274a0`
- `0x180127ce0`
- `0x18012d340`
- `0x18012f760`
- `0x18012f8a0`
- `0x180237920`
- `0x180237ea0`
- `0x180238060`
- `0x1802382c0`
- `0x180240d20`
- `0x180241790`
- `0x18024bbe0`
- `0x18024c180`
- `0x18024c2a0`
- `0x18024c3c0`
- `0x1802f0fb0`
- `0x18030c180`
- `0x18030c200`
- `0x18030cdc0`
- `0x18030ce20`
- `0x180334640`
- `0x180358070`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall arrow::compute::internal::RegisterScalarAggregateBasic(
        arrow::compute::internal *this,
        struct arrow::compute::FunctionRegistry *a2)
{
  _DWORD *v3; // r15
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  volatile signed __int32 *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  _BYTE *v11; // rax
  _BYTE *v12; // rdi
  __int64 v13; // rax
  char *v14; // rbx
  unsigned __int64 v15; // rdx
  char *v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rdx
  __int64 v19; // rbx
  __int64 v20; // rdx
  __int64 v21; // rbx
  __int64 v22; // rdx
  _BYTE *v23; // rax
  _BYTE *v24; // rdi
  __int64 v25; // rax
  char *v26; // rbx
  unsigned __int64 v27; // rdx
  char *v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rdx
  _BYTE *v31; // rax
  _BYTE *v32; // rdi
  char *v33; // rbx
  unsigned __int64 v34; // rdx
  char *v35; // rax
  __int64 v36; // rdx
  int v37; // [rsp+30h] [rbp-D0h] BYREF
  char v38; // [rsp+34h] [rbp-CCh]
  void *v39; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v40; // [rsp+40h] [rbp-C0h]
  void *v41; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v42; // [rsp+58h] [rbp-A8h]
  void *v43; // [rsp+68h] [rbp-98h] BYREF
  __int128 v44; // [rsp+70h] [rbp-90h]
  _DWORD v45[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v46; // [rsp+88h] [rbp-78h] BYREF
  __int128 v47; // [rsp+98h] [rbp-68h]
  _QWORD v48[3]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD v49[2]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v50[16]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v51[2]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v52[16]; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD v53[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v54[16]; // [rsp+110h] [rbp+10h] BYREF
  __int128 v55; // [rsp+120h] [rbp+20h] BYREF
  __int64 v56; // [rsp+130h] [rbp+30h]
  _BYTE v57[16]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v58; // [rsp+148h] [rbp+48h]
  __int64 v59; // [rsp+150h] [rbp+50h]
  _BYTE v60[16]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v61; // [rsp+168h] [rbp+68h]
  __int64 v62; // [rsp+170h] [rbp+70h]
  _BYTE v63[16]; // [rsp+178h] [rbp+78h] BYREF
  __int64 v64; // [rsp+188h] [rbp+88h]
  __int64 v65; // [rsp+190h] [rbp+90h]
  _BYTE v66[16]; // [rsp+198h] [rbp+98h] BYREF
  __int64 v67; // [rsp+1A8h] [rbp+A8h]
  __int64 v68; // [rsp+1B0h] [rbp+B0h]
  _DWORD v69[2]; // [rsp+1B8h] [rbp+B8h] BYREF
  _OWORD v70[2]; // [rsp+1C0h] [rbp+C0h] BYREF
  char v71[16]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v72[16]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v73[16]; // [rsp+200h] [rbp+100h] BYREF
  char v74[8]; // [rsp+210h] [rbp+110h] BYREF
  arrow::Status::State *v75; // [rsp+218h] [rbp+118h]
  __int64 v76; // [rsp+220h] [rbp+120h]
  _QWORD *v77; // [rsp+228h] [rbp+128h]
  char v78[16]; // [rsp+230h] [rbp+130h] BYREF
  char v79[8]; // [rsp+240h] [rbp+140h] BYREF
  arrow::Status::State *v80; // [rsp+248h] [rbp+148h]
  char v81[16]; // [rsp+250h] [rbp+150h] BYREF
  char v82[8]; // [rsp+260h] [rbp+160h] BYREF
  arrow::Status::State *v83; // [rsp+268h] [rbp+168h]
  char v84[16]; // [rsp+270h] [rbp+170h] BYREF
  _BYTE v85[16]; // [rsp+280h] [rbp+180h] BYREF
  _BYTE v86[16]; // [rsp+290h] [rbp+190h] BYREF
  char v87[8]; // [rsp+2A0h] [rbp+1A0h] BYREF
  arrow::Status::State *v88; // [rsp+2A8h] [rbp+1A8h]
  _QWORD v89[8]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _QWORD v90[8]; // [rsp+2F0h] [rbp+1F0h] BYREF
  _QWORD v91[8]; // [rsp+330h] [rbp+230h] BYREF
  _QWORD v92[8]; // [rsp+370h] [rbp+270h] BYREF
  _QWORD v93[8]; // [rsp+3B0h] [rbp+2B0h] BYREF
  _QWORD v94[8]; // [rsp+3F0h] [rbp+2F0h] BYREF
  _QWORD v95[8]; // [rsp+430h] [rbp+330h] BYREF
  _QWORD v96[8]; // [rsp+470h] [rbp+370h] BYREF
  _QWORD v97[8]; // [rsp+4B0h] [rbp+3B0h] BYREF
  char v98[24]; // [rsp+4F0h] [rbp+3F0h] BYREF
  _BYTE v99[152]; // [rsp+508h] [rbp+408h] BYREF
  _BYTE *v100; // [rsp+5B8h] [rbp+4B8h] BYREF
  _QWORD *v101; // [rsp+5C0h] [rbp+4C0h] BYREF
  int v102; // [rsp+5C8h] [rbp+4C8h] BYREF
  char v103; // [rsp+5CCh] [rbp+4CCh]

  v76 = -2;
  v3 = (_DWORD *)(*((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index) + 4LL);
  if ( dword_1804C53FC > *v3 )
  {
    Init_thread_header(&dword_1804C53FC);
    if ( dword_1804C53FC == -1 )
    {
      dword_1804C53F8 = 0;
      Init_thread_footer(&dword_1804C53FC);
    }
  }
  LODWORD(v100) = 1;
  BYTE4(v100) = 0;
  v4 = operator new(0x68u);
  v5 = v4;
  v101 = v4;
  if ( v4 )
  {
    *((_DWORD *)v4 + 2) = 1;
    *((_DWORD *)v4 + 3) = 1;
    *v4 = &std::_Ref_count_obj<arrow::compute::ScalarAggregateFunction>::`vftable';
    v58 = 0;
    v59 = 15;
    v57[0] = 0;
    std::string::assign(v57, (void *)"count", 5u);
    arrow::compute::ScalarAggregateFunction::ScalarAggregateFunction(v5 + 2, v57, &v100, &dword_1804C53F8);
  }
  else
  {
    v5 = 0;
  }
  v69[0] = 0;
  v69[1] = 1;
  memset(v70, 0, sizeof(v70));
  v77 = v89;
  v48[2] = v99;
  v46 = 0;
  v47 = 0;
  v45[0] = 0;
  v45[1] = 1;
  std::shared_ptr<arrow::ArrayData>::operator=(&v46, v70);
  v6 = (volatile signed __int32 *)*((_QWORD *)&v47 + 1);
  v47 = 0u;
  if ( v6 )
  {
    if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  v89[0] = &std::_Func_impl_no_alloc<std::unique_ptr<arrow::compute::KernelState> (*)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),std::unique_ptr<arrow::compute::KernelState>,arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &>::`vftable';
  v89[1] = arrow::compute::aggregate::CountInit;
  v89[7] = v89;
  v7 = arrow::int64(v78);
  v8 = arrow::ValueDescr::Scalar(v98, v7);
  v9 = arrow::compute::OutputType::OutputType(v99, v8);
  v55 = 0;
  v56 = 0;
  std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(
    &v55,
    v45,
    v48,
    (unsigned __int8)v100);
  v10 = arrow::compute::KernelSignature::Make(v81, &v55, v9, 0, v5 + 2, v5);
  arrow::compute::aggregate::AddAggKernel(v10, v89, v5 + 2);
  `eh vector destructor iterator'(v45, 0x28u, 1u, (void (*)(void *))arrow::compute::InputType::~InputType);
  v49[0] = v5 + 2;
  v49[1] = v5;
  arrow::compute::FunctionRegistry::AddFunction(this, v82, v49, 0);
  if ( v83 )
    arrow::Status::State::`scalar deleting destructor'(v83, 1u);
  LODWORD(v101) = 1;
  BYTE4(v101) = 0;
  v11 = operator new(0x68u);
  v12 = v11;
  v100 = v11;
  if ( v11 )
  {
    *((_DWORD *)v11 + 2) = 1;
    *((_DWORD *)v11 + 3) = 1;
    *(_QWORD *)v11 = &std::_Ref_count_obj<arrow::compute::ScalarAggregateFunction>::`vftable';
    v61 = 0;
    v62 = 15;
    v60[0] = 0;
    std::string::assign(v60, "sum", 3u);
    arrow::compute::ScalarAggregateFunction::ScalarAggregateFunction(v12 + 16, v60, &v101, 0);
  }
  else
  {
    v12 = 0;
  }
  arrow::boolean(v50);
  v39 = 0;
  v40 = 0;
  std::vector<std::shared_ptr<arrow::compute::CastFunction>>::_Range_construct_or_tidy<std::shared_ptr<arrow::compute::CastFunction> const *>(
    &v39,
    v50,
    v51,
    (unsigned __int8)v100,
    v12 + 16,
    v12);
  v13 = arrow::int64(v84);
  v90[0] = &std::_Func_impl_no_alloc<std::unique_ptr<arrow::compute::KernelState> (*)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),std::unique_ptr<arrow::compute::KernelState>,arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &>::`vftable';
  v90[1] = arrow::compute::aggregate::SumInit;
  v90[7] = v90;
  arrow::compute::aggregate::AddBasicAggKernels(v90, &v39, v13, v12 + 16);
  v14 = (char *)v39;
  if ( v39 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<arrow::ChunkedArray>>>(v39, v40, &v39);
    v15 = (*((_QWORD *)&v40 + 1) - (_QWORD)v14) & 0xFFFFFFFFFFFFFFF0uLL;
    v16 = v14;
    if ( v15 >= 0x1000 )
    {
      v15 += 39LL;
      v14 = (char *)*((_QWORD *)v14 - 1);
      if ( (unsigned __int64)(v16 - v14 - 8) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v14, v15);
  }
  `eh vector destructor iterator'(
    v50,
    0x10u,
    1u,
    arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>);
  v100 = v85;
  v101 = v91;
  v17 = arrow::int64(v85);
  v91[0] = &std::_Func_impl_no_alloc<std::unique_ptr<arrow::compute::KernelState> (*)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),std::unique_ptr<arrow::compute::KernelState>,arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &>::`vftable';
  v91[1] = arrow::compute::aggregate::SumInit;
  v91[7] = v91;
  v18 = arrow::compute::internal::SignedIntTypes();
  arrow::compute::aggregate::AddBasicAggKernels(v91, v18, v17, v12 + 16);
  v100 = v73;
  v101 = v92;
  v19 = arrow::uint64(v73);
  v92[0] = &std::_Func_impl_no_alloc<std::unique_ptr<arrow::compute::KernelState> (*)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),std::unique_ptr<arrow::compute::KernelState>,arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &>::`vftable';
  v92[1] = arrow::compute::aggregate::SumInit;
  v92[7] = v92;
  v20 = arrow::compute::internal::UnsignedIntTypes();
  arrow::compute::aggregate::AddBasicAggKernels(v92, v20, v19, v12 + 16);
  v100 = v86;
  v101 = v93;
  v21 = arrow::float64(v86);
  v93[0] = &std::_Func_impl_no_alloc<std::unique_ptr<arrow::compute::KernelState> (*)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),std::unique_ptr<arrow::compute::KernelState>,arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &>::`vftable';
  v93[1] = arrow::compute::aggregate::SumInit;
  v93[7] = v93;
  v22 = arrow::compute::internal::FloatingPointTypes();
  arrow::compute::aggregate::AddBasicAggKernels(v93, v22, v21, v12 + 16);
  v51[0] = v12 + 16;
  v51[1] = v12;
  arrow::compute::FunctionRegistry::AddFunction(this, v87, v51, 0);
  if ( v88 )
    arrow::Status::State::`scalar deleting destructor'(v88, 1u);
  v102 = 1;
  v103 = 0;
  v23 = operator new(0x68u);
  v24 = v23;
  v100 = v23;
  if ( v23 )
  {
    *((_DWORD *)v23 + 2) = 1;
    *((_DWORD *)v23 + 3) = 1;
    *(_QWORD *)v23 = &std::_Ref_count_obj<arrow::compute::ScalarAggregateFunction>::`vftable';
    v64 = 0;
    v65 = 15;
    v63[0] = 0;
    std::string::assign(v63, "mean", 4u);
    arrow::compute::ScalarAggregateFunction::ScalarAggregateFunction(v24 + 16, v63, &v102, 0);
  }
  else
  {
    v24 = 0;
  }
  arrow::boolean(v52);
  v41 = 0;
  v42 = 0;
  std::vector<std::shared_ptr<arrow::compute::CastFunction>>::_Range_construct_or_tidy<std::shared_ptr<arrow::compute::CastFunction> const *>(
    &v41,
    v52,
    v53,
    (unsigned __int8)v100,
    v24 + 16,
    v24);
  v25 = arrow::float64(v71);
  v94[0] = &std::_Func_impl_no_alloc<std::unique_ptr<arrow::compute::KernelState> (*)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),std::unique_ptr<arrow::compute::KernelState>,arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &>::`vftable';
  v94[1] = arrow::compute::aggregate::MeanInit;
  v94[7] = v94;
  arrow::compute::aggregate::AddBasicAggKernels(v94, &v41, v25, v24 + 16);
  v26 = (char *)v41;
  if ( v41 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<arrow::ChunkedArray>>>(v41, v42, &v41);
    v27 = (*((_QWORD *)&v42 + 1) - (_QWORD)v26) & 0xFFFFFFFFFFFFFFF0uLL;
    v28 = v26;
    if ( v27 >= 0x1000 )
    {
      v27 += 39LL;
      v26 = (char *)*((_QWORD *)v26 - 1);
      if ( (unsigned __int64)(v28 - v26 - 8) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v26, v27);
  }
  `eh vector destructor iterator'(
    v52,
    0x10u,
    1u,
    arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>);
  v100 = v72;
  v101 = v95;
  v29 = arrow::float64(v72);
  v95[0] = &std::_Func_impl_no_alloc<std::unique_ptr<arrow::compute::KernelState> (*)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),std::unique_ptr<arrow::compute::KernelState>,arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &>::`vftable';
  v95[1] = arrow::compute::aggregate::MeanInit;
  v95[7] = v95;
  v30 = arrow::compute::internal::NumericTypes();
  arrow::compute::aggregate::AddBasicAggKernels(v95, v30, v29, v24 + 16);
  v53[0] = v24 + 16;
  v53[1] = v24;
  arrow::compute::FunctionRegistry::AddFunction(this, v79, v53, 0);
  if ( v80 )
    arrow::Status::State::`scalar deleting destructor'(v80, 1u);
  if ( dword_1804C5404 > *v3 )
  {
    Init_thread_header(&dword_1804C5404);
    if ( dword_1804C5404 == -1 )
    {
      dword_1804C5400 = 0;
      Init_thread_footer(&dword_1804C5404);
    }
  }
  v37 = 1;
  v38 = 0;
  v31 = operator new(0x68u);
  v32 = v31;
  v100 = v31;
  if ( v31 )
  {
    *((_DWORD *)v31 + 2) = 1;
    *((_DWORD *)v31 + 3) = 1;
    *(_QWORD *)v31 = &std::_Ref_count_obj<arrow::compute::ScalarAggregateFunction>::`vftable';
    v67 = 0;
    v68 = 15;
    v66[0] = 0;
    std::string::assign(v66, "min_max", 7u);
    arrow::compute::ScalarAggregateFunction::ScalarAggregateFunction(v32 + 16, v66, &v37, &dword_1804C5400);
  }
  else
  {
    v32 = 0;
  }
  arrow::boolean(v54);
  v43 = 0;
  v44 = 0;
  std::vector<std::shared_ptr<arrow::compute::CastFunction>>::_Range_construct_or_tidy<std::shared_ptr<arrow::compute::CastFunction> const *>(
    &v43,
    v54,
    &v55,
    (unsigned __int8)v100,
    v32 + 16,
    v32);
  v96[0] = &std::_Func_impl_no_alloc<std::unique_ptr<arrow::compute::KernelState> (*)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),std::unique_ptr<arrow::compute::KernelState>,arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &>::`vftable';
  v96[1] = arrow::compute::aggregate::MinMaxInit;
  v96[7] = v96;
  arrow::compute::aggregate::AddMinMaxKernels(v96, &v43, v32 + 16);
  v33 = (char *)v43;
  if ( v43 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<arrow::ChunkedArray>>>(v43, v44, &v43);
    v34 = (*((_QWORD *)&v44 + 1) - (_QWORD)v33) & 0xFFFFFFFFFFFFFFF0uLL;
    v35 = v33;
    if ( v34 >= 0x1000 )
    {
      v34 += 39LL;
      v33 = (char *)*((_QWORD *)v33 - 1);
      if ( (unsigned __int64)(v35 - v33 - 8) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v33, v34);
  }
  `eh vector destructor iterator'(
    v54,
    0x10u,
    1u,
    arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>);
  v100 = v97;
  v97[0] = &std::_Func_impl_no_alloc<std::unique_ptr<arrow::compute::KernelState> (*)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),std::unique_ptr<arrow::compute::KernelState>,arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &>::`vftable';
  v97[1] = arrow::compute::aggregate::MinMaxInit;
  v97[7] = v97;
  v36 = arrow::compute::internal::NumericTypes();
  arrow::compute::aggregate::AddMinMaxKernels(v97, v36, v32 + 16);
  v48[0] = v32 + 16;
  v48[1] = v32;
  arrow::compute::FunctionRegistry::AddFunction(this, v74, v48, 0);
  if ( v75 )
    arrow::Status::State::`scalar deleting destructor'(v75, 1u);
  arrow::compute::InputType::~InputType((arrow::compute::InputType *)v69);
}

```

## disassembly

```asm
0x180240d20  push    rbp
0x180240d22  push    rsi
0x180240d23  push    rdi
0x180240d24  push    r12
0x180240d26  push    r13
0x180240d28  push    r14
0x180240d2a  push    r15
0x180240d2c  lea     rbp, [rsp-470h]
0x180240d34  sub     rsp, 570h
0x180240d3b  mov     [rbp+4A0h+var_380], 0FFFFFFFFFFFFFFFEh
0x180240d46  mov     [rsp+5A0h+arg_0], rbx
0x180240d4e  mov     r12, rcx
0x180240d51  mov     edx, cs:_tls_index
0x180240d57  mov     rax, gs:58h
0x180240d60  mov     ecx, 4
0x180240d65  mov     r15, [rax+rdx*8]
0x180240d69  add     r15, rcx
0x180240d6c  xor     r13d, r13d
0x180240d6f  mov     eax, [r15]
0x180240d72  cmp     cs:dword_1804C53FC, eax
0x180240d78  jg      loc_180241713
0x180240d7e  mov     dword ptr [rbp+4A0h+arg_8], 1
0x180240d88  mov     byte ptr [rbp+4A0h+arg_8+4], r13b
0x180240d8f  mov     ecx, 68h ; 'h'; Size
0x180240d94  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180240d99  mov     rdi, rax
0x180240d9c  mov     [rbp+4A0h+arg_10], rax
0x180240da3  lea     rsi, ??_7?$_Ref_count_obj@VScalarAggregateFunction@compute@arrow@@@std@@6B@; const std::_Ref_count_obj<arrow::compute::ScalarAggregateFunction>::`vftable'
0x180240daa  test    rax, rax
0x180240dad  jz      short loc_180240E03
0x180240daf  mov     dword ptr [rax+8], 1
0x180240db6  mov     dword ptr [rax+0Ch], 1
0x180240dbd  mov     [rax], rsi
0x180240dc0  mov     [rbp+4A0h+var_458], r13
0x180240dc4  mov     [rbp+4A0h+var_450], 0Fh
0x180240dcc  mov     [rbp+4A0h+var_468], 0
0x180240dd0  mov     r8d, 5; Size
0x180240dd6  lea     rdx, aCount; "count"
0x180240ddd  lea     rcx, [rbp+4A0h+var_468]; void *
0x180240de1  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x180240de6  lea     r9, dword_1804C53F8
0x180240ded  lea     r8, [rbp+4A0h+arg_8]
0x180240df4  lea     rdx, [rbp+4A0h+var_468]
0x180240df8  lea     rcx, [rdi+10h]
0x180240dfc  call    ??0ScalarAggregateFunction@compute@arrow@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUArity@12@PEBUFunctionOptions@12@@Z; arrow::compute::ScalarAggregateFunction::ScalarAggregateFunction(std::string,arrow::compute::Arity const &,arrow::compute::FunctionOptions const *)
0x180240e01  jmp     short loc_180240E06
0x180240e03  mov     rdi, r13
0x180240e06  lea     r14, [rdi+10h]
0x180240e0a  mov     qword ptr [rsp+5A0h+var_580], r14
0x180240e0f  mov     qword ptr [rsp+5A0h+var_580+8], rdi
0x180240e14  mov     [rbp+4A0h+var_3E8], r13d
0x180240e1b  mov     [rbp+4A0h+var_3E4], 1
0x180240e25  xorps   xmm0, xmm0
0x180240e28  movdqu  [rbp+4A0h+var_3E0], xmm0
0x180240e30  xorps   xmm1, xmm1
0x180240e33  movdqu  [rbp+4A0h+var_3D0], xmm1
0x180240e3b  lea     rax, [rbp+4A0h+var_2F0]
0x180240e42  mov     [rbp+4A0h+var_378], rax
0x180240e49  lea     rax, [rbp+4A0h+var_98]
0x180240e50  mov     [rbp+4A0h+var_4E8], rax
0x180240e54  movdqu  [rbp+4A0h+var_518], xmm0
0x180240e59  movdqu  [rbp+4A0h+var_508], xmm1
0x180240e5e  mov     [rbp+4A0h+var_520], r13d
0x180240e62  mov     [rbp+4A0h+var_51C], 1
0x180240e69  lea     rdx, [rbp+4A0h+var_3E0]
0x180240e70  lea     rcx, [rbp+4A0h+var_518]
0x180240e74  call    ??4?$shared_ptr@UArrayData@arrow@@@std@@QEAAAEAV01@AEBV01@@Z; std::shared_ptr<arrow::ArrayData>::operator=(std::shared_ptr<arrow::ArrayData> const &)
0x180240e79  mov     qword ptr [rbp+4A0h+var_508], r13
0x180240e7d  mov     rbx, qword ptr [rbp+4A0h+var_508+8]
0x180240e81  mov     qword ptr [rbp+4A0h+var_508+8], r13
0x180240e85  test    rbx, rbx
0x180240e88  jz      short loc_180240ECB
0x180240e8a  mov     esi, 0FFFFFFFFh
0x180240e8f  mov     eax, esi
0x180240e91  lock xadd [rbx+8], eax
0x180240e96  cmp     eax, 1
0x180240e99  jnz     short loc_180240EC4
0x180240e9b  mov     rax, [rbx]
0x180240e9e  mov     rcx, rbx
0x180240ea1  mov     rax, [rax]
0x180240ea4  call    cs:__guard_dispatch_icall_fptr
0x180240eaa  lock xadd [rbx+0Ch], esi
0x180240eaf  cmp     esi, 1
0x180240eb2  jnz     short loc_180240EC4
0x180240eb4  mov     rax, [rbx]
0x180240eb7  mov     rcx, rbx
0x180240eba  mov     rax, [rax+8]
0x180240ebe  call    cs:__guard_dispatch_icall_fptr
0x180240ec4  lea     rsi, ??_7?$_Ref_count_obj@VScalarAggregateFunction@compute@arrow@@@std@@6B@; const std::_Ref_count_obj<arrow::compute::ScalarAggregateFunction>::`vftable'
0x180240ecb  lea     rax, ??_7?$_Func_impl_no_alloc@P6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@45@@ZV12@PEAV345@AEBU645@@std@@6B@; const std::_Func_impl_no_alloc<std::unique_ptr<arrow::compute::KernelState> (*)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),std::unique_ptr<arrow::compute::KernelState>,arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &>::`vftable'
0x180240ed2  mov     [rbp+4A0h+var_2F0], rax
0x180240ed9  lea     rax, ?CountInit@aggregate@compute@arrow@@YA?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@23@AEBUKernelInitArgs@23@@Z; arrow::compute::aggregate::CountInit(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)
0x180240ee0  mov     [rbp+4A0h+var_2E8], rax
0x180240ee7  lea     rax, [rbp+4A0h+var_2F0]
0x180240eee  mov     [rbp+4A0h+var_2B8], rax
0x180240ef5  lea     rcx, [rbp+4A0h+var_370]
0x180240efc  call    ?int64@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::int64(void)
0x180240f01  mov     rdx, rax
0x180240f04  lea     rcx, [rbp+4A0h+var_B0]
0x180240f0b  call    ?Scalar@ValueDescr@arrow@@SA?AU12@V?$shared_ptr@VDataType@arrow@@@std@@@Z; arrow::ValueDescr::Scalar(std::shared_ptr<arrow::DataType>)
0x180240f10  mov     rdx, rax
0x180240f13  lea     rcx, [rbp+4A0h+var_98]
0x180240f1a  call    ??0OutputType@compute@arrow@@QEAA@UValueDescr@2@@Z; arrow::compute::OutputType::OutputType(arrow::ValueDescr)
0x180240f1f  mov     rbx, rax
0x180240f22  xorps   xmm0, xmm0
0x180240f25  movdqu  [rbp+4A0h+var_480], xmm0
0x180240f2a  mov     [rbp+4A0h+var_470], r13
0x180240f2e  movzx   r9d, byte ptr [rbp+4A0h+arg_8]
0x180240f36  lea     r8, [rbp+4A0h+var_4F8]
0x180240f3a  lea     rdx, [rbp+4A0h+var_520]
0x180240f3e  lea     rcx, [rbp+4A0h+var_480]
0x180240f42  call    ??$_Range_construct_or_tidy@PEBVInputType@compute@arrow@@@?$vector@VInputType@compute@arrow@@V?$allocator@VInputType@compute@arrow@@@std@@@std@@AEAAXPEBVInputType@compute@arrow@@0Uforward_iterator_tag@1@@Z; std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(arrow::compute::InputType const *,arrow::compute::InputType const *,std::forward_iterator_tag)
0x180240f47  nop
0x180240f48  xor     r9d, r9d
0x180240f4b  mov     r8, rbx
0x180240f4e  lea     rdx, [rbp+4A0h+var_480]
0x180240f52  lea     rcx, [rbp+4A0h+var_350]
0x180240f59  call    ?Make@KernelSignature@compute@arrow@@SA?AV?$shared_ptr@VKernelSignature@compute@arrow@@@std@@V?$vector@VInputType@compute@arrow@@V?$allocator@VInputType@compute@arrow@@@std@@@5@VOutputType@23@_N@Z; arrow::compute::KernelSignature::Make(std::vector<arrow::compute::InputType>,arrow::compute::OutputType,bool)
0x180240f5e  nop
0x180240f5f  mov     r8, r14
0x180240f62  lea     rdx, [rbp+4A0h+var_2F0]
0x180240f69  mov     rcx, rax
0x180240f6c  call    ?AddAggKernel@aggregate@compute@arrow@@YAXV?$shared_ptr@VKernelSignature@compute@arrow@@@std@@V?$function@$$A6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@45@@Z@5@PEAVScalarAggregateFunction@23@@Z; arrow::compute::aggregate::AddAggKernel(std::shared_ptr<arrow::compute::KernelSignature>,std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>,arrow::compute::ScalarAggregateFunction *)
0x180240f71  nop
0x180240f72  lea     r9, ??1InputType@compute@arrow@@QEAA@XZ; void (*)(void *)
0x180240f79  mov     edx, 28h ; '('; unsigned __int64
0x180240f7e  lea     r8d, [rdx-27h]; unsigned __int64
0x180240f82  lea     rcx, [rbp+4A0h+var_520]; void *
0x180240f86  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180240f8b  mov     [rbp+4A0h+var_4E0], r14
0x180240f8f  mov     [rbp+4A0h+var_4D8], rdi
0x180240f93  xorps   xmm0, xmm0
0x180240f96  movdqu  [rsp+5A0h+var_580], xmm0
0x180240f9c  xor     r9d, r9d
0x180240f9f  lea     r8, [rbp+4A0h+var_4E0]
0x180240fa3  lea     rdx, [rbp+4A0h+var_340]
0x180240faa  mov     rcx, r12
0x180240fad  call    ?AddFunction@FunctionRegistry@compute@arrow@@QEAA?AVStatus@3@V?$shared_ptr@VFunction@compute@arrow@@@std@@_N@Z; arrow::compute::FunctionRegistry::AddFunction(std::shared_ptr<arrow::compute::Function>,bool)
0x180240fb2  mov     rcx, [rbp+4A0h+var_338]; this
0x180240fb9  test    rcx, rcx
0x180240fbc  jz      short loc_180240FC8
0x180240fbe  mov     edx, 1; unsigned int
0x180240fc3  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x180240fc8  mov     dword ptr [rbp+4A0h+arg_10], 1
0x180240fd2  mov     byte ptr [rbp+4A0h+arg_10+4], 0
0x180240fd9  mov     ecx, 68h ; 'h'; Size
0x180240fde  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180240fe3  mov     rdi, rax
0x180240fe6  mov     [rbp+4A0h+arg_8], rax
0x180240fed  test    rax, rax
0x180240ff0  jz      short loc_180241042
0x180240ff2  mov     dword ptr [rax+8], 1
0x180240ff9  mov     dword ptr [rax+0Ch], 1
0x180241000  mov     [rax], rsi
0x180241003  mov     [rbp+4A0h+var_438], r13
0x180241007  mov     [rbp+4A0h+var_430], 0Fh
0x18024100f  mov     [rbp+4A0h+var_448], 0
0x180241013  mov     r8d, 3; Size
0x180241019  lea     rdx, aSum; "sum"
0x180241020  lea     rcx, [rbp+4A0h+var_448]; void *
0x180241024  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x180241029  xor     r9d, r9d
0x18024102c  lea     r8, [rbp+4A0h+arg_10]
0x180241033  lea     rdx, [rbp+4A0h+var_448]
0x180241037  lea     rcx, [rdi+10h]
0x18024103b  call    ??0ScalarAggregateFunction@compute@arrow@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUArity@12@PEBUFunctionOptions@12@@Z; arrow::compute::ScalarAggregateFunction::ScalarAggregateFunction(std::string,arrow::compute::Arity const &,arrow::compute::FunctionOptions const *)
0x180241040  jmp     short loc_180241045
0x180241042  mov     rdi, r13
0x180241045  lea     rsi, [rdi+10h]
0x180241049  mov     qword ptr [rsp+5A0h+var_580], rsi
0x18024104e  mov     qword ptr [rsp+5A0h+var_580+8], rdi
0x180241053  lea     rcx, [rbp+4A0h+var_4D0]
0x180241057  call    ?boolean@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::boolean(void)
0x18024105c  nop
0x18024105d  mov     [rsp+5A0h+var_568], r13
0x180241062  xorps   xmm0, xmm0
0x180241065  movdqu  [rsp+5A0h+var_560], xmm0
0x18024106b  movzx   r9d, byte ptr [rbp+4A0h+arg_8]
0x180241073  lea     r8, [rbp+4A0h+var_4C0]
0x180241077  lea     rdx, [rbp+4A0h+var_4D0]
0x18024107b  lea     rcx, [rsp+5A0h+var_568]
0x180241080  call    ??$_Range_construct_or_tidy@PEBV?$shared_ptr@VCastFunction@compute@arrow@@@std@@@?$vector@V?$shared_ptr@VCastFunction@compute@arrow@@@std@@V?$allocator@V?$shared_ptr@VCastFunction@compute@arrow@@@std@@@2@@std@@AEAAXPEBV?$shared_ptr@VCastFunction@compute@arrow@@@1@0Uforward_iterator_tag@1@@Z; std::vector<std::shared_ptr<arrow::compute::CastFunction>>::_Range_construct_or_tidy<std::shared_ptr<arrow::compute::CastFunction> const *>(std::shared_ptr<arrow::compute::CastFunction> const *,std::shared_ptr<arrow::compute::CastFunction> const *,std::forward_iterator_tag)
0x180241085  nop
0x180241086  lea     rcx, [rbp+4A0h+var_330]
0x18024108d  call    ?int64@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::int64(void)
0x180241092  lea     r14, ??_7?$_Func_impl_no_alloc@P6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@45@@ZV12@PEAV345@AEBU645@@std@@6B@; const std::_Func_impl_no_alloc<std::unique_ptr<arrow::compute::KernelState> (*)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),std::unique_ptr<arrow::compute::KernelState>,arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &>::`vftable'
0x180241099  mov     [rbp+4A0h+var_2B0], r14
0x1802410a0  lea     rcx, ?SumInit@aggregate@compute@arrow@@YA?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@23@AEBUKernelInitArgs@23@@Z; arrow::compute::aggregate::SumInit(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)
0x1802410a7  mov     [rbp+4A0h+var_2A8], rcx
0x1802410ae  lea     rcx, [rbp+4A0h+var_2B0]
0x1802410b5  mov     [rbp+4A0h+var_278], rcx
0x1802410bc  mov     r9, rsi
0x1802410bf  mov     r8, rax
0x1802410c2  lea     rdx, [rsp+5A0h+var_568]
0x1802410c7  lea     rcx, [rbp+4A0h+var_2B0]
0x1802410ce  call    ?AddBasicAggKernels@aggregate@compute@arrow@@YAXV?$function@$$A6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@45@@Z@std@@AEBV?$vector@V?$shared_ptr@VDataType@arrow@@@std@@V?$allocator@V?$shared_ptr@VDataType@arrow@@@std@@@2@@5@V?$shared_ptr@VDataType@arrow@@@5@PEAVScalarAggregateFunction@23@@Z; arrow::compute::aggregate::AddBasicAggKernels(std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>,std::vector<std::shared_ptr<arrow::DataType>> const &,std::shared_ptr<arrow::DataType>,arrow::compute::ScalarAggregateFunction *)
0x1802410d3  nop
0x1802410d4  mov     rbx, [rsp+5A0h+var_568]
0x1802410d9  test    rbx, rbx
0x1802410dc  jz      short loc_18024112A
0x1802410de  lea     r8, [rsp+5A0h+var_568]
0x1802410e3  mov     rdx, qword ptr [rsp+5A0h+var_560]
0x1802410e8  mov     rcx, rbx
0x1802410eb  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VChunkedArray@arrow@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VChunkedArray@arrow@@@0@0AEAV?$allocator@V?$shared_ptr@VChunkedArray@arrow@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<arrow::ChunkedArray>>>(std::shared_ptr<arrow::ChunkedArray> *,std::shared_ptr<arrow::ChunkedArray> *,std::allocator<std::shared_ptr<arrow::ChunkedArray>> &)
0x1802410f0  mov     rdx, qword ptr [rsp+5A0h+var_560+8]
0x1802410f5  sub     rdx, rbx
0x1802410f8  and     rdx, 0FFFFFFFFFFFFFFF0h
0x1802410fc  mov     rax, rbx
0x1802410ff  cmp     rdx, 1000h
0x180241106  jb      short loc_180241121
0x180241108  add     rdx, 27h ; '''; unsigned __int64
0x18024110c  mov     rbx, [rbx-8]
0x180241110  sub     rax, rbx
0x180241113  add     rax, 0FFFFFFFFFFFFFFF8h
0x180241117  cmp     rax, 1Fh
0x18024111b  ja      loc_180241744
0x180241121  mov     rcx, rbx; void *
0x180241124  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180241129  nop
0x18024112a  lea     r9, ??1?$TypedBufferBuilder@_JX@arrow@@QEAA@XZ; void (*)(void *)
0x180241131  mov     edx, 10h; unsigned __int64
0x180241136  lea     r8d, [rdx-0Fh]; unsigned __int64
0x18024113a  lea     rcx, [rbp+4A0h+var_4D0]; void *
0x18024113e  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180241143  lea     rax, [rbp+4A0h+var_320]
0x18024114a  mov     [rbp+4A0h+arg_8], rax
0x180241151  lea     rax, [rbp+4A0h+var_270]
0x180241158  mov     [rbp+4A0h+arg_10], rax
0x18024115f  lea     rcx, [rbp+4A0h+var_320]
0x180241166  call    ?int64@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::int64(void)
0x18024116b  mov     rbx, rax
0x18024116e  mov     [rbp+4A0h+var_270], r14
0x180241175  lea     rax, ?SumInit@aggregate@compute@arrow@@YA?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@23@AEBUKernelInitArgs@23@@Z; arrow::compute::aggregate::SumInit(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)
0x18024117c  mov     [rbp+4A0h+var_268], rax
0x180241183  lea     rax, [rbp+4A0h+var_270]
0x18024118a  mov     [rbp+4A0h+var_238], rax
0x180241191  call    ?SignedIntTypes@internal@compute@arrow@@YAAEBV?$vector@V?$shared_ptr@VDataType@arrow@@@std@@V?$allocator@V?$shared_ptr@VDataType@arrow@@@std@@@2@@std@@XZ; arrow::compute::internal::SignedIntTypes(void)
0x180241196  mov     rdx, rax
0x180241199  mov     r9, rsi
0x18024119c  mov     r8, rbx
0x18024119f  lea     rcx, [rbp+4A0h+var_270]
0x1802411a6  call    ?AddBasicAggKernels@aggregate@compute@arrow@@YAXV?$function@$$A6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@45@@Z@std@@AEBV?$vector@V?$shared_ptr@VDataType@arrow@@@std@@V?$allocator@V?$shared_ptr@VDataType@arrow@@@std@@@2@@5@V?$shared_ptr@VDataType@arrow@@@5@PEAVScalarAggregateFunction@23@@Z; arrow::compute::aggregate::AddBasicAggKernels(std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>,std::vector<std::shared_ptr<arrow::DataType>> const &,std::shared_ptr<arrow::DataType>,arrow::compute::ScalarAggregateFunction *)
0x1802411ab  lea     rax, [rbp+4A0h+var_3A0]
0x1802411b2  mov     [rbp+4A0h+arg_8], rax
0x1802411b9  lea     rax, [rbp+4A0h+var_230]
0x1802411c0  mov     [rbp+4A0h+arg_10], rax
0x1802411c7  lea     rcx, [rbp+4A0h+var_3A0]
0x1802411ce  call    ?uint64@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::uint64(void)
0x1802411d3  mov     rbx, rax
0x1802411d6  mov     [rbp+4A0h+var_230], r14
0x1802411dd  lea     rax, ?SumInit@aggregate@compute@arrow@@YA?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@23@AEBUKernelInitArgs@23@@Z; arrow::compute::aggregate::SumInit(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)
0x1802411e4  mov     [rbp+4A0h+var_228], rax
0x1802411eb  lea     rax, [rbp+4A0h+var_230]
0x1802411f2  mov     [rbp+4A0h+var_1F8], rax
0x1802411f9  call    ?UnsignedIntTypes@internal@compute@arrow@@YAAEBV?$vector@V?$shared_ptr@VDataType@arrow@@@std@@V?$allocator@V?$shared_ptr@VDataType@arrow@@@std@@@2@@std@@XZ; arrow::compute::internal::UnsignedIntTypes(void)
0x1802411fe  mov     rdx, rax
0x180241201  mov     r9, rsi
0x180241204  mov     r8, rbx
0x180241207  lea     rcx, [rbp+4A0h+var_230]
0x18024120e  call    ?AddBasicAggKernels@aggregate@compute@arrow@@YAXV?$function@$$A6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@45@@Z@std@@AEBV?$vector@V?$shared_ptr@VDataType@arrow@@@std@@V?$allocator@V?$shared_ptr@VDataType@arrow@@@std@@@2@@5@V?$shared_ptr@VDataType@arrow@@@5@PEAVScalarAggregateFunction@23@@Z; arrow::compute::aggregate::AddBasicAggKernels(std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>,std::vector<std::shared_ptr<arrow::DataType>> const &,std::shared_ptr<arrow::DataType>,arrow::compute::ScalarAggregateFunction *)
0x180241213  lea     rax, [rbp+4A0h+var_310]
0x18024121a  mov     [rbp+4A0h+arg_8], rax
0x180241221  lea     rax, [rbp+4A0h+var_1F0]
0x180241228  mov     [rbp+4A0h+arg_10], rax
0x18024122f  lea     rcx, [rbp+4A0h+var_310]
0x180241236  call    ?float64@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::float64(void)
0x18024123b  mov     rbx, rax
0x18024123e  mov     [rbp+4A0h+var_1F0], r14
0x180241245  lea     rax, ?SumInit@aggregate@compute@arrow@@YA?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@23@AEBUKernelInitArgs@23@@Z; arrow::compute::aggregate::SumInit(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)
0x18024124c  mov     [rbp+4A0h+var_1E8], rax
0x180241253  lea     rax, [rbp+4A0h+var_1F0]
0x18024125a  mov     [rbp+4A0h+var_1B8], rax
0x180241261  call    ?FloatingPointTypes@internal@compute@arrow@@YAAEBV?$vector@V?$shared_ptr@VDataType@arrow@@@std@@V?$allocator@V?$shared_ptr@VDataType@arrow@@@std@@@2@@std@@XZ; arrow::compute::internal::FloatingPointTypes(void)
0x180241266  mov     rdx, rax
0x180241269  mov     r9, rsi
0x18024126c  mov     r8, rbx
0x18024126f  lea     rcx, [rbp+4A0h+var_1F0]
0x180241276  call    ?AddBasicAggKernels@aggregate@compute@arrow@@YAXV?$function@$$A6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@45@@Z@std@@AEBV?$vector@V?$shared_ptr@VDataType@arrow@@@std@@V?$allocator@V?$shared_ptr@VDataType@arrow@@@std@@@2@@5@V?$shared_ptr@VDataType@arrow@@@5@PEAVScalarAggregateFunction@23@@Z; arrow::compute::aggregate::AddBasicAggKernels(std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>,std::vector<std::shared_ptr<arrow::DataType>> const &,std::shared_ptr<arrow::DataType>,arrow::compute::ScalarAggregateFunction *)
0x18024127b  mov     [rbp+4A0h+var_4C0], rsi
0x18024127f  mov     [rbp+4A0h+var_4B8], rdi
0x180241283  xorps   xmm0, xmm0
0x180241286  movdqu  [rsp+5A0h+var_580], xmm0
0x18024128c  xor     r9d, r9d
0x18024128f  lea     r8, [rbp+4A0h+var_4C0]
0x180241293  lea     rdx, [rbp+4A0h+var_300]
0x18024129a  mov     rcx, r12
0x18024129d  call    ?AddFunction@FunctionRegistry@compute@arrow@@QEAA?AVStatus@3@V?$shared_ptr@VFunction@compute@arrow@@@std@@_N@Z; arrow::compute::FunctionRegistry::AddFunction(std::shared_ptr<arrow::compute::Function>,bool)
0x1802412a2  mov     rcx, [rbp+4A0h+var_2F8]; this
0x1802412a9  test    rcx, rcx
0x1802412ac  jz      short loc_1802412B8
0x1802412ae  mov     edx, 1; unsigned int
0x1802412b3  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1802412b8  mov     [rbp+4A0h+arg_18], 1
0x1802412c2  mov     [rbp+4A0h+arg_1C], 0
0x1802412c9  mov     ecx, 68h ; 'h'; Size
0x1802412ce  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1802412d3  mov     rdi, rax
0x1802412d6  mov     [rbp+4A0h+arg_8], rax
0x1802412dd  test    rax, rax
0x1802412e0  jz      short loc_18024133F
  ... truncated ...
```
