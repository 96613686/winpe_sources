# Spectre::Engine::Engine::Engine(Spectre::Engine::Lockable::ThreadingMode,std::shared_ptr<Spectre::Utils::PerformanceLogger>,std::shared_ptr<Spectre::Utils::ITelemetryManager>,std::shared_ptr<Spectre::Utils::ITelemetryTraceLogger>)

- ea: `0x18002fb58`
- end: `0x18002ff2a`
- name: `??0Engine@0Spectre@@IEAA@W4ThreadingMode@Lockable@01@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@V?$shared_ptr@VITelemetryManager@Utils@Spectre@@@5@V?$shared_ptr@VITelemetryTraceLogger@Utils@Spectre@@@5@@Z`
- size: `978`
- prototype: ``
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config`

## callers

- `0x18005e3d8`

## callees

- `0x18000ca90`
- `0x18000d678`
- `0x18000e8d0`
- `0x18001128c`
- `0x1800121f4`
- `0x180012cd0`
- `0x180024e84`
- `0x180026798`
- `0x180027b28`
- `0x180028df0`
- `0x18002be64`
- `0x18002edb8`
- `0x18002f180`
- `0x18002f4cc`
- `0x18002fa34`
- `0x18002fb58`
- `0x18002ff30`
- `0x18002ff8c`
- `0x18002ffe4`
- `0x180030060`
- `0x1800316f0`
- `0x1800366e4`
- `0x180036754`
- `0x18004d400`
- `0x18006d10c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002feb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002feb3`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x18002fec3`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x18002fec3`

## pseudocode

```c
// Hidden C++ exception states: #wind=32
Spectre::Engine::Engine *__fastcall Spectre::Engine::Engine::Engine(
        Spectre::Engine::Engine *this,
        __int64 a2,
        _QWORD *a3,
        _QWORD *a4,
        _QWORD *a5)
{
  int v8; // edx
  int v9; // edx
  __int64 v10; // rax
  HANDLE CurrentProcess; // rax
  std::_Ref_count_base *v12; // rcx
  std::_Ref_count_base *v13; // rcx
  std::_Ref_count_base *v14; // rcx
  Spectre::Engine::Engine *v16; // [rsp+20h] [rbp-81h] BYREF
  _BYTE v17[8]; // [rsp+28h] [rbp-79h] BYREF
  std::_Ref_count_base *v18; // [rsp+30h] [rbp-71h]
  Spectre::Engine::Engine *v19; // [rsp+38h] [rbp-69h]
  _QWORD *v20; // [rsp+40h] [rbp-61h]
  _QWORD *v21; // [rsp+48h] [rbp-59h]
  _QWORD *v22; // [rsp+50h] [rbp-51h]
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+60h] [rbp-41h] BYREF

  v19 = this;
  v20 = a3;
  v21 = a4;
  v22 = a5;
  Spectre::Engine::Lockable::Lockable((char *)this + 8);
  *(_QWORD *)this = &Spectre::Engine::Engine::`vftable';
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>((char *)this + 88);
  Spectre::Engine::Lockable::Lockable((char *)this + 112);
  *((_QWORD *)this + 21) = 0;
  *((_QWORD *)this + 22) = 0;
  std::list<std::shared_ptr<Spectre::Engine::Display>>::_Alloc_sentinel_and_proxy();
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  std::_Tree<std::_Tmap_traits<enum Spectre::Engine::GpuQuery::QueryType,std::stack<std::shared_ptr<Spectre::Engine::GpuQuery>,std::vector<std::shared_ptr<Spectre::Engine::GpuQuery>>>,std::less<enum Spectre::Engine::GpuQuery::QueryType>,std::allocator<std::pair<enum Spectre::Engine::GpuQuery::QueryType const,std::stack<std::shared_ptr<Spectre::Engine::GpuQuery>,std::vector<std::shared_ptr<Spectre::Engine::GpuQuery>>>>>,0>>::_Alloc_sentinel_and_proxy();
  Spectre::Engine::Input::Input((Spectre::Engine::Engine *)((char *)this + 200));
  std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>((char *)this + 288);
  Spectre::Engine::Lockable::Lockable((char *)this + 312);
  Spectre::Engine::FrameData::FrameData((Spectre::Engine::Engine *)((char *)this + 368));
  *((_QWORD *)this + 58) = 0;
  *((_QWORD *)this + 59) = 0;
  *((_QWORD *)this + 58) = *a3;
  *((_QWORD *)this + 59) = a3[1];
  *a3 = 0;
  a3[1] = 0;
  *((_QWORD *)this + 60) = 0;
  *((_QWORD *)this + 61) = 0;
  *((_QWORD *)this + 60) = *a4;
  *((_QWORD *)this + 61) = a4[1];
  *a4 = 0;
  a4[1] = 0;
  *((_QWORD *)this + 62) = 0;
  *((_QWORD *)this + 63) = 0;
  *((_QWORD *)this + 62) = *a5;
  *((_QWORD *)this + 63) = a5[1];
  *a5 = 0;
  a5[1] = 0;
  *((_QWORD *)this + 64) = 0;
  *((_QWORD *)this + 65) = 0;
  Spectre::Engine::EngineDescription::EngineDescription((Spectre::Engine::Engine *)((char *)this + 528));
  *((_DWORD *)this + 174) = 0;
  std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>((char *)this + 704);
  *((_QWORD *)this + 91) = 0;
  *((_QWORD *)this + 92) = 0;
  std::_Tree<std::_Tmap_traits<std::weak_ptr<Spectre::Engine::Camera>,Spectre::Engine::Display::CameraViewport,std::owner_less<std::weak_ptr<Spectre::Engine::Camera>>,std::allocator<std::pair<std::weak_ptr<Spectre::Engine::Camera> const,Spectre::Engine::Display::CameraViewport>>,0>>::_Alloc_sentinel_and_proxy((char *)this + 728);
  *((_BYTE *)this + 744) = 1;
  *(_OWORD *)((char *)this + 748) = 0;
  *(_OWORD *)((char *)this + 764) = 0;
  *(_OWORD *)((char *)this + 780) = 0;
  *(_OWORD *)((char *)this + 792) = 0;
  Spectre::Engine::Lockable::Lockable((char *)this + 808);
  std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>((char *)this + 864);
  std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>((char *)this + 888);
  *((_QWORD *)this + 114) = 0;
  *((_QWORD *)this + 115) = 0;
  *((_QWORD *)this + 116) = 0x8000000000000000uLL;
  *((_DWORD *)this + 234) = 0;
  *((_QWORD *)this + 118) = 1;
  *((_DWORD *)this + 238) = 2139095039;
  *(_QWORD *)((char *)this + 956) = 1023960469;
  std::make_shared<Spectre::Engine::CpuProfiler,>((char *)this + 968);
  std::make_unique<Spectre::Engine::CpuProfileStatsRenderer,,0>((char *)this + 984);
  *((_QWORD *)this + 134) = 0;
  *((_QWORD *)this + 135) = 0;
  *((_QWORD *)this + 136) = 0;
  std::_Tree<std::_Tmap_traits<int,std::shared_ptr<Spectre::Engine::LightProbe>,std::less<int>,std::allocator<std::pair<int const,std::shared_ptr<Spectre::Engine::LightProbe>>>,0>>::_Alloc_sentinel_and_proxy();
  *((_DWORD *)this + 274) = 1;
  Spectre::Engine::Lockable::Lockable((char *)this + 1104);
  *((_BYTE *)this + 1160) = 0;
  *((_QWORD *)this + 147) = 0;
  *((_OWORD *)this + 74) = 0;
  *((_DWORD *)this + 300) = 60;
  std::condition_variable::condition_variable((Spectre::Engine::Engine *)((char *)this + 1208));
  std::_Mutex_base::_Mutex_base((Spectre::Engine::Engine *)((char *)this + 1280), v8);
  Spectre::Utils::TelemetryTraceLogger::ProfileDataBase::ProfileDataBase((Spectre::Engine::Engine *)((char *)this + 1368));
  *((_QWORD *)this + 178) = 0;
  *((_QWORD *)this + 179) = 0;
  std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::_Alloc_sentinel_and_proxy((char *)this + 1424);
  std::map<unsigned int,_LARGE_INTEGER>::map<unsigned int,_LARGE_INTEGER>((char *)this + 1440);
  Spectre::Engine::Engine::CreateConfiguration(this, v9);
  v16 = this;
  v10 = std::make_shared<Spectre::Engine::ShaderManager,Spectre::Engine::Engine *>(v17, &v16);
  std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=((char *)this + 512, v10);
  if ( v18 )
    std::_Ref_count_base::_Decref(v18);
  Spectre::Engine::ShaderManager::Startup(*((Spectre::Engine::ShaderManager **)this + 64));
  *((_QWORD *)this + 147) = *(_QWORD *)std::chrono::steady_clock::now(v17);
  memset_0(&ppsmemCounters, 0, sizeof(ppsmemCounters));
  CurrentProcess = GetCurrentProcess();
  K32GetProcessMemoryInfo(CurrentProcess, &ppsmemCounters, 0x48u);
  *((_QWORD *)this + 146) = ppsmemCounters.PeakWorkingSetSize;
  v12 = (std::_Ref_count_base *)a3[1];
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  v13 = (std::_Ref_count_base *)a4[1];
  if ( v13 )
    std::_Ref_count_base::_Decref(v13);
  v14 = (std::_Ref_count_base *)a5[1];
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  return this;
}

```

## disassembly

```asm
0x18002fb58  mov     [rsp-8+arg_8], rbx
0x18002fb5d  push    rbp
0x18002fb5e  push    rsi
0x18002fb5f  push    rdi
0x18002fb60  push    r12
0x18002fb62  push    r13
0x18002fb64  push    r14
0x18002fb66  push    r15
0x18002fb68  lea     rbp, [rsp-1Fh]
0x18002fb6d  sub     rsp, 0C0h
0x18002fb74  mov     rax, cs:__security_cookie
0x18002fb7b  xor     rax, rsp
0x18002fb7e  mov     [rbp+4Fh+var_40], rax
0x18002fb82  mov     rsi, r9
0x18002fb85  mov     r15, r8
0x18002fb88  mov     ebx, edx
0x18002fb8a  mov     rdi, rcx
0x18002fb8d  mov     [rbp+4Fh+var_B8], rcx
0x18002fb91  mov     [rbp+4Fh+var_B0], r8
0x18002fb95  mov     [rbp+4Fh+var_A8], r9
0x18002fb99  mov     r14, [rbp+4Fh+arg_20]
0x18002fb9d  mov     [rbp+4Fh+var_A0], r14
0x18002fba1  add     rcx, 8
0x18002fba5  call    ??0Lockable@Engine@Spectre@@QEAA@W4ThreadingMode@012@@Z; Spectre::Engine::Lockable::Lockable(Spectre::Engine::Lockable::ThreadingMode)
0x18002fbaa  nop
0x18002fbab  lea     rax, ??_7Engine@0Spectre@@6B@; const Spectre::Engine::Engine::`vftable'
0x18002fbb2  mov     [rdi], rax
0x18002fbb5  xor     r13d, r13d
0x18002fbb8  mov     [rdi+40h], r13
0x18002fbbc  mov     [rdi+48h], r13
0x18002fbc0  mov     [rdi+50h], r13
0x18002fbc4  lea     rcx, [rdi+58h]; void *
0x18002fbc8  call    ??0?$vector@UShaderPropertyDefinition@Engine@Spectre@@V?$allocator@UShaderPropertyDefinition@Engine@Spectre@@@std@@@std@@QEAA@XZ; std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>(void)
0x18002fbcd  nop
0x18002fbce  lea     rcx, [rdi+70h]
0x18002fbd2  mov     edx, ebx
0x18002fbd4  call    ??0Lockable@Engine@Spectre@@QEAA@W4ThreadingMode@012@@Z; Spectre::Engine::Lockable::Lockable(Spectre::Engine::Lockable::ThreadingMode)
0x18002fbd9  nop
0x18002fbda  lea     rcx, [rdi+0A8h]
0x18002fbe1  mov     [rcx], r13
0x18002fbe4  mov     [rcx+8], r13
0x18002fbe8  call    ?_Alloc_sentinel_and_proxy@?$list@V?$shared_ptr@VDisplay@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VDisplay@Engine@Spectre@@@std@@@2@@std@@AEAAXXZ; std::list<std::shared_ptr<Spectre::Engine::Display>>::_Alloc_sentinel_and_proxy(void)
0x18002fbed  nop
0x18002fbee  lea     rcx, [rdi+0B8h]
0x18002fbf5  mov     [rcx], r13
0x18002fbf8  mov     [rcx+8], r13
0x18002fbfc  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@W4QueryType@GpuQuery@Engine@Spectre@@V?$stack@V?$shared_ptr@VGpuQuery@Engine@Spectre@@@std@@V?$vector@V?$shared_ptr@VGpuQuery@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VGpuQuery@Engine@Spectre@@@std@@@2@@2@@std@@U?$less@W4QueryType@GpuQuery@Engine@Spectre@@@6@V?$allocator@U?$pair@$$CBW4QueryType@GpuQuery@Engine@Spectre@@V?$stack@V?$shared_ptr@VGpuQuery@Engine@Spectre@@@std@@V?$vector@V?$shared_ptr@VGpuQuery@Engine@Spectre@@@std@@V?$allocator@V?$shared_ptr@VGpuQuery@Engine@Spectre@@@std@@@2@@2@@std@@@std@@@6@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<Spectre::Engine::GpuQuery::QueryType,std::stack<std::shared_ptr<Spectre::Engine::GpuQuery>,std::vector<std::shared_ptr<Spectre::Engine::GpuQuery>>>,std::less<Spectre::Engine::GpuQuery::QueryType>,std::allocator<std::pair<Spectre::Engine::GpuQuery::QueryType const,std::stack<std::shared_ptr<Spectre::Engine::GpuQuery>,std::vector<std::shared_ptr<Spectre::Engine::GpuQuery>>>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18002fc01  nop
0x18002fc02  lea     rcx, [rdi+0C8h]; this
0x18002fc09  call    ??0Input@Engine@Spectre@@QEAA@XZ; Spectre::Engine::Input::Input(void)
0x18002fc0e  nop
0x18002fc0f  lea     rcx, [rdi+120h]; void *
0x18002fc16  call    ??0?$vector@UShaderPropertyDefinition@Engine@Spectre@@V?$allocator@UShaderPropertyDefinition@Engine@Spectre@@@std@@@std@@QEAA@XZ; std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>(void)
0x18002fc1b  nop
0x18002fc1c  lea     rcx, [rdi+138h]
0x18002fc23  mov     edx, ebx
0x18002fc25  call    ??0Lockable@Engine@Spectre@@QEAA@W4ThreadingMode@012@@Z; Spectre::Engine::Lockable::Lockable(Spectre::Engine::Lockable::ThreadingMode)
0x18002fc2a  nop
0x18002fc2b  lea     rcx, [rdi+170h]; this
0x18002fc32  call    ??0FrameData@Engine@Spectre@@QEAA@XZ; Spectre::Engine::FrameData::FrameData(void)
0x18002fc37  nop
0x18002fc38  mov     [rdi+1D0h], r13
0x18002fc3f  mov     [rdi+1D8h], r13
0x18002fc46  mov     rax, [r15]
0x18002fc49  mov     [rdi+1D0h], rax
0x18002fc50  mov     rax, [r15+8]
0x18002fc54  mov     [rdi+1D8h], rax
0x18002fc5b  mov     [r15], r13
0x18002fc5e  mov     [r15+8], r13
0x18002fc62  mov     [rdi+1E0h], r13
0x18002fc69  mov     [rdi+1E8h], r13
0x18002fc70  mov     rax, [rsi]
0x18002fc73  mov     [rdi+1E0h], rax
0x18002fc7a  mov     rax, [rsi+8]
0x18002fc7e  mov     [rdi+1E8h], rax
0x18002fc85  mov     [rsi], r13
0x18002fc88  mov     [rsi+8], r13
0x18002fc8c  mov     [rdi+1F0h], r13
0x18002fc93  mov     [rdi+1F8h], r13
0x18002fc9a  mov     rax, [r14]
0x18002fc9d  mov     [rdi+1F0h], rax
0x18002fca4  mov     rax, [r14+8]
0x18002fca8  mov     [rdi+1F8h], rax
0x18002fcaf  mov     [r14], r13
0x18002fcb2  mov     [r14+8], r13
0x18002fcb6  lea     r12, [rdi+200h]
0x18002fcbd  mov     [r12], r13
0x18002fcc1  mov     [r12+8], r13
0x18002fcc6  lea     rcx, [rdi+210h]; this
0x18002fccd  call    ??0EngineDescription@Engine@Spectre@@QEAA@XZ; Spectre::Engine::EngineDescription::EngineDescription(void)
0x18002fcd2  nop
0x18002fcd3  mov     [rdi+2B8h], r13d
0x18002fcda  lea     rcx, [rdi+2C0h]; void *
0x18002fce1  call    ??0?$vector@UShaderPropertyDefinition@Engine@Spectre@@V?$allocator@UShaderPropertyDefinition@Engine@Spectre@@@std@@@std@@QEAA@XZ; std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>(void)
0x18002fce6  nop
0x18002fce7  lea     rcx, [rdi+2D8h]
0x18002fcee  mov     [rcx], r13
0x18002fcf1  mov     [rcx+8], r13
0x18002fcf5  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$weak_ptr@VCamera@Engine@Spectre@@@std@@UCameraViewport@Display@Engine@Spectre@@U?$owner_less@V?$weak_ptr@VCamera@Engine@Spectre@@@std@@@2@V?$allocator@U?$pair@$$CBV?$weak_ptr@VCamera@Engine@Spectre@@@std@@UCameraViewport@Display@Engine@Spectre@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::weak_ptr<Spectre::Engine::Camera>,Spectre::Engine::Display::CameraViewport,std::owner_less<std::weak_ptr<Spectre::Engine::Camera>>,std::allocator<std::pair<std::weak_ptr<Spectre::Engine::Camera> const,Spectre::Engine::Display::CameraViewport>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18002fcfa  nop
0x18002fcfb  mov     r13d, 1
0x18002fd01  mov     [rdi+2E8h], r13b
0x18002fd08  xorps   xmm0, xmm0
0x18002fd0b  movups  xmmword ptr [rdi+2ECh], xmm0
0x18002fd12  movups  xmmword ptr [rdi+2FCh], xmm0
0x18002fd19  movups  xmmword ptr [rdi+30Ch], xmm0
0x18002fd20  movups  xmmword ptr [rdi+318h], xmm0
0x18002fd27  lea     rcx, [rdi+328h]
0x18002fd2e  mov     edx, ebx
0x18002fd30  call    ??0Lockable@Engine@Spectre@@QEAA@W4ThreadingMode@012@@Z; Spectre::Engine::Lockable::Lockable(Spectre::Engine::Lockable::ThreadingMode)
0x18002fd35  nop
0x18002fd36  lea     rcx, [rdi+360h]; void *
0x18002fd3d  call    ??0?$vector@UShaderPropertyDefinition@Engine@Spectre@@V?$allocator@UShaderPropertyDefinition@Engine@Spectre@@@std@@@std@@QEAA@XZ; std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>(void)
0x18002fd42  nop
0x18002fd43  lea     rcx, [rdi+378h]; void *
0x18002fd4a  call    ??0?$vector@UShaderPropertyDefinition@Engine@Spectre@@V?$allocator@UShaderPropertyDefinition@Engine@Spectre@@@std@@@std@@QEAA@XZ; std::vector<Spectre::Engine::ShaderPropertyDefinition>::vector<Spectre::Engine::ShaderPropertyDefinition>(void)
0x18002fd4f  nop
0x18002fd50  xor     ecx, ecx
0x18002fd52  mov     [rdi+390h], rcx
0x18002fd59  mov     [rdi+398h], rcx
0x18002fd60  mov     rax, 8000000000000000h
0x18002fd6a  mov     [rdi+3A0h], rax
0x18002fd71  mov     [rdi+3A8h], ecx
0x18002fd77  mov     [rdi+3B0h], r13
0x18002fd7e  mov     dword ptr [rdi+3B8h], 7F7FFFFFh
0x18002fd88  mov     qword ptr [rdi+3BCh], 3D086595h
0x18002fd93  lea     rcx, [rdi+3C8h]
0x18002fd9a  call    ??$make_shared@VCpuProfiler@Engine@Spectre@@$$V@std@@YA?AV?$shared_ptr@VCpuProfiler@Engine@Spectre@@@0@XZ; std::make_shared<Spectre::Engine::CpuProfiler,>(void)
0x18002fd9f  nop
0x18002fda0  lea     rcx, [rdi+3D8h]
0x18002fda7  call    ??$make_unique@VCpuProfileStatsRenderer@Engine@Spectre@@$$V$0A@@std@@YA?AV?$unique_ptr@VCpuProfileStatsRenderer@Engine@Spectre@@U?$default_delete@VCpuProfileStatsRenderer@Engine@Spectre@@@std@@@0@XZ; std::make_unique<Spectre::Engine::CpuProfileStatsRenderer,,0>(void)
0x18002fdac  nop
0x18002fdad  xor     eax, eax
0x18002fdaf  mov     [rdi+430h], rax
0x18002fdb6  lea     rcx, [rdi+438h]
0x18002fdbd  mov     [rcx], rax
0x18002fdc0  mov     [rcx+8], rax
0x18002fdc4  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@HV?$shared_ptr@VLightProbe@Engine@Spectre@@@std@@U?$less@H@2@V?$allocator@U?$pair@$$CBHV?$shared_ptr@VLightProbe@Engine@Spectre@@@std@@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<int,std::shared_ptr<Spectre::Engine::LightProbe>,std::less<int>,std::allocator<std::pair<int const,std::shared_ptr<Spectre::Engine::LightProbe>>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18002fdc9  nop
0x18002fdca  mov     [rdi+448h], r13d
0x18002fdd1  lea     rcx, [rdi+450h]
0x18002fdd8  mov     edx, ebx
0x18002fdda  call    ??0Lockable@Engine@Spectre@@QEAA@W4ThreadingMode@012@@Z; Spectre::Engine::Lockable::Lockable(Spectre::Engine::Lockable::ThreadingMode)
0x18002fddf  nop
0x18002fde0  xor     r13d, r13d
0x18002fde3  mov     [rdi+488h], r13b
0x18002fdea  mov     [rdi+498h], r13
0x18002fdf1  xorps   xmm0, xmm0
0x18002fdf4  movups  xmmword ptr [rdi+4A0h], xmm0
0x18002fdfb  mov     dword ptr [rdi+4B0h], 3Ch ; '<'
0x18002fe05  lea     rcx, [rdi+4B8h]; this
0x18002fe0c  call    ??0condition_variable@std@@QEAA@XZ; std::condition_variable::condition_variable(void)
0x18002fe11  lea     rcx, [rdi+500h]; this
0x18002fe18  call    ??0_Mutex_base@std@@QEAA@H@Z; std::_Mutex_base::_Mutex_base(int)
0x18002fe1d  lea     rcx, [rdi+558h]; this
0x18002fe24  call    ??0ProfileDataBase@TelemetryTraceLogger@Utils@Spectre@@QEAA@XZ; Spectre::Utils::TelemetryTraceLogger::ProfileDataBase::ProfileDataBase(void)
0x18002fe29  nop
0x18002fe2a  lea     rbx, [rdi+590h]
0x18002fe31  mov     [rsp+0F0h+var_D0], rbx
0x18002fe36  mov     [rbx], r13
0x18002fe39  mov     [rbx+8], r13
0x18002fe3d  mov     rcx, rbx
0x18002fe40  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@U?$less@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<std::string,std::string,std::less<std::string>,std::allocator<std::pair<std::string const,std::string>>,0>>::_Alloc_sentinel_and_proxy(void)
0x18002fe45  nop
0x18002fe46  lea     rcx, [rbx+10h]
0x18002fe4a  call    ??0?$map@IT_LARGE_INTEGER@@U?$less@I@std@@V?$allocator@U?$pair@$$CBIT_LARGE_INTEGER@@@std@@@3@@std@@QEAA@XZ; std::map<uint,_LARGE_INTEGER>::map<uint,_LARGE_INTEGER>(void)
0x18002fe4f  nop
0x18002fe50  mov     rcx, rdi; this
0x18002fe53  call    ?CreateConfiguration@Engine@1Spectre@@QEAAHH@Z; Spectre::Engine::Engine::CreateConfiguration(int)
0x18002fe58  mov     [rsp+0F0h+var_D0], rdi
0x18002fe5d  lea     rdx, [rsp+0F0h+var_D0]
0x18002fe62  lea     rcx, [rbp+4Fh+var_C8]
0x18002fe66  call    ??$make_shared@VShaderManager@Engine@Spectre@@PEAV223@@std@@YA?AV?$shared_ptr@VShaderManager@Engine@Spectre@@@0@$$QEAPEAVEngine@2Spectre@@@Z; std::make_shared<Spectre::Engine::ShaderManager,Spectre::Engine::Engine *>(Spectre::Engine::Engine * &&)
0x18002fe6b  mov     rdx, rax
0x18002fe6e  mov     rcx, r12
0x18002fe71  call    ??4?$shared_ptr@VDeviceArrayBuffer@Engine@Spectre@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Spectre::Engine::DeviceArrayBuffer>::operator=(std::shared_ptr<Spectre::Engine::DeviceArrayBuffer> &&)
0x18002fe76  mov     rcx, [rbp+4Fh+var_C0]; this
0x18002fe7a  test    rcx, rcx
0x18002fe7d  jz      short loc_18002FE84
0x18002fe7f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002fe84  mov     rcx, [r12]; this
0x18002fe88  call    ?Startup@ShaderManager@Engine@Spectre@@QEAAXXZ; Spectre::Engine::ShaderManager::Startup(void)
0x18002fe8d  lea     rcx, [rbp+4Fh+var_C8]
0x18002fe91  call    ?now@steady_clock@chrono@std@@SA?AV?$time_point@Usteady_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0DLJKMKAA@@std@@@23@@23@XZ; std::chrono::steady_clock::now(void)
0x18002fe96  mov     rcx, [rax]
0x18002fe99  mov     [rdi+498h], rcx
0x18002fea0  mov     ebx, 48h ; 'H'
0x18002fea5  mov     r8d, ebx; Size
0x18002fea8  xor     edx, edx; Val
0x18002feaa  lea     rcx, [rbp+4Fh+ppsmemCounters]; void *
0x18002feae  call    memset_0
0x18002feb3  call    cs:__imp_GetCurrentProcess
0x18002feb9  mov     rcx, rax; Process
0x18002febc  mov     r8d, ebx; cb
0x18002febf  lea     rdx, [rbp+4Fh+ppsmemCounters]; ppsmemCounters
0x18002fec3  call    cs:__imp_K32GetProcessMemoryInfo
0x18002fec9  mov     rax, [rbp+4Fh+ppsmemCounters.PeakWorkingSetSize]
0x18002fecd  mov     [rdi+490h], rax
0x18002fed4  mov     rcx, [r15+8]; this
0x18002fed8  test    rcx, rcx
0x18002fedb  jz      short loc_18002FEE3
0x18002fedd  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002fee2  nop
0x18002fee3  mov     rcx, [rsi+8]; this
0x18002fee7  test    rcx, rcx
0x18002feea  jz      short loc_18002FEF2
0x18002feec  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002fef1  nop
0x18002fef2  mov     rcx, [r14+8]; this
0x18002fef6  test    rcx, rcx
0x18002fef9  jz      short loc_18002FF00
0x18002fefb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18002ff00  mov     rax, rdi
0x18002ff03  mov     rcx, [rbp+4Fh+var_40]
0x18002ff07  xor     rcx, rsp; StackCookie
0x18002ff0a  call    __security_check_cookie
0x18002ff0f  mov     rbx, [rsp+0F0h+arg_8]
0x18002ff17  add     rsp, 0C0h
0x18002ff1e  pop     r15
0x18002ff20  pop     r14
0x18002ff22  pop     r13
0x18002ff24  pop     r12
0x18002ff26  pop     rdi
0x18002ff27  pop     rsi
0x18002ff28  pop     rbp
0x18002ff29  retn
```
