# Spectre::Engine::Engine::FrameTick(std::unique_lock<Spectre::Engine::Mutex> &)

- ea: `0x180032720`
- end: `0x180032933`
- name: `?FrameTick@Engine@1Spectre@@UEAAXAEAV?$unique_lock@VMutex@Engine@Spectre@@@std@@@Z`
- size: `531`
- prototype: `__int64 __fastcall(Spectre::Engine::Engine *this)`
- caller_count: `0`
- callee_count: `27`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x18000ca90`
- `0x18001128c`
- `0x1800112c4`
- `0x180011f64`
- `0x180012ba8`
- `0x180012df8`
- `0x180016324`
- `0x18001fba8`
- `0x18001fca8`
- `0x18002921c`
- `0x18002fadc`
- `0x180030700`
- `0x180031554`
- `0x180032720`
- `0x180032b10`
- `0x180032b58`
- `0x180032c44`
- `0x180032cdc`
- `0x180033210`
- `0x1800343b4`
- `0x1800345ec`
- `0x180034c38`
- `0x1800356c0`
- `0x180035ba4`
- `0x1800364a8`
- `0x180036634`
- `0x1800e7010`

## string_xrefs

- `0x180032788`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Spectre::Engine::Engine::FrameTick(Spectre::Engine::Engine *this)
{
  int v2; // eax
  __int64 CpuProfiler; // rax
  __int64 v4; // rdi
  struct Spectre::Utils::IConfigurationManager *Configuration; // rax
  unsigned int v6; // eax
  struct Spectre::Utils::IConfigurationManager *v7; // rax
  Spectre::Engine::Engine *v8; // rcx
  __int64 v9; // [rsp+40h] [rbp-59h] BYREF
  std::_Ref_count_base *v10; // [rsp+48h] [rbp-51h]
  _BYTE v11[8]; // [rsp+50h] [rbp-49h] BYREF
  std::_Ref_count_base *v12; // [rsp+58h] [rbp-41h]
  _BYTE v13[32]; // [rsp+60h] [rbp-39h] BYREF
  _BYTE v14[64]; // [rsp+80h] [rbp-19h] BYREF
  _BYTE v15[32]; // [rsp+C0h] [rbp+27h] BYREF

  Spectre::Engine::Lockable::VerifyWriteAccess((Spectre::Engine::Engine *)((char *)this + 8));
  Spectre::Engine::Engine::WaitForAsyncDisplayPresents(this);
  Spectre::Engine::Engine::BeginCpuProfilerFrame(this);
  v2 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
         &v9,
         (char *)this + 464);
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v14,
    v2,
    (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
    819,
    (__int64)"FrameTick",
    (__int64)"FrameTick");
  std::string::string(v15, "FrameTick");
  CpuProfiler = Spectre::Engine::Engine::GetCpuProfiler(this, v11);
  std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(&v9, CpuProfiler);
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(v13, &v9, v15);
  if ( v10 )
    std::_Ref_count_base::_Decwref(v10);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  std::string::_Tidy_deallocate(v15);
  Spectre::Engine::Engine::ProcessNewResources(this);
  if ( Spectre::Engine::Engine::GetDeviceCount(this) > 1 )
  {
    Spectre::Engine::Engine::GetDevice(this);
    v4 = v9;
    if ( v9 )
    {
      Configuration = Spectre::Engine::Engine::GetConfiguration(this, 1);
      v6 = (*(__int64 (__fastcall **)(struct Spectre::Utils::IConfigurationManager *, __int64 *, __int64))(*(_QWORD *)Configuration + 72LL))(
             Configuration,
             Spectre::Engine::ConfigurationProperties::kRenderer_FrameLatencyMaximum,
             1);
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v4 + 224LL))(v4, v6);
    }
    if ( v10 )
      std::_Ref_count_base::_Decref(v10);
    Spectre::Engine::Engine::UpdateStatistics((Spectre::Utils::PerformanceLogger **)this);
    Spectre::Engine::Engine::UpdateFrameTime(this);
    (*(void (__fastcall **)(Spectre::Engine::Engine *))(*(_QWORD *)this + 72LL))(this);
    v7 = Spectre::Engine::Engine::GetConfiguration(this, 1);
    if ( (*(unsigned __int8 (__fastcall **)(struct Spectre::Utils::IConfigurationManager *, __int64 *, _QWORD))(*(_QWORD *)v7 + 64LL))(
           v7,
           Spectre::Engine::ConfigurationProperties::kRenderer_DisplayPerformanceStats,
           0) )
    {
      Spectre::Engine::Engine::GetSymbolManager(v8);
    }
    Spectre::Engine::Engine::RenderDisplays(this);
    Spectre::Engine::Engine::RemoveInvalidDevices(this);
    Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v13);
    Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v14);
    Spectre::Engine::Engine::UpdatePerformanceStats(this);
  }
  else
  {
    Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v13);
    Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v14);
  }
}

```

## disassembly

```asm
0x180032720  mov     [rsp-8+arg_8], rbx
0x180032725  mov     [rsp-8+arg_10], rdi
0x18003272a  push    rbp
0x18003272b  lea     rbp, [rsp-57h]
0x180032730  sub     rsp, 0F0h
0x180032737  mov     rax, cs:__security_cookie
0x18003273e  xor     rax, rsp
0x180032741  mov     [rbp+57h+var_10], rax
0x180032745  mov     rbx, rcx
0x180032748  add     rcx, 8; this
0x18003274c  call    ?VerifyWriteAccess@Lockable@Engine@Spectre@@QEBAXXZ; Spectre::Engine::Lockable::VerifyWriteAccess(void)
0x180032751  mov     rcx, rbx; this
0x180032754  call    ?WaitForAsyncDisplayPresents@Engine@1Spectre@@IEAAXXZ; Spectre::Engine::Engine::WaitForAsyncDisplayPresents(void)
0x180032759  mov     rcx, rbx; this
0x18003275c  call    ?BeginCpuProfilerFrame@Engine@1Spectre@@IEAAXXZ; Spectre::Engine::Engine::BeginCpuProfilerFrame(void)
0x180032761  lea     rdx, [rbx+1D0h]
0x180032768  lea     rcx, [rbp+57h+var_B0]
0x18003276c  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180032771  lea     rdi, aFrametick; "FrameTick"
0x180032778  mov     [rsp+0F0h+var_C8], rdi
0x18003277d  mov     [rsp+0F0h+var_D0], rdi
0x180032782  mov     r9d, 333h
0x180032788  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x18003278f  mov     rdx, rax
0x180032792  lea     rcx, [rbp+57h+var_70]
0x180032796  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x18003279b  nop
0x18003279c  mov     rdx, rdi
0x18003279f  lea     rcx, [rbp+57h+var_30]
0x1800327a3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1800327a8  nop
0x1800327a9  lea     rdx, [rbp+57h+var_A0]
0x1800327ad  mov     rcx, rbx
0x1800327b0  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x1800327b5  nop
0x1800327b6  mov     rdx, rax
0x1800327b9  lea     rcx, [rbp+57h+var_B0]
0x1800327bd  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x1800327c2  nop
0x1800327c3  lea     r8, [rbp+57h+var_30]
0x1800327c7  lea     rdx, [rbp+57h+var_B0]
0x1800327cb  lea     rcx, [rbp+57h+var_90]
0x1800327cf  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x1800327d4  nop
0x1800327d5  mov     rcx, [rbp+57h+var_A8]; this
0x1800327d9  test    rcx, rcx
0x1800327dc  jz      short loc_1800327E4
0x1800327de  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x1800327e3  nop
0x1800327e4  mov     rcx, [rbp+57h+var_98]; this
0x1800327e8  test    rcx, rcx
0x1800327eb  jz      short loc_1800327F3
0x1800327ed  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800327f2  nop
0x1800327f3  lea     rcx, [rbp+57h+var_30]
0x1800327f7  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800327fc  mov     rcx, rbx; this
0x1800327ff  call    ?ProcessNewResources@Engine@1Spectre@@IEAAXXZ; Spectre::Engine::Engine::ProcessNewResources(void)
0x180032804  mov     rcx, rbx; this
0x180032807  call    ?GetDeviceCount@Engine@1Spectre@@QEBAIXZ; Spectre::Engine::Engine::GetDeviceCount(void)
0x18003280c  cmp     eax, 1
0x18003280f  ja      short loc_180032829
0x180032811  lea     rcx, [rbp+57h+var_90]; this
0x180032815  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x18003281a  nop
0x18003281b  lea     rcx, [rbp+57h+var_70]; this
0x18003281f  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x180032824  jmp     loc_180032912
0x180032829  mov     r8d, 1
0x18003282f  lea     rdx, [rbp+57h+var_B0]
0x180032833  mov     rcx, rbx
0x180032836  call    ?GetDevice@Engine@1Spectre@@QEBA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@I@Z; Spectre::Engine::Engine::GetDevice(uint)
0x18003283b  nop
0x18003283c  mov     rdi, [rbp+57h+var_B0]
0x180032840  test    rdi, rdi
0x180032843  jz      short loc_180032886
0x180032845  mov     edx, 1; int
0x18003284a  mov     rcx, rbx; this
0x18003284d  call    ?GetConfiguration@Engine@1Spectre@@QEBAAEAVIConfigurationManager@Utils@2@H@Z; Spectre::Engine::Engine::GetConfiguration(int)
0x180032852  mov     r9, rax
0x180032855  mov     rcx, [rax]
0x180032858  mov     rax, [rcx+48h]
0x18003285c  mov     r8d, 1
0x180032862  lea     rdx, ?kRenderer_FrameLatencyMaximum@ConfigurationProperties@Engine@Spectre@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Spectre::Engine::ConfigurationProperties::kRenderer_FrameLatencyMaximum
0x180032869  mov     rcx, r9
0x18003286c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032871  mov     edx, eax
0x180032873  mov     rcx, [rdi]
0x180032876  mov     rax, [rcx+0E0h]
0x18003287d  mov     rcx, rdi
0x180032880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032885  nop
0x180032886  mov     rcx, [rbp+57h+var_A8]; this
0x18003288a  test    rcx, rcx
0x18003288d  jz      short loc_180032894
0x18003288f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180032894  mov     rcx, rbx; this
0x180032897  call    ?UpdateStatistics@Engine@1Spectre@@IEAAXXZ; Spectre::Engine::Engine::UpdateStatistics(void)
0x18003289c  mov     rcx, rbx; this
0x18003289f  call    ?UpdateFrameTime@Engine@1Spectre@@IEAAXXZ; Spectre::Engine::Engine::UpdateFrameTime(void)
0x1800328a4  mov     rax, [rbx]
0x1800328a7  mov     rcx, rbx
0x1800328aa  mov     rax, [rax+48h]
0x1800328ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328b3  mov     edx, 1; int
0x1800328b8  mov     rcx, rbx; this
0x1800328bb  call    ?GetConfiguration@Engine@1Spectre@@QEBAAEAVIConfigurationManager@Utils@2@H@Z; Spectre::Engine::Engine::GetConfiguration(int)
0x1800328c0  mov     r9, rax
0x1800328c3  mov     rcx, [rax]
0x1800328c6  mov     rax, [rcx+40h]
0x1800328ca  xor     r8d, r8d
0x1800328cd  lea     rdx, ?kRenderer_DisplayPerformanceStats@ConfigurationProperties@Engine@Spectre@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Spectre::Engine::ConfigurationProperties::kRenderer_DisplayPerformanceStats
0x1800328d4  mov     rcx, r9
0x1800328d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328dc  test    al, al
0x1800328de  jz      short loc_1800328E6
0x1800328e0  call    ?GetSymbolManager@Engine@1Spectre@@QEAAAEAVISymbolManager@12@XZ; Spectre::Engine::Engine::GetSymbolManager(void)
0x1800328e6  mov     rcx, rbx; this
0x1800328e9  call    ?RenderDisplays@Engine@1Spectre@@IEAAXXZ; Spectre::Engine::Engine::RenderDisplays(void)
0x1800328ee  mov     rcx, rbx; this
0x1800328f1  call    ?RemoveInvalidDevices@Engine@1Spectre@@IEAAXXZ; Spectre::Engine::Engine::RemoveInvalidDevices(void)
0x1800328f6  nop
0x1800328f7  lea     rcx, [rbp+57h+var_90]; this
0x1800328fb  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x180032900  nop
0x180032901  lea     rcx, [rbp+57h+var_70]; this
0x180032905  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x18003290a  mov     rcx, rbx; this
0x18003290d  call    ?UpdatePerformanceStats@Engine@1Spectre@@IEAAXXZ; Spectre::Engine::Engine::UpdatePerformanceStats(void)
0x180032912  mov     rcx, [rbp+57h+var_10]
0x180032916  xor     rcx, rsp; StackCookie
0x180032919  call    __security_check_cookie
0x18003291e  lea     r11, [rsp+0F0h+var_s0]
0x180032926  mov     rbx, [r11+18h]
0x18003292a  mov     rdi, [r11+20h]
0x18003292e  mov     rsp, r11
0x180032931  pop     rbp
0x180032932  retn
```
