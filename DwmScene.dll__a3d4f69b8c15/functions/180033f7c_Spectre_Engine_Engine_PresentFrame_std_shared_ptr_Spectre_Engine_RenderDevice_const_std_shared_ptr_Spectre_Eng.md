# Spectre::Engine::Engine::PresentFrame(std::shared_ptr<Spectre::Engine::RenderDevice> const &,std::shared_ptr<Spectre::Engine::IRenderOutput> const &,std::unique_lock<Spectre::Engine::Mutex> &,std::unique_lock<Spectre::Engine::Mutex> &,std::unique_lock<Spectre::Engine::Mutex> &)

- ea: `0x180033f7c`
- end: `0x1800341cf`
- name: `?PresentFrame@Engine@1Spectre@@IEAAXAEBV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@AEBV?$shared_ptr@VIRenderOutput@Engine@Spectre@@@4@AEAV?$unique_lock@VMutex@Engine@Spectre@@@4@22@Z`
- size: `595`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x18005355c`

## callees

- `0x18000ca90`
- `0x18001128c`
- `0x1800112c4`
- `0x180011f64`
- `0x180012ba8`
- `0x180012cd0`
- `0x180012df8`
- `0x180016324`
- `0x18001fba8`
- `0x18001fca8`
- `0x18002fadc`
- `0x180030700`
- `0x180032b58`
- `0x180033794`
- `0x180033f7c`
- `0x1800945d8`
- `0x1800e7010`

## string_xrefs

- `0x180033fe8`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`
- `0x1800340c6`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall Spectre::Engine::Engine::PresentFrame(
        __int64 a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v10; // r14
  int v11; // eax
  __int64 CpuProfiler; // rax
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // r9
  _BYTE v17[8]; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v18; // [rsp+48h] [rbp-B8h]
  _BYTE v19[8]; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v20; // [rsp+58h] [rbp-A8h]
  Spectre::Engine::CpuProfiler *v21; // [rsp+60h] [rbp-A0h] BYREF
  int v22; // [rsp+68h] [rbp-98h]
  _BYTE v23[8]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v24[8]; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v25; // [rsp+80h] [rbp-80h]
  _BYTE v26[64]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v27[32]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v28[64]; // [rsp+F0h] [rbp-10h] BYREF

  v10 = a1 + 464;
  v11 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
          v17,
          a1 + 464);
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v28,
    v11,
    (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
    1050,
    (__int64)"PresentFrame",
    (__int64)"PresentFrame");
  std::string::string(v27, "PresentFrame");
  CpuProfiler = Spectre::Engine::Engine::GetCpuProfiler(a1, v19);
  std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v17, CpuProfiler);
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(&v21, v17, v27);
  if ( v18 )
    std::_Ref_count_base::_Decwref(v18);
  if ( v20 )
    std::_Ref_count_base::_Decref(v20);
  std::string::_Tidy_deallocate(v27);
  (*(void (__fastcall **)(_QWORD, __int64, __int64, __int64, __int64))(*(_QWORD *)*a2 + 216LL))(*a2, a3, a4, a5, a6);
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)&v21);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v28);
  v13 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
          v19,
          v10);
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v26,
    v13,
    (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
    1056,
    (__int64)"PresentFrame",
    (__int64)"kSpectreRenderCB_PostPresent");
  std::string::string(v28, "kSpectreRenderCB_PostPresent");
  v14 = Spectre::Engine::Engine::GetCpuProfiler(a1, v24);
  std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v17, v14);
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(v27, v17, v28);
  if ( v18 )
    std::_Ref_count_base::_Decwref(v18);
  if ( v25 )
    std::_Ref_count_base::_Decref(v25);
  std::string::_Tidy_deallocate(v28);
  v21 = *(Spectre::Engine::CpuProfiler **)(a1 + 968);
  v22 = 6;
  std::chrono::steady_clock::now(v23);
  Spectre::Engine::CpuProfiler::RegisterCallbackTime(
    v21,
    (const struct Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer *)&v21);
  std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(v19, a3);
  v15 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
          &v21,
          a2);
  Spectre::Engine::Engine::InvokeCallback(a1, 6, v15, v16);
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v27);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v26);
}

```

## disassembly

```asm
0x180033f7c  push    rbp
0x180033f7e  push    rbx
0x180033f7f  push    rsi
0x180033f80  push    rdi
0x180033f81  push    r12
0x180033f83  push    r13
0x180033f85  push    r14
0x180033f87  push    r15
0x180033f89  lea     rbp, [rsp-48h]
0x180033f8e  sub     rsp, 148h
0x180033f95  mov     rax, cs:__security_cookie
0x180033f9c  xor     rax, rsp
0x180033f9f  mov     [rbp+80h+var_50], rax
0x180033fa3  mov     r15, r9
0x180033fa6  mov     rsi, r8
0x180033fa9  mov     rdi, rdx
0x180033fac  mov     rbx, rcx
0x180033faf  mov     r12, [rbp+80h+arg_20]
0x180033fb6  mov     r13, [rbp+80h+arg_28]
0x180033fbd  lea     r14, [rcx+1D0h]
0x180033fc4  mov     rdx, r14
0x180033fc7  lea     rcx, [rsp+180h+var_140]
0x180033fcc  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180033fd1  lea     rcx, aPresentframe; "PresentFrame"
0x180033fd8  mov     [rsp+180h+var_158], rcx
0x180033fdd  mov     [rsp+180h+var_160], rcx
0x180033fe2  mov     r9d, 41Ah
0x180033fe8  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180033fef  mov     rdx, rax
0x180033ff2  lea     rcx, [rbp+80h+var_90]
0x180033ff6  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x180033ffb  nop
0x180033ffc  lea     rdx, aPresentframe; "PresentFrame"
0x180034003  lea     rcx, [rbp+80h+var_B0]
0x180034007  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003400c  nop
0x18003400d  lea     rdx, [rsp+180h+var_130]
0x180034012  mov     rcx, rbx
0x180034015  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x18003401a  nop
0x18003401b  mov     rdx, rax
0x18003401e  lea     rcx, [rsp+180h+var_140]
0x180034023  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x180034028  nop
0x180034029  lea     r8, [rbp+80h+var_B0]
0x18003402d  lea     rdx, [rsp+180h+var_140]
0x180034032  lea     rcx, [rsp+180h+var_120]
0x180034037  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x18003403c  nop
0x18003403d  mov     rcx, [rsp+180h+var_138]; this
0x180034042  test    rcx, rcx
0x180034045  jz      short loc_18003404D
0x180034047  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18003404c  nop
0x18003404d  mov     rcx, [rsp+180h+var_128]; this
0x180034052  test    rcx, rcx
0x180034055  jz      short loc_18003405D
0x180034057  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003405c  nop
0x18003405d  lea     rcx, [rbp+80h+var_B0]
0x180034061  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180034066  mov     rcx, [rdi]
0x180034069  mov     rax, [rcx]
0x18003406c  mov     [rsp+180h+var_160], r13
0x180034071  mov     r9, r12
0x180034074  mov     r8, r15
0x180034077  mov     rdx, rsi
0x18003407a  mov     rax, [rax+0D8h]
0x180034081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034086  nop
0x180034087  lea     rcx, [rsp+180h+var_120]; this
0x18003408c  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x180034091  nop
0x180034092  lea     rcx, [rbp+80h+var_90]; this
0x180034096  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x18003409b  mov     rdx, r14
0x18003409e  lea     rcx, [rsp+180h+var_130]
0x1800340a3  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800340a8  lea     r14, aKspectrerender_4; "kSpectreRenderCB_PostPresent"
0x1800340af  mov     [rsp+180h+var_158], r14
0x1800340b4  lea     rcx, aPresentframe; "PresentFrame"
0x1800340bb  mov     [rsp+180h+var_160], rcx
0x1800340c0  mov     r9d, 420h
0x1800340c6  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800340cd  mov     rdx, rax
0x1800340d0  lea     rcx, [rbp+80h+var_F0]
0x1800340d4  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x1800340d9  nop
0x1800340da  mov     rdx, r14
0x1800340dd  lea     rcx, [rbp+80h+var_90]
0x1800340e1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800340e6  nop
0x1800340e7  lea     rdx, [rsp+180h+var_108]
0x1800340ec  mov     rcx, rbx
0x1800340ef  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x1800340f4  nop
0x1800340f5  mov     rdx, rax
0x1800340f8  lea     rcx, [rsp+180h+var_140]
0x1800340fd  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x180034102  nop
0x180034103  lea     r8, [rbp+80h+var_90]
0x180034107  lea     rdx, [rsp+180h+var_140]
0x18003410c  lea     rcx, [rbp+80h+var_B0]
0x180034110  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x180034115  nop
0x180034116  mov     rcx, [rsp+180h+var_138]; this
0x18003411b  test    rcx, rcx
0x18003411e  jz      short loc_180034126
0x180034120  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180034125  nop
0x180034126  mov     rcx, [rbp+80h+var_100]; this
0x18003412a  test    rcx, rcx
0x18003412d  jz      short loc_180034135
0x18003412f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180034134  nop
0x180034135  lea     rcx, [rbp+80h+var_90]
0x180034139  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x18003413e  mov     rax, [rbx+3C8h]
0x180034145  mov     [rsp+180h+var_120], rax
0x18003414a  mov     r14d, 6
0x180034150  mov     [rsp+180h+var_118], r14d
0x180034155  lea     rcx, [rsp+180h+var_110]
0x18003415a  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18003415f  nop
0x180034160  lea     rdx, [rsp+180h+var_120]; struct Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer *
0x180034165  mov     rcx, [rsp+180h+var_120]; this
0x18003416a  call    ?RegisterCallbackTime@CpuProfiler@Engine@Spectre@@QEAAXAEBVScopedCallbackPerformanceTimer@123@@Z; Spectre::Engine::CpuProfiler::RegisterCallbackTime(Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer const &)
0x18003416f  nop
0x180034170  mov     rdx, rsi
0x180034173  lea     rcx, [rsp+180h+var_130]
0x180034178  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003417d  mov     r9, rax
0x180034180  mov     rdx, rdi
0x180034183  lea     rcx, [rsp+180h+var_120]
0x180034188  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003418d  mov     r8, rax
0x180034190  mov     edx, r14d
0x180034193  mov     rcx, rbx
0x180034196  call    ?InvokeCallback@Engine@1Spectre@@IEAAXW4ESpectreNativeRenderCallbackType@12@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VIRenderOutput@Engine@Spectre@@@5@@Z; Spectre::Engine::Engine::InvokeCallback(Spectre::Engine::ESpectreNativeRenderCallbackType,std::shared_ptr<Spectre::Engine::RenderDevice>,std::shared_ptr<Spectre::Engine::IRenderOutput>)
0x18003419b  nop
0x18003419c  lea     rcx, [rbp+80h+var_B0]; this
0x1800341a0  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x1800341a5  nop
0x1800341a6  lea     rcx, [rbp+80h+var_F0]; this
0x1800341aa  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x1800341af  mov     rcx, [rbp+80h+var_50]
0x1800341b3  xor     rcx, rsp; StackCookie
0x1800341b6  call    __security_check_cookie
0x1800341bb  add     rsp, 148h
0x1800341c2  pop     r15
0x1800341c4  pop     r14
0x1800341c6  pop     r13
0x1800341c8  pop     r12
0x1800341ca  pop     rdi
0x1800341cb  pop     rsi
0x1800341cc  pop     rbx
0x1800341cd  pop     rbp
0x1800341ce  retn
```
