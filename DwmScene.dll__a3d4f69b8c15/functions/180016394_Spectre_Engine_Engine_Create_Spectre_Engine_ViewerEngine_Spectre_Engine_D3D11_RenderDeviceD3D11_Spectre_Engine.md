# Spectre::Engine::Engine::Create<Spectre::Engine::ViewerEngine,Spectre::Engine::D3D11::RenderDeviceD3D11>(Spectre::Engine::EngineDescription const &,std::shared_ptr<Spectre::Utils::PerformanceLogger>,std::shared_ptr<Spectre::Utils::ITelemetryManager>,std::shared_ptr<Spectre::Utils::ITelemetryTraceLogger>)

- ea: `0x180016394`
- end: `0x180016702`
- name: `??$Create@VViewerEngine@Engine@Spectre@@VRenderDeviceD3D11@D3D11@23@@Engine@0Spectre@@SA?AV?$unique_ptr@VViewerEngine@Engine@Spectre@@U?$default_delete@VViewerEngine@Engine@Spectre@@@std@@@std@@AEBUEngineDescription@01@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@3@V?$shared_ptr@VITelemetryManager@Utils@Spectre@@@3@V?$shared_ptr@VITelemetryTraceLogger@Utils@Spectre@@@3@@Z`
- size: `878`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `broker_com_uri`

## callers

- `0x180016708`

## callees

- `0x18000ca90`
- `0x18001128c`
- `0x1800120ec`
- `0x180012ba8`
- `0x180012df8`
- `0x180016394`
- `0x1800167f4`
- `0x180016918`
- `0x180018360`
- `0x1800187f4`
- `0x1800188ac`
- `0x18001c290`
- `0x18001ffa4`
- `0x180028f40`
- `0x180032f14`
- `0x18003327c`
- `0x180034f90`
- `0x18003565c`
- `0x18005e3d8`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800165d9`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x1800165d9`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
Spectre::Engine::Engine **__fastcall Spectre::Engine::Engine::Create<Spectre::Engine::ViewerEngine,Spectre::Engine::D3D11::RenderDeviceD3D11>(
        Spectre::Engine::Engine **a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5)
{
  char v9; // r12
  __int64 *v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rdx
  std::_Ref_count_base *v13; // rcx
  void *v14; // rax
  int v15; // eax
  __int64 v16; // r8
  int v17; // r9d
  int v18; // r10d
  Spectre::Engine::Engine *v19; // rax
  char v20; // di
  __int64 HardwareVersion; // rax
  Spectre::Engine::Engine *v22; // r15
  Spectre::Engine::Engine *v23; // r15
  __int128 v24; // xmm6
  __int128 v25; // xmm7
  __int64 v26; // rax
  Spectre::Engine::Engine *v27; // r15
  Spectre::Engine::Engine *v28; // r15
  __int128 v29; // xmm6
  __int128 v30; // xmm7
  __int64 v31; // rax
  std::_Ref_count_base *v32; // rcx
  std::_Ref_count_base *v33; // rcx
  std::_Ref_count_base *v34; // rcx
  Spectre::Engine::Engine **result; // rax
  __int64 v36; // rdi
  void (__fastcall *v37)(__int64, _QWORD, __int64, const char *); // rbx
  __int64 v38; // rax
  _BYTE v39[8]; // [rsp+38h] [rbp-1D0h] BYREF
  std::_Ref_count_base *v40; // [rsp+40h] [rbp-1C8h]
  __int64 v41; // [rsp+48h] [rbp-1C0h]
  __int64 v42; // [rsp+50h] [rbp-1B8h]
  _OWORD v43[2]; // [rsp+60h] [rbp-1A8h] BYREF
  Spectre::Engine::Engine **v44; // [rsp+80h] [rbp-188h]
  _QWORD *v45; // [rsp+88h] [rbp-180h]
  __int64 v46; // [rsp+90h] [rbp-178h]
  Spectre::Utils::SpectreException *v47; // [rsp+98h] [rbp-170h] BYREF
  _BYTE v48[16]; // [rsp+A0h] [rbp-168h] BYREF
  _BYTE v49[8]; // [rsp+B0h] [rbp-158h] BYREF
  std::_Ref_count_base *v50; // [rsp+B8h] [rbp-150h]
  _BYTE v51[96]; // [rsp+C0h] [rbp-148h] BYREF
  _BYTE v52[96]; // [rsp+120h] [rbp-E8h] BYREF
  std::_Ref_count_base *v53[2]; // [rsp+180h] [rbp-88h] BYREF
  __int128 v54; // [rsp+190h] [rbp-78h]

  v44 = a1;
  v45 = a3;
  v46 = a4;
  v41 = a5;
  v42 = a5;
  v9 = 1;
  if ( !*a3 )
  {
    v10 = (__int64 *)Spectre::Utils::PerformanceLogger::CreateWithDefaultProviders(v53);
    v11 = *v10;
    v12 = v10[1];
    *v10 = 0;
    v10[1] = 0;
    *a3 = v11;
    v13 = (std::_Ref_count_base *)a3[1];
    a3[1] = v12;
    if ( v13 )
      std::_Ref_count_base::_Decref(v13);
    if ( v53[1] )
      std::_Ref_count_base::_Decref(v53[1]);
  }
  v14 = operator new(0x660u);
  try
  {
    if ( v14 )
    {
      std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(v48, a5);
      std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(v43, a4);
      v15 = std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(
              v39,
              a3);
      v19 = (Spectre::Engine::Engine *)Spectre::Engine::ViewerEngine::ViewerEngine(
                                         v18,
                                         *(_DWORD *)(a2 + 20),
                                         v15,
                                         v17,
                                         v16);
    }
    else
    {
      v19 = 0;
    }
    *a1 = v19;
    v20 = 1;
    HardwareVersion = Spectre::Engine::Engine::GetHardwareVersion(v19);
    std::string::operator=(Spectre::Engine::g_hardwareVersion, HardwareVersion);
    std::string::_Tidy_deallocate(v53);
    v22 = *a1;
    *((_OWORD *)v22 + 33) = *(_OWORD *)a2;
    *((_OWORD *)v22 + 34) = *(_OWORD *)(a2 + 16);
    *((_QWORD *)v22 + 70) = *(_QWORD *)(a2 + 32);
    Spectre::Engine::DeviceDescription::operator=((char *)v22 + 568, a2 + 40);
    *(_OWORD *)((char *)v22 + 664) = *(_OWORD *)(a2 + 136);
    *(_OWORD *)((char *)v22 + 680) = *(_OWORD *)(a2 + 152);
    v23 = *a1;
    v24 = *(_OWORD *)(a2 + 136);
    v25 = *(_OWORD *)(a2 + 152);
    v26 = Spectre::Engine::DeviceDescription::DeviceDescription(
            (Spectre::Engine::DeviceDescription *)v51,
            (const struct Spectre::Engine::DeviceDescription *)(a2 + 40));
    *(_OWORD *)v53 = v24;
    v54 = v25;
    Spectre::Engine::Engine::CreateDevice<Spectre::Engine::RenderDeviceGeneric>(v23, v49, v26, v53);
    v27 = *a1;
    Spectre::Engine::Lockable::GetExclusiveLock((char *)*a1 + 8, v39);
    *((_QWORD *)v27 + 114) = *(_QWORD *)a2;
    *((_QWORD *)v27 + 115) = *(_QWORD *)(a2 + 8);
    (*(void (__fastcall **)(Spectre::Engine::Engine *, __int64))(*(_QWORD *)v27 + 88LL))(v27, a2);
    std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(v39);
    if ( (unsigned int)__std_type_info_compare(&qword_18022BE80, &qword_18022BE08) )
    {
      v28 = *a1;
      v29 = *(_OWORD *)(a2 + 136);
      v30 = *(_OWORD *)(a2 + 152);
      v31 = Spectre::Engine::DeviceDescription::DeviceDescription(
              (Spectre::Engine::DeviceDescription *)v52,
              (const struct Spectre::Engine::DeviceDescription *)(a2 + 40));
      v43[0] = v29;
      v43[1] = v30;
      Spectre::Engine::Engine::CreateDevice<Spectre::Engine::D3D11::RenderDeviceD3D11>(v28, v39, v31, v43);
      if ( v40 )
        std::_Ref_count_base::_Decref(v40);
    }
    Spectre::Engine::Engine::SendEngineInitializedTelemetry(*a1);
    if ( !*(_BYTE *)(a2 + 28) || (v20 = 3, !*(_QWORD *)Spectre::Engine::Engine::GetTelemetryTraceLogger(*a1, v39)) )
      v9 = 0;
    if ( (v20 & 2) != 0 && v40 )
      std::_Ref_count_base::_Decref(v40);
    if ( v9 )
      Spectre::Engine::Engine::StartPerformanceThread(*a1);
    if ( v50 )
      std::_Ref_count_base::_Decref(v50);
    v32 = (std::_Ref_count_base *)a3[1];
    if ( v32 )
      std::_Ref_count_base::_Decref(v32);
    v33 = *(std::_Ref_count_base **)(a4 + 8);
    if ( v33 )
      std::_Ref_count_base::_Decref(v33);
    v34 = *(std::_Ref_count_base **)(v41 + 8);
    if ( v34 )
      std::_Ref_count_base::_Decref(v34);
    result = a1;
  }
  catch ( Spectre::Utils::SpectreException *v47 )
  {
    if ( *(_QWORD *)v42 )
    {
      v36 = *(_QWORD *)v42;
      v37 = *(void (__fastcall **)(__int64, _QWORD, __int64, const char *))(**(_QWORD **)v42 + 24LL);
      v38 = (*(__int64 (__fastcall **)(Spectre::Utils::SpectreException *))(*(_QWORD *)v47 + 8LL))(v47);
      v37(v36, 0, v38, "2.7.0.2");
    }
    throw;
  }
  return result;
}

```

## disassembly

```asm
0x180016394  mov     r11, rsp
0x180016397  push    rbx
0x180016398  push    rsi
0x180016399  push    rdi
0x18001639a  push    r12
0x18001639c  push    r13
0x18001639e  push    r14
0x1800163a0  push    r15
0x1800163a2  sub     rsp, 1D0h
0x1800163a9  movaps  xmmword ptr [r11-48h], xmm6
0x1800163ae  movaps  xmmword ptr [r11-58h], xmm7
0x1800163b3  mov     rax, cs:__security_cookie
0x1800163ba  xor     rax, rsp
0x1800163bd  mov     [rsp+208h+var_68], rax
0x1800163c5  mov     r13, r9
0x1800163c8  mov     r14, r8
0x1800163cb  mov     rsi, rdx
0x1800163ce  mov     rbx, rcx
0x1800163d1  mov     [r11-188h], rcx
0x1800163d8  mov     [r11-180h], r8
0x1800163df  mov     [r11-178h], r9
0x1800163e6  mov     rdi, [rsp+208h+arg_20]
0x1800163ee  mov     [rsp+208h+var_1C0], rdi
0x1800163f3  mov     [rsp+208h+var_1B8], rdi
0x1800163f8  mov     r12d, 1
0x1800163fe  mov     dword ptr [rsp+208h+var_1D8], r12d
0x180016403  xor     r15d, r15d
0x180016406  cmp     [r8], r15
0x180016409  jnz     short loc_18001644D
0x18001640b  lea     rcx, [r11-88h]
0x180016412  call    ?CreateWithDefaultProviders@PerformanceLogger@Utils@Spectre@@SA?AV?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@XZ; Spectre::Utils::PerformanceLogger::CreateWithDefaultProviders(void)
0x180016417  mov     rcx, [rax]
0x18001641a  mov     rdx, [rax+8]
0x18001641e  mov     [rax], r15
0x180016421  mov     [rax+8], r15
0x180016425  mov     [r14], rcx
0x180016428  mov     rcx, [r14+8]; this
0x18001642c  mov     [r14+8], rdx
0x180016430  test    rcx, rcx
0x180016433  jz      short loc_18001643A
0x180016435  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001643a  mov     rcx, [rsp+208h+var_88+8]; this
0x180016442  test    rcx, rcx
0x180016445  jz      short loc_18001644D
0x180016447  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001644c  nop
0x18001644d  mov     ecx, 660h; unsigned __int64
0x180016452  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180016457  mov     r10, rax
0x18001645a  mov     [rsp+208h+var_1D8], rax
0x18001645f  test    rax, rax
0x180016462  jz      short loc_1800164A9
0x180016464  mov     rdx, rdi
0x180016467  lea     rcx, [rsp+208h+var_168]
0x18001646f  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180016474  mov     r8, rax
0x180016477  mov     rdx, r13
0x18001647a  lea     rcx, [rsp+208h+var_1A8]
0x18001647f  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180016484  mov     r9, rax
0x180016487  mov     rdx, r14
0x18001648a  lea     rcx, [rsp+208h+var_1D0]
0x18001648f  call    ??$?0VDefaultSceneNodeTraversal@Engine@Spectre@@$0A@@?$shared_ptr@VISceneNodeTraversal@Engine@Spectre@@@std@@QEAA@AEBV?$shared_ptr@VDefaultSceneNodeTraversal@Engine@Spectre@@@1@@Z; std::shared_ptr<Spectre::Engine::ISceneNodeTraversal>::shared_ptr<Spectre::Engine::ISceneNodeTraversal>(std::shared_ptr<Spectre::Engine::DefaultSceneNodeTraversal> const &)
0x180016494  mov     [rsp+208h+var_1E8], r8
0x180016499  mov     r8, rax
0x18001649c  mov     edx, [rsi+14h]
0x18001649f  mov     rcx, r10
0x1800164a2  call    ??0ViewerEngine@Engine@Spectre@@IEAA@W4ThreadingMode@Lockable@12@V?$shared_ptr@VPerformanceLogger@Utils@Spectre@@@std@@V?$shared_ptr@VITelemetryManager@Utils@Spectre@@@6@V?$shared_ptr@VITelemetryTraceLogger@Utils@Spectre@@@6@@Z; Spectre::Engine::ViewerEngine::ViewerEngine(Spectre::Engine::Lockable::ThreadingMode,std::shared_ptr<Spectre::Utils::PerformanceLogger>,std::shared_ptr<Spectre::Utils::ITelemetryManager>,std::shared_ptr<Spectre::Utils::ITelemetryTraceLogger>)
0x1800164a7  jmp     short loc_1800164AC
0x1800164a9  mov     rax, r15
0x1800164ac  mov     [rbx], rax
0x1800164af  mov     edi, r12d
0x1800164b2  mov     dword ptr [rsp+208h+var_1D8], r12d
0x1800164b7  lea     rdx, [rsp+208h+var_88]
0x1800164bf  mov     rcx, rax; this
0x1800164c2  call    ?GetHardwareVersion@Engine@1Spectre@@IEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Spectre::Engine::Engine::GetHardwareVersion(void)
0x1800164c7  mov     rdx, rax
0x1800164ca  lea     rcx, ?g_hardwareVersion@Engine@Spectre@@3V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@A; std::string Spectre::Engine::g_hardwareVersion
0x1800164d1  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1800164d6  lea     rcx, [rsp+208h+var_88]
0x1800164de  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x1800164e3  mov     r15, [rbx]
0x1800164e6  movups  xmm0, xmmword ptr [rsi]
0x1800164e9  movups  xmmword ptr [r15+210h], xmm0
0x1800164f1  movups  xmm1, xmmword ptr [rsi+10h]
0x1800164f5  movups  xmmword ptr [r15+220h], xmm1
0x1800164fd  movsd   xmm0, qword ptr [rsi+20h]
0x180016502  movsd   qword ptr [r15+230h], xmm0
0x18001650b  lea     rdx, [rsi+28h]
0x18001650f  lea     rcx, [r15+238h]
0x180016516  call    ??4DeviceDescription@Engine@Spectre@@QEAAAEAU012@AEBU012@@Z; Spectre::Engine::DeviceDescription::operator=(Spectre::Engine::DeviceDescription const &)
0x18001651b  movups  xmm0, xmmword ptr [rsi+88h]
0x180016522  movups  xmmword ptr [r15+298h], xmm0
0x18001652a  movups  xmm1, xmmword ptr [rsi+98h]
0x180016531  movups  xmmword ptr [r15+2A8h], xmm1
0x180016539  mov     r15, [rbx]
0x18001653c  movups  xmm6, xmmword ptr [rsi+88h]
0x180016543  movups  xmm7, xmmword ptr [rsi+98h]
0x18001654a  lea     rdx, [rsi+28h]; struct Spectre::Engine::DeviceDescription *
0x18001654e  lea     rcx, [rsp+208h+var_148]; this
0x180016556  call    ??0DeviceDescription@Engine@Spectre@@QEAA@AEBU012@@Z; Spectre::Engine::DeviceDescription::DeviceDescription(Spectre::Engine::DeviceDescription const &)
0x18001655b  movaps  xmmword ptr [rsp+208h+var_88], xmm6
0x180016563  movaps  [rsp+208h+var_78], xmm7
0x18001656b  lea     r9, [rsp+208h+var_88]
0x180016573  mov     r8, rax
0x180016576  lea     rdx, [rsp+208h+var_158]
0x18001657e  mov     rcx, r15
0x180016581  call    ??$CreateDevice@VRenderDeviceGeneric@Engine@Spectre@@@Engine@0Spectre@@QEAA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@UDeviceDescription@01@UOutputDescription@01@@Z; Spectre::Engine::Engine::CreateDevice<Spectre::Engine::RenderDeviceGeneric>(Spectre::Engine::DeviceDescription,Spectre::Engine::OutputDescription)
0x180016586  nop
0x180016587  mov     r15, [rbx]
0x18001658a  lea     rcx, [r15+8]
0x18001658e  lea     rdx, [rsp+208h+var_1D0]
0x180016593  call    ?GetExclusiveLock@Lockable@Engine@Spectre@@QEAA?AV?$unique_lock@VMutex@Engine@Spectre@@@std@@XZ; Spectre::Engine::Lockable::GetExclusiveLock(void)
0x180016598  nop
0x180016599  mov     rax, [rsi]
0x18001659c  mov     [r15+390h], rax
0x1800165a3  mov     rax, [rsi+8]
0x1800165a7  mov     [r15+398h], rax
0x1800165ae  mov     rax, [r15]
0x1800165b1  mov     rdx, rsi
0x1800165b4  mov     rcx, r15
0x1800165b7  mov     rax, [rax+58h]
0x1800165bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800165c0  nop
0x1800165c1  lea     rcx, [rsp+208h+var_1D0]
0x1800165c6  call    ??1?$unique_lock@VMutex@Engine@Spectre@@@std@@QEAA@XZ; std::unique_lock<Spectre::Engine::Mutex>::~unique_lock<Spectre::Engine::Mutex>(void)
0x1800165cb  lea     rdx, qword_18022BE08
0x1800165d2  lea     rcx, qword_18022BE80
0x1800165d9  call    cs:__imp___std_type_info_compare
0x1800165df  test    eax, eax
0x1800165e1  jz      short loc_180016633
0x1800165e3  mov     r15, [rbx]
0x1800165e6  movups  xmm6, xmmword ptr [rsi+88h]
0x1800165ed  movups  xmm7, xmmword ptr [rsi+98h]
0x1800165f4  lea     rdx, [rsi+28h]; struct Spectre::Engine::DeviceDescription *
0x1800165f8  lea     rcx, [rsp+208h+var_E8]; this
0x180016600  call    ??0DeviceDescription@Engine@Spectre@@QEAA@AEBU012@@Z; Spectre::Engine::DeviceDescription::DeviceDescription(Spectre::Engine::DeviceDescription const &)
0x180016605  movaps  [rsp+208h+var_1A8], xmm6
0x18001660a  movaps  [rsp+208h+var_198], xmm7
0x18001660f  lea     r9, [rsp+208h+var_1A8]
0x180016614  mov     r8, rax
0x180016617  lea     rdx, [rsp+208h+var_1D0]
0x18001661c  mov     rcx, r15
0x18001661f  call    ??$CreateDevice@VRenderDeviceD3D11@D3D11@Engine@Spectre@@@Engine@0Spectre@@QEAA?AV?$shared_ptr@VRenderDevice@Engine@Spectre@@@std@@UDeviceDescription@01@UOutputDescription@01@@Z; Spectre::Engine::Engine::CreateDevice<Spectre::Engine::D3D11::RenderDeviceD3D11>(Spectre::Engine::DeviceDescription,Spectre::Engine::OutputDescription)
0x180016624  mov     rcx, [rsp+208h+var_1C8]; this
0x180016629  test    rcx, rcx
0x18001662c  jz      short loc_180016633
0x18001662e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180016633  mov     rcx, [rbx]; this
0x180016636  call    ?SendEngineInitializedTelemetry@Engine@1Spectre@@IEAAXXZ; Spectre::Engine::Engine::SendEngineInitializedTelemetry(void)
0x18001663b  cmp     byte ptr [rsi+1Ch], 0
0x18001663f  jz      short loc_18001665D
0x180016641  lea     rdx, [rsp+208h+var_1D0]
0x180016646  mov     rcx, [rbx]
0x180016649  call    ?GetTelemetryTraceLogger@Engine@1Spectre@@QEBA?AV?$shared_ptr@VITelemetryTraceLogger@Utils@Spectre@@@std@@XZ; Spectre::Engine::Engine::GetTelemetryTraceLogger(void)
0x18001664e  mov     edi, 3
0x180016653  mov     dword ptr [rsp+208h+var_1D8], edi
0x180016657  cmp     qword ptr [rax], 0
0x18001665b  jnz     short loc_180016660
0x18001665d  xor     r12b, r12b
0x180016660  test    dil, 2
0x180016664  jz      short loc_18001667C
0x180016666  and     edi, 0FFFFFFFDh
0x180016669  mov     dword ptr [rsp+208h+var_1D8], edi
0x18001666d  mov     rcx, [rsp+208h+var_1C8]; this
0x180016672  test    rcx, rcx
0x180016675  jz      short loc_18001667C
0x180016677  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001667c  test    r12b, r12b
0x18001667f  jz      short loc_18001668A
0x180016681  mov     rcx, [rbx]; this
0x180016684  call    ?StartPerformanceThread@Engine@1Spectre@@IEAAXXZ; Spectre::Engine::Engine::StartPerformanceThread(void)
0x180016689  nop
0x18001668a  mov     rcx, [rsp+208h+var_150]; this
0x180016692  test    rcx, rcx
0x180016695  jz      short loc_18001669D
0x180016697  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18001669c  nop
0x18001669d  mov     rcx, [r14+8]; this
0x1800166a1  test    rcx, rcx
0x1800166a4  jz      short loc_1800166AC
0x1800166a6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800166ab  nop
0x1800166ac  mov     rcx, [r13+8]; this
0x1800166b0  test    rcx, rcx
0x1800166b3  jz      short loc_1800166BB
0x1800166b5  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800166ba  nop
0x1800166bb  mov     rcx, [rsp+208h+var_1C0]
0x1800166c0  mov     rcx, [rcx+8]; this
0x1800166c4  test    rcx, rcx
0x1800166c7  jz      short loc_1800166CE
0x1800166c9  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800166ce  mov     rax, rbx
0x1800166d1  mov     rcx, [rsp+208h+var_68]
0x1800166d9  xor     rcx, rsp; StackCookie
0x1800166dc  call    __security_check_cookie
0x1800166e1  lea     r11, [rsp+208h+var_38]
0x1800166e9  movaps  xmm6, xmmword ptr [r11-10h]
0x1800166ee  movaps  xmm7, xmmword ptr [r11-20h]
0x1800166f3  mov     rsp, r11
0x1800166f6  pop     r15
0x1800166f8  pop     r14
0x1800166fa  pop     r13
0x1800166fc  pop     r12
0x1800166fe  pop     rdi
0x1800166ff  pop     rsi
0x180016700  pop     rbx
0x180016701  retn
```
