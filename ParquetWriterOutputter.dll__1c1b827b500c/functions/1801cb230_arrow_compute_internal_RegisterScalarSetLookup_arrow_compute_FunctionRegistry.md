# arrow::compute::internal::RegisterScalarSetLookup(arrow::compute::FunctionRegistry *)

- ea: `0x1801cb230`
- end: `0x1801cbd26`
- name: `?RegisterScalarSetLookup@internal@compute@arrow@@YAXPEAVFunctionRegistry@23@@Z`
- size: `2806`
- prototype: `void __fastcall(arrow::compute::internal *__hidden this, struct arrow::compute::FunctionRegistry *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18012d690`

## callees

- `0x180010860`
- `0x18001f8c0`
- `0x1800a8dd0`
- `0x1800a99c0`
- `0x1800aad60`
- `0x180127ce0`
- `0x18012b4f0`
- `0x18012d340`
- `0x18012f8a0`
- `0x18012fa90`
- `0x1801550d0`
- `0x1801bfc30`
- `0x1801c85c0`
- `0x1801c8680`
- `0x1801c8750`
- `0x1801c8e00`
- `0x1801cb230`
- `0x1802f0fb0`
- `0x18030c200`
- `0x18030c3f0`
- `0x180358070`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall arrow::compute::internal::RegisterScalarSetLookup(
        arrow::compute::internal *this,
        struct arrow::compute::FunctionRegistry *a2)
{
  volatile signed __int32 *v3; // rax
  volatile signed __int32 *v4; // r14
  arrow::compute::Kernel *v5; // rax
  volatile signed __int32 *v6; // rbx
  __int64 v7; // rax
  volatile signed __int32 *v8; // rbx
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 *v11; // rax
  __int64 v12; // rcx
  __int64 v13; // rdx
  volatile signed __int32 *v14; // rbx
  volatile signed __int32 *v15; // rbx
  __int64 v16; // rax
  _DWORD *v17; // rax
  _DWORD *v18; // rdi
  _BYTE *v19; // rdx
  _BYTE *v20; // rdx
  volatile signed __int32 *v21; // rbx
  volatile signed __int32 *v22; // rax
  volatile signed __int32 *v23; // r14
  arrow::compute::Kernel *v24; // rax
  volatile signed __int32 *v25; // rbx
  __int64 v26; // rax
  volatile signed __int32 *v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 *v30; // rax
  __int64 v31; // rcx
  __int64 v32; // rdx
  volatile signed __int32 *v33; // rbx
  volatile signed __int32 *v34; // rbx
  __int64 v35; // rax
  _DWORD *v36; // rax
  _DWORD *v37; // rdi
  _BYTE *v38; // rdx
  _BYTE *v39; // rdx
  volatile signed __int32 *v40; // rbx
  int v41; // [rsp+28h] [rbp-E0h]
  int v42; // [rsp+28h] [rbp-E0h]
  volatile signed __int32 *v43; // [rsp+40h] [rbp-C8h] BYREF
  int v44; // [rsp+48h] [rbp-C0h] BYREF
  char v45; // [rsp+4Ch] [rbp-BCh]
  int v46; // [rsp+50h] [rbp-B8h] BYREF
  char v47; // [rsp+54h] [rbp-B4h]
  int v48; // [rsp+58h] [rbp-B0h] BYREF
  char v49; // [rsp+5Ch] [rbp-ACh]
  __int128 v50; // [rsp+60h] [rbp-A8h] BYREF
  __int128 v51; // [rsp+70h] [rbp-98h] BYREF
  _QWORD v52[2]; // [rsp+80h] [rbp-88h] BYREF
  volatile signed __int32 *v53; // [rsp+90h] [rbp-78h]
  volatile signed __int32 *v54; // [rsp+98h] [rbp-70h]
  _QWORD v55[2]; // [rsp+A0h] [rbp-68h] BYREF
  volatile signed __int32 *v56; // [rsp+B0h] [rbp-58h]
  volatile signed __int32 *v57; // [rsp+B8h] [rbp-50h]
  __int64 v58; // [rsp+C0h] [rbp-48h] BYREF
  __int128 v59; // [rsp+C8h] [rbp-40h]
  __int128 v60; // [rsp+D8h] [rbp-30h]
  __int64 v61; // [rsp+E8h] [rbp-20h] BYREF
  __int128 v62; // [rsp+F0h] [rbp-18h]
  __int128 v63; // [rsp+100h] [rbp-8h]
  __int128 v64; // [rsp+110h] [rbp+8h] BYREF
  __int64 v65; // [rsp+120h] [rbp+18h]
  __int128 v66; // [rsp+128h] [rbp+20h] BYREF
  __int64 v67; // [rsp+138h] [rbp+30h]
  _BYTE v68[16]; // [rsp+140h] [rbp+38h] BYREF
  __int64 v69; // [rsp+150h] [rbp+48h]
  __int64 v70; // [rsp+158h] [rbp+50h]
  _BYTE v71[16]; // [rsp+160h] [rbp+58h] BYREF
  __int64 v72; // [rsp+170h] [rbp+68h]
  __int64 v73; // [rsp+178h] [rbp+70h]
  _BYTE v74[16]; // [rsp+180h] [rbp+78h] BYREF
  __int64 v75; // [rsp+190h] [rbp+88h]
  __int64 v76; // [rsp+198h] [rbp+90h]
  _BYTE v77[16]; // [rsp+1A0h] [rbp+98h] BYREF
  __int64 v78; // [rsp+1B0h] [rbp+A8h]
  __int64 v79; // [rsp+1B8h] [rbp+B0h]
  _BYTE v80[8]; // [rsp+1C0h] [rbp+B8h] BYREF
  arrow::Status::State *v81; // [rsp+1C8h] [rbp+C0h]
  _BYTE v82[8]; // [rsp+1D0h] [rbp+C8h] BYREF
  arrow::Status::State *v83; // [rsp+1D8h] [rbp+D0h]
  _BYTE v84[8]; // [rsp+1E0h] [rbp+D8h] BYREF
  volatile signed __int32 *v85; // [rsp+1E8h] [rbp+E0h]
  _BYTE v86[16]; // [rsp+1F0h] [rbp+E8h] BYREF
  _BYTE v87[16]; // [rsp+200h] [rbp+F8h] BYREF
  _BYTE v88[8]; // [rsp+210h] [rbp+108h] BYREF
  volatile signed __int32 *v89; // [rsp+218h] [rbp+110h]
  _BYTE v90[8]; // [rsp+220h] [rbp+118h] BYREF
  arrow::Status::State *v91; // [rsp+228h] [rbp+120h]
  _BYTE v92[8]; // [rsp+230h] [rbp+128h] BYREF
  arrow::Status::State *v93; // [rsp+238h] [rbp+130h]
  _BYTE v94[8]; // [rsp+240h] [rbp+138h] BYREF
  arrow::Status::State *v95; // [rsp+248h] [rbp+140h]
  __int64 v96; // [rsp+250h] [rbp+148h]
  __int64 v97; // [rsp+258h] [rbp+150h]
  __int64 v98; // [rsp+260h] [rbp+158h]
  _BYTE v99[8]; // [rsp+268h] [rbp+160h] BYREF
  volatile signed __int32 *v100; // [rsp+270h] [rbp+168h]
  _BYTE v101[16]; // [rsp+278h] [rbp+170h] BYREF
  _BYTE v102[16]; // [rsp+288h] [rbp+180h] BYREF
  _BYTE v103[8]; // [rsp+298h] [rbp+190h] BYREF
  volatile signed __int32 *v104; // [rsp+2A0h] [rbp+198h]
  _BYTE v105[8]; // [rsp+2A8h] [rbp+1A0h] BYREF
  arrow::Status::State *v106; // [rsp+2B0h] [rbp+1A8h]
  __int128 v107; // [rsp+2B8h] [rbp+1B0h]
  __int128 v108; // [rsp+2C8h] [rbp+1C0h]
  _BYTE v109[96]; // [rsp+2D8h] [rbp+1D0h] BYREF
  _BYTE v110[96]; // [rsp+338h] [rbp+230h] BYREF
  _BYTE v111[168]; // [rsp+398h] [rbp+290h] BYREF
  _BYTE v112[168]; // [rsp+440h] [rbp+338h] BYREF
  _BYTE v113[168]; // [rsp+4E8h] [rbp+3E0h] BYREF
  _BYTE v114[168]; // [rsp+590h] [rbp+488h] BYREF
  __int128 v115; // [rsp+638h] [rbp+530h] BYREF
  _BYTE v116[56]; // [rsp+648h] [rbp+540h] BYREF
  _BYTE *v117; // [rsp+680h] [rbp+578h]
  char v118; // [rsp+688h] [rbp+580h]
  int v119; // [rsp+68Ch] [rbp+584h]
  _BYTE v120[56]; // [rsp+690h] [rbp+588h] BYREF
  _BYTE *v121; // [rsp+6C8h] [rbp+5C0h]
  char v122; // [rsp+6D0h] [rbp+5C8h]
  __int64 v123; // [rsp+6D8h] [rbp+5D0h]
  __int128 v124; // [rsp+6E8h] [rbp+5E0h] BYREF
  _BYTE v125[56]; // [rsp+6F8h] [rbp+5F0h] BYREF
  _BYTE *v126; // [rsp+730h] [rbp+628h]
  char v127; // [rsp+738h] [rbp+630h]
  int v128; // [rsp+73Ch] [rbp+634h]
  _BYTE v129[56]; // [rsp+740h] [rbp+638h] BYREF
  _BYTE *v130; // [rsp+778h] [rbp+670h]
  char v131; // [rsp+780h] [rbp+678h]
  __int64 v132; // [rsp+788h] [rbp+680h]

  v96 = -2;
  v124 = 0;
  v126 = 0;
  v127 = 1;
  v128 = 0;
  v130 = 0;
  v131 = 1;
  v132 = 0;
  std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>::operator=<std::unique_ptr<arrow::compute::KernelState> (&)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),void>(
    v125,
    &arrow::compute::internal::_anonymous_namespace_::InitSetLookup);
  std::function<void (arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *)>::operator=<void (&)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void>(
    v129,
    arrow::compute::internal::_anonymous_namespace_::ExecIsIn);
  v46 = 1;
  v47 = 0;
  v3 = (volatile signed __int32 *)operator new(0x68u);
  v4 = v3;
  v43 = v3;
  if ( v3 )
  {
    *((_DWORD *)v3 + 2) = 1;
    *((_DWORD *)v3 + 3) = 1;
    *(_QWORD *)v3 = &std::_Ref_count_obj<arrow::compute::ScalarFunction>::`vftable';
    v69 = 0;
    v70 = 15;
    v68[0] = 0;
    std::string::assign(v68, "is_in", 5u);
    arrow::compute::ScalarFunction::ScalarFunction(v4 + 4, v68, &v46, 0);
  }
  else
  {
    v4 = 0;
  }
  v56 = v4 + 4;
  v57 = v4;
  arrow::boolean(v99);
  v5 = (arrow::compute::Kernel *)arrow::compute::ScalarKernel::ScalarKernel(
                                   (arrow::compute::ScalarKernel *)v111,
                                   (const struct arrow::compute::ScalarKernel *)&v124);
  arrow::compute::internal::_anonymous_namespace_::AddBasicSetLookupKernels(v5);
  v6 = v100;
  if ( v100 )
  {
    if ( _InterlockedExchangeAdd(v100 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
      if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
    }
  }
  v7 = arrow::null(v101);
  v58 = 1;
  v59 = 0;
  v59 = *(_OWORD *)v7;
  *(_QWORD *)v7 = 0;
  *(_QWORD *)(v7 + 8) = 0;
  v60 = 0;
  v8 = *(volatile signed __int32 **)(v7 + 8);
  if ( v8 )
  {
    if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
      if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
    }
  }
  v9 = arrow::boolean(v102);
  v10 = arrow::compute::OutputType::OutputType(v109, v9);
  v64 = 0;
  v65 = 0;
  std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(
    &v64,
    &v58,
    &v61,
    (unsigned __int8)v41);
  v11 = (__int64 *)arrow::compute::KernelSignature::Make(v103, &v64, v10, 0, v41);
  v12 = *v11;
  v13 = v11[1];
  *v11 = 0;
  v11[1] = 0;
  *(_QWORD *)&v124 = v12;
  v97 = v13;
  v14 = (volatile signed __int32 *)*((_QWORD *)&v124 + 1);
  *((_QWORD *)&v124 + 1) = v13;
  if ( v14 )
  {
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  v15 = v104;
  if ( v104 )
  {
    if ( _InterlockedExchangeAdd(v104 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
      if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
    }
  }
  `eh vector destructor iterator'(&v58, 0x28u, 1u, (void (*)(void *))arrow::compute::InputType::~InputType);
  LODWORD(v132) = 1;
  v16 = arrow::compute::ScalarKernel::ScalarKernel(
          (arrow::compute::ScalarKernel *)v112,
          (const struct arrow::compute::ScalarKernel *)&v124);
  arrow::compute::ScalarFunction::AddKernel(v56, v105, v16);
  if ( v106 )
    arrow::Status::State::`scalar deleting destructor'(v106, 1u);
  v50 = 0;
  if ( v4 )
    _InterlockedIncrement(v4 + 2);
  *(_QWORD *)&v50 = v56;
  *((_QWORD *)&v50 + 1) = v4;
  arrow::compute::FunctionRegistry::AddFunction(this, v80, &v50, 0);
  if ( v81 )
    arrow::Status::State::`scalar deleting destructor'(v81, 1u);
  v17 = operator new(0x50u);
  v18 = v17;
  if ( v17 )
  {
    v17[2] = 1;
    v17[3] = 1;
    *(_QWORD *)v17 = std::_Ref_count_obj<arrow::compute::internal::`anonymous namespace'::IsInMetaBinary>::`vftable';
    v72 = 0;
    v73 = 15;
    v71[0] = 0;
    std::string::assign(v71, "is_in_meta_binary", 0x11u);
    v48 = 2;
    v49 = 0;
    arrow::compute::MetaFunction::MetaFunction(v18 + 4, v71, &v48, 0);
    *((_QWORD *)v18 + 2) = &arrow::compute::internal::`anonymous namespace'::IsInMetaBinary::`vftable';
  }
  else
  {
    v18 = 0;
  }
  v52[0] = v18 + 4;
  v52[1] = v18;
  v107 = 0;
  arrow::compute::FunctionRegistry::AddFunction(this, v82, v52, 0);
  if ( v83 )
    arrow::Status::State::`scalar deleting destructor'(v83, 1u);
  if ( v4 )
  {
    if ( _InterlockedExchangeAdd(v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v4)(v4);
      if ( _InterlockedExchangeAdd(v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v4 + 8LL))(v4);
    }
  }
  if ( v130 )
  {
    v19 = v129;
    LOBYTE(v19) = v130 != v129;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v130 + 32LL))(v130, v19);
    v130 = 0;
  }
  if ( v126 )
  {
    v20 = v125;
    LOBYTE(v20) = v126 != v125;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v126 + 32LL))(v126, v20);
    v126 = 0;
  }
  v21 = (volatile signed __int32 *)*((_QWORD *)&v124 + 1);
  if ( *((_QWORD *)&v124 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v124 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v21)(v21);
      if ( _InterlockedExchangeAdd(v21 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v21 + 8LL))(v21);
    }
  }
  v115 = 0;
  v117 = 0;
  v118 = 1;
  v119 = 0;
  v121 = 0;
  v122 = 1;
  v123 = 0;
  std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>::operator=<std::unique_ptr<arrow::compute::KernelState> (&)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),void>(
    v116,
    &arrow::compute::internal::_anonymous_namespace_::InitSetLookup);
  std::function<void (arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *)>::operator=<void (&)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void>(
    v120,
    arrow::compute::internal::_anonymous_namespace_::ExecIndexIn);
  v123 = 0x100000002LL;
  v44 = 1;
  v45 = 0;
  v22 = (volatile signed __int32 *)operator new(0x68u);
  v23 = v22;
  if ( v22 )
  {
    *((_DWORD *)v22 + 2) = 1;
    *((_DWORD *)v22 + 3) = 1;
    *(_QWORD *)v22 = &std::_Ref_count_obj<arrow::compute::ScalarFunction>::`vftable';
    v75 = 0;
    v76 = 15;
    v74[0] = 0;
    std::string::assign(v74, "index_in", 8u);
    arrow::compute::ScalarFunction::ScalarFunction(v23 + 4, v74, &v44, 0);
  }
  else
  {
    v23 = 0;
  }
  v53 = v23 + 4;
  v54 = v23;
  arrow::int32(v84);
  v24 = (arrow::compute::Kernel *)arrow::compute::ScalarKernel::ScalarKernel(
                                    (arrow::compute::ScalarKernel *)v113,
                                    (const struct arrow::compute::ScalarKernel *)&v115);
  arrow::compute::internal::_anonymous_namespace_::AddBasicSetLookupKernels(v24);
  v25 = v85;
  if ( v85 )
  {
    if ( _InterlockedExchangeAdd(v85 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v25)(v25);
      if ( _InterlockedExchangeAdd(v25 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v25 + 8LL))(v25);
    }
  }
  v26 = arrow::null(v86);
  v61 = 1;
  v62 = 0;
  v62 = *(_OWORD *)v26;
  *(_QWORD *)v26 = 0;
  *(_QWORD *)(v26 + 8) = 0;
  v63 = 0;
  v27 = *(volatile signed __int32 **)(v26 + 8);
  if ( v27 )
  {
    if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
      if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
    }
  }
  v28 = arrow::int32(v87);
  v29 = arrow::compute::OutputType::OutputType(v110, v28);
  v66 = 0;
  v67 = 0;
  std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(
    &v66,
    &v61,
    &v64,
    (unsigned __int8)v42);
  v30 = (__int64 *)arrow::compute::KernelSignature::Make(v88, &v66, v29, 0, v42);
  v31 = *v30;
  v32 = v30[1];
  *v30 = 0;
  v30[1] = 0;
  *(_QWORD *)&v115 = v31;
  v98 = v32;
  v33 = (volatile signed __int32 *)*((_QWORD *)&v115 + 1);
  *((_QWORD *)&v115 + 1) = v32;
  if ( v33 )
  {
    if ( _InterlockedExchangeAdd(v33 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v33)(v33);
      if ( _InterlockedExchangeAdd(v33 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v33 + 8LL))(v33);
    }
  }
  v34 = v89;
  if ( v89 )
  {
    if ( _InterlockedExchangeAdd(v89 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v34)(v34);
      if ( _InterlockedExchangeAdd(v34 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v34 + 8LL))(v34);
    }
  }
  `eh vector destructor iterator'(&v61, 0x28u, 1u, (void (*)(void *))arrow::compute::InputType::~InputType);
  v35 = arrow::compute::ScalarKernel::ScalarKernel(
          (arrow::compute::ScalarKernel *)v114,
          (const struct arrow::compute::ScalarKernel *)&v115);
  arrow::compute::ScalarFunction::AddKernel(v53, v90, v35);
  if ( v91 )
    arrow::Status::State::`scalar deleting destructor'(v91, 1u);
  v51 = 0;
  if ( v23 )
    _InterlockedIncrement(v23 + 2);
  *(_QWORD *)&v51 = v53;
  *((_QWORD *)&v51 + 1) = v23;
  arrow::compute::FunctionRegistry::AddFunction(this, v92, &v51, 0);
  if ( v93 )
    arrow::Status::State::`scalar deleting destructor'(v93, 1u);
  v36 = operator new(0x50u);
  v37 = v36;
  if ( v36 )
  {
    v36[2] = 1;
    v36[3] = 1;
    *(_QWORD *)v36 = std::_Ref_count_obj<arrow::compute::internal::`anonymous namespace'::IndexInMetaBinary>::`vftable';
    v78 = 0;
    v79 = 15;
    v77[0] = 0;
    std::string::assign(v77, "index_in_meta_binary", 0x14u);
    LODWORD(v43) = 2;
    BYTE4(v43) = 0;
    arrow::compute::MetaFunction::MetaFunction(v37 + 4, v77, &v43, 0);
    *((_QWORD *)v37 + 2) = &arrow::compute::internal::`anonymous namespace'::IndexInMetaBinary::`vftable';
  }
  else
  {
    v37 = 0;
  }
  v55[0] = v37 + 4;
  v55[1] = v37;
  v108 = 0;
  arrow::compute::FunctionRegistry::AddFunction(this, v94, v55, 0);
  if ( v95 )
    arrow::Status::State::`scalar deleting destructor'(v95, 1u);
  if ( v23 )
  {
    if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
      if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
    }
  }
  if ( v121 )
  {
    v38 = v120;
    LOBYTE(v38) = v121 != v120;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v121 + 32LL))(v121, v38);
    v121 = 0;
  }
  if ( v117 )
  {
    v39 = v116;
    LOBYTE(v39) = v117 != v116;
    (*(void (__fastcall **)(_BYTE *, _BYTE *))(*(_QWORD *)v117 + 32LL))(v117, v39);
    v117 = 0;
  }
  v40 = (volatile signed __int32 *)*((_QWORD *)&v115 + 1);
  if ( *((_QWORD *)&v115 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v115 + 1) + 8LL), 0xFFFFFFFF) == 1 )
  {
    (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
    if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
  }
}

```

## disassembly

```asm
0x1801cb230  mov     rax, rsp
0x1801cb233  push    rbp
0x1801cb234  push    r12
0x1801cb236  push    r13
0x1801cb238  push    r14
0x1801cb23a  push    r15
0x1801cb23c  lea     rbp, [rax-6C8h]
0x1801cb243  sub     rsp, 7A0h
0x1801cb24a  mov     [rbp+6C0h+var_578], 0FFFFFFFFFFFFFFFEh
0x1801cb255  mov     [rax+10h], rbx
0x1801cb259  mov     [rax+18h], rsi
0x1801cb25d  mov     [rax+20h], rdi
0x1801cb261  mov     rax, cs:__security_cookie
0x1801cb268  xor     rax, rsp
0x1801cb26b  mov     [rbp+6C0h+var_30], rax
0x1801cb272  mov     r15, rcx
0x1801cb275  xorps   xmm0, xmm0
0x1801cb278  movdqa  [rbp+6C0h+var_E0], xmm0
0x1801cb280  xor     r12d, r12d
0x1801cb283  mov     [rbp+6C0h+var_98], r12
0x1801cb28a  mov     [rbp+6C0h+var_90], 1
0x1801cb291  mov     [rbp+6C0h+var_8C], r12d
0x1801cb298  mov     [rbp+6C0h+var_50], r12
0x1801cb29f  mov     [rbp+6C0h+var_48], 1
0x1801cb2a6  mov     [rbp+6C0h+var_40], r12
0x1801cb2ad  lea     rdx, arrow__compute__internal___anonymous_namespace___InitSetLookup
0x1801cb2b4  lea     rcx, [rbp+6C0h+var_D0]
0x1801cb2bb  call    ??$?4A6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@34@@ZX@?$function@$$A6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@std@@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@45@@Z@std@@QEAAAEAV01@A6A?AV?$unique_ptr@UKernelState@compute@arrow@@U?$default_delete@UKernelState@compute@arrow@@@std@@@1@PEAVKernelContext@compute@arrow@@AEBUKernelInitArgs@45@@Z@Z; std::function<std::unique_ptr<arrow::compute::KernelState> (arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &)>::operator=<std::unique_ptr<arrow::compute::KernelState> (&)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &),void>(std::unique_ptr<arrow::compute::KernelState> (&)(arrow::compute::KernelContext *,arrow::compute::KernelInitArgs const &))
0x1801cb2c0  lea     rdx, arrow__compute__internal___anonymous_namespace___ExecIsIn
0x1801cb2c7  lea     rcx, [rbp+6C0h+var_88]
0x1801cb2ce  call    ??$?4A6AXPEAVKernelContext@compute@arrow@@AEBUExecBatch@12@PEAUDatum@2@@ZX@?$function@$$A6AXPEAVKernelContext@compute@arrow@@AEBUExecBatch@23@PEAUDatum@3@@Z@std@@QEAAAEAV01@A6AXPEAVKernelContext@compute@arrow@@AEBUExecBatch@34@PEAUDatum@4@@Z@Z; std::function<void (arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *)>::operator=<void (&)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *),void>(void (&)(arrow::compute::KernelContext *,arrow::compute::ExecBatch const &,arrow::Datum *))
0x1801cb2d3  mov     [rsp+7C0h+var_778], 1
0x1801cb2db  mov     [rsp+7C0h+var_774], r12b
0x1801cb2e0  lea     ecx, [r12+68h]; Size
0x1801cb2e5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801cb2ea  mov     r14, rax
0x1801cb2ed  mov     qword ptr [rsp+7C0h+var_788], rax
0x1801cb2f2  lea     r13, ??_7?$_Ref_count_obj@VScalarFunction@compute@arrow@@@std@@6B@; const std::_Ref_count_obj<arrow::compute::ScalarFunction>::`vftable'
0x1801cb2f9  test    rax, rax
0x1801cb2fc  jz      short loc_1801CB34B
0x1801cb2fe  mov     dword ptr [rax+8], 1
0x1801cb305  mov     dword ptr [rax+0Ch], 1
0x1801cb30c  mov     [rax], r13
0x1801cb30f  mov     [rbp+6C0h+var_678], r12
0x1801cb313  mov     [rbp+6C0h+var_670], 0Fh
0x1801cb31b  mov     [rbp+6C0h+var_688], r12b
0x1801cb31f  lea     r8d, [r12+5]; Size
0x1801cb324  lea     rdx, aIsIn; "is_in"
0x1801cb32b  lea     rcx, [rbp+6C0h+var_688]; void *
0x1801cb32f  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1801cb334  xor     r9d, r9d
0x1801cb337  lea     r8, [rsp+7C0h+var_778]
0x1801cb33c  lea     rdx, [rbp+6C0h+var_688]
0x1801cb340  lea     rcx, [r14+10h]
0x1801cb344  call    ??0ScalarFunction@compute@arrow@@QEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUArity@12@PEBUFunctionOptions@12@@Z; arrow::compute::ScalarFunction::ScalarFunction(std::string,arrow::compute::Arity const &,arrow::compute::FunctionOptions const *)
0x1801cb349  jmp     short loc_1801CB34E
0x1801cb34b  mov     r14, r12
0x1801cb34e  lea     rdi, [r14+10h]
0x1801cb352  mov     [rbp+6C0h+var_718], rdi
0x1801cb356  mov     [rbp+6C0h+var_710], r14
0x1801cb35a  lea     rcx, [rbp+6C0h+var_560]
0x1801cb361  call    ?boolean@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::boolean(void)
0x1801cb366  mov     rbx, rax
0x1801cb369  lea     rdx, [rbp+6C0h+var_E0]; struct arrow::compute::ScalarKernel *
0x1801cb370  lea     rcx, [rbp+6C0h+var_430]; this
0x1801cb377  call    ??0ScalarKernel@compute@arrow@@QEAA@AEBU012@@Z; arrow::compute::ScalarKernel::ScalarKernel(arrow::compute::ScalarKernel const &)
0x1801cb37c  mov     r8, rdi
0x1801cb37f  mov     rdx, rbx
0x1801cb382  mov     rcx, rax; this
0x1801cb385  call    arrow__compute__internal___anonymous_namespace___AddBasicSetLookupKernels
0x1801cb38a  nop
0x1801cb38b  mov     esi, 0FFFFFFFFh
0x1801cb390  mov     rbx, [rbp+6C0h+var_558]
0x1801cb397  test    rbx, rbx
0x1801cb39a  jz      short loc_1801CB3D3
0x1801cb39c  mov     eax, esi
0x1801cb39e  lock xadd [rbx+8], eax
0x1801cb3a3  cmp     eax, 1
0x1801cb3a6  jnz     short loc_1801CB3D3
0x1801cb3a8  mov     rax, [rbx]
0x1801cb3ab  mov     rcx, rbx
0x1801cb3ae  mov     rax, [rax]
0x1801cb3b1  call    cs:__guard_dispatch_icall_fptr
0x1801cb3b7  mov     eax, esi
0x1801cb3b9  lock xadd [rbx+0Ch], eax
0x1801cb3be  cmp     eax, 1
0x1801cb3c1  jnz     short loc_1801CB3D3
0x1801cb3c3  mov     rax, [rbx]
0x1801cb3c6  mov     rcx, rbx
0x1801cb3c9  mov     rax, [rax+8]
0x1801cb3cd  call    cs:__guard_dispatch_icall_fptr
0x1801cb3d3  lea     rax, [rbp+6C0h+var_4F0]
0x1801cb3da  mov     [rsp+7C0h+var_790], rax
0x1801cb3df  lea     rcx, [rbp+6C0h+var_550]
0x1801cb3e6  call    ?null@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::null(void)
0x1801cb3eb  mov     [rbp+6C0h+var_708], 1
0x1801cb3f3  xorps   xmm0, xmm0
0x1801cb3f6  movdqu  [rbp+6C0h+var_700], xmm0
0x1801cb3fb  mov     rcx, [rax]
0x1801cb3fe  mov     qword ptr [rbp+6C0h+var_700], rcx
0x1801cb402  mov     rcx, [rax+8]
0x1801cb406  mov     qword ptr [rbp+6C0h+var_700+8], rcx
0x1801cb40a  mov     [rax], r12
0x1801cb40d  mov     [rax+8], r12
0x1801cb411  movdqu  [rbp+6C0h+var_6F0], xmm0
0x1801cb416  mov     rbx, [rax+8]
0x1801cb41a  test    rbx, rbx
0x1801cb41d  jz      short loc_1801CB457
0x1801cb41f  mov     eax, esi
0x1801cb421  lock xadd [rbx+8], eax
0x1801cb426  cmp     eax, 1
0x1801cb429  jnz     short loc_1801CB457
0x1801cb42b  mov     rax, [rbx]
0x1801cb42e  mov     rcx, rbx
0x1801cb431  mov     rax, [rax]
0x1801cb434  call    cs:__guard_dispatch_icall_fptr
0x1801cb43a  mov     eax, esi
0x1801cb43c  lock xadd [rbx+0Ch], eax
0x1801cb441  cmp     eax, 1
0x1801cb444  jnz     short loc_1801CB457
0x1801cb446  mov     rax, [rbx]
0x1801cb449  mov     rcx, rbx
0x1801cb44c  mov     rax, [rax+8]
0x1801cb450  call    cs:__guard_dispatch_icall_fptr
0x1801cb456  nop
0x1801cb457  lea     rcx, [rbp+6C0h+var_540]
0x1801cb45e  call    ?boolean@arrow@@YA?AV?$shared_ptr@VDataType@arrow@@@std@@XZ; arrow::boolean(void)
0x1801cb463  mov     rdx, rax
0x1801cb466  lea     rcx, [rbp+6C0h+var_4F0]
0x1801cb46d  call    ??0OutputType@compute@arrow@@QEAA@V?$shared_ptr@VDataType@arrow@@@std@@@Z; arrow::compute::OutputType::OutputType(std::shared_ptr<arrow::DataType>)
0x1801cb472  mov     rbx, rax
0x1801cb475  xorps   xmm0, xmm0
0x1801cb478  movdqu  [rbp+6C0h+var_6B8], xmm0
0x1801cb47d  mov     [rbp+6C0h+var_6A8], r12
0x1801cb481  movzx   r9d, byte ptr [rsp+7C0h+var_7A0]
0x1801cb487  lea     r8, [rbp+6C0h+var_6E0]
0x1801cb48b  lea     rdx, [rbp+6C0h+var_708]
0x1801cb48f  lea     rcx, [rbp+6C0h+var_6B8]
0x1801cb493  call    ??$_Range_construct_or_tidy@PEBVInputType@compute@arrow@@@?$vector@VInputType@compute@arrow@@V?$allocator@VInputType@compute@arrow@@@std@@@std@@AEAAXPEBVInputType@compute@arrow@@0Uforward_iterator_tag@1@@Z; std::vector<arrow::compute::InputType>::_Range_construct_or_tidy<arrow::compute::InputType const *>(arrow::compute::InputType const *,arrow::compute::InputType const *,std::forward_iterator_tag)
0x1801cb498  nop
0x1801cb499  xor     r9d, r9d
0x1801cb49c  mov     r8, rbx
0x1801cb49f  lea     rdx, [rbp+6C0h+var_6B8]
0x1801cb4a3  lea     rcx, [rbp+6C0h+var_530]
0x1801cb4aa  call    ?Make@KernelSignature@compute@arrow@@SA?AV?$shared_ptr@VKernelSignature@compute@arrow@@@std@@V?$vector@VInputType@compute@arrow@@V?$allocator@VInputType@compute@arrow@@@std@@@5@VOutputType@23@_N@Z; arrow::compute::KernelSignature::Make(std::vector<arrow::compute::InputType>,arrow::compute::OutputType,bool)
0x1801cb4af  mov     rcx, [rax]
0x1801cb4b2  mov     rdx, [rax+8]
0x1801cb4b6  mov     [rax], r12
0x1801cb4b9  mov     [rax+8], r12
0x1801cb4bd  mov     qword ptr [rbp+6C0h+var_E0], rcx
0x1801cb4c4  mov     [rbp+6C0h+var_570], rdx
0x1801cb4cb  mov     rbx, qword ptr [rbp+6C0h+var_E0+8]
0x1801cb4d2  mov     qword ptr [rbp+6C0h+var_E0+8], rdx
0x1801cb4d9  test    rbx, rbx
0x1801cb4dc  jz      short loc_1801CB515
0x1801cb4de  mov     eax, esi
0x1801cb4e0  lock xadd [rbx+8], eax
0x1801cb4e5  cmp     eax, 1
0x1801cb4e8  jnz     short loc_1801CB515
0x1801cb4ea  mov     rax, [rbx]
0x1801cb4ed  mov     rcx, rbx
0x1801cb4f0  mov     rax, [rax]
0x1801cb4f3  call    cs:__guard_dispatch_icall_fptr
0x1801cb4f9  mov     eax, esi
0x1801cb4fb  lock xadd [rbx+0Ch], eax
0x1801cb500  cmp     eax, 1
0x1801cb503  jnz     short loc_1801CB515
0x1801cb505  mov     rax, [rbx]
0x1801cb508  mov     rcx, rbx
0x1801cb50b  mov     rax, [rax+8]
0x1801cb50f  call    cs:__guard_dispatch_icall_fptr
0x1801cb515  mov     rbx, [rbp+6C0h+var_528]
0x1801cb51c  test    rbx, rbx
0x1801cb51f  jz      short loc_1801CB559
0x1801cb521  mov     eax, esi
0x1801cb523  lock xadd [rbx+8], eax
0x1801cb528  cmp     eax, 1
0x1801cb52b  jnz     short loc_1801CB559
0x1801cb52d  mov     rax, [rbx]
0x1801cb530  mov     rcx, rbx
0x1801cb533  mov     rax, [rax]
0x1801cb536  call    cs:__guard_dispatch_icall_fptr
0x1801cb53c  mov     eax, esi
0x1801cb53e  lock xadd [rbx+0Ch], eax
0x1801cb543  cmp     eax, 1
0x1801cb546  jnz     short loc_1801CB559
0x1801cb548  mov     rax, [rbx]
0x1801cb54b  mov     rcx, rbx
0x1801cb54e  mov     rax, [rax+8]
0x1801cb552  call    cs:__guard_dispatch_icall_fptr
0x1801cb558  nop
0x1801cb559  lea     r9, ??1InputType@compute@arrow@@QEAA@XZ; void (*)(void *)
0x1801cb560  mov     edx, 28h ; '('; unsigned __int64
0x1801cb565  lea     r8d, [rdx-27h]; unsigned __int64
0x1801cb569  lea     rcx, [rbp+6C0h+var_708]; void *
0x1801cb56d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1801cb572  mov     dword ptr [rbp+6C0h+var_40], 1
0x1801cb57c  lea     rdx, [rbp+6C0h+var_E0]; struct arrow::compute::ScalarKernel *
0x1801cb583  lea     rcx, [rbp+6C0h+var_388]; this
0x1801cb58a  call    ??0ScalarKernel@compute@arrow@@QEAA@AEBU012@@Z; arrow::compute::ScalarKernel::ScalarKernel(arrow::compute::ScalarKernel const &)
0x1801cb58f  mov     r8, rax
0x1801cb592  lea     rdx, [rbp+6C0h+var_520]
0x1801cb599  mov     rcx, [rbp+6C0h+var_718]
0x1801cb59d  call    ?AddKernel@ScalarFunction@compute@arrow@@QEAA?AVStatus@3@UScalarKernel@23@@Z; arrow::compute::ScalarFunction::AddKernel(arrow::compute::ScalarKernel)
0x1801cb5a2  mov     rcx, [rbp+6C0h+var_518]; this
0x1801cb5a9  test    rcx, rcx
0x1801cb5ac  jz      short loc_1801CB5B8
0x1801cb5ae  mov     edx, 1; unsigned int
0x1801cb5b3  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1801cb5b8  xorps   xmm0, xmm0
0x1801cb5bb  movdqu  [rsp+7C0h+var_770+8], xmm0
0x1801cb5c1  test    r14, r14
0x1801cb5c4  jz      short loc_1801CB5CB
0x1801cb5c6  lock inc dword ptr [r14+8]
0x1801cb5cb  mov     rax, [rbp+6C0h+var_718]
0x1801cb5cf  mov     qword ptr [rsp+7C0h+var_770+8], rax
0x1801cb5d4  mov     qword ptr [rsp+7C0h+var_760], r14
0x1801cb5d9  xor     r9d, r9d
0x1801cb5dc  lea     r8, [rsp+7C0h+var_770+8]
0x1801cb5e1  lea     rdx, [rbp+6C0h+var_608]
0x1801cb5e8  mov     rcx, r15
0x1801cb5eb  call    ?AddFunction@FunctionRegistry@compute@arrow@@QEAA?AVStatus@3@V?$shared_ptr@VFunction@compute@arrow@@@std@@_N@Z; arrow::compute::FunctionRegistry::AddFunction(std::shared_ptr<arrow::compute::Function>,bool)
0x1801cb5f0  mov     rcx, [rbp+6C0h+var_600]; this
0x1801cb5f7  test    rcx, rcx
0x1801cb5fa  jz      short loc_1801CB606
0x1801cb5fc  mov     edx, 1; unsigned int
0x1801cb601  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1801cb606  mov     ecx, 50h ; 'P'; Size
0x1801cb60b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1801cb610  mov     rdi, rax
0x1801cb613  mov     [rsp+7C0h+var_798], rax
0x1801cb618  test    rax, rax
0x1801cb61b  jz      short loc_1801CB68A
0x1801cb61d  mov     dword ptr [rax+8], 1
0x1801cb624  mov     dword ptr [rax+0Ch], 1
0x1801cb62b  lea     rax, ??_7?$_Ref_count_obj@VIsInMetaBinary@?A0x6854d052@internal@compute@arrow@@@std@@6B@; const std::_Ref_count_obj<arrow::compute::internal::`anonymous namespace'::IsInMetaBinary>::`vftable'
0x1801cb632  mov     [rdi], rax
0x1801cb635  mov     [rbp+6C0h+var_658], r12
0x1801cb639  mov     [rbp+6C0h+var_650], 0Fh
0x1801cb641  mov     [rbp+6C0h+var_668], 0
0x1801cb645  mov     r8d, 11h; Size
0x1801cb64b  lea     rdx, aIsInMetaBinary; "is_in_meta_binary"
0x1801cb652  lea     rcx, [rbp+6C0h+var_668]; void *
0x1801cb656  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x1801cb65b  mov     dword ptr [rsp+7C0h+var_770], 2
0x1801cb663  mov     byte ptr [rsp+7C0h+var_770+4], 0
0x1801cb668  xor     r9d, r9d
0x1801cb66b  lea     r8, [rsp+7C0h+var_770]
0x1801cb670  lea     rdx, [rbp+6C0h+var_668]
0x1801cb674  lea     rcx, [rdi+10h]
0x1801cb678  call    ??0MetaFunction@compute@arrow@@IEAA@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBUArity@12@PEBUFunctionOptions@12@@Z; arrow::compute::MetaFunction::MetaFunction(std::string,arrow::compute::Arity const &,arrow::compute::FunctionOptions const *)
0x1801cb67d  lea     rax, ??_7IsInMetaBinary@?A0x6854d052@internal@compute@arrow@@6B@; const arrow::compute::internal::`anonymous namespace'::IsInMetaBinary::`vftable'
0x1801cb684  mov     [rdi+10h], rax
0x1801cb688  jmp     short loc_1801CB68D
0x1801cb68a  mov     rdi, r12
0x1801cb68d  lea     rax, [rdi+10h]
0x1801cb691  mov     [rsp+7C0h+var_748], rax
0x1801cb696  mov     [rbp+6C0h+var_740], rdi
0x1801cb69a  xorps   xmm0, xmm0
0x1801cb69d  movdqu  [rbp+6C0h+var_510], xmm0
0x1801cb6a5  xor     r9d, r9d
0x1801cb6a8  lea     r8, [rsp+7C0h+var_748]
0x1801cb6ad  lea     rdx, [rbp+6C0h+var_5F8]
0x1801cb6b4  mov     rcx, r15
0x1801cb6b7  call    ?AddFunction@FunctionRegistry@compute@arrow@@QEAA?AVStatus@3@V?$shared_ptr@VFunction@compute@arrow@@@std@@_N@Z; arrow::compute::FunctionRegistry::AddFunction(std::shared_ptr<arrow::compute::Function>,bool)
0x1801cb6bc  mov     rcx, [rbp+6C0h+var_5F0]; this
0x1801cb6c3  test    rcx, rcx
0x1801cb6c6  jz      short loc_1801CB6D3
0x1801cb6c8  mov     edx, 1; unsigned int
0x1801cb6cd  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1801cb6d2  nop
0x1801cb6d3  test    r14, r14
0x1801cb6d6  jz      short loc_1801CB712
0x1801cb6d8  mov     eax, esi
0x1801cb6da  lock xadd [r14+8], eax
0x1801cb6e0  cmp     eax, 1
0x1801cb6e3  jnz     short loc_1801CB712
0x1801cb6e5  mov     rax, [r14]
0x1801cb6e8  mov     rcx, r14
0x1801cb6eb  mov     rax, [rax]
0x1801cb6ee  call    cs:__guard_dispatch_icall_fptr
0x1801cb6f4  mov     eax, esi
0x1801cb6f6  lock xadd [r14+0Ch], eax
0x1801cb6fc  cmp     eax, 1
0x1801cb6ff  jnz     short loc_1801CB712
0x1801cb701  mov     rax, [r14]
0x1801cb704  mov     rcx, r14
0x1801cb707  mov     rax, [rax+8]
0x1801cb70b  call    cs:__guard_dispatch_icall_fptr
0x1801cb711  nop
0x1801cb712  mov     rcx, [rbp+6C0h+var_50]
0x1801cb719  test    rcx, rcx
0x1801cb71c  jz      short loc_1801CB73F
0x1801cb71e  mov     rax, [rcx]
0x1801cb721  lea     rdx, [rbp+6C0h+var_88]
0x1801cb728  cmp     rcx, rdx
0x1801cb72b  setnz   dl
0x1801cb72e  mov     rax, [rax+20h]
0x1801cb732  call    cs:__guard_dispatch_icall_fptr
0x1801cb738  mov     [rbp+6C0h+var_50], r12
  ... truncated ...
```
