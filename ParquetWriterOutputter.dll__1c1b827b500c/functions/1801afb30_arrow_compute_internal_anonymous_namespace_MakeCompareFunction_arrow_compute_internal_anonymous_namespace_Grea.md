# arrow::compute::internal::_anonymous_namespace_::MakeCompareFunction_arrow::compute::internal::_anonymous_namespace_::Greater_

- ea: `0x1801afb30`
- end: `0x1801b1165`
- name: `arrow::compute::internal::_anonymous_namespace_::MakeCompareFunction_arrow::compute::internal::_anonymous_namespace_::Greater_`
- size: `5685`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `broker_com_uri`

## callers

- `0x1801bebc0`

## callees

- `0x18000ff30`
- `0x18001e1f0`
- `0x18001f8c0`
- `0x180049a90`
- `0x1800a8dd0`
- `0x1800a8f00`
- `0x1800a9010`
- `0x1800a9630`
- `0x1800a9760`
- `0x1800a99c0`
- `0x1800a9af0`
- `0x1800d6280`
- `0x1801278d0`
- `0x180128420`
- `0x180128490`
- `0x180128500`
- `0x18012b620`
- `0x18012f8a0`
- `0x18012fa90`
- `0x18017b9a0`
- `0x18018de70`
- `0x18018e470`
- `0x18018eac0`
- `0x1801adeb0`
- `0x1801ae3a0`
- `0x1801afb30`
- `0x18024b970`
- `0x18024ba40`
- `0x18024c030`
- `0x18030c200`
- `0x18030c3f0`
- `0x180358070`

## pseudocode

```c
// Hidden C++ exception states: #wind=45
_QWORD *__fastcall arrow::compute::internal::_anonymous_namespace_::MakeCompareFunction_arrow::compute::internal::_anonymous_namespace_::Greater_(
        _QWORD *a1,
        __int64 a2)
{
  __int64 *v4; // rax
  volatile signed __int32 *v5; // rbx
  __int64 v6; // rax
  volatile signed __int32 *v7; // rbx
  __int64 v8; // rax
  __int64 v9; // rbx
  __int64 *v10; // rax
  __int64 v11; // rdi
  __int64 i; // rbx
  __int64 v13; // rax
  volatile signed __int32 *v14; // rbx
  __int64 v15; // rax
  volatile signed __int32 *v16; // rbx
  __int64 v17; // rax
  volatile signed __int32 *v18; // rbx
  __int64 v19; // rax
  volatile signed __int32 *v20; // rbx
  __int64 v21; // rax
  unsigned int *v22; // r14
  unsigned int *v23; // r15
  _QWORD *v24; // rax
  __int64 v25; // rsi
  volatile signed __int32 *v26; // rdi
  volatile signed __int32 *v27; // rdi
  volatile signed __int32 *v28; // rdi
  __int64 v29; // rax
  volatile signed __int32 *v30; // rdi
  _BYTE *v31; // rdx
  __int64 v32; // rdi
  __int64 v33; // rax
  unsigned int *v34; // r14
  unsigned int *v35; // r15
  _QWORD *v36; // rax
  __int64 v37; // rsi
  volatile signed __int32 *v38; // rdi
  volatile signed __int32 *v39; // rdi
  volatile signed __int32 *v40; // rdi
  __int64 v41; // rax
  volatile signed __int32 *v42; // rdi
  _BYTE *v43; // rdx
  __int64 v44; // rdi
  int *v45; // r14
  _QWORD *v46; // rax
  __int64 v47; // rsi
  volatile signed __int32 *v48; // rdi
  volatile signed __int32 *v49; // rdi
  volatile signed __int32 *v50; // rdi
  __int64 v51; // rax
  volatile signed __int32 *v52; // rdi
  _BYTE *v53; // rdx
  __int64 v54; // rdi
  int **v55; // r14
  _QWORD *v56; // rax
  __int64 v57; // rsi
  volatile signed __int32 *v58; // rdi
  volatile signed __int32 *v59; // rdi
  volatile signed __int32 *v60; // rdi
  _QWORD *v61; // rax
  _BYTE *v62; // rdx
  __int64 v63; // rax
  _QWORD *v64; // rdi
  _QWORD *v65; // rsi
  __int64 v66; // rcx
  __int64 v67; // rax
  __int64 v68; // rcx
  __int64 v69; // rax
  _QWORD *v70; // rax
  _BYTE *v71; // rdx
  unsigned __int8 v73; // [rsp+30h] [rbp-D0h]
  _DWORD v74[2]; // [rsp+48h] [rbp-B8h] BYREF
  int *v75; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE *v76; // [rsp+58h] [rbp-A8h]
  int v77; // [rsp+60h] [rbp-A0h]
  _DWORD v78[2]; // [rsp+68h] [rbp-98h] BYREF
  int v79; // [rsp+70h] [rbp-90h] BYREF
  char v80; // [rsp+74h] [rbp-8Ch]
  __int64 v81; // [rsp+78h] [rbp-88h]
  __int128 v82; // [rsp+80h] [rbp-80h] BYREF
  __int128 v83; // [rsp+90h] [rbp-70h]
  __int64 v84; // [rsp+A0h] [rbp-60h]
  __int128 v85; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v86; // [rsp+B8h] [rbp-48h]
  __int64 v87; // [rsp+C8h] [rbp-38h]
  __int128 v88; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v89; // [rsp+E0h] [rbp-20h]
  __int64 v90; // [rsp+F0h] [rbp-10h]
  __int128 v91; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v92; // [rsp+108h] [rbp+8h] BYREF
  int v93; // [rsp+118h] [rbp+18h]
  int v94; // [rsp+11Ch] [rbp+1Ch]
  int v95; // [rsp+120h] [rbp+20h]
  int v96; // [rsp+124h] [rbp+24h]
  int v97; // [rsp+128h] [rbp+28h]
  _QWORD v98[2]; // [rsp+130h] [rbp+30h] BYREF
  _QWORD v99[2]; // [rsp+140h] [rbp+40h] BYREF
  __int64 v100; // [rsp+150h] [rbp+50h] BYREF
  _OWORD v101[2]; // [rsp+158h] [rbp+58h] BYREF
  __int64 v102; // [rsp+178h] [rbp+78h]
  __int128 v103; // [rsp+180h] [rbp+80h] BYREF
  __int128 v104; // [rsp+190h] [rbp+90h]
  __int64 v105; // [rsp+1A0h] [rbp+A0h] BYREF
  _OWORD v106[2]; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v107; // [rsp+1C8h] [rbp+C8h]
  __int128 v108; // [rsp+1D0h] [rbp+D0h] BYREF
  __int128 v109; // [rsp+1E0h] [rbp+E0h]
  __int64 v110; // [rsp+1F0h] [rbp+F0h] BYREF
  _OWORD v111[2]; // [rsp+1F8h] [rbp+F8h] BYREF
  __int64 v112; // [rsp+218h] [rbp+118h]
  __int128 v113; // [rsp+220h] [rbp+120h] BYREF
  __int128 v114; // [rsp+230h] [rbp+130h]
  __int64 v115; // [rsp+240h] [rbp+140h] BYREF
  _OWORD v116[2]; // [rsp+248h] [rbp+148h] BYREF
  __int64 v117; // [rsp+268h] [rbp+168h]
  __int128 v118; // [rsp+270h] [rbp+170h] BYREF
  __int128 v119; // [rsp+280h] [rbp+180h]
  __int64 v120; // [rsp+290h] [rbp+190h] BYREF
  __int64 v121; // [rsp+298h] [rbp+198h]
  __int64 v122; // [rsp+2A0h] [rbp+1A0h]
  __int64 v123; // [rsp+2A8h] [rbp+1A8h]
  __int64 v124; // [rsp+2B0h] [rbp+1B0h]
  __int64 v125; // [rsp+2B8h] [rbp+1B8h]
  __int128 v126; // [rsp+2C0h] [rbp+1C0h]
  __int128 v127; // [rsp+2D0h] [rbp+1D0h]
  __int128 v128; // [rsp+2E0h] [rbp+1E0h] BYREF
  __int64 v129; // [rsp+2F0h] [rbp+1F0h]
  __int128 v130; // [rsp+2F8h] [rbp+1F8h] BYREF
  __int64 v131; // [rsp+308h] [rbp+208h]
  __int128 v132; // [rsp+310h] [rbp+210h] BYREF
  __int64 v133; // [rsp+320h] [rbp+220h]
  __int128 v134; // [rsp+328h] [rbp+228h] BYREF
  __int64 v135; // [rsp+338h] [rbp+238h]
  __int128 v136; // [rsp+340h] [rbp+240h] BYREF
  __int64 v137; // [rsp+350h] [rbp+250h]
  __int128 v138; // [rsp+358h] [rbp+258h] BYREF
  __int64 v139; // [rsp+368h] [rbp+268h]
  _BYTE v140[8]; // [rsp+370h] [rbp+270h] BYREF
  arrow::Status::State *v141; // [rsp+378h] [rbp+278h]
  _BYTE v142[8]; // [rsp+380h] [rbp+280h] BYREF
  arrow::Status::State *v143; // [rsp+388h] [rbp+288h]
  _BYTE v144[8]; // [rsp+390h] [rbp+290h] BYREF
  arrow::Status::State *v145; // [rsp+398h] [rbp+298h]
  _BYTE v146[8]; // [rsp+3A0h] [rbp+2A0h] BYREF
  arrow::Status::State *v147; // [rsp+3A8h] [rbp+2A8h]
  _BYTE v148[8]; // [rsp+3B0h] [rbp+2B0h] BYREF
  arrow::Status::State *v149; // [rsp+3B8h] [rbp+2B8h]
  _BYTE v150[8]; // [rsp+3C0h] [rbp+2C0h] BYREF
  arrow::Status::State *v151; // [rsp+3C8h] [rbp+2C8h]
  _QWORD v152[8]; // [rsp+3D0h] [rbp+2D0h] BYREF
  __int128 v153; // [rsp+410h] [rbp+310h]
  _BYTE v154[16]; // [rsp+420h] [rbp+320h] BYREF
  _BYTE v155[8]; // [rsp+430h] [rbp+330h] BYREF
  volatile signed __int32 *v156; // [rsp+438h] [rbp+338h]
  _BYTE v157[16]; // [rsp+440h] [rbp+340h] BYREF
  _BYTE v158[16]; // [rsp+450h] [rbp+350h] BYREF
  _BYTE v159[16]; // [rsp+460h] [rbp+360h] BYREF
  _BYTE v160[16]; // [rsp+470h] [rbp+370h] BYREF
  _BYTE v161[16]; // [rsp+480h] [rbp+380h] BYREF
  _QWORD *v162; // [rsp+490h] [rbp+390h]
  __int64 v163; // [rsp+498h] [rbp+398h]
  _BYTE v164[16]; // [rsp+4A0h] [rbp+3A0h] BYREF
  _BYTE v165[16]; // [rsp+4B0h] [rbp+3B0h] BYREF
  _BYTE v166[16]; // [rsp+4C0h] [rbp+3C0h] BYREF
  _BYTE v167[8]; // [rsp+4D0h] [rbp+3D0h] BYREF
  volatile signed __int32 *v168; // [rsp+4D8h] [rbp+3D8h]
  _BYTE v169[8]; // [rsp+4E0h] [rbp+3E0h] BYREF
  volatile signed __int32 *v170; // [rsp+4E8h] [rbp+3E8h]
  _BYTE v171[8]; // [rsp+4F0h] [rbp+3F0h] BYREF
  volatile signed __int32 *v172; // [rsp+4F8h] [rbp+3F8h]
  _BYTE v173[8]; // [rsp+500h] [rbp+400h] BYREF
  volatile signed __int32 *v174; // [rsp+508h] [rbp+408h]
  _BYTE v175[8]; // [rsp+510h] [rbp+410h] BYREF
  volatile signed __int32 *v176; // [rsp+518h] [rbp+418h]
  _BYTE v177[8]; // [rsp+520h] [rbp+420h] BYREF
  volatile signed __int32 *v178; // [rsp+528h] [rbp+428h]
  _BYTE v179[16]; // [rsp+530h] [rbp+430h] BYREF
  _BYTE v180[16]; // [rsp+540h] [rbp+440h] BYREF
  _BYTE v181[8]; // [rsp+550h] [rbp+450h] BYREF
  volatile signed __int32 *v182; // [rsp+558h] [rbp+458h]
  _BYTE v183[16]; // [rsp+560h] [rbp+460h] BYREF
  _QWORD v184[8]; // [rsp+570h] [rbp+470h] BYREF
  int v185; // [rsp+5B0h] [rbp+4B0h] BYREF
  __int128 v186; // [rsp+5B8h] [rbp+4B8h]
  int v187; // [rsp+5C8h] [rbp+4C8h]
  __int64 v188; // [rsp+608h] [rbp+508h]
  int v189; // [rsp+610h] [rbp+510h] BYREF
  __int128 v190; // [rsp+618h] [rbp+518h]
  int v191; // [rsp+628h] [rbp+528h]
  __int64 v192; // [rsp+668h] [rbp+568h]
  int v193; // [rsp+670h] [rbp+570h] BYREF
  __int128 v194; // [rsp+678h] [rbp+578h]
  int v195; // [rsp+688h] [rbp+588h]
  __int64 v196; // [rsp+6C8h] [rbp+5C8h]
  int v197; // [rsp+6D0h] [rbp+5D0h] BYREF
  __int128 v198; // [rsp+6D8h] [rbp+5D8h]
  int v199; // [rsp+6E8h] [rbp+5E8h]
  __int64 v200; // [rsp+728h] [rbp+628h]
  int v201; // [rsp+730h] [rbp+630h] BYREF
  __int128 v202; // [rsp+738h] [rbp+638h]
  int v203; // [rsp+748h] [rbp+648h]
  __int64 v204; // [rsp+788h] [rbp+688h]
  _BYTE v205[56]; // [rsp+790h] [rbp+690h] BYREF
  __int64 v206; // [rsp+7C8h] [rbp+6C8h]
  _BYTE v207[56]; // [rsp+7D0h] [rbp+6D0h] BYREF
  __int64 v208; // [rsp+808h] [rbp+708h]
  _BYTE v209[56]; // [rsp+810h] [rbp+710h] BYREF
  __int64 v210; // [rsp+848h] [rbp+748h]
  _BYTE v211[56]; // [rsp+850h] [rbp+750h] BYREF
  __int64 v212; // [rsp+888h] [rbp+788h]
  _BYTE v213[56]; // [rsp+890h] [rbp+790h] BYREF
  __int64 v214; // [rsp+8C8h] [rbp+7C8h]
  _BYTE v215[56]; // [rsp+8D0h] [rbp+7D0h] BYREF
  __int64 v216; // [rsp+908h] [rbp+808h]
  _BYTE v217[56]; // [rsp+910h] [rbp+810h] BYREF
  __int64 v218; // [rsp+948h] [rbp+848h]
  _BYTE v219[56]; // [rsp+950h] [rbp+850h] BYREF
  __int64 v220; // [rsp+988h] [rbp+888h]
  _BYTE v221[56]; // [rsp+990h] [rbp+890h] BYREF
  __int64 v222; // [rsp+9C8h] [rbp+8C8h]
  _BYTE v223[56]; // [rsp+9D0h] [rbp+8D0h] BYREF
  __int64 v224; // [rsp+A08h] [rbp+908h]
  _BYTE v225[56]; // [rsp+A10h] [rbp+910h] BYREF
  __int64 v226; // [rsp+A48h] [rbp+948h]
  _BYTE v227[96]; // [rsp+A50h] [rbp+950h] BYREF
  __int64 v228; // [rsp+AB0h] [rbp+9B0h]
  _BYTE v229[56]; // [rsp+AC0h] [rbp+9C0h] BYREF
  _BYTE *v230; // [rsp+AF8h] [rbp+9F8h]
  _BYTE v231[56]; // [rsp+B00h] [rbp+A00h] BYREF
  _BYTE *v232; // [rsp+B38h] [rbp+A38h]
  _BYTE v233[56]; // [rsp+B40h] [rbp+A40h] BYREF
  _BYTE *v234; // [rsp+B78h] [rbp+A78h]
  _BYTE v235[56]; // [rsp+B80h] [rbp+A80h] BYREF
  _BYTE *v236; // [rsp+BB8h] [rbp+AB8h]
  _BYTE v237[56]; // [rsp+BC0h] [rbp+AC0h] BYREF
  _BYTE *v238; // [rsp+BF8h] [rbp+AF8h]

  v163 = -2;
  v162 = a1;
  v228 = a2;
  v79 = 2;
  v80 = 0;
  std::make_shared<arrow::compute::ScalarFunction,std::string &,arrow::compute::Arity>(a1, a2, &v79);
  v77 = 1;
  v75 = (int *)v184;
  v76 = v227;
  v4 = (__int64 *)arrow::boolean(v164);
  v120 = 1;
  v121 = 0;
  v122 = 0;
  v121 = *v4;
  v122 = v4[1];
  *v4 = 0;
  v4[1] = 0;
  v123 = 0;
  v124 = 0;
  v5 = (volatile signed __int32 *)v4[1];
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  v6 = arrow::boolean(v165);
  v125 = 1;
  v126 = 0;
  v126 = *(_OWORD *)v6;
  *(_QWORD *)v6 = 0;
  *(_QWORD *)(v6 + 8) = 0;
  v127 = 0;
  v7 = *(volatile signed __int32 **)(v6 + 8);
  if ( v7 )
  {
    if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
      if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
    }
  }
  v216 = 0;
  v184[0] = &std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable';
  v184[1] = arrow::compute::internal::applicator::ScalarBinary_arrow::BooleanType_arrow::BooleanType_arrow::BooleanType_arrow::compute::internal::_anonymous_namespace_::Greater_::Exec;
  v184[7] = v184;
  v8 = arrow::boolean(v166);
  v9 = arrow::compute::OutputType::OutputType(v227, v8);
  v128 = 0;
  v129 = 0;
  std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(
    &v128,
    &v120,
    &v128,
    v73);
  arrow::compute::ScalarFunction::AddKernel(*a1, v140, &v128, v9, v184, v215);
  if ( v141 )
  {
    arrow::Status::State::`scalar deleting destructor'(v141, 1u);
    v141 = 0;
  }
  `eh vector destructor iterator'(&v120, 0x28u, 2u, (void (*)(void *))arrow::compute::InputType::~InputType);
  v10 = (__int64 *)arrow::compute::internal::IntTypes();
  v11 = v10[1];
  for ( i = *v10; i != v11; i += 16 )
    arrow::compute::internal::_anonymous_namespace_::AddIntegerCompare_arrow::compute::internal::_anonymous_namespace_::Greater_(
      i,
      *a1);
  v13 = arrow::date32(v167);
  arrow::compute::internal::_anonymous_namespace_::AddIntegerCompare_arrow::compute::internal::_anonymous_namespace_::Greater_(
    v13,
    *a1);
  v14 = v168;
  if ( v168 )
  {
    if ( _InterlockedExchangeAdd(v168 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  v15 = arrow::date64(v171);
  arrow::compute::internal::_anonymous_namespace_::AddIntegerCompare_arrow::compute::internal::_anonymous_namespace_::Greater_(
    v15,
    *a1);
  v16 = v172;
  if ( v172 )
  {
    if ( _InterlockedExchangeAdd(v172 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  v17 = arrow::float32(v173);
  arrow::compute::internal::_anonymous_namespace_::AddGenericCompare_arrow::FloatType_arrow::compute::internal::_anonymous_namespace_::Greater_(
    v17,
    *a1);
  v18 = v174;
  if ( v174 )
  {
    if ( _InterlockedExchangeAdd(v174 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
  }
  v19 = arrow::float64(v175);
  arrow::compute::internal::_anonymous_namespace_::AddGenericCompare_arrow::DoubleType_arrow::compute::internal::_anonymous_namespace_::Greater_(
    v19,
    *a1);
  v20 = v176;
  if ( v176 )
  {
    if ( _InterlockedExchangeAdd(v176 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  v21 = arrow::compute::internal::AllTimeUnits();
  v22 = *(unsigned int **)v21;
  v23 = *(unsigned int **)(v21 + 8);
  if ( *(unsigned int **)v21 != v23 )
  {
    do
    {
      v24 = (_QWORD *)arrow::compute::match::TimestampTypeUnit(v159, *v22);
      v84 = 2;
      v85 = 0;
      *(_QWORD *)&v86 = *v24;
      v25 = v24[1];
      *((_QWORD *)&v86 + 1) = v25;
      *v24 = 0;
      v24[1] = 0;
      v93 = *(_DWORD *)(*(_QWORD *)arrow::int64(v177) + 24LL);
      ___GeneratePhysicalInteger___YScalarBinaryEqualTypes_applicator_internal_compute_arrow__VBooleanType_5_UGreater__A0x553c5b7f_345__internal_compute_arrow__YA_AV__function___A6AXPEAVKernelContext_compute_arrow__AEBUExecBatch_23_PEAUDatum_3__Z_std__UGetTypeId_detail_012__Z(v229);
      v26 = v178;
      if ( v178 )
      {
        if ( _InterlockedExchangeAdd(v178 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v26)(v26);
          if ( _InterlockedExchangeAdd(v26 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v26 + 8LL))(v26);
        }
      }
      v76 = v205;
      v75 = &v185;
      memset(v106, 0, sizeof(v106));
      v105 = 2;
      std::shared_ptr<arrow::ArrayData>::operator=(v106, &v85);
      if ( v25 )
        _InterlockedIncrement((volatile signed __int32 *)(v25 + 8));
      v27 = (volatile signed __int32 *)*((_QWORD *)&v106[1] + 1);
      v106[1] = v86;
      if ( v27 )
      {
        if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
          if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
        }
      }
      v108 = 0;
      v109 = 0;
      v107 = 2;
      std::shared_ptr<arrow::ArrayData>::operator=(&v108, &v85);
      if ( *((_QWORD *)&v86 + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v86 + 1) + 8LL));
      v28 = (volatile signed __int32 *)*((_QWORD *)&v109 + 1);
      v109 = v86;
      if ( v28 )
      {
        if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
          if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
        }
      }
      v218 = 0;
      v206 = 0;
      std::_Func_class<void,arrow::compute::KernelContext *,std::vector<arrow::Datum> *>::_Reset_move(v205, v229);
      v29 = arrow::boolean(v179);
      v185 = 0;
      v186 = 0;
      v186 = *(_OWORD *)v29;
      *(_QWORD *)v29 = 0;
      *(_QWORD *)(v29 + 8) = 0;
      v187 = 0;
      v188 = 0;
      v30 = *(volatile signed __int32 **)(v29 + 8);
      if ( v30 )
      {
        if ( _InterlockedExchangeAdd(v30 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
          if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
        }
      }
      v130 = 0;
      v131 = 0;
      std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(
        &v130,
        &v105,
        &v110,
        v73);
      arrow::compute::ScalarFunction::AddKernel(*a1, v142, &v130, &v185, v205, v217);
      if ( v143 )
      {
        arrow::Status::State::`scalar deleting destructor'(v143, 1u);
        v143 = 0;
      }
      `eh vector destructor iterator'(&v105, 0x28u, 2u, (void (*)(void *))arrow::compute::InputType::~InputType);
      if ( v230 )
      {
        v31 = v229;
        LOBYTE(v31) = v230 != v229;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v230 + 32LL))(v230, v31);
        v230 = 0;
      }
      if ( *((_QWORD *)&v86 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v86 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          v32 = *((_QWORD *)&v86 + 1);
          (***((void (__fastcall ****)(_QWORD))&v86 + 1))(*((_QWORD *)&v86 + 1));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v32 + 12), 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v86 + 1) + 8LL))(*((_QWORD *)&v86 + 1));
        }
      }
      ++v22;
    }
    while ( v22 != v23 );
  }
  v33 = arrow::compute::internal::AllTimeUnits();
  v34 = *(unsigned int **)v33;
  v35 = *(unsigned int **)(v33 + 8);
  if ( *(unsigned int **)v33 != v35 )
  {
    do
    {
      v36 = (_QWORD *)arrow::compute::match::DurationTypeUnit(v180, *v34);
      v81 = 2;
      v82 = 0;
      *(_QWORD *)&v83 = *v36;
      v37 = v36[1];
      *((_QWORD *)&v83 + 1) = v37;
      *v36 = 0;
      v36[1] = 0;
      v94 = *(_DWORD *)(*(_QWORD *)arrow::int64(v181) + 24LL);
      ___GeneratePhysicalInteger___YScalarBinaryEqualTypes_applicator_internal_compute_arrow__VBooleanType_5_UGreater__A0x553c5b7f_345__internal_compute_arrow__YA_AV__function___A6AXPEAVKernelContext_compute_arrow__AEBUExecBatch_23_PEAUDatum_3__Z_std__UGetTypeId_detail_012__Z(v231);
      v38 = v182;
      if ( v182 )
      {
        if ( _InterlockedExchangeAdd(v182 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v38)(v38);
          if ( _InterlockedExchangeAdd(v38 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v38 + 8LL))(v38);
        }
      }
      v76 = v207;
      v75 = &v189;
      memset(v101, 0, sizeof(v101));
      v100 = 2;
      std::shared_ptr<arrow::ArrayData>::operator=(v101, &v82);
      if ( v37 )
        _InterlockedIncrement((volatile signed __int32 *)(v37 + 8));
      v39 = (volatile signed __int32 *)*((_QWORD *)&v101[1] + 1);
      v101[1] = v83;
      if ( v39 )
      {
        if ( _InterlockedExchangeAdd(v39 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
          if ( _InterlockedExchangeAdd(v39 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
        }
      }
      v103 = 0;
      v104 = 0;
      v102 = 2;
      std::shared_ptr<arrow::ArrayData>::operator=(&v103, &v82);
      if ( *((_QWORD *)&v83 + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v83 + 1) + 8LL));
      v40 = (volatile signed __int32 *)*((_QWORD *)&v104 + 1);
      v104 = v83;
      if ( v40 )
      {
        if ( _InterlockedExchangeAdd(v40 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
          if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
        }
      }
      v220 = 0;
      v208 = 0;
      std::_Func_class<void,arrow::compute::KernelContext *,std::vector<arrow::Datum> *>::_Reset_move(v207, v231);
      v41 = arrow::boolean(v183);
      v189 = 0;
      v190 = 0;
      v190 = *(_OWORD *)v41;
      *(_QWORD *)v41 = 0;
      *(_QWORD *)(v41 + 8) = 0;
      v191 = 0;
      v192 = 0;
      v42 = *(volatile signed __int32 **)(v41 + 8);
      if ( v42 )
      {
        if ( _InterlockedExchangeAdd(v42 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
          if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
        }
      }
      v132 = 0;
      v133 = 0;
      std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(
        &v132,
        &v100,
        &v105,
        v73);
      arrow::compute::ScalarFunction::AddKernel(*a1, v144, &v132, &v189, v207, v219);
      if ( v145 )
      {
        arrow::Status::State::`scalar deleting destructor'(v145, 1u);
        v145 = 0;
      }
      `eh vector destructor iterator'(&v100, 0x28u, 2u, (void (*)(void *))arrow::compute::InputType::~InputType);
      if ( v232 )
      {
        v43 = v231;
        LOBYTE(v43) = v232 != v231;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v232 + 32LL))(v232, v43);
        v232 = 0;
      }
      if ( *((_QWORD *)&v83 + 1) )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v83 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          v44 = *((_QWORD *)&v83 + 1);
          (***((void (__fastcall ****)(_QWORD))&v83 + 1))(*((_QWORD *)&v83 + 1));
          if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v44 + 12), 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v83 + 1) + 8LL))(*((_QWORD *)&v83 + 1));
        }
      }
      ++v34;
    }
    while ( v34 != v35 );
  }
  v78[0] = 0;
  v78[1] = 1;
  v45 = v78;
  do
  {
    v46 = (_QWORD *)arrow::compute::match::Time32TypeUnit(v154, (unsigned int)*v45);
    v87 = 2;
    v88 = 0;
    *(_QWORD *)&v89 = *v46;
    v47 = v46[1];
    *((_QWORD *)&v89 + 1) = v47;
    *v46 = 0;
    v46[1] = 0;
    v95 = *(_DWORD *)(*(_QWORD *)arrow::int32(v155) + 24LL);
    ___GeneratePhysicalInteger___YScalarBinaryEqualTypes_applicator_internal_compute_arrow__VBooleanType_5_UGreater__A0x553c5b7f_345__internal_compute_arrow__YA_AV__function___A6AXPEAVKernelContext_compute_arrow__AEBUExecBatch_23_PEAUDatum_3__Z_std__UGetTypeId_detail_012__Z(v233);
    v48 = v156;
    if ( v156 )
    {
      if ( _InterlockedExchangeAdd(v156 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v48)(v48);
        if ( _InterlockedExchangeAdd(v48 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v48 + 8LL))(v48);
      }
    }
    v76 = v209;
    v75 = &v193;
    memset(v111, 0, sizeof(v111));
    v110 = 2;
    std::shared_ptr<arrow::ArrayData>::operator=(v111, &v88);
    if ( v47 )
      _InterlockedIncrement((volatile signed __int32 *)(v47 + 8));
    v49 = (volatile signed __int32 *)*((_QWORD *)&v111[1] + 1);
    v111[1] = v89;
    if ( v49 )
    {
      if ( _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
        if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
      }
    }
    v113 = 0;
    v114 = 0;
    v112 = 2;
    std::shared_ptr<arrow::ArrayData>::operator=(&v113, &v88);
    if ( *((_QWORD *)&v89 + 1) )
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v89 + 1) + 8LL));
    v50 = (volatile signed __int32 *)*((_QWORD *)&v114 + 1);
    v114 = v89;
    if ( v50 )
    {
      if ( _InterlockedExchangeAdd(v50 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v50)(v50);
        if ( _InterlockedExchangeAdd(v50 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v50 + 8LL))(v50);
      }
    }
    v222 = 0;
    v210 = 0;
    std::_Func_class<void,arrow::compute::KernelContext *,std::vector<arrow::Datum> *>::_Reset_move(v209, v233);
    v51 = arrow::boolean(v157);
    v193 = 0;
    v194 = 0;
    v194 = *(_OWORD *)v51;
    *(_QWORD *)v51 = 0;
    *(_QWORD *)(v51 + 8) = 0;
    v195 = 0;
    v196 = 0;
    v52 = *(volatile signed __int32 **)(v51 + 8);
    if ( v52 )
    {
      if ( _InterlockedExchangeAdd(v52 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v52)(v52);
        if ( _InterlockedExchangeAdd(v52 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v52 + 8LL))(v52);
      }
    }
    v134 = 0;
    v135 = 0;
    std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(
      &v134,
      &v110,
      &v115,
      v73);
    arrow::compute::ScalarFunction::AddKernel(*a1, v146, &v134, &v193, v209, v221);
    if ( v147 )
    {
      arrow::Status::State::`scalar deleting destructor'(v147, 1u);
      v147 = 0;
    }
    `eh vector destructor iterator'(&v110, 0x28u, 2u, (void (*)(void *))arrow::compute::InputType::~InputType);
    if ( v234 )
    {
      v53 = v233;
      LOBYTE(v53) = v234 != v233;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v234 + 32LL))(v234, v53);
      v234 = 0;
    }
    if ( *((_QWORD *)&v89 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v89 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        v54 = *((_QWORD *)&v89 + 1);
        (***((void (__fastcall ****)(_QWORD))&v89 + 1))(*((_QWORD *)&v89 + 1));
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v54 + 12), 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v89 + 1) + 8LL))(*((_QWORD *)&v89 + 1));
      }
    }
    ++v45;
  }
  while ( v45 != &v79 );
  v74[0] = 2;
  v74[1] = 3;
  v55 = (int **)v74;
  do
  {
    v56 = (_QWORD *)arrow::compute::match::Time64TypeUnit(v158, *(unsigned int *)v55);
    v90 = 2;
    v91 = 0;
    *(_QWORD *)&v92 = *v56;
    v57 = v56[1];
    *((_QWORD *)&v92 + 1) = v57;
    *v56 = 0;
    v56[1] = 0;
    v96 = *(_DWORD *)(*(_QWORD *)arrow::int64(v169) + 24LL);
    ___GeneratePhysicalInteger___YScalarBinaryEqualTypes_applicator_internal_compute_arrow__VBooleanType_5_UGreater__A0x553c5b7f_345__internal_compute_arrow__YA_AV__function___A6AXPEAVKernelContext_compute_arrow__AEBUExecBatch_23_PEAUDatum_3__Z_std__UGetTypeId_detail_012__Z(v235);
    v58 = v170;
    if ( v170 )
    {
      if ( _InterlockedExchangeAdd(v170 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
        if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
      }
    }
    v76 = v213;
    v75 = &v197;
    memset(v116, 0, sizeof(v116));
    v115 = 2;
    std::shared_ptr<arrow::ArrayData>::operator=(v116, &v91);
    if ( v57 )
      _InterlockedIncrement((volatile signed __int32 *)(v57 + 8));
    v59 = (volatile signed __int32 *)*((_QWORD *)&v116[1] + 1);
    v116[1] = v92;
    if ( v59 )
    {
      if ( _InterlockedExchangeAdd(v59 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
        if ( _InterlockedExchangeAdd(v59 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
      }
    }
    v118 = 0;
    v119 = 0;
    v117 = 2;
    std::shared_ptr<arrow::ArrayData>::operator=(&v118, &v91);
    if ( *((_QWORD *)&v92 + 1) )
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v92 + 1) + 8LL));
    v60 = (volatile signed __int32 *)*((_QWORD *)&v119 + 1);
    v119 = v92;
    if ( v60 )
    {
      if ( _InterlockedExchangeAdd(v60 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v60)(v60);
        if ( _InterlockedExchangeAdd(v60 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v60 + 8LL))(v60);
      }
    }
    v224 = 0;
    v214 = 0;
    std::_Func_class<void,arrow::compute::KernelContext *,std::vector<arrow::Datum> *>::_Reset_move(v213, v235);
    v61 = (_QWORD *)arrow::boolean(v160);
    v197 = 0;
    v198 = 0;
    v198 = *(_OWORD *)v61;
    *v61 = 0;
    v61[1] = 0;
    v199 = 0;
    v200 = 0;
    arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v61);
    v136 = 0;
    v137 = 0;
    std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(
      &v136,
      &v115,
      &v120,
      v73);
    arrow::compute::ScalarFunction::AddKernel(*a1, v148, &v136, &v197, v213, v223);
    if ( v149 )
    {
      arrow::Status::State::`scalar deleting destructor'(v149, 1u);
      v149 = 0;
    }
    `eh vector destructor iterator'(&v115, 0x28u, 2u, (void (*)(void *))arrow::compute::InputType::~InputType);
    if ( v236 )
    {
      v62 = v235;
      LOBYTE(v62) = v236 != v235;
      (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v236 + 32LL))(v236, v62);
      v236 = 0;
    }
    arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(&v92);
    arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(&v91);
    v55 = (int **)((char *)v55 + 4);
  }
  while ( v55 != &v75 );
  v63 = arrow::compute::internal::BaseBinaryTypes();
  v64 = *(_QWORD **)v63;
  v65 = *(_QWORD **)(v63 + 8);
  if ( *(_QWORD **)v63 != v65 )
  {
    v98[1] = 0;
    v99[1] = 0;
    do
    {
      v97 = *(_DWORD *)(*v64 + 24LL);
      ___GenerateVarBinaryBase___YScalarBinaryEqualTypes_applicator_internal_compute_arrow__VBooleanType_5_UGreater__A0x553c5b7f_345__internal_compute_arrow__YA_AV__function___A6AXPEAVKernelContext_compute_arrow__AEBUExecBatch_23_PEAUDatum_3__Z_std__UGetTypeId_detail_012__Z(v237);
      v76 = v211;
      v75 = &v201;
      v66 = v64[1];
      if ( v66 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v66 + 8));
        v66 = v64[1];
      }
      v67 = *v64;
      v152[0] = 1;
      v152[1] = v67;
      v152[2] = v66;
      v98[0] = 0;
      v152[3] = 0;
      v152[4] = 0;
      arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v98);
      v68 = v64[1];
      if ( v68 )
      {
        _InterlockedIncrement((volatile signed __int32 *)(v68 + 8));
        v68 = v64[1];
      }
      v69 = *v64;
      v152[5] = 1;
      v152[6] = v69;
      v152[7] = v68;
      v99[0] = 0;
      v153 = 0;
      arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v99);
      v226 = 0;
      v212 = 0;
      std::_Func_class<void,arrow::compute::KernelContext *,std::vector<arrow::Datum> *>::_Reset_move(v211, v237);
      v70 = (_QWORD *)arrow::boolean(v161);
      v201 = 0;
      v202 = 0;
      v202 = *(_OWORD *)v70;
      *v70 = 0;
      v70[1] = 0;
      v203 = 0;
      v204 = 0;
      arrow::TypedBufferBuilder<__int64,void>::~TypedBufferBuilder<__int64,void>(v70);
      v138 = 0;
      v139 = 0;
      std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(
        &v138,
        v152,
        v154,
        v73);
      arrow::compute::ScalarFunction::AddKernel(*a1, v150, &v138, &v201, v211, v225);
      if ( v151 )
      {
        arrow::Status::State::`scalar deleting destructor'(v151, 1u);
        v151 = 0;
      }
      `eh vector destructor iterator'(v152, 0x28u, 2u, (void (*)(void *))arrow::compute::InputType::~InputType);
      if ( v238 )
      {
        v71 = v237;
        LOBYTE(v71) = v238 != v237;
        (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v238 + 32LL))(v238, v71);
      }
      v64 += 2;
    }
    while ( v64 != v65 );
  }
  std::string::~string(a2);
  return a1;
}

```

## disassembly

```asm
0x1801afb30  push    rbp
0x1801afb32  push    rsi
0x1801afb33  push    rdi
0x1801afb34  push    r12
0x1801afb36  push    r13
0x1801afb38  push    r14
0x1801afb3a  push    r15
0x1801afb3c  lea     rbp, [rsp-0B10h]
0x1801afb44  sub     rsp, 0C10h
0x1801afb4b  mov     [rbp+0B40h+var_7A8], 0FFFFFFFFFFFFFFFEh
0x1801afb56  mov     [rsp+0C40h+arg_10], rbx
0x1801afb5e  mov     rax, cs:__security_cookie
0x1801afb65  xor     rax, rsp
0x1801afb68  mov     [rbp+0B40h+var_40], rax
0x1801afb6f  mov     r13, rdx
0x1801afb72  mov     r12, rcx
0x1801afb75  mov     [rbp+0B40h+var_7B0], rcx
0x1801afb7c  mov     [rbp+0B40h+var_190], rdx
0x1801afb83  xor     esi, esi
0x1801afb85  mov     [rsp+0C40h+var_BE0], esi
0x1801afb89  mov     [rsp+0C40h+var_BD0], 2
0x1801afb91  mov     [rsp+0C40h+var_BCC], sil
0x1801afb96  lea     r8, [rsp+0C40h+var_BD0]
0x1801afb9b  call    ??$make_shared@VScalarFunction@compute@arrow@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@UArity@23@@std@@YA?AV?$shared_ptr@VScalarFunction@compute@arrow@@@0@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@$$QEAUArity@compute@arrow@@@Z; std::make_shared<arrow::compute::ScalarFunction,std::string &,arrow::compute::Arity>(std::string &,arrow::compute::Arity &&)
0x1801afba0  mov     [rsp+0C40h+var_BE0], 1
0x1801afba8  lea     rax, [rbp+0B40h+var_370]
0x1801afbaf  mov     [rsp+0C40h+var_C08], rax
0x1801afbb4  lea     rax, [rbp+0B40h+var_6D0]
0x1801afbbb  mov     [rsp+0C40h+var_BF0], rax
0x1801afbc0  lea     rax, [rbp+0B40h+var_1F0]
0x1801afbc7  mov     [rsp+0C40h+var_BE8], rax
0x1801afbcc  lea     rcx, [rbp+0B40h+var_7A0]
0x1801afbd3  call    ?boolean@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::boolean(void)
0x1801afbd8  mov     rcx, rax
0x1801afbdb  mov     [rbp+0B40h+var_9B0], 1
0x1801afbe6  mov     [rbp+0B40h+var_9A8], rsi
0x1801afbed  mov     [rbp+0B40h+var_9A0], rsi
0x1801afbf4  mov     rax, [rax]
0x1801afbf7  mov     [rbp+0B40h+var_9A8], rax
0x1801afbfe  mov     rax, [rcx+8]
0x1801afc02  mov     [rbp+0B40h+var_9A0], rax
0x1801afc09  mov     [rcx], rsi
0x1801afc0c  mov     [rcx+8], rsi
0x1801afc10  mov     [rbp+0B40h+var_998], rsi
0x1801afc17  mov     [rbp+0B40h+var_990], rsi
0x1801afc1e  mov     rbx, [rcx+8]
0x1801afc22  test    rbx, rbx
0x1801afc25  jz      short loc_1801AFC65
0x1801afc27  mov     eax, 0FFFFFFFFh
0x1801afc2c  lock xadd [rbx+8], eax
0x1801afc31  cmp     eax, 1
0x1801afc34  jnz     short loc_1801AFC65
0x1801afc36  mov     rax, [rbx]
0x1801afc39  mov     rcx, rbx
0x1801afc3c  mov     rax, [rax]
0x1801afc3f  call    cs:__guard_dispatch_icall_fptr
0x1801afc45  mov     eax, 0FFFFFFFFh
0x1801afc4a  lock xadd [rbx+0Ch], eax
0x1801afc4f  cmp     eax, 1
0x1801afc52  jnz     short loc_1801AFC65
0x1801afc54  mov     rax, [rbx]
0x1801afc57  mov     rcx, rbx
0x1801afc5a  mov     rax, [rax+8]
0x1801afc5e  call    cs:__guard_dispatch_icall_fptr
0x1801afc64  nop
0x1801afc65  lea     rcx, [rbp+0B40h+var_790]
0x1801afc6c  call    ?boolean@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::boolean(void)
0x1801afc71  mov     rcx, rax
0x1801afc74  mov     [rbp+0B40h+var_988], 1
0x1801afc7f  xorps   xmm0, xmm0
0x1801afc82  movdqa  [rbp+0B40h+var_980], xmm0
0x1801afc8a  mov     rax, [rax]
0x1801afc8d  mov     qword ptr [rbp+0B40h+var_980], rax
0x1801afc94  mov     rax, [rcx+8]
0x1801afc98  mov     qword ptr [rbp+0B40h+var_980+8], rax
0x1801afc9f  mov     [rcx], rsi
0x1801afca2  mov     [rcx+8], rsi
0x1801afca6  movdqa  [rbp+0B40h+var_970], xmm0
0x1801afcae  mov     rbx, [rcx+8]
0x1801afcb2  test    rbx, rbx
0x1801afcb5  jz      short loc_1801AFCF5
0x1801afcb7  mov     eax, 0FFFFFFFFh
0x1801afcbc  lock xadd [rbx+8], eax
0x1801afcc1  cmp     eax, 1
0x1801afcc4  jnz     short loc_1801AFCF5
0x1801afcc6  mov     rax, [rbx]
0x1801afcc9  mov     rcx, rbx
0x1801afccc  mov     rax, [rax]
0x1801afccf  call    cs:__guard_dispatch_icall_fptr
0x1801afcd5  mov     eax, 0FFFFFFFFh
0x1801afcda  lock xadd [rbx+0Ch], eax
0x1801afcdf  cmp     eax, 1
0x1801afce2  jnz     short loc_1801AFCF5
0x1801afce4  mov     rax, [rbx]
0x1801afce7  mov     rcx, rbx
0x1801afcea  mov     rax, [rax+8]
0x1801afcee  call    cs:__guard_dispatch_icall_fptr
0x1801afcf4  nop
0x1801afcf5  mov     [rbp+0B40h+var_338], rsi
0x1801afcfc  lea     rax, ??_7?$_Func_impl_no_alloc@P6AXPEAVKernelContext@compute@arrow@@AEBUExecBatch@23@PEAUDatum@3@@ZXPEAV123@AEBU423@PEAU53@@std@@6B@; const std::_Func_impl_no_alloc<void (*)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void,arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *>::`vftable'
0x1801afd03  mov     [rbp+0B40h+var_6D0], rax
0x1801afd0a  lea     rax, arrow__compute__internal__applicator__ScalarBinary_arrow__BooleanType_arrow__BooleanType_arrow__BooleanType_arrow__compute__internal___anonymous_namespace___Greater___Exec
0x1801afd11  mov     [rbp+0B40h+var_6C8], rax
0x1801afd18  lea     rax, [rbp+0B40h+var_6D0]
0x1801afd1f  mov     [rbp+0B40h+var_698], rax
0x1801afd26  lea     rcx, [rbp+0B40h+var_780]
0x1801afd2d  call    ?boolean@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::boolean(void)
0x1801afd32  mov     rdx, rax
0x1801afd35  lea     rcx, [rbp+0B40h+var_1F0]
0x1801afd3c  call    ??0OutputType@compute@arrow@@QEAA@V?$shared_ptr@VDataType@arrow@@@std@@@Z; arrow::compute::OutputType::OutputType(std::shared_ptr<arrow::DataType>)
0x1801afd41  mov     rbx, rax
0x1801afd44  xorps   xmm0, xmm0
0x1801afd47  movdqu  [rbp+0B40h+var_960], xmm0
0x1801afd4f  mov     [rbp+0B40h+var_950], rsi
0x1801afd56  movzx   r9d, [rsp+0C40h+var_C10]
0x1801afd5c  lea     r8, [rbp+0B40h+var_960]
0x1801afd63  lea     rdx, [rbp+0B40h+var_9B0]
0x1801afd6a  lea     rcx, [rbp+0B40h+var_960]
0x1801afd71  call    ??$_Range_construct_or_tidy@PEBVInputType@compute@arrow@@@?$vector@VInputType@compute@arrow@@V?$allocator@VInputType@compute@arrow@@@std@@@std@@AEAAXPEBVInputType@compute@arrow@@0Uforward_iterator_tag@1@@Z; std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(arrow::compute::InputType const *,arrow::compute::InputType const *,std::forward_iterator_tag)
0x1801afd76  nop
0x1801afd77  lea     rax, [rbp+0B40h+var_370]
0x1801afd7e  mov     [rsp+0C40h+var_C18], rax
0x1801afd83  lea     rax, [rbp+0B40h+var_6D0]
0x1801afd8a  mov     [rsp+0C40h+var_C20], rax
0x1801afd8f  mov     r9, rbx
0x1801afd92  lea     r8, [rbp+0B40h+var_960]
0x1801afd99  lea     rdx, [rbp+0B40h+var_8D0]
0x1801afda0  mov     rcx, [r12]
0x1801afda4  call    ?AddKernel@ScalarFunction@compute@arrow@@QEAA?AVStatus@3@V?$vector@VInputType@compute@arrow@@V?$allocator@VInputType@compute@arrow@@@std@@@std@@VOutputType@23@V?$function@$$A6AXPEAVKernelContext@compute@arrow@@AEBUExecBatch@23@PEAUDatum@3@@Z@6@V?$function@$$A6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@45@@Z@6@@Z; arrow::compute::ScalarFunction::AddKernel(std::vector<arrow::compute::InputType>,arrow::compute::OutputType,std::function<void (arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *)>,std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>)
0x1801afda9  mov     rcx, [rbp+0B40h+var_8C8]; this
0x1801afdb0  test    rcx, rcx
0x1801afdb3  jz      short loc_1801AFDC6
0x1801afdb5  mov     edx, 1; unsigned int
0x1801afdba  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1801afdbf  mov     [rbp+0B40h+var_8C8], rsi
0x1801afdc6  lea     r9, ??1InputType@compute@arrow@@QEAA@XZ; void (*)(void *)
0x1801afdcd  mov     edx, 28h ; '('; unsigned __int64
0x1801afdd2  lea     r8d, [rdx-26h]; unsigned __int64
0x1801afdd6  lea     rcx, [rbp+0B40h+var_9B0]; void *
0x1801afddd  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1801afde2  call    ?IntTypes@internal@compute@arrow@@YAAEBV?$vector@V?$shared_ptr@VDataType@arrow@@@std@@V?$allocator@V?$shared_ptr@VDataType@arrow@@@std@@@2@@std@@XZ; arrow::compute::internal::IntTypes(void)
0x1801afde7  mov     rdi, [rax+8]
0x1801afdeb  mov     rbx, [rax]
0x1801afdee  cmp     rbx, rdi
0x1801afdf1  jz      short loc_1801AFE08
0x1801afdf3  mov     rdx, [r12]
0x1801afdf7  mov     rcx, rbx
0x1801afdfa  call    arrow__compute__internal___anonymous_namespace___AddIntegerCompare_arrow__compute__internal___anonymous_namespace___Greater_
0x1801afdff  add     rbx, 10h
0x1801afe03  cmp     rbx, rdi
0x1801afe06  jnz     short loc_1801AFDF3
0x1801afe08  lea     rcx, [rbp+0B40h+var_770]
0x1801afe0f  call    ?date32@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::date32(void)
0x1801afe14  nop
0x1801afe15  mov     rdx, [r12]
0x1801afe19  mov     rcx, rax
0x1801afe1c  call    arrow__compute__internal___anonymous_namespace___AddIntegerCompare_arrow__compute__internal___anonymous_namespace___Greater_
0x1801afe21  nop
0x1801afe22  mov     rbx, [rbp+0B40h+var_768]
0x1801afe29  test    rbx, rbx
0x1801afe2c  jz      short loc_1801AFE6B
0x1801afe2e  mov     eax, 0FFFFFFFFh
0x1801afe33  lock xadd [rbx+8], eax
0x1801afe38  cmp     eax, 1
0x1801afe3b  jnz     short loc_1801AFE6B
0x1801afe3d  mov     rax, [rbx]
0x1801afe40  mov     rcx, rbx
0x1801afe43  mov     rax, [rax]
0x1801afe46  call    cs:__guard_dispatch_icall_fptr
0x1801afe4c  mov     eax, 0FFFFFFFFh
0x1801afe51  lock xadd [rbx+0Ch], eax
0x1801afe56  cmp     eax, 1
0x1801afe59  jnz     short loc_1801AFE6B
0x1801afe5b  mov     rax, [rbx]
0x1801afe5e  mov     rcx, rbx
0x1801afe61  mov     rax, [rax+8]
0x1801afe65  call    cs:__guard_dispatch_icall_fptr
0x1801afe6b  lea     rcx, [rbp+0B40h+var_750]
0x1801afe72  call    ?date64@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::date64(void)
0x1801afe77  nop
0x1801afe78  mov     rdx, [r12]
0x1801afe7c  mov     rcx, rax
0x1801afe7f  call    arrow__compute__internal___anonymous_namespace___AddIntegerCompare_arrow__compute__internal___anonymous_namespace___Greater_
0x1801afe84  nop
0x1801afe85  mov     rbx, [rbp+0B40h+var_748]
0x1801afe8c  test    rbx, rbx
0x1801afe8f  jz      short loc_1801AFECE
0x1801afe91  mov     eax, 0FFFFFFFFh
0x1801afe96  lock xadd [rbx+8], eax
0x1801afe9b  cmp     eax, 1
0x1801afe9e  jnz     short loc_1801AFECE
0x1801afea0  mov     rax, [rbx]
0x1801afea3  mov     rcx, rbx
0x1801afea6  mov     rax, [rax]
0x1801afea9  call    cs:__guard_dispatch_icall_fptr
0x1801afeaf  mov     eax, 0FFFFFFFFh
0x1801afeb4  lock xadd [rbx+0Ch], eax
0x1801afeb9  cmp     eax, 1
0x1801afebc  jnz     short loc_1801AFECE
0x1801afebe  mov     rax, [rbx]
0x1801afec1  mov     rcx, rbx
0x1801afec4  mov     rax, [rax+8]
0x1801afec8  call    cs:__guard_dispatch_icall_fptr
0x1801afece  lea     rcx, [rbp+0B40h+var_740]
0x1801afed5  call    ?float32@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::float32(void)
0x1801afeda  nop
0x1801afedb  mov     rdx, [r12]
0x1801afedf  mov     rcx, rax
0x1801afee2  call    arrow__compute__internal___anonymous_namespace___AddGenericCompare_arrow__FloatType_arrow__compute__internal___anonymous_namespace___Greater_
0x1801afee7  nop
0x1801afee8  mov     rbx, [rbp+0B40h+var_738]
0x1801afeef  test    rbx, rbx
0x1801afef2  jz      short loc_1801AFF31
0x1801afef4  mov     eax, 0FFFFFFFFh
0x1801afef9  lock xadd [rbx+8], eax
0x1801afefe  cmp     eax, 1
0x1801aff01  jnz     short loc_1801AFF31
0x1801aff03  mov     rax, [rbx]
0x1801aff06  mov     rcx, rbx
0x1801aff09  mov     rax, [rax]
0x1801aff0c  call    cs:__guard_dispatch_icall_fptr
0x1801aff12  mov     eax, 0FFFFFFFFh
0x1801aff17  lock xadd [rbx+0Ch], eax
0x1801aff1c  cmp     eax, 1
0x1801aff1f  jnz     short loc_1801AFF31
0x1801aff21  mov     rax, [rbx]
0x1801aff24  mov     rcx, rbx
0x1801aff27  mov     rax, [rax+8]
0x1801aff2b  call    cs:__guard_dispatch_icall_fptr
0x1801aff31  lea     rcx, [rbp+0B40h+var_730]
0x1801aff38  call    ?float64@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::float64(void)
0x1801aff3d  nop
0x1801aff3e  mov     rdx, [r12]
0x1801aff42  mov     rcx, rax
0x1801aff45  call    arrow__compute__internal___anonymous_namespace___AddGenericCompare_arrow__DoubleType_arrow__compute__internal___anonymous_namespace___Greater_
0x1801aff4a  nop
0x1801aff4b  mov     rbx, [rbp+0B40h+var_728]
0x1801aff52  test    rbx, rbx
0x1801aff55  jz      short loc_1801AFF94
0x1801aff57  mov     eax, 0FFFFFFFFh
0x1801aff5c  lock xadd [rbx+8], eax
0x1801aff61  cmp     eax, 1
0x1801aff64  jnz     short loc_1801AFF94
0x1801aff66  mov     rax, [rbx]
0x1801aff69  mov     rcx, rbx
0x1801aff6c  mov     rax, [rax]
0x1801aff6f  call    cs:__guard_dispatch_icall_fptr
0x1801aff75  mov     eax, 0FFFFFFFFh
0x1801aff7a  lock xadd [rbx+0Ch], eax
0x1801aff7f  cmp     eax, 1
0x1801aff82  jnz     short loc_1801AFF94
0x1801aff84  mov     rax, [rbx]
0x1801aff87  mov     rcx, rbx
0x1801aff8a  mov     rax, [rax+8]
0x1801aff8e  call    cs:__guard_dispatch_icall_fptr
0x1801aff94  call    ?AllTimeUnits@internal@compute@arrow@@YAAEBV?$vector@W4type@TimeUnit@arrow@@V?$allocator@W4type@TimeUnit@arrow@@@std@@@std@@XZ; arrow::compute::internal::AllTimeUnits(void)
0x1801aff99  mov     r14, [rax]
0x1801aff9c  mov     r15, [rax+8]
0x1801affa0  cmp     r14, r15
0x1801affa3  jz      loc_1801B038F
0x1801affa9  movzx   ebx, [rsp+0C40h+var_C10]
0x1801affae  xchg    ax, ax
0x1801affb0  mov     edx, [r14]
0x1801affb3  lea     rcx, [rbp+0B40h+var_7E0]
0x1801affba  call    ?TimestampTypeUnit@match@compute@arrow@@YA?AV?$shared_ptr@UTypeMatcher@compute@arrow@@@std@@W4type@TimeUnit@3@@Z; arrow::compute::match::TimestampTypeUnit(arrow::TimeUnit::type)
0x1801affbf  mov     rcx, rax
0x1801affc2  mov     [rbp+0B40h+var_BA0], 2
0x1801affca  xorps   xmm0, xmm0
0x1801affcd  movdqu  [rbp+0B40h+var_B98], xmm0
0x1801affd2  mov     rax, [rax]
0x1801affd5  mov     [rbp+0B40h+var_B88], rax
0x1801affd9  mov     rsi, [rcx+8]
0x1801affdd  mov     [rbp+0B40h+var_B80], rsi
0x1801affe1  xor     eax, eax
0x1801affe3  mov     [rcx], rax
0x1801affe6  mov     [rcx+8], rax
0x1801affea  lea     rcx, [rbp+0B40h+var_720]
0x1801afff1  call    ?int64@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::int64(void)
0x1801afff6  mov     rcx, [rax]
0x1801afff9  mov     edx, [rcx+18h]
0x1801afffc  mov     [rbp+0B40h+var_B28], edx
0x1801affff  lea     rcx, [rbp+0B40h+var_180]
0x1801b0006  call    ??$GeneratePhysicalInteger@$$YScalarBinaryEqualTypes@applicator@internal@compute@arrow@@VBooleanType@5@UGreater@?A0x553c5b7f@345@@internal@compute@arrow@@YA?AV?$function@$$A6AXPEAVKernelContext@compute@arrow@@AEBUExecBatch@23@PEAUDatum@3@@Z@std@@UGetTypeId@detail@012@@Z
0x1801b000b  nop
0x1801b000c  mov     rdi, [rbp+0B40h+var_718]
0x1801b0013  test    rdi, rdi
0x1801b0016  jz      short loc_1801B0055
0x1801b0018  mov     eax, 0FFFFFFFFh
0x1801b001d  lock xadd [rdi+8], eax
0x1801b0022  cmp     eax, 1
0x1801b0025  jnz     short loc_1801B0055
0x1801b0027  mov     rax, [rdi]
0x1801b002a  mov     rcx, rdi
0x1801b002d  mov     rax, [rax]
0x1801b0030  call    cs:__guard_dispatch_icall_fptr
0x1801b0036  mov     eax, 0FFFFFFFFh
0x1801b003b  lock xadd [rdi+0Ch], eax
0x1801b0040  cmp     eax, 1
0x1801b0043  jnz     short loc_1801B0055
0x1801b0045  mov     rax, [rdi]
  ... truncated ...
```
