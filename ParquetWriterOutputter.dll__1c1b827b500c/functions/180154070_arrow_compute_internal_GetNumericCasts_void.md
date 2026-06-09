# arrow::compute::internal::GetNumericCasts(void)

- ea: `0x180154070`
- end: `0x180154e02`
- name: `?GetNumericCasts@internal@compute@arrow@@YA?AV?$vector@V?$shared_ptr@VCastFunction@compute@arrow@@@std@@V?$allocator@V?$shared_ptr@VCastFunction@compute@arrow@@@std@@@2@@std@@XZ`
- size: `3474`
- prototype: ``
- caller_count: `1`
- callee_count: `33`
- tags: `broker_com_uri`

## callers

- `0x1800d5e20`

## callees

- `0x180010640`
- `0x180010860`
- `0x18001f8c0`
- `0x1800a1f90`
- `0x1800a2170`
- `0x1800a8f00`
- `0x1800a9500`
- `0x1800a99c0`
- `0x1800a9af0`
- `0x1800aad60`
- `0x1800d33f0`
- `0x1800d4420`
- `0x180128390`
- `0x18012f8a0`
- `0x18012fa90`
- `0x18013c210`
- `0x18013c770`
- `0x18013ccd0`
- `0x18013d230`
- `0x18013d790`
- `0x18013dcf0`
- `0x18013e250`
- `0x18013e7b0`
- `0x18013ed10`
- `0x18013f270`
- `0x18014ac20`
- `0x180153950`
- `0x180154070`
- `0x1802502d0`
- `0x1802506d0`
- `0x1802f0fb0`
- `0x18030c200`
- `0x180358070`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
_QWORD *__fastcall arrow::compute::internal::GetNumericCasts(_QWORD *a1)
{
  volatile signed __int32 *v2; // rax
  volatile signed __int32 *v3; // rsi
  __int64 v4; // rax
  __int64 v5; // rax
  arrow::compute::OutputType *v6; // rbx
  _QWORD *v7; // rdx
  _QWORD *v8; // rax
  _QWORD *v9; // rdx
  volatile signed __int32 *v10; // rbx
  _QWORD *v11; // rax
  _QWORD *v12; // rdx
  volatile signed __int32 *v13; // rbx
  __int64 v14; // rax
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rbx
  __int64 v20; // rax
  _QWORD *v21; // rdx
  __int64 v22; // rax
  __int64 v23; // rbx
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rbx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rbx
  __int64 v33; // rax
  _QWORD *v34; // rdx
  _QWORD *v35; // rax
  _QWORD *v36; // rdx
  volatile signed __int32 *v37; // rbx
  _QWORD *v38; // rax
  _QWORD *v39; // rdx
  volatile signed __int32 *v40; // rbx
  _QWORD *v41; // rax
  _QWORD *v42; // rdx
  volatile signed __int32 *v43; // rbx
  _QWORD *v44; // rax
  _QWORD *v45; // rdx
  volatile signed __int32 *v46; // rbx
  volatile signed __int32 *v47; // rax
  volatile signed __int32 *v48; // rsi
  std::_Ref_count_base *v49; // rbx
  __int64 v50; // rax
  __int64 v51; // rax
  _QWORD *v52; // rdx
  _QWORD *v53; // rax
  _QWORD *v54; // rdx
  _QWORD *v55; // rax
  _QWORD *v56; // rdx
  _QWORD *CastToDecimal; // rax
  _QWORD *v58; // rdx
  __int64 v60; // [rsp+48h] [rbp-B8h] BYREF
  std::_Ref_count_base *v61; // [rsp+50h] [rbp-B0h]
  __int64 v62; // [rsp+58h] [rbp-A8h] BYREF
  std::_Ref_count_base *v63; // [rsp+60h] [rbp-A0h]
  volatile signed __int32 *v64; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v65; // [rsp+70h] [rbp-90h]
  volatile signed __int32 *v66; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v67; // [rsp+80h] [rbp-80h]
  _DWORD v68[2]; // [rsp+88h] [rbp-78h] BYREF
  __int128 v69; // [rsp+90h] [rbp-70h]
  __int128 v70; // [rsp+A0h] [rbp-60h]
  int v71[4]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v72; // [rsp+C0h] [rbp-40h]
  __int64 v73; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v74; // [rsp+D0h] [rbp-30h]
  __int128 v75; // [rsp+E0h] [rbp-20h]
  __int64 v76; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v77; // [rsp+F8h] [rbp-8h]
  __int128 v78; // [rsp+108h] [rbp+8h]
  __int64 v79; // [rsp+118h] [rbp+18h] BYREF
  __int128 v80; // [rsp+120h] [rbp+20h]
  __int128 v81; // [rsp+130h] [rbp+30h]
  __int64 v82; // [rsp+140h] [rbp+40h] BYREF
  __int128 v83; // [rsp+148h] [rbp+48h]
  __int128 v84; // [rsp+158h] [rbp+58h]
  __int64 v85; // [rsp+168h] [rbp+68h] BYREF
  __int128 v86; // [rsp+170h] [rbp+70h]
  __int128 v87; // [rsp+180h] [rbp+80h]
  _BYTE v88[16]; // [rsp+190h] [rbp+90h] BYREF
  __int64 v89; // [rsp+1A0h] [rbp+A0h]
  __int64 v90; // [rsp+1A8h] [rbp+A8h]
  int v91; // [rsp+1B0h] [rbp+B0h] BYREF
  arrow::Status::State *v92; // [rsp+1B8h] [rbp+B8h]
  _BYTE v93[16]; // [rsp+1C0h] [rbp+C0h] BYREF
  __int64 v94; // [rsp+1D0h] [rbp+D0h]
  __int64 v95; // [rsp+1D8h] [rbp+D8h]
  _BYTE v96[16]; // [rsp+1E0h] [rbp+E0h] BYREF
  __int64 v97; // [rsp+1F0h] [rbp+F0h]
  __int64 v98; // [rsp+1F8h] [rbp+F8h]
  _BYTE v99[16]; // [rsp+200h] [rbp+100h] BYREF
  __int64 v100; // [rsp+210h] [rbp+110h]
  __int64 v101; // [rsp+218h] [rbp+118h]
  _BYTE v102[16]; // [rsp+220h] [rbp+120h] BYREF
  __int64 v103; // [rsp+230h] [rbp+130h]
  __int64 v104; // [rsp+238h] [rbp+138h]
  _BYTE v105[16]; // [rsp+240h] [rbp+140h] BYREF
  __int64 v106; // [rsp+250h] [rbp+150h]
  __int64 v107; // [rsp+258h] [rbp+158h]
  _BYTE v108[16]; // [rsp+260h] [rbp+160h] BYREF
  __int64 v109; // [rsp+270h] [rbp+170h]
  __int64 v110; // [rsp+278h] [rbp+178h]
  _BYTE v111[16]; // [rsp+280h] [rbp+180h] BYREF
  __int64 v112; // [rsp+290h] [rbp+190h]
  __int64 v113; // [rsp+298h] [rbp+198h]
  _BYTE v114[16]; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int64 v115; // [rsp+2B0h] [rbp+1B0h]
  __int64 v116; // [rsp+2B8h] [rbp+1B8h]
  _BYTE v117[16]; // [rsp+2C0h] [rbp+1C0h] BYREF
  __int64 v118; // [rsp+2D0h] [rbp+1D0h]
  __int64 v119; // [rsp+2D8h] [rbp+1D8h]
  _BYTE v120[16]; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int64 v121; // [rsp+2F0h] [rbp+1F0h]
  __int64 v122; // [rsp+2F8h] [rbp+1F8h]
  _BYTE v123[16]; // [rsp+300h] [rbp+200h] BYREF
  __int64 v124; // [rsp+310h] [rbp+210h]
  __int64 v125; // [rsp+318h] [rbp+218h]
  char v126[8]; // [rsp+320h] [rbp+220h] BYREF
  volatile signed __int32 *v127; // [rsp+328h] [rbp+228h]
  char v128[8]; // [rsp+330h] [rbp+230h] BYREF
  volatile signed __int32 *v129; // [rsp+338h] [rbp+238h]
  char v130[16]; // [rsp+340h] [rbp+240h] BYREF
  char v131[8]; // [rsp+350h] [rbp+250h] BYREF
  std::_Ref_count_base *v132; // [rsp+358h] [rbp+258h]
  char v133[8]; // [rsp+360h] [rbp+260h] BYREF
  std::_Ref_count_base *v134; // [rsp+368h] [rbp+268h]
  char v135[8]; // [rsp+370h] [rbp+270h] BYREF
  volatile signed __int32 *v136; // [rsp+378h] [rbp+278h]
  __int64 v137; // [rsp+380h] [rbp+280h]
  char v138[16]; // [rsp+388h] [rbp+288h] BYREF
  char v139[16]; // [rsp+398h] [rbp+298h] BYREF
  char v140[8]; // [rsp+3A8h] [rbp+2A8h] BYREF
  volatile signed __int32 *v141; // [rsp+3B0h] [rbp+2B0h]
  char v142[8]; // [rsp+3B8h] [rbp+2B8h] BYREF
  volatile signed __int32 *v143; // [rsp+3C0h] [rbp+2C0h]
  char v144[16]; // [rsp+3C8h] [rbp+2C8h] BYREF
  char v145[8]; // [rsp+3D8h] [rbp+2D8h] BYREF
  std::_Ref_count_base *v146; // [rsp+3E0h] [rbp+2E0h]
  char v147[16]; // [rsp+3E8h] [rbp+2E8h] BYREF
  char v148[16]; // [rsp+3F8h] [rbp+2F8h] BYREF
  char v149[16]; // [rsp+408h] [rbp+308h] BYREF
  char v150[16]; // [rsp+418h] [rbp+318h] BYREF
  char v151[16]; // [rsp+428h] [rbp+328h] BYREF
  char v152[16]; // [rsp+438h] [rbp+338h] BYREF
  char v153[16]; // [rsp+448h] [rbp+348h] BYREF
  char v154[16]; // [rsp+458h] [rbp+358h] BYREF
  char v155[16]; // [rsp+468h] [rbp+368h] BYREF
  char v156[16]; // [rsp+478h] [rbp+378h] BYREF
  char v157[16]; // [rsp+488h] [rbp+388h] BYREF
  char v158[8]; // [rsp+498h] [rbp+398h] BYREF
  volatile signed __int32 *v159; // [rsp+4A0h] [rbp+3A0h]
  __int64 v160[8]; // [rsp+4A8h] [rbp+3A8h] BYREF
  char v161[40]; // [rsp+4E8h] [rbp+3E8h] BYREF
  char v162[96]; // [rsp+510h] [rbp+410h] BYREF
  char v163[96]; // [rsp+570h] [rbp+470h] BYREF
  char v164[96]; // [rsp+5D0h] [rbp+4D0h] BYREF
  char v165[96]; // [rsp+630h] [rbp+530h] BYREF
  char v166[96]; // [rsp+690h] [rbp+590h] BYREF
  char v167[96]; // [rsp+6F0h] [rbp+5F0h] BYREF
  char v168[96]; // [rsp+750h] [rbp+650h] BYREF
  char v169[144]; // [rsp+7B0h] [rbp+6B0h] BYREF
  unsigned __int8 v170; // [rsp+850h] [rbp+750h]

  v170 = (unsigned __int8)a1;
  v137 = -2;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  v2 = (volatile signed __int32 *)operator new(0x70u);
  v3 = v2;
  if ( v2 )
  {
    *((_DWORD *)v2 + 2) = 1;
    *((_DWORD *)v2 + 3) = 1;
    *(_QWORD *)v2 = &std::_Ref_count_obj<arrow::compute::CastFunction>::`vftable';
    v94 = 0;
    v95 = 15;
    v93[0] = 0;
    std::string::assign(v93, "cast_null", 9u);
    arrow::compute::CastFunction::CastFunction(v3 + 4, v93, 0);
  }
  else
  {
    v3 = 0;
  }
  v66 = v3 + 4;
  v67 = (std::_Ref_count_base *)v3;
  v4 = arrow::compute::match::SameTypeId(v138, 28);
  v68[0] = 2;
  v68[1] = 1;
  v69 = 0;
  v70 = 0;
  v70 = *(_OWORD *)v4;
  *(_QWORD *)v4 = 0;
  *(_QWORD *)(v4 + 8) = 0;
  v160[0] = (__int64)&std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v160[1] = (__int64)arrow::compute::internal::OutputAllNull;
  v160[7] = (__int64)v160;
  v5 = arrow::null(v139);
  v6 = (arrow::compute::OutputType *)arrow::compute::OutputType::OutputType(v162, v5);
  *(_OWORD *)v71 = 0;
  v72 = 0;
  std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(
    v71,
    v68,
    v71,
    v170);
  arrow::compute::CastFunction::AddKernel((_DWORD)v3 + 16, (int)&v91, 28, (int)v71, v6, (__int64)v160, 0, 0);
  if ( v92 )
  {
    arrow::Status::State::`scalar deleting destructor'(v92, 1u);
    v92 = 0;
  }
  `eh vector destructor iterator'(v68, 0x28u, 1u, (void (*)(void *))arrow::compute::InputType::~InputType);
  v7 = (_QWORD *)a1[1];
  if ( (_QWORD *)a1[2] == v7 )
  {
    std::vector<std::shared_ptr<arrow::DataType>>::_Emplace_reallocate<std::shared_ptr<arrow::DataType> const &>(
      a1,
      v7,
      &v66);
  }
  else
  {
    *v7 = 0;
    v7[1] = 0;
    if ( v3 )
      _InterlockedIncrement(v3 + 2);
    *v7 = v3 + 4;
    v7[1] = v3;
    a1[1] += 16LL;
  }
  v97 = 0;
  v98 = 15;
  v96[0] = 0;
  std::string::assign(v96, "cast_int8", 9u);
  v8 = (_QWORD *)arrow::compute::internal::_anonymous_namespace_::GetCastToInteger_arrow::Int8Type_(v140, v96);
  v9 = (_QWORD *)a1[1];
  if ( (_QWORD *)a1[2] == v9 )
  {
    std::vector<std::shared_ptr<arrow::ChunkedArray>>::_Emplace_reallocate<std::shared_ptr<arrow::ChunkedArray>>(
      a1,
      v9,
      v8);
  }
  else
  {
    *v9 = 0;
    v9[1] = 0;
    *v9 = *v8;
    v9[1] = v8[1];
    *v8 = 0;
    v8[1] = 0;
    a1[1] += 16LL;
  }
  v10 = v141;
  if ( v141 )
  {
    if ( _InterlockedExchangeAdd(v141 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
      if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
    }
  }
  v100 = 0;
  v101 = 15;
  v99[0] = 0;
  std::string::assign(v99, "cast_int16", 0xAu);
  v11 = (_QWORD *)arrow::compute::internal::_anonymous_namespace_::GetCastToInteger_arrow::Int16Type_(v142, v99);
  v12 = (_QWORD *)a1[1];
  if ( (_QWORD *)a1[2] == v12 )
  {
    std::vector<std::shared_ptr<arrow::ChunkedArray>>::_Emplace_reallocate<std::shared_ptr<arrow::ChunkedArray>>(
      a1,
      v12,
      v11);
  }
  else
  {
    *v12 = 0;
    v12[1] = 0;
    *v12 = *v11;
    v12[1] = v11[1];
    *v11 = 0;
    v11[1] = 0;
    a1[1] += 16LL;
  }
  v13 = v143;
  if ( v143 )
  {
    if ( _InterlockedExchangeAdd(v143 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  v103 = 0;
  v104 = 15;
  v102[0] = 0;
  std::string::assign(v102, "cast_int32", 0xAu);
  arrow::compute::internal::_anonymous_namespace_::GetCastToInteger_arrow::Int32Type_(&v62, v102);
  v14 = arrow::int32(v144);
  v15 = arrow::compute::OutputType::OutputType(v163, v14);
  v16 = arrow::date32(v147);
  v17 = arrow::compute::InputType::InputType(v161, v16, 0);
  arrow::compute::internal::AddZeroCopyCast(16, v17, v15, v62);
  v18 = arrow::int32(v148);
  v19 = arrow::compute::OutputType::OutputType(v164, v18);
  v20 = arrow::compute::match::SameTypeId(v149, 19);
  v73 = 2;
  v74 = 0;
  v75 = 0;
  v75 = *(_OWORD *)v20;
  *(_QWORD *)v20 = 0;
  *(_QWORD *)(v20 + 8) = 0;
  arrow::compute::internal::AddZeroCopyCast(19, &v73, v19, v62);
  v21 = (_QWORD *)a1[1];
  if ( (_QWORD *)a1[2] == v21 )
  {
    std::vector<std::shared_ptr<arrow::DataType>>::_Emplace_reallocate<std::shared_ptr<arrow::DataType> const &>(
      a1,
      v21,
      &v62);
  }
  else
  {
    *v21 = 0;
    v21[1] = 0;
    if ( v63 )
      _InterlockedIncrement((volatile signed __int32 *)v63 + 2);
    *v21 = v62;
    v21[1] = v63;
    a1[1] += 16LL;
  }
  v106 = 0;
  v107 = 15;
  v105[0] = 0;
  std::string::assign(v105, "cast_int64", 0xAu);
  arrow::compute::internal::_anonymous_namespace_::GetCastToInteger_arrow::Int64Type_(&v60, v105);
  v22 = arrow::int64(v150);
  v23 = arrow::compute::OutputType::OutputType(v165, v22);
  v24 = arrow::compute::match::SameTypeId(v151, 17);
  v76 = 2;
  v77 = 0;
  v78 = 0;
  v78 = *(_OWORD *)v24;
  *(_QWORD *)v24 = 0;
  *(_QWORD *)(v24 + 8) = 0;
  arrow::compute::internal::AddZeroCopyCast(17, &v76, v23, v60);
  v25 = arrow::int64(v152);
  v26 = arrow::compute::OutputType::OutputType(v166, v25);
  v27 = arrow::compute::match::SameTypeId(v153, 32);
  v79 = 2;
  v80 = 0;
  v81 = 0;
  v81 = *(_OWORD *)v27;
  *(_QWORD *)v27 = 0;
  *(_QWORD *)(v27 + 8) = 0;
  arrow::compute::internal::AddZeroCopyCast(32, &v79, v26, v60);
  v28 = arrow::int64(v154);
  v29 = arrow::compute::OutputType::OutputType(v167, v28);
  v30 = arrow::compute::match::SameTypeId(v155, 18);
  v82 = 2;
  v83 = 0;
  v84 = 0;
  v84 = *(_OWORD *)v30;
  *(_QWORD *)v30 = 0;
  *(_QWORD *)(v30 + 8) = 0;
  arrow::compute::internal::AddZeroCopyCast(18, &v82, v29, v60);
  v31 = arrow::int64(v156);
  v32 = arrow::compute::OutputType::OutputType(v168, v31);
  v33 = arrow::compute::match::SameTypeId(v157, 20);
  v85 = 2;
  v86 = 0;
  v87 = 0;
  v87 = *(_OWORD *)v33;
  *(_QWORD *)v33 = 0;
  *(_QWORD *)(v33 + 8) = 0;
  arrow::compute::internal::AddZeroCopyCast(20, &v85, v32, v60);
  v34 = (_QWORD *)a1[1];
  if ( (_QWORD *)a1[2] == v34 )
  {
    std::vector<std::shared_ptr<arrow::DataType>>::_Emplace_reallocate<std::shared_ptr<arrow::DataType> const &>(
      a1,
      v34,
      &v60);
  }
  else
  {
    *v34 = 0;
    v34[1] = 0;
    if ( v61 )
      _InterlockedIncrement((volatile signed __int32 *)v61 + 2);
    *v34 = v60;
    v34[1] = v61;
    a1[1] += 16LL;
  }
  v89 = 0;
  v90 = 15;
  v88[0] = 0;
  std::string::assign(v88, "cast_uint8", 0xAu);
  v35 = (_QWORD *)arrow::compute::internal::_anonymous_namespace_::GetCastToInteger_arrow::UInt8Type_(v135, v88);
  v36 = (_QWORD *)a1[1];
  if ( (_QWORD *)a1[2] == v36 )
  {
    std::vector<std::shared_ptr<arrow::ChunkedArray>>::_Emplace_reallocate<std::shared_ptr<arrow::ChunkedArray>>(
      a1,
      v36,
      v35);
  }
  else
  {
    *v36 = 0;
    v36[1] = 0;
    *v36 = *v35;
    v36[1] = v35[1];
    *v35 = 0;
    v35[1] = 0;
    a1[1] += 16LL;
  }
  v37 = v136;
  if ( v136 )
  {
    if ( _InterlockedExchangeAdd(v136 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v37)(v37);
      if ( _InterlockedExchangeAdd(v37 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v37 + 8LL))(v37);
    }
  }
  v109 = 0;
  v110 = 15;
  v108[0] = 0;
  std::string::assign(v108, "cast_uint16", 0xBu);
  v38 = (_QWORD *)arrow::compute::internal::_anonymous_namespace_::GetCastToInteger_arrow::UInt16Type_(v158, v108);
  v39 = (_QWORD *)a1[1];
  if ( (_QWORD *)a1[2] == v39 )
  {
    std::vector<std::shared_ptr<arrow::ChunkedArray>>::_Emplace_reallocate<std::shared_ptr<arrow::ChunkedArray>>(
      a1,
      v39,
      v38);
  }
  else
  {
    *v39 = 0;
    v39[1] = 0;
    *v39 = *v38;
    v39[1] = v38[1];
    *v38 = 0;
    v38[1] = 0;
    a1[1] += 16LL;
  }
  v40 = v159;
  if ( v159 )
  {
    if ( _InterlockedExchangeAdd(v159 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
      if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
    }
  }
  v112 = 0;
  v113 = 15;
  v111[0] = 0;
  std::string::assign(v111, "cast_uint32", 0xBu);
  v41 = (_QWORD *)arrow::compute::internal::_anonymous_namespace_::GetCastToInteger_arrow::UInt32Type_(v126, v111);
  v42 = (_QWORD *)a1[1];
  if ( (_QWORD *)a1[2] == v42 )
  {
    std::vector<std::shared_ptr<arrow::ChunkedArray>>::_Emplace_reallocate<std::shared_ptr<arrow::ChunkedArray>>(
      a1,
      v42,
      v41);
  }
  else
  {
    *v42 = 0;
    v42[1] = 0;
    *v42 = *v41;
    v42[1] = v41[1];
    *v41 = 0;
    v41[1] = 0;
    a1[1] += 16LL;
  }
  v43 = v127;
  if ( v127 )
  {
    if ( _InterlockedExchangeAdd(v127 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v43)(v43);
      if ( _InterlockedExchangeAdd(v43 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v43 + 8LL))(v43);
    }
  }
  v115 = 0;
  v116 = 15;
  v114[0] = 0;
  std::string::assign(v114, "cast_uint64", 0xBu);
  v44 = (_QWORD *)arrow::compute::internal::_anonymous_namespace_::GetCastToInteger_arrow::UInt64Type_(v128, v114);
  v45 = (_QWORD *)a1[1];
  if ( (_QWORD *)a1[2] == v45 )
  {
    std::vector<std::shared_ptr<arrow::ChunkedArray>>::_Emplace_reallocate<std::shared_ptr<arrow::ChunkedArray>>(
      a1,
      v45,
      v44);
  }
  else
  {
    *v45 = 0;
    v45[1] = 0;
    *v45 = *v44;
    v45[1] = v44[1];
    *v44 = 0;
    v44[1] = 0;
    a1[1] += 16LL;
  }
  v46 = v129;
  if ( v129 )
  {
    if ( _InterlockedExchangeAdd(v129 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v46)(v46);
      if ( _InterlockedExchangeAdd(v46 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v46 + 8LL))(v46);
    }
  }
  v47 = (volatile signed __int32 *)operator new(0x70u);
  v48 = v47;
  if ( v47 )
  {
    *((_DWORD *)v47 + 2) = 1;
    *((_DWORD *)v47 + 3) = 1;
    *(_QWORD *)v47 = &std::_Ref_count_obj<arrow::compute::CastFunction>::`vftable';
    v118 = 0;
    v119 = 15;
    v117[0] = 0;
    std::string::assign(v117, "cast_half_float", 0xFu);
    arrow::compute::CastFunction::CastFunction(v48 + 4, v117, 10);
  }
  else
  {
    v48 = 0;
  }
  v64 = v48 + 4;
  v49 = (std::_Ref_count_base *)v48;
  v65 = (std::_Ref_count_base *)v48;
  v50 = arrow::float16(v130);
  v51 = arrow::compute::OutputType::OutputType(v169, v50);
  arrow::compute::internal::AddCommonCasts(10, v51, v48 + 4);
  v52 = (_QWORD *)a1[1];
  if ( (_QWORD *)a1[2] == v52 )
  {
    std::vector<std::shared_ptr<arrow::DataType>>::_Emplace_reallocate<std::shared_ptr<arrow::DataType> const &>(
      a1,
      v52,
      &v64);
    v49 = v65;
  }
  else
  {
    *v52 = 0;
    v52[1] = 0;
    if ( v48 )
    {
      _InterlockedIncrement(v48 + 2);
      v49 = v65;
    }
    *v52 = v48 + 4;
    v52[1] = v48;
    a1[1] += 16LL;
  }
  v121 = 0;
  v122 = 15;
  v120[0] = 0;
  std::string::assign(v120, "cast_float", 0xAu);
  v53 = (_QWORD *)arrow::compute::internal::_anonymous_namespace_::GetCastToFloating_arrow::FloatType_(v131, v120);
  v54 = (_QWORD *)a1[1];
  if ( (_QWORD *)a1[2] == v54 )
  {
    std::vector<std::shared_ptr<arrow::ChunkedArray>>::_Emplace_reallocate<std::shared_ptr<arrow::ChunkedArray>>(
      a1,
      v54,
      v53);
  }
  else
  {
    *v54 = 0;
    v54[1] = 0;
    *v54 = *v53;
    v54[1] = v53[1];
    *v53 = 0;
    v53[1] = 0;
    a1[1] += 16LL;
  }
  if ( v132 )
    std::_Ref_count_base::_Decref(v132);
  v124 = 0;
  v125 = 15;
  v123[0] = 0;
  std::string::assign(v123, "cast_double", 0xBu);
  v55 = (_QWORD *)arrow::compute::internal::_anonymous_namespace_::GetCastToFloating_arrow::DoubleType_(v133, v123);
  v56 = (_QWORD *)a1[1];
  if ( (_QWORD *)a1[2] == v56 )
  {
    std::vector<std::shared_ptr<arrow::ChunkedArray>>::_Emplace_reallocate<std::shared_ptr<arrow::ChunkedArray>>(
      a1,
      v56,
      v55);
  }
  else
  {
    *v56 = 0;
    v56[1] = 0;
    *v56 = *v55;
    v56[1] = v55[1];
    *v55 = 0;
    v55[1] = 0;
    a1[1] += 16LL;
  }
  if ( v134 )
    std::_Ref_count_base::_Decref(v134);
  CastToDecimal = (_QWORD *)arrow::compute::internal::_anonymous_namespace_::GetCastToDecimal(v145);
  v58 = (_QWORD *)a1[1];
  if ( (_QWORD *)a1[2] == v58 )
  {
    std::vector<std::shared_ptr<arrow::ChunkedArray>>::_Emplace_reallocate<std::shared_ptr<arrow::ChunkedArray>>(
      a1,
      v58,
      CastToDecimal);
  }
  else
  {
    *v58 = 0;
    v58[1] = 0;
    *v58 = *CastToDecimal;
    v58[1] = CastToDecimal[1];
    *CastToDecimal = 0;
    CastToDecimal[1] = 0;
    a1[1] += 16LL;
  }
  if ( v146 )
    std::_Ref_count_base::_Decref(v146);
  if ( v49 )
    std::_Ref_count_base::_Decref(v49);
  if ( v61 )
    std::_Ref_count_base::_Decref(v61);
  if ( v63 )
    std::_Ref_count_base::_Decref(v63);
  if ( v67 )
    std::_Ref_count_base::_Decref(v67);
  return a1;
}

```

## disassembly

```asm
0x180154070  mov     [rsp-8+arg_0], rcx
0x180154075  push    rbp
0x180154076  push    rbx
0x180154077  push    rsi
0x180154078  push    rdi
0x180154079  push    r12
0x18015407b  push    r14
0x18015407d  push    r15
0x18015407f  lea     rbp, [rsp-710h]
0x180154087  sub     rsp, 810h
0x18015408e  mov     [rbp+740h+var_4C0], 0FFFFFFFFFFFFFFFEh
0x180154099  mov     rdi, rcx
0x18015409c  xor     r15d, r15d
0x18015409f  mov     [rsp+840h+var_800], r15d
0x1801540a4  mov     [rcx], r15
0x1801540a7  mov     [rcx+8], r15
0x1801540ab  mov     [rcx+10h], r15
0x1801540af  mov     [rsp+840h+var_800], 1
0x1801540b7  lea     ecx, [r15+70h]; Size
0x1801540bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801540c0  mov     rsi, rax
0x1801540c3  mov     [rbp+740h+arg_8], rax
0x1801540ca  lea     r12, ??_7?$_Ref_count_obj@VCastFunction@compute@arrow@@@std@@6B@; const std::_Ref_count_obj<arrow::compute::CastFunction>::`vftable'
0x1801540d1  test    rax, rax
0x1801540d4  jz      short loc_18015412C
0x1801540d6  mov     dword ptr [rax+8], 1
0x1801540dd  mov     dword ptr [rax+0Ch], 1
0x1801540e4  mov     [rax], r12
0x1801540e7  mov     [rbp+740h+var_670], r15
0x1801540ee  mov     [rbp+740h+var_668], 0Fh
0x1801540f9  mov     [rbp+740h+var_680], r15b
0x180154100  lea     r8d, [r15+9]; Size
0x180154104  lea     rdx, aCastNull; "cast_null"
0x18015410b  lea     rcx, [rbp+740h+var_680]; void *
0x180154112  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x180154117  xor     r8d, r8d
0x18015411a  lea     rdx, [rbp+740h+var_680]
0x180154121  lea     rcx, [rsi+10h]
0x180154125  call    ??0CastFunction@compute@arrow@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@W4type@Type@2@@Z; arrow::compute::CastFunction::CastFunction(std::string,arrow::Type::type)
0x18015412a  jmp     short loc_18015412F
0x18015412c  mov     rsi, r15
0x18015412f  mov     [rsp+840h+var_800], 3
0x180154137  lea     r14, [rsi+10h]
0x18015413b  mov     [rsp+840h+var_7C8], r14
0x180154140  mov     [rbp+740h+var_7C0], rsi
0x180154144  lea     rax, [rbp+740h+var_398]
0x18015414b  mov     [rbp+740h+arg_8], rax
0x180154152  lea     rax, [rbp+740h+var_330]
0x180154159  mov     [rbp+740h+arg_10], rax
0x180154160  mov     edx, 1Ch
0x180154165  lea     rcx, [rbp+740h+var_4B8]
0x18015416c  call    ?SameTypeId@match@compute@arrow@@YA?AV?$shared_ptr@UTypeMatcher@compute@arrow@@@std@@W4type@Type@3@@Z; arrow::compute::match::SameTypeId(arrow::Type::type)
0x180154171  mov     [rbp+740h+var_7B8], 2
0x180154178  mov     [rbp+740h+var_7B4], 1
0x18015417f  xorps   xmm0, xmm0
0x180154182  movdqu  [rbp+740h+var_7B0], xmm0
0x180154187  xorps   xmm1, xmm1
0x18015418a  movdqu  [rbp+740h+var_7A0], xmm1
0x18015418f  mov     rcx, [rax]
0x180154192  mov     qword ptr [rbp+740h+var_7A0], rcx
0x180154196  mov     rcx, [rax+8]
0x18015419a  mov     qword ptr [rbp+740h+var_7A0+8], rcx
0x18015419e  mov     [rax], r15
0x1801541a1  mov     [rax+8], r15
0x1801541a5  mov     [rsp+840h+var_800], 7
0x1801541ad  lea     rax, ??_7?$_Func_impl_no_alloc@P6AXPEAVKernelContext@compute@arrow@@AEBUExecBatch@23@PEAUDatum@3@@ZXPEAV123@AEBU423@PEAU53@@std@@6B@; const std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable'
0x1801541b4  mov     [rbp+740h+var_398], rax
0x1801541bb  lea     rax, ?OutputAllNull@internal@compute@arrow@@YAXPEAVKernelContext@23@AEBUExecBatch@23@PEAUDatum@3@@Z; arrow::compute::internal::OutputAllNull(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *)
0x1801541c2  mov     [rbp+740h+var_390], rax
0x1801541c9  lea     rax, [rbp+740h+var_398]
0x1801541d0  mov     [rbp+740h+var_360], rax
0x1801541d7  lea     rcx, [rbp+740h+var_4A8]
0x1801541de  call    ?null@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::null(void)
0x1801541e3  mov     rdx, rax
0x1801541e6  lea     rcx, [rbp+740h+var_330]
0x1801541ed  call    ??0OutputType@compute@arrow@@QEAA@V?$shared_ptr@VDataType@arrow@@@std@@@Z; arrow::compute::OutputType::OutputType(std::shared_ptr<arrow::DataType>)
0x1801541f2  mov     rbx, rax
0x1801541f5  xorps   xmm0, xmm0
0x1801541f8  movdqu  xmmword ptr [rbp+740h+var_790], xmm0
0x1801541fd  mov     [rbp+740h+var_780], r15
0x180154201  movzx   r9d, byte ptr [rbp+740h+arg_0]
0x180154209  lea     r8, [rbp+740h+var_790]
0x18015420d  lea     rdx, [rbp+740h+var_7B8]
0x180154211  lea     rcx, [rbp+740h+var_790]
0x180154215  call    ??$_Range_construct_or_tidy@PEBVInputType@compute@arrow@@@?$vector@VInputType@compute@arrow@@V?$allocator@VInputType@compute@arrow@@@std@@@std@@AEAAXPEBVInputType@compute@arrow@@0Uforward_iterator_tag@1@@Z; std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(arrow::compute::InputType const *,arrow::compute::InputType const *,std::forward_iterator_tag)
0x18015421a  nop
0x18015421b  mov     [rsp+840h+var_808], r15d; int
0x180154220  mov     [rsp+840h+var_810], r15d; int
0x180154225  lea     rax, [rbp+740h+var_398]
0x18015422c  mov     [rsp+840h+var_818], rax; __int64
0x180154231  mov     [rsp+840h+var_820], rbx; arrow::compute::OutputType *
0x180154236  lea     r9, [rbp+740h+var_790]; int
0x18015423a  mov     r8d, 1Ch; int
0x180154240  lea     rdx, [rbp+740h+var_690]; int
0x180154247  mov     rcx, r14; int
0x18015424a  call    ?AddKernel@CastFunction@compute@arrow@@QEAA?AVStatus@3@W4type@Type@3@V?$vector@VInputType@compute@arrow@@V?$allocator@VInputType@compute@arrow@@@std@@@std@@VOutputType@23@V?$function@$$A6AXPEAVKernelContext@compute@arrow@@AEBUExecBatch@23@PEAUDatum@3@@Z@8@W45NullHandling@23@W45MemAllocation@23@@Z; arrow::compute::CastFunction::AddKernel(arrow::Type::type,std::vector<arrow::compute::InputType>,arrow::compute::OutputType,std::function<void (arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *)>,arrow::compute::NullHandling::type,arrow::compute::MemAllocation::type)
0x18015424f  mov     rcx, [rbp+740h+var_688]; this
0x180154256  test    rcx, rcx
0x180154259  jz      short loc_18015426C
0x18015425b  mov     edx, 1; unsigned int
0x180154260  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x180154265  mov     [rbp+740h+var_688], r15
0x18015426c  lea     r9, ??1InputType@compute@arrow@@QEAA@XZ; void (*)(void *)
0x180154273  mov     edx, 28h ; '('; unsigned __int64
0x180154278  lea     r8d, [rdx-27h]; unsigned __int64
0x18015427c  lea     rcx, [rbp+740h+var_7B8]; void *
0x180154280  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180154285  mov     rdx, [rdi+8]
0x180154289  cmp     [rdi+10h], rdx
0x18015428d  jz      short loc_1801542AD
0x18015428f  mov     [rdx], r15
0x180154292  mov     [rdx+8], r15
0x180154296  test    rsi, rsi
0x180154299  jz      short loc_18015429F
0x18015429b  lock inc dword ptr [rsi+8]
0x18015429f  mov     [rdx], r14
0x1801542a2  mov     [rdx+8], rsi
0x1801542a6  add     qword ptr [rdi+8], 10h
0x1801542ab  jmp     short loc_1801542BA
0x1801542ad  lea     r8, [rsp+840h+var_7C8]
0x1801542b2  mov     rcx, rdi
0x1801542b5  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VDataType@arrow@@@std@@@?$vector@V?$shared_ptr@VDataType@arrow@@@std@@V?$allocator@V?$shared_ptr@VDataType@arrow@@@std@@@2@@std@@QEAAPEAV?$shared_ptr@VDataType@arrow@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<arrow::DataType>>::_Emplace_reallocate<std::shared_ptr<arrow::DataType> const &>(std::shared_ptr<arrow::DataType> * const,std::shared_ptr<arrow::DataType> const &)
0x1801542ba  mov     [rbp+740h+var_650], r15
0x1801542c1  mov     [rbp+740h+var_648], 0Fh
0x1801542cc  mov     [rbp+740h+var_660], 0
0x1801542d3  mov     r8d, 9; Size
0x1801542d9  lea     rdx, aCastInt8; "cast_int8"
0x1801542e0  lea     rcx, [rbp+740h+var_660]; void *
0x1801542e7  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1801542ec  lea     rdx, [rbp+740h+var_660]
0x1801542f3  lea     rcx, [rbp+740h+var_498]
0x1801542fa  call    arrow__compute__internal___anonymous_namespace___GetCastToInteger_arrow__Int8Type_
0x1801542ff  mov     r8, rax
0x180154302  mov     rdx, [rdi+8]
0x180154306  cmp     [rdi+10h], rdx
0x18015430a  jz      short loc_18015432F
0x18015430c  mov     [rdx], r15
0x18015430f  mov     [rdx+8], r15
0x180154313  mov     rax, [rax]
0x180154316  mov     [rdx], rax
0x180154319  mov     rax, [r8+8]
0x18015431d  mov     [rdx+8], rax
0x180154321  mov     [r8], r15
0x180154324  mov     [r8+8], r15
0x180154328  add     qword ptr [rdi+8], 10h
0x18015432d  jmp     short loc_180154338
0x18015432f  mov     rcx, rdi
0x180154332  call    ??$_Emplace_reallocate@V?$shared_ptr@VChunkedArray@arrow@@@std@@@?$vector@V?$shared_ptr@VChunkedArray@arrow@@@std@@V?$allocator@V?$shared_ptr@VChunkedArray@arrow@@@std@@@2@@std@@QEAAPEAV?$shared_ptr@VChunkedArray@arrow@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<arrow::ChunkedArray>>::_Emplace_reallocate<std::shared_ptr<arrow::ChunkedArray>>(std::shared_ptr<arrow::ChunkedArray> * const,std::shared_ptr<arrow::ChunkedArray> &&)
0x180154337  nop
0x180154338  mov     esi, 0FFFFFFFFh
0x18015433d  mov     rbx, [rbp+740h+var_490]
0x180154344  test    rbx, rbx
0x180154347  jz      short loc_180154380
0x180154349  mov     eax, esi
0x18015434b  lock xadd [rbx+8], eax
0x180154350  cmp     eax, 1
0x180154353  jnz     short loc_180154380
0x180154355  mov     rax, [rbx]
0x180154358  mov     rcx, rbx
0x18015435b  mov     rax, [rax]
0x18015435e  call    cs:__guard_dispatch_icall_fptr
0x180154364  mov     eax, esi
0x180154366  lock xadd [rbx+0Ch], eax
0x18015436b  cmp     eax, 1
0x18015436e  jnz     short loc_180154380
0x180154370  mov     rax, [rbx]
0x180154373  mov     rcx, rbx
0x180154376  mov     rax, [rax+8]
0x18015437a  call    cs:__guard_dispatch_icall_fptr
0x180154380  mov     [rbp+740h+var_630], r15
0x180154387  mov     [rbp+740h+var_628], 0Fh
0x180154392  mov     [rbp+740h+var_640], 0
0x180154399  mov     r8d, 0Ah; Size
0x18015439f  lea     rdx, aCastInt16; "cast_int16"
0x1801543a6  lea     rcx, [rbp+740h+var_640]; void *
0x1801543ad  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1801543b2  lea     rdx, [rbp+740h+var_640]
0x1801543b9  lea     rcx, [rbp+740h+var_488]
0x1801543c0  call    arrow__compute__internal___anonymous_namespace___GetCastToInteger_arrow__Int16Type_
0x1801543c5  mov     r8, rax
0x1801543c8  mov     rdx, [rdi+8]
0x1801543cc  cmp     [rdi+10h], rdx
0x1801543d0  jz      short loc_1801543F5
0x1801543d2  mov     [rdx], r15
0x1801543d5  mov     [rdx+8], r15
0x1801543d9  mov     rax, [rax]
0x1801543dc  mov     [rdx], rax
0x1801543df  mov     rax, [r8+8]
0x1801543e3  mov     [rdx+8], rax
0x1801543e7  mov     [r8], r15
0x1801543ea  mov     [r8+8], r15
0x1801543ee  add     qword ptr [rdi+8], 10h
0x1801543f3  jmp     short loc_1801543FE
0x1801543f5  mov     rcx, rdi
0x1801543f8  call    ??$_Emplace_reallocate@V?$shared_ptr@VChunkedArray@arrow@@@std@@@?$vector@V?$shared_ptr@VChunkedArray@arrow@@@std@@V?$allocator@V?$shared_ptr@VChunkedArray@arrow@@@std@@@2@@std@@QEAAPEAV?$shared_ptr@VChunkedArray@arrow@@@1@QEAV21@$$QEAV21@@Z; std::vector<std::shared_ptr<arrow::ChunkedArray>>::_Emplace_reallocate<std::shared_ptr<arrow::ChunkedArray>>(std::shared_ptr<arrow::ChunkedArray> * const,std::shared_ptr<arrow::ChunkedArray> &&)
0x1801543fd  nop
0x1801543fe  mov     rbx, [rbp+740h+var_480]
0x180154405  test    rbx, rbx
0x180154408  jz      short loc_180154441
0x18015440a  mov     eax, esi
0x18015440c  lock xadd [rbx+8], eax
0x180154411  cmp     eax, 1
0x180154414  jnz     short loc_180154441
0x180154416  mov     rax, [rbx]
0x180154419  mov     rcx, rbx
0x18015441c  mov     rax, [rax]
0x18015441f  call    cs:__guard_dispatch_icall_fptr
0x180154425  mov     eax, esi
0x180154427  lock xadd [rbx+0Ch], eax
0x18015442c  cmp     eax, 1
0x18015442f  jnz     short loc_180154441
0x180154431  mov     rax, [rbx]
0x180154434  mov     rcx, rbx
0x180154437  mov     rax, [rax+8]
0x18015443b  call    cs:__guard_dispatch_icall_fptr
0x180154441  mov     [rbp+740h+var_610], r15
0x180154448  mov     [rbp+740h+var_608], 0Fh
0x180154453  mov     [rbp+740h+var_620], 0
0x18015445a  mov     r8d, 0Ah; Size
0x180154460  lea     rdx, aCastInt32; "cast_int32"
0x180154467  lea     rcx, [rbp+740h+var_620]; void *
0x18015446e  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x180154473  lea     rdx, [rbp+740h+var_620]
0x18015447a  lea     rcx, [rsp+840h+var_7E8]
0x18015447f  call    arrow__compute__internal___anonymous_namespace___GetCastToInteger_arrow__Int32Type_
0x180154484  nop
0x180154485  lea     rax, [rbp+740h+var_2D0]
0x18015448c  mov     [rbp+740h+arg_8], rax
0x180154493  lea     rcx, [rbp+740h+var_478]
0x18015449a  call    ?int32@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::int32(void)
0x18015449f  mov     rdx, rax
0x1801544a2  lea     rcx, [rbp+740h+var_2D0]
0x1801544a9  call    ??0OutputType@compute@arrow@@QEAA@V?$shared_ptr@VDataType@arrow@@@std@@@Z; arrow::compute::OutputType::OutputType(std::shared_ptr<arrow::DataType>)
0x1801544ae  mov     rbx, rax
0x1801544b1  lea     rcx, [rbp+740h+var_458]
0x1801544b8  call    ?date32@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::date32(void)
0x1801544bd  xor     r8d, r8d
0x1801544c0  mov     rdx, rax
0x1801544c3  lea     rcx, [rbp+740h+var_358]
0x1801544ca  call    ??0InputType@compute@arrow@@QEAA@V?$shared_ptr@VDataType@arrow@@@std@@W4Shape@ValueDescr@2@@Z; arrow::compute::InputType::InputType(std::shared_ptr<arrow::DataType>,arrow::ValueDescr::Shape)
0x1801544cf  nop
0x1801544d0  mov     r9, [rsp+840h+var_7E8]
0x1801544d5  mov     r8, rbx
0x1801544d8  mov     rdx, rax
0x1801544db  mov     ecx, 10h
0x1801544e0  call    ?AddZeroCopyCast@internal@compute@arrow@@YAXW4type@Type@3@VInputType@23@VOutputType@23@PEAVCastFunction@23@@Z; arrow::compute::internal::AddZeroCopyCast(arrow::Type::type,arrow::compute::InputType,arrow::compute::OutputType,arrow::compute::CastFunction *)
0x1801544e5  lea     rax, [rbp+740h+var_270]
0x1801544ec  mov     [rbp+740h+arg_8], rax
0x1801544f3  lea     rcx, [rbp+740h+var_448]
0x1801544fa  call    ?int32@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::int32(void)
0x1801544ff  mov     rdx, rax
0x180154502  lea     rcx, [rbp+740h+var_270]
0x180154509  call    ??0OutputType@compute@arrow@@QEAA@V?$shared_ptr@VDataType@arrow@@@std@@@Z; arrow::compute::OutputType::OutputType(std::shared_ptr<arrow::DataType>)
0x18015450e  mov     rbx, rax
0x180154511  mov     edx, 13h
0x180154516  lea     rcx, [rbp+740h+var_438]
0x18015451d  call    ?SameTypeId@match@compute@arrow@@YA?AV?$shared_ptr@UTypeMatcher@compute@arrow@@@std@@W4type@Type@3@@Z; arrow::compute::match::SameTypeId(arrow::Type::type)
0x180154522  mov     [rbp+740h+var_778], 2
0x18015452a  xorps   xmm0, xmm0
0x18015452d  movdqu  [rbp+740h+var_770], xmm0
0x180154532  xorps   xmm1, xmm1
0x180154535  movdqu  [rbp+740h+var_760], xmm1
0x18015453a  mov     rdx, [rax]
0x18015453d  mov     qword ptr [rbp+740h+var_760], rdx
0x180154541  mov     rdx, [rax+8]
0x180154545  mov     qword ptr [rbp+740h+var_760+8], rdx
0x180154549  mov     [rax], r15
0x18015454c  mov     [rax+8], r15
0x180154550  mov     r9, [rsp+840h+var_7E8]
0x180154555  mov     r8, rbx
0x180154558  lea     rdx, [rbp+740h+var_778]
0x18015455c  mov     ecx, 13h
0x180154561  call    ?AddZeroCopyCast@internal@compute@arrow@@YAXW4type@Type@3@VInputType@23@VOutputType@23@PEAVCastFunction@23@@Z; arrow::compute::internal::AddZeroCopyCast(arrow::Type::type,arrow::compute::InputType,arrow::compute::OutputType,arrow::compute::CastFunction *)
0x180154566  mov     rdx, [rdi+8]
0x18015456a  cmp     [rdi+10h], rdx
0x18015456e  jz      short loc_18015459D
0x180154570  mov     [rdx], r15
0x180154573  mov     [rdx+8], r15
0x180154577  mov     rax, [rsp+840h+var_7E0]
0x18015457c  test    rax, rax
0x18015457f  jz      short loc_180154585
0x180154581  lock inc dword ptr [rax+8]
0x180154585  mov     rax, [rsp+840h+var_7E8]
0x18015458a  mov     [rdx], rax
0x18015458d  mov     rax, [rsp+840h+var_7E0]
0x180154592  mov     [rdx+8], rax
0x180154596  add     qword ptr [rdi+8], 10h
0x18015459b  jmp     short loc_1801545AA
0x18015459d  lea     r8, [rsp+840h+var_7E8]
0x1801545a2  mov     rcx, rdi
0x1801545a5  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@VDataType@arrow@@@std@@@?$vector@V?$shared_ptr@VDataType@arrow@@@std@@V?$allocator@V?$shared_ptr@VDataType@arrow@@@std@@@2@@std@@QEAAPEAV?$shared_ptr@VDataType@arrow@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<arrow::DataType>>::_Emplace_reallocate<std::shared_ptr<arrow::DataType> const &>(std::shared_ptr<arrow::DataType> * const,std::shared_ptr<arrow::DataType> const &)
0x1801545aa  mov     [rbp+740h+var_5F0], r15
0x1801545b1  mov     [rbp+740h+var_5E8], 0Fh
0x1801545bc  mov     [rbp+740h+var_600], 0
0x1801545c3  mov     r8d, 0Ah; Size
0x1801545c9  lea     rdx, aCastInt64; "cast_int64"
0x1801545d0  lea     rcx, [rbp+740h+var_600]; void *
0x1801545d7  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1801545dc  lea     rdx, [rbp+740h+var_600]
0x1801545e3  lea     rcx, [rsp+840h+var_7F8]
  ... truncated ...
```
