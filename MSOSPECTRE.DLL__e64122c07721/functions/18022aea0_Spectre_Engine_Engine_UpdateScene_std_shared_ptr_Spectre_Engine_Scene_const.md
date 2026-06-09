# Spectre::Engine::Engine::UpdateScene(std::shared_ptr<Spectre::Engine::Scene> const &)

- ea: `0x18022aea0`
- end: `0x18022b904`
- name: `?UpdateScene@Engine@1Spectre@@IEAAXAEBV?$shared_ptr@VScene@Engine@Spectre@@@std@@@Z`
- size: `2660`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, installer_update`

## callers

- `0x18022b910`

## callees

- `0x180016430`
- `0x18003da60`
- `0x1801d52a0`
- `0x1801d5460`
- `0x180219c90`
- `0x18021b0d0`
- `0x18021b930`
- `0x18021c640`
- `0x18021dfb0`
- `0x18021e1f0`
- `0x18021f1c0`
- `0x1802255c0`
- `0x18022aea0`
- `0x18028f4d0`
- `0x18039e5b0`
- `0x18039ebb0`
- `0x1804b0750`
- `0x1804f99e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18022b1f3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18022b3e7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18022b623`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18022b80e`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18022b1f3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18022b3e7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18022b623`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x18022b80e`

## string_xrefs

- `0x18022b090`: `PreUpdateScene`
- `0x18022b09c`: `UpdateScene`
- `0x18022b28b`: `kSpectreRenderCB_PreSceneUpdate`
- `0x18022b4c7`: `Update Scene`
- `0x18022b6b7`: `kSpectreRenderCB_PostSceneUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=39
void __fastcall Spectre::Engine::Engine::UpdateScene(__int64 a1, Spectre::Engine::Scene **a2)
{
  __int64 v4; // r14
  __int64 *v5; // rax
  __int64 v6; // rcx
  __int64 v7; // rdx
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 *v9; // rbx
  __int128 v10; // rcx
  __int64 v11; // rcx
  volatile signed __int32 *v12; // rbx
  __int64 v13; // rax
  void *v14; // rcx
  __int64 v15; // rcx
  volatile signed __int32 *v16; // rbx
  __int64 v17; // rax
  void *v18; // rcx
  __int64 v19; // rcx
  volatile signed __int32 *v20; // rbx
  __int64 v21; // rax
  void *v22; // rcx
  __int64 v23; // rcx
  volatile signed __int32 *v24; // rbx
  __int64 v25; // rax
  void *v26; // rcx
  __int128 v27; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v28; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v29; // [rsp+68h] [rbp-98h] BYREF
  __int128 v30; // [rsp+78h] [rbp-88h] BYREF
  void *Block[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v32; // [rsp+98h] [rbp-68h]
  unsigned __int64 v33; // [rsp+A0h] [rbp-60h]
  void *v34[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v35; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v36; // [rsp+C0h] [rbp-40h]
  void *v37[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v38; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v39; // [rsp+E0h] [rbp-20h]
  void *v40[2]; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v41; // [rsp+F8h] [rbp-8h]
  unsigned __int64 v42; // [rsp+100h] [rbp+0h]
  Spectre::Engine::CpuProfiler *v43[2]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v44[8]; // [rsp+118h] [rbp+18h] BYREF
  __int128 v45; // [rsp+120h] [rbp+20h] BYREF
  __int128 v46; // [rsp+130h] [rbp+30h] BYREF
  __int128 v47; // [rsp+140h] [rbp+40h] BYREF
  __int128 v48; // [rsp+150h] [rbp+50h] BYREF
  Spectre::Engine::CpuProfiler *v49; // [rsp+160h] [rbp+60h] BYREF
  int v50; // [rsp+168h] [rbp+68h]
  _BYTE v51[8]; // [rsp+170h] [rbp+70h] BYREF
  __int128 v52; // [rsp+178h] [rbp+78h]
  __int128 v53; // [rsp+188h] [rbp+88h] BYREF
  __int128 v54; // [rsp+198h] [rbp+98h] BYREF
  __int128 v55; // [rsp+1A8h] [rbp+A8h] BYREF
  __int128 v56; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v57; // [rsp+1C8h] [rbp+C8h]
  __int128 v58; // [rsp+1D0h] [rbp+D0h] BYREF
  __int64 v59; // [rsp+1E0h] [rbp+E0h]
  __int128 v60; // [rsp+1E8h] [rbp+E8h] BYREF
  __int64 v61; // [rsp+1F8h] [rbp+F8h]
  __int128 v62; // [rsp+200h] [rbp+100h] BYREF
  __int64 v63; // [rsp+210h] [rbp+110h]
  __int64 v64; // [rsp+218h] [rbp+118h]
  volatile signed __int32 *v65; // [rsp+220h] [rbp+120h]
  __int64 v66; // [rsp+228h] [rbp+128h]
  volatile signed __int32 *v67; // [rsp+230h] [rbp+130h]
  __int64 v68; // [rsp+238h] [rbp+138h]
  volatile signed __int32 *v69; // [rsp+240h] [rbp+140h]
  _BYTE v70[8]; // [rsp+248h] [rbp+148h] BYREF
  volatile signed __int32 *v71; // [rsp+250h] [rbp+150h]
  __int64 v72; // [rsp+258h] [rbp+158h]
  volatile signed __int32 *v73; // [rsp+260h] [rbp+160h]
  Spectre::Engine::Mutex *v74[2]; // [rsp+268h] [rbp+168h]
  Spectre::Engine::Mutex *v75[2]; // [rsp+278h] [rbp+178h]
  _OWORD v76[4]; // [rsp+290h] [rbp+190h] BYREF
  _OWORD v77[4]; // [rsp+2D0h] [rbp+1D0h] BYREF
  _OWORD v78[4]; // [rsp+310h] [rbp+210h] BYREF
  _OWORD v79[4]; // [rsp+350h] [rbp+250h] BYREF

  *(_OWORD *)v75 = 0;
  Spectre::Engine::Lockable::GetExclusiveLockIfNecessary((Spectre::Utils::SharedMutex *)(a1 + 8));
  *(_OWORD *)v74 = 0;
  Spectre::Engine::Lockable::GetExclusiveLockIfNecessary((Spectre::Engine::Scene *)((char *)*a2 + 16));
  v52 = 0;
  v4 = Spectre::Engine::Scene::GetCustomData<Spectre::Engine::Engine::EngineSceneData>(*a2);
  if ( !*(_QWORD *)(v4 + 8) )
  {
    v5 = (__int64 *)std::make_shared<Spectre::Utils::Tweening::TweenManager,>(v70);
    v6 = *v5;
    v7 = v5[1];
    *v5 = 0;
    v5[1] = 0;
    *(_QWORD *)(v4 + 8) = v6;
    v8 = *(volatile signed __int32 **)(v4 + 16);
    *(_QWORD *)(v4 + 16) = v7;
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    v9 = v71;
    if ( v71 )
    {
      if ( _InterlockedExchangeAdd(v71 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
  }
  *((_QWORD *)&v10 + 1) = *(_QWORD *)(v4 + 16);
  if ( *((_QWORD *)&v10 + 1) )
  {
    _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v10 + 1) + 8LL));
    *((_QWORD *)&v10 + 1) = *(_QWORD *)(v4 + 16);
  }
  *(_QWORD *)&v10 = *(_QWORD *)(v4 + 8);
  v52 = v10;
  if ( (_QWORD)v10 )
    Spectre::Utils::Tweening::TweenManager::Update((Spectre::Utils::Tweening::TweenManager *)v10);
  if ( *((_QWORD *)&v10 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v10 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (***((void (__fastcall ****)(_QWORD))&v10 + 1))(*((_QWORD *)&v10 + 1));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v10 + 1) + 12LL), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v10 + 1) + 8LL))(*((_QWORD *)&v10 + 1));
    }
  }
  memset(v76, 0, sizeof(v76));
  v45 = 0;
  v11 = *(_QWORD *)(a1 + 472);
  if ( v11 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
    v11 = *(_QWORD *)(a1 + 472);
  }
  *(_QWORD *)&v45 = *(_QWORD *)(a1 + 464);
  *((_QWORD *)&v45 + 1) = v11;
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v76,
    (unsigned int)&v45,
    (unsigned int)"..\\Source\\Engine\\Engine.cpp",
    768,
    (__int64)"UpdateScene",
    (__int64)"PreUpdateScene",
    1);
  v56 = 0;
  v57 = 0;
  Block[0] = 0;
  v32 = 0;
  v33 = 15;
  std::string::assign(Block);
  v12 = *(volatile signed __int32 **)(a1 + 1512);
  if ( v12 )
  {
    _InterlockedIncrement(v12 + 2);
    v12 = *(volatile signed __int32 **)(a1 + 1512);
  }
  v13 = *(_QWORD *)(a1 + 1504);
  v72 = v13;
  v73 = v12;
  v27 = 0;
  if ( v12 )
  {
    *(_QWORD *)&v27 = v13;
    *((_QWORD *)&v27 + 1) = v12;
    _InterlockedIncrement(v12 + 3);
  }
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(&v56, &v27, Block);
  if ( *((_QWORD *)&v27 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v27 + 1) + 12LL), 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v27 + 1) + 8LL))(*((_QWORD *)&v27 + 1));
  }
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  if ( v33 >= 0x10 )
  {
    v14 = Block[0];
    if ( v33 + 1 >= 0x1000 )
    {
      v14 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v14 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v14);
  }
  v32 = 0;
  v33 = 15;
  LOBYTE(Block[0]) = 0;
  (*(void (__fastcall **)(__int64, Spectre::Engine::Scene **))(*(_QWORD *)a1 + 104LL))(a1, a2);
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)&v56);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v76);
  memset(v77, 0, sizeof(v77));
  v46 = 0;
  v15 = *(_QWORD *)(a1 + 472);
  if ( v15 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v15 + 8));
    v15 = *(_QWORD *)(a1 + 472);
  }
  *(_QWORD *)&v46 = *(_QWORD *)(a1 + 464);
  *((_QWORD *)&v46 + 1) = v15;
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v77,
    (unsigned int)&v46,
    (unsigned int)"..\\Source\\Engine\\Engine.cpp",
    783,
    (__int64)"UpdateScene",
    (__int64)"kSpectreRenderCB_PreSceneUpdate",
    1);
  v58 = 0;
  v59 = 0;
  v34[0] = 0;
  v35 = 0;
  v36 = 15;
  std::string::assign(v34);
  v16 = *(volatile signed __int32 **)(a1 + 1512);
  if ( v16 )
  {
    _InterlockedIncrement(v16 + 2);
    v16 = *(volatile signed __int32 **)(a1 + 1512);
  }
  v17 = *(_QWORD *)(a1 + 1504);
  v64 = v17;
  v65 = v16;
  v28 = 0;
  if ( v16 )
  {
    *(_QWORD *)&v28 = v17;
    *((_QWORD *)&v28 + 1) = v16;
    _InterlockedIncrement(v16 + 3);
  }
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(&v58, &v28, v34);
  if ( *((_QWORD *)&v28 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v28 + 1) + 12LL), 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v28 + 1) + 8LL))(*((_QWORD *)&v28 + 1));
  }
  if ( v16 )
  {
    if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  if ( v36 >= 0x10 )
  {
    v18 = v34[0];
    if ( v36 + 1 >= 0x1000 )
    {
      v18 = (void *)*((_QWORD *)v34[0] - 1);
      if ( (unsigned __int64)((char *)v34[0] - (char *)v18 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v18);
  }
  v35 = 0;
  v36 = 15;
  LOBYTE(v34[0]) = 0;
  v49 = *(Spectre::Engine::CpuProfiler **)(a1 + 1504);
  v50 = 1;
  std::chrono::steady_clock::now(v51);
  Spectre::Engine::CpuProfiler::RegisterCallbackTime(
    v49,
    (const struct Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer *)&v49);
  v53 = 0;
  v54 = 0;
  Spectre::Engine::Engine::InvokeCallback(a1, 1, &v54, &v53);
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)&v58);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v77);
  memset(v78, 0, sizeof(v78));
  v47 = 0;
  v19 = *(_QWORD *)(a1 + 472);
  if ( v19 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v19 + 8));
    v19 = *(_QWORD *)(a1 + 472);
  }
  *(_QWORD *)&v47 = *(_QWORD *)(a1 + 464);
  *((_QWORD *)&v47 + 1) = v19;
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v78,
    (unsigned int)&v47,
    (unsigned int)"..\\Source\\Engine\\Engine.cpp",
    789,
    (__int64)"UpdateScene",
    (__int64)"Update Scene",
    1);
  v60 = 0;
  v61 = 0;
  v37[0] = 0;
  v38 = 0;
  v39 = 15;
  std::string::assign(v37);
  v20 = *(volatile signed __int32 **)(a1 + 1512);
  if ( v20 )
  {
    _InterlockedIncrement(v20 + 2);
    v20 = *(volatile signed __int32 **)(a1 + 1512);
  }
  v21 = *(_QWORD *)(a1 + 1504);
  v66 = v21;
  v67 = v20;
  v29 = 0;
  if ( v20 )
  {
    *(_QWORD *)&v29 = v21;
    *((_QWORD *)&v29 + 1) = v20;
    _InterlockedIncrement(v20 + 3);
  }
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(&v60, &v29, v37);
  if ( *((_QWORD *)&v29 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v29 + 1) + 12LL), 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v29 + 1) + 8LL))(*((_QWORD *)&v29 + 1));
  }
  if ( v20 )
  {
    if ( _InterlockedExchangeAdd(v20 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
      if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
    }
  }
  if ( v39 >= 0x10 )
  {
    v22 = v37[0];
    if ( v39 + 1 >= 0x1000 )
    {
      v22 = (void *)*((_QWORD *)v37[0] - 1);
      if ( (unsigned __int64)((char *)v37[0] - (char *)v22 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v22);
  }
  v38 = 0;
  v39 = 15;
  LOBYTE(v37[0]) = 0;
  Spectre::Engine::Scene::Update(*a2, (const struct Spectre::Engine::FrameData *)(a1 + 368));
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)&v60);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v78);
  memset(v79, 0, sizeof(v79));
  v48 = 0;
  v23 = *(_QWORD *)(a1 + 472);
  if ( v23 )
  {
    _InterlockedIncrement((volatile signed __int32 *)(v23 + 8));
    v23 = *(_QWORD *)(a1 + 472);
  }
  *(_QWORD *)&v48 = *(_QWORD *)(a1 + 464);
  *((_QWORD *)&v48 + 1) = v23;
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v79,
    (unsigned int)&v48,
    (unsigned int)"..\\Source\\Engine\\Engine.cpp",
    795,
    (__int64)"UpdateScene",
    (__int64)"kSpectreRenderCB_PostSceneUpdate",
    1);
  v62 = 0;
  v63 = 0;
  v40[0] = 0;
  v41 = 0;
  v42 = 15;
  std::string::assign(v40);
  v24 = *(volatile signed __int32 **)(a1 + 1512);
  if ( v24 )
  {
    _InterlockedIncrement(v24 + 2);
    v24 = *(volatile signed __int32 **)(a1 + 1512);
  }
  v25 = *(_QWORD *)(a1 + 1504);
  v68 = v25;
  v69 = v24;
  v30 = 0;
  if ( v24 )
  {
    *(_QWORD *)&v30 = v25;
    *((_QWORD *)&v30 + 1) = v24;
    _InterlockedIncrement(v24 + 3);
  }
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(&v62, &v30, v40);
  if ( *((_QWORD *)&v30 + 1)
    && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v30 + 1) + 12LL), 0xFFFFFFFF) == 1 )
  {
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v30 + 1) + 8LL))(*((_QWORD *)&v30 + 1));
  }
  if ( v24 )
  {
    if ( _InterlockedExchangeAdd(v24 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v24)(v24);
      if ( _InterlockedExchangeAdd(v24 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v24 + 8LL))(v24);
    }
  }
  if ( v42 >= 0x10 )
  {
    v26 = v40[0];
    if ( v42 + 1 >= 0x1000 )
    {
      v26 = (void *)*((_QWORD *)v40[0] - 1);
      if ( (unsigned __int64)((char *)v40[0] - (char *)v26 - 8) > 0x1F )
        _invalid_parameter_noinfo_noreturn();
    }
    operator delete(v26);
  }
  v41 = 0;
  v42 = 15;
  LOBYTE(v40[0]) = 0;
  v43[0] = *(Spectre::Engine::CpuProfiler **)(a1 + 1504);
  LODWORD(v43[1]) = 2;
  std::chrono::steady_clock::now(v44);
  Spectre::Engine::CpuProfiler::RegisterCallbackTime(
    v43[0],
    (const struct Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer *)v43);
  v55 = 0;
  *(_OWORD *)v43 = 0;
  Spectre::Engine::Engine::InvokeCallback(a1, 2, v43, &v55);
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)&v62);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v79);
  (*(void (__fastcall **)(__int64, Spectre::Engine::Scene **))(*(_QWORD *)a1 + 112LL))(a1, a2);
  if ( LOBYTE(v74[1]) )
    Spectre::Engine::Mutex::unlock(v74[0]);
  if ( LOBYTE(v75[1]) )
    Spectre::Engine::Mutex::unlock(v75[0]);
}

```

## disassembly

```asm
0x18022aea0  mov     [rsp-8+arg_10], rbx
0x18022aea5  mov     [rsp-8+arg_18], rsi
0x18022aeaa  push    rbp
0x18022aeab  push    rdi
0x18022aeac  push    r12
0x18022aeae  push    r14
0x18022aeb0  push    r15
0x18022aeb2  lea     rbp, [rsp-2A0h]
0x18022aeba  sub     rsp, 3A0h
0x18022aec1  mov     rax, cs:__security_cookie
0x18022aec8  xor     rax, rsp
0x18022aecb  mov     [rbp+2C0h+var_30], rax
0x18022aed2  mov     r15, rdx
0x18022aed5  mov     rdi, rcx
0x18022aed8  xorps   xmm0, xmm0
0x18022aedb  movups  xmmword ptr [rbp+2C0h+var_148], xmm0
0x18022aee2  add     rcx, 8; this
0x18022aee6  lea     rdx, [rbp+2C0h+var_148]
0x18022aeed  call    ?GetExclusiveLockIfNecessary@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLockIfNecessary(void)
0x18022aef2  nop
0x18022aef3  xorps   xmm0, xmm0
0x18022aef6  movups  xmmword ptr [rbp+2C0h+var_158], xmm0
0x18022aefd  mov     rcx, [r15]
0x18022af00  add     rcx, 10h; this
0x18022af04  lea     rdx, [rbp+2C0h+var_158]
0x18022af0b  call    ?GetExclusiveLockIfNecessary@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLockIfNecessary(void)
0x18022af10  nop
0x18022af11  xorps   xmm0, xmm0
0x18022af14  movups  [rbp+2C0h+var_248], xmm0
0x18022af18  mov     rcx, [r15]
0x18022af1b  call    ??$GetCustomData@UEngineSceneData@Engine@2Spectre@@@Scene@Engine@Spectre@@QEAAAEAUEngineSceneData@112@XZ; Spectre::Engine::Scene::GetCustomData<Spectre::Engine::Engine::EngineSceneData>(void)
0x18022af20  mov     r14, rax
0x18022af23  xor     r12d, r12d
0x18022af26  lea     esi, [r12-1]
0x18022af2b  cmp     [rax+8], r12
0x18022af2f  jnz     loc_18022AFDA
0x18022af35  lea     rcx, [rbp+2C0h+var_178]
0x18022af3c  call    ??$make_shared@VTweenManager@Tweening@Utils@Spectre@@$$V@std@@YA?AV?$shared_ptr@VTweenManager@Tweening@Utils@Spectre@@@0@XZ; std::make_shared<Spectre::Utils::Tweening::TweenManager,>(void)
0x18022af41  mov     rcx, [rax]
0x18022af44  mov     rdx, [rax+8]
0x18022af48  mov     [rax], r12
0x18022af4b  mov     [rax+8], r12
0x18022af4f  mov     [r14+8], rcx
0x18022af53  mov     rbx, [r14+10h]
0x18022af57  mov     [r14+10h], rdx
0x18022af5b  test    rbx, rbx
0x18022af5e  jz      short loc_18022AF97
0x18022af60  mov     eax, esi
0x18022af62  lock xadd [rbx+8], eax
0x18022af67  cmp     eax, 1
0x18022af6a  jnz     short loc_18022AF97
0x18022af6c  mov     rax, [rbx]
0x18022af6f  mov     rcx, rbx
0x18022af72  mov     rax, [rax]
0x18022af75  call    cs:__guard_dispatch_icall_fptr
0x18022af7b  mov     eax, esi
0x18022af7d  lock xadd [rbx+0Ch], eax
0x18022af82  cmp     eax, 1
0x18022af85  jnz     short loc_18022AF97
0x18022af87  mov     rax, [rbx]
0x18022af8a  mov     rcx, rbx
0x18022af8d  mov     rax, [rax+8]
0x18022af91  call    cs:__guard_dispatch_icall_fptr
0x18022af97  mov     rbx, [rbp+2C0h+var_170]
0x18022af9e  test    rbx, rbx
0x18022afa1  jz      short loc_18022AFDA
0x18022afa3  mov     eax, esi
0x18022afa5  lock xadd [rbx+8], eax
0x18022afaa  cmp     eax, 1
0x18022afad  jnz     short loc_18022AFDA
0x18022afaf  mov     rax, [rbx]
0x18022afb2  mov     rcx, rbx
0x18022afb5  mov     rax, [rax]
0x18022afb8  call    cs:__guard_dispatch_icall_fptr
0x18022afbe  mov     eax, esi
0x18022afc0  lock xadd [rbx+0Ch], eax
0x18022afc5  cmp     eax, 1
0x18022afc8  jnz     short loc_18022AFDA
0x18022afca  mov     rax, [rbx]
0x18022afcd  mov     rcx, rbx
0x18022afd0  mov     rax, [rax+8]
0x18022afd4  call    cs:__guard_dispatch_icall_fptr
0x18022afda  mov     rbx, [r14+10h]
0x18022afde  test    rbx, rbx
0x18022afe1  jz      short loc_18022AFEB
0x18022afe3  lock inc dword ptr [rbx+8]
0x18022afe7  mov     rbx, [r14+10h]
0x18022afeb  mov     rcx, [r14+8]; this
0x18022afef  mov     qword ptr [rbp+2C0h+var_248], rcx
0x18022aff3  mov     qword ptr [rbp+2C0h+var_248+8], rbx
0x18022affa  test    rcx, rcx
0x18022affd  jz      short loc_18022B005
0x18022afff  call    ?Update@TweenManager@Tweening@Utils@Spectre@@QEAAXXZ; Spectre::Utils::Tweening::TweenManager::Update(void)
0x18022b004  nop
0x18022b005  test    rbx, rbx
0x18022b008  jz      short loc_18022B041
0x18022b00a  mov     eax, esi
0x18022b00c  lock xadd [rbx+8], eax
0x18022b011  cmp     eax, 1
0x18022b014  jnz     short loc_18022B041
0x18022b016  mov     rax, [rbx]
0x18022b019  mov     rcx, rbx
0x18022b01c  mov     rax, [rax]
0x18022b01f  call    cs:__guard_dispatch_icall_fptr
0x18022b025  mov     eax, esi
0x18022b027  lock xadd [rbx+0Ch], eax
0x18022b02c  cmp     eax, 1
0x18022b02f  jnz     short loc_18022B041
0x18022b031  mov     rax, [rbx]
0x18022b034  mov     rcx, rbx
0x18022b037  mov     rax, [rax+8]
0x18022b03b  call    cs:__guard_dispatch_icall_fptr
0x18022b041  xorps   xmm0, xmm0
0x18022b044  movups  [rbp+2C0h+var_130], xmm0
0x18022b04b  movups  [rbp+2C0h+var_120], xmm0
0x18022b052  movups  [rbp+2C0h+var_110], xmm0
0x18022b059  movups  [rbp+2C0h+var_100], xmm0
0x18022b060  movdqu  [rbp+2C0h+var_2A0], xmm0
0x18022b065  mov     rcx, [rdi+1D8h]
0x18022b06c  test    rcx, rcx
0x18022b06f  jz      short loc_18022B07C
0x18022b071  lock inc dword ptr [rcx+8]
0x18022b075  mov     rcx, [rdi+1D8h]
0x18022b07c  mov     rax, [rdi+1D0h]
0x18022b083  mov     qword ptr [rbp+2C0h+var_2A0], rax
0x18022b087  mov     qword ptr [rbp+2C0h+var_2A0+8], rcx
0x18022b08b  mov     [rsp+3C0h+var_390], 1
0x18022b090  lea     rbx, aPreupdatescene; "PreUpdateScene"
0x18022b097  mov     [rsp+3C0h+var_398], rbx
0x18022b09c  lea     r14, aUpdatescene; "UpdateScene"
0x18022b0a3  mov     [rsp+3C0h+var_3A0], r14
0x18022b0a8  mov     r9d, 300h
0x18022b0ae  lea     r8, aSourceEngineEn; "..\\Source\\Engine\\Engine.cpp"
0x18022b0b5  lea     rdx, [rbp+2C0h+var_2A0]
0x18022b0b9  lea     rcx, [rbp+2C0h+var_130]
0x18022b0c0  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x18022b0c5  nop
0x18022b0c6  xorps   xmm0, xmm0
0x18022b0c9  xor     eax, eax
0x18022b0cb  movups  [rbp+2C0h+var_208], xmm0
0x18022b0d2  mov     [rbp+2C0h+var_1F8], rax
0x18022b0d9  mov     [rbp+2C0h+Block], r12
0x18022b0dd  mov     [rbp+2C0h+var_328], r12
0x18022b0e1  mov     [rbp+2C0h+var_320], 0Fh
0x18022b0e9  mov     byte ptr [rbp+2C0h+Block], al
0x18022b0ec  lea     r8d, [rax+0Eh]
0x18022b0f0  mov     rdx, rbx
0x18022b0f3  lea     rcx, [rbp+2C0h+Block]; void *
0x18022b0f7  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x18022b0fc  nop
0x18022b0fd  mov     rbx, [rdi+5E8h]
0x18022b104  test    rbx, rbx
0x18022b107  jz      short loc_18022B114
0x18022b109  lock inc dword ptr [rbx+8]
0x18022b10d  mov     rbx, [rdi+5E8h]
0x18022b114  mov     rax, [rdi+5E0h]
0x18022b11b  mov     [rbp+2C0h+var_168], rax
0x18022b122  mov     [rbp+2C0h+var_160], rbx
0x18022b129  xorps   xmm0, xmm0
0x18022b12c  movdqu  [rsp+3C0h+var_378], xmm0
0x18022b132  test    rbx, rbx
0x18022b135  jz      short loc_18022B145
0x18022b137  mov     qword ptr [rsp+3C0h+var_378], rax
0x18022b13c  mov     qword ptr [rsp+3C0h+var_378+8], rbx
0x18022b141  lock inc dword ptr [rbx+0Ch]
0x18022b145  lea     r8, [rbp+2C0h+Block]
0x18022b149  lea     rdx, [rsp+3C0h+var_378]
0x18022b14e  lea     rcx, [rbp+2C0h+var_208]
0x18022b155  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x18022b15a  nop
0x18022b15b  mov     rcx, qword ptr [rsp+3C0h+var_378+8]
0x18022b160  test    rcx, rcx
0x18022b163  jz      short loc_18022B184
0x18022b165  mov     eax, esi
0x18022b167  lock xadd [rcx+0Ch], eax
0x18022b16c  cmp     eax, 1
0x18022b16f  jnz     short loc_18022B184
0x18022b171  mov     rcx, qword ptr [rsp+3C0h+var_378+8]
0x18022b176  mov     rax, [rcx]
0x18022b179  mov     rax, [rax+8]
0x18022b17d  call    cs:__guard_dispatch_icall_fptr
0x18022b183  nop
0x18022b184  test    rbx, rbx
0x18022b187  jz      short loc_18022B1C1
0x18022b189  mov     eax, esi
0x18022b18b  lock xadd [rbx+8], eax
0x18022b190  cmp     eax, 1
0x18022b193  jnz     short loc_18022B1C1
0x18022b195  mov     rax, [rbx]
0x18022b198  mov     rcx, rbx
0x18022b19b  mov     rax, [rax]
0x18022b19e  call    cs:__guard_dispatch_icall_fptr
0x18022b1a4  mov     eax, esi
0x18022b1a6  lock xadd [rbx+0Ch], eax
0x18022b1ab  cmp     eax, 1
0x18022b1ae  jnz     short loc_18022B1C1
0x18022b1b0  mov     rax, [rbx]
0x18022b1b3  mov     rcx, rbx
0x18022b1b6  mov     rax, [rax+8]
0x18022b1ba  call    cs:__guard_dispatch_icall_fptr
0x18022b1c0  nop
0x18022b1c1  mov     rdx, [rbp+2C0h+var_320]
0x18022b1c5  cmp     rdx, 10h
0x18022b1c9  jb      short loc_18022B1FF
0x18022b1cb  inc     rdx
0x18022b1ce  mov     rcx, [rbp+2C0h+Block]; Block
0x18022b1d2  mov     rax, rcx
0x18022b1d5  cmp     rdx, 1000h
0x18022b1dc  jb      short loc_18022B1FA
0x18022b1de  add     rdx, 27h ; '''
0x18022b1e2  mov     rcx, [rcx-8]
0x18022b1e6  sub     rax, rcx
0x18022b1e9  add     rax, 0FFFFFFFFFFFFFFF8h
0x18022b1ed  cmp     rax, 1Fh
0x18022b1f1  jbe     short loc_18022B1FA
0x18022b1f3  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x18022b1fa  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18022b1ff  mov     [rbp+2C0h+var_328], r12
0x18022b203  mov     [rbp+2C0h+var_320], 0Fh
0x18022b20b  mov     byte ptr [rbp+2C0h+Block], 0
0x18022b20f  mov     rax, [rdi]
0x18022b212  mov     rdx, r15
0x18022b215  mov     rcx, rdi
0x18022b218  mov     rax, [rax+68h]
0x18022b21c  call    cs:__guard_dispatch_icall_fptr
0x18022b222  nop
0x18022b223  lea     rcx, [rbp+2C0h+var_208]; this
0x18022b22a  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x18022b22f  nop
0x18022b230  lea     rcx, [rbp+2C0h+var_130]; this
0x18022b237  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x18022b23c  xorps   xmm0, xmm0
0x18022b23f  movups  [rbp+2C0h+var_F0], xmm0
0x18022b246  movups  [rbp+2C0h+var_E0], xmm0
0x18022b24d  movups  [rbp+2C0h+var_D0], xmm0
0x18022b254  movups  [rbp+2C0h+var_C0], xmm0
0x18022b25b  movdqu  [rbp+2C0h+var_290], xmm0
0x18022b260  mov     rcx, [rdi+1D8h]
0x18022b267  test    rcx, rcx
0x18022b26a  jz      short loc_18022B277
0x18022b26c  lock inc dword ptr [rcx+8]
0x18022b270  mov     rcx, [rdi+1D8h]
0x18022b277  mov     rax, [rdi+1D0h]
0x18022b27e  mov     qword ptr [rbp+2C0h+var_290], rax
0x18022b282  mov     qword ptr [rbp+2C0h+var_290+8], rcx
0x18022b286  mov     [rsp+3C0h+var_390], 1
0x18022b28b  lea     rbx, aKspectrerender_6; "kSpectreRenderCB_PreSceneUpdate"
0x18022b292  mov     [rsp+3C0h+var_398], rbx
0x18022b297  mov     [rsp+3C0h+var_3A0], r14
0x18022b29c  mov     r9d, 30Fh
0x18022b2a2  lea     r8, aSourceEngineEn; "..\\Source\\Engine\\Engine.cpp"
0x18022b2a9  lea     rdx, [rbp+2C0h+var_290]
0x18022b2ad  lea     rcx, [rbp+2C0h+var_F0]
0x18022b2b4  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x18022b2b9  nop
0x18022b2ba  xorps   xmm0, xmm0
0x18022b2bd  xor     eax, eax
0x18022b2bf  movups  [rbp+2C0h+var_1F0], xmm0
0x18022b2c6  mov     [rbp+2C0h+var_1E0], rax
0x18022b2cd  mov     [rbp+2C0h+var_318], r12
0x18022b2d1  mov     [rbp+2C0h+var_308], r12
0x18022b2d5  mov     [rbp+2C0h+var_300], 0Fh
0x18022b2dd  mov     byte ptr [rbp+2C0h+var_318], al
0x18022b2e0  lea     r8d, [rax+1Fh]
0x18022b2e4  mov     rdx, rbx
0x18022b2e7  lea     rcx, [rbp+2C0h+var_318]; void *
0x18022b2eb  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@QEBD_K@Z; std::string::assign(char const * const,unsigned __int64)
0x18022b2f0  nop
0x18022b2f1  mov     rbx, [rdi+5E8h]
0x18022b2f8  test    rbx, rbx
0x18022b2fb  jz      short loc_18022B308
0x18022b2fd  lock inc dword ptr [rbx+8]
0x18022b301  mov     rbx, [rdi+5E8h]
0x18022b308  mov     rax, [rdi+5E0h]
0x18022b30f  mov     [rbp+2C0h+var_1A8], rax
0x18022b316  mov     [rbp+2C0h+var_1A0], rbx
0x18022b31d  xorps   xmm0, xmm0
0x18022b320  movdqu  [rsp+3C0h+var_368], xmm0
0x18022b326  test    rbx, rbx
0x18022b329  jz      short loc_18022B339
0x18022b32b  mov     qword ptr [rsp+3C0h+var_368], rax
0x18022b330  mov     qword ptr [rsp+3C0h+var_368+8], rbx
0x18022b335  lock inc dword ptr [rbx+0Ch]
0x18022b339  lea     r8, [rbp+2C0h+var_318]
0x18022b33d  lea     rdx, [rsp+3C0h+var_368]
0x18022b342  lea     rcx, [rbp+2C0h+var_1F0]
0x18022b349  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x18022b34e  nop
0x18022b34f  mov     rcx, qword ptr [rsp+3C0h+var_368+8]
0x18022b354  test    rcx, rcx
0x18022b357  jz      short loc_18022B378
0x18022b359  mov     eax, esi
0x18022b35b  lock xadd [rcx+0Ch], eax
0x18022b360  cmp     eax, 1
0x18022b363  jnz     short loc_18022B378
0x18022b365  mov     rcx, qword ptr [rsp+3C0h+var_368+8]
0x18022b36a  mov     rax, [rcx]
0x18022b36d  mov     rax, [rax+8]
0x18022b371  call    cs:__guard_dispatch_icall_fptr
0x18022b377  nop
  ... truncated ...
```
