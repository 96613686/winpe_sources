# Spectre::Engine::Engine::RenderDisplays(void)

- ea: `0x180034c38`
- end: `0x180034d76`
- name: `?RenderDisplays@Engine@1Spectre@@IEAAXXZ`
- size: `318`
- prototype: `void __fastcall(Spectre::Engine::Engine *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180032720`

## callees

- `0x18000ca90`
- `0x18001128c`
- `0x1800112c4`
- `0x180011f64`
- `0x180012ba8`
- `0x180012c88`
- `0x180012df8`
- `0x180016324`
- `0x18001fba8`
- `0x18001fca8`
- `0x18002fadc`
- `0x180030700`
- `0x180032b58`
- `0x18003384c`
- `0x180034c38`
- `0x1800534f0`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x180034d25`
- `msvcp_win!_Mtx_unlock` at `0x180034d25`

## string_xrefs

- `0x180034c86`: `onecoreuap\windows\dwm\spectre\engine\products\components\nativerenderer\cpp\source\engine\engine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall Spectre::Engine::Engine::RenderDisplays(Spectre::Engine::Engine *this)
{
  int v2; // eax
  __int64 CpuProfiler; // rax
  __int64 ***v4; // rdi
  __int64 **i; // rbx
  __int64 *v6; // rsi
  struct _Mtx_internal_imp_t *v7; // r14
  _BYTE v8[8]; // [rsp+40h] [rbp-89h] BYREF
  std::_Ref_count_base *v9; // [rsp+48h] [rbp-81h]
  _BYTE v10[8]; // [rsp+50h] [rbp-79h] BYREF
  std::_Ref_count_base *v11; // [rsp+58h] [rbp-71h]
  _BYTE v12[32]; // [rsp+60h] [rbp-69h] BYREF
  _BYTE v13[64]; // [rsp+80h] [rbp-49h] BYREF
  _BYTE v14[32]; // [rsp+C0h] [rbp-9h] BYREF

  v2 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
         v8,
         (char *)this + 464);
  Spectre::Utils::PerformanceScope::PerformanceScope(
    (unsigned int)v13,
    v2,
    (unsigned int)"onecoreuap\\windows\\dwm\\spectre\\engine\\products\\components\\nativerenderer\\cpp\\source\\engine\\engine.cpp",
    898,
    (__int64)"RenderDisplays",
    (__int64)"RenderDisplays");
  std::string::string(v14, "RenderDisplays");
  CpuProfiler = Spectre::Engine::Engine::GetCpuProfiler(this, v10);
  std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(v8, CpuProfiler);
  Spectre::Engine::CpuProfilerScope::CpuProfilerScope(v12, v8, v14);
  if ( v9 )
    std::_Ref_count_base::_Decwref(v9);
  if ( v11 )
    std::_Ref_count_base::_Decref(v11);
  std::string::_Tidy_deallocate(v14);
  v4 = (__int64 ***)*((_QWORD *)this + 21);
  for ( i = *v4; i != (__int64 **)v4; i = (__int64 **)*i )
  {
    v6 = i[2];
    v7 = (struct _Mtx_internal_imp_t *)(v6 + 16);
    std::_Mutex_base::lock((std::_Mutex_base *)(v6 + 16));
    LODWORD(v6) = *((_DWORD *)v6 + 8);
    _Mtx_unlock(v7);
    if ( (_DWORD)v6 == 1 )
      Spectre::Engine::Display::Render((Spectre::Engine::Display *)i[2]);
  }
  Spectre::Engine::Engine::LogInstanceCounts(this);
  Spectre::Engine::CpuProfilerScope::~CpuProfilerScope((Spectre::Engine::CpuProfilerScope *)v12);
  Spectre::Utils::PerformanceScope::~PerformanceScope((Spectre::Utils::PerformanceScope *)v13);
}

```

## disassembly

```asm
0x180034c38  push    rbp
0x180034c3a  push    rbx
0x180034c3b  push    rsi
0x180034c3c  push    rdi
0x180034c3d  push    r14
0x180034c3f  push    r15
0x180034c41  lea     rbp, [rsp-2Fh]
0x180034c46  sub     rsp, 0F8h
0x180034c4d  mov     rax, cs:__security_cookie
0x180034c54  xor     rax, rsp
0x180034c57  mov     [rbp+57h+var_40], rax
0x180034c5b  mov     r15, rcx
0x180034c5e  lea     rdx, [rcx+1D0h]
0x180034c65  lea     rcx, [rsp+120h+var_E0]
0x180034c6a  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180034c6f  lea     rbx, aRenderdisplays; "RenderDisplays"
0x180034c76  mov     [rsp+120h+var_F8], rbx
0x180034c7b  mov     [rsp+120h+var_100], rbx
0x180034c80  mov     r9d, 382h
0x180034c86  lea     r8, aOnecoreuapWind_31; "onecoreuap\\windows\\dwm\\spectre\\engi"...
0x180034c8d  mov     rdx, rax
0x180034c90  lea     rcx, [rbp+57h+var_A0]
0x180034c94  call    ??0PerformanceScope@Utils@Spectre@@QEAA@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@PEBDH11_N@Z; Spectre::Utils::PerformanceScope::PerformanceScope(std::shared_ptr<Spectre::Utils::PerformanceLogger>,char const *,int,char const *,char const *,bool)
0x180034c99  nop
0x180034c9a  mov     rdx, rbx
0x180034c9d  lea     rcx, [rbp+57h+var_60]
0x180034ca1  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180034ca6  nop
0x180034ca7  lea     rdx, [rbp+57h+var_D0]
0x180034cab  mov     rcx, r15
0x180034cae  call    ?GetCpuProfiler@Engine@1Spectre@@QEBA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetCpuProfiler(void)
0x180034cb3  nop
0x180034cb4  mov     rdx, rax
0x180034cb7  lea     rcx, [rsp+120h+var_E0]
0x180034cbc  call    ??$?0VScene@Engine@Spectre@@$0A@@?$weak_ptr@VScene@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VScene@Engine@Spectre@@@1@@Z; std::weak_ptr<Spectre::Engine::Scene>::weak_ptr<Spectre::Engine::Scene>(std::shared_ptr<Spectre::Engine::Scene> const &)
0x180034cc1  nop
0x180034cc2  lea     r8, [rbp+57h+var_60]
0x180034cc6  lea     rdx, [rsp+120h+var_E0]
0x180034ccb  lea     rcx, [rbp+57h+var_C0]
0x180034ccf  call    ??0CpuProfilerScope@Engine@Spectre@@QEAA@AEBV?$weak_ptr@VCpuProfiler@Engine@Spectre@@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@4@@Z; Spectre::Engine::CpuProfilerScope::CpuProfilerScope(std::weak_ptr<Spectre::Engine::CpuProfiler> const &,std::string const &)
0x180034cd4  nop
0x180034cd5  mov     rcx, [rsp+120h+var_D8]; this
0x180034cda  test    rcx, rcx
0x180034cdd  jz      short loc_180034CE5
0x180034cdf  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x180034ce4  nop
0x180034ce5  mov     rcx, [rbp+57h+var_C8]; this
0x180034ce9  test    rcx, rcx
0x180034cec  jz      short loc_180034CF4
0x180034cee  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180034cf3  nop
0x180034cf4  lea     rcx, [rbp+57h+var_60]
0x180034cf8  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180034cfd  mov     rdi, [r15+0A8h]
0x180034d04  mov     rbx, [rdi]
0x180034d07  cmp     rbx, rdi
0x180034d0a  jz      short loc_180034D3E
0x180034d0c  mov     rsi, [rbx+10h]
0x180034d10  lea     r14, [rsi+80h]
0x180034d17  mov     rcx, r14; this
0x180034d1a  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180034d1f  mov     esi, [rsi+20h]
0x180034d22  mov     rcx, r14; _Mtx_t
0x180034d25  call    cs:__imp__Mtx_unlock
0x180034d2b  cmp     esi, 1
0x180034d2e  jnz     short loc_180034D39
0x180034d30  mov     rcx, [rbx+10h]; this
0x180034d34  call    ?Render@Display@Engine@Spectre@@QEAAXXZ; Spectre::Engine::Display::Render(void)
0x180034d39  mov     rbx, [rbx]
0x180034d3c  jmp     short loc_180034D07
0x180034d3e  mov     rcx, r15; this
0x180034d41  call    ?LogInstanceCounts@Engine@1Spectre@@AEBAXXZ; Spectre::Engine::Engine::LogInstanceCounts(void)
0x180034d46  nop
0x180034d47  lea     rcx, [rbp+57h+var_C0]; this
0x180034d4b  call    ??1CpuProfilerScope@Engine@Spectre@@QEAA@XZ; Spectre::Engine::CpuProfilerScope::~CpuProfilerScope(void)
0x180034d50  nop
0x180034d51  lea     rcx, [rbp+57h+var_A0]; this
0x180034d55  call    ??1PerformanceScope@Utils@Spectre@@QEAA@XZ; Spectre::Utils::PerformanceScope::~PerformanceScope(void)
0x180034d5a  mov     rcx, [rbp+57h+var_40]
0x180034d5e  xor     rcx, rsp; StackCookie
0x180034d61  call    __security_check_cookie
0x180034d66  add     rsp, 0F8h
0x180034d6d  pop     r15
0x180034d6f  pop     r14
0x180034d71  pop     rdi
0x180034d72  pop     rsi
0x180034d73  pop     rbx
0x180034d74  pop     rbp
0x180034d75  retn
```
