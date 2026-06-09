# Spectre::Engine::Engine::RemoveInvalidDevices(void)

- ea: `0x1800345ec`
- end: `0x1800347ad`
- name: `?RemoveInvalidDevices@Engine@1Spectre@@IEAAXXZ`
- size: `449`
- prototype: `void __fastcall(Spectre::Engine::Engine *__hidden this)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032720`

## callees

- `0x18000ca90`
- `0x18001128c`
- `0x1800112c4`
- `0x180011f64`
- `0x1800120ec`
- `0x180012ba8`
- `0x180012df8`
- `0x180014280`
- `0x180016324`
- `0x18001daf4`
- `0x18001fba8`
- `0x18001fca8`
- `0x180028f78`
- `0x18002faa0`
- `0x18002fadc`
- `0x180030700`
- `0x180031efc`
- `0x180032b58`
- `0x1800345ec`
- `0x1800e7010`

## string_xrefs

- `0x180034636`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`
- `0x18003461f`: `RemoveInvalidDevices`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall Spectre::Engine::Engine::RemoveInvalidDevices(Spectre::Engine::Engine *this)
{
  int v2; // eax
  __int64 CpuProfiler; // rax
  __int64 *v4; // rbx
  __int64 *v5; // rdi
  _BYTE v6[8]; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v7; // [rsp+48h] [rbp-B8h]
  _BYTE v8[8]; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v9; // [rsp+58h] [rbp-A8h]
  _QWORD v10[3]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v11[16]; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v12[24]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v13[64]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v14[32]; // [rsp+E0h] [rbp-20h] BYREF

  v2 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
         v6,
         (char *)this + 464);
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v13,
    v2,
    (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
    1719,
    (__int64)"RemoveInvalidDevices",
    (__int64)"RemoveInvalidDevices");
  std::string::string(v14, "RemoveInvalidDevices");
  CpuProfiler = Spectre::Engine::Engine::GetCpuProfiler(this, v8);
  std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v6, CpuProfiler);
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(v12, v6, v14);
  if ( v7 )
    std::_Ref_count_base::_Decwref(v7);
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  std::string::_Tidy_deallocate(v14);
  Spectre::Engine::Lockable::GetExclusiveLockIfNecessary((Spectre::Engine::Engine *)((char *)this + 112));
  std::vector<std::shared_ptr<Spectre::Engine::RenderDevice>>::vector<std::shared_ptr<Spectre::Engine::RenderDevice>>(
    v10,
    (char *)this + 88);
  v4 = (__int64 *)v10[0];
  v5 = (__int64 *)v10[1];
  while ( v4 != v5 )
  {
    if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)*v4 + 16LL))(*v4) )
    {
      Trace::LevelSettingsWrapper::Output(&gTraceLevelsNativeRenderer_Engine, 3, "==============================");
      Trace::LevelSettingsWrapper::Output(&gTraceLevelsNativeRenderer_Engine, 3, "INVALID RENDER DEVICE DETECTED");
      Spectre::Engine::Lockable::GetExclusiveLockIfNecessary((Spectre::Engine::Mutex *)(*v4 + 24));
      Spectre::Engine::Engine::DeleteDevice(this, v4);
      Trace::LevelSettingsWrapper::Output(&gTraceLevelsNativeRenderer_Engine, 3, "==============================");
      std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v8);
    }
    v4 += 2;
  }
  std::vector<std::shared_ptr<Spectre::Engine::LightProbe>>::_Tidy(v10);
  std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v11);
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v12);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v13);
}

```

## disassembly

```asm
0x1800345ec  push    rbp
0x1800345ee  push    rbx
0x1800345ef  push    rsi
0x1800345f0  push    rdi
0x1800345f1  lea     rbp, [rsp-18h]
0x1800345f6  sub     rsp, 118h
0x1800345fd  mov     rax, cs:__security_cookie
0x180034604  xor     rax, rsp
0x180034607  mov     [rbp+30h+var_30], rax
0x18003460b  mov     rsi, rcx
0x18003460e  lea     rdx, [rcx+1D0h]
0x180034615  lea     rcx, [rsp+130h+var_F0]
0x18003461a  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x18003461f  lea     rbx, aRemoveinvalidd; "RemoveInvalidDevices"
0x180034626  mov     [rsp+130h+var_108], rbx
0x18003462b  mov     [rsp+130h+var_110], rbx
0x180034630  mov     r9d, 6B7h
0x180034636  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003463d  mov     rdx, rax
0x180034640  lea     rcx, [rbp+30h+var_90]
0x180034644  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x180034649  nop
0x18003464a  mov     rdx, rbx
0x18003464d  lea     rcx, [rbp+30h+var_50]
0x180034651  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180034656  nop
0x180034657  lea     rdx, [rsp+130h+var_E0]
0x18003465c  mov     rcx, rsi
0x18003465f  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x180034664  nop
0x180034665  mov     rdx, rax
0x180034668  lea     rcx, [rsp+130h+var_F0]
0x18003466d  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x180034672  nop
0x180034673  lea     r8, [rbp+30h+var_50]
0x180034677  lea     rdx, [rsp+130h+var_F0]
0x18003467c  lea     rcx, [rbp+30h+var_A8]
0x180034680  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x180034685  nop
0x180034686  mov     rcx, [rsp+130h+var_E8]; this
0x18003468b  test    rcx, rcx
0x18003468e  jz      short loc_180034696
0x180034690  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180034695  nop
0x180034696  mov     rcx, [rsp+130h+var_D8]; this
0x18003469b  test    rcx, rcx
0x18003469e  jz      short loc_1800346A6
0x1800346a0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800346a5  nop
0x1800346a6  lea     rcx, [rbp+30h+var_50]
0x1800346aa  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800346af  lea     rcx, [rsi+70h]; this
0x1800346b3  lea     rdx, [rsp+130h+var_B8]
0x1800346b8  call    ?GetExclusiveLockIfNecessary@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLockIfNecessary(void)
0x1800346bd  nop
0x1800346be  lea     rdx, [rsi+58h]
0x1800346c2  lea     rcx, [rsp+130h+var_D0]
0x1800346c7  call    ??0?$vector@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@2@@std@@QEAA@AEBV01@@Z; std::vector<std::shared_ptr<Spectre::Engine::RenderDevice>>::vector<std::shared_ptr<Spectre::Engine::RenderDevice>>(std::vector<std::shared_ptr<Spectre::Engine::RenderDevice>> const &)
0x1800346cc  nop
0x1800346cd  mov     rbx, [rsp+130h+var_D0]
0x1800346d2  mov     rdi, [rsp+130h+var_C8]
0x1800346d7  jmp     loc_180034763
0x1800346dc  mov     rcx, [rbx]
0x1800346df  mov     rax, [rcx]
0x1800346e2  mov     rax, [rax+10h]
0x1800346e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800346eb  test    al, al
0x1800346ed  jnz     short loc_18003475F
0x1800346ef  lea     r8, asc_18016A4D8; "=============================="
0x1800346f6  mov     edx, 3
0x1800346fb  lea     rcx, ?gTraceLevelsNativeRenderer_Engine@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsNativeRenderer_Engine
0x180034702  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x180034707  lea     r8, aInvalidRenderD; "INVALID RENDER DEVICE DETECTED"
0x18003470e  mov     edx, 3
0x180034713  lea     rcx, ?gTraceLevelsNativeRenderer_Engine@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsNativeRenderer_Engine
0x18003471a  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x18003471f  mov     rcx, [rbx]
0x180034722  add     rcx, 18h; this
0x180034726  lea     rdx, [rsp+130h+var_E0]
0x18003472b  call    ?GetExclusiveLockIfNecessary@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLockIfNecessary(void)
0x180034730  nop
0x180034731  mov     rdx, rbx
0x180034734  mov     rcx, rsi; this
0x180034737  call    ?DeleteDevice@Engine@1Spectre@@QEAAX$$QEAV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@Z; Spectre::Engine::Engine::DeleteDevice(std::shared_ptr<Spectre::Engine::RenderDevice> &&)
0x18003473c  lea     r8, asc_18016A4D8; "=============================="
0x180034743  mov     edx, 3
0x180034748  lea     rcx, ?gTraceLevelsNativeRenderer_Engine@@3ULevelSettingsWrapper@Trace@@A; Trace::LevelSettingsWrapper gTraceLevelsNativeRenderer_Engine
0x18003474f  call    ?Output@LevelSettingsWrapper@Trace@@QEAAXW4Level@2@PEBDZZ; Trace::LevelSettingsWrapper::Output(Trace::Level,char const *,...)
0x180034754  nop
0x180034755  lea     rcx, [rsp+130h+var_E0]
0x18003475a  call    ??1?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(void)
0x18003475f  add     rbx, 10h
0x180034763  cmp     rbx, rdi
0x180034766  jnz     loc_1800346DC
0x18003476c  lea     rcx, [rsp+130h+var_D0]
0x180034771  call    ?_Tidy@?$vector@V?$shared_ptr@VLightProbe@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VLightProbe@Engine@Spectre@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<Spectre::Engine::LightProbe>>::_Tidy(void)
0x180034776  nop
0x180034777  lea     rcx, [rsp+130h+var_B8]
0x18003477c  call    ??1?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(void)
0x180034781  nop
0x180034782  lea     rcx, [rbp+30h+var_A8]; this
0x180034786  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x18003478b  nop
0x18003478c  lea     rcx, [rbp+30h+var_90]; this
0x180034790  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x180034795  mov     rcx, [rbp+30h+var_30]
0x180034799  xor     rcx, rsp; StackCookie
0x18003479c  call    __security_check_cookie
0x1800347a1  add     rsp, 118h
0x1800347a8  pop     rdi
0x1800347a9  pop     rsi
0x1800347aa  pop     rbx
0x1800347ab  pop     rbp
0x1800347ac  retn
```
