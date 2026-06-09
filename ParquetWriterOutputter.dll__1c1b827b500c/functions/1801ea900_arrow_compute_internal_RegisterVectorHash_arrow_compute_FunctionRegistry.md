# arrow::compute::internal::RegisterVectorHash(arrow::compute::FunctionRegistry *)

- ea: `0x1801ea900`
- end: `0x1801eb34d`
- name: `?RegisterVectorHash@internal@compute@arrow@@YAXPEAVFunctionRegistry@23@@Z`
- size: `2637`
- prototype: `void __fastcall(arrow::compute::internal *__hidden this, struct arrow::compute::FunctionRegistry *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18012d690`

## callees

- `0x180010860`
- `0x18001f8c0`
- `0x1800d6280`
- `0x180127ce0`
- `0x180128390`
- `0x18012b8a0`
- `0x18012d340`
- `0x18012f8a0`
- `0x1801bfc30`
- `0x1801d3420`
- `0x1801d9ec0`
- `0x1801da010`
- `0x1801da9e0`
- `0x1801db3b0`
- `0x1801e75c0`
- `0x1801e7690`
- `0x1801ea900`
- `0x1802f0fb0`
- `0x18030c200`
- `0x18030c3f0`
- `0x180358070`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
void __fastcall arrow::compute::internal::RegisterVectorHash(
        arrow::compute::internal *this,
        struct arrow::compute::FunctionRegistry *a2)
{
  _QWORD *v3; // rdx
  _BYTE *v4; // rdx
  _QWORD *v5; // rdx
  _BYTE *v6; // r14
  const struct arrow::compute::OutputType *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  volatile signed __int32 *v14; // rbx
  volatile signed __int32 *v15; // rbx
  __int64 v16; // rax
  _DWORD *v17; // rax
  _DWORD *v18; // r14
  const struct arrow::compute::OutputType *v19; // rbx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rbx
  __int64 *v23; // rax
  __int64 v24; // rcx
  _BYTE *v25; // rdx
  volatile signed __int32 *v26; // rbx
  volatile signed __int32 *v27; // rbx
  __int64 v28; // rax
  _DWORD *v29; // rax
  _DWORD *v30; // r14
  const struct arrow::compute::OutputType *v31; // rbx
  __int64 v32; // rax
  _BYTE *v33; // rdx
  _BYTE *v34; // rdx
  _BYTE *v35; // rdx
  volatile signed __int32 *v36; // rbx
  int v37; // [rsp+28h] [rbp-E0h]
  int v38; // [rsp+28h] [rbp-E0h]
  int v39; // [rsp+38h] [rbp-D0h] BYREF
  char v40; // [rsp+3Ch] [rbp-CCh]
  _BYTE *v41; // [rsp+40h] [rbp-C8h] BYREF
  _BYTE *v42; // [rsp+48h] [rbp-C0h]
  int v43; // [rsp+50h] [rbp-B8h] BYREF
  char v44; // [rsp+54h] [rbp-B4h]
  _BYTE *v45; // [rsp+58h] [rbp-B0h]
  __int128 v46; // [rsp+60h] [rbp-A8h]
  __int128 v47; // [rsp+70h] [rbp-98h]
  _QWORD v48[2]; // [rsp+80h] [rbp-88h] BYREF
  _QWORD v49[2]; // [rsp+90h] [rbp-78h] BYREF
  _QWORD v50[2]; // [rsp+A0h] [rbp-68h] BYREF
  _DWORD v51[2]; // [rsp+B0h] [rbp-58h] BYREF
  __int128 v52; // [rsp+B8h] [rbp-50h]
  __int128 v53; // [rsp+C8h] [rbp-40h]
  _DWORD v54[2]; // [rsp+D8h] [rbp-30h] BYREF
  __int128 v55; // [rsp+E0h] [rbp-28h]
  __int128 v56; // [rsp+F0h] [rbp-18h]
  __int128 v57; // [rsp+100h] [rbp-8h] BYREF
  __int64 v58; // [rsp+110h] [rbp+8h]
  __int128 v59; // [rsp+118h] [rbp+10h] BYREF
  __int64 v60; // [rsp+128h] [rbp+20h]
  __int128 v61; // [rsp+130h] [rbp+28h]
  _BYTE v62[16]; // [rsp+140h] [rbp+38h] BYREF
  __int64 v63; // [rsp+150h] [rbp+48h]
  __int64 v64; // [rsp+158h] [rbp+50h]
  _BYTE v65[16]; // [rsp+160h] [rbp+58h] BYREF
  __int64 v66; // [rsp+170h] [rbp+68h]
  __int64 v67; // [rsp+178h] [rbp+70h]
  _BYTE v68[16]; // [rsp+180h] [rbp+78h] BYREF
  __int64 v69; // [rsp+190h] [rbp+88h]
  __int64 v70; // [rsp+198h] [rbp+90h]
  __int64 v71; // [rsp+1A0h] [rbp+98h]
  __int64 v72; // [rsp+1A8h] [rbp+A0h]
  _BYTE v73[16]; // [rsp+1B0h] [rbp+A8h] BYREF
  _BYTE v74[8]; // [rsp+1C0h] [rbp+B8h] BYREF
  volatile signed __int32 *v75; // [rsp+1C8h] [rbp+C0h]
  _BYTE v76[8]; // [rsp+1D0h] [rbp+C8h] BYREF
  arrow::Status::State *v77; // [rsp+1D8h] [rbp+D0h]
  _BYTE v78[16]; // [rsp+1E0h] [rbp+D8h] BYREF
  _BYTE v79[8]; // [rsp+1F0h] [rbp+E8h] BYREF
  volatile signed __int32 *v80; // [rsp+1F8h] [rbp+F0h]
  _BYTE v81[8]; // [rsp+200h] [rbp+F8h] BYREF
  arrow::Status::State *v82; // [rsp+208h] [rbp+100h]
  _BYTE v83[8]; // [rsp+210h] [rbp+108h] BYREF
  arrow::Status::State *v84; // [rsp+218h] [rbp+110h]
  _BYTE v85[8]; // [rsp+220h] [rbp+118h] BYREF
  arrow::Status::State *v86; // [rsp+228h] [rbp+120h]
  _BYTE v87[8]; // [rsp+230h] [rbp+128h] BYREF
  arrow::Status::State *v88; // [rsp+238h] [rbp+130h]
  _QWORD v89[8]; // [rsp+240h] [rbp+138h] BYREF
  _QWORD v90[8]; // [rsp+280h] [rbp+178h] BYREF
  _QWORD v91[8]; // [rsp+2C0h] [rbp+1B8h] BYREF
  _QWORD v92[8]; // [rsp+300h] [rbp+1F8h] BYREF
  _QWORD v93[8]; // [rsp+340h] [rbp+238h] BYREF
  _BYTE v94[96]; // [rsp+380h] [rbp+278h] BYREF
  _BYTE v95[96]; // [rsp+3E0h] [rbp+2D8h] BYREF
  _BYTE v96[96]; // [rsp+440h] [rbp+338h] BYREF
  _BYTE v97[96]; // [rsp+4A0h] [rbp+398h] BYREF
  _BYTE v98[96]; // [rsp+500h] [rbp+3F8h] BYREF
  _BYTE v99[240]; // [rsp+560h] [rbp+458h] BYREF
  _BYTE v100[240]; // [rsp+650h] [rbp+548h] BYREF
  _BYTE v101[240]; // [rsp+740h] [rbp+638h] BYREF
  _BYTE v102[240]; // [rsp+830h] [rbp+728h] BYREF
  _BYTE v103[248]; // [rsp+920h] [rbp+818h] BYREF
  __int128 v104; // [rsp+A18h] [rbp+910h] BYREF
  _BYTE v105[56]; // [rsp+A28h] [rbp+920h] BYREF
  _BYTE *v106; // [rsp+A60h] [rbp+958h]
  char v107; // [rsp+A68h] [rbp+960h]
  int v108; // [rsp+A6Ch] [rbp+964h]
  _BYTE v109[56]; // [rsp+A70h] [rbp+968h] BYREF
  _BYTE *v110; // [rsp+AA8h] [rbp+9A0h]
  char v111; // [rsp+AB0h] [rbp+9A8h]
  _BYTE v112[56]; // [rsp+AB8h] [rbp+9B0h] BYREF
  _BYTE *v113; // [rsp+AF0h] [rbp+9E8h]
  int v114; // [rsp+AF8h] [rbp+9F0h]
  int v115; // [rsp+AFCh] [rbp+9F4h]
  __int16 v116; // [rsp+B00h] [rbp+9F8h]
  _QWORD v117[7]; // [rsp+B08h] [rbp+A00h] BYREF
  _QWORD *v118; // [rsp+B40h] [rbp+A38h]
  _BYTE v119[56]; // [rsp+B48h] [rbp+A40h] BYREF
  _BYTE *v120; // [rsp+B80h] [rbp+A78h]

  v71 = -2;
  v104 = 0;
  v106 = 0;
  v107 = 1;
  v108 = 0;
  v110 = 0;
  v111 = 1;
  v113 = 0;
  v114 = 2;
  v115 = 1;
  v116 = 257;
  v117[0] = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v117[1] = arrow::compute::internal::_anonymous_namespace_::HashExec;
  v118 = v117;
  v120 = 0;
  v120 = (_BYTE *)std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::_Copy(
                    v117,
                    v119);
  if ( v118 )
  {
    v3 = v117;
    LOBYTE(v3) = v118 != v117;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v118 + 32LL))(v118, v3);
    v118 = 0;
  }
  std::_Func_class<void,arrow::compute::KernelContext *,std::vector<arrow::Datum> *>::_Reset_move(v117, v109);
  std::_Func_class<void,arrow::compute::KernelContext *,std::vector<arrow::Datum> *>::_Reset_move(v109, v119);
  if ( v120 )
  {
    v4 = v119;
    LOBYTE(v4) = v120 != v119;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v120 + 32LL))(v120, v4);
  }
  if ( v118 )
  {
    v5 = v117;
    LOBYTE(v5) = v118 != v117;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v118 + 32LL))(v118, v5);
  }
  std::function<void (arrow::compute::KernelContext *,std::vector<arrow::Datum> *)>::operator=<void (&)(arrow::compute::KernelContext *,std::vector<arrow::Datum> *),void>(
    v112,
    arrow::compute::internal::_anonymous_namespace_::UniqueFinalize);
  HIBYTE(v116) = 0;
  v43 = 1;
  v44 = 0;
  v6 = operator new(0x68u);
  v41 = v6;
  if ( v6 )
  {
    *((_DWORD *)v6 + 2) = 1;
    *((_DWORD *)v6 + 3) = 1;
    *(_QWORD *)v6 = &std::_Ref_count_obj<arrow::compute::VectorFunction>::`vftable';
    v63 = 0;
    v64 = 15;
    v62[0] = 0;
    std::string::assign(v62, "unique", 6u);
    arrow::compute::VectorFunction::VectorFunction(v6 + 16, v62, &v43, 0);
  }
  else
  {
    v6 = 0;
  }
  *(_QWORD *)&v46 = v6 + 16;
  *((_QWORD *)&v46 + 1) = v6;
  v89[0] = &std::_Func_impl_no_alloc<arrow::Result<arrow::ValueDescr> (*)(arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &),arrow::Result<arrow::ValueDescr>,arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &>::`vftable';
  v89[1] = arrow::compute::internal::FirstType;
  v89[7] = v89;
  v7 = (const struct arrow::compute::OutputType *)arrow::compute::OutputType::OutputType(v94, v89);
  v8 = arrow::compute::VectorKernel::VectorKernel(
         (arrow::compute::VectorKernel *)v100,
         (const struct arrow::compute::VectorKernel *)&v104);
  arrow::compute::internal::_anonymous_namespace_::AddHashKernels_arrow::compute::internal::_anonymous_namespace_::UniqueAction_(
    (__int64)(v6 + 16),
    v8,
    v7);
  std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>::operator=<std::unique_ptr<arrow::compute::KernelState> (&)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),void>(
    v105,
    arrow::compute::internal::_anonymous_namespace_::DictionaryHashInit_arrow::compute::internal::_anonymous_namespace_::UniqueAction_);
  std::function<void (arrow::compute::KernelContext *,std::vector<arrow::Datum> *)>::operator=<void (&)(arrow::compute::KernelContext *,std::vector<arrow::Datum> *),void>(
    v112,
    arrow::compute::internal::_anonymous_namespace_::UniqueFinalizeDictionary);
  v41 = v95;
  v9 = arrow::compute::match::SameTypeId(v73, 28);
  v54[0] = 2;
  v54[1] = 1;
  v55 = 0;
  v56 = 0;
  v56 = *(_OWORD *)v9;
  *(_QWORD *)v9 = 0;
  *(_QWORD *)(v9 + 8) = 0;
  v90[0] = &std::_Func_impl_no_alloc<arrow::Result<arrow::ValueDescr> (*)(arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &),arrow::Result<arrow::ValueDescr>,arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &>::`vftable';
  v90[1] = arrow::compute::internal::FirstType;
  v90[7] = v90;
  v10 = arrow::compute::OutputType::OutputType(v95, v90);
  v57 = 0;
  v58 = 0;
  std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(
    &v57,
    v54,
    &v57,
    (unsigned __int8)v37);
  v11 = (__int64 *)arrow::compute::KernelSignature::Make(v74, &v57, v10, 0, v37);
  v12 = *v11;
  v13 = v11[1];
  *v11 = 0;
  v11[1] = 0;
  *(_QWORD *)&v104 = v12;
  v72 = v13;
  v14 = (volatile signed __int32 *)*((_QWORD *)&v104 + 1);
  *((_QWORD *)&v104 + 1) = v13;
  if ( v14 )
  {
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  v15 = v75;
  if ( v75 )
  {
    if ( _InterlockedExchangeAdd(v75 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  `eh vector destructor iterator'(v54, 0x28u, 1u, (void (*)(void *))arrow::compute::InputType::~InputType);
  v16 = arrow::compute::VectorKernel::VectorKernel(
          (arrow::compute::VectorKernel *)v101,
          (const struct arrow::compute::VectorKernel *)&v104);
  arrow::compute::VectorFunction::AddKernel(v46, v76, v16);
  if ( v77 )
    arrow::Status::State::`scalar deleting destructor'(v77, 1u);
  v48[0] = v46;
  v48[1] = v6;
  v46 = 0;
  arrow::compute::FunctionRegistry::AddFunction(this, v87, v48, 0);
  if ( v88 )
    arrow::Status::State::`scalar deleting destructor'(v88, 1u);
  std::function<void (arrow::compute::KernelContext *,std::vector<arrow::Datum> *)>::operator=<void (&)(arrow::compute::KernelContext *,std::vector<arrow::Datum> *),void>(
    v112,
    arrow::compute::internal::_anonymous_namespace_::ValueCountsFinalize);
  v39 = 1;
  v40 = 0;
  v17 = operator new(0x68u);
  v18 = v17;
  if ( v17 )
  {
    v17[2] = 1;
    v17[3] = 1;
    *(_QWORD *)v17 = &std::_Ref_count_obj<arrow::compute::VectorFunction>::`vftable';
    v66 = 0;
    v67 = 15;
    v65[0] = 0;
    std::string::assign(v65, "value_counts", 0xCu);
    arrow::compute::VectorFunction::VectorFunction(v18 + 4, v65, &v39, 0);
  }
  else
  {
    v18 = 0;
  }
  *(_QWORD *)&v47 = v18 + 4;
  *((_QWORD *)&v47 + 1) = v18;
  v42 = v96;
  v91[0] = &std::_Func_impl_no_alloc<arrow::ValueDescr (*)(arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &),arrow::Result<arrow::ValueDescr>,arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &>::`vftable';
  v91[1] = arrow::compute::internal::_anonymous_namespace_::ValueCountsOutput;
  v91[7] = v91;
  v19 = (const struct arrow::compute::OutputType *)arrow::compute::OutputType::OutputType(v96, v91);
  v20 = arrow::compute::VectorKernel::VectorKernel(
          (arrow::compute::VectorKernel *)v102,
          (const struct arrow::compute::VectorKernel *)&v104);
  arrow::compute::internal::_anonymous_namespace_::AddHashKernels_arrow::compute::internal::_anonymous_namespace_::ValueCountsAction_(
    (__int64)(v18 + 4),
    v20,
    v19);
  std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>::operator=<std::unique_ptr<arrow::compute::KernelState> (&)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),void>(
    v105,
    arrow::compute::internal::_anonymous_namespace_::DictionaryHashInit_arrow::compute::internal::_anonymous_namespace_::ValueCountsAction_);
  std::function<void (arrow::compute::KernelContext *,std::vector<arrow::Datum> *)>::operator=<void (&)(arrow::compute::KernelContext *,std::vector<arrow::Datum> *),void>(
    v112,
    arrow::compute::internal::_anonymous_namespace_::ValueCountsFinalizeDictionary);
  v42 = v97;
  v21 = arrow::compute::match::SameTypeId(v78, 28);
  v51[0] = 2;
  v51[1] = 1;
  v52 = 0;
  v53 = 0;
  v53 = *(_OWORD *)v21;
  *(_QWORD *)v21 = 0;
  *(_QWORD *)(v21 + 8) = 0;
  v92[0] = &std::_Func_impl_no_alloc<arrow::ValueDescr (*)(arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &),arrow::Result<arrow::ValueDescr>,arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &>::`vftable';
  v92[1] = arrow::compute::internal::_anonymous_namespace_::ValueCountsOutput;
  v92[7] = v92;
  v22 = arrow::compute::OutputType::OutputType(v97, v92);
  v59 = 0;
  v60 = 0;
  std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(
    &v59,
    v51,
    v54,
    (unsigned __int8)v38);
  v23 = (__int64 *)arrow::compute::KernelSignature::Make(v79, &v59, v22, 0, v38);
  v24 = *v23;
  v25 = (_BYTE *)v23[1];
  *v23 = 0;
  v23[1] = 0;
  *(_QWORD *)&v104 = v24;
  v42 = v25;
  v26 = (volatile signed __int32 *)*((_QWORD *)&v104 + 1);
  *((_QWORD *)&v104 + 1) = v25;
  if ( v26 )
  {
    if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
      if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
    }
  }
  v27 = v80;
  if ( v80 )
  {
    if ( _InterlockedExchangeAdd(v80 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
      if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
    }
  }
  `eh vector destructor iterator'(v51, 0x28u, 1u, (void (*)(void *))arrow::compute::InputType::~InputType);
  v28 = arrow::compute::VectorKernel::VectorKernel(
          (arrow::compute::VectorKernel *)v103,
          (const struct arrow::compute::VectorKernel *)&v104);
  arrow::compute::VectorFunction::AddKernel(v47, v81, v28);
  if ( v82 )
    arrow::Status::State::`scalar deleting destructor'(v82, 1u);
  v49[0] = v47;
  v49[1] = v18;
  v47 = 0;
  arrow::compute::FunctionRegistry::AddFunction(this, v83, v49, 0);
  if ( v84 )
    arrow::Status::State::`scalar deleting destructor'(v84, 1u);
  std::function<void (arrow::compute::KernelContext *,std::vector<arrow::Datum> *)>::operator=<void (&)(arrow::compute::KernelContext *,std::vector<arrow::Datum> *),void>(
    v112,
    arrow::compute::internal::_anonymous_namespace_::DictEncodeFinalize);
  HIBYTE(v116) = 1;
  LODWORD(v41) = 1;
  BYTE4(v41) = 0;
  v29 = operator new(0x68u);
  v30 = v29;
  if ( v29 )
  {
    v29[2] = 1;
    v29[3] = 1;
    *(_QWORD *)v29 = &std::_Ref_count_obj<arrow::compute::VectorFunction>::`vftable';
    v69 = 0;
    v70 = 15;
    v68[0] = 0;
    std::string::assign(v68, "dictionary_encode", 0x11u);
    arrow::compute::VectorFunction::VectorFunction(v30 + 4, v68, &v41, 0);
  }
  else
  {
    v30 = 0;
  }
  *(_QWORD *)&v61 = v30 + 4;
  *((_QWORD *)&v61 + 1) = v30;
  v45 = v98;
  v93[0] = &std::_Func_impl_no_alloc<arrow::ValueDescr (*)(arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &),arrow::Result<arrow::ValueDescr>,arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &>::`vftable';
  v93[1] = arrow::compute::internal::_anonymous_namespace_::DictEncodeOutput;
  v93[7] = v93;
  v31 = (const struct arrow::compute::OutputType *)arrow::compute::OutputType::OutputType(v98, v93);
  v32 = arrow::compute::VectorKernel::VectorKernel(
          (arrow::compute::VectorKernel *)v99,
          (const struct arrow::compute::VectorKernel *)&v104);
  arrow::compute::internal::_anonymous_namespace_::AddHashKernels_arrow::compute::internal::_anonymous_namespace_::DictEncodeAction_(
    (__int64)(v30 + 4),
    v32,
    v31);
  v50[0] = v30 + 4;
  v50[1] = v30;
  v61 = 0;
  arrow::compute::FunctionRegistry::AddFunction(this, v85, v50, 0);
  if ( v86 )
    arrow::Status::State::`scalar deleting destructor'(v86, 1u);
  if ( v113 )
  {
    v33 = v112;
    LOBYTE(v33) = v113 != v112;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v113 + 32LL))(v113, v33);
    v113 = 0;
  }
  if ( v110 )
  {
    v34 = v109;
    LOBYTE(v34) = v110 != v109;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v110 + 32LL))(v110, v34);
    v110 = 0;
  }
  if ( v106 )
  {
    v35 = v105;
    LOBYTE(v35) = v106 != v105;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v106 + 32LL))(v106, v35);
    v106 = 0;
  }
  v36 = (volatile signed __int32 *)*((_QWORD *)&v104 + 1);
  if ( *((_QWORD *)&v104 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v104 + 1) + 8LL), 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v36)(v36);
    if ( _InterlockedExchangeAdd(v36 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v36 + 8LL))(v36);
  }
}

```

## disassembly

```asm
0x1801ea900  mov     rax, rsp
0x1801ea903  push    rbp
0x1801ea904  push    r12
0x1801ea906  push    r13
0x1801ea908  push    r14
0x1801ea90a  push    r15
0x1801ea90c  lea     rbp, [rax-0AB8h]
0x1801ea913  sub     rsp, 0B90h
0x1801ea91a  mov     [rbp+0AB0h+var_A18], 0FFFFFFFFFFFFFFFEh
0x1801ea925  mov     [rax+10h], rbx
0x1801ea929  mov     [rax+18h], rsi
0x1801ea92d  mov     [rax+20h], rdi
0x1801ea931  mov     rax, cs:__security_cookie
0x1801ea938  xor     rax, rsp
0x1801ea93b  mov     [rbp+0AB0h+var_30], rax
0x1801ea942  mov     r15, rcx
0x1801ea945  xorps   xmm0, xmm0
0x1801ea948  movdqa  [rbp+0AB0h+var_1A0], xmm0
0x1801ea950  xor     r13d, r13d
0x1801ea953  mov     [rbp+0AB0h+var_158], r13
0x1801ea95a  mov     [rbp+0AB0h+var_150], 1
0x1801ea961  mov     [rbp+0AB0h+var_14C], r13d
0x1801ea968  mov     [rbp+0AB0h+var_110], r13
0x1801ea96f  mov     [rbp+0AB0h+var_108], 1
0x1801ea976  mov     [rbp+0AB0h+var_C8], r13
0x1801ea97d  mov     [rbp+0AB0h+var_C0], 2
0x1801ea987  mov     [rbp+0AB0h+var_BC], 1
0x1801ea991  mov     [rbp+0AB0h+var_B8], 101h
0x1801ea99a  lea     rax, ??_7?$_Func_impl_no_alloc@P6AXPEAVKernelContext@compute@arrow@@AEBUExecBatch@23@PEAUDatum@3@@ZXPEAV123@AEBU423@PEAU53@@std@@6B@; const std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable'
0x1801ea9a1  mov     [rbp+0AB0h+var_B0], rax
0x1801ea9a8  lea     rax, arrow__compute__internal___anonymous_namespace___HashExec
0x1801ea9af  mov     [rbp+0AB0h+var_A8], rax
0x1801ea9b6  lea     rax, [rbp+0AB0h+var_B0]
0x1801ea9bd  mov     [rbp+0AB0h+var_78], rax
0x1801ea9c4  mov     [rbp+0AB0h+var_38], r13
0x1801ea9cb  lea     rdx, [rbp+0AB0h+var_70]
0x1801ea9d2  lea     rcx, [rbp+0AB0h+var_B0]
0x1801ea9d9  mov     rax, cs:off_180392358
0x1801ea9e0  call    cs:__guard_dispatch_icall_fptr
0x1801ea9e6  mov     [rbp+0AB0h+var_38], rax
0x1801ea9ed  mov     rcx, [rbp+0AB0h+var_78]
0x1801ea9f4  test    rcx, rcx
0x1801ea9f7  jz      short loc_1801EAA1A
0x1801ea9f9  mov     rax, [rcx]
0x1801ea9fc  lea     rdx, [rbp+0AB0h+var_B0]
0x1801eaa03  cmp     rcx, rdx
0x1801eaa06  setnz   dl
0x1801eaa09  mov     rax, [rax+20h]
0x1801eaa0d  call    cs:__guard_dispatch_icall_fptr
0x1801eaa13  mov     [rbp+0AB0h+var_78], r13
0x1801eaa1a  lea     rdx, [rbp+0AB0h+var_148]
0x1801eaa21  lea     rcx, [rbp+0AB0h+var_B0]
0x1801eaa28  call    ?_Reset_move@?$_Func_class@XPEAVKernelContext@compute@arrow@@PEAV?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@std@@@std@@IEAAX$$QEAV12@@Z; std::_Func_class<void,arrow::compute::KernelContext *,std::vector<arrow::Datum> *>::_Reset_move(std::_Func_class<void,arrow::compute::KernelContext *,std::vector<arrow::Datum> *> &&)
0x1801eaa2d  lea     rdx, [rbp+0AB0h+var_70]
0x1801eaa34  lea     rcx, [rbp+0AB0h+var_148]
0x1801eaa3b  call    ?_Reset_move@?$_Func_class@XPEAVKernelContext@compute@arrow@@PEAV?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@std@@@std@@IEAAX$$QEAV12@@Z; std::_Func_class<void,arrow::compute::KernelContext *,std::vector<arrow::Datum> *>::_Reset_move(std::_Func_class<void,arrow::compute::KernelContext *,std::vector<arrow::Datum> *> &&)
0x1801eaa40  mov     rcx, [rbp+0AB0h+var_38]
0x1801eaa47  test    rcx, rcx
0x1801eaa4a  jz      short loc_1801EAA67
0x1801eaa4c  mov     rax, [rcx]
0x1801eaa4f  lea     rdx, [rbp+0AB0h+var_70]
0x1801eaa56  cmp     rcx, rdx
0x1801eaa59  setnz   dl
0x1801eaa5c  mov     rax, [rax+20h]
0x1801eaa60  call    cs:__guard_dispatch_icall_fptr
0x1801eaa66  nop
0x1801eaa67  mov     rcx, [rbp+0AB0h+var_78]
0x1801eaa6e  test    rcx, rcx
0x1801eaa71  jz      short loc_1801EAA8D
0x1801eaa73  mov     rax, [rcx]
0x1801eaa76  lea     rdx, [rbp+0AB0h+var_B0]
0x1801eaa7d  cmp     rcx, rdx
0x1801eaa80  setnz   dl
0x1801eaa83  mov     rax, [rax+20h]
0x1801eaa87  call    cs:__guard_dispatch_icall_fptr
0x1801eaa8d  lea     rdx, arrow__compute__internal___anonymous_namespace___UniqueFinalize
0x1801eaa94  lea     rcx, [rbp+0AB0h+var_100]
0x1801eaa9b  call    ??$?4A6AXPEAVKernelContext@compute@arrow@@PEAV?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@std@@@ZX@?$function@$$A6AXPEAVKernelContext@compute@arrow@@PEAV?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@std@@@Z@std@@QEAAAEAV01@A6AXPEAVKernelContext@compute@arrow@@PEAV?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@1@@Z@Z; std::function<void (arrow::compute::KernelContext *,std::vector<arrow::Datum> *)>::operator=<void (&)(arrow::compute::KernelContext *,std::vector<arrow::Datum> *),void>(void (&)(arrow::compute::KernelContext *,std::vector<arrow::Datum> *))
0x1801eaaa0  mov     byte ptr [rbp+0AB0h+var_B8+1], 0
0x1801eaaa7  mov     dword ptr [rsp+0BB0h+var_B68], 1
0x1801eaaaf  mov     byte ptr [rsp+0BB0h+var_B68+4], 0
0x1801eaab4  mov     ecx, 68h ; 'h'; Size
0x1801eaab9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801eaabe  mov     r14, rax
0x1801eaac1  mov     [rsp+0BB0h+var_B78], rax
0x1801eaac6  lea     rax, ??_7?$_Ref_count_obj@VVectorFunction@compute@arrow@@@std@@6B@; const std::_Ref_count_obj<arrow::compute::VectorFunction>::`vftable'
0x1801eaacd  test    r14, r14
0x1801eaad0  jz      short loc_1801EAB22
0x1801eaad2  mov     dword ptr [r14+8], 1
0x1801eaada  mov     dword ptr [r14+0Ch], 1
0x1801eaae2  mov     [r14], rax
0x1801eaae5  mov     [rbp+0AB0h+var_A68], r13
0x1801eaae9  mov     [rbp+0AB0h+var_A60], 0Fh
0x1801eaaf1  mov     [rbp+0AB0h+var_A78], 0
0x1801eaaf5  mov     r8d, 6; Size
0x1801eaafb  lea     rdx, aUnique; "unique"
0x1801eab02  lea     rcx, [rbp+0AB0h+var_A78]; void *
0x1801eab06  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1801eab0b  xor     r9d, r9d
0x1801eab0e  lea     r8, [rsp+0BB0h+var_B68]
0x1801eab13  lea     rdx, [rbp+0AB0h+var_A78]
0x1801eab17  lea     rcx, [r14+10h]
0x1801eab1b  call    ??0VectorFunction@compute@arrow@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUArity@12@PEBUFunctionOptions@12@@Z; arrow::compute::VectorFunction::VectorFunction(std::string,arrow::compute::Arity const &,arrow::compute::FunctionOptions const *)
0x1801eab20  jmp     short loc_1801EAB25
0x1801eab22  mov     r14, r13
0x1801eab25  lea     rdi, [r14+10h]
0x1801eab29  mov     qword ptr [rsp+0BB0h+var_B60+8], rdi
0x1801eab2e  mov     qword ptr [rsp+0BB0h+var_B50], r14
0x1801eab33  lea     rax, [rbp+0AB0h+var_838]
0x1801eab3a  mov     [rsp+0BB0h+var_B78], rax
0x1801eab3f  lea     r12, ??_7?$_Func_impl_no_alloc@P6A?AV?$Result@UValueDescr@arrow@@@arrow@@PEAVKernelContext@compute@2@AEBV?$vector@UValueDescr@arrow@@V?$allocator@UValueDescr@arrow@@@std@@@std@@@ZV12@PEAV342@AEBV56@@std@@6B@; const std::_Func_impl_no_alloc<arrow::Result<arrow::ValueDescr> (*)(arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &),arrow::Result<arrow::ValueDescr>,arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &>::`vftable'
0x1801eab46  mov     [rbp+0AB0h+var_978], r12
0x1801eab4d  lea     rsi, ?FirstType@internal@compute@arrow@@YA?AV?$Result@UValueDescr@arrow@@@3@PEAVKernelContext@23@AEBV?$vector@UValueDescr@arrow@@V?$allocator@UValueDescr@arrow@@@std@@@std@@@Z; arrow::compute::internal::FirstType(arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &)
0x1801eab54  mov     [rbp+0AB0h+var_970], rsi
0x1801eab5b  lea     rax, [rbp+0AB0h+var_978]
0x1801eab62  mov     [rbp+0AB0h+var_940], rax
0x1801eab69  lea     rdx, [rbp+0AB0h+var_978]
0x1801eab70  lea     rcx, [rbp+0AB0h+var_838]
0x1801eab77  call    ??0OutputType@compute@arrow@@QEAA@V?$function@$$A6A?AV?$Result@UValueDescr@arrow@@@arrow@@PEAVKernelContext@compute@2@AEBV?$vector@UValueDescr@arrow@@V?$allocator@UValueDescr@arrow@@@std@@@std@@@Z@std@@@Z; arrow::compute::OutputType::OutputType(std::function<arrow::Result<arrow::ValueDescr> (arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &)>)
0x1801eab7c  mov     rbx, rax
0x1801eab7f  lea     rdx, [rbp+0AB0h+var_1A0]; struct arrow::compute::VectorKernel *
0x1801eab86  lea     rcx, [rbp+0AB0h+var_568]; this
0x1801eab8d  call    ??0VectorKernel@compute@arrow@@QEAA@AEBU012@@Z; arrow::compute::VectorKernel::VectorKernel(arrow::compute::VectorKernel const &)
0x1801eab92  nop
0x1801eab93  mov     r8, rbx
0x1801eab96  mov     rdx, rax
0x1801eab99  mov     rcx, rdi
0x1801eab9c  call    arrow__compute__internal___anonymous_namespace___AddHashKernels_arrow__compute__internal___anonymous_namespace___UniqueAction_
0x1801eaba1  lea     rdx, arrow__compute__internal___anonymous_namespace___DictionaryHashInit_arrow__compute__internal___anonymous_namespace___UniqueAction_
0x1801eaba8  lea     rcx, [rbp+0AB0h+var_190]
0x1801eabaf  call    ??$?4A6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@34@@ZX@?$function@$$A6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@45@@Z@std@@QEAAAEAV01@A6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@1@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@45@@Z@Z; std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>::operator=<std::unique_ptr<arrow::compute::KernelState> (&)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),void>(std::unique_ptr<arrow::compute::KernelState> (&)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &))
0x1801eabb4  lea     rdx, arrow__compute__internal___anonymous_namespace___UniqueFinalizeDictionary
0x1801eabbb  lea     rcx, [rbp+0AB0h+var_100]
0x1801eabc2  call    ??$?4A6AXPEAVKernelContext@compute@arrow@@PEAV?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@std@@@ZX@?$function@$$A6AXPEAVKernelContext@compute@arrow@@PEAV?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@std@@@Z@std@@QEAAAEAV01@A6AXPEAVKernelContext@compute@arrow@@PEAV?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@1@@Z@Z; std::function<void (arrow::compute::KernelContext *,std::vector<arrow::Datum> *)>::operator=<void (&)(arrow::compute::KernelContext *,std::vector<arrow::Datum> *),void>(void (&)(arrow::compute::KernelContext *,std::vector<arrow::Datum> *))
0x1801eabc7  lea     rax, [rbp+0AB0h+var_7D8]
0x1801eabce  mov     [rsp+0BB0h+var_B78], rax
0x1801eabd3  mov     edx, 1Ch
0x1801eabd8  lea     rcx, [rbp+0AB0h+var_A08]
0x1801eabdf  call    ?SameTypeId@match@compute@arrow@@YA?AV?$shared_ptr@UTypeMatcher@compute@arrow@@@std@@W4type@Type@3@@Z; arrow::compute::match::SameTypeId(arrow::Type::type)
0x1801eabe4  mov     [rbp+0AB0h+var_AE0], 2
0x1801eabeb  mov     [rbp+0AB0h+var_ADC], 1
0x1801eabf2  xorps   xmm0, xmm0
0x1801eabf5  movdqu  [rbp+0AB0h+var_AD8], xmm0
0x1801eabfa  xorps   xmm1, xmm1
0x1801eabfd  movdqu  [rbp+0AB0h+var_AC8], xmm1
0x1801eac02  mov     rcx, [rax]
0x1801eac05  mov     qword ptr [rbp+0AB0h+var_AC8], rcx
0x1801eac09  mov     rcx, [rax+8]
0x1801eac0d  mov     qword ptr [rbp+0AB0h+var_AC8+8], rcx
0x1801eac11  mov     [rax], r13
0x1801eac14  mov     [rax+8], r13
0x1801eac18  mov     [rbp+0AB0h+var_938], r12
0x1801eac1f  mov     [rbp+0AB0h+var_930], rsi
0x1801eac26  lea     rax, [rbp+0AB0h+var_938]
0x1801eac2d  mov     [rbp+0AB0h+var_900], rax
0x1801eac34  lea     rdx, [rbp+0AB0h+var_938]
0x1801eac3b  lea     rcx, [rbp+0AB0h+var_7D8]
0x1801eac42  call    ??0OutputType@compute@arrow@@QEAA@V?$function@$$A6A?AV?$Result@UValueDescr@arrow@@@arrow@@PEAVKernelContext@compute@2@AEBV?$vector@UValueDescr@arrow@@V?$allocator@UValueDescr@arrow@@@std@@@std@@@Z@std@@@Z; arrow::compute::OutputType::OutputType(std::function<arrow::Result<arrow::ValueDescr> (arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &)>)
0x1801eac47  mov     rbx, rax
0x1801eac4a  xorps   xmm0, xmm0
0x1801eac4d  movdqu  [rbp+0AB0h+var_AB8], xmm0
0x1801eac52  mov     [rbp+0AB0h+var_AA8], r13
0x1801eac56  movzx   r9d, byte ptr [rsp+0BB0h+var_B90]
0x1801eac5c  lea     r8, [rbp+0AB0h+var_AB8]
0x1801eac60  lea     rdx, [rbp+0AB0h+var_AE0]
0x1801eac64  lea     rcx, [rbp+0AB0h+var_AB8]
0x1801eac68  call    ??$_Range_construct_or_tidy@PEBVInputType@compute@arrow@@@?$vector@VInputType@compute@arrow@@V?$allocator@VInputType@compute@arrow@@@std@@@std@@AEAAXPEBVInputType@compute@arrow@@0Uforward_iterator_tag@1@@Z; std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(arrow::compute::InputType const *,arrow::compute::InputType const *,std::forward_iterator_tag)
0x1801eac6d  nop
0x1801eac6e  xor     r9d, r9d
0x1801eac71  mov     r8, rbx
0x1801eac74  lea     rdx, [rbp+0AB0h+var_AB8]
0x1801eac78  lea     rcx, [rbp+0AB0h+var_9F8]
0x1801eac7f  call    ?Make@KernelSignature@compute@arrow@@SA?AV?$shared_ptr@VKernelSignature@compute@arrow@@@std@@V?$vector@VInputType@compute@arrow@@V?$allocator@VInputType@compute@arrow@@@std@@@5@VOutputType@23@_N@Z; arrow::compute::KernelSignature::Make(std::vector<arrow::compute::InputType>,arrow::compute::OutputType,bool)
0x1801eac84  mov     rcx, [rax]
0x1801eac87  mov     rdx, [rax+8]
0x1801eac8b  mov     [rax], r13
0x1801eac8e  mov     [rax+8], r13
0x1801eac92  mov     qword ptr [rbp+0AB0h+var_1A0], rcx
0x1801eac99  mov     [rbp+0AB0h+var_A10], rdx
0x1801eaca0  mov     rbx, qword ptr [rbp+0AB0h+var_1A0+8]
0x1801eaca7  mov     qword ptr [rbp+0AB0h+var_1A0+8], rdx
0x1801eacae  mov     esi, 0FFFFFFFFh
0x1801eacb3  test    rbx, rbx
0x1801eacb6  jz      short loc_1801EACEF
0x1801eacb8  mov     eax, esi
0x1801eacba  lock xadd [rbx+8], eax
0x1801eacbf  cmp     eax, 1
0x1801eacc2  jnz     short loc_1801EACEF
0x1801eacc4  mov     rax, [rbx]
0x1801eacc7  mov     rcx, rbx
0x1801eacca  mov     rax, [rax]
0x1801eaccd  call    cs:__guard_dispatch_icall_fptr
0x1801eacd3  mov     eax, esi
0x1801eacd5  lock xadd [rbx+0Ch], eax
0x1801eacda  cmp     eax, 1
0x1801eacdd  jnz     short loc_1801EACEF
0x1801eacdf  mov     rax, [rbx]
0x1801eace2  mov     rcx, rbx
0x1801eace5  mov     rax, [rax+8]
0x1801eace9  call    cs:__guard_dispatch_icall_fptr
0x1801eacef  mov     rbx, [rbp+0AB0h+var_9F0]
0x1801eacf6  test    rbx, rbx
0x1801eacf9  jz      short loc_1801EAD33
0x1801eacfb  mov     eax, esi
0x1801eacfd  lock xadd [rbx+8], eax
0x1801ead02  cmp     eax, 1
0x1801ead05  jnz     short loc_1801EAD33
0x1801ead07  mov     rax, [rbx]
0x1801ead0a  mov     rcx, rbx
0x1801ead0d  mov     rax, [rax]
0x1801ead10  call    cs:__guard_dispatch_icall_fptr
0x1801ead16  mov     eax, esi
0x1801ead18  lock xadd [rbx+0Ch], eax
0x1801ead1d  cmp     eax, 1
0x1801ead20  jnz     short loc_1801EAD33
0x1801ead22  mov     rax, [rbx]
0x1801ead25  mov     rcx, rbx
0x1801ead28  mov     rax, [rax+8]
0x1801ead2c  call    cs:__guard_dispatch_icall_fptr
0x1801ead32  nop
0x1801ead33  lea     r9, ??1InputType@compute@arrow@@QEAA@XZ; void (*)(void *)
0x1801ead3a  mov     edx, 28h ; '('; unsigned __int64
0x1801ead3f  lea     r8d, [rdx-27h]; unsigned __int64
0x1801ead43  lea     rcx, [rbp+0AB0h+var_AE0]; void *
0x1801ead47  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1801ead4c  lea     rdx, [rbp+0AB0h+var_1A0]; struct arrow::compute::VectorKernel *
0x1801ead53  lea     rcx, [rbp+0AB0h+var_478]; this
0x1801ead5a  call    ??0VectorKernel@compute@arrow@@QEAA@AEBU012@@Z; arrow::compute::VectorKernel::VectorKernel(arrow::compute::VectorKernel const &)
0x1801ead5f  mov     r8, rax
0x1801ead62  lea     rdx, [rbp+0AB0h+var_9E8]
0x1801ead69  mov     rcx, qword ptr [rsp+0BB0h+var_B60+8]
0x1801ead6e  call    ?AddKernel@VectorFunction@compute@arrow@@QEAA?AVStatus@3@UVectorKernel@23@@Z; arrow::compute::VectorFunction::AddKernel(arrow::compute::VectorKernel)
0x1801ead73  mov     rcx, [rbp+0AB0h+var_9E0]; this
0x1801ead7a  test    rcx, rcx
0x1801ead7d  jz      short loc_1801EAD89
0x1801ead7f  mov     edx, 1; unsigned int
0x1801ead84  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1801ead89  mov     rax, qword ptr [rsp+0BB0h+var_B60+8]
0x1801ead8e  mov     [rsp+0BB0h+var_B38], rax
0x1801ead93  mov     [rbp+0AB0h+var_B30], r14
0x1801ead97  xorps   xmm0, xmm0
0x1801ead9a  movdqu  [rsp+0BB0h+var_B60+8], xmm0
0x1801eada0  xor     r9d, r9d
0x1801eada3  lea     r8, [rsp+0BB0h+var_B38]
0x1801eada8  lea     rdx, [rbp+0AB0h+var_988]
0x1801eadaf  mov     rcx, r15
0x1801eadb2  call    ?AddFunction@FunctionRegistry@compute@arrow@@QEAA?AVStatus@3@V?$shared_ptr@VFunction@compute@arrow@@@std@@_N@Z; arrow::compute::FunctionRegistry::AddFunction(std::shared_ptr<arrow::compute::Function>,bool)
0x1801eadb7  mov     rcx, [rbp+0AB0h+var_980]; this
0x1801eadbe  test    rcx, rcx
0x1801eadc1  jz      short loc_1801EADCD
0x1801eadc3  mov     edx, 1; unsigned int
0x1801eadc8  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1801eadcd  lea     rdx, arrow__compute__internal___anonymous_namespace___ValueCountsFinalize
0x1801eadd4  lea     rcx, [rbp+0AB0h+var_100]
0x1801eaddb  call    ??$?4A6AXPEAVKernelContext@compute@arrow@@PEAV?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@std@@@ZX@?$function@$$A6AXPEAVKernelContext@compute@arrow@@PEAV?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@std@@@Z@std@@QEAAAEAV01@A6AXPEAVKernelContext@compute@arrow@@PEAV?$vector@UDatum@arrow@@V?$allocator@UDatum@arrow@@@std@@@1@@Z@Z; std::function<void (arrow::compute::KernelContext *,std::vector<arrow::Datum> *)>::operator=<void (&)(arrow::compute::KernelContext *,std::vector<arrow::Datum> *),void>(void (&)(arrow::compute::KernelContext *,std::vector<arrow::Datum> *))
0x1801eade0  mov     dword ptr [rsp+0BB0h+var_B80], 1
0x1801eade8  mov     byte ptr [rsp+0BB0h+var_B80+4], 0
0x1801eaded  mov     ecx, 68h ; 'h'; Size
0x1801eadf2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801eadf7  mov     r14, rax
0x1801eadfa  mov     qword ptr [rsp+0BB0h+var_B88], rax
0x1801eadff  test    rax, rax
0x1801eae02  jz      short loc_1801EAE59
0x1801eae04  mov     dword ptr [rax+8], 1
0x1801eae0b  mov     dword ptr [rax+0Ch], 1
0x1801eae12  lea     rax, ??_7?$_Ref_count_obj@VVectorFunction@compute@arrow@@@std@@6B@; const std::_Ref_count_obj<arrow::compute::VectorFunction>::`vftable'
0x1801eae19  mov     [r14], rax
0x1801eae1c  mov     [rbp+0AB0h+var_A48], r13
0x1801eae20  mov     [rbp+0AB0h+var_A40], 0Fh
0x1801eae28  mov     [rbp+0AB0h+var_A58], 0
0x1801eae2c  mov     r8d, 0Ch; Size
0x1801eae32  lea     rdx, aValueCounts; "value_counts"
0x1801eae39  lea     rcx, [rbp+0AB0h+var_A58]; void *
0x1801eae3d  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1801eae42  xor     r9d, r9d
0x1801eae45  lea     r8, [rsp+0BB0h+var_B80]
0x1801eae4a  lea     rdx, [rbp+0AB0h+var_A58]
0x1801eae4e  lea     rcx, [r14+10h]
0x1801eae52  call    ??0VectorFunction@compute@arrow@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUArity@12@PEBUFunctionOptions@12@@Z; arrow::compute::VectorFunction::VectorFunction(std::string,arrow::compute::Arity const &,arrow::compute::FunctionOptions const *)
0x1801eae57  jmp     short loc_1801EAE5C
0x1801eae59  mov     r14, r13
0x1801eae5c  lea     rdi, [r14+10h]
0x1801eae60  mov     qword ptr [rsp+0BB0h+var_B50+8], rdi
0x1801eae65  mov     [rsp+0BB0h+var_B40], r14
0x1801eae6a  lea     rax, [rbp+0AB0h+var_778]
0x1801eae71  mov     [rsp+0BB0h+var_B70], rax
0x1801eae76  lea     rax, ??_7?$_Func_impl_no_alloc@P6A?AUValueDescr@arrow@@PEAVKernelContext@compute@2@AEBV?$vector@UValueDescr@arrow@@V?$allocator@UValueDescr@arrow@@@std@@@std@@@ZV?$Result@UValueDescr@arrow@@@2@PEAV342@AEBV56@@std@@6B@; const std::_Func_impl_no_alloc<arrow::ValueDescr (*)(arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &),arrow::Result<arrow::ValueDescr>,arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &>::`vftable'
0x1801eae7d  mov     [rbp+0AB0h+var_8F8], rax
0x1801eae84  lea     r12, arrow__compute__internal___anonymous_namespace___ValueCountsOutput
0x1801eae8b  mov     [rbp+0AB0h+var_8F0], r12
0x1801eae92  lea     rax, [rbp+0AB0h+var_8F8]
0x1801eae99  mov     [rbp+0AB0h+var_8C0], rax
0x1801eaea0  lea     rdx, [rbp+0AB0h+var_8F8]
0x1801eaea7  lea     rcx, [rbp+0AB0h+var_778]
0x1801eaeae  call    ??0OutputType@compute@arrow@@QEAA@V?$function@$$A6A?AV?$Result@UValueDescr@arrow@@@arrow@@PEAVKernelContext@compute@2@AEBV?$vector@UValueDescr@arrow@@V?$allocator@UValueDescr@arrow@@@std@@@std@@@Z@std@@@Z; arrow::compute::OutputType::OutputType(std::function<arrow::Result<arrow::ValueDescr> (arrow::compute::KernelContext *,std::vector<arrow::ValueDescr> const &)>)
0x1801eaeb3  mov     rbx, rax
0x1801eaeb6  lea     rdx, [rbp+0AB0h+var_1A0]; struct arrow::compute::VectorKernel *
0x1801eaebd  lea     rcx, [rbp+0AB0h+var_388]; this
0x1801eaec4  call    ??0VectorKernel@compute@arrow@@QEAA@AEBU012@@Z; arrow::compute::VectorKernel::VectorKernel(arrow::compute::VectorKernel const &)
0x1801eaec9  nop
  ... truncated ...
```
