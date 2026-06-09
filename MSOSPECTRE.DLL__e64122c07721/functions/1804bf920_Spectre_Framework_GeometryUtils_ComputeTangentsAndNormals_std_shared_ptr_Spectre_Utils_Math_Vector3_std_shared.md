# Spectre::Framework::GeometryUtils::ComputeTangentsAndNormals(std::shared_ptr<Spectre::Utils::Math::Vector3>,std::shared_ptr<Spectre::Utils::Math::Vector2>,uint,std::shared_ptr<void>,uint,bool,Spectre::Framework::GeometryUtils::TriangularMeshTopology,bool,std::function<void (std::shared_ptr<Spectre::Utils::Math::Vector4> const &,std::shared_ptr<Spectre::Utils::Math::Vector3> const &,void *)>,void *,std::shared_ptr<Spectre::Utils::ICancellationToken> const &)

- ea: `0x1804bf920`
- end: `0x1804c04d6`
- name: `?ComputeTangentsAndNormals@GeometryUtils@Framework@Spectre@@SAXV?$shared_ptr@UVector3@Math@Utils@Spectre@@@std@@V?$shared_ptr@UVector2@Math@Utils@Spectre@@@5@IV?$shared_ptr@X@5@I_NW4TriangularMeshTopology@123@3V?$function@$$A6AXAEBV?$shared_ptr@UVector4@Math@Utils@Spectre@@@std@@AEBV?$shared_ptr@UVector3@Math@Utils@Spectre@@@2@PEAX@Z@5@PEAXAEBV?$shared_ptr@VICancellationToken@Utils@Spectre@@@5@@Z`
- size: `2998`
- prototype: `__int64 __fastcall(void *, void *, struct Spectre::Utils::Math::Vector4 *, void *, int, char, int, char, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180244260`

## callees

- `0x180015770`
- `0x1800423e0`
- `0x1801cc5e0`
- `0x1801cd2a0`
- `0x1801d5400`
- `0x18039e5b0`
- `0x18039e5d0`
- `0x18039ebb0`
- `0x18039f8e0`
- `0x18039f910`
- `0x18039faa0`
- `0x1804bd2a0`
- `0x1804bd4d0`
- `0x1804bdc90`
- `0x1804be010`
- `0x1804bf920`
- `0x1804c04e0`
- `0x1804c08c0`
- `0x1804c0b80`
- `0x1804c0c20`
- `0x1804f99e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804c0401`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x1804c0401`
- `api-ms-win-crt-heap-l1-1-0!_aligned_malloc` at `0x1804bfb64`
- `api-ms-win-crt-heap-l1-1-0!_aligned_malloc` at `0x1804bfc69`
- `api-ms-win-crt-heap-l1-1-0!_aligned_malloc` at `0x1804bfb64`
- `api-ms-win-crt-heap-l1-1-0!_aligned_malloc` at `0x1804bfc69`

## string_xrefs

- `0x1804bf9d6`: `ComputeTangentsAndNormals`
- `0x1804bfa00`: `ComputeTangentsAndNormals`
- `0x1804c0452`: `Index out of range while computing tangents and normals`
- `0x1804c0491`: `Index out of range while computing tangents and normals`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
void __fastcall Spectre::Framework::GeometryUtils::ComputeTangentsAndNormals(
        void *a1,
        void *a2,
        struct Spectre::Utils::Math::Vector4 *a3,
        __int64 *a4,
        unsigned int a5,
        char a6,
        unsigned int a7,
        char a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  unsigned __int64 v12; // rdi
  __int64 v15; // rsi
  __int64 v16; // rcx
  volatile signed __int32 *v17; // rdi
  volatile signed __int32 *v18; // rdi
  __int64 *v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  size_t v22; // rax
  const Spectre::Framework::GeometryProcessingException *v23; // r14
  _DWORD *v24; // rax
  size_t v25; // rax
  void *v26; // r14
  _DWORD *v27; // rax
  Spectre *v28; // r14
  unsigned int v29; // r14d
  __int64 v30; // r9
  int v31; // eax
  int v32; // ecx
  __int64 v33; // rsi
  unsigned int v34; // r13d
  __int64 v35; // r8
  unsigned int v36; // eax
  unsigned int v37; // r12d
  unsigned int v38; // r15d
  char v39; // r14
  unsigned int v40; // r14d
  __int64 v41; // r8
  int v42; // eax
  int v43; // ecx
  __int64 v44; // rsi
  unsigned int v45; // r13d
  unsigned int v46; // edx
  unsigned int v47; // r15d
  unsigned int v48; // r12d
  char v49; // r14
  const struct Spectre::Utils::Math::Vector3 *v50; // r13
  const struct Spectre::Utils::Math::Vector3 *v51; // rsi
  __int64 v52; // rcx
  volatile signed __int32 *v53; // rdi
  void *v54; // r8
  volatile signed __int32 *v55; // rdi
  volatile signed __int32 *v56; // rdi
  void *v57; // r8
  volatile signed __int32 *v58; // rdi
  volatile signed __int32 *v59; // rdi
  const char *v60; // r9
  __int64 v61; // rcx
  volatile signed __int32 *v62; // rbx
  volatile signed __int32 *v63; // rbx
  __int64 v64; // rcx
  volatile signed __int32 *v65; // rbx
  volatile signed __int32 *v66; // rbx
  struct Spectre::Utils::Math::Vector3 *v67; // [rsp+28h] [rbp-280h]
  bool v68; // [rsp+30h] [rbp-278h]
  struct Spectre::Utils::Math::Vector3 *v69; // [rsp+30h] [rbp-278h]
  struct Spectre::Utils::Math::Vector3 *v70; // [rsp+30h] [rbp-278h]
  struct Spectre::Utils::Math::Vector3 *v71; // [rsp+40h] [rbp-268h]
  struct Spectre::Utils::Math::Vector3 *v72; // [rsp+40h] [rbp-268h]
  int v73; // [rsp+48h] [rbp-260h]
  int v74; // [rsp+48h] [rbp-260h]
  struct Spectre::Utils::Math::Vector3 *v75; // [rsp+50h] [rbp-258h]
  struct Spectre::Utils::Math::Vector3 *v76; // [rsp+58h] [rbp-250h]
  Spectre *v77; // [rsp+60h] [rbp-248h]
  bool v79[16]; // [rsp+70h] [rbp-238h] BYREF
  __int64 v80; // [rsp+80h] [rbp-228h]
  __int128 v81; // [rsp+88h] [rbp-220h] BYREF
  bool v82[16]; // [rsp+98h] [rbp-210h] BYREF
  __int128 v83; // [rsp+A8h] [rbp-200h] BYREF
  __int128 v84; // [rsp+B8h] [rbp-1F0h] BYREF
  __int128 v85; // [rsp+C8h] [rbp-1E0h] BYREF
  void *v86; // [rsp+D8h] [rbp-1D0h]
  void *v87; // [rsp+E0h] [rbp-1C8h]
  void *v88; // [rsp+E8h] [rbp-1C0h]
  const Spectre::Framework::GeometryProcessingException *v89[3]; // [rsp+F0h] [rbp-1B8h] BYREF
  char v90; // [rsp+108h] [rbp-1A0h]
  void *v91; // [rsp+110h] [rbp-198h]
  _BYTE *v92; // [rsp+118h] [rbp-190h]
  char v93; // [rsp+120h] [rbp-188h]
  _BYTE v94[32]; // [rsp+128h] [rbp-180h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+148h] [rbp-160h] BYREF
  _BYTE v96[32]; // [rsp+160h] [rbp-148h] BYREF
  _BYTE v97[64]; // [rsp+180h] [rbp-128h] BYREF
  _BYTE v98[64]; // [rsp+1C0h] [rbp-E8h] BYREF
  __int64 v99; // [rsp+200h] [rbp-A8h] BYREF
  __int64 v100; // [rsp+208h] [rbp-A0h] BYREF
  __int64 v101; // [rsp+210h] [rbp-98h] BYREF
  _BYTE v102[8]; // [rsp+218h] [rbp-90h] BYREF
  char v103; // [rsp+220h] [rbp-88h] BYREF
  unsigned int v104[4]; // [rsp+228h] [rbp-80h] BYREF
  void *Block[2]; // [rsp+238h] [rbp-70h] BYREF
  __int64 v106; // [rsp+248h] [rbp-60h]
  Spectre *v107[2]; // [rsp+250h] [rbp-58h] BYREF

  v12 = (unsigned int)a3;
  *(_QWORD *)&v85 = a2;
  *(_QWORD *)&v84 = a1;
  v87 = a1;
  v86 = a2;
  v88 = a4;
  v15 = a9;
  v99 = a9;
  v80 = a9;
  v101 = a10;
  v100 = a10;
  *(_QWORD *)&v81 = a11;
  if ( (unsigned int)a3 > 0x4000000 )
  {
    Trace::LevelSettingsWrapper::Output(
      &gTraceLevelsGeometryUtils,
      3,
      "%s cannot process more than %u vertices (requested: %u)",
      "ComputeTangentsAndNormals",
      0x4000000,
      (_DWORD)a3);
LABEL_5:
    *(_OWORD *)v82 = 0;
    *(_OWORD *)v79 = 0;
    v100 = a10;
    v16 = *(_QWORD *)(a9 + 56);
    if ( v16 )
    {
      (*(void (__fastcall **)(__int64, bool *, bool *, __int64 *))(*(_QWORD *)v16 + 16LL))(v16, v79, v82, &v100);
      v17 = *(volatile signed __int32 **)&v79[8];
      if ( *(_QWORD *)&v79[8] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v79[8] + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
          if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
        }
      }
      v18 = *(volatile signed __int32 **)&v82[8];
      if ( *(_QWORD *)&v82[8] )
      {
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v82[8] + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
      std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(a1);
      std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(a2);
      v19 = a4;
LABEL_15:
      std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(v19);
      v21 = *(_QWORD *)(v15 + 56);
      if ( v21 )
      {
        LOBYTE(v20) = v21 != v15;
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v21 + 32LL))(v21, v20);
        *(_QWORD *)(v15 + 56) = 0;
      }
      return;
    }
    std::_Xbad_function_call();
LABEL_105:
    std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
    throw (std::bad_alloc *)pExceptionObject;
  }
  if ( !(_DWORD)a3 )
  {
    Trace::LevelSettingsWrapper::Output(
      &gTraceLevelsGeometryUtils,
      3,
      "%s cannot process zero vertices",
      "ComputeTangentsAndNormals");
    goto LABEL_5;
  }
  *(_OWORD *)v107 = 0;
  v22 = 16LL * (unsigned int)a3;
  if ( !is_mul_ok((unsigned int)a3, 0x10u) )
    v22 = -1;
  v23 = (const Spectre::Framework::GeometryProcessingException *)_aligned_malloc(v22, 0x10u);
  *(_OWORD *)v107 = 0;
  v103 = 0;
  v89[1] = v23;
  v89[2] = (const Spectre::Framework::GeometryProcessingException *)&v103;
  v90 = 1;
  v24 = operator new(0x18u);
  *(_QWORD *)v79 = v24;
  if ( v24 )
  {
    *(_OWORD *)v24 = 0;
    v24[2] = 1;
    v24[3] = 1;
    *(_QWORD *)v24 = &std::_Ref_count_resource<Spectre::Utils::Math::Vector4 *,_lambda_09190a7960fb7328d869125f9992b982_>::`vftable';
    *((_QWORD *)v24 + 2) = v23;
  }
  v107[0] = v23;
  v107[1] = (Spectre *)v24;
  if ( !v23 )
    goto LABEL_105;
  memset_0(v23, 0, 16 * v12);
  *(_OWORD *)Block = 0;
  v106 = 0;
  std::vector<Spectre::Utils::Math::Vector3>::vector<Spectre::Utils::Math::Vector3>(
    Block,
    (unsigned int)(2 * v12),
    v102);
  v75 = (struct Spectre::Utils::Math::Vector3 *)Block[0];
  v76 = (struct Spectre::Utils::Math::Vector3 *)((char *)Block[0] + 12 * v12);
  *(_OWORD *)v104 = 0;
  v25 = 12 * v12;
  if ( !is_mul_ok(v12, 0xCu) )
    v25 = -1;
  v26 = _aligned_malloc(v25, 0x10u);
  *(_OWORD *)v104 = 0;
  v102[0] = 0;
  v91 = v26;
  v92 = v102;
  v93 = 1;
  v27 = operator new(0x18u);
  *(_QWORD *)v79 = v27;
  if ( v27 )
  {
    *(_OWORD *)v27 = 0;
    v27[2] = 1;
    v27[3] = 1;
    *(_QWORD *)v27 = &std::_Ref_count_resource<Spectre::Utils::Math::Vector3 *,_lambda_9e2a54d4004deec9ebe94d081616ca13_>::`vftable';
    *((_QWORD *)v27 + 2) = v26;
  }
  *(_QWORD *)v104 = v26;
  *(_QWORD *)&v104[2] = v27;
  if ( !v26 )
  {
    std::bad_alloc::bad_alloc((std::bad_alloc *)v96);
    throw (std::bad_alloc *)v96;
  }
  memset_0(v26, 0, 12 * v12);
  try
  {
    v28 = *(Spectre **)v84;
    v77 = *(Spectre **)v84;
    *(_QWORD *)&v83 = *(_QWORD *)v85;
    if ( a6 )
    {
      if ( !*a4 )
      {
        sub_1804C0C20((unsigned int)v12, a7);
        v50 = v76;
        v51 = v75;
        Spectre::Framework::CalculateNonIndexedeTangentsAndNormals(v28, v81, *(__int64 *)v104, (bool)v75, v76);
        goto LABEL_138;
      }
      v40 = a5;
      sub_1804C0B80(a5, a7);
      v41 = *a4;
      *(_QWORD *)v82 = *a4;
      *(_QWORD *)v79 = *(_QWORD *)v104;
      v42 = 3;
      if ( a7 == 1 )
        v42 = 1;
      HIDWORD(v72) = v42;
      v43 = 0;
      if ( a7 == 1 )
        v43 = 2;
      v74 = v43;
      v44 = 0;
      v45 = 0;
      while ( (unsigned int)v44 < v40 - v43 )
      {
        v46 = *(_DWORD *)(v41 + 4 * v44);
        LODWORD(v72) = v46;
        v47 = *(_DWORD *)(v41 + 4LL * (unsigned int)(v44 + 1));
        v48 = *(_DWORD *)(v41 + 4LL * (unsigned int)(v44 + 2));
        if ( v46 >= (unsigned int)v12 || v47 >= (unsigned int)v12 || v48 >= (unsigned int)v12 )
        {
          std::string::string(v94, "Index out of range while computing tangents and normals");
          Spectre::Framework::GeometryProcessingException::GeometryProcessingException(v97, v94);
          throw (Spectre::Framework::GeometryProcessingException *)v97;
        }
        if ( *(_QWORD *)v81 )
        {
          if ( v45 == 100 * (v45 / 0x64) )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v81 + 40LL))(*(_QWORD *)v81);
          v46 = (unsigned int)v72;
        }
        v49 = a7 == 1 && (v44 & 1) != 0;
        Spectre::ComputeTriangleTangents(
          v77,
          (const struct Spectre::Utils::Math::Vector3 *)v83,
          (const struct Spectre::Utils::Math::Vector2 *)v46,
          v47,
          v48,
          v49,
          (bool)v75,
          v76,
          v72);
        Spectre::CalculateTriangleNormal(
          v77,
          (const struct Spectre::Utils::Math::Vector3 *)(unsigned int)v72,
          v47,
          v48,
          v49,
          v79[0],
          v70);
        v44 = (unsigned int)(HIDWORD(v72) + v44);
        ++v45;
        v41 = *(_QWORD *)v82;
        v43 = v74;
        v40 = a5;
      }
    }
    else
    {
      v29 = a5;
      sub_1804C0B80(a5, a7);
      v30 = *a4;
      *(_QWORD *)v79 = *a4;
      *(_QWORD *)v82 = *(_QWORD *)v104;
      v31 = 3;
      if ( a7 == 1 )
        v31 = 1;
      HIDWORD(v71) = v31;
      v32 = 0;
      if ( a7 == 1 )
        v32 = 2;
      v73 = v32;
      v33 = 0;
      v34 = 0;
      while ( (unsigned int)v33 < v29 - v32 )
      {
        v35 = *(unsigned __int16 *)(v30 + 2LL * (unsigned int)(v33 + 1));
        v36 = *(unsigned __int16 *)(v30 + 2 * v33);
        LODWORD(v71) = v36;
        if ( v36 >= (unsigned int)v12
          || (v37 = *(unsigned __int16 *)(v30 + 2LL * (unsigned int)(v33 + 1)), (unsigned int)v35 >= (unsigned int)v12)
          || (v38 = *(unsigned __int16 *)(v30 + 2LL * (unsigned int)(v33 + 2)), v38 >= (unsigned int)v12) )
        {
          std::string::string(v94, "Index out of range while computing tangents and normals", v35);
          Spectre::Framework::GeometryProcessingException::GeometryProcessingException(v98, v94);
          throw (Spectre::Framework::GeometryProcessingException *)v98;
        }
        if ( *(_QWORD *)v81 )
        {
          if ( v34 == 100 * (v34 / 0x64) )
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v81 + 40LL))(*(_QWORD *)v81);
          v36 = (unsigned int)v71;
        }
        v39 = a7 == 1 && (v33 & 1) != 0;
        Spectre::ComputeTriangleTangents(
          v77,
          (const struct Spectre::Utils::Math::Vector3 *)v83,
          (const struct Spectre::Utils::Math::Vector2 *)v36,
          v37,
          v38,
          v39,
          (bool)v75,
          v76,
          v71);
        Spectre::CalculateTriangleNormal(
          v77,
          (const struct Spectre::Utils::Math::Vector3 *)(unsigned int)v71,
          v37,
          v38,
          v39,
          v82[0],
          v69);
        v33 = (unsigned int)(HIDWORD(v71) + v33);
        ++v34;
        v30 = *(_QWORD *)v79;
        v32 = v73;
        v29 = a5;
      }
    }
    v50 = v76;
    v51 = v75;
  }
  catch ( Spectre::Utils::CancelledException )
  {
    throw;
  }
  catch ( const Spectre::Framework::GeometryProcessingException *v89 )
  {
    v60 = (char *)v89[0] + 24;
    if ( *((_QWORD *)v89[0] + 6) >= 0x10u )
      v60 = *(const char **)v60;
    Trace::LevelSettingsWrapper::Output(&gTraceLevelsGeometryUtils, 3, "%s", v60);
    v84 = 0;
    v85 = 0;
    v99 = v100;
    v61 = *(_QWORD *)(v80 + 56);
    if ( !v61 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(__int64, __int128 *, __int128 *, __int64 *))(*(_QWORD *)v61 + 16LL))(v61, &v85, &v84, &v99);
    v62 = (volatile signed __int32 *)*((_QWORD *)&v85 + 1);
    if ( *((_QWORD *)&v85 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v85 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v62)(v62);
        if ( _InterlockedExchangeAdd(v62 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v62 + 8LL))(v62);
      }
    }
    v63 = (volatile signed __int32 *)*((_QWORD *)&v84 + 1);
    if ( *((_QWORD *)&v84 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v84 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v63)(v63);
        if ( _InterlockedExchangeAdd(v63 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v63 + 8LL))(v63);
      }
    }
    v56 = *(volatile signed __int32 **)&v104[2];
    if ( *(_QWORD *)&v104[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v104[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v56)(v56);
        if ( _InterlockedExchangeAdd(v56 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v56 + 8LL))(v56);
      }
    }
    v57 = Block[0];
    if ( !Block[0] )
      goto LABEL_90;
    if ( (unsigned __int64)(12 * ((signed __int64)(v106 - (unsigned __int64)Block[0]) / 12)) >= 0x1000 )
    {
      v57 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v57 - 8) > 0x1F )
        goto LABEL_103;
    }
LABEL_89:
    operator delete(v57);
    *(_OWORD *)Block = 0;
    v106 = 0;
LABEL_90:
    v58 = (volatile signed __int32 *)v107[1];
    if ( v107[1] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v107[1] + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v58)(v58);
        if ( _InterlockedExchangeAdd(v58 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v58 + 8LL))(v58);
      }
    }
    std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(v87);
    std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(v86);
    std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(v88);
    std::function<void (Microsoft::glTF::Document &,Microsoft::glTF::BufferBuilder &,Spectre::Engine::NodeAnimationComponent const &,std::function<void (void)>)>::~function<void (Microsoft::glTF::Document &,Microsoft::glTF::BufferBuilder &,Spectre::Engine::NodeAnimationComponent const &,std::function<void (void)>)>(v80);
    return;
  }
  catch ( ... )
  {
    Trace::LevelSettingsWrapper::Output(&gTraceLevelsGeometryUtils, 3, "ComputeTangentsAndNormals threw exception");
    v81 = 0;
    v83 = 0;
    v99 = v100;
    v64 = *(_QWORD *)(v80 + 56);
    if ( !v64 )
    {
      std::_Xbad_function_call();
      __debugbreak();
    }
    (*(void (__fastcall **)(__int64, __int128 *, __int128 *, __int64 *))(*(_QWORD *)v64 + 16LL))(v64, &v83, &v81, &v99);
    v65 = (volatile signed __int32 *)*((_QWORD *)&v83 + 1);
    if ( *((_QWORD *)&v83 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v83 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v65)(v65);
        if ( _InterlockedExchangeAdd(v65 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v65 + 8LL))(v65);
      }
    }
    v66 = (volatile signed __int32 *)*((_QWORD *)&v81 + 1);
    if ( *((_QWORD *)&v81 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v81 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v66)(v66);
        if ( _InterlockedExchangeAdd(v66 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v66 + 8LL))(v66);
      }
    }
    v59 = *(volatile signed __int32 **)&v104[2];
    if ( *(_QWORD *)&v104[2] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v104[2] + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v59)(v59);
        if ( _InterlockedExchangeAdd(v59 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v59 + 8LL))(v59);
      }
    }
    v57 = Block[0];
    if ( !Block[0] )
      goto LABEL_90;
    if ( (unsigned __int64)(12 * ((signed __int64)(v106 - (unsigned __int64)Block[0]) / 12)) < 0x1000 )
      goto LABEL_89;
    v57 = (void *)*((_QWORD *)Block[0] - 1);
    if ( (unsigned __int64)((char *)Block[0] - (char *)v57 - 8) <= 0x1F )
      goto LABEL_89;
LABEL_103:
    _invalid_parameter_noinfo_noreturn();
  }
LABEL_138:
  LOBYTE(v67) = a8;
  Spectre::FinalizeVertexTangents(
    v107[0],
    (struct Spectre::Utils::Math::Vector4 *)(unsigned int)v12,
    v104[0],
    v51,
    v50,
    v67,
    v68);
  v15 = v99;
  v52 = *(_QWORD *)(v99 + 56);
  if ( !v52 )
  {
    std::_Xbad_function_call();
    JUMPOUT(0x1804C04D5LL);
  }
  (*(void (__fastcall **)(__int64, Spectre **, unsigned int *, __int64 *))(*(_QWORD *)v52 + 16LL))(
    v52,
    v107,
    v104,
    &v101);
  v53 = *(volatile signed __int32 **)&v104[2];
  if ( *(_QWORD *)&v104[2] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&v104[2] + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v53)(v53);
      if ( _InterlockedExchangeAdd(v53 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v53 + 8LL))(v53);
    }
  }
  v54 = Block[0];
  if ( Block[0] )
  {
    if ( (unsigned __int64)(12 * ((signed __int64)(v106 - (unsigned __int64)Block[0]) / 12)) >= 0x1000 )
    {
      v54 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v54 - 8) > 0x1F )
        goto LABEL_103;
    }
    operator delete(v54);
    *(_OWORD *)Block = 0;
    v106 = 0;
  }
  v55 = (volatile signed __int32 *)v107[1];
  if ( v107[1] )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v107[1] + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v55)(v55);
      if ( _InterlockedExchangeAdd(v55 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v55 + 8LL))(v55);
    }
  }
  std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>((void *)v84);
  std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>((void *)v85);
  v19 = a4;
  goto LABEL_15;
}

```

## disassembly

```asm
0x1804bf920  mov     r11, rsp
0x1804bf923  push    rbx
0x1804bf924  push    rsi
0x1804bf925  push    rdi
0x1804bf926  push    r12
0x1804bf928  push    r13
0x1804bf92a  push    r14
0x1804bf92c  push    r15
0x1804bf92e  sub     rsp, 270h
0x1804bf935  mov     rax, cs:__security_cookie
0x1804bf93c  xor     rax, rsp
0x1804bf93f  mov     [rsp+2A8h+var_48], rax
0x1804bf947  mov     r14, r9
0x1804bf94a  mov     [rsp+2A8h+var_240], r9
0x1804bf94f  mov     edi, r8d
0x1804bf952  mov     r13, rdx
0x1804bf955  mov     [r11-1E0h], rdx
0x1804bf95c  mov     r15, rcx
0x1804bf95f  mov     [r11-1F0h], rcx
0x1804bf966  mov     r12d, [rsp+2A8h+arg_30]
0x1804bf96e  mov     [r11-1C8h], rcx
0x1804bf975  mov     [r11-1D0h], rdx
0x1804bf97c  mov     [r11-1C0h], r9
0x1804bf983  mov     rsi, [rsp+2A8h+arg_40]
0x1804bf98b  mov     [r11-0A8h], rsi
0x1804bf992  mov     [r11-228h], rsi
0x1804bf999  mov     rbx, [rsp+2A8h+arg_48]
0x1804bf9a1  mov     [rsp+2A8h+var_98], rbx
0x1804bf9a9  mov     [rsp+2A8h+var_A0], rbx
0x1804bf9b1  mov     rax, [rsp+2A8h+arg_50]
0x1804bf9b9  mov     qword ptr [rsp+2A8h+var_220], rax
0x1804bf9c1  cmp     r8d, 4000000h
0x1804bf9c8  jbe     short loc_1804BF9F7
0x1804bf9ca  mov     dword ptr [rsp+2A8h+var_280], edi
0x1804bf9ce  mov     dword ptr [rsp+2A8h+var_288], 4000000h
0x1804bf9d6  lea     r9, aComputetangent_1; "ComputeTangentsAndNormals"
0x1804bf9dd  lea     r8, aSCannotProcess; "%s cannot process more than %u vertices"...
0x1804bf9e4  mov     edx, 3
0x1804bf9e9  lea     rcx, ?gTraceLevelsGeometryUtils@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsGeometryUtils
0x1804bf9f0  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x1804bf9f5  jmp     short loc_1804BFA1F
0x1804bf9f7  test    r8d, r8d
0x1804bf9fa  jnz     loc_1804BFB3D
0x1804bfa00  lea     r9, aComputetangent_1; "ComputeTangentsAndNormals"
0x1804bfa07  lea     r8, aSCannotProcess_0; "%s cannot process zero vertices"
0x1804bfa0e  mov     edx, 3
0x1804bfa13  lea     rcx, ?gTraceLevelsGeometryUtils@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsGeometryUtils
0x1804bfa1a  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x1804bfa1f  xorps   xmm0, xmm0
0x1804bfa22  movdqu  xmmword ptr [rsp+2A8h+var_210], xmm0
0x1804bfa2b  movdqu  xmmword ptr [rsp+2A8h+var_238], xmm0
0x1804bfa31  mov     [rsp+2A8h+var_A0], rbx
0x1804bfa39  mov     rcx, [rsi+38h]
0x1804bfa3d  test    rcx, rcx
0x1804bfa40  jz      loc_1804C0408
0x1804bfa46  mov     rax, [rcx]
0x1804bfa49  lea     r9, [rsp+2A8h+var_A0]
0x1804bfa51  lea     r8, [rsp+2A8h+var_210]
0x1804bfa59  lea     rdx, [rsp+2A8h+var_238]
0x1804bfa5e  mov     rax, [rax+10h]
0x1804bfa62  call    cs:__guard_dispatch_icall_fptr
0x1804bfa68  nop
0x1804bfa69  mov     rdi, qword ptr [rsp+2A8h+var_238+8]
0x1804bfa6e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1804bfa75  test    rdi, rdi
0x1804bfa78  jz      short loc_1804BFAB2
0x1804bfa7a  mov     eax, ebx
0x1804bfa7c  lock xadd [rdi+8], eax
0x1804bfa81  cmp     eax, 1
0x1804bfa84  jnz     short loc_1804BFAB2
0x1804bfa86  mov     rax, [rdi]
0x1804bfa89  mov     rcx, rdi
0x1804bfa8c  mov     rax, [rax]
0x1804bfa8f  call    cs:__guard_dispatch_icall_fptr
0x1804bfa95  mov     eax, ebx
0x1804bfa97  lock xadd [rdi+0Ch], eax
0x1804bfa9c  cmp     eax, 1
0x1804bfa9f  jnz     short loc_1804BFAB2
0x1804bfaa1  mov     rax, [rdi]
0x1804bfaa4  mov     rcx, rdi
0x1804bfaa7  mov     rax, [rax+8]
0x1804bfaab  call    cs:__guard_dispatch_icall_fptr
0x1804bfab1  nop
0x1804bfab2  mov     rdi, qword ptr [rsp+2A8h+var_210+8]
0x1804bfaba  test    rdi, rdi
0x1804bfabd  jz      short loc_1804BFAF5
0x1804bfabf  mov     eax, ebx
0x1804bfac1  lock xadd [rdi+8], eax
0x1804bfac6  cmp     eax, 1
0x1804bfac9  jnz     short loc_1804BFAF5
0x1804bfacb  mov     rax, [rdi]
0x1804bface  mov     rcx, rdi
0x1804bfad1  mov     rax, [rax]
0x1804bfad4  call    cs:__guard_dispatch_icall_fptr
0x1804bfada  lock xadd [rdi+0Ch], ebx
0x1804bfadf  cmp     ebx, 1
0x1804bfae2  jnz     short loc_1804BFAF5
0x1804bfae4  mov     rax, [rdi]
0x1804bfae7  mov     rcx, rdi
0x1804bfaea  mov     rax, [rax+8]
0x1804bfaee  call    cs:__guard_dispatch_icall_fptr
0x1804bfaf4  nop
0x1804bfaf5  mov     rcx, r15; void *
0x1804bfaf8  call    ??1?$shared_ptr@VDeviceVertexLayout@Engine@Spectre@@@std@@QEAA@XZ; std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(void)
0x1804bfafd  nop
0x1804bfafe  mov     rcx, r13; void *
0x1804bfb01  call    ??1?$shared_ptr@VDeviceVertexLayout@Engine@Spectre@@@std@@QEAA@XZ; std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(void)
0x1804bfb06  nop
0x1804bfb07  mov     rcx, r14; void *
0x1804bfb0a  call    ??1?$shared_ptr@VDeviceVertexLayout@Engine@Spectre@@@std@@QEAA@XZ; std::shared_ptr<Spectre::Engine::DeviceVertexLayout>::~shared_ptr<Spectre::Engine::DeviceVertexLayout>(void)
0x1804bfb0f  nop
0x1804bfb10  mov     rcx, [rsi+38h]
0x1804bfb14  test    rcx, rcx
0x1804bfb17  jz      loc_1804C032B
0x1804bfb1d  mov     rax, [rcx]
0x1804bfb20  cmp     rcx, rsi
0x1804bfb23  setnz   dl
0x1804bfb26  mov     rax, [rax+20h]
0x1804bfb2a  call    cs:__guard_dispatch_icall_fptr
0x1804bfb30  mov     qword ptr [rsi+38h], 0
0x1804bfb38  jmp     loc_1804C032B
0x1804bfb3d  xorps   xmm0, xmm0
0x1804bfb40  movups  xmmword ptr [rsp+2A8h+var_58], xmm0
0x1804bfb48  mov     r15, rdi
0x1804bfb4b  mov     eax, 10h
0x1804bfb50  mul     rdi
0x1804bfb53  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1804bfb5a  cmovo   rax, rbx
0x1804bfb5e  lea     edx, [rbx+11h]; Alignment
0x1804bfb61  mov     rcx, rax; Size
0x1804bfb64  call    cs:__imp__aligned_malloc
0x1804bfb6a  mov     r14, rax
0x1804bfb6d  xorps   xmm0, xmm0
0x1804bfb70  movdqu  xmmword ptr [rsp+2A8h+var_58], xmm0
0x1804bfb79  mov     [rsp+2A8h+var_88], 0
0x1804bfb81  mov     [rsp+2A8h+var_1B0], rax
0x1804bfb89  lea     rax, [rsp+2A8h+var_88]
0x1804bfb91  mov     [rsp+2A8h+var_1A8], rax
0x1804bfb99  mov     [rsp+2A8h+var_1A0], 1
0x1804bfba1  lea     ecx, [rbx+19h]; Size
0x1804bfba4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1804bfba9  mov     qword ptr [rsp+2A8h+var_238], rax
0x1804bfbae  lea     esi, [rbx+2]
0x1804bfbb1  test    rax, rax
0x1804bfbb4  jz      short loc_1804BFBD0
0x1804bfbb6  xorps   xmm0, xmm0
0x1804bfbb9  movups  xmmword ptr [rax], xmm0
0x1804bfbbc  mov     [rax+8], esi
0x1804bfbbf  mov     [rax+0Ch], esi
0x1804bfbc2  lea     rcx, ??_7?$_Ref_count_resource@PEAUVector4@Math@Utils@Spectre@@V_lambda_09190a7960fb7328d869125f9992b982_@@@std@@6B@; const std::_Ref_count_resource<Spectre::Utils::Math::Vector4 *,_lambda_09190a7960fb7328d869125f9992b982_>::`vftable'
0x1804bfbc9  mov     [rax], rcx
0x1804bfbcc  mov     [rax+10h], r14
0x1804bfbd0  mov     [rsp+2A8h+var_58], r14
0x1804bfbd8  mov     [rsp+2A8h+var_58+8], rax
0x1804bfbe0  test    r14, r14
0x1804bfbe3  jz      loc_1804C040E
0x1804bfbe9  mov     r8, r15
0x1804bfbec  shl     r8, 4; Size
0x1804bfbf0  xor     edx, edx; Val
0x1804bfbf2  mov     rcx, r14; void *
0x1804bfbf5  call    memset_0
0x1804bfbfa  xorps   xmm0, xmm0
0x1804bfbfd  xor     eax, eax
0x1804bfbff  movups  xmmword ptr [rsp+2A8h+Block], xmm0
0x1804bfc07  mov     [rsp+2A8h+var_60], rax
0x1804bfc0f  lea     edx, [rdi+rdi]
0x1804bfc12  lea     r8, [rsp+2A8h+var_90]
0x1804bfc1a  lea     rcx, [rsp+2A8h+Block]
0x1804bfc22  call    ??0?$vector@UVector3@Math@Utils@Spectre@@V?$allocator@UVector3@Math@Utils@Spectre@@@std@@@std@@QEAA@_KAEBV?$allocator@UVector3@Math@Utils@Spectre@@@1@@Z; std::vector<Spectre::Utils::Math::Vector3>::vector<Spectre::Utils::Math::Vector3>(unsigned __int64,std::allocator<Spectre::Utils::Math::Vector3> const &)
0x1804bfc27  nop
0x1804bfc28  mov     rcx, [rsp+2A8h+Block]
0x1804bfc30  mov     [rsp+2A8h+var_258], rcx
0x1804bfc35  lea     rax, [rdi+rdi*2]
0x1804bfc39  lea     r13, ds:0[rax*4]
0x1804bfc41  lea     rax, [rcx+r13]
0x1804bfc45  mov     [rsp+2A8h+var_250], rax
0x1804bfc4a  xorps   xmm0, xmm0
0x1804bfc4d  movups  xmmword ptr [rsp+2A8h+var_80], xmm0
0x1804bfc55  mov     eax, 0Ch
0x1804bfc5a  mul     r15
0x1804bfc5d  cmovo   rax, rbx
0x1804bfc61  mov     edx, 10h; Alignment
0x1804bfc66  mov     rcx, rax; Size
0x1804bfc69  call    cs:__imp__aligned_malloc
0x1804bfc6f  mov     r14, rax
0x1804bfc72  xorps   xmm0, xmm0
0x1804bfc75  movdqu  xmmword ptr [rsp+2A8h+var_80], xmm0
0x1804bfc7e  mov     [rsp+2A8h+var_90], 0
0x1804bfc86  mov     [rsp+2A8h+var_198], rax
0x1804bfc8e  lea     rax, [rsp+2A8h+var_90]
0x1804bfc96  mov     [rsp+2A8h+var_190], rax
0x1804bfc9e  mov     [rsp+2A8h+var_188], 1
0x1804bfca6  mov     ecx, 18h; Size
0x1804bfcab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1804bfcb0  mov     qword ptr [rsp+2A8h+var_238], rax
0x1804bfcb5  test    rax, rax
0x1804bfcb8  jz      short loc_1804BFCD4
0x1804bfcba  xorps   xmm0, xmm0
0x1804bfcbd  movups  xmmword ptr [rax], xmm0
0x1804bfcc0  mov     [rax+8], esi
0x1804bfcc3  mov     [rax+0Ch], esi
0x1804bfcc6  lea     rcx, ??_7?$_Ref_count_resource@PEAUVector3@Math@Utils@Spectre@@V_lambda_9e2a54d4004deec9ebe94d081616ca13_@@@std@@6B@; const std::_Ref_count_resource<Spectre::Utils::Math::Vector3 *,_lambda_9e2a54d4004deec9ebe94d081616ca13_>::`vftable'
0x1804bfccd  mov     [rax], rcx
0x1804bfcd0  mov     [rax+10h], r14
0x1804bfcd4  mov     qword ptr [rsp+2A8h+var_80], r14
0x1804bfcdc  mov     qword ptr [rsp+2A8h+var_80+8], rax
0x1804bfce4  test    r14, r14
0x1804bfce7  jz      loc_1804C0430
0x1804bfced  mov     r8, r13; Size
0x1804bfcf0  xor     edx, edx; Val
0x1804bfcf2  mov     rcx, r14; void *
0x1804bfcf5  call    memset_0
0x1804bfcfa  mov     r14, qword ptr [rsp+2A8h+var_1F0]
0x1804bfd02  mov     r14, [r14]
0x1804bfd05  mov     [rsp+2A8h+var_248], r14
0x1804bfd0a  mov     r15, qword ptr [rsp+2A8h+var_1E0]
0x1804bfd12  mov     r15, [r15]
0x1804bfd15  mov     qword ptr [rsp+2A8h+var_200], r15
0x1804bfd1d  mov     edx, r12d
0x1804bfd20  cmp     [rsp+2A8h+arg_28], 0
0x1804bfd28  jnz     loc_1804BFE8C
0x1804bfd2e  mov     r14d, [rsp+2A8h+arg_20]
0x1804bfd36  mov     ecx, r14d
0x1804bfd39  call    sub_1804C0B80
0x1804bfd3e  mov     r15, [rsp+2A8h+var_240]
0x1804bfd43  mov     r9, [r15]
0x1804bfd46  mov     qword ptr [rsp+2A8h+var_238], r9
0x1804bfd4b  mov     rax, qword ptr [rsp+2A8h+var_80]
0x1804bfd53  mov     qword ptr [rsp+2A8h+var_210], rax
0x1804bfd5b  mov     eax, 3
0x1804bfd60  cmp     r12d, 1
0x1804bfd64  cmovz   eax, esi
0x1804bfd67  mov     dword ptr [rsp+2A8h+var_268+4], eax
0x1804bfd6b  xor     ecx, ecx
0x1804bfd6d  mov     eax, 2
0x1804bfd72  cmp     r12d, 1
0x1804bfd76  cmovz   ecx, eax
0x1804bfd79  mov     [rsp+2A8h+var_260], ecx
0x1804bfd7d  xor     esi, esi
0x1804bfd7f  xor     r13d, r13d
0x1804bfd82  sub     r14d, ecx
0x1804bfd85  cmp     esi, r14d
0x1804bfd88  jnb     loc_1804C0039
0x1804bfd8e  movzx   edx, word ptr [r9+rsi*2]
0x1804bfd93  lea     eax, [rsi+1]
0x1804bfd96  movzx   r8d, word ptr [r9+rax*2]
0x1804bfd9b  lea     ecx, [rsi+2]
0x1804bfd9e  mov     eax, edx
0x1804bfda0  mov     dword ptr [rsp+2A8h+var_268], edx; struct Spectre::Utils::Math::Vector3 *
0x1804bfda4  cmp     edx, edi
0x1804bfda6  jnb     loc_1804C0452
0x1804bfdac  mov     r12d, r8d
0x1804bfdaf  cmp     r8d, edi
0x1804bfdb2  jnb     loc_1804C0452
0x1804bfdb8  movzx   r15d, word ptr [r9+rcx*2]
0x1804bfdbd  cmp     r15d, edi
0x1804bfdc0  jnb     loc_1804C0452
0x1804bfdc6  mov     rcx, qword ptr [rsp+2A8h+var_220]
0x1804bfdce  mov     rcx, [rcx]
0x1804bfdd1  test    rcx, rcx
0x1804bfdd4  jz      short loc_1804BFDFB
0x1804bfdd6  mov     eax, 51EB851Fh
0x1804bfddb  mul     r13d
0x1804bfdde  shr     edx, 5
0x1804bfde1  imul    r8d, edx, 64h ; 'd'
0x1804bfde5  cmp     r13d, r8d
0x1804bfde8  jnz     short loc_1804BFDF7
0x1804bfdea  mov     rax, [rcx]
0x1804bfded  mov     rax, [rax+28h]
0x1804bfdf1  call    cs:__guard_dispatch_icall_fptr
0x1804bfdf7  mov     eax, dword ptr [rsp+2A8h+var_268]
0x1804bfdfb  cmp     [rsp+2A8h+arg_30], 1
0x1804bfe03  jnz     short loc_1804BFE10
0x1804bfe05  test    sil, 1
0x1804bfe09  jz      short loc_1804BFE10
0x1804bfe0b  mov     r14b, 1
0x1804bfe0e  jmp     short loc_1804BFE13
0x1804bfe10  xor     r14b, r14b
0x1804bfe13  mov     rcx, [rsp+2A8h+var_250]
0x1804bfe18  mov     [rsp+2A8h+var_270], rcx; struct Spectre::Utils::Math::Vector3 *
0x1804bfe1d  mov     rcx, [rsp+2A8h+var_258]
0x1804bfe22  mov     [rsp+2A8h+var_278], rcx; struct Spectre::Utils::Math::Vector3 *
0x1804bfe27  mov     byte ptr [rsp+2A8h+var_280], r14b; char
0x1804bfe2c  mov     dword ptr [rsp+2A8h+var_288], r15d; unsigned int
0x1804bfe31  mov     r9d, r12d; unsigned int
0x1804bfe34  mov     r8d, eax; struct Spectre::Utils::Math::Vector2 *
0x1804bfe37  mov     rdx, qword ptr [rsp+2A8h+var_200]; struct Spectre::Utils::Math::Vector3 *
0x1804bfe3f  mov     rcx, [rsp+2A8h+var_248]; this
0x1804bfe44  call    ?ComputeTriangleTangents@Spectre@@YAXPEBUVector3@Math@Utils@1@PEBUVector2@341@III_NPEAU2341@3@Z; Spectre::ComputeTriangleTangents(Spectre::Utils::Math::Vector3 const *,Spectre::Utils::Math::Vector2 const *,uint,uint,uint,bool,Spectre::Utils::Math::Vector3 *,Spectre::Utils::Math::Vector3 *)
0x1804bfe49  mov     rax, qword ptr [rsp+2A8h+var_210]
0x1804bfe51  mov     [rsp+2A8h+var_280], rax; bool
0x1804bfe56  mov     byte ptr [rsp+2A8h+var_288], r14b; char
0x1804bfe5b  mov     r9d, r15d; unsigned int
0x1804bfe5e  mov     r8d, r12d; unsigned int
0x1804bfe61  mov     edx, dword ptr [rsp+2A8h+var_268]; struct Spectre::Utils::Math::Vector3 *
0x1804bfe65  mov     rcx, [rsp+2A8h+var_248]; this
0x1804bfe6a  call    ?CalculateTriangleNormal@Spectre@@YAXPEBUVector3@Math@Utils@1@III_NPEAU2341@@Z; Spectre::CalculateTriangleNormal(Spectre::Utils::Math::Vector3 const *,uint,uint,uint,bool,Spectre::Utils::Math::Vector3 *)
0x1804bfe6f  add     esi, dword ptr [rsp+2A8h+var_268+4]
0x1804bfe73  inc     r13d
0x1804bfe76  mov     r9, qword ptr [rsp+2A8h+var_238]
  ... truncated ...
```
