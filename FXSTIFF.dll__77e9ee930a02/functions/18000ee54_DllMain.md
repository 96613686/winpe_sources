# DllMain

- ea: `0x18000ee54`
- end: `0x18000efdb`
- name: `DllMain`
- size: `391`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001504`

## callees

- `0x18000ee54`
- `0x18000f08c`
- `0x1800172f4`
- `0x180017618`
- `0x180017744`
- `0x180018580`

## import_xrefs

- `KERNEL32!DisableThreadLibraryCalls` at `0x18000ee73`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18000ee73`
- `KERNEL32!CloseHandle` at `0x18000efb2`
- `KERNEL32!CloseHandle` at `0x18000efb2`
- `ADVAPI32!RegisterTraceGuidsW` at `0x18000ef02`
- `ADVAPI32!RegisterTraceGuidsW` at `0x18000ef02`
- `ADVAPI32!UnregisterTraceGuids` at `0x18000ef75`
- `ADVAPI32!UnregisterTraceGuids` at `0x18000ef75`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  ULONG64 *v3; // rdi
  const GUID **v4; // rsi
  const GUID *v5; // r8
  _QWORD *v6; // rdi
  TRACEHANDLE v7; // rcx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-18h] BYREF
  LPVOID lpMem; // [rsp+78h] [rbp+20h] BYREF

  if ( fdwReason == 1 )
  {
    lpMem = 0;
    DisableThreadLibraryCalls(hinstDLL);
    debugOpenLogFile();
    qword_180071D50 = 0;
    v3 = (ULONG64 *)&WPP_MAIN_CB;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    v4 = (const GUID **)&WPP_REGISTRATION_GUIDS;
    WPP_MAIN_CB = 0;
    qword_180071D58 = 1;
    do
    {
      v5 = *v4;
      TraceGuidReg.Guid = v5;
      ++v4;
      TraceGuidReg.RegHandle = 0;
      v3[4] = (ULONG64)v5;
      RegisterTraceGuidsW(WppControlCallback, v3, v5, 1u, &TraceGuidReg, 0, 0, v3 + 1);
      v3 = (ULONG64 *)*v3;
    }
    while ( v3 );
    hEventLog = 0;
    gs_pFaxCategory = 0;
    dword_180071960 = 0;
    InitializeEventLog(&lpMem);
    if ( lpMem )
      FreeFaxRegistry(lpMem);
  }
  else if ( !fdwReason )
  {
    FXSEVENTFree(hinstDLL, fdwReason, lpvReserved);
    HeapCleanup();
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      while ( v6 )
      {
        v7 = v6[1];
        if ( v7 )
        {
          UnregisterTraceGuids(v7);
          v6[1] = 0;
        }
        v6 = (_QWORD *)*v6;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
    if ( _InterlockedExchangeAdd(&g_iLogFileRefCount, 0xFFFFFFFF) == 1 && g_hLogFile != (HANDLE)-1LL )
    {
      CloseHandle(g_hLogFile);
      g_hLogFile = (HANDLE)-1LL;
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000ee54  mov     [rsp+arg_0], rbx
0x18000ee59  mov     [rsp+arg_10], rsi
0x18000ee5e  push    rdi
0x18000ee5f  sub     rsp, 50h
0x18000ee63  xor     ebx, ebx
0x18000ee65  cmp     edx, 1
0x18000ee68  jnz     loc_18000EF49
0x18000ee6e  mov     [rsp+58h+lpMem], rbx
0x18000ee73  call    cs:__imp_DisableThreadLibraryCalls
0x18000ee7a  nop     dword ptr [rax+rax+00h]
0x18000ee7f  call    debugOpenLogFile
0x18000ee84  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x18000ee8b  mov     cs:qword_180071D50, rbx
0x18000ee92  lea     rdi, WPP_MAIN_CB
0x18000ee99  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000eea0  mov     cs:WPP_GLOBAL_Control, rdi
0x18000eea7  lea     rsi, WPP_REGISTRATION_GUIDS
0x18000eeae  mov     cs:WPP_MAIN_CB, rbx
0x18000eeb5  mov     cs:qword_180071D58, 1
0x18000eec0  mov     r8, [rsi]; ControlGuid
0x18000eec3  lea     rax, [rdi+8]
0x18000eec7  mov     [rsp+58h+RegistrationHandle], rax; RegistrationHandle
0x18000eecc  lea     rcx, WppControlCallback; RequestAddress
0x18000eed3  mov     [rsp+58h+MofResourceName], rbx; MofResourceName
0x18000eed8  lea     rax, [rsp+58h+var_18]
0x18000eedd  mov     [rsp+58h+var_18.Guid], r8
0x18000eee2  lea     rsi, [rsi+8]
0x18000eee6  mov     [rsp+58h+var_18.RegHandle], rbx
0x18000eeeb  mov     r9d, 1; GuidCount
0x18000eef1  mov     [rsp+58h+MofImagePath], rbx; MofImagePath
0x18000eef6  mov     rdx, rdi; RequestContext
0x18000eef9  mov     [rsp+58h+TraceGuidReg], rax; TraceGuidReg
0x18000eefe  mov     [rdi+20h], r8
0x18000ef02  call    cs:__imp_RegisterTraceGuidsW
0x18000ef09  nop     dword ptr [rax+rax+00h]
0x18000ef0e  mov     rdi, [rdi]
0x18000ef11  test    rdi, rdi
0x18000ef14  jnz     short loc_18000EEC0
0x18000ef16  lea     rcx, [rsp+58h+lpMem]
0x18000ef1b  mov     cs:hEventLog, rbx
0x18000ef22  mov     cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA, rbx; _FAX_LOG_CATEGORYW * gs_pFaxCategory
0x18000ef29  mov     cs:dword_180071960, ebx
0x18000ef2f  call    InitializeEventLog
0x18000ef34  mov     rcx, [rsp+58h+lpMem]; lpMem
0x18000ef39  test    rcx, rcx
0x18000ef3c  jz      loc_18000EFC5
0x18000ef42  call    FreeFaxRegistry
0x18000ef47  jmp     short loc_18000EFC5
0x18000ef49  test    edx, edx
0x18000ef4b  jnz     short loc_18000EFC5
0x18000ef4d  call    FXSEVENTFree
0x18000ef52  call    HeapCleanup
0x18000ef57  mov     rdi, cs:WPP_GLOBAL_Control
0x18000ef5e  lea     rsi, WPP_GLOBAL_Control
0x18000ef65  cmp     rdi, rsi
0x18000ef68  jz      short loc_18000EF94
0x18000ef6a  jmp     short loc_18000EF88
0x18000ef6c  mov     rcx, [rdi+8]; RegistrationHandle
0x18000ef70  test    rcx, rcx
0x18000ef73  jz      short loc_18000EF85
0x18000ef75  call    cs:__imp_UnregisterTraceGuids
0x18000ef7c  nop     dword ptr [rax+rax+00h]
0x18000ef81  mov     [rdi+8], rbx
0x18000ef85  mov     rdi, [rdi]
0x18000ef88  test    rdi, rdi
0x18000ef8b  jnz     short loc_18000EF6C
0x18000ef8d  mov     cs:WPP_GLOBAL_Control, rsi
0x18000ef94  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000ef98  mov     ecx, ebx
0x18000ef9a  lock xadd cs:?g_iLogFileRefCount@@3JA, ecx; long g_iLogFileRefCount
0x18000efa2  add     ecx, ebx
0x18000efa4  jnz     short loc_18000EFC5
0x18000efa6  mov     rcx, cs:?g_hLogFile@@3PEAXEA; hObject
0x18000efad  cmp     rcx, rbx
0x18000efb0  jz      short loc_18000EFC5
0x18000efb2  call    cs:__imp_CloseHandle
0x18000efb9  nop     dword ptr [rax+rax+00h]
0x18000efbe  mov     cs:?g_hLogFile@@3PEAXEA, rbx; void * g_hLogFile
0x18000efc5  mov     rbx, [rsp+58h+arg_0]
0x18000efca  mov     eax, 1
0x18000efcf  mov     rsi, [rsp+58h+arg_10]
0x18000efd4  add     rsp, 50h
0x18000efd8  pop     rdi
0x18000efd9  retn
```
