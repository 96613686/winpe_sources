# Spectre::Engine::Engine::UpdateScenes(void)

- ea: `0x180036100`
- end: `0x1800364a0`
- name: `?UpdateScenes@Engine@1Spectre@@MEAAXXZ`
- size: `928`
- prototype: `void __fastcall(Spectre::Engine::Engine *__hidden this)`
- caller_count: `1`
- callee_count: `21`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800674f0`

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
- `0x180033354`
- `0x180033794`
- `0x180035c90`
- `0x180036100`
- `0x180037480`
- `0x18006cff4`
- `0x18006d218`
- `0x1800945d8`

## string_xrefs

- `0x18003615b`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`
- `0x1800361f8`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`
- `0x180036144`: `UpdateScenes`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall Spectre::Engine::Engine::UpdateScenes(Spectre::Engine::Engine *this)
{
  char *v2; // rdi
  int v3; // eax
  __int64 CpuProfiler; // rax
  int v5; // eax
  __int64 v6; // rax
  __int64 v7; // rdx
  Spectre::Engine::Scene **v8; // r14
  Spectre::Engine::Scene **v9; // rdi
  _OWORD *v10; // rsi
  Spectre::Engine::Engine *v11; // r12
  const struct Spectre::Engine::FrameInputData *FrameInputData; // rax
  __int128 v13; // xmm2
  __int128 v14; // xmm3
  Spectre::Engine::FrameInputData *v15; // rax
  __int64 v16; // rdx
  __int64 *v17; // rax
  __int64 v18; // rdx
  volatile __int32 *v19; // rcx
  std::_Ref_count_base *v20[2]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+58h] [rbp-A8h] BYREF
  _BYTE v23[8]; // [rsp+68h] [rbp-98h] BYREF
  std::_Ref_count_base *v24; // [rsp+70h] [rbp-90h]
  _BYTE v25[8]; // [rsp+78h] [rbp-88h] BYREF
  std::_Ref_count_base *v26; // [rsp+80h] [rbp-80h]
  _BYTE v27[24]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v28[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v29[64]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v30[64]; // [rsp+100h] [rbp+0h] BYREF
  _OWORD v31[3]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v32[32]; // [rsp+170h] [rbp+70h] BYREF

  v2 = (char *)this + 464;
  v3 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
         v20,
         (char *)this + 464);
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v30,
    v3,
    (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
    707,
    (__int64)"UpdateScenes",
    (__int64)"UpdateScenes");
  std::string::string(v32, "UpdateScenes");
  CpuProfiler = Spectre::Engine::Engine::GetCpuProfiler(this, v23);
  std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v20, CpuProfiler);
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(v28, v20, v32);
  if ( v20[1] )
    std::_Ref_count_base::_Decwref(v20[1]);
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
  std::string::_Tidy_deallocate(v32);
  v5 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(v20, v2);
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v29,
    v5,
    (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
    712,
    (__int64)"UpdateScenes",
    (__int64)"kSpectreRenderCB_BeginFrame");
  std::string::string(v31, "kSpectreRenderCB_BeginFrame");
  v6 = Spectre::Engine::Engine::GetCpuProfiler(this, v25);
  std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v20, v6);
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(v27, v20, v31);
  if ( v20[1] )
    std::_Ref_count_base::_Decwref(v20[1]);
  if ( v26 )
    std::_Ref_count_base::_Decref(v26);
  std::string::_Tidy_deallocate(v31);
  v20[0] = *((std::_Ref_count_base **)this + 121);
  LODWORD(v20[1]) = 0;
  std::chrono::steady_clock::now(v21);
  Spectre::Engine::CpuProfiler::RegisterCallbackTime(
    v20[0],
    (const struct Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer *)v20);
  *(_OWORD *)v20 = 0;
  v22 = 0;
  Spectre::Engine::Engine::InvokeCallback(this, 0, &v22, v20);
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v27);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v29);
  v8 = (Spectre::Engine::Scene **)*((_QWORD *)this + 89);
  *(_QWORD *)&v22 = v8;
  v9 = (Spectre::Engine::Scene **)*((_QWORD *)this + 88);
  if ( v9 != v8 )
  {
    v10 = (_OWORD *)((char *)this + 200);
    v11 = (Spectre::Engine::Engine *)((char *)this + 256);
    do
    {
      FrameInputData = Spectre::Engine::Input::GetFrameInputData((Spectre::Engine::Engine *)((char *)this + 376));
      v13 = *(_OWORD *)FrameInputData;
      v31[0] = *(_OWORD *)FrameInputData;
      v14 = *((_OWORD *)FrameInputData + 1);
      v31[1] = v14;
      v31[2] = *((_OWORD *)FrameInputData + 2);
      v15 = Spectre::Engine::Input::GetFrameInputData((Spectre::Engine::Engine *)((char *)this + 200));
      if ( Spectre::Engine::FrameInputData::HasAnyDefaultPointerState(v15)
        && !Spectre::Engine::FrameInputData::HasAnyDefaultPointerState((Spectre::Engine::FrameInputData *)v31) )
      {
        while ( _InterlockedExchange((volatile __int32 *)this + 62, 1) )
          ;
        *v10 = v13;
        *((_DWORD *)this + 54) = v14;
        v17 = (__int64 *)std::chrono::steady_clock::now(v20);
        v18 = *v17;
        *((_QWORD *)this + 35) = *v17;
        std::_Atomic_storage<long,4>::store((char *)this + 248, v18, 3);
        v8 = (Spectre::Engine::Scene **)v22;
      }
      *(_OWORD *)((char *)this + 376) = *v10;
      *(_OWORD *)((char *)this + 392) = *(_OWORD *)((char *)this + 216);
      *(_OWORD *)((char *)this + 408) = *(_OWORD *)((char *)this + 232);
      std::_Atomic_storage<long,4>::store((char *)this + 424, v16, 5);
      if ( (Spectre::Engine::Engine *)((char *)this + 432) != v11 )
        std::vector<Spectre::Engine::MessageEvent>::_Assign_counted_range<Spectre::Engine::MessageEvent *>(
          (char *)this + 432,
          *(_QWORD *)v11,
          (__int64)(*((_QWORD *)this + 33) - *(_QWORD *)v11) >> 3);
      *((_QWORD *)this + 57) = *((_QWORD *)this + 35);
      Spectre::Engine::Engine::UpdateScene((Spectre::Engine::CpuProfiler **)this, v9);
      v9 += 2;
    }
    while ( v9 != v8 );
  }
  v19 = (volatile __int32 *)((char *)this + 248);
  while ( _InterlockedExchange(v19, 1) )
    ;
  *(_OWORD *)((char *)this + 220) = *(_OWORD *)((char *)this + 200);
  *((_DWORD *)this + 59) = *((_DWORD *)this + 54);
  *((_DWORD *)this + 50) = -1082130432;
  *((_DWORD *)this + 51) = -1082130432;
  *((_QWORD *)this + 26) = 2;
  *((_DWORD *)this + 54) = 0;
  *((_QWORD *)this + 30) = 2;
  std::_Atomic_storage<long,4>::store(v19, v7, 3);
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v28);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v30);
}

```

## disassembly

```asm
0x180036100  push    rbp
0x180036102  push    rbx
0x180036103  push    rsi
0x180036104  push    rdi
0x180036105  push    r12
0x180036107  push    r13
0x180036109  push    r14
0x18003610b  push    r15
0x18003610d  lea     rbp, [rsp-0A8h]
0x180036115  sub     rsp, 1A8h
0x18003611c  mov     rax, cs:__security_cookie
0x180036123  xor     rax, rsp
0x180036126  mov     [rbp+0E0h+var_50], rax
0x18003612d  mov     rbx, rcx
0x180036130  lea     rdi, [rcx+1D0h]
0x180036137  mov     rdx, rdi
0x18003613a  lea     rcx, [rsp+1E0h+var_1A0]
0x18003613f  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180036144  lea     rsi, aUpdatescenes; "UpdateScenes"
0x18003614b  mov     [rsp+1E0h+var_1B8], rsi
0x180036150  mov     [rsp+1E0h+var_1C0], rsi
0x180036155  mov     r9d, 2C3h
0x18003615b  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180036162  mov     rdx, rax
0x180036165  lea     rcx, [rbp+0E0h+var_E0]
0x180036169  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x18003616e  nop
0x18003616f  mov     rdx, rsi
0x180036172  lea     rcx, [rbp+0E0h+var_70]
0x180036176  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x18003617b  nop
0x18003617c  lea     rdx, [rsp+1E0h+var_178]
0x180036181  mov     rcx, rbx
0x180036184  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x180036189  nop
0x18003618a  mov     rdx, rax
0x18003618d  lea     rcx, [rsp+1E0h+var_1A0]
0x180036192  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x180036197  nop
0x180036198  lea     r8, [rbp+0E0h+var_70]
0x18003619c  lea     rdx, [rsp+1E0h+var_1A0]
0x1800361a1  lea     rcx, [rbp+0E0h+var_140]
0x1800361a5  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x1800361aa  nop
0x1800361ab  mov     rcx, [rsp+1E0h+var_1A0+8]; this
0x1800361b0  test    rcx, rcx
0x1800361b3  jz      short loc_1800361BB
0x1800361b5  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800361ba  nop
0x1800361bb  mov     rcx, [rsp+1E0h+var_170]; this
0x1800361c0  test    rcx, rcx
0x1800361c3  jz      short loc_1800361CB
0x1800361c5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800361ca  nop
0x1800361cb  lea     rcx, [rbp+0E0h+var_70]
0x1800361cf  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800361d4  mov     rdx, rdi
0x1800361d7  lea     rcx, [rsp+1E0h+var_1A0]
0x1800361dc  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800361e1  lea     rdi, aKspectrerender_3; "kSpectreRenderCB_BeginFrame"
0x1800361e8  mov     [rsp+1E0h+var_1B8], rdi
0x1800361ed  mov     [rsp+1E0h+var_1C0], rsi
0x1800361f2  mov     r9d, 2C8h
0x1800361f8  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x1800361ff  mov     rdx, rax
0x180036202  lea     rcx, [rbp+0E0h+var_120]
0x180036206  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x18003620b  nop
0x18003620c  mov     rdx, rdi
0x18003620f  lea     rcx, [rbp+0E0h+var_A0]
0x180036213  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180036218  nop
0x180036219  lea     rdx, [rsp+1E0h+var_168]
0x18003621e  mov     rcx, rbx
0x180036221  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x180036226  nop
0x180036227  mov     rdx, rax
0x18003622a  lea     rcx, [rsp+1E0h+var_1A0]
0x18003622f  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x180036234  nop
0x180036235  lea     r8, [rbp+0E0h+var_A0]
0x180036239  lea     rdx, [rsp+1E0h+var_1A0]
0x18003623e  lea     rcx, [rbp+0E0h+var_158]
0x180036242  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x180036247  nop
0x180036248  mov     rcx, [rsp+1E0h+var_1A0+8]; this
0x18003624d  test    rcx, rcx
0x180036250  jz      short loc_180036258
0x180036252  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180036257  nop
0x180036258  mov     rcx, [rbp+0E0h+var_160]; this
0x18003625c  test    rcx, rcx
0x18003625f  jz      short loc_180036267
0x180036261  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180036266  nop
0x180036267  lea     rcx, [rbp+0E0h+var_A0]
0x18003626b  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180036270  mov     rax, [rbx+3C8h]
0x180036277  mov     [rsp+1E0h+var_1A0], rax
0x18003627c  mov     dword ptr [rsp+1E0h+var_1A0+8], 0
0x180036284  lea     rcx, [rsp+1E0h+var_190]
0x180036289  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18003628e  nop
0x18003628f  lea     rdx, [rsp+1E0h+var_1A0]; struct Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer *
0x180036294  mov     rcx, [rsp+1E0h+var_1A0]; this
0x180036299  call    ?RegisterCallbackTime@CpuProfiler@Engine@Spectre@@QEAAXAEBVScopedCallbackPerformanceTimer@123@@Z; Spectre::Engine::CpuProfiler::RegisterCallbackTime(Spectre::Engine::CpuProfiler::ScopedCallbackPerformanceTimer const &)
0x18003629e  nop
0x18003629f  xorps   xmm0, xmm0
0x1800362a2  movdqu  xmmword ptr [rsp+1E0h+var_1A0], xmm0
0x1800362a8  movdqu  [rsp+1E0h+var_188], xmm0
0x1800362ae  lea     r9, [rsp+1E0h+var_1A0]
0x1800362b3  lea     r8, [rsp+1E0h+var_188]
0x1800362b8  xor     edx, edx
0x1800362ba  mov     rcx, rbx
0x1800362bd  call    ?InvokeCallback@Engine@1Spectre@@IEAAXW4ESpectreNativeRenderCallbackType@12@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$shared_ptr@VIRenderOutput@Engine@Spectre@@@5@@Z; Spectre::Engine::Engine::InvokeCallback(Spectre::Engine::ESpectreNativeRenderCallbackType,std::shared_ptr<Spectre::Engine::RenderDevice>,std::shared_ptr<Spectre::Engine::IRenderOutput>)
0x1800362c2  nop
0x1800362c3  lea     rcx, [rbp+0E0h+var_158]; this
0x1800362c7  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x1800362cc  nop
0x1800362cd  lea     rcx, [rbp+0E0h+var_120]; this
0x1800362d1  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x1800362d6  mov     r14, [rbx+2C8h]
0x1800362dd  mov     qword ptr [rsp+1E0h+var_188], r14
0x1800362e2  mov     rdi, [rbx+2C0h]
0x1800362e9  cmp     rdi, r14
0x1800362ec  jz      loc_180036401
0x1800362f2  lea     r15, [rbx+178h]
0x1800362f9  lea     rsi, [rbx+0C8h]
0x180036300  lea     r12, [rbx+100h]
0x180036307  lea     r13, [rbx+1B0h]
0x18003630e  mov     rcx, r15; this
0x180036311  call    ?GetFrameInputData@Input@Engine@Spectre@@QEBAAEBUFrameInputData@23@XZ; Spectre::Engine::Input::GetFrameInputData(void)
0x180036316  movups  xmm2, xmmword ptr [rax]
0x180036319  movups  [rbp+0E0h+var_A0], xmm2
0x18003631d  movups  xmm3, xmmword ptr [rax+10h]
0x180036321  movups  [rbp+0E0h+var_90], xmm3
0x180036325  movups  xmm0, xmmword ptr [rax+20h]
0x180036329  movups  [rbp+0E0h+var_80], xmm0
0x18003632d  mov     rcx, rsi; this
0x180036330  call    ?GetFrameInputData@Input@Engine@Spectre@@QEBAAEBUFrameInputData@23@XZ; Spectre::Engine::Input::GetFrameInputData(void)
0x180036335  mov     rcx, rax; this
0x180036338  call    ?HasAnyDefaultPointerState@FrameInputData@Engine@Spectre@@QEBA_NXZ; Spectre::Engine::FrameInputData::HasAnyDefaultPointerState(void)
0x18003633d  test    al, al
0x18003633f  jz      short loc_180036390
0x180036341  lea     rcx, [rbp+0E0h+var_A0]; this
0x180036345  call    ?HasAnyDefaultPointerState@FrameInputData@Engine@Spectre@@QEBA_NXZ; Spectre::Engine::FrameInputData::HasAnyDefaultPointerState(void)
0x18003634a  test    al, al
0x18003634c  jnz     short loc_180036390
0x18003634e  lea     r14, [rbx+0F8h]
0x180036355  mov     eax, 1
0x18003635a  xchg    eax, [r14]
0x18003635d  test    eax, eax
0x18003635f  jnz     short loc_180036355
0x180036361  movups  xmmword ptr [rsi], xmm2
0x180036364  movss   dword ptr [rsi+10h], xmm3
0x180036369  lea     rcx, [rsp+1E0h+var_1A0]
0x18003636e  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x180036373  mov     rdx, [rax]
0x180036376  mov     [rbx+118h], rdx
0x18003637d  mov     r8d, 3
0x180036383  mov     rcx, r14
0x180036386  call    ?store@?$_Atomic_storage@J$03@std@@QEAAXJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::store(long,std::memory_order)
0x18003638b  mov     r14, qword ptr [rsp+1E0h+var_188]
0x180036390  movups  xmm0, xmmword ptr [rsi]
0x180036393  movups  xmmword ptr [r15], xmm0
0x180036397  movups  xmm1, xmmword ptr [rsi+10h]
0x18003639b  movups  xmmword ptr [r15+10h], xmm1
0x1800363a0  movups  xmm0, xmmword ptr [rsi+20h]
0x1800363a4  movups  xmmword ptr [r15+20h], xmm0
0x1800363a9  mov     r8d, 5
0x1800363af  lea     rcx, [rbx+1A8h]
0x1800363b6  call    ?store@?$_Atomic_storage@J$03@std@@QEAAXJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::store(long,std::memory_order)
0x1800363bb  cmp     r13, r12
0x1800363be  jz      short loc_1800363DB
0x1800363c0  mov     r8, [rbx+108h]
0x1800363c7  sub     r8, [r12]
0x1800363cb  sar     r8, 3
0x1800363cf  mov     rdx, [r12]
0x1800363d3  mov     rcx, r13
0x1800363d6  call    ??$_Assign_counted_range@PEAUMessageEvent@Engine@Spectre@@@?$vector@UMessageEvent@Engine@Spectre@@V?$allocator@UMessageEvent@Engine@Spectre@@@std@@@std@@AEAAXPEAUMessageEvent@Engine@Spectre@@_K@Z; std::vector<Spectre::Engine::MessageEvent>::_Assign_counted_range<Spectre::Engine::MessageEvent *>(Spectre::Engine::MessageEvent *,unsigned __int64)
0x1800363db  mov     rax, [rbx+118h]
0x1800363e2  mov     [rbx+1C8h], rax
0x1800363e9  mov     rdx, rdi
0x1800363ec  mov     rcx, rbx
0x1800363ef  call    ?UpdateScene@Engine@1Spectre@@IEAAXAEBV?$shared_ptr@VScene@Engine@Spectre@@@std@@@Z; Spectre::Engine::Engine::UpdateScene(std::shared_ptr<Spectre::Engine::Scene> const &)
0x1800363f4  add     rdi, 10h
0x1800363f8  cmp     rdi, r14
0x1800363fb  jnz     loc_18003630E
0x180036401  lea     rcx, [rbx+0F8h]
0x180036408  mov     eax, 1
0x18003640d  xchg    eax, [rcx]
0x18003640f  test    eax, eax
0x180036411  jnz     short loc_180036408
0x180036413  movups  xmm0, xmmword ptr [rbx+0C8h]
0x18003641a  movups  xmmword ptr [rbx+0DCh], xmm0
0x180036421  mov     eax, [rbx+0D8h]
0x180036427  mov     [rbx+0ECh], eax
0x18003642d  mov     eax, 0BF800000h
0x180036432  mov     [rbx+0C8h], eax
0x180036438  mov     [rbx+0CCh], eax
0x18003643e  mov     qword ptr [rbx+0D0h], 2
0x180036449  mov     dword ptr [rbx+0D8h], 0
0x180036453  mov     qword ptr [rbx+0F0h], 2
0x18003645e  mov     r8d, 3
0x180036464  call    ?store@?$_Atomic_storage@J$03@std@@QEAAXJW4memory_order@2@@Z; std::_Atomic_storage<long,4>::store(long,std::memory_order)
0x180036469  nop
0x18003646a  lea     rcx, [rbp+0E0h+var_140]; this
0x18003646e  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x180036473  nop
0x180036474  lea     rcx, [rbp+0E0h+var_E0]; this
0x180036478  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x18003647d  mov     rcx, [rbp+0E0h+var_50]
0x180036484  xor     rcx, rsp; StackCookie
0x180036487  call    __security_check_cookie
0x18003648c  add     rsp, 1A8h
0x180036493  pop     r15
0x180036495  pop     r14
0x180036497  pop     r13
0x180036499  pop     r12
0x18003649b  pop     rdi
0x18003649c  pop     rsi
0x18003649d  pop     rbx
0x18003649e  pop     rbp
0x18003649f  retn
```
