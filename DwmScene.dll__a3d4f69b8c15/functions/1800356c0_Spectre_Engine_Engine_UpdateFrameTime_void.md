# Spectre::Engine::Engine::UpdateFrameTime(void)

- ea: `0x1800356c0`
- end: `0x180035916`
- name: `?UpdateFrameTime@Engine@1Spectre@@IEAAXXZ`
- size: `598`
- prototype: `void __fastcall(Spectre::Engine::Engine *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180032720`

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
- `0x180024420`
- `0x18002c8b0`
- `0x18002fadc`
- `0x180030700`
- `0x180032b10`
- `0x180032b58`
- `0x180032e10`
- `0x180033210`
- `0x1800356c0`
- `0x1800e7010`

## string_xrefs

- `0x180035712`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`
- `0x1800356fb`: `UpdateFrameTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
void __fastcall Spectre::Engine::Engine::UpdateFrameTime(Spectre::Engine::Engine *this)
{
  int v2; // eax
  __int64 CpuProfiler; // rax
  unsigned __int64 v4; // rsi
  __int64 v5; // rax
  __int64 v6; // rdi
  int v7; // ecx
  float v8; // xmm0_4
  float v9; // xmm1_4
  struct Spectre::Utils::IConfigurationManager *Configuration; // r14
  double v11; // xmm0_8
  unsigned int v12; // eax
  _BYTE v13[8]; // [rsp+40h] [rbp-79h] BYREF
  std::_Ref_count_base *v14; // [rsp+48h] [rbp-71h]
  __int64 v15; // [rsp+50h] [rbp-69h] BYREF
  std::_Ref_count_base *v16; // [rsp+58h] [rbp-61h]
  _BYTE v17[8]; // [rsp+60h] [rbp-59h] BYREF
  std::_Ref_count_base *v18; // [rsp+68h] [rbp-51h]
  _BYTE v19[32]; // [rsp+70h] [rbp-49h] BYREF
  _BYTE v20[64]; // [rsp+90h] [rbp-29h] BYREF
  _BYTE v21[32]; // [rsp+D0h] [rbp+17h] BYREF

  v2 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
         &v15,
         (char *)this + 464);
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v20,
    v2,
    (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
    640,
    (__int64)"UpdateFrameTime",
    (__int64)"UpdateFrameTime");
  std::string::string(v21, "UpdateFrameTime");
  CpuProfiler = Spectre::Engine::Engine::GetCpuProfiler(this, v17);
  std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v13, CpuProfiler);
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(v19, v13, v21);
  if ( v14 )
    std::_Ref_count_base::_Decwref(v14);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  std::string::_Tidy_deallocate(v21);
  anonymous_namespace_::GetFirstRenderOutput(&v15, this);
  if ( v15 )
    v4 = *(_QWORD *)(*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v15 + 328LL))(v15, v13);
  else
    v4 = 0x8000000000000000uLL;
  v5 = *((_QWORD *)this + 116);
  if ( v5 == 0x8000000000000000uLL || v4 == 0x8000000000000000uLL )
    v6 = 0;
  else
    v6 = v4 - v5;
  v7 = *((_DWORD *)this + 240);
  if ( v7 )
  {
    if ( v7 == 1 )
      *((_DWORD *)this + 234) = *((_DWORD *)this + 239);
  }
  else
  {
    v8 = Spectre::Engine::GetDurationSeconds<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(v6);
    *((float *)this + 234) = v8;
    v9 = *((float *)this + 238);
    if ( v8 > v9 )
      *((float *)this + 234) = v9;
  }
  Configuration = Spectre::Engine::Engine::GetConfiguration(this, 1);
  if ( (*(unsigned __int8 (__fastcall **)(struct Spectre::Utils::IConfigurationManager *, __int64 *, _QWORD))(*(_QWORD *)Configuration + 64LL))(
         Configuration,
         Spectre::Engine::ConfigurationProperties::kCpuProfiling_DisplayFrameTimings,
         0)
    || (*(unsigned __int8 (__fastcall **)(struct Spectre::Utils::IConfigurationManager *, __int64 *, _QWORD))(*(_QWORD *)Configuration + 64LL))(
         Configuration,
         Spectre::Engine::ConfigurationProperties::kGpuProfiling_DisplayFrameTimings,
         0) )
  {
    v11 = Spectre::Engine::GetDurationMilliseconds<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(v6);
    *((_DWORD *)this + *((unsigned int *)this + 268) + 248) = LODWORD(v11);
    *((_DWORD *)this + 268) = (*((_DWORD *)this + 268) + 1) % 0x14u;
    v12 = *((_DWORD *)this + 269) + 1;
    if ( v12 > 0x14 )
      v12 = 20;
    *((_DWORD *)this + 269) = v12;
    Spectre::Engine::Engine::GetSymbolManager((Spectre::Engine::Engine *)0x14);
  }
  *((_QWORD *)this + 116) = v4;
  *((_DWORD *)this + 92) = *((_DWORD *)this + 234);
  if ( v16 )
    std::_Ref_count_base::_Decref(v16);
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v19);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v20);
}

```

## disassembly

```asm
0x1800356c0  mov     [rsp-8+arg_8], rbx
0x1800356c5  mov     [rsp-8+arg_10], rsi
0x1800356ca  push    rbp
0x1800356cb  push    rdi
0x1800356cc  push    r14
0x1800356ce  lea     rbp, [rsp-47h]
0x1800356d3  sub     rsp, 100h
0x1800356da  mov     rax, cs:__security_cookie
0x1800356e1  xor     rax, rsp
0x1800356e4  mov     [rbp+57h+var_20], rax
0x1800356e8  mov     rbx, rcx
0x1800356eb  lea     rdx, [rcx+1D0h]
0x1800356f2  lea     rcx, [rbp+57h+var_C0]
0x1800356f6  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x1800356fb  lea     rdi, aUpdateframetim; "UpdateFrameTime"
0x180035702  mov     [rsp+110h+var_E8], rdi
0x180035707  mov     [rsp+110h+var_F0], rdi
0x18003570c  mov     r9d, 280h
0x180035712  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180035719  mov     rdx, rax
0x18003571c  lea     rcx, [rbp+57h+var_80]
0x180035720  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x180035725  nop
0x180035726  mov     rdx, rdi
0x180035729  lea     rcx, [rbp+57h+var_40]
0x18003572d  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180035732  nop
0x180035733  lea     rdx, [rbp+57h+var_B0]
0x180035737  mov     rcx, rbx
0x18003573a  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x18003573f  nop
0x180035740  mov     rdx, rax
0x180035743  lea     rcx, [rbp+57h+var_D0]
0x180035747  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x18003574c  nop
0x18003574d  lea     r8, [rbp+57h+var_40]
0x180035751  lea     rdx, [rbp+57h+var_D0]
0x180035755  lea     rcx, [rbp+57h+var_A0]
0x180035759  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x18003575e  nop
0x18003575f  mov     rcx, [rbp+57h+var_C8]; this
0x180035763  test    rcx, rcx
0x180035766  jz      short loc_18003576E
0x180035768  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18003576d  nop
0x18003576e  mov     rcx, [rbp+57h+var_A8]; this
0x180035772  test    rcx, rcx
0x180035775  jz      short loc_18003577D
0x180035777  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003577c  nop
0x18003577d  lea     rcx, [rbp+57h+var_40]
0x180035781  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180035786  mov     rdx, rbx
0x180035789  lea     rcx, [rbp+57h+var_C0]
0x18003578d  call    _anonymous_namespace___GetFirstRenderOutput
0x180035792  nop
0x180035793  mov     rdi, 8000000000000000h
0x18003579d  mov     rcx, [rbp+57h+var_C0]
0x1800357a1  test    rcx, rcx
0x1800357a4  jz      short loc_1800357BE
0x1800357a6  mov     rax, [rcx]
0x1800357a9  lea     rdx, [rbp+57h+var_D0]
0x1800357ad  mov     rax, [rax+148h]
0x1800357b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800357b9  mov     rsi, [rax]
0x1800357bc  jmp     short loc_1800357C1
0x1800357be  mov     rsi, rdi
0x1800357c1  mov     rax, [rbx+3A0h]
0x1800357c8  cmp     rax, rdi
0x1800357cb  jz      short loc_1800357DA
0x1800357cd  cmp     rsi, rdi
0x1800357d0  jz      short loc_1800357DA
0x1800357d2  mov     rdi, rsi
0x1800357d5  sub     rdi, rax
0x1800357d8  jmp     short loc_1800357DC
0x1800357da  xor     edi, edi
0x1800357dc  mov     ecx, [rbx+3C0h]
0x1800357e2  test    ecx, ecx
0x1800357e4  jz      short loc_1800357F9
0x1800357e6  cmp     ecx, 1
0x1800357e9  jnz     short loc_18003581E
0x1800357eb  mov     eax, [rbx+3BCh]
0x1800357f1  mov     [rbx+3A8h], eax
0x1800357f7  jmp     short loc_18003581E
0x1800357f9  mov     rcx, rdi
0x1800357fc  call    ??$GetDurationSeconds@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Engine@Spectre@@YAMV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Z; Spectre::Engine::GetDurationSeconds<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::chrono::duration<__int64,std::ratio<1,1000000000>>)
0x180035801  movss   dword ptr [rbx+3A8h], xmm0
0x180035809  movss   xmm1, dword ptr [rbx+3B8h]
0x180035811  comiss  xmm0, xmm1
0x180035814  jbe     short loc_18003581E
0x180035816  movss   dword ptr [rbx+3A8h], xmm1
0x18003581e  mov     edx, 1; int
0x180035823  mov     rcx, rbx; this
0x180035826  call    ?GetConfiguration@Engine@1Spectre@@QEBAAEAVIConfigurationManager@Utils@2@H@Z; Spectre::Engine::Engine::GetConfiguration(int)
0x18003582b  mov     r14, rax
0x18003582e  mov     rcx, [rax]
0x180035831  mov     rax, [rcx+40h]
0x180035835  xor     r8d, r8d
0x180035838  lea     rdx, ?kCpuProfiling_DisplayFrameTimings@ConfigurationProperties@Engine@Spectre@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Spectre::Engine::ConfigurationProperties::kCpuProfiling_DisplayFrameTimings
0x18003583f  mov     rcx, r14
0x180035842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035847  test    al, al
0x180035849  jnz     short loc_1800358C1
0x18003584b  mov     rcx, [r14]
0x18003584e  mov     rax, [rcx+40h]
0x180035852  xor     r8d, r8d
0x180035855  lea     rdx, ?kGpuProfiling_DisplayFrameTimings@ConfigurationProperties@Engine@Spectre@@3V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@B; std::wstring const Spectre::Engine::ConfigurationProperties::kGpuProfiling_DisplayFrameTimings
0x18003585c  mov     rcx, r14
0x18003585f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035864  test    al, al
0x180035866  jnz     short loc_1800358C1
0x180035868  mov     [rbx+3A0h], rsi
0x18003586f  mov     eax, [rbx+3A8h]
0x180035875  mov     [rbx+170h], eax
0x18003587b  mov     rcx, [rbp+57h+var_B8]; this
0x18003587f  test    rcx, rcx
0x180035882  jz      short loc_18003588A
0x180035884  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180035889  nop
0x18003588a  lea     rcx, [rbp+57h+var_A0]; this
0x18003588e  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x180035893  nop
0x180035894  lea     rcx, [rbp+57h+var_80]; this
0x180035898  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x18003589d  mov     rcx, [rbp+57h+var_20]
0x1800358a1  xor     rcx, rsp; StackCookie
0x1800358a4  call    __security_check_cookie
0x1800358a9  lea     r11, [rsp+110h+var_10]
0x1800358b1  mov     rbx, [r11+28h]
0x1800358b5  mov     rsi, [r11+30h]
0x1800358b9  mov     rsp, r11
0x1800358bc  pop     r14
0x1800358be  pop     rdi
0x1800358bf  pop     rbp
0x1800358c0  retn
0x1800358c1  mov     rcx, rdi
0x1800358c4  call    ??$GetDurationMilliseconds@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Engine@Spectre@@YAMV?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@chrono@std@@@Z; Spectre::Engine::GetDurationMilliseconds<std::chrono::duration<__int64,std::ratio<1,1000000000>>>(std::chrono::duration<__int64,std::ratio<1,1000000000>>)
0x1800358c9  mov     eax, [rbx+430h]
0x1800358cf  movss   dword ptr [rbx+rax*4+3E0h], xmm0
0x1800358d8  mov     ecx, [rbx+430h]
0x1800358de  inc     ecx
0x1800358e0  mov     eax, 0CCCCCCCDh
0x1800358e5  mul     ecx
0x1800358e7  shr     edx, 4
0x1800358ea  lea     eax, [rdx+rdx*4]
0x1800358ed  shl     eax, 2
0x1800358f0  sub     ecx, eax
0x1800358f2  mov     [rbx+430h], ecx
0x1800358f8  mov     eax, [rbx+434h]
0x1800358fe  inc     eax
0x180035900  mov     ecx, 14h; this
0x180035905  cmp     eax, ecx
0x180035907  cmova   eax, ecx
0x18003590a  mov     [rbx+434h], eax
0x180035910  call    ?GetSymbolManager@Engine@1Spectre@@QEAAAEAVISymbolManager@12@XZ; Spectre::Engine::Engine::GetSymbolManager(void)
```
