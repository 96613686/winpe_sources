# Microsoft::Applications::Events::LogManagerImpl::LogManagerImpl(Microsoft::Applications::Events::ILogConfiguration &,bool)

- ea: `0x140110dfc`
- end: `0x140111ff8`
- name: `??0LogManagerImpl@Events@Applications@Microsoft@@QEAA@AEAVILogConfiguration@123@_N@Z`
- size: `4604`
- prototype: `__int64 __fastcall(Microsoft::Applications::Events::LogManagerImpl *__hidden this, struct Microsoft::Applications::Events::ILogConfiguration *, bool)`
- caller_count: `1`
- callee_count: `38`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14010f714`

## callees

- `0x140020e60`
- `0x14003a0f4`
- `0x14003a130`
- `0x14003a5c0`
- `0x14003a60c`
- `0x14003a630`
- `0x14007e088`
- `0x14007e14c`
- `0x14007f0f4`
- `0x140084a18`
- `0x140084b3c`
- `0x1400a93e4`
- `0x1400aaab8`
- `0x1400ab430`
- `0x1400bead4`
- `0x1400fe950`
- `0x1400fecc0`
- `0x1400feeb8`
- `0x1400ff188`
- `0x1400ff91c`
- `0x1401044d8`
- `0x1401045ec`
- `0x1401047fc`
- `0x140110dfc`
- `0x140113ff0`
- `0x140115d30`
- `0x140116870`
- `0x140116900`
- `0x140116b30`
- `0x140125740`
- `0x140128b94`
- `0x140129160`
- `0x140129d0c`
- `0x140135740`
- `0x14014091c`
- `0x14015fba8`
- `0x140166250`
- `0x140166990`

## string_xrefs

- `0x14011161a`: `primaryToken`
- `0x140111635`: `primaryToken`
- `0x14011125e`: `taskDispatcher`
- `0x1401115c5`: `cacheFilePath`
- `0x1401115e1`: `cacheFilePath`
- `0x140111661`: `cacheFilePath`
- `0x140111768`: `cacheFilePath`
- `0x14011192b`: `cacheFilePath`
- `0x140111baf`: `TaskDispatcher: External %p`
- `0x140111f17`: `Telemetry system created, starting up...`
- `0x140110f97`: `EventsSDK.AuthTokensController`
- `0x140110f90`: `New AuthTokensController instance`

## pseudocode

```c
// Hidden C++ exception states: #wind=34
Microsoft::Applications::Events::LogManagerImpl *__fastcall Microsoft::Applications::Events::LogManagerImpl::LogManagerImpl(
        Microsoft::Applications::Events::LogManagerImpl *this,
        struct Microsoft::Applications::Events::ILogConfiguration *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // r14
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  _QWORD *v8; // rax
  _QWORD *Module; // rdi
  _QWORD *v10; // rbx
  __int64 v11; // rax
  volatile signed __int32 *v12; // rbx
  volatile signed __int32 *v13; // rbx
  _QWORD *v14; // rdi
  _QWORD *v15; // rbx
  __int64 v16; // rax
  volatile signed __int32 *v17; // rbx
  volatile signed __int32 *v18; // rbx
  _QWORD *v19; // rdi
  _QWORD *v20; // rbx
  __int64 v21; // rax
  volatile signed __int32 *v22; // rbx
  volatile signed __int32 *v23; // rbx
  _QWORD *v24; // rbx
  _QWORD *v25; // rdi
  __int64 v26; // rax
  volatile signed __int32 *v27; // rbx
  volatile signed __int32 *v28; // rbx
  _QWORD *v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // rcx
  int v32; // edx
  Microsoft::Applications::Events::PlatformAbstraction *v33; // rcx
  int v34; // edx
  int v35; // edx
  int v36; // edx
  struct Microsoft::Applications::Events::IRuntimeConfig *v37; // rbx
  Microsoft::Applications::Events::PlatformAbstraction::PlatformAbstractionLayer *PAL; // rax
  Microsoft::Applications::Events::PlatformAbstraction *v39; // rcx
  Microsoft::Applications::Events::PlatformAbstraction::PlatformAbstractionLayer *v40; // rax
  __int64 v41; // rax
  int v42; // ecx
  _QWORD *v43; // rax
  __int64 v44; // r8
  __int64 v45; // rax
  int v46; // ecx
  const char *v47; // rdx
  __int64 v48; // rax
  int v49; // ecx
  const char *v50; // rdx
  size_t v51; // r8
  __int128 *v52; // rdi
  __int64 v53; // r8
  char *v54; // rbx
  __int64 trivial_1; // rax
  _OWORD *v56; // rdx
  __int64 v57; // rax
  size_t v58; // r8
  __int64 v59; // rbx
  unsigned __int64 v60; // rcx
  _QWORD *v61; // rax
  _QWORD *v62; // rax
  char *v63; // rcx
  _OWORD *v64; // rdx
  __int64 v65; // rax
  __int64 v66; // rax
  _OWORD *v67; // rdx
  __int64 v68; // rax
  _OWORD *v69; // rdx
  const char *v70; // r9
  void (__fastcall *v71)(char *, __int128 *, _QWORD *); // rbx
  __int64 v72; // rax
  Microsoft::Applications::Events::PlatformAbstraction *v73; // rcx
  const void *v74; // r9
  struct Microsoft::Applications::Events::PlatformAbstraction::PlatformAbstractionLayer *v75; // rax
  __int64 v76; // rcx
  volatile signed __int32 *v77; // rbx
  const void *v78; // r9
  __int64 *v79; // rax
  __int64 v80; // rcx
  __int64 v81; // rdx
  volatile signed __int32 *v82; // rbx
  volatile signed __int32 *v83; // rbx
  __int64 v84; // rbx
  __int64 v85; // rax
  __int64 v86; // rdx
  __int64 v87; // rcx
  const void *v88; // r9
  void *v89; // rbx
  __int64 v90; // rax
  void (__fastcall ***v91)(_QWORD, __int64); // rcx
  _OWORD *v92; // rbx
  _OWORD *v93; // rdx
  _QWORD *v94; // rdi
  char *v95; // rbx
  void *v96; // rbx
  __int64 v97; // rax
  __int64 v98; // rcx
  __int64 v99; // rcx
  _QWORD *v100; // rdi
  _QWORD *i; // rbx
  __int128 v103; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v104; // [rsp+50h] [rbp-B0h]
  __int64 v105; // [rsp+58h] [rbp-A8h]
  char *v106; // [rsp+60h] [rbp-A0h]
  Microsoft::Applications::Events::LogManagerImpl *v107; // [rsp+68h] [rbp-98h]
  _QWORD v108[5]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v109; // [rsp+98h] [rbp-68h] BYREF
  __int64 v110; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v111; // [rsp+B0h] [rbp-50h]
  _QWORD Src[2]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int64 v113; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v114; // [rsp+D0h] [rbp-30h]
  __int128 v115; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v116; // [rsp+E8h] [rbp-18h]
  unsigned __int64 v117; // [rsp+F0h] [rbp-10h]
  __int128 v118; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v119; // [rsp+108h] [rbp+8h]

  v107 = this;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *(_QWORD *)this = &Microsoft::Applications::Events::LogManagerImpl::`vftable'{for `Microsoft::Applications::Events::ILogController'};
  *((_QWORD *)this + 1) = &Microsoft::Applications::Events::LogManagerImpl::`vftable'{for `Microsoft::Applications::Events::IContextProvider'};
  *((_QWORD *)this + 2) = &Microsoft::Applications::Events::LogManagerImpl::`vftable'{for `Microsoft::Applications::Events::DebugEventDispatcher'};
  *((_QWORD *)this + 5) = 258;
  *((_OWORD *)this + 4) = 0;
  *((_OWORD *)this + 5) = 0;
  *((_OWORD *)this + 6) = 0;
  *((_OWORD *)this + 3) = 0;
  *((_DWORD *)this + 28) = -1;
  *((_DWORD *)this + 29) = 0;
  *((_QWORD *)this + 15) = 0;
  *((_QWORD *)this + 16) = 0;
  v4 = operator new(0x48u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  *((_QWORD *)this + 15) = v4;
  Microsoft::Applications::Events::ContextFieldsProvider::ContextFieldsProvider(
    (Microsoft::Applications::Events::LogManagerImpl *)((char *)this + 136),
    0);
  *((_QWORD *)this + 17) = &Microsoft::Applications::Events::ContextFieldsProvider::`vftable';
  *((_QWORD *)this + 37) = 0;
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  *((_QWORD *)this + 40) = 0;
  v5 = (_QWORD *)((char *)this + 328);
  *((_QWORD *)this + 41) = 0;
  *((_QWORD *)this + 42) = 0;
  *((_QWORD *)this + 43) = 0;
  *((_QWORD *)this + 44) = a2;
  *((_QWORD *)this + 45) = 0;
  *((_QWORD *)this + 46) = 0;
  v106 = (char *)this + 376;
  *((_QWORD *)this + 47) = &Microsoft::Applications::Events::AuthTokensController::`vftable';
  *((_QWORD *)this + 48) = 0;
  *((_QWORD *)this + 49) = 0;
  v6 = operator new(0x48u);
  *v6 = v6;
  v6[1] = v6;
  v6[2] = v6;
  *((_WORD *)v6 + 12) = 257;
  *((_QWORD *)this + 48) = v6;
  *((_QWORD *)this + 50) = 0;
  *((_QWORD *)this + 51) = 0;
  v7 = operator new(0x48u);
  *v7 = v7;
  v7[1] = v7;
  v7[2] = v7;
  *((_WORD *)v7 + 12) = 257;
  *((_QWORD *)this + 50) = v7;
  *((_QWORD *)this + 52) = 0;
  *((_QWORD *)this + 53) = 0;
  *((_QWORD *)this + 54) = 0;
  *((_BYTE *)this + 440) = 0;
  if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      4,
      "EventsSDK.AuthTokensController",
      "New AuthTokensController instance");
  *((_QWORD *)this + 56) = 0;
  *((_QWORD *)this + 57) = 0;
  *((_BYTE *)this + 464) = 0;
  *((_QWORD *)this + 59) = 0;
  Microsoft::Applications::Events::DebugEventSource::DebugEventSource((Microsoft::Applications::Events::LogManagerImpl *)((char *)this + 488));
  *((_WORD *)this + 268) = 513;
  *((_BYTE *)this + 538) = -1;
  *(_QWORD *)&v109 = (char *)this + 544;
  *((_QWORD *)this + 68) = 0;
  *((_QWORD *)this + 69) = 0;
  _mm_lfence();
  v8 = operator new(0x20u);
  *v8 = v8;
  v8[1] = v8;
  v8[2] = v8;
  *((_WORD *)v8 + 12) = 257;
  *((_QWORD *)this + 68) = v8;
  *((_QWORD *)this + 70) = &Microsoft::Applications::Events::EventFilterCollection::`vftable';
  *((_QWORD *)this + 71) = 0;
  *((_QWORD *)this + 72) = 2;
  *(_OWORD *)((char *)this + 600) = 0;
  *(_OWORD *)((char *)this + 616) = 0;
  *(_OWORD *)((char *)this + 632) = 0;
  *(_OWORD *)((char *)this + 584) = 0;
  *((_DWORD *)this + 162) = -1;
  *((_DWORD *)this + 163) = 0;
  *((_QWORD *)this + 82) = 0;
  *((_QWORD *)this + 83) = 0;
  *((_QWORD *)this + 84) = 0;
  *((_QWORD *)this + 85) = 0;
  *((_QWORD *)this + 86) = 0;
  *((_QWORD *)this + 87) = 0;
  *((_QWORD *)this + 88) = &Microsoft::Applications::Events::DataViewerCollection::`vftable';
  *((_QWORD *)this + 89) = 258;
  *((_OWORD *)this + 46) = 0;
  *((_OWORD *)this + 47) = 0;
  *((_OWORD *)this + 48) = 0;
  *((_OWORD *)this + 45) = 0;
  *((_DWORD *)this + 196) = -1;
  *((_DWORD *)this + 197) = 0;
  *((_QWORD *)this + 99) = 0;
  *((_QWORD *)this + 100) = 0;
  *((_QWORD *)this + 101) = 0;
  *((_QWORD *)this + 102) = 0;
  *((_QWORD *)this + 103) = 0;
  *((_QWORD *)this + 104) = 0;
  *((_QWORD *)this + 105) = 258;
  *((_OWORD *)this + 54) = 0;
  *((_OWORD *)this + 55) = 0;
  *((_OWORD *)this + 56) = 0;
  *((_OWORD *)this + 53) = 0;
  *((_DWORD *)this + 228) = -1;
  *((_DWORD *)this + 229) = 0;
  *((_QWORD *)this + 115) = 2;
  *((_OWORD *)this + 59) = 0;
  *((_OWORD *)this + 60) = 0;
  *((_OWORD *)this + 61) = 0;
  *((_OWORD *)this + 58) = 0;
  *((_DWORD *)this + 248) = -1;
  *((_DWORD *)this + 249) = 0;
  *((_QWORD *)this + 125) = 0;
  *((_QWORD *)this + 126) = 0;
  *(_OWORD *)((char *)this + 1016) = 0;
  *(_OWORD *)((char *)this + 1032) = 0;
  *(_OWORD *)((char *)this + 1048) = 0;
  *((_QWORD *)this + 133) = 0;
  *((_QWORD *)this + 134) = 0;
  *((_BYTE *)this + 1080) = 0;
  Module = (_QWORD *)Microsoft::Applications::Events::ILogConfiguration::GetModule(a2, &v109, "httpClient");
  v10 = (_QWORD *)*Module;
  if ( *Module )
    _castguard_slow_path_check_fastfail(*v10, 616, 0);
  else
    v10 = 0;
  v11 = Module[1];
  *Module = 0;
  Module[1] = 0;
  *((_QWORD *)this + 37) = v10;
  v12 = (volatile signed __int32 *)*((_QWORD *)this + 38);
  *((_QWORD *)this + 38) = v11;
  if ( v12 )
  {
    if ( _InterlockedExchangeAdd(v12 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
      if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
    }
  }
  v13 = (volatile signed __int32 *)*((_QWORD *)&v109 + 1);
  if ( *((_QWORD *)&v109 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v109 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
      if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    }
  }
  v14 = (_QWORD *)Microsoft::Applications::Events::ILogConfiguration::GetModule(a2, &v109, "taskDispatcher");
  v15 = (_QWORD *)*v14;
  if ( *v14 )
    _castguard_slow_path_check_fastfail(*v15, 560, 0);
  else
    v15 = 0;
  v16 = v14[1];
  *v14 = 0;
  v14[1] = 0;
  *((_QWORD *)this + 39) = v15;
  v17 = (volatile signed __int32 *)*((_QWORD *)this + 40);
  *((_QWORD *)this + 40) = v16;
  if ( v17 )
  {
    if ( _InterlockedExchangeAdd(v17 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v17)(v17);
      if ( _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    }
  }
  v18 = (volatile signed __int32 *)*((_QWORD *)&v109 + 1);
  if ( *((_QWORD *)&v109 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v109 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
      if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    }
  }
  v19 = (_QWORD *)Microsoft::Applications::Events::ILogConfiguration::GetModule(a2, &v109, "dataViewer");
  v20 = (_QWORD *)*v19;
  if ( *v19 )
    _castguard_check_failure_fastfail(*v20);
  else
    v20 = 0;
  v21 = v19[1];
  *v19 = 0;
  v19[1] = 0;
  *v5 = v20;
  v22 = (volatile signed __int32 *)*((_QWORD *)this + 42);
  *((_QWORD *)this + 42) = v21;
  if ( v22 )
  {
    if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
  }
  v23 = (volatile signed __int32 *)*((_QWORD *)&v109 + 1);
  if ( *((_QWORD *)&v109 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v109 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
      if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
    }
  }
  v24 = (_QWORD *)Microsoft::Applications::Events::ILogConfiguration::GetModule(a2, &v109, "decorator");
  if ( *v24 )
  {
    v25 = (_QWORD *)(*v24 - 8LL);
    _castguard_check_failure_fastfail(*v25);
  }
  else
  {
    v25 = 0;
  }
  v26 = v24[1];
  *v24 = 0;
  v24[1] = 0;
  *((_QWORD *)this + 3) = v25;
  v27 = (volatile signed __int32 *)*((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = v26;
  if ( v27 )
  {
    if ( _InterlockedExchangeAdd(v27 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v27)(v27);
      if ( _InterlockedExchangeAdd(v27 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v27 + 8LL))(v27);
    }
  }
  v28 = (volatile signed __int32 *)*((_QWORD *)&v109 + 1);
  if ( *((_QWORD *)&v109 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v109 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
      if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
    }
  }
  v29 = operator new(0x10u);
  *(_QWORD *)&v109 = v29;
  v30 = *((_QWORD *)this + 44);
  *v29 = &Microsoft::Applications::Events::RuntimeConfig_Default::`vftable';
  v29[1] = v30;
  Microsoft::Applications::Events::Variant::merge_map(v30, qword_1401E6150);
  v31 = *((_QWORD *)this + 43);
  *((_QWORD *)this + 43) = v29;
  if ( v31 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 176LL))(v31, 1);
  v32 = *(_DWORD *)(Microsoft::Applications::Events::ILogConfiguration::operator[](a2, "minimumTraceLevel") + 8);
  if ( v32 && (v34 = v32 - 1) != 0 )
  {
    v35 = v34 - 1;
    if ( v35 )
    {
      v36 = v35 - 1;
      if ( v36 && (unsigned int)(v36 - 1) < 2 )
        Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel = 1;
      else
        Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel = 2;
    }
    else
    {
      Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel = 3;
    }
  }
  else
  {
    Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel = 4;
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      4,
      "EventsSDK.LogManager",
      "New LogManager instance");
  }
  v37 = (struct Microsoft::Applications::Events::IRuntimeConfig *)*((_QWORD *)this + 43);
  PAL = Microsoft::Applications::Events::PlatformAbstraction::GetPAL(v33);
  Microsoft::Applications::Events::PlatformAbstraction::PlatformAbstractionLayer::initialize(PAL, v37);
  v40 = Microsoft::Applications::Events::PlatformAbstraction::GetPAL(v39);
  Microsoft::Applications::Events::PlatformAbstraction::PlatformAbstractionLayer::registerSemanticContext(
    v40,
    (Microsoft::Applications::Events::LogManagerImpl *)((char *)this + 136));
  Microsoft::Applications::Events::GetTempDirectory(Src);
  if ( !Microsoft::Applications::Events::ILogConfiguration::HasConfig(
          *((Microsoft::Applications::Events::ILogConfiguration **)this + 44),
          "cacheFilePath") )
    goto LABEL_65;
  v41 = Microsoft::Applications::Events::ILogConfiguration::operator[](*((_QWORD *)this + 44), "cacheFilePath");
  v42 = *(_DWORD *)(v41 + 88);
  if ( v42 == 3 )
  {
    v43 = *(_QWORD **)(v41 + 8);
  }
  else
  {
    if ( v42 != 4 )
    {
      if ( v42 )
        goto LABEL_65;
      goto LABEL_69;
    }
    v43 = (_QWORD *)(v41 + 16);
    if ( v43[3] > 0xFu )
      v43 = (_QWORD *)*v43;
  }
  if ( !v43 )
  {
LABEL_65:
    if ( Microsoft::Applications::Events::ILogConfiguration::HasConfig(
           *((Microsoft::Applications::Events::ILogConfiguration **)this + 44),
           "primaryToken") )
    {
      v45 = Microsoft::Applications::Events::ILogConfiguration::operator[](*((_QWORD *)this + 44), "primaryToken");
      v46 = *(_DWORD *)(v45 + 88);
      if ( v46 == 3 )
      {
        v47 = *(const char **)(v45 + 8);
      }
      else if ( v46 == 4 )
      {
        v47 = (const char *)(v45 + 16);
        if ( *(_QWORD *)(v45 + 40) > 0xFu )
          v47 = *(const char **)v47;
      }
      else
      {
        v47 = qword_140194AF8;
        if ( v46 )
          v47 = 0;
      }
      v118 = 0;
      v119 = 0u;
      v58 = -1;
      do
        ++v58;
      while ( v47[v58] );
      std::string::_Construct<1,char const *>(&v118, v47, v58);
      v59 = Microsoft::Applications::Events::tenantTokenToId(&v103, &v118);
      if ( &v118 != (__int128 *)v59 )
      {
        std::string::_Tidy_deallocate(&v118);
        v118 = *(_OWORD *)v59;
        v119 = *(_OWORD *)(v59 + 16);
        *(_QWORD *)(v59 + 16) = 0;
        *(_QWORD *)(v59 + 24) = 15;
        *(_BYTE *)v59 = 0;
      }
      std::string::_Tidy_deallocate(&v103);
      v60 = v113;
      if ( v113 )
      {
        v61 = Src;
        if ( v114 > 0xF )
          v61 = (_QWORD *)Src[0];
        if ( HIBYTE(v61[v113 / 8 - 1]) != 92 )
        {
          if ( v113 >= v114 )
          {
            std::string::_Reallocate_grow_by<_lambda_319d5e083f45f90dcdce5dce53cbb275_,char>(Src);
          }
          else
          {
            ++v113;
            v62 = Src;
            if ( v114 > 0xF )
              v62 = (_QWORD *)Src[0];
            *(_WORD *)((char *)v62 + v60) = 92;
          }
        }
      }
      std::string::append(Src);
      std::string::append(Src);
      std::string::_Tidy_deallocate(&v118);
    }
    else
    {
      v63 = (char *)Src;
      if ( v114 < 8 )
      {
        _mm_lfence();
        std::string::_Reallocate_for<_lambda_66f57f934f28d61049862f64df852ff0_,char const *>(Src, 8, v44, ":memory:");
      }
      else
      {
        if ( v114 > 0xF )
          v63 = (char *)Src[0];
        v113 = 8;
        strcpy(v63, ":memory:");
      }
    }
    *(_QWORD *)&v109 = &v103;
    v103 = 0;
    v104 = 0;
    v105 = 0;
    v64 = Src;
    if ( v114 > 0xF )
      v64 = (_OWORD *)Src[0];
    std::string::_Construct<2,char const *>((__int64)&v103, v64, v113);
    v65 = Microsoft::Applications::Events::ILogConfiguration::operator[](*((_QWORD *)this + 44), "cacheFilePath");
    Microsoft::Applications::Events::Variant::operator=(v65, &v103);
    goto LABEL_114;
  }
LABEL_69:
  v48 = Microsoft::Applications::Events::ILogConfiguration::operator[](*((_QWORD *)this + 44), "cacheFilePath");
  v49 = *(_DWORD *)(v48 + 88);
  if ( v49 == 3 )
  {
    v50 = *(const char **)(v48 + 8);
  }
  else if ( v49 == 4 )
  {
    v50 = (const char *)(v48 + 16);
    if ( *(_QWORD *)(v48 + 40) > 0xFu )
      v50 = *(const char **)v50;
  }
  else
  {
    v50 = qword_140194AF8;
    if ( v49 )
      v50 = 0;
  }
  v115 = 0;
  v116 = 0;
  v117 = 0;
  v51 = -1;
  do
    ++v51;
  while ( v50[v51] );
  std::string::_Construct<1,char const *>(&v115, v50, v51);
  v52 = &v115;
  if ( v117 > 0xF )
    v52 = (__int128 *)v115;
  v53 = v116;
  if ( !v116
    || (_mm_lfence(),
        v54 = (char *)v52 + v116,
        LOBYTE(v53) = 92,
        trivial_1 = _std_find_trivial_1(v52, (char *)v52 + v116, v53),
        (char *)trivial_1 == v54)
    || trivial_1 - (_QWORD)v52 == -1 )
  {
    std::string::append(Src);
    *(_QWORD *)&v109 = &v103;
    v103 = 0;
    v104 = 0;
    v105 = 0;
    v56 = Src;
    if ( v114 > 0xF )
      v56 = (_OWORD *)Src[0];
    std::string::_Construct<2,char const *>((__int64)&v103, v56, v113);
    v57 = Microsoft::Applications::Events::ILogConfiguration::operator[](*((_QWORD *)this + 44), "cacheFilePath");
    Microsoft::Applications::Events::Variant::operator=(v57, &v103);
  }
  std::string::_Tidy_deallocate(&v115);
LABEL_114:
  if ( Microsoft::Applications::Events::ILogConfiguration::HasConfig(
         *((Microsoft::Applications::Events::ILogConfiguration **)this + 44),
         "transmitProfiles") )
  {
    v66 = Microsoft::Applications::Events::ILogConfiguration::operator[](*((_QWORD *)this + 44), "transmitProfiles");
    v67 = (_OWORD *)(v66 + 16);
    v109 = 0;
    v110 = 0;
    v111 = 0;
    if ( *(_QWORD *)(v66 + 40) > 0xFu )
      v67 = *(_OWORD **)v67;
    std::string::_Construct<2,char const *>((__int64)&v109, v67, *(_QWORD *)(v66 + 32));
    if ( v110 )
    {
      if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 3 )
        Microsoft::Applications::Events::PlatformAbstraction::detail::log(
          3,
          "EventsSDK.LogManager",
          "Loading custom transmit profiles...");
      Microsoft::Applications::Events::LogManagerImpl::LoadTransmitProfiles(this, &v109);
    }
    std::string::_Tidy_deallocate(&v109);
  }
  if ( Microsoft::Applications::Events::ILogConfiguration::HasConfig(
         *((Microsoft::Applications::Events::ILogConfiguration **)this + 44),
         "startProfileName") )
  {
    v68 = Microsoft::Applications::Events::ILogConfiguration::operator[](*((_QWORD *)this + 44), "startProfileName");
    v69 = (_OWORD *)(v68 + 16);
    v109 = 0;
    v110 = 0;
    v111 = 0;
    if ( *(_QWORD *)(v68 + 40) > 0xFu )
      v69 = *(_OWORD **)v69;
    std::string::_Construct<2,char const *>((__int64)&v109, v69, *(_QWORD *)(v68 + 32));
    if ( v110 )
    {
      if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 3 )
      {
        v70 = (const char *)&v109;
        if ( v111 > 0xF )
          v70 = (const char *)v109;
        Microsoft::Applications::Events::PlatformAbstraction::detail::log(
          3,
          "EventsSDK.LogManager",
          "Setting custom transmit profile %s",
          v70);
      }
      Microsoft::Applications::Events::LogManagerImpl::SetTransmitProfile(this, &v109);
    }
    std::string::_Tidy_deallocate(&v109);
  }
  v71 = *(void (__fastcall **)(char *, __int128 *, _QWORD *))(*((_QWORD *)this + 17) + 232LL);
  v72 = Microsoft::Applications::Events::PlatformAbstraction::generateUuidString(&v109);
  Microsoft::Applications::Events::EventProperty::EventProperty(v108, v72, 0);
  v103 = 0;
  v104 = 0;
  v105 = 0;
  std::string::_Construct<1,char const *>(&v103, "act_session_id", 0xEu);
  v71((char *)this + 136, &v103, v108);
  std::string::_Tidy_deallocate(&v103);
  v108[0] = &Microsoft::Applications::Events::EventProperty::`vftable';
  Microsoft::Applications::Events::EventProperty::clear((Microsoft::Applications::Events::EventProperty *)v108);
  std::string::_Tidy_deallocate(&v109);
  if ( *v5 )
    (*(void (__fastcall **)(char *, char *))(*((_QWORD *)this + 88) + 8LL))((char *)this + 704, (char *)this + 328);
  v74 = (const void *)*((_QWORD *)this + 39);
  if ( v74 )
  {
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        4,
        "EventsSDK.LogManager",
        "TaskDispatcher: External %p",
        v74);
  }
  else
  {
    v75 = Microsoft::Applications::Events::PlatformAbstraction::GetPAL(v73);
    Microsoft::Applications::Events::PlatformAbstraction::PlatformAbstractionLayer::getDefaultTaskDispatcher(v75, &v109);
    v76 = *((_QWORD *)&v109 + 1);
    *((_QWORD *)this + 39) = v109;
    v77 = (volatile signed __int32 *)*((_QWORD *)this + 40);
    *((_QWORD *)this + 40) = v76;
    if ( v77 )
    {
      if ( _InterlockedExchangeAdd(v77 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v77)(v77);
        if ( _InterlockedExchangeAdd(v77 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v77 + 8LL))(v77);
      }
    }
  }
  Microsoft::Applications::Events::ILogConfiguration::operator[](a2, "sdkmode");
  v78 = (const void *)*((_QWORD *)this + 37);
  if ( v78 )
  {
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        4,
        "EventsSDK.LogManager",
        "HttpClient: External %p",
        v78);
  }
  else
  {
    v79 = (__int64 *)Microsoft::Applications::Events::HttpClientFactory::Create(&v109);
    v80 = *v79;
    v81 = v79[1];
    *v79 = 0;
    v79[1] = 0;
    *((_QWORD *)this + 37) = v80;
    v82 = (volatile signed __int32 *)*((_QWORD *)this + 38);
    *((_QWORD *)this + 38) = v81;
    if ( v82 )
    {
      if ( _InterlockedExchangeAdd(v82 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v82)(v82);
        if ( _InterlockedExchangeAdd(v82 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v82 + 8LL))(v82);
      }
    }
    v83 = (volatile signed __int32 *)*((_QWORD *)&v109 + 1);
    if ( *((_QWORD *)&v109 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v109 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v83)(v83);
        if ( _InterlockedExchangeAdd(v83 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v83 + 8LL))(v83);
      }
    }
    v84 = *((_QWORD *)this + 37);
    if ( v84 )
    {
      _castguard_slow_path_check_fastfail(*(_QWORD *)v84, 616, 0);
      v85 = Microsoft::Applications::Events::ILogConfiguration::operator[](*((_QWORD *)this + 44), "http");
      LOBYTE(v86) = *(_BYTE *)(Microsoft::Applications::Events::Variant::operator[](v85, "msRootCheck") + 8);
      v87 = *(_QWORD *)(v84 + 168);
      if ( v87 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v87 + 56LL))(v87, v86);
      else
        *(_BYTE *)(v84 + 112) = v86;
    }
  }
  v88 = (const void *)*((_QWORD *)this + 45);
  if ( v88 )
  {
    if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
      Microsoft::Applications::Events::PlatformAbstraction::detail::log(
        4,
        "EventsSDK.LogManager",
        "BandwidthController: External %p",
        v88);
  }
  else
  {
    *((_QWORD *)this + 45) = *((_QWORD *)this + 46);
  }
  if ( !*((_QWORD *)this + 45) && Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      4,
      "EventsSDK.LogManager",
      "BandwidthController: None");
  v89 = operator new(0x288u);
  *(_QWORD *)&v109 = v89;
  memset(v89, 0, 0x288u);
  v90 = Microsoft::Applications::Events::OfflineStorageHandler::OfflineStorageHandler(
          (Microsoft::Applications::Events::OfflineStorageHandler *)v89,
          this,
          *((struct Microsoft::Applications::Events::IRuntimeConfig **)this + 43),
          *((struct Microsoft::Applications::Events::ITaskDispatcher **)this + 39));
  v91 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 56);
  *((_QWORD *)this + 56) = v90;
  if ( v91 )
    (**v91)(v91, 1);
  v92 = operator new(0x38u);
  *(_QWORD *)&v109 = v92;
  *v92 = 0;
  v92[1] = 0;
  v92[2] = 0;
  *((_QWORD *)v92 + 6) = 0;
  *(_QWORD *)v92 = 0;
  *(_OWORD *)((char *)v92 + 8) = 0;
  *((_QWORD *)v92 + 3) = 0;
  *((_QWORD *)v92 + 4) = 0;
  v93 = Src;
  if ( v114 > 0xF )
    v93 = (_OWORD *)Src[0];
  std::string::_Construct<2,char const *>((__int64)v92 + 8, v93, v113);
  *((_BYTE *)v92 + 40) = 0;
  *((_QWORD *)v92 + 6) = 0;
  v94 = (_QWORD *)*((_QWORD *)this + 57);
  *((_QWORD *)this + 57) = v92;
  if ( v94 )
  {
    v95 = (char *)v94[6];
    if ( v95 )
    {
      std::string::_Tidy_deallocate(v95 + 8);
      operator delete(v95, (const struct std::nothrow_t *)0x28);
    }
    std::string::_Tidy_deallocate(v94 + 1);
    operator delete(v94, (const struct std::nothrow_t *)0x38);
  }
  v96 = operator new(0x1130u);
  *(_QWORD *)&v109 = v96;
  memset(v96, 0, 0x1130u);
  v97 = Microsoft::Applications::Events::TelemetrySystem::TelemetrySystem(
          (Microsoft::Applications::Events::TelemetrySystem *)v96,
          this,
          *((struct Microsoft::Applications::Events::IRuntimeConfig **)this + 43),
          *((struct Microsoft::Applications::Events::IOfflineStorage **)this + 56),
          *((struct Microsoft::Applications::Events::IHttpClient **)this + 37),
          *((struct Microsoft::Applications::Events::ITaskDispatcher **)this + 39),
          *((struct Microsoft::Applications::Events::IBandwidthController **)this + 45),
          *((struct Microsoft::Applications::Events::LogSessionDataProvider **)this + 57));
  v98 = *((_QWORD *)this + 59);
  *((_QWORD *)this + 59) = v97;
  if ( v98 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v98 + 8LL))(v98, 1);
  if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 4 )
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      4,
      "EventsSDK.LogManager",
      "Telemetry system created, starting up...");
  v99 = *((_QWORD *)this + 59);
  if ( v99 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 16LL))(v99);
    *((_BYTE *)this + 464) = 1;
  }
  if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 3 )
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(3, "EventsSDK.LogManager", "Initializing Modules");
  v100 = (_QWORD *)*((_QWORD *)this + 86);
  for ( i = (_QWORD *)*((_QWORD *)this + 85); i != v100; ++i )
    (*(void (__fastcall **)(_QWORD, Microsoft::Applications::Events::LogManagerImpl *))(*(_QWORD *)*i + 8LL))(*i, this);
  if ( Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel >= 3 )
    Microsoft::Applications::Events::PlatformAbstraction::detail::log(
      3,
      "EventsSDK.LogManager",
      "Started up and running");
  *((_BYTE *)this + 480) = 1;
  std::string::_Tidy_deallocate(Src);
  return this;
}

```

## disassembly

```asm
0x140110dfc  mov     [rsp-8+arg_10], rbx
0x140110e01  push    rbp
0x140110e02  push    rsi
0x140110e03  push    rdi
0x140110e04  push    r12
0x140110e06  push    r13
0x140110e08  push    r14
0x140110e0a  push    r15
0x140110e0c  lea     rbp, [rsp-20h]
0x140110e11  sub     rsp, 120h
0x140110e18  mov     rax, cs:__security_cookie
0x140110e1f  xor     rax, rsp
0x140110e22  mov     [rbp+50h+var_38], rax
0x140110e26  mov     r15, rdx
0x140110e29  mov     rsi, rcx
0x140110e2c  mov     [rsp+150h+var_E8], rcx
0x140110e31  xor     edi, edi
0x140110e33  mov     [rcx+18h], rdi
0x140110e37  mov     [rcx+20h], rdi
0x140110e3b  lea     rax, ??_7LogManagerImpl@Events@Applications@Microsoft@@6BILogController@123@@; const Microsoft::Applications::Events::LogManagerImpl::`vftable'{for `Microsoft::Applications::Events::ILogController'}
0x140110e42  mov     [rcx], rax
0x140110e45  lea     rax, ??_7LogManagerImpl@Events@Applications@Microsoft@@6BIContextProvider@123@@; const Microsoft::Applications::Events::LogManagerImpl::`vftable'{for `Microsoft::Applications::Events::IContextProvider'}
0x140110e4c  mov     [rcx+8], rax
0x140110e50  lea     rax, ??_7LogManagerImpl@Events@Applications@Microsoft@@6BDebugEventDispatcher@123@@; const Microsoft::Applications::Events::LogManagerImpl::`vftable'{for `Microsoft::Applications::Events::DebugEventDispatcher'}
0x140110e57  mov     [rcx+10h], rax
0x140110e5b  mov     qword ptr [rcx+28h], 102h
0x140110e63  xorps   xmm0, xmm0
0x140110e66  movups  xmmword ptr [rcx+40h], xmm0
0x140110e6a  movups  xmmword ptr [rcx+50h], xmm0
0x140110e6e  movups  xmmword ptr [rcx+60h], xmm0
0x140110e72  xorps   xmm1, xmm1
0x140110e75  movdqu  xmmword ptr [rcx+30h], xmm1
0x140110e7a  mov     dword ptr [rcx+70h], 0FFFFFFFFh
0x140110e81  mov     [rcx+74h], edi
0x140110e84  mov     [rcx+78h], rdi
0x140110e88  mov     [rcx+80h], rdi
0x140110e8f  lea     r13d, [rdi+48h]
0x140110e93  mov     ecx, r13d; Size
0x140110e96  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140110e9b  mov     [rax], rax
0x140110e9e  mov     [rax+8], rax
0x140110ea2  mov     [rax+10h], rax
0x140110ea6  mov     word ptr [rax+18h], 101h
0x140110eac  mov     [rsi+78h], rax
0x140110eb0  lea     r12, [rsi+88h]
0x140110eb7  xor     edx, edx; struct Microsoft::Applications::Events::ContextFieldsProvider *
0x140110eb9  mov     rcx, r12; this
0x140110ebc  call    ??0ContextFieldsProvider@Events@Applications@Microsoft@@QEAA@PEAV0123@@Z; Microsoft::Applications::Events::ContextFieldsProvider::ContextFieldsProvider(Microsoft::Applications::Events::ContextFieldsProvider *)
0x140110ec1  lea     rax, ??_7ContextFieldsProvider@Events@Applications@Microsoft@@6B@; const Microsoft::Applications::Events::ContextFieldsProvider::`vftable'
0x140110ec8  mov     [r12], rax
0x140110ecc  mov     [rsi+128h], rdi
0x140110ed3  mov     [rsi+130h], rdi
0x140110eda  mov     [rsi+138h], rdi
0x140110ee1  mov     [rsi+140h], rdi
0x140110ee8  lea     r14, [rsi+148h]
0x140110eef  mov     [r14], rdi
0x140110ef2  mov     [r14+8], rdi
0x140110ef6  mov     [rsi+158h], rdi
0x140110efd  mov     [rsi+160h], r15
0x140110f04  mov     [rsi+168h], rdi
0x140110f0b  mov     [rsi+170h], rdi
0x140110f12  lea     rdi, [rsi+178h]
0x140110f19  mov     [rsp+150h+var_F0], rdi
0x140110f1e  lea     rax, ??_7AuthTokensController@Events@Applications@Microsoft@@6B@; const Microsoft::Applications::Events::AuthTokensController::`vftable'
0x140110f25  mov     [rdi], rax
0x140110f28  xor     edx, edx
0x140110f2a  mov     [rdi+8], rdx
0x140110f2e  mov     [rdi+10h], rdx
0x140110f32  mov     ecx, r13d; Size
0x140110f35  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140110f3a  mov     [rax], rax
0x140110f3d  mov     [rax+8], rax
0x140110f41  mov     [rax+10h], rax
0x140110f45  mov     word ptr [rax+18h], 101h
0x140110f4b  mov     [rdi+8], rax
0x140110f4f  xor     eax, eax
0x140110f51  mov     [rdi+18h], rax
0x140110f55  mov     [rdi+20h], rax
0x140110f59  mov     ecx, r13d; Size
0x140110f5c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140110f61  mov     [rax], rax
0x140110f64  mov     [rax+8], rax
0x140110f68  mov     [rax+10h], rax
0x140110f6c  mov     word ptr [rax+18h], 101h
0x140110f72  mov     [rdi+18h], rax
0x140110f76  xor     eax, eax
0x140110f78  mov     [rdi+28h], rax
0x140110f7c  mov     [rdi+30h], rax
0x140110f80  mov     [rdi+38h], rax
0x140110f84  mov     [rdi+40h], al
0x140110f87  cmp     cs:?g_logLevel@detail@PlatformAbstraction@Events@Applications@Microsoft@@3W4LogLevel@2345@A, 4; Microsoft::Applications::Events::PlatformAbstraction::LogLevel Microsoft::Applications::Events::PlatformAbstraction::detail::g_logLevel
0x140110f8e  jl      short loc_140110FA7
0x140110f90  lea     r8, aNewAuthtokensc; "New AuthTokensController instance"
0x140110f97  lea     rdx, aEventssdkAutht; "EventsSDK.AuthTokensController"
0x140110f9e  lea     ecx, [rax+4]
0x140110fa1  call    ?log@detail@PlatformAbstraction@Events@Applications@Microsoft@@YAXW4LogLevel@2345@PEBD1ZZ; Microsoft::Applications::Events::PlatformAbstraction::detail::log(Microsoft::Applications::Events::PlatformAbstraction::LogLevel,char const *,char const *,...)
0x140110fa6  nop
0x140110fa7  xor     edi, edi
0x140110fa9  mov     [rsi+1C0h], rdi
0x140110fb0  mov     [rsi+1C8h], rdi
0x140110fb7  mov     [rsi+1D0h], dil
0x140110fbe  mov     [rsi+1D8h], rdi
0x140110fc5  lea     rcx, [rsi+1E8h]; this
0x140110fcc  call    ??0DebugEventSource@Events@Applications@Microsoft@@QEAA@XZ; Microsoft::Applications::Events::DebugEventSource::DebugEventSource(void)
0x140110fd1  nop
0x140110fd2  lea     rax, [rsi+218h]
0x140110fd9  mov     word ptr [rax], 201h
0x140110fde  mov     byte ptr [rax+2], 0FFh
0x140110fe2  lea     rbx, [rax+8]
0x140110fe6  mov     qword ptr [rbp+50h+var_B8], rbx
0x140110fea  mov     [rbx], rdi
0x140110fed  mov     [rbx+8], rdi
0x140110ff1  lfence
0x140110ff4  lea     ecx, [rdi+20h]; Size
0x140110ff7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140110ffc  mov     [rax], rax
0x140110fff  mov     [rax+8], rax
0x140111003  mov     [rax+10h], rax
0x140111007  mov     word ptr [rax+18h], 101h
0x14011100d  mov     [rbx], rax
0x140111010  lea     rax, ??_7EventFilterCollection@Events@Applications@Microsoft@@6B@; const Microsoft::Applications::Events::EventFilterCollection::`vftable'
0x140111017  mov     [rsi+230h], rax
0x14011101e  mov     [rsi+238h], rdi
0x140111025  mov     qword ptr [rsi+240h], 2
0x140111030  xorps   xmm0, xmm0
0x140111033  movups  xmmword ptr [rsi+258h], xmm0
0x14011103a  movups  xmmword ptr [rsi+268h], xmm0
0x140111041  movups  xmmword ptr [rsi+278h], xmm0
0x140111048  xorps   xmm1, xmm1
0x14011104b  movdqu  xmmword ptr [rsi+248h], xmm1
0x140111053  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140111057  mov     [rsi+288h], ecx
0x14011105d  mov     [rsi+28Ch], edi
0x140111063  mov     [rsi+290h], rdi
0x14011106a  mov     [rsi+298h], rdi
0x140111071  mov     [rsi+2A0h], rdi
0x140111078  mov     [rsi+2A8h], rdi
0x14011107f  mov     [rsi+2B0h], rdi
0x140111086  mov     [rsi+2B8h], rdi
0x14011108d  lea     r13, [rsi+2C0h]
0x140111094  lea     rax, ??_7DataViewerCollection@Events@Applications@Microsoft@@6B@; const Microsoft::Applications::Events::DataViewerCollection::`vftable'
0x14011109b  mov     [r13+0], rax
0x14011109f  mov     qword ptr [r13+8], 102h
0x1401110a7  movups  xmmword ptr [r13+20h], xmm0
0x1401110ac  movups  xmmword ptr [r13+30h], xmm0
0x1401110b1  movups  xmmword ptr [r13+40h], xmm0
0x1401110b6  movdqu  xmmword ptr [r13+10h], xmm1
0x1401110bc  mov     [r13+50h], ecx
0x1401110c0  mov     [r13+54h], edi
0x1401110c4  mov     [r13+58h], rdi
0x1401110c8  mov     [r13+60h], rdi
0x1401110cc  mov     [r13+68h], rdi
0x1401110d0  mov     [rsi+330h], rdi
0x1401110d7  mov     [rsi+338h], rdi
0x1401110de  mov     [rsi+340h], rdi
0x1401110e5  mov     qword ptr [rsi+348h], 102h
0x1401110f0  movups  xmmword ptr [rsi+360h], xmm0
0x1401110f7  movups  xmmword ptr [rsi+370h], xmm0
0x1401110fe  movups  xmmword ptr [rsi+380h], xmm0
0x140111105  movdqu  xmmword ptr [rsi+350h], xmm1
0x14011110d  mov     [rsi+390h], ecx
0x140111113  mov     [rsi+394h], edi
0x140111119  mov     qword ptr [rsi+398h], 2
0x140111124  movups  xmmword ptr [rsi+3B0h], xmm0
0x14011112b  movups  xmmword ptr [rsi+3C0h], xmm0
0x140111132  movups  xmmword ptr [rsi+3D0h], xmm0
0x140111139  movdqu  xmmword ptr [rsi+3A0h], xmm1
0x140111141  mov     [rsi+3E0h], ecx
0x140111147  mov     [rsi+3E4h], edi
0x14011114d  mov     [rsi+3E8h], rdi
0x140111154  mov     [rsi+3F0h], rdi
0x14011115b  xor     eax, eax
0x14011115d  movups  xmmword ptr [rsi+3F8h], xmm0
0x140111164  movups  xmmword ptr [rsi+408h], xmm0
0x14011116b  movups  xmmword ptr [rsi+418h], xmm0
0x140111172  mov     [rsi+428h], rax
0x140111179  mov     [rsi+430h], rdi
0x140111180  mov     [rsi+438h], dil
0x140111187  lea     r8, aHttpclient; "httpClient"
0x14011118e  lea     rdx, [rbp+50h+var_B8]
0x140111192  mov     rcx, r15
0x140111195  call    ?GetModule@ILogConfiguration@Events@Applications@Microsoft@@QEAA?AV?$shared_ptr@VIModule@Events@Applications@Microsoft@@@std@@PEBD@Z; Microsoft::Applications::Events::ILogConfiguration::GetModule(char const *)
0x14011119a  mov     rdi, rax
0x14011119d  mov     rbx, [rax]
0x1401111a0  xor     ecx, ecx
0x1401111a2  test    rbx, rbx
0x1401111a5  jz      short loc_1401111BB
0x1401111a7  xor     r8d, r8d
0x1401111aa  mov     edx, 268h
0x1401111af  mov     rcx, [rbx]
0x1401111b2  call    __castguard_slow_path_check_fastfail
0x1401111b7  xor     ecx, ecx
0x1401111b9  jmp     short loc_1401111BE
0x1401111bb  mov     rbx, rcx
0x1401111be  mov     rax, [rdi+8]
0x1401111c2  mov     [rdi], rcx
0x1401111c5  mov     [rdi+8], rcx
0x1401111c9  mov     [rsi+128h], rbx
0x1401111d0  mov     rbx, [rsi+130h]
0x1401111d7  mov     [rsi+130h], rax
0x1401111de  test    rbx, rbx
0x1401111e1  jz      short loc_14011121C
0x1401111e3  or      eax, 0FFFFFFFFh
0x1401111e6  lock xadd [rbx+8], eax
0x1401111eb  cmp     eax, 1
0x1401111ee  jnz     short loc_14011121C
0x1401111f0  mov     rax, [rbx]
0x1401111f3  mov     rcx, rbx
0x1401111f6  mov     rax, [rax]
0x1401111f9  call    cs:__guard_dispatch_icall_fptr
0x1401111ff  or      eax, 0FFFFFFFFh
0x140111202  lock xadd [rbx+0Ch], eax
0x140111207  cmp     eax, 1
0x14011120a  jnz     short loc_14011121C
0x14011120c  mov     rax, [rbx]
0x14011120f  mov     rcx, rbx
0x140111212  mov     rax, [rax+8]
0x140111216  call    cs:__guard_dispatch_icall_fptr
0x14011121c  mov     rbx, qword ptr [rbp+50h+var_B8+8]
0x140111220  test    rbx, rbx
0x140111223  jz      short loc_14011125E
0x140111225  or      eax, 0FFFFFFFFh
0x140111228  lock xadd [rbx+8], eax
0x14011122d  cmp     eax, 1
0x140111230  jnz     short loc_14011125E
0x140111232  mov     rax, [rbx]
0x140111235  mov     rcx, rbx
0x140111238  mov     rax, [rax]
0x14011123b  call    cs:__guard_dispatch_icall_fptr
0x140111241  or      eax, 0FFFFFFFFh
0x140111244  lock xadd [rbx+0Ch], eax
0x140111249  cmp     eax, 1
0x14011124c  jnz     short loc_14011125E
0x14011124e  mov     rax, [rbx]
0x140111251  mov     rcx, rbx
0x140111254  mov     rax, [rax+8]
0x140111258  call    cs:__guard_dispatch_icall_fptr
0x14011125e  lea     r8, aTaskdispatcher_0; "taskDispatcher"
0x140111265  lea     rdx, [rbp+50h+var_B8]
0x140111269  mov     rcx, r15
0x14011126c  call    ?GetModule@ILogConfiguration@Events@Applications@Microsoft@@QEAA?AV?$shared_ptr@VIModule@Events@Applications@Microsoft@@@std@@PEBD@Z; Microsoft::Applications::Events::ILogConfiguration::GetModule(char const *)
0x140111271  mov     rdi, rax
0x140111274  mov     rbx, [rax]
0x140111277  xor     ecx, ecx
0x140111279  test    rbx, rbx
0x14011127c  jz      short loc_140111292
0x14011127e  xor     r8d, r8d
0x140111281  mov     edx, 230h
0x140111286  mov     rcx, [rbx]
0x140111289  call    __castguard_slow_path_check_fastfail
0x14011128e  xor     ecx, ecx
0x140111290  jmp     short loc_140111295
0x140111292  mov     rbx, rcx
0x140111295  mov     rax, [rdi+8]
0x140111299  mov     [rdi], rcx
0x14011129c  mov     [rdi+8], rcx
0x1401112a0  mov     [rsi+138h], rbx
0x1401112a7  mov     rbx, [rsi+140h]
0x1401112ae  mov     [rsi+140h], rax
0x1401112b5  test    rbx, rbx
0x1401112b8  jz      short loc_1401112F3
0x1401112ba  or      eax, 0FFFFFFFFh
0x1401112bd  lock xadd [rbx+8], eax
0x1401112c2  cmp     eax, 1
0x1401112c5  jnz     short loc_1401112F3
0x1401112c7  mov     rax, [rbx]
0x1401112ca  mov     rcx, rbx
0x1401112cd  mov     rax, [rax]
0x1401112d0  call    cs:__guard_dispatch_icall_fptr
0x1401112d6  or      eax, 0FFFFFFFFh
0x1401112d9  lock xadd [rbx+0Ch], eax
0x1401112de  cmp     eax, 1
0x1401112e1  jnz     short loc_1401112F3
0x1401112e3  mov     rax, [rbx]
0x1401112e6  mov     rcx, rbx
0x1401112e9  mov     rax, [rax+8]
0x1401112ed  call    cs:__guard_dispatch_icall_fptr
0x1401112f3  mov     rbx, qword ptr [rbp+50h+var_B8+8]
0x1401112f7  test    rbx, rbx
0x1401112fa  jz      short loc_140111335
0x1401112fc  or      eax, 0FFFFFFFFh
0x1401112ff  lock xadd [rbx+8], eax
0x140111304  cmp     eax, 1
0x140111307  jnz     short loc_140111335
0x140111309  mov     rax, [rbx]
0x14011130c  mov     rcx, rbx
0x14011130f  mov     rax, [rax]
0x140111312  call    cs:__guard_dispatch_icall_fptr
0x140111318  or      eax, 0FFFFFFFFh
0x14011131b  lock xadd [rbx+0Ch], eax
0x140111320  cmp     eax, 1
0x140111323  jnz     short loc_140111335
0x140111325  mov     rax, [rbx]
0x140111328  mov     rcx, rbx
0x14011132b  mov     rax, [rax+8]
0x14011132f  call    cs:__guard_dispatch_icall_fptr
0x140111335  lea     r8, aDataviewer; "dataViewer"
0x14011133c  lea     rdx, [rbp+50h+var_B8]
0x140111340  mov     rcx, r15
0x140111343  call    ?GetModule@ILogConfiguration@Events@Applications@Microsoft@@QEAA?AV?$shared_ptr@VIModule@Events@Applications@Microsoft@@@std@@PEBD@Z; Microsoft::Applications::Events::ILogConfiguration::GetModule(char const *)
  ... truncated ...
```
