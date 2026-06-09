# arrow::compute::internal::RegisterVectorSelection(arrow::compute::FunctionRegistry *)

- ea: `0x180214160`
- end: `0x180215212`
- name: `?RegisterVectorSelection@internal@compute@arrow@@YAXPEAVFunctionRegistry@23@@Z`
- size: `4274`
- prototype: `void __fastcall(arrow::compute::internal *__hidden this, struct arrow::compute::FunctionRegistry *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18012d690`

## callees

- `0x18000ff30`
- `0x180010860`
- `0x18001e1f0`
- `0x18001f8c0`
- `0x1800a8dd0`
- `0x1800aad60`
- `0x180127870`
- `0x180127c20`
- `0x180127c80`
- `0x180128020`
- `0x180128390`
- `0x18012b320`
- `0x18012d340`
- `0x1801bfc30`
- `0x1801c85c0`
- `0x1801e7690`
- `0x1801ff800`
- `0x1802015b0`
- `0x1802139c0`
- `0x180214160`
- `0x180217c00`
- `0x1802f0fb0`
- `0x18030c180`
- `0x18030c200`
- `0x18030c3f0`
- `0x180334640`

## pseudocode

```c
// Hidden C++ exception states: #wind=40
void __fastcall arrow::compute::internal::RegisterVectorSelection(
        arrow::compute::internal *this,
        struct arrow::compute::FunctionRegistry *a2)
{
  _QWORD *v3; // rax
  __int64 v4; // rax
  _QWORD *v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  _QWORD *v9; // rax
  __int64 v10; // rax
  _QWORD *v11; // rax
  __int64 v12; // rax
  _QWORD *v13; // rax
  __int64 v14; // rax
  _QWORD *v15; // rax
  __int64 v16; // rax
  __int64 v17; // rbx
  __int64 v18; // rax
  unsigned __int64 v19; // rdx
  void *v20; // rcx
  _DWORD *v21; // rax
  _DWORD *v22; // rbx
  __int64 v23; // rdx
  _QWORD *v24; // rax
  _QWORD *v25; // rax
  _QWORD *v26; // rax
  _QWORD *v27; // rax
  __int64 v28; // rax
  _QWORD *v29; // rax
  _QWORD *v30; // rax
  _QWORD *v31; // rax
  _QWORD *v32; // rax
  _QWORD *v33; // rax
  _QWORD *v34; // rax
  _QWORD *v35; // rax
  _QWORD *v36; // rax
  _QWORD *v37; // rax
  __int64 v38; // rax
  _DWORD *v39; // rax
  _DWORD *v40; // rdi
  _QWORD v41[2]; // [rsp+38h] [rbp-D0h] BYREF
  _QWORD v42[2]; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v43; // [rsp+58h] [rbp-B0h]
  _DWORD *v44; // [rsp+60h] [rbp-A8h] BYREF
  _DWORD *v45; // [rsp+68h] [rbp-A0h]
  __int64 v46; // [rsp+70h] [rbp-98h] BYREF
  arrow::Status::State *v47; // [rsp+78h] [rbp-90h]
  _DWORD v48[2]; // [rsp+80h] [rbp-88h] BYREF
  __int128 v49; // [rsp+88h] [rbp-80h]
  __int128 v50; // [rsp+98h] [rbp-70h]
  __int128 v51; // [rsp+A8h] [rbp-60h] BYREF
  __int64 v52; // [rsp+B8h] [rbp-50h]
  __int128 v53; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v54; // [rsp+D0h] [rbp-38h]
  __int64 v55; // [rsp+D8h] [rbp-30h]
  __int128 v56; // [rsp+E0h] [rbp-28h] BYREF
  __m128i si128; // [rsp+F0h] [rbp-18h]
  int v58; // [rsp+108h] [rbp+0h] BYREF
  int v59; // [rsp+10Ch] [rbp+4h]
  __int64 v60; // [rsp+110h] [rbp+8h]
  __int128 v61; // [rsp+118h] [rbp+10h]
  __int64 v62; // [rsp+128h] [rbp+20h]
  void **v63; // [rsp+130h] [rbp+28h] BYREF
  __int64 (__fastcall *v64)(arrow::compute::KernelContext *); // [rsp+138h] [rbp+30h]
  void ***v65; // [rsp+168h] [rbp+60h]
  int v66; // [rsp+170h] [rbp+68h]
  int v67; // [rsp+174h] [rbp+6Ch]
  __int128 v68; // [rsp+178h] [rbp+70h]
  __int128 v69; // [rsp+188h] [rbp+80h]
  void **v70; // [rsp+198h] [rbp+90h] BYREF
  __int64 (__fastcall *v71)(arrow::compute::KernelContext *); // [rsp+1A0h] [rbp+98h]
  void ***v72; // [rsp+1D0h] [rbp+C8h]
  int v73; // [rsp+1D8h] [rbp+D0h]
  int v74; // [rsp+1DCh] [rbp+D4h]
  __int64 v75; // [rsp+1E0h] [rbp+D8h]
  __int128 v76; // [rsp+1E8h] [rbp+E0h]
  __int64 v77; // [rsp+1F8h] [rbp+F0h]
  void **v78; // [rsp+200h] [rbp+F8h] BYREF
  __int64 (__fastcall *v79)(arrow::compute::KernelContext *); // [rsp+208h] [rbp+100h]
  void ***v80; // [rsp+238h] [rbp+130h]
  int v81; // [rsp+240h] [rbp+138h]
  int v82; // [rsp+244h] [rbp+13Ch]
  __int128 v83; // [rsp+248h] [rbp+140h]
  __int128 v84; // [rsp+258h] [rbp+150h]
  void **v85; // [rsp+268h] [rbp+160h] BYREF
  __int64 (__fastcall *v86)(arrow::compute::KernelContext *, int, mpark *); // [rsp+270h] [rbp+168h]
  void ***v87; // [rsp+2A0h] [rbp+198h]
  _BYTE v88[40]; // [rsp+2A8h] [rbp+1A0h] BYREF
  void **v89; // [rsp+2D0h] [rbp+1C8h] BYREF
  __int64 (__fastcall *v90)(); // [rsp+2D8h] [rbp+1D0h]
  void ***v91; // [rsp+308h] [rbp+200h]
  int v92; // [rsp+310h] [rbp+208h]
  int v93; // [rsp+314h] [rbp+20Ch]
  __int128 v94; // [rsp+318h] [rbp+210h]
  __int128 v95; // [rsp+328h] [rbp+220h]
  void **v96; // [rsp+338h] [rbp+230h] BYREF
  __int64 (__fastcall *v97)(arrow::compute::KernelContext *, int, mpark *); // [rsp+340h] [rbp+238h]
  void ***v98; // [rsp+370h] [rbp+268h]
  int v99; // [rsp+378h] [rbp+270h]
  int v100; // [rsp+37Ch] [rbp+274h]
  __int64 v101; // [rsp+380h] [rbp+278h]
  __int128 v102; // [rsp+388h] [rbp+280h]
  __int64 v103; // [rsp+398h] [rbp+290h]
  void **v104; // [rsp+3A0h] [rbp+298h] BYREF
  __int64 (__fastcall *v105)(arrow::compute::KernelContext *); // [rsp+3A8h] [rbp+2A0h]
  void ***v106; // [rsp+3D8h] [rbp+2D0h]
  int v107; // [rsp+3E0h] [rbp+2D8h]
  int v108; // [rsp+3E4h] [rbp+2DCh]
  __int128 v109; // [rsp+3E8h] [rbp+2E0h]
  __int128 v110; // [rsp+3F8h] [rbp+2F0h]
  void **v111; // [rsp+408h] [rbp+300h] BYREF
  __int64 (__fastcall *v112)(arrow::compute::KernelContext *); // [rsp+410h] [rbp+308h]
  void ***v113; // [rsp+440h] [rbp+338h]
  int v114; // [rsp+448h] [rbp+340h]
  int v115; // [rsp+44Ch] [rbp+344h]
  __int64 v116; // [rsp+450h] [rbp+348h]
  __int128 v117; // [rsp+458h] [rbp+350h]
  __int64 v118; // [rsp+468h] [rbp+360h]
  void **v119; // [rsp+470h] [rbp+368h] BYREF
  __int64 (__fastcall *v120)(int, int, mpark *); // [rsp+478h] [rbp+370h]
  void ***v121; // [rsp+4A8h] [rbp+3A0h]
  int v122; // [rsp+4B0h] [rbp+3A8h]
  int v123; // [rsp+4B4h] [rbp+3ACh]
  __int128 v124; // [rsp+4B8h] [rbp+3B0h]
  __int128 v125; // [rsp+4C8h] [rbp+3C0h]
  void **v126; // [rsp+4D8h] [rbp+3D0h] BYREF
  __int64 (__fastcall *v127)(int, int, mpark *); // [rsp+4E0h] [rbp+3D8h]
  void ***v128; // [rsp+510h] [rbp+408h]
  int v129; // [rsp+518h] [rbp+410h]
  int v130; // [rsp+51Ch] [rbp+414h]
  __int64 v131; // [rsp+520h] [rbp+418h]
  __int128 v132; // [rsp+528h] [rbp+420h]
  __int64 v133; // [rsp+538h] [rbp+430h]
  void **v134; // [rsp+540h] [rbp+438h] BYREF
  __int64 (__fastcall *v135)(int, int, mpark *); // [rsp+548h] [rbp+440h]
  void ***v136; // [rsp+578h] [rbp+470h]
  int v137; // [rsp+580h] [rbp+478h]
  int v138; // [rsp+584h] [rbp+47Ch]
  __int128 v139; // [rsp+588h] [rbp+480h]
  __int128 v140; // [rsp+598h] [rbp+490h]
  void **v141; // [rsp+5A8h] [rbp+4A0h] BYREF
  __int64 (__fastcall *v142)(arrow::compute::KernelContext *); // [rsp+5B0h] [rbp+4A8h]
  void ***v143; // [rsp+5E0h] [rbp+4D8h]
  int v144; // [rsp+5E8h] [rbp+4E0h]
  int v145; // [rsp+5ECh] [rbp+4E4h]
  __int64 v146; // [rsp+5F0h] [rbp+4E8h]
  __int128 v147; // [rsp+5F8h] [rbp+4F0h]
  __int64 v148; // [rsp+608h] [rbp+500h]
  void **v149; // [rsp+610h] [rbp+508h] BYREF
  __int64 (__fastcall *v150)(int, int, mpark *); // [rsp+618h] [rbp+510h]
  void ***v151; // [rsp+648h] [rbp+540h]
  char v152[8]; // [rsp+650h] [rbp+548h] BYREF
  __int128 v153; // [rsp+658h] [rbp+550h] BYREF
  char v154[56]; // [rsp+668h] [rbp+560h] BYREF
  __int64 v155; // [rsp+6A0h] [rbp+598h]
  char v156; // [rsp+6A8h] [rbp+5A0h]
  int v157; // [rsp+6ACh] [rbp+5A4h]
  __int64 v158; // [rsp+6E8h] [rbp+5E0h]
  char v159; // [rsp+6F0h] [rbp+5E8h]
  __int64 v160; // [rsp+730h] [rbp+628h]
  int v161; // [rsp+738h] [rbp+630h]
  int v162; // [rsp+73Ch] [rbp+634h]
  __int16 v163; // [rsp+740h] [rbp+638h]
  __int128 v164; // [rsp+748h] [rbp+640h] BYREF
  char v165[56]; // [rsp+758h] [rbp+650h] BYREF
  __int64 v166; // [rsp+790h] [rbp+688h]
  char v167; // [rsp+798h] [rbp+690h]
  int v168; // [rsp+79Ch] [rbp+694h]
  __int64 v169; // [rsp+7D8h] [rbp+6D0h]
  char v170; // [rsp+7E0h] [rbp+6D8h]
  __int64 v171; // [rsp+820h] [rbp+718h]
  int v172; // [rsp+828h] [rbp+720h]
  int v173; // [rsp+82Ch] [rbp+724h]
  __int16 v174; // [rsp+830h] [rbp+728h]

  v55 = -2;
  v3 = (_QWORD *)arrow::compute::match::Primitive(&v44, a2);
  v58 = 2;
  v59 = 1;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  *((_QWORD *)&v61 + 1) = *v3;
  v62 = v3[1];
  *v3 = 0;
  v3[1] = 0;
  v63 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v64 = arrow::compute::internal::_anonymous_namespace_::PrimitiveFilter;
  v65 = &v63;
  v4 = arrow::compute::match::BinaryLike(v42);
  v66 = 2;
  v67 = 1;
  v68 = 0;
  v69 = 0;
  v69 = *(_OWORD *)v4;
  *(_QWORD *)v4 = 0;
  *(_QWORD *)(v4 + 8) = 0;
  v70 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v71 = arrow::compute::internal::_anonymous_namespace_::BinaryFilter;
  v72 = &v70;
  v5 = (_QWORD *)arrow::compute::match::LargeBinaryLike(&v56);
  v73 = 2;
  v74 = 1;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  *((_QWORD *)&v76 + 1) = *v5;
  v77 = v5[1];
  *v5 = 0;
  v5[1] = 0;
  v78 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v79 = arrow::compute::internal::_anonymous_namespace_::BinaryFilter;
  v80 = &v78;
  v6 = arrow::compute::match::SameTypeId(v41, 15);
  v81 = 2;
  v82 = 1;
  v83 = 0;
  v84 = 0;
  v84 = *(_OWORD *)v6;
  *(_QWORD *)v6 = 0;
  *(_QWORD *)(v6 + 8) = 0;
  v85 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v86 = arrow::compute::internal::_anonymous_namespace_::FilterExec_arrow::compute::internal::_anonymous_namespace_::FSBImpl_;
  v87 = &v85;
  v7 = arrow::null(&v46);
  arrow::compute::InputType::Array(v88, v7);
  v89 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v90 = arrow::compute::internal::_anonymous_namespace_::NullFilter;
  v91 = &v89;
  v8 = arrow::compute::match::SameTypeId(v41, 23);
  v92 = 2;
  v93 = 1;
  v94 = 0;
  v95 = 0;
  v95 = *(_OWORD *)v8;
  *(_QWORD *)v8 = 0;
  *(_QWORD *)(v8 + 8) = 0;
  v96 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v97 = arrow::compute::internal::_anonymous_namespace_::FilterExec_arrow::compute::internal::_anonymous_namespace_::FSBImpl_;
  v98 = &v96;
  v9 = (_QWORD *)arrow::compute::match::SameTypeId(v41, 28);
  v99 = 2;
  v100 = 1;
  v101 = 0;
  v102 = 0;
  v103 = 0;
  *((_QWORD *)&v102 + 1) = *v9;
  v103 = v9[1];
  *v9 = 0;
  v9[1] = 0;
  v104 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v105 = arrow::compute::internal::_anonymous_namespace_::DictionaryFilter;
  v106 = &v104;
  v10 = arrow::compute::match::SameTypeId(v41, 30);
  v107 = 2;
  v108 = 1;
  v109 = 0;
  v110 = 0;
  v110 = *(_OWORD *)v10;
  *(_QWORD *)v10 = 0;
  *(_QWORD *)(v10 + 8) = 0;
  v111 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v112 = arrow::compute::internal::_anonymous_namespace_::ExtensionFilter;
  v113 = &v111;
  v11 = (_QWORD *)arrow::compute::match::SameTypeId(v41, 24);
  v114 = 2;
  v115 = 1;
  v116 = 0;
  v117 = 0;
  v118 = 0;
  *((_QWORD *)&v117 + 1) = *v11;
  v118 = v11[1];
  *v11 = 0;
  v11[1] = 0;
  v119 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v120 = arrow::compute::internal::_anonymous_namespace_::FilterExec_arrow::compute::internal::_anonymous_namespace_::ListImpl_arrow::ListType___;
  v121 = &v119;
  v12 = arrow::compute::match::SameTypeId(v41, 35);
  v122 = 2;
  v123 = 1;
  v124 = 0;
  v125 = 0;
  v125 = *(_OWORD *)v12;
  *(_QWORD *)v12 = 0;
  *(_QWORD *)(v12 + 8) = 0;
  v126 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v127 = arrow::compute::internal::_anonymous_namespace_::FilterExec_arrow::compute::internal::_anonymous_namespace_::ListImpl_arrow::LargeListType___;
  v128 = &v126;
  v13 = (_QWORD *)arrow::compute::match::SameTypeId(v41, 31);
  v129 = 2;
  v130 = 1;
  v131 = 0;
  v132 = 0;
  v133 = 0;
  *((_QWORD *)&v132 + 1) = *v13;
  v133 = v13[1];
  *v13 = 0;
  v13[1] = 0;
  v134 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v135 = arrow::compute::internal::_anonymous_namespace_::FilterExec_arrow::compute::internal::_anonymous_namespace_::FSLImpl_;
  v136 = &v134;
  v14 = arrow::compute::match::SameTypeId(v41, 25);
  v137 = 2;
  v138 = 1;
  v139 = 0;
  v140 = 0;
  v140 = *(_OWORD *)v14;
  *(_QWORD *)v14 = 0;
  *(_QWORD *)(v14 + 8) = 0;
  v141 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v142 = arrow::compute::internal::_anonymous_namespace_::StructFilter;
  v143 = &v141;
  v15 = (_QWORD *)arrow::compute::match::SameTypeId(v41, 29);
  v144 = 2;
  v145 = 1;
  v146 = 0;
  v147 = 0;
  v148 = 0;
  *((_QWORD *)&v147 + 1) = *v15;
  v148 = v15[1];
  *v15 = 0;
  v15[1] = 0;
  v149 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v150 = arrow::compute::internal::_anonymous_namespace_::FilterExec_arrow::compute::internal::_anonymous_namespace_::ListImpl_arrow::MapType___;
  v151 = &v149;
  v53 = 0;
  v54 = 0;
  std::vector_arrow::compute::internal::_anonymous_namespace_::SelectionKernelDescr_std::allocator_arrow::compute::internal::_anonymous_namespace_::SelectionKernelDescr___::_Range_construct_or_tidy_arrow::compute::internal::_anonymous_namespace_::SelectionKernelDescr_const___(
    &v53,
    &v58,
    v152,
    (unsigned __int8)v43);
  `eh vector destructor iterator'(
    &v58,
    0x68u,
    0xDu,
    (void (*)(void *))arrow::compute::internal::_anonymous_namespace_::SelectionKernelDescr::_SelectionKernelDescr);
  v164 = 0;
  v166 = 0;
  v167 = 1;
  v168 = 0;
  v169 = 0;
  v170 = 1;
  v171 = 0;
  v172 = 2;
  v173 = 1;
  v174 = 257;
  std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>::operator=<std::unique_ptr<arrow::compute::KernelState> (&)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),void>(
    v165,
    arrow::compute::internal::OptionsWrapper<arrow::compute::FilterOptions>::Init);
  v41[0] = v48;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v56) = 0;
  std::string::assign(&v56, "array_filter", 0xCu);
  v16 = arrow::boolean(&v46);
  v17 = arrow::compute::InputType::Array(v48, v16);
  v18 = arrow::compute::VectorKernel::VectorKernel(
          (arrow::compute::VectorKernel *)&v58,
          (const struct arrow::compute::VectorKernel *)&v164);
  arrow::compute::internal::_anonymous_namespace_::RegisterSelectionFunction(&v56, v18, v17, &v53, byte_1804C53F0, this);
  if ( si128.m128i_i64[1] >= 0x10uLL )
  {
    v19 = si128.m128i_i64[1] + 1;
    v20 = (void *)v56;
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
    {
      v19 = si128.m128i_i64[1] + 40;
      v20 = *(void **)(v56 - 8);
      if ( (unsigned __int64)(v56 - (_QWORD)v20 - 8) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v20, v19);
  }
  v21 = operator new(0x50u);
  v22 = v21;
  v42[0] = v21;
  if ( v21 )
  {
    v21[2] = 1;
    v21[3] = 1;
    *(_QWORD *)v21 = std::_Ref_count_obj<arrow::compute::internal::`anonymous namespace'::FilterMetaFunction>::`vftable';
    si128.m128i_i64[0] = 0;
    si128.m128i_i64[1] = 15;
    LOBYTE(v56) = 0;
    std::string::assign(&v56, "filter", 6u);
    LODWORD(v41[0]) = 2;
    BYTE4(v41[0]) = 0;
    *(_OWORD *)(v22 + 6) = v56;
    *(__m128i *)(v22 + 10) = si128;
    v22[14] = 3;
    *(_QWORD *)(v22 + 15) = v41[0];
    *((_QWORD *)v22 + 9) = byte_1804C53F0;
    *((_QWORD *)v22 + 2) = &arrow::compute::internal::`anonymous namespace'::FilterMetaFunction::`vftable';
  }
  else
  {
    v22 = 0;
  }
  v44 = v22 + 4;
  v45 = v22;
  v56 = 0;
  arrow::compute::FunctionRegistry::AddFunction(this, &v46, &v44, 0);
  if ( v47 )
    arrow::Status::State::`scalar deleting destructor'(v47, 1u);
  v24 = (_QWORD *)arrow::compute::match::Primitive(&v46, v23);
  v58 = 2;
  v59 = 1;
  v60 = 0;
  v61 = 0;
  v62 = 0;
  *((_QWORD *)&v61 + 1) = *v24;
  v62 = v24[1];
  *v24 = 0;
  v24[1] = 0;
  arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v24);
  v63 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v64 = arrow::compute::internal::_anonymous_namespace_::PrimitiveTake;
  v65 = &v63;
  v25 = (_QWORD *)arrow::compute::match::BinaryLike(&v56);
  v66 = 2;
  v67 = 1;
  v68 = 0;
  v69 = 0;
  v69 = *(_OWORD *)v25;
  *v25 = 0;
  v25[1] = 0;
  arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v25);
  v70 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v71 = (__int64 (__fastcall *)(arrow::compute::KernelContext *))arrow::compute::internal::_anonymous_namespace_::TakeExec_arrow::compute::internal::_anonymous_namespace_::VarBinaryImpl_arrow::BinaryType___;
  v72 = &v70;
  v26 = (_QWORD *)arrow::compute::match::LargeBinaryLike(&v44);
  v73 = 2;
  v74 = 1;
  v75 = 0;
  v76 = 0;
  v77 = 0;
  *((_QWORD *)&v76 + 1) = *v26;
  v77 = v26[1];
  *v26 = 0;
  v26[1] = 0;
  arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v26);
  v78 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v79 = (__int64 (__fastcall *)(arrow::compute::KernelContext *))arrow::compute::internal::_anonymous_namespace_::TakeExec_arrow::compute::internal::_anonymous_namespace_::VarBinaryImpl_arrow::LargeBinaryType___;
  v80 = &v78;
  v27 = (_QWORD *)arrow::compute::match::SameTypeId(v42, 15);
  v81 = 2;
  v82 = 1;
  v83 = 0;
  v84 = 0;
  v84 = *(_OWORD *)v27;
  *v27 = 0;
  v27[1] = 0;
  arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v27);
  v85 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v86 = arrow::compute::internal::_anonymous_namespace_::TakeExec_arrow::compute::internal::_anonymous_namespace_::FSBImpl_;
  v87 = &v85;
  v28 = arrow::null(v41);
  arrow::compute::InputType::Array(v88, v28);
  v89 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v90 = (__int64 (__fastcall *)())arrow::compute::internal::_anonymous_namespace_::NullTake;
  v91 = &v89;
  v29 = (_QWORD *)arrow::compute::match::SameTypeId(v42, 23);
  v92 = 2;
  v93 = 1;
  v94 = 0;
  v95 = 0;
  v95 = *(_OWORD *)v29;
  *v29 = 0;
  v29[1] = 0;
  arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v29);
  v96 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v97 = arrow::compute::internal::_anonymous_namespace_::TakeExec_arrow::compute::internal::_anonymous_namespace_::FSBImpl_;
  v98 = &v96;
  v30 = (_QWORD *)arrow::compute::match::SameTypeId(v42, 28);
  v99 = 2;
  v100 = 1;
  v101 = 0;
  v102 = 0;
  v103 = 0;
  *((_QWORD *)&v102 + 1) = *v30;
  v103 = v30[1];
  *v30 = 0;
  v30[1] = 0;
  arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v30);
  v104 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v105 = arrow::compute::internal::_anonymous_namespace_::DictionaryTake;
  v106 = &v104;
  v31 = (_QWORD *)arrow::compute::match::SameTypeId(v42, 30);
  v107 = 2;
  v108 = 1;
  v109 = 0;
  v110 = 0;
  v110 = *(_OWORD *)v31;
  *v31 = 0;
  v31[1] = 0;
  arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v31);
  v111 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v112 = arrow::compute::internal::_anonymous_namespace_::ExtensionTake;
  v113 = &v111;
  v32 = (_QWORD *)arrow::compute::match::SameTypeId(v42, 24);
  v114 = 2;
  v115 = 1;
  v116 = 0;
  v117 = 0;
  v118 = 0;
  *((_QWORD *)&v117 + 1) = *v32;
  v118 = v32[1];
  *v32 = 0;
  v32[1] = 0;
  arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v32);
  v119 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v120 = arrow::compute::internal::_anonymous_namespace_::TakeExec_arrow::compute::internal::_anonymous_namespace_::ListImpl_arrow::ListType___;
  v121 = &v119;
  v33 = (_QWORD *)arrow::compute::match::SameTypeId(v42, 35);
  v122 = 2;
  v123 = 1;
  v124 = 0;
  v125 = 0;
  v125 = *(_OWORD *)v33;
  *v33 = 0;
  v33[1] = 0;
  arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v33);
  v126 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v127 = arrow::compute::internal::_anonymous_namespace_::TakeExec_arrow::compute::internal::_anonymous_namespace_::ListImpl_arrow::LargeListType___;
  v128 = &v126;
  v34 = (_QWORD *)arrow::compute::match::SameTypeId(v42, 31);
  v129 = 2;
  v130 = 1;
  v131 = 0;
  v132 = 0;
  v133 = 0;
  *((_QWORD *)&v132 + 1) = *v34;
  v133 = v34[1];
  *v34 = 0;
  v34[1] = 0;
  arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v34);
  v134 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v135 = arrow::compute::internal::_anonymous_namespace_::TakeExec_arrow::compute::internal::_anonymous_namespace_::FSLImpl_;
  v136 = &v134;
  v35 = (_QWORD *)arrow::compute::match::SameTypeId(v42, 25);
  v137 = 2;
  v138 = 1;
  v139 = 0;
  v140 = 0;
  v140 = *(_OWORD *)v35;
  *v35 = 0;
  v35[1] = 0;
  arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v35);
  v141 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v142 = arrow::compute::internal::_anonymous_namespace_::TakeExec_arrow::compute::internal::_anonymous_namespace_::StructImpl_;
  v143 = &v141;
  v36 = (_QWORD *)arrow::compute::match::SameTypeId(v42, 29);
  v144 = 2;
  v145 = 1;
  v146 = 0;
  v147 = 0;
  v148 = 0;
  *((_QWORD *)&v147 + 1) = *v36;
  v148 = v36[1];
  *v36 = 0;
  v36[1] = 0;
  arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v36);
  v149 = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v150 = arrow::compute::internal::_anonymous_namespace_::TakeExec_arrow::compute::internal::_anonymous_namespace_::ListImpl_arrow::MapType___;
  v151 = &v149;
  v51 = 0;
  v52 = 0;
  std::vector_arrow::compute::internal::_anonymous_namespace_::SelectionKernelDescr_std::allocator_arrow::compute::internal::_anonymous_namespace_::SelectionKernelDescr___::_Range_construct_or_tidy_arrow::compute::internal::_anonymous_namespace_::SelectionKernelDescr_const___(
    &v51,
    &v58,
    v152,
    (unsigned __int8)v43);
  `eh vector destructor iterator'(
    &v58,
    0x68u,
    0xDu,
    (void (*)(void *))arrow::compute::internal::_anonymous_namespace_::SelectionKernelDescr::_SelectionKernelDescr);
  v153 = 0;
  v155 = 0;
  v156 = 1;
  v157 = 0;
  v158 = 0;
  v159 = 1;
  v160 = 0;
  v161 = 2;
  v162 = 1;
  v163 = 257;
  std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>::operator=<std::unique_ptr<arrow::compute::KernelState> (&)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),void>(
    v154,
    arrow::compute::internal::OptionsWrapper<arrow::compute::TakeOptions>::Init);
  LOBYTE(v163) = 0;
  v42[0] = v48;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v56) = 0;
  std::string::assign(&v56, "array_take", 0xAu);
  v37 = (_QWORD *)arrow::compute::match::Integer(&v46);
  v48[0] = 2;
  v48[1] = 1;
  v49 = 0;
  v50 = 0;
  v50 = *(_OWORD *)v37;
  *v37 = 0;
  v37[1] = 0;
  arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v37);
  v38 = arrow::compute::VectorKernel::VectorKernel(
          (arrow::compute::VectorKernel *)&v58,
          (const struct arrow::compute::VectorKernel *)&v153);
  arrow::compute::internal::_anonymous_namespace_::RegisterSelectionFunction(
    &v56,
    v38,
    v48,
    &v51,
    &qword_1804A7DB0,
    this);
  std::string::~string(&v56);
  v39 = operator new(0x50u);
  v40 = v39;
  v42[0] = v39;
  if ( v39 )
  {
    v39[2] = 1;
    v39[3] = 1;
    *(_QWORD *)v39 = std::_Ref_count_obj<arrow::compute::internal::`anonymous namespace'::TakeMetaFunction>::`vftable';
    si128.m128i_i64[0] = 0;
    si128.m128i_i64[1] = 15;
    LOBYTE(v56) = 0;
    std::string::assign(&v56, "take", 4u);
    LODWORD(v41[0]) = 2;
    BYTE4(v41[0]) = 0;
    arrow::compute::MetaFunction::MetaFunction(v40 + 4, &v56, v41, &qword_1804A7DB0);
    *((_QWORD *)v40 + 2) = &arrow::compute::internal::`anonymous namespace'::TakeMetaFunction::`vftable';
  }
  else
  {
    v40 = 0;
  }
  v44 = v40 + 4;
  v45 = v40;
  v56 = 0;
  arrow::compute::FunctionRegistry::AddFunction(this, &v46, &v44, 0);
  if ( v47 )
    arrow::Status::State::`scalar deleting destructor'(v47, 1u);
  arrow::compute::VectorKernel::~VectorKernel((arrow::compute::VectorKernel *)&v153);
  std::vector_arrow::compute::internal::_anonymous_namespace_::SelectionKernelDescr_std::allocator_arrow::compute::internal::_anonymous_namespace_::SelectionKernelDescr___::_Tidy(&v51);
  arrow::compute::VectorKernel::~VectorKernel((arrow::compute::VectorKernel *)&v164);
  std::vector_arrow::compute::internal::_anonymous_namespace_::SelectionKernelDescr_std::allocator_arrow::compute::internal::_anonymous_namespace_::SelectionKernelDescr___::_Tidy(&v53);
}

```

## disassembly

```asm
0x180214160  mov     rax, rsp
0x180214163  push    rbp
0x180214164  push    r14
0x180214166  push    r15
0x180214168  lea     rbp, [rax-758h]
0x18021416f  sub     rsp, 840h
0x180214176  mov     [rbp+750h+var_780], 0FFFFFFFFFFFFFFFEh
0x18021417e  mov     [rax+10h], rbx
0x180214182  mov     [rax+18h], rsi
0x180214186  mov     [rax+20h], rdi
0x18021418a  mov     rax, cs:__security_cookie
0x180214191  xor     rax, rsp
0x180214194  mov     [rbp+750h+var_20], rax
0x18021419b  mov     rsi, rcx
0x18021419e  lea     rcx, [rsp+850h+var_7F8]
0x1802141a3  call    ?Primitive@match@compute@arrow@@YA?AV?$shared_ptr@UTypeMatcher@compute@arrow@@@std@@XZ; arrow::compute::match::Primitive(void)
0x1802141a8  mov     [rbp+750h+var_750], 2
0x1802141af  mov     [rbp+750h+var_74C], 1
0x1802141b6  xor     r14d, r14d
0x1802141b9  mov     [rbp+750h+var_748], r14
0x1802141bd  xorps   xmm0, xmm0
0x1802141c0  movdqa  [rbp+750h+var_740], xmm0
0x1802141c5  mov     [rbp+750h+var_730], r14
0x1802141c9  mov     rcx, [rax]
0x1802141cc  mov     qword ptr [rbp+750h+var_740+8], rcx
0x1802141d0  mov     rcx, [rax+8]
0x1802141d4  mov     [rbp+750h+var_730], rcx
0x1802141d8  mov     [rax], r14
0x1802141db  mov     [rax+8], r14
0x1802141df  lea     rdi, ??_7?$_Func_impl_no_alloc@P6AXPEAVKernelContext@compute@arrow@@AEBUExecBatch@23@PEAUDatum@3@@ZXPEAV123@AEBU423@PEAU53@@std@@6B@; const std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable'
0x1802141e6  mov     [rbp+750h+var_728], rdi
0x1802141ea  lea     rax, arrow__compute__internal___anonymous_namespace___PrimitiveFilter
0x1802141f1  mov     [rbp+750h+var_720], rax
0x1802141f5  lea     rax, [rbp+750h+var_728]
0x1802141f9  mov     [rbp+750h+var_6F0], rax
0x1802141fd  lea     rcx, [rsp+850h+var_810]
0x180214202  call    ?BinaryLike@match@compute@arrow@@YA?AV?$shared_ptr@UTypeMatcher@compute@arrow@@@std@@XZ; arrow::compute::match::BinaryLike(void)
0x180214207  mov     [rbp+750h+var_6E8], 2
0x18021420e  mov     [rbp+750h+var_6E4], 1
0x180214215  xorps   xmm0, xmm0
0x180214218  movdqa  [rbp+750h+var_6E0], xmm0
0x18021421d  xorps   xmm1, xmm1
0x180214220  movdqa  [rbp+750h+var_6D0], xmm1
0x180214228  mov     rcx, [rax]
0x18021422b  mov     qword ptr [rbp+750h+var_6D0], rcx
0x180214232  mov     rcx, [rax+8]
0x180214236  mov     qword ptr [rbp+750h+var_6D0+8], rcx
0x18021423d  mov     [rax], r14
0x180214240  mov     [rax+8], r14
0x180214244  mov     [rbp+750h+var_6C0], rdi
0x18021424b  lea     rbx, arrow__compute__internal___anonymous_namespace___BinaryFilter
0x180214252  mov     [rbp+750h+var_6B8], rbx
0x180214259  lea     rax, [rbp+750h+var_6C0]
0x180214260  mov     [rbp+750h+var_688], rax
0x180214267  lea     rcx, [rbp+750h+var_778]
0x18021426b  call    ?LargeBinaryLike@match@compute@arrow@@YA?AV?$shared_ptr@UTypeMatcher@compute@arrow@@@std@@XZ; arrow::compute::match::LargeBinaryLike(void)
0x180214270  mov     [rbp+750h+var_680], 2
0x18021427a  mov     [rbp+750h+var_67C], 1
0x180214284  mov     [rbp+750h+var_678], r14
0x18021428b  xorps   xmm0, xmm0
0x18021428e  movdqa  [rbp+750h+var_670], xmm0
0x180214296  mov     [rbp+750h+var_660], r14
0x18021429d  mov     rcx, [rax]
0x1802142a0  mov     qword ptr [rbp+750h+var_670+8], rcx
0x1802142a7  mov     rcx, [rax+8]
0x1802142ab  mov     [rbp+750h+var_660], rcx
0x1802142b2  mov     [rax], r14
0x1802142b5  mov     [rax+8], r14
0x1802142b9  mov     [rbp+750h+var_658], rdi
0x1802142c0  mov     [rbp+750h+var_650], rbx
0x1802142c7  lea     rax, [rbp+750h+var_658]
0x1802142ce  mov     [rbp+750h+var_620], rax
0x1802142d5  lea     edx, [r14+0Fh]
0x1802142d9  lea     rcx, [rsp+850h+var_820]
0x1802142de  call    ?SameTypeId@match@compute@arrow@@YA?AV?$shared_ptr@UTypeMatcher@compute@arrow@@@std@@W4type@Type@3@@Z; arrow::compute::match::SameTypeId(arrow::Type::type)
0x1802142e3  mov     [rbp+750h+var_618], 2
0x1802142ed  mov     [rbp+750h+var_614], 1
0x1802142f7  xorps   xmm0, xmm0
0x1802142fa  movdqa  [rbp+750h+var_610], xmm0
0x180214302  xorps   xmm1, xmm1
0x180214305  movdqa  [rbp+750h+var_600], xmm1
0x18021430d  mov     rcx, [rax]
0x180214310  mov     qword ptr [rbp+750h+var_600], rcx
0x180214317  mov     rcx, [rax+8]
0x18021431b  mov     qword ptr [rbp+750h+var_600+8], rcx
0x180214322  mov     [rax], r14
0x180214325  mov     [rax+8], r14
0x180214329  mov     [rbp+750h+var_5F0], rdi
0x180214330  lea     rbx, arrow__compute__internal___anonymous_namespace___FilterExec_arrow__compute__internal___anonymous_namespace___FSBImpl_
0x180214337  mov     [rbp+750h+var_5E8], rbx
0x18021433e  lea     rax, [rbp+750h+var_5F0]
0x180214345  mov     [rbp+750h+var_5B8], rax
0x18021434c  lea     rcx, [rsp+850h+var_7E8]
0x180214351  call    ?null@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::null(void)
0x180214356  mov     rdx, rax
0x180214359  lea     rcx, [rbp+750h+var_5B0]
0x180214360  call    ?Array@InputType@compute@arrow@@SA?AV123@V?$shared_ptr@VDataType@arrow@@@std@@@Z; arrow::compute::InputType::Array(std::shared_ptr<arrow::DataType>)
0x180214365  mov     [rbp+750h+var_588], rdi
0x18021436c  lea     rax, arrow__compute__internal___anonymous_namespace___NullFilter
0x180214373  mov     [rbp+750h+var_580], rax
0x18021437a  lea     rax, [rbp+750h+var_588]
0x180214381  mov     [rbp+750h+var_550], rax
0x180214388  lea     edx, [r14+17h]
0x18021438c  lea     rcx, [rsp+850h+var_820]
0x180214391  call    ?SameTypeId@match@compute@arrow@@YA?AV?$shared_ptr@UTypeMatcher@compute@arrow@@@std@@W4type@Type@3@@Z; arrow::compute::match::SameTypeId(arrow::Type::type)
0x180214396  mov     [rbp+750h+var_548], 2
0x1802143a0  mov     [rbp+750h+var_544], 1
0x1802143aa  xorps   xmm0, xmm0
0x1802143ad  movdqa  [rbp+750h+var_540], xmm0
0x1802143b5  xorps   xmm1, xmm1
0x1802143b8  movdqa  [rbp+750h+var_530], xmm1
0x1802143c0  mov     rcx, [rax]
0x1802143c3  mov     qword ptr [rbp+750h+var_530], rcx
0x1802143ca  mov     rcx, [rax+8]
0x1802143ce  mov     qword ptr [rbp+750h+var_530+8], rcx
0x1802143d5  mov     [rax], r14
0x1802143d8  mov     [rax+8], r14
0x1802143dc  mov     [rbp+750h+var_520], rdi
0x1802143e3  mov     [rbp+750h+var_518], rbx
0x1802143ea  lea     rax, [rbp+750h+var_520]
0x1802143f1  mov     [rbp+750h+var_4E8], rax
0x1802143f8  lea     edx, [r14+1Ch]
0x1802143fc  lea     rcx, [rsp+850h+var_820]
0x180214401  call    ?SameTypeId@match@compute@arrow@@YA?AV?$shared_ptr@UTypeMatcher@compute@arrow@@@std@@W4type@Type@3@@Z; arrow::compute::match::SameTypeId(arrow::Type::type)
0x180214406  mov     [rbp+750h+var_4E0], 2
0x180214410  mov     [rbp+750h+var_4DC], 1
0x18021441a  mov     [rbp+750h+var_4D8], r14
0x180214421  xorps   xmm0, xmm0
0x180214424  movdqa  [rbp+750h+var_4D0], xmm0
0x18021442c  mov     [rbp+750h+var_4C0], r14
0x180214433  mov     rcx, [rax]
0x180214436  mov     qword ptr [rbp+750h+var_4D0+8], rcx
0x18021443d  mov     rcx, [rax+8]
0x180214441  mov     [rbp+750h+var_4C0], rcx
0x180214448  mov     [rax], r14
0x18021444b  mov     [rax+8], r14
0x18021444f  mov     [rbp+750h+var_4B8], rdi
0x180214456  lea     rax, arrow__compute__internal___anonymous_namespace___DictionaryFilter
0x18021445d  mov     [rbp+750h+var_4B0], rax
0x180214464  lea     rax, [rbp+750h+var_4B8]
0x18021446b  mov     [rbp+750h+var_480], rax
0x180214472  lea     edx, [r14+1Eh]
0x180214476  lea     rcx, [rsp+850h+var_820]
0x18021447b  call    ?SameTypeId@match@compute@arrow@@YA?AV?$shared_ptr@UTypeMatcher@compute@arrow@@@std@@W4type@Type@3@@Z; arrow::compute::match::SameTypeId(arrow::Type::type)
0x180214480  mov     [rbp+750h+var_478], 2
0x18021448a  mov     [rbp+750h+var_474], 1
0x180214494  xorps   xmm0, xmm0
0x180214497  movdqa  [rbp+750h+var_470], xmm0
0x18021449f  xorps   xmm1, xmm1
0x1802144a2  movdqa  [rbp+750h+var_460], xmm1
0x1802144aa  mov     rcx, [rax]
0x1802144ad  mov     qword ptr [rbp+750h+var_460], rcx
0x1802144b4  mov     rcx, [rax+8]
0x1802144b8  mov     qword ptr [rbp+750h+var_460+8], rcx
0x1802144bf  mov     [rax], r14
0x1802144c2  mov     [rax+8], r14
0x1802144c6  mov     [rbp+750h+var_450], rdi
0x1802144cd  lea     rax, arrow__compute__internal___anonymous_namespace___ExtensionFilter
0x1802144d4  mov     [rbp+750h+var_448], rax
0x1802144db  lea     rax, [rbp+750h+var_450]
0x1802144e2  mov     [rbp+750h+var_418], rax
0x1802144e9  lea     edx, [r14+18h]
0x1802144ed  lea     rcx, [rsp+850h+var_820]
0x1802144f2  call    ?SameTypeId@match@compute@arrow@@YA?AV?$shared_ptr@UTypeMatcher@compute@arrow@@@std@@W4type@Type@3@@Z; arrow::compute::match::SameTypeId(arrow::Type::type)
0x1802144f7  mov     [rbp+750h+var_410], 2
0x180214501  mov     [rbp+750h+var_40C], 1
0x18021450b  mov     [rbp+750h+var_408], r14
0x180214512  xorps   xmm0, xmm0
0x180214515  movdqa  [rbp+750h+var_400], xmm0
0x18021451d  mov     [rbp+750h+var_3F0], r14
0x180214524  mov     rcx, [rax]
0x180214527  mov     qword ptr [rbp+750h+var_400+8], rcx
0x18021452e  mov     rcx, [rax+8]
0x180214532  mov     [rbp+750h+var_3F0], rcx
0x180214539  mov     [rax], r14
0x18021453c  mov     [rax+8], r14
0x180214540  mov     [rbp+750h+var_3E8], rdi
0x180214547  lea     rax, arrow__compute__internal___anonymous_namespace___FilterExec_arrow__compute__internal___anonymous_namespace___ListImpl_arrow__ListType___
0x18021454e  mov     [rbp+750h+var_3E0], rax
0x180214555  lea     rax, [rbp+750h+var_3E8]
0x18021455c  mov     [rbp+750h+var_3B0], rax
0x180214563  lea     edx, [r14+23h]
0x180214567  lea     rcx, [rsp+850h+var_820]
0x18021456c  call    ?SameTypeId@match@compute@arrow@@YA?AV?$shared_ptr@UTypeMatcher@compute@arrow@@@std@@W4type@Type@3@@Z; arrow::compute::match::SameTypeId(arrow::Type::type)
0x180214571  mov     [rbp+750h+var_3A8], 2
0x18021457b  mov     [rbp+750h+var_3A4], 1
0x180214585  xorps   xmm0, xmm0
0x180214588  movdqa  [rbp+750h+var_3A0], xmm0
0x180214590  xorps   xmm1, xmm1
0x180214593  movdqa  [rbp+750h+var_390], xmm1
0x18021459b  mov     rcx, [rax]
0x18021459e  mov     qword ptr [rbp+750h+var_390], rcx
0x1802145a5  mov     rcx, [rax+8]
0x1802145a9  mov     qword ptr [rbp+750h+var_390+8], rcx
0x1802145b0  mov     [rax], r14
0x1802145b3  mov     [rax+8], r14
0x1802145b7  mov     [rbp+750h+var_380], rdi
0x1802145be  lea     rax, arrow__compute__internal___anonymous_namespace___FilterExec_arrow__compute__internal___anonymous_namespace___ListImpl_arrow__LargeListType___
0x1802145c5  mov     [rbp+750h+var_378], rax
0x1802145cc  lea     rax, [rbp+750h+var_380]
0x1802145d3  mov     [rbp+750h+var_348], rax
0x1802145da  lea     edx, [r14+1Fh]
0x1802145de  lea     rcx, [rsp+850h+var_820]
0x1802145e3  call    ?SameTypeId@match@compute@arrow@@YA?AV?$shared_ptr@UTypeMatcher@compute@arrow@@@std@@W4type@Type@3@@Z; arrow::compute::match::SameTypeId(arrow::Type::type)
0x1802145e8  mov     [rbp+750h+var_340], 2
0x1802145f2  mov     [rbp+750h+var_33C], 1
0x1802145fc  mov     [rbp+750h+var_338], r14
0x180214603  xorps   xmm0, xmm0
0x180214606  movdqa  [rbp+750h+var_330], xmm0
0x18021460e  mov     [rbp+750h+var_320], r14
0x180214615  mov     rcx, [rax]
0x180214618  mov     qword ptr [rbp+750h+var_330+8], rcx
0x18021461f  mov     rcx, [rax+8]
0x180214623  mov     [rbp+750h+var_320], rcx
0x18021462a  mov     [rax], r14
0x18021462d  mov     [rax+8], r14
0x180214631  mov     [rbp+750h+var_318], rdi
0x180214638  lea     rax, arrow__compute__internal___anonymous_namespace___FilterExec_arrow__compute__internal___anonymous_namespace___FSLImpl_
0x18021463f  mov     [rbp+750h+var_310], rax
0x180214646  lea     rax, [rbp+750h+var_318]
0x18021464d  mov     [rbp+750h+var_2E0], rax
0x180214654  lea     edx, [r14+19h]
0x180214658  lea     rcx, [rsp+850h+var_820]
0x18021465d  call    ?SameTypeId@match@compute@arrow@@YA?AV?$shared_ptr@UTypeMatcher@compute@arrow@@@std@@W4type@Type@3@@Z; arrow::compute::match::SameTypeId(arrow::Type::type)
0x180214662  mov     [rbp+750h+var_2D8], 2
0x18021466c  mov     [rbp+750h+var_2D4], 1
0x180214676  xorps   xmm0, xmm0
0x180214679  movdqa  [rbp+750h+var_2D0], xmm0
0x180214681  xorps   xmm1, xmm1
0x180214684  movdqa  [rbp+750h+var_2C0], xmm1
0x18021468c  mov     rcx, [rax]
0x18021468f  mov     qword ptr [rbp+750h+var_2C0], rcx
0x180214696  mov     rcx, [rax+8]
0x18021469a  mov     qword ptr [rbp+750h+var_2C0+8], rcx
0x1802146a1  mov     [rax], r14
0x1802146a4  mov     [rax+8], r14
0x1802146a8  mov     [rbp+750h+var_2B0], rdi
0x1802146af  lea     rax, arrow__compute__internal___anonymous_namespace___StructFilter
0x1802146b6  mov     [rbp+750h+var_2A8], rax
0x1802146bd  lea     rax, [rbp+750h+var_2B0]
0x1802146c4  mov     [rbp+750h+var_278], rax
0x1802146cb  lea     edx, [r14+1Dh]
0x1802146cf  lea     rcx, [rsp+850h+var_820]
0x1802146d4  call    ?SameTypeId@match@compute@arrow@@YA?AV?$shared_ptr@UTypeMatcher@compute@arrow@@@std@@W4type@Type@3@@Z; arrow::compute::match::SameTypeId(arrow::Type::type)
0x1802146d9  mov     [rbp+750h+var_270], 2
0x1802146e3  mov     [rbp+750h+var_26C], 1
0x1802146ed  mov     [rbp+750h+var_268], r14
0x1802146f4  xorps   xmm0, xmm0
0x1802146f7  movdqa  [rbp+750h+var_260], xmm0
0x1802146ff  mov     [rbp+750h+var_250], r14
0x180214706  mov     rcx, [rax]
0x180214709  mov     qword ptr [rbp+750h+var_260+8], rcx
0x180214710  mov     rcx, [rax+8]
0x180214714  mov     [rbp+750h+var_250], rcx
0x18021471b  mov     [rax], r14
0x18021471e  mov     [rax+8], r14
0x180214722  mov     [rbp+750h+var_248], rdi
0x180214729  lea     rax, arrow__compute__internal___anonymous_namespace___FilterExec_arrow__compute__internal___anonymous_namespace___ListImpl_arrow__MapType___
0x180214730  mov     [rbp+750h+var_240], rax
0x180214737  lea     rax, [rbp+750h+var_248]
0x18021473e  mov     [rbp+750h+var_210], rax
0x180214745  movdqu  [rbp+750h+var_798], xmm0
0x18021474a  mov     [rbp+750h+var_788], r14
0x18021474e  movzx   r9d, byte ptr [rsp+850h+var_800]
0x180214754  lea     r8, [rbp+750h+var_208]
0x18021475b  lea     rdx, [rbp+750h+var_750]
0x18021475f  lea     rcx, [rbp+750h+var_798]
0x180214763  call    std__vector_arrow__compute__internal___anonymous_namespace___SelectionKernelDescr_std__allocator_arrow__compute__internal___anonymous_namespace___SelectionKernelDescr______Range_construct_or_tidy_arrow__compute__internal___anonymous_namespace___SelectionKernelDescr_const___
0x180214768  nop
0x180214769  lea     r9, arrow__compute__internal___anonymous_namespace___SelectionKernelDescr___SelectionKernelDescr; void (*)(void *)
0x180214770  lea     edx, [r14+68h]; unsigned __int64
0x180214774  lea     r8d, [r14+0Dh]; unsigned __int64
0x180214778  lea     rcx, [rbp+750h+var_750]; void *
0x18021477c  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180214781  xorps   xmm0, xmm0
0x180214784  movdqa  [rbp+750h+var_110], xmm0
0x18021478c  mov     [rbp+750h+var_C8], r14
0x180214793  mov     [rbp+750h+var_C0], 1
0x18021479a  mov     [rbp+750h+var_BC], r14d
0x1802147a1  mov     [rbp+750h+var_80], r14
0x1802147a8  mov     [rbp+750h+var_78], 1
0x1802147af  mov     [rbp+750h+var_38], r14
0x1802147b6  mov     [rbp+750h+var_30], 2
0x1802147c0  mov     [rbp+750h+var_2C], 1
0x1802147ca  mov     [rbp+750h+var_28], 101h
0x1802147d3  lea     rdx, ?Init@?$OptionsWrapper@UFilterOptions@compute@arrow@@@internal@compute@arrow@@SA?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@34@AEBUKernelInitArgs@34@@Z; arrow::compute::internal::OptionsWrapper<arrow::compute::FilterOptions>::Init(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)
0x1802147da  lea     rcx, [rbp+750h+var_100]
0x1802147e1  call    ??$?4A6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@34@@ZX@?$function@$$A6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@45@@Z@std@@QEAAAEAV01@A6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@1@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@45@@Z@Z; std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>::operator=<std::unique_ptr<arrow::compute::KernelState> (&)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),void>(std::unique_ptr<arrow::compute::KernelState> (&)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &))
0x1802147e6  lea     rax, [rsp+850h+var_7D8]
0x1802147eb  mov     [rsp+850h+var_820], rax
0x1802147f0  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1802147f8  movdqu  [rbp+750h+var_768], xmm0
0x1802147fd  mov     byte ptr [rbp+750h+var_778], r14b
0x180214801  lea     r8d, [r14+0Ch]; Size
0x180214805  lea     rdx, aArrayFilter; "array_filter"
0x18021480c  lea     rcx, [rbp+750h+var_778]; void *
0x180214810  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x180214815  nop
0x180214816  lea     rcx, [rsp+850h+var_7E8]
0x18021481b  call    ?boolean@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::boolean(void)
  ... truncated ...
```
