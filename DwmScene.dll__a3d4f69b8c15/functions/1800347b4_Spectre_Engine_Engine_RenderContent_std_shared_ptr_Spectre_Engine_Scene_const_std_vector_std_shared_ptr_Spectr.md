# Spectre::Engine::Engine::RenderContent(std::shared_ptr<Spectre::Engine::Scene> const &,std::vector<std::shared_ptr<Spectre::Engine::Camera>,std::allocator<std::shared_ptr<Spectre::Engine::Camera>>> const &,std::shared_ptr<Spectre::Engine::IRenderOutput> const &)

- ea: `0x1800347b4`
- end: `0x180034c31`
- name: `?RenderContent@Engine@1Spectre@@IEAAXAEBV?$shared_ptr@VScene@Engine@Spectre@@@std@@AEBV?$vector@V?$shared_ptr@VCamera@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VCamera@Engine@Spectre@@@std@@@2@@4@AEBV?$shared_ptr@VIRenderOutput@Engine@Spectre@@@4@@Z`
- size: `1149`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18005355c`

## callees

- `0x18000ca90`
- `0x18001128c`
- `0x1800112c4`
- `0x180011f64`
- `0x180012ba8`
- `0x180012c58`
- `0x180012cd0`
- `0x180012df8`
- `0x180016324`
- `0x18001fba8`
- `0x18001fca8`
- `0x18002fadc`
- `0x180030700`
- `0x180032b58`
- `0x180033794`
- `0x1800347b4`
- `0x18007b744`
- `0x1800945d8`
- `0x1800e7010`

## string_xrefs

- `0x180034818`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`
- `0x180034910`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`
- `0x180034a1e`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`
- `0x180034af0`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
void __fastcall Spectre::Engine::Engine::RenderContent(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 v8; // rsi
  int v9; // eax
  __int64 CpuProfiler; // rax
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // r9
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rax
  __int64 v20; // rax
  __int64 v21; // r9
  _BYTE v22[8]; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v23; // [rsp+48h] [rbp-B8h]
  Spectre::Engine::CpuProfiler *v24; // [rsp+50h] [rbp-B0h] BYREF
  int v25; // [rsp+58h] [rbp-A8h]
  _BYTE v26[8]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v27; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v28; // [rsp+70h] [rbp-90h]
  _BYTE v29[8]; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v30; // [rsp+80h] [rbp-80h]
  _BYTE v31[8]; // [rsp+88h] [rbp-78h] BYREF
  std::_Ref_count_base *v32; // [rsp+90h] [rbp-70h]
  _BYTE v33[24]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v34[8]; // [rsp+B0h] [rbp-50h] BYREF
  std::_Ref_count_base *v35; // [rsp+B8h] [rbp-48h]
  _BYTE v36[8]; // [rsp+C0h] [rbp-40h] BYREF
  std::_Ref_count_base *v37; // [rsp+C8h] [rbp-38h]
  _BYTE v38[64]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v39[32]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v40[64]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v41[32]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v42[32]; // [rsp+190h] [rbp+90h] BYREF

  v8 = a1 + 464;
  v9 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
         &v27,
         a1 + 464);
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v40,
    v9,
    (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
    1017,
    (__int64)"RenderContent",
    (__int64)"RenderContent");
  std::string::string(v42, "RenderContent");
  CpuProfiler = Spectre::Engine::Engine::GetCpuProfiler(a1, v34);
  std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(&v27, CpuProfiler);
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(v39, &v27, v42);
  if ( v28 )
    std::_Ref_count_base::_Decwref(v28);
  if ( v35 )
    std::_Ref_count_base::_Decref(v35);
  std::string::_Tidy_deallocate(v42);
  v11 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(*(_QWORD *)*a4 + 376LL))(*a4, v36);
  std::weak_ptr<Spectre::Engine::RenderDevice>::lock(v11, &v27);
  if ( v37 )
    std::_Ref_count_base::_Decwref(v37);
  if ( v27 && (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27) )
  {
    v12 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
            v22,
            v8);
    Spectre::Utils::PerformanceScope::PerformanceScope(
      (unsigned int)v38,
      v12,
      (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
      1025,
      (__int64)"RenderContent",
      (__int64)"kSpectreRenderCB_PreRender");
    std::string::string(v41, "kSpectreRenderCB_PreRender");
    v13 = Spectre::Engine::Engine::GetCpuProfiler(a1, v31);
    std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v22, v13);
    Spectre::Engine::CpuProfilerScope::CpuProfilerScope(v33, v22, v41);
    if ( v23 )
      std::_Ref_count_base::_Decwref(v23);
    if ( v32 )
      std::_Ref_count_base::_Decref(v32);
    std::string::_Tidy_deallocate(v41);
    v24 = *(Spectre::Engine::CpuProfiler **)(a1 + 968);
    v25 = 3;
    std::chrono::steady_clock::now(v26);
    Spectre::Engine::CpuProfiler::RegisterCallbackTime(
      v24,
      (const struct Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer *)&v24);
    std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(v29, a4);
    v14 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
            &v24,
            &v27);
    Spectre::Engine::Engine::InvokeCallback(a1, 3, v14, v15);
    Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v33);
    Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v38);
    v16 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
            &v24,
            v8);
    Spectre::Utils::PerformanceScope::PerformanceScope(
      (unsigned int)v38,
      v16,
      (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
      1030,
      (__int64)"RenderContent",
      (__int64)"RenderScene");
    std::string::string(v41, "RenderScene");
    v17 = Spectre::Engine::Engine::GetCpuProfiler(a1, v29);
    std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v22, v17);
    Spectre::Engine::CpuProfilerScope::CpuProfilerScope(v33, v22, v41);
    if ( v23 )
      std::_Ref_count_base::_Decwref(v23);
    if ( v30 )
      std::_Ref_count_base::_Decref(v30);
    std::string::_Tidy_deallocate(v41);
    (*(void (__fastcall **)(__int64, __int64, __int64, __int64 *, _QWORD *))(*(_QWORD *)a1 + 128LL))(
      a1,
      a2,
      a3,
      &v27,
      a4);
    Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v33);
    Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v38);
    v18 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
            &v24,
            v8);
    Spectre::Utils::PerformanceScope::PerformanceScope(
      (unsigned int)v38,
      v18,
      (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
      1036,
      (__int64)"RenderContent",
      (__int64)"kSpectreRenderCB_EndFrame");
    std::string::string(v41, "kSpectreRenderCB_EndFrame");
    v19 = Spectre::Engine::Engine::GetCpuProfiler(a1, v29);
    std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v22, v19);
    Spectre::Engine::CpuProfilerScope::CpuProfilerScope(v33, v22, v41);
    if ( v23 )
      std::_Ref_count_base::_Decwref(v23);
    if ( v30 )
      std::_Ref_count_base::_Decref(v30);
    std::string::_Tidy_deallocate(v41);
    v24 = *(Spectre::Engine::CpuProfiler **)(a1 + 968);
    v25 = 5;
    std::chrono::steady_clock::now(v26);
    Spectre::Engine::CpuProfiler::RegisterCallbackTime(
      v24,
      (const struct Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer *)&v24);
    std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(&v24, a4);
    v20 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
            v31,
            &v27);
    Spectre::Engine::Engine::InvokeCallback(a1, 5, v20, v21);
    Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v33);
    Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v38);
  }
  if ( v28 )
    std::_Ref_count_base::_Decref(v28);
  Spectre::Engine::ShaderPropertyBlock::ClearTextureState(*(Spectre::Engine::ShaderPropertyBlock **)(*(_QWORD *)(a1 + 512) + 18648LL));
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v39);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v40);
}

```

## disassembly

```asm
0x1800347b4  push    rbp
0x1800347b6  push    rbx
0x1800347b7  push    rsi
0x1800347b8  push    rdi
0x1800347b9  push    r12
0x1800347bb  push    r13
0x1800347bd  push    r14
0x1800347bf  push    r15
0x1800347c1  lea     rbp, [rsp-0C8h]
0x1800347c9  sub     rsp, 1C8h
0x1800347d0  mov     rax, cs:__security_cookie
0x1800347d7  xor     rax, rsp
0x1800347da  mov     [rbp+100h+var_50], rax
0x1800347e1  mov     rdi, r9
0x1800347e4  mov     r15, r8
0x1800347e7  mov     r14, rdx
0x1800347ea  mov     rbx, rcx
0x1800347ed  lea     rsi, [rcx+1D0h]
0x1800347f4  mov     rdx, rsi
0x1800347f7  lea     rcx, [rsp+200h+var_198]
0x1800347fc  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180034801  lea     r13, aRendercontent; "RenderContent"
0x180034808  mov     [rsp+200h+var_1D8], r13
0x18003480d  mov     [rsp+200h+var_1E0], r13
0x180034812  mov     r9d, 3F9h
0x180034818  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003481f  mov     rdx, rax
0x180034822  lea     rcx, [rbp+100h+var_D0]
0x180034826  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x18003482b  nop
0x18003482c  mov     rdx, r13
0x18003482f  lea     rcx, [rbp+100h+var_70]
0x180034836  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003483b  nop
0x18003483c  lea     rdx, [rbp+100h+var_150]
0x180034840  mov     rcx, rbx
0x180034843  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x180034848  nop
0x180034849  mov     rdx, rax
0x18003484c  lea     rcx, [rsp+200h+var_198]
0x180034851  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x180034856  nop
0x180034857  lea     r8, [rbp+100h+var_70]
0x18003485e  lea     rdx, [rsp+200h+var_198]
0x180034863  lea     rcx, [rbp+100h+var_F0]
0x180034867  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x18003486c  nop
0x18003486d  mov     rcx, [rsp+200h+var_190]; this
0x180034872  test    rcx, rcx
0x180034875  jz      short loc_18003487D
0x180034877  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18003487c  nop
0x18003487d  mov     rcx, [rbp+100h+var_148]; this
0x180034881  test    rcx, rcx
0x180034884  jz      short loc_18003488C
0x180034886  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003488b  nop
0x18003488c  lea     rcx, [rbp+100h+var_70]
0x180034893  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180034898  mov     rcx, [rdi]
0x18003489b  mov     rax, [rcx]
0x18003489e  lea     rdx, [rbp+100h+var_140]
0x1800348a2  mov     rax, [rax+178h]
0x1800348a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348ae  lea     rdx, [rsp+200h+var_198]
0x1800348b3  mov     rcx, rax
0x1800348b6  call    ?lock@?$weak_ptr@VRenderDevice@Engine@Spectre@@@std@@QEBA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@2@XZ; std::weak_ptr<Spectre::Engine::RenderDevice>::lock(void)
0x1800348bb  nop
0x1800348bc  mov     rcx, [rbp+100h+var_138]; this
0x1800348c0  test    rcx, rcx
0x1800348c3  jz      short loc_1800348CA
0x1800348c5  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800348ca  mov     rcx, [rsp+200h+var_198]
0x1800348cf  test    rcx, rcx
0x1800348d2  jz      loc_180034BD8
0x1800348d8  mov     rax, [rcx]
0x1800348db  mov     rax, [rax+10h]
0x1800348df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800348e4  test    al, al
0x1800348e6  jz      loc_180034BD8
0x1800348ec  mov     rdx, rsi
0x1800348ef  lea     rcx, [rsp+200h+var_1C0]
0x1800348f4  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800348f9  lea     r12, aKspectrerender_1; "kSpectreRenderCB_PreRender"
0x180034900  mov     [rsp+200h+var_1D8], r12
0x180034905  mov     [rsp+200h+var_1E0], r13
0x18003490a  mov     r9d, 401h
0x180034910  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180034917  mov     rdx, rax
0x18003491a  lea     rcx, [rbp+100h+var_130]
0x18003491e  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x180034923  nop
0x180034924  mov     rdx, r12
0x180034927  lea     rcx, [rbp+100h+var_90]
0x18003492b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180034930  nop
0x180034931  lea     rdx, [rbp+100h+var_178]
0x180034935  mov     rcx, rbx
0x180034938  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x18003493d  nop
0x18003493e  mov     rdx, rax
0x180034941  lea     rcx, [rsp+200h+var_1C0]
0x180034946  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x18003494b  nop
0x18003494c  lea     r8, [rbp+100h+var_90]
0x180034950  lea     rdx, [rsp+200h+var_1C0]
0x180034955  lea     rcx, [rbp+100h+var_168]
0x180034959  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x18003495e  nop
0x18003495f  mov     rcx, [rsp+200h+var_1B8]; this
0x180034964  test    rcx, rcx
0x180034967  jz      short loc_18003496F
0x180034969  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18003496e  nop
0x18003496f  mov     rcx, [rbp+100h+var_170]; this
0x180034973  test    rcx, rcx
0x180034976  jz      short loc_18003497E
0x180034978  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003497d  nop
0x18003497e  lea     rcx, [rbp+100h+var_90]
0x180034982  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180034987  mov     rax, [rbx+3C8h]
0x18003498e  mov     [rsp+200h+var_1B0], rax
0x180034993  mov     r12d, 3
0x180034999  mov     [rsp+200h+var_1A8], r12d
0x18003499e  lea     rcx, [rsp+200h+var_1A0]
0x1800349a3  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x1800349a8  nop
0x1800349a9  lea     rdx, [rsp+200h+var_1B0]; struct Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer *
0x1800349ae  mov     rcx, [rsp+200h+var_1B0]; this
0x1800349b3  call    ?RegisterCallbackTime@CpuProfiler@Engine@Spectre@@QEAAXAEBVScopedCallbackPerformanceTimer@123@@Z; Spectre::Engine::CpuProfiler::RegisterCallbackTime(Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer const &)
0x1800349b8  nop
0x1800349b9  mov     rdx, rdi
0x1800349bc  lea     rcx, [rsp+200h+var_188]
0x1800349c1  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800349c6  mov     r9, rax
0x1800349c9  lea     rdx, [rsp+200h+var_198]
0x1800349ce  lea     rcx, [rsp+200h+var_1B0]
0x1800349d3  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800349d8  mov     r8, rax
0x1800349db  mov     edx, r12d
0x1800349de  mov     rcx, rbx
0x1800349e1  call    ?InvokeCallback@Engine@1Spectre@@IEAAXW4ESpectreNativeRenderCallbackType@12@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VIRenderOutput@Engine@Spectre@@@5@@Z; Spectre::Engine::Engine::InvokeCallback(Spectre::Engine::ESpectreNativeRenderCallbackType,std::shared_ptr<Spectre::Engine::RenderDevice>,std::shared_ptr<Spectre::Engine::IRenderOutput>)
0x1800349e6  nop
0x1800349e7  lea     rcx, [rbp+100h+var_168]; this
0x1800349eb  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x1800349f0  nop
0x1800349f1  lea     rcx, [rbp+100h+var_130]; this
0x1800349f5  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x1800349fa  mov     rdx, rsi
0x1800349fd  lea     rcx, [rsp+200h+var_1B0]
0x180034a02  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180034a07  lea     r12, aRenderscene; "RenderScene"
0x180034a0e  mov     [rsp+200h+var_1D8], r12
0x180034a13  mov     [rsp+200h+var_1E0], r13
0x180034a18  mov     r9d, 406h
0x180034a1e  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180034a25  mov     rdx, rax
0x180034a28  lea     rcx, [rbp+100h+var_130]
0x180034a2c  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x180034a31  nop
0x180034a32  mov     rdx, r12
0x180034a35  lea     rcx, [rbp+100h+var_90]
0x180034a39  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180034a3e  nop
0x180034a3f  lea     rdx, [rsp+200h+var_188]
0x180034a44  mov     rcx, rbx
0x180034a47  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x180034a4c  nop
0x180034a4d  mov     rdx, rax
0x180034a50  lea     rcx, [rsp+200h+var_1C0]
0x180034a55  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x180034a5a  nop
0x180034a5b  lea     r8, [rbp+100h+var_90]
0x180034a5f  lea     rdx, [rsp+200h+var_1C0]
0x180034a64  lea     rcx, [rbp+100h+var_168]
0x180034a68  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x180034a6d  nop
0x180034a6e  mov     rcx, [rsp+200h+var_1B8]; this
0x180034a73  test    rcx, rcx
0x180034a76  jz      short loc_180034A7E
0x180034a78  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180034a7d  nop
0x180034a7e  mov     rcx, [rbp+100h+var_180]; this
0x180034a82  test    rcx, rcx
0x180034a85  jz      short loc_180034A8D
0x180034a87  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180034a8c  nop
0x180034a8d  lea     rcx, [rbp+100h+var_90]
0x180034a91  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180034a96  mov     rax, [rbx]
0x180034a99  mov     [rsp+200h+var_1E0], rdi
0x180034a9e  lea     r9, [rsp+200h+var_198]
0x180034aa3  mov     r8, r15
0x180034aa6  mov     rdx, r14
0x180034aa9  mov     rcx, rbx
0x180034aac  mov     rax, [rax+80h]
0x180034ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034ab8  nop
0x180034ab9  lea     rcx, [rbp+100h+var_168]; this
0x180034abd  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x180034ac2  nop
0x180034ac3  lea     rcx, [rbp+100h+var_130]; this
0x180034ac7  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x180034acc  mov     rdx, rsi
0x180034acf  lea     rcx, [rsp+200h+var_1B0]
0x180034ad4  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180034ad9  lea     rsi, aKspectrerender; "kSpectreRenderCB_EndFrame"
0x180034ae0  mov     [rsp+200h+var_1D8], rsi
0x180034ae5  mov     [rsp+200h+var_1E0], r13
0x180034aea  mov     r9d, 40Ch
0x180034af0  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180034af7  mov     rdx, rax
0x180034afa  lea     rcx, [rbp+100h+var_130]
0x180034afe  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x180034b03  nop
0x180034b04  mov     rdx, rsi
0x180034b07  lea     rcx, [rbp+100h+var_90]
0x180034b0b  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180034b10  nop
0x180034b11  lea     rdx, [rsp+200h+var_188]
0x180034b16  mov     rcx, rbx
0x180034b19  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x180034b1e  nop
0x180034b1f  mov     rdx, rax
0x180034b22  lea     rcx, [rsp+200h+var_1C0]
0x180034b27  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x180034b2c  nop
0x180034b2d  lea     r8, [rbp+100h+var_90]
0x180034b31  lea     rdx, [rsp+200h+var_1C0]
0x180034b36  lea     rcx, [rbp+100h+var_168]
0x180034b3a  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x180034b3f  nop
0x180034b40  mov     rcx, [rsp+200h+var_1B8]; this
0x180034b45  test    rcx, rcx
0x180034b48  jz      short loc_180034B50
0x180034b4a  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180034b4f  nop
0x180034b50  mov     rcx, [rbp+100h+var_180]; this
0x180034b54  test    rcx, rcx
0x180034b57  jz      short loc_180034B5F
0x180034b59  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180034b5e  nop
0x180034b5f  lea     rcx, [rbp+100h+var_90]
0x180034b63  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180034b68  mov     rax, [rbx+3C8h]
0x180034b6f  mov     [rsp+200h+var_1B0], rax
0x180034b74  mov     esi, 5
0x180034b79  mov     [rsp+200h+var_1A8], esi
0x180034b7d  lea     rcx, [rsp+200h+var_1A0]
0x180034b82  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180034b87  nop
0x180034b88  lea     rdx, [rsp+200h+var_1B0]; struct Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer *
0x180034b8d  mov     rcx, [rsp+200h+var_1B0]; this
0x180034b92  call    ?RegisterCallbackTime@CpuProfiler@Engine@Spectre@@QEAAXAEBVScopedCallbackPerformanceTimer@123@@Z; Spectre::Engine::CpuProfiler::RegisterCallbackTime(Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer const &)
0x180034b97  nop
0x180034b98  mov     rdx, rdi
0x180034b9b  lea     rcx, [rsp+200h+var_1B0]
0x180034ba0  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180034ba5  mov     r9, rax
0x180034ba8  lea     rdx, [rsp+200h+var_198]
0x180034bad  lea     rcx, [rbp+100h+var_178]
0x180034bb1  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180034bb6  mov     r8, rax
0x180034bb9  mov     edx, esi
0x180034bbb  mov     rcx, rbx
0x180034bbe  call    ?InvokeCallback@Engine@1Spectre@@IEAAXW4ESpectreNativeRenderCallbackType@12@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VIRenderOutput@Engine@Spectre@@@5@@Z; Spectre::Engine::Engine::InvokeCallback(Spectre::Engine::ESpectreNativeRenderCallbackType,std::shared_ptr<Spectre::Engine::RenderDevice>,std::shared_ptr<Spectre::Engine::IRenderOutput>)
0x180034bc3  nop
0x180034bc4  lea     rcx, [rbp+100h+var_168]; this
0x180034bc8  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x180034bcd  nop
0x180034bce  lea     rcx, [rbp+100h+var_130]; this
0x180034bd2  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x180034bd7  nop
0x180034bd8  mov     rcx, [rsp+200h+var_190]; this
0x180034bdd  test    rcx, rcx
0x180034be0  jz      short loc_180034BE7
0x180034be2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180034be7  mov     rcx, [rbx+200h]
0x180034bee  mov     rcx, [rcx+48D8h]; this
0x180034bf5  call    ?ClearTextureState@ShaderPropertyBlock@Engine@Spectre@@QEAAXXZ; Spectre::Engine::ShaderPropertyBlock::ClearTextureState(void)
0x180034bfa  nop
0x180034bfb  lea     rcx, [rbp+100h+var_F0]; this
0x180034bff  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x180034c04  nop
0x180034c05  lea     rcx, [rbp+100h+var_D0]; this
0x180034c09  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x180034c0e  mov     rcx, [rbp+100h+var_50]
0x180034c15  xor     rcx, rsp; StackCookie
0x180034c18  call    __security_check_cookie
0x180034c1d  add     rsp, 1C8h
0x180034c24  pop     r15
0x180034c26  pop     r14
0x180034c28  pop     r13
0x180034c2a  pop     r12
0x180034c2c  pop     rdi
0x180034c2d  pop     rsi
0x180034c2e  pop     rbx
0x180034c2f  pop     rbp
0x180034c30  retn
  ... truncated ...
```
