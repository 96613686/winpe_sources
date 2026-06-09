# Spectre::Engine::ViewerEngine::PreRenderScene(std::shared_ptr<Spectre::Engine::Scene> const &,std::shared_ptr<Spectre::Engine::RenderDevice> const &,std::shared_ptr<Spectre::Engine::IRenderOutput> const &)

- ea: `0x180061aa0`
- end: `0x180061d1f`
- name: `?PreRenderScene@ViewerEngine@Engine@Spectre@@MEAAXAEBV?$shared_ptr@VScene@Engine@Spectre@@@std@@AEBV?$shared_ptr@VRenderDevice@Engine@Spectre@@@5@AEBV?$shared_ptr@VIRenderOutput@Engine@Spectre@@@5@@Z`
- size: `639`
- prototype: `__int64 __fastcall(Spectre::Engine::Engine *this)`
- caller_count: `0`
- callee_count: `25`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000ca90`
- `0x18001128c`
- `0x1800112c4`
- `0x180011f64`
- `0x180012ba8`
- `0x180012df8`
- `0x180016324`
- `0x180018318`
- `0x18001fba8`
- `0x18001fca8`
- `0x18002fadc`
- `0x180030700`
- `0x180032b10`
- `0x180032b58`
- `0x180032da0`
- `0x18004cda0`
- `0x18005bd54`
- `0x180061aa0`
- `0x1800622a8`
- `0x180063bbc`
- `0x1800643e0`
- `0x1800659a0`
- `0x180066990`
- `0x18006741c`
- `0x1800e7010`

## string_xrefs

- `0x180061af9`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\viewerengine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
void __fastcall Spectre::Engine::ViewerEngine::PreRenderScene(
        Spectre::Engine::Engine *this,
        _QWORD *a2,
        struct Spectre::Engine::RenderDevice **a3,
        struct Spectre::Engine::IRenderOutput **a4)
{
  int v8; // eax
  __int64 CpuProfiler; // rax
  struct Spectre::Utils::IConfigurationManager *Configuration; // rdi
  Spectre::Engine::ViewerEngine *v11; // rcx
  __int64 v12; // r8
  char v13; // al
  char v14; // bl
  double v15; // xmm0_8
  __int64 v16; // rbx
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rax
  __int64 v20; // r8
  int DeviceIndex; // eax
  __int64 v22; // [rsp+40h] [rbp-C0h] BYREF
  std::_Ref_count_base *v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h] BYREF
  std::_Ref_count_base *v25; // [rsp+58h] [rbp-A8h]
  _BYTE v26[8]; // [rsp+60h] [rbp-A0h] BYREF
  std::_Ref_count_base *v27; // [rsp+68h] [rbp-98h]
  _BYTE v28[24]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[40]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v30[64]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v31[32]; // [rsp+F0h] [rbp-10h] BYREF

  v8 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
         &v24,
         (char *)this + 464);
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v30,
    v8,
    (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\"
                  "viewerengine.cpp",
    1570,
    (__int64)"PreRenderScene",
    (__int64)"PreRenderScene");
  std::string::string(v31, "PreRenderScene");
  CpuProfiler = Spectre::Engine::Engine::GetCpuProfiler(this, v26);
  std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(&v22, CpuProfiler);
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(v28, &v22, v31);
  if ( v23 )
    std::_Ref_count_base::_Decwref(v23);
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
  std::string::_Tidy_deallocate(v31);
  Configuration = Spectre::Engine::Engine::GetConfiguration(this, *(_DWORD *)(*a2 + 112LL));
  Spectre::Engine::ViewerEngine::UpdateRendererSettings(v11, *a3, *a4, Configuration);
  LOBYTE(v12) = 1;
  (*(void (__fastcall **)(struct Spectre::Utils::IConfigurationManager *, __int64 *, __int64))(*(_QWORD *)Configuration
                                                                                             + 64LL))(
    Configuration,
    Spectre::Engine::ConfigurationProperties::kGroundPlane_BottomVisible,
    v12);
  v14 = v13;
  v15 = (*(double (__fastcall **)(struct Spectre::Utils::IConfigurationManager *, __int64 *))(*(_QWORD *)Configuration
                                                                                            + 88LL))(
          Configuration,
          Spectre::Engine::ConfigurationProperties::kGroundPlane_BottomGridOpacity);
  Spectre::Engine::ViewerEngine::UpdateBackground(this, a2, v14, *(float *)&v15);
  (*(void (__fastcall **)(struct Spectre::Engine::RenderDevice *))(*(_QWORD *)*a3 + 120LL))(*a3);
  *((_BYTE *)this + 1457) = (*(__int64 (__fastcall **)(struct Spectre::Utils::IConfigurationManager *, __int64 *, _QWORD))(*(_QWORD *)Configuration + 64LL))(
                              Configuration,
                              Spectre::Engine::ConfigurationProperties::kShader_DiagnosticsEnabled,
                              0);
  Spectre::Engine::ViewerEngine::UpdateFrameConstants(this);
  Spectre::Engine::ViewerEngine::UpdateDebugConstants(this, *a4, *(_DWORD *)(*a2 + 112LL));
  Spectre::Engine::ViewerEngine::UpdatePipelineConstants((__int64)this, (__int64)a3, (__int64)a4, a2);
  v16 = *((_QWORD *)this + 64);
  v17 = std::string::string(v29, Spectre::Engine::StandardShaderExtension::kShaderFamilyName);
  Spectre::Engine::ShaderManager::GetShaderFamily(v16, &v24, v17);
  LOBYTE(v18) = *((_BYTE *)this + 1457);
  Spectre::Engine::ShaderFamily::SetOption(v24, Spectre::Engine::ShaderConstants::kOption_Diagnostics, v18);
  v19 = std::string::string(v31, Spectre::Engine::UnlitShaderExtension::kShaderFamilyName);
  Spectre::Engine::ShaderManager::GetShaderFamily(v16, &v22, v19);
  LOBYTE(v20) = *((_BYTE *)this + 1457);
  Spectre::Engine::ShaderFamily::SetOption(v22, Spectre::Engine::ShaderConstants::kOption_Diagnostics, v20);
  DeviceIndex = Spectre::Engine::Engine::GetDeviceIndex(this);
  Spectre::Engine::ViewerEngine::UpdatePlanarReflection(this, a2, DeviceIndex, a4);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  if ( v25 )
    std::_Ref_count_base::_Decref(v25);
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v28);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v30);
}

```

## disassembly

```asm
0x180061aa0  push    rbp
0x180061aa2  push    rbx
0x180061aa3  push    rsi
0x180061aa4  push    rdi
0x180061aa5  push    r12
0x180061aa7  push    r14
0x180061aa9  push    r15
0x180061aab  lea     rbp, [rsp-20h]
0x180061ab0  sub     rsp, 120h
0x180061ab7  mov     rax, cs:__security_cookie
0x180061abe  xor     rax, rsp
0x180061ac1  mov     [rbp+50h+var_40], rax
0x180061ac5  mov     r12, r9
0x180061ac8  mov     r15, r8
0x180061acb  mov     r14, rdx
0x180061ace  mov     rsi, rcx
0x180061ad1  lea     rdx, [rcx+1D0h]
0x180061ad8  lea     rcx, [rsp+150h+var_100]
0x180061add  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180061ae2  lea     rbx, aPrerenderscene; "PreRenderScene"
0x180061ae9  mov     [rsp+150h+var_128], rbx
0x180061aee  mov     [rsp+150h+var_130], rbx
0x180061af3  mov     r9d, 622h
0x180061af9  lea     r8, aOnecoreuapWind_36; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180061b00  mov     rdx, rax
0x180061b03  lea     rcx, [rbp+50h+var_A0]
0x180061b07  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x180061b0c  nop
0x180061b0d  mov     rdx, rbx
0x180061b10  lea     rcx, [rbp+50h+var_60]
0x180061b14  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180061b19  nop
0x180061b1a  lea     rdx, [rsp+150h+var_F0]
0x180061b1f  mov     rcx, rsi
0x180061b22  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x180061b27  nop
0x180061b28  mov     rdx, rax
0x180061b2b  lea     rcx, [rsp+150h+var_110]
0x180061b30  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x180061b35  nop
0x180061b36  lea     r8, [rbp+50h+var_60]
0x180061b3a  lea     rdx, [rsp+150h+var_110]
0x180061b3f  lea     rcx, [rsp+150h+var_E0]
0x180061b44  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x180061b49  nop
0x180061b4a  mov     rcx, [rsp+150h+var_108]; this
0x180061b4f  test    rcx, rcx
0x180061b52  jz      short loc_180061B5A
0x180061b54  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180061b59  nop
0x180061b5a  mov     rcx, [rsp+150h+var_E8]; this
0x180061b5f  test    rcx, rcx
0x180061b62  jz      short loc_180061B6A
0x180061b64  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180061b69  nop
0x180061b6a  lea     rcx, [rbp+50h+var_60]
0x180061b6e  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180061b73  mov     rdx, [r14]
0x180061b76  mov     edx, [rdx+70h]; int
0x180061b79  mov     rcx, rsi; this
0x180061b7c  call    ?GetConfiguration@Engine@1Spectre@@QEBAAEAVIConfigurationManager@Utils@2@H@Z; Spectre::Engine::Engine::GetConfiguration(int)
0x180061b81  mov     rdi, rax
0x180061b84  mov     r9, rax; struct Spectre::Utils::IConfigurationManager *
0x180061b87  mov     r8, [r12]; struct Spectre::Engine::IRenderOutput *
0x180061b8b  mov     rdx, [r15]; struct Spectre::Engine::RenderDevice *
0x180061b8e  call    ?UpdateRendererSettings@ViewerEngine@Engine@Spectre@@AEAAXAEAVRenderDevice@23@AEAVIRenderOutput@23@AEAVIConfigurationManager@Utils@3@@Z; Spectre::Engine::ViewerEngine::UpdateRendererSettings(Spectre::Engine::RenderDevice &,Spectre::Engine::IRenderOutput &,Spectre::Utils::IConfigurationManager &)
0x180061b93  mov     rcx, [rdi]
0x180061b96  mov     rax, [rcx+40h]
0x180061b9a  mov     r8b, 1
0x180061b9d  lea     rdx, ?kGroundPlane_BottomVisible@ConfigurationProperties@Engine@Spectre@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Spectre::Engine::ConfigurationProperties::kGroundPlane_BottomVisible
0x180061ba4  mov     rcx, rdi
0x180061ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061bac  mov     bl, al
0x180061bae  mov     rcx, [rdi]
0x180061bb1  mov     rax, [rcx+58h]
0x180061bb5  movss   xmm2, cs:__real@3f800000
0x180061bbd  lea     rdx, ?kGroundPlane_BottomGridOpacity@ConfigurationProperties@Engine@Spectre@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Spectre::Engine::ConfigurationProperties::kGroundPlane_BottomGridOpacity
0x180061bc4  mov     rcx, rdi
0x180061bc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061bcc  movaps  xmm3, xmm0
0x180061bcf  mov     r8b, bl
0x180061bd2  mov     rdx, r14
0x180061bd5  mov     rcx, rsi; this
0x180061bd8  call    ?UpdateBackground@ViewerEngine@Engine@Spectre@@AEAAXAEBV?$shared_ptr@VScene@Engine@Spectre@@@std@@_NM@Z; Spectre::Engine::ViewerEngine::UpdateBackground(std::shared_ptr<Spectre::Engine::Scene> const &,bool,float)
0x180061bdd  mov     rcx, [r15]
0x180061be0  mov     rax, [rcx]
0x180061be3  mov     rax, [rax+78h]
0x180061be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061bec  mov     rax, [rdi]
0x180061bef  xor     r8d, r8d
0x180061bf2  lea     rdx, ?kShader_DiagnosticsEnabled@ConfigurationProperties@Engine@Spectre@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Spectre::Engine::ConfigurationProperties::kShader_DiagnosticsEnabled
0x180061bf9  mov     rcx, rdi
0x180061bfc  mov     rax, [rax+40h]
0x180061c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180061c05  mov     [rsi+5B1h], al
0x180061c0b  mov     rcx, rsi; this
0x180061c0e  call    ?UpdateFrameConstants@ViewerEngine@Engine@Spectre@@AEAAXXZ; Spectre::Engine::ViewerEngine::UpdateFrameConstants(void)
0x180061c13  mov     r8, [r14]
0x180061c16  mov     r8d, [r8+70h]; int
0x180061c1a  mov     rdx, [r12]; struct Spectre::Engine::IRenderOutput *
0x180061c1e  mov     rcx, rsi; this
0x180061c21  call    ?UpdateDebugConstants@ViewerEngine@Engine@Spectre@@AEAAXAEAVIRenderOutput@23@H@Z; Spectre::Engine::ViewerEngine::UpdateDebugConstants(Spectre::Engine::IRenderOutput &,int)
0x180061c26  mov     r9, r14
0x180061c29  mov     r8, r12
0x180061c2c  mov     rdx, r15
0x180061c2f  mov     rcx, rsi
0x180061c32  call    ?UpdatePipelineConstants@ViewerEngine@Engine@Spectre@@AEAAXAEBV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@AEBV?$shared_ptr@VIRenderOutput@Engine@Spectre@@@5@AEBV?$shared_ptr@VScene@Engine@Spectre@@@5@@Z; Spectre::Engine::ViewerEngine::UpdatePipelineConstants(std::shared_ptr<Spectre::Engine::RenderDevice> const &,std::shared_ptr<Spectre::Engine::IRenderOutput> const &,std::shared_ptr<Spectre::Engine::Scene> const &)
0x180061c37  mov     rbx, [rsi+200h]
0x180061c3e  lea     rdx, ?kShaderFamilyName@StandardShaderExtension@Engine@Spectre@@2V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@B; std::string const Spectre::Engine::StandardShaderExtension::kShaderFamilyName
0x180061c45  lea     rcx, [rbp+50h+var_C8]
0x180061c49  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180061c4e  mov     r8, rax
0x180061c51  lea     rdx, [rsp+150h+var_100]
0x180061c56  mov     rcx, rbx
0x180061c59  call    ?GetShaderFamily@ShaderManager@Engine@Spectre@@QEAA?AV?$shared_ptr@VShaderFamily@Engine@Spectre@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Spectre::Engine::ShaderManager::GetShaderFamily(std::string)
0x180061c5e  nop
0x180061c5f  mov     r8b, [rsi+5B1h]
0x180061c66  lea     rdx, ?kOption_Diagnostics@ShaderConstants@Engine@Spectre@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@B; std::string const Spectre::Engine::ShaderConstants::kOption_Diagnostics
0x180061c6d  mov     rcx, [rsp+150h+var_100]
0x180061c72  call    ?SetOption@ShaderFamily@Engine@Spectre@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; Spectre::Engine::ShaderFamily::SetOption(std::string const &,bool)
0x180061c77  lea     rdx, ?kShaderFamilyName@UnlitShaderExtension@Engine@Spectre@@2V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@B; std::string const Spectre::Engine::UnlitShaderExtension::kShaderFamilyName
0x180061c7e  lea     rcx, [rbp+50h+var_60]
0x180061c82  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@AEBV01@@Z; std::string::string(std::string const &)
0x180061c87  mov     r8, rax
0x180061c8a  lea     rdx, [rsp+150h+var_110]
0x180061c8f  mov     rcx, rbx
0x180061c92  call    ?GetShaderFamily@ShaderManager@Engine@Spectre@@QEAA?AV?$shared_ptr@VShaderFamily@Engine@Spectre@@@std@@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@5@@Z; Spectre::Engine::ShaderManager::GetShaderFamily(std::string)
0x180061c97  nop
0x180061c98  mov     r8b, [rsi+5B1h]
0x180061c9f  lea     rdx, ?kOption_Diagnostics@ShaderConstants@Engine@Spectre@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@B; std::string const Spectre::Engine::ShaderConstants::kOption_Diagnostics
0x180061ca6  mov     rcx, [rsp+150h+var_110]
0x180061cab  call    ?SetOption@ShaderFamily@Engine@Spectre@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@_N@Z; Spectre::Engine::ShaderFamily::SetOption(std::string const &,bool)
0x180061cb0  mov     rdx, r15
0x180061cb3  mov     rcx, rsi; this
0x180061cb6  call    ?GetDeviceIndex@Engine@1Spectre@@QEAAIAEBV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@@Z; Spectre::Engine::Engine::GetDeviceIndex(std::shared_ptr<Spectre::Engine::RenderDevice> const &)
0x180061cbb  mov     r9, r12
0x180061cbe  mov     r8d, eax
0x180061cc1  mov     rdx, r14
0x180061cc4  mov     rcx, rsi; this
0x180061cc7  call    ?UpdatePlanarReflection@ViewerEngine@Engine@Spectre@@AEAAXAEBV?$shared_ptr@VScene@Engine@Spectre@@@std@@IAEBV?$shared_ptr@VIRenderOutput@Engine@Spectre@@@5@@Z; Spectre::Engine::ViewerEngine::UpdatePlanarReflection(std::shared_ptr<Spectre::Engine::Scene> const &,uint,std::shared_ptr<Spectre::Engine::IRenderOutput> const &)
0x180061ccc  nop
0x180061ccd  mov     rcx, [rsp+150h+var_108]; this
0x180061cd2  test    rcx, rcx
0x180061cd5  jz      short loc_180061CDD
0x180061cd7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180061cdc  nop
0x180061cdd  mov     rcx, [rsp+150h+var_F8]; this
0x180061ce2  test    rcx, rcx
0x180061ce5  jz      short loc_180061CED
0x180061ce7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180061cec  nop
0x180061ced  lea     rcx, [rsp+150h+var_E0]; this
0x180061cf2  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x180061cf7  nop
0x180061cf8  lea     rcx, [rbp+50h+var_A0]; this
0x180061cfc  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x180061d01  mov     rcx, [rbp+50h+var_40]
0x180061d05  xor     rcx, rsp; StackCookie
0x180061d08  call    __security_check_cookie
0x180061d0d  add     rsp, 120h
0x180061d14  pop     r15
0x180061d16  pop     r14
0x180061d18  pop     r12
0x180061d1a  pop     rdi
0x180061d1b  pop     rsi
0x180061d1c  pop     rbx
0x180061d1d  pop     rbp
0x180061d1e  retn
```
