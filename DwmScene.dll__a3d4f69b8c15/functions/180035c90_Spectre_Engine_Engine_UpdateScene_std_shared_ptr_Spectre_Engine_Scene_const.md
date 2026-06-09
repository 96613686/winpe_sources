# Spectre::Engine::Engine::UpdateScene(std::shared_ptr<Spectre::Engine::Scene> const &)

- ea: `0x180035c90`
- end: `0x1800360ec`
- name: `?UpdateScene@Engine@1Spectre@@IEAAXAEBV?$shared_ptr@VScene@Engine@Spectre@@@std@@@Z`
- size: `1116`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180036100`

## callees

- `0x18000ca90`
- `0x18001128c`
- `0x1800112c4`
- `0x180011f64`
- `0x1800120ec`
- `0x180012ba8`
- `0x180012cd0`
- `0x180012df8`
- `0x180016324`
- `0x18001fba8`
- `0x18001fca8`
- `0x180028f78`
- `0x18002fadc`
- `0x180030700`
- `0x180032b58`
- `0x1800332a0`
- `0x180033794`
- `0x180035c90`
- `0x18003fbe4`
- `0x1800945d8`
- `0x1800ce920`
- `0x1800e7010`

## string_xrefs

- `0x180035d3a`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`
- `0x180035dff`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`
- `0x180035f05`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`
- `0x180035fc5`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`
- `0x180035de8`: `kSpectreRenderCB_PreSceneUpdate`
- `0x180035eee`: `Update Scene`
- `0x180035d1c`: `PreUpdateScene`
- `0x180035d28`: `UpdateScene`
- `0x180035fae`: `kSpectreRenderCB_PostSceneUpdate`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall Spectre::Engine::Engine::UpdateScene(Spectre::Engine::CpuProfiler **a1, Spectre::Engine::Scene **a2)
{
  __int64 v4; // rcx
  int v5; // eax
  __int64 CpuProfiler; // rax
  int v7; // eax
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rax
  int v11; // eax
  __int64 v12; // rax
  std::_Ref_count_base *v14[2]; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v15[2]; // [rsp+50h] [rbp-B0h] BYREF
  Spectre::Engine::CpuProfiler *v16; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v17; // [rsp+68h] [rbp-98h]
  _BYTE v18[8]; // [rsp+70h] [rbp-90h] BYREF
  Spectre::Engine::CpuProfiler *v19; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v20; // [rsp+80h] [rbp-80h]
  _BYTE v21[8]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v22[16]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v23[16]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v24[64]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v25[32]; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v26[64]; // [rsp+110h] [rbp+10h] BYREF

  Spectre::Engine::Lockable::GetExclusiveLockIfNecessary((Spectre::Engine::Mutex *)(a1 + 1));
  Spectre::Engine::Lockable::GetExclusiveLockIfNecessary((Spectre::Engine::Scene *)((char *)*a2 + 16));
  Spectre::Engine::Engine::GetTweenManager(v4, v14, a2);
  if ( v14[0] )
    Spectre::Utils::Tweening::TweenManager::Update(v14[0]);
  if ( v14[1] )
    std::_Ref_count_base::_Decref(v14[1]);
  v5 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
         v15,
         a1 + 58);
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v26,
    v5,
    (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
    750,
    (__int64)"UpdateScene",
    (__int64)"PreUpdateScene");
  std::string::string(v25, "PreUpdateScene");
  CpuProfiler = Spectre::Engine::Engine::GetCpuProfiler(a1, &v16);
  std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v14, CpuProfiler);
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(&v19, v14, v25);
  if ( v14[1] )
    std::_Ref_count_base::_Decwref(v14[1]);
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  std::string::_Tidy_deallocate(v25);
  (*((void (__fastcall **)(Spectre::Engine::CpuProfiler **, Spectre::Engine::Scene **))*a1 + 12))(a1, a2);
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)&v19);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v26);
  v7 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
         &v16,
         a1 + 58);
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v24,
    v7,
    (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
    765,
    (__int64)"UpdateScene",
    (__int64)"kSpectreRenderCB_PreSceneUpdate");
  std::string::string(v26, "kSpectreRenderCB_PreSceneUpdate");
  v8 = Spectre::Engine::Engine::GetCpuProfiler(a1, &v19);
  std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v14, v8);
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(v25, v14, v26);
  if ( v14[1] )
    std::_Ref_count_base::_Decwref(v14[1]);
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  std::string::_Tidy_deallocate(v26);
  v16 = a1[121];
  LODWORD(v17) = 1;
  std::chrono::steady_clock::now(v18);
  Spectre::Engine::CpuProfiler::RegisterCallbackTime(
    v16,
    (const struct Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer *)&v16);
  *(_OWORD *)v15 = 0;
  *(_OWORD *)v14 = 0;
  Spectre::Engine::Engine::InvokeCallback(a1, 1, v14, v15);
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v25);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v24);
  v9 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
         &v19,
         a1 + 58);
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v24,
    v9,
    (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
    771,
    (__int64)"UpdateScene",
    (__int64)"Update Scene");
  std::string::string(v26, "Update Scene");
  v10 = Spectre::Engine::Engine::GetCpuProfiler(a1, &v16);
  std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v15, v10);
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(v25, v15, v26);
  if ( v15[1] )
    std::_Ref_count_base::_Decwref(v15[1]);
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  std::string::_Tidy_deallocate(v26);
  Spectre::Engine::Scene::Update(*a2, (const struct Spectre::Engine::FrameData *)(a1 + 46));
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v25);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v24);
  v11 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
          &v19,
          a1 + 58);
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v24,
    v11,
    (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
    777,
    (__int64)"UpdateScene",
    (__int64)"kSpectreRenderCB_PostSceneUpdate");
  std::string::string(v26, "kSpectreRenderCB_PostSceneUpdate");
  v12 = Spectre::Engine::Engine::GetCpuProfiler(a1, &v16);
  std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v15, v12);
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(v25, v15, v26);
  if ( v15[1] )
    std::_Ref_count_base::_Decwref(v15[1]);
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
  std::string::_Tidy_deallocate(v26);
  v19 = a1[121];
  LODWORD(v20) = 2;
  std::chrono::steady_clock::now(v21);
  Spectre::Engine::CpuProfiler::RegisterCallbackTime(
    v19,
    (const struct Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer *)&v19);
  *(_OWORD *)v15 = 0;
  *(_OWORD *)v14 = 0;
  Spectre::Engine::Engine::InvokeCallback(a1, 2, v14, v15);
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v25);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v24);
  (*((void (__fastcall **)(Spectre::Engine::CpuProfiler **, Spectre::Engine::Scene **))*a1 + 13))(a1, a2);
  std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v22);
  return std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v23);
}

```

## disassembly

```asm
0x180035c90  mov     [rsp-8+arg_10], rbx
0x180035c95  push    rbp
0x180035c96  push    rsi
0x180035c97  push    rdi
0x180035c98  push    r12
0x180035c9a  push    r14
0x180035c9c  lea     rbp, [rsp-60h]
0x180035ca1  sub     rsp, 160h
0x180035ca8  mov     rax, cs:__security_cookie
0x180035caf  xor     rax, rsp
0x180035cb2  mov     [rbp+80h+var_30], rax
0x180035cb6  mov     rdi, rdx
0x180035cb9  mov     rbx, rcx
0x180035cbc  add     rcx, 8; this
0x180035cc0  lea     rdx, [rbp+80h+var_E0]
0x180035cc4  call    ?GetExclusiveLockIfNecessary@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLockIfNecessary(void)
0x180035cc9  nop
0x180035cca  mov     rcx, [rdi]
0x180035ccd  add     rcx, 10h; this
0x180035cd1  lea     rdx, [rbp+80h+var_F0]
0x180035cd5  call    ?GetExclusiveLockIfNecessary@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLockIfNecessary(void)
0x180035cda  nop
0x180035cdb  mov     r8, rdi
0x180035cde  lea     rdx, [rsp+180h+var_140]
0x180035ce3  call    ?GetTweenManager@Engine@1Spectre@@QEBA?AV?$shared_ptr@VTweenManager@Tweening@Utils@Spectre@@@std@@AEBV?$shared_ptr@VScene@Engine@Spectre@@@4@@Z; Spectre::Engine::Engine::GetTweenManager(std::shared_ptr<Spectre::Engine::Scene> const &)
0x180035ce8  nop
0x180035ce9  mov     rcx, [rsp+180h+var_140]; this
0x180035cee  test    rcx, rcx
0x180035cf1  jz      short loc_180035CF9
0x180035cf3  call    ?Update@TweenManager@Tweening@Utils@Spectre@@QEAAXXZ; Spectre::Utils::Tweening::TweenManager::Update(void)
0x180035cf8  nop
0x180035cf9  mov     rcx, [rsp+180h+var_140+8]; this
0x180035cfe  test    rcx, rcx
0x180035d01  jz      short loc_180035D08
0x180035d03  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180035d08  lea     rsi, [rbx+1D0h]
0x180035d0f  mov     rdx, rsi
0x180035d12  lea     rcx, [rsp+180h+var_130]
0x180035d17  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180035d1c  lea     r14, aPreupdatescene; "PreUpdateScene"
0x180035d23  mov     [rsp+180h+var_158], r14
0x180035d28  lea     r12, aUpdatescene; "UpdateScene"
0x180035d2f  mov     [rsp+180h+var_160], r12
0x180035d34  mov     r9d, 2EEh
0x180035d3a  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180035d41  mov     rdx, rax
0x180035d44  lea     rcx, [rbp+80h+var_70]
0x180035d48  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x180035d4d  nop
0x180035d4e  mov     rdx, r14
0x180035d51  lea     rcx, [rbp+80h+var_90]
0x180035d55  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180035d5a  nop
0x180035d5b  lea     rdx, [rsp+180h+var_120]
0x180035d60  mov     rcx, rbx
0x180035d63  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x180035d68  nop
0x180035d69  mov     rdx, rax
0x180035d6c  lea     rcx, [rsp+180h+var_140]
0x180035d71  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x180035d76  nop
0x180035d77  lea     r8, [rbp+80h+var_90]
0x180035d7b  lea     rdx, [rsp+180h+var_140]
0x180035d80  lea     rcx, [rsp+180h+var_108]
0x180035d85  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x180035d8a  nop
0x180035d8b  mov     rcx, [rsp+180h+var_140+8]; this
0x180035d90  test    rcx, rcx
0x180035d93  jz      short loc_180035D9B
0x180035d95  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180035d9a  nop
0x180035d9b  mov     rcx, [rsp+180h+var_118]; this
0x180035da0  test    rcx, rcx
0x180035da3  jz      short loc_180035DAB
0x180035da5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180035daa  nop
0x180035dab  lea     rcx, [rbp+80h+var_90]
0x180035daf  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180035db4  mov     rax, [rbx]
0x180035db7  mov     rdx, rdi
0x180035dba  mov     rcx, rbx
0x180035dbd  mov     rax, [rax+60h]
0x180035dc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035dc6  nop
0x180035dc7  lea     rcx, [rsp+180h+var_108]; this
0x180035dcc  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x180035dd1  nop
0x180035dd2  lea     rcx, [rbp+80h+var_70]; this
0x180035dd6  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x180035ddb  mov     rdx, rsi
0x180035dde  lea     rcx, [rsp+180h+var_120]
0x180035de3  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180035de8  lea     r14, aKspectrerender_5; "kSpectreRenderCB_PreSceneUpdate"
0x180035def  mov     [rsp+180h+var_158], r14
0x180035df4  mov     [rsp+180h+var_160], r12
0x180035df9  mov     r9d, 2FDh
0x180035dff  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180035e06  mov     rdx, rax
0x180035e09  lea     rcx, [rbp+80h+var_D0]
0x180035e0d  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x180035e12  nop
0x180035e13  mov     rdx, r14
0x180035e16  lea     rcx, [rbp+80h+var_70]
0x180035e1a  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180035e1f  nop
0x180035e20  lea     rdx, [rsp+180h+var_108]
0x180035e25  mov     rcx, rbx
0x180035e28  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x180035e2d  nop
0x180035e2e  mov     rdx, rax
0x180035e31  lea     rcx, [rsp+180h+var_140]
0x180035e36  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x180035e3b  nop
0x180035e3c  lea     r8, [rbp+80h+var_70]
0x180035e40  lea     rdx, [rsp+180h+var_140]
0x180035e45  lea     rcx, [rbp+80h+var_90]
0x180035e49  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x180035e4e  nop
0x180035e4f  mov     rcx, [rsp+180h+var_140+8]; this
0x180035e54  test    rcx, rcx
0x180035e57  jz      short loc_180035E5F
0x180035e59  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180035e5e  nop
0x180035e5f  mov     rcx, [rbp+80h+var_100]; this
0x180035e63  test    rcx, rcx
0x180035e66  jz      short loc_180035E6E
0x180035e68  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180035e6d  nop
0x180035e6e  lea     rcx, [rbp+80h+var_70]
0x180035e72  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180035e77  mov     rax, [rbx+3C8h]
0x180035e7e  mov     [rsp+180h+var_120], rax
0x180035e83  mov     r14d, 1
0x180035e89  mov     dword ptr [rsp+180h+var_118], r14d
0x180035e8e  lea     rcx, [rsp+180h+var_110]
0x180035e93  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180035e98  nop
0x180035e99  lea     rdx, [rsp+180h+var_120]; struct Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer *
0x180035e9e  mov     rcx, [rsp+180h+var_120]; this
0x180035ea3  call    ?RegisterCallbackTime@CpuProfiler@Engine@Spectre@@QEAAXAEBVScopedCallbackPerformanceTimer@123@@Z; Spectre::Engine::CpuProfiler::RegisterCallbackTime(Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer const &)
0x180035ea8  nop
0x180035ea9  xorps   xmm0, xmm0
0x180035eac  movdqu  xmmword ptr [rsp+180h+var_130], xmm0
0x180035eb2  movdqu  xmmword ptr [rsp+180h+var_140], xmm0
0x180035eb8  lea     r9, [rsp+180h+var_130]
0x180035ebd  lea     r8, [rsp+180h+var_140]
0x180035ec2  mov     edx, r14d
0x180035ec5  mov     rcx, rbx
0x180035ec8  call    ?InvokeCallback@Engine@1Spectre@@IEAAXW4ESpectreNativeRenderCallbackType@12@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VIRenderOutput@Engine@Spectre@@@5@@Z; Spectre::Engine::Engine::InvokeCallback(Spectre::Engine::ESpectreNativeRenderCallbackType,std::shared_ptr<Spectre::Engine::RenderDevice>,std::shared_ptr<Spectre::Engine::IRenderOutput>)
0x180035ecd  nop
0x180035ece  lea     rcx, [rbp+80h+var_90]; this
0x180035ed2  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x180035ed7  nop
0x180035ed8  lea     rcx, [rbp+80h+var_D0]; this
0x180035edc  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x180035ee1  mov     rdx, rsi
0x180035ee4  lea     rcx, [rsp+180h+var_108]
0x180035ee9  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180035eee  lea     r14, aUpdateScene; "Update Scene"
0x180035ef5  mov     [rsp+180h+var_158], r14
0x180035efa  mov     [rsp+180h+var_160], r12
0x180035eff  mov     r9d, 303h
0x180035f05  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180035f0c  mov     rdx, rax
0x180035f0f  lea     rcx, [rbp+80h+var_D0]
0x180035f13  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x180035f18  nop
0x180035f19  mov     rdx, r14
0x180035f1c  lea     rcx, [rbp+80h+var_70]
0x180035f20  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180035f25  nop
0x180035f26  lea     rdx, [rsp+180h+var_120]
0x180035f2b  mov     rcx, rbx
0x180035f2e  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x180035f33  nop
0x180035f34  mov     rdx, rax
0x180035f37  lea     rcx, [rsp+180h+var_130]
0x180035f3c  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x180035f41  nop
0x180035f42  lea     r8, [rbp+80h+var_70]
0x180035f46  lea     rdx, [rsp+180h+var_130]
0x180035f4b  lea     rcx, [rbp+80h+var_90]
0x180035f4f  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x180035f54  nop
0x180035f55  mov     rcx, [rsp+180h+var_130+8]; this
0x180035f5a  test    rcx, rcx
0x180035f5d  jz      short loc_180035F65
0x180035f5f  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180035f64  nop
0x180035f65  mov     rcx, [rsp+180h+var_118]; this
0x180035f6a  test    rcx, rcx
0x180035f6d  jz      short loc_180035F75
0x180035f6f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180035f74  nop
0x180035f75  lea     rcx, [rbp+80h+var_70]
0x180035f79  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180035f7e  lea     rdx, [rbx+170h]; struct Spectre::Engine::FrameData *
0x180035f85  mov     rcx, [rdi]; this
0x180035f88  call    ?Update@Scene@Engine@Spectre@@QEAAXAEBVFrameData@23@@Z; Spectre::Engine::Scene::Update(Spectre::Engine::FrameData const &)
0x180035f8d  nop
0x180035f8e  lea     rcx, [rbp+80h+var_90]; this
0x180035f92  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x180035f97  nop
0x180035f98  lea     rcx, [rbp+80h+var_D0]; this
0x180035f9c  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x180035fa1  mov     rdx, rsi
0x180035fa4  lea     rcx, [rsp+180h+var_108]
0x180035fa9  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180035fae  lea     rsi, aKspectrerender_2; "kSpectreRenderCB_PostSceneUpdate"
0x180035fb5  mov     [rsp+180h+var_158], rsi
0x180035fba  mov     [rsp+180h+var_160], r12
0x180035fbf  mov     r9d, 309h
0x180035fc5  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180035fcc  mov     rdx, rax
0x180035fcf  lea     rcx, [rbp+80h+var_D0]
0x180035fd3  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x180035fd8  nop
0x180035fd9  mov     rdx, rsi
0x180035fdc  lea     rcx, [rbp+80h+var_70]
0x180035fe0  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180035fe5  nop
0x180035fe6  lea     rdx, [rsp+180h+var_120]
0x180035feb  mov     rcx, rbx
0x180035fee  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x180035ff3  nop
0x180035ff4  mov     rdx, rax
0x180035ff7  lea     rcx, [rsp+180h+var_130]
0x180035ffc  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x180036001  nop
0x180036002  lea     r8, [rbp+80h+var_70]
0x180036006  lea     rdx, [rsp+180h+var_130]
0x18003600b  lea     rcx, [rbp+80h+var_90]
0x18003600f  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x180036014  nop
0x180036015  mov     rcx, [rsp+180h+var_130+8]; this
0x18003601a  test    rcx, rcx
0x18003601d  jz      short loc_180036025
0x18003601f  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180036024  nop
0x180036025  mov     rcx, [rsp+180h+var_118]; this
0x18003602a  test    rcx, rcx
0x18003602d  jz      short loc_180036035
0x18003602f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180036034  nop
0x180036035  lea     rcx, [rbp+80h+var_70]
0x180036039  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003603e  mov     rax, [rbx+3C8h]
0x180036045  mov     [rsp+180h+var_108], rax
0x18003604a  mov     esi, 2
0x18003604f  mov     dword ptr [rbp+80h+var_100], esi
0x180036052  lea     rcx, [rbp+80h+var_F8]
0x180036056  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18003605b  nop
0x18003605c  lea     rdx, [rsp+180h+var_108]; struct Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer *
0x180036061  mov     rcx, [rsp+180h+var_108]; this
0x180036066  call    ?RegisterCallbackTime@CpuProfiler@Engine@Spectre@@QEAAXAEBVScopedCallbackPerformanceTimer@123@@Z; Spectre::Engine::CpuProfiler::RegisterCallbackTime(Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer const &)
0x18003606b  nop
0x18003606c  xorps   xmm0, xmm0
0x18003606f  movdqu  xmmword ptr [rsp+180h+var_130], xmm0
0x180036075  movdqu  xmmword ptr [rsp+180h+var_140], xmm0
0x18003607b  lea     r9, [rsp+180h+var_130]
0x180036080  lea     r8, [rsp+180h+var_140]
0x180036085  mov     edx, esi
0x180036087  mov     rcx, rbx
0x18003608a  call    ?InvokeCallback@Engine@1Spectre@@IEAAXW4ESpectreNativeRenderCallbackType@12@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VIRenderOutput@Engine@Spectre@@@5@@Z; Spectre::Engine::Engine::InvokeCallback(Spectre::Engine::ESpectreNativeRenderCallbackType,std::shared_ptr<Spectre::Engine::RenderDevice>,std::shared_ptr<Spectre::Engine::IRenderOutput>)
0x18003608f  nop
0x180036090  lea     rcx, [rbp+80h+var_90]; this
0x180036094  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x180036099  nop
0x18003609a  lea     rcx, [rbp+80h+var_D0]; this
0x18003609e  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x1800360a3  mov     rax, [rbx]
0x1800360a6  mov     rdx, rdi
0x1800360a9  mov     rcx, rbx
0x1800360ac  mov     rax, [rax+68h]
0x1800360b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800360b5  nop
0x1800360b6  lea     rcx, [rbp+80h+var_F0]
0x1800360ba  call    ??1?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(void)
0x1800360bf  nop
0x1800360c0  lea     rcx, [rbp+80h+var_E0]
0x1800360c4  call    ??1?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(void)
0x1800360c9  mov     rcx, [rbp+80h+var_30]
0x1800360cd  xor     rcx, rsp; StackCookie
0x1800360d0  call    __security_check_cookie
0x1800360d5  mov     rbx, [rsp+180h+arg_10]
0x1800360dd  add     rsp, 160h
0x1800360e4  pop     r14
0x1800360e6  pop     r12
0x1800360e8  pop     rdi
0x1800360e9  pop     rsi
0x1800360ea  pop     rbp
0x1800360eb  retn
```
