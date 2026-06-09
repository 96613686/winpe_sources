# DllMain

- ea: `0x18000f0c0`
- end: `0x18000f264`
- name: `DllMain`
- size: `420`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180017334`

## callees

- `0x18000f0c0`
- `0x18000f26c`
- `0x180018638`
- `0x18001865c`
- `0x180018800`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000f0d3`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000f0d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000f1db`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000f1db`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18000f22b`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18000f22b`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  __int64 v3; // rdx
  __int64 v4; // rdx
  __int64 v5; // rdx
  __int64 v6; // r8
  _QWORD *v7; // rbx
  TRACEHANDLE v8; // rcx
  HMODULE phModule; // [rsp+48h] [rbp+20h] BYREF

  if ( fdwReason == 1 )
  {
    DisableThreadLibraryCalls(hinstDLL);
    McGenEventRegister_EventRegister(
      Microsoft_Windows_MediaFoundation_Performance,
      v3,
      Microsoft_Windows_MediaFoundation_Performance_Context,
      Microsoft_Windows_MediaFoundation_Performance_Context);
    WPP_INIT_CONTROL_ARRAY();
    qword_180069818 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_PIPELINE;
    WPP_REGISTRATION_GUIDS = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_PLATFORM;
    qword_180069820 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_CORE_SINKS;
    qword_180069828 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_CORE_SOURCES;
    qword_180069830 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_NETWORK;
    qword_180069838 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_CORE_MFTS;
    qword_180069840 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_PLAY;
    qword_180069848 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_CAPTURE_ENGINE;
    qword_180069850 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_VIDEO_PROCESSOR;
    qword_180069858 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_PIPELINE_HIGH_VOLUME;
    qword_180069860 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_TEMP_DEBUG_REFCOUNT_TRACE;
    qword_180069868 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_PERSAMPLE_INFO_TRACE;
    qword_180069870 = (__int64)&WPP_ThisDir_CTLGUID_CTRLGUID_MF_CAMERA_SETTINGS_HANDLERS;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    WppInitUm();
    phModule = 0;
    GetModuleHandleExW(5u, (LPCWSTR)DllMain, &phModule);
    McGenEventRegister_EventRegister(
      Microsoft_Windows_MF,
      v4,
      Microsoft_Windows_MF_Context,
      Microsoft_Windows_MF_Context);
  }
  else if ( !fdwReason )
  {
    McGenEventUnregister_EventUnregister(Microsoft_Windows_MediaFoundation_Performance_Context, fdwReason, lpvReserved);
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      while ( v7 )
      {
        v8 = v7[1];
        if ( v8 )
        {
          UnregisterTraceGuids(v8);
          v7[1] = 0;
        }
        v7 = (_QWORD *)*v7;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
    McGenEventUnregister_EventUnregister(Microsoft_Windows_MF_Context, v5, v6);
  }
  return 1;
}

```

## disassembly

```asm
0x18000f0c0  mov     [rsp+arg_0], rbx
0x18000f0c5  push    rdi
0x18000f0c6  sub     rsp, 20h
0x18000f0ca  cmp     edx, 1
0x18000f0cd  jnz     loc_18000F1FD
0x18000f0d3  call    cs:__imp_DisableThreadLibraryCalls
0x18000f0d9  lea     r9, Microsoft_Windows_MediaFoundation_Performance_Context
0x18000f0e0  lea     r8, Microsoft_Windows_MediaFoundation_Performance_Context
0x18000f0e7  lea     rcx, Microsoft_Windows_MediaFoundation_Performance
0x18000f0ee  call    McGenEventRegister_EventRegister
0x18000f0f3  call    WPP_INIT_CONTROL_ARRAY
0x18000f0f8  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_PIPELINE
0x18000f0ff  mov     cs:qword_180069818, rax
0x18000f106  lea     rdx, WPP_ThisDir_CTLGUID_CTRLGUID_MF_PLATFORM
0x18000f10d  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_CORE_SINKS
0x18000f114  mov     cs:WPP_REGISTRATION_GUIDS, rdx
0x18000f11b  mov     cs:qword_180069820, rax
0x18000f122  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_CORE_SOURCES
0x18000f129  mov     cs:qword_180069828, rax
0x18000f130  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_NETWORK
0x18000f137  mov     cs:qword_180069830, rax
0x18000f13e  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_CORE_MFTS
0x18000f145  mov     cs:qword_180069838, rax
0x18000f14c  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_PLAY
0x18000f153  mov     cs:qword_180069840, rax
0x18000f15a  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_CAPTURE_ENGINE
0x18000f161  mov     cs:qword_180069848, rax
0x18000f168  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_VIDEO_PROCESSOR
0x18000f16f  mov     cs:qword_180069850, rax
0x18000f176  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_PIPELINE_HIGH_VOLUME
0x18000f17d  mov     cs:qword_180069858, rax
0x18000f184  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_TEMP_DEBUG_REFCOUNT_TRACE
0x18000f18b  mov     cs:qword_180069860, rax
0x18000f192  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_PERSAMPLE_INFO_TRACE
0x18000f199  mov     cs:qword_180069868, rax
0x18000f1a0  lea     rax, WPP_ThisDir_CTLGUID_CTRLGUID_MF_CAMERA_SETTINGS_HANDLERS
0x18000f1a7  mov     cs:qword_180069870, rax
0x18000f1ae  lea     rax, WPP_MAIN_CB
0x18000f1b5  mov     cs:WPP_GLOBAL_Control, rax
0x18000f1bc  call    WppInitUm
0x18000f1c1  lea     r8, [rsp+28h+phModule]; phModule
0x18000f1c6  mov     [rsp+28h+phModule], 0
0x18000f1cf  lea     rdx, DllMain; lpModuleName
0x18000f1d6  mov     ecx, 5; dwFlags
0x18000f1db  call    cs:__imp_GetModuleHandleExW
0x18000f1e1  lea     r9, Microsoft_Windows_MF_Context
0x18000f1e8  lea     r8, Microsoft_Windows_MF_Context
0x18000f1ef  lea     rcx, Microsoft_Windows_MF
0x18000f1f6  call    McGenEventRegister_EventRegister
0x18000f1fb  jmp     short loc_18000F254
0x18000f1fd  test    edx, edx
0x18000f1ff  jnz     short loc_18000F254
0x18000f201  lea     rcx, Microsoft_Windows_MediaFoundation_Performance_Context
0x18000f208  call    McGenEventUnregister_EventUnregister
0x18000f20d  mov     rbx, cs:WPP_GLOBAL_Control
0x18000f214  lea     rdi, WPP_GLOBAL_Control
0x18000f21b  cmp     rbx, rdi
0x18000f21e  jz      short loc_18000F248
0x18000f220  jmp     short loc_18000F23C
0x18000f222  mov     rcx, [rbx+8]; RegistrationHandle
0x18000f226  test    rcx, rcx
0x18000f229  jz      short loc_18000F239
0x18000f22b  call    cs:__imp_UnregisterTraceGuids
0x18000f231  mov     qword ptr [rbx+8], 0
0x18000f239  mov     rbx, [rbx]
0x18000f23c  test    rbx, rbx
0x18000f23f  jnz     short loc_18000F222
0x18000f241  mov     cs:WPP_GLOBAL_Control, rdi
0x18000f248  lea     rcx, Microsoft_Windows_MF_Context
0x18000f24f  call    McGenEventUnregister_EventUnregister
0x18000f254  mov     rbx, [rsp+28h+arg_0]
0x18000f259  mov     eax, 1
0x18000f25e  add     rsp, 20h
0x18000f262  pop     rdi
0x18000f263  retn
```
