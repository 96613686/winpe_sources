# DllMain

- ea: `0x18000e7e4`
- end: `0x18000e97c`
- name: `DllMain`
- size: `408`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x180001504`

## callees

- `0x18000e7e4`
- `0x1800165d0`
- `0x1800168c8`
- `0x180016a08`
- `0x1800177c8`

## import_xrefs

- `KERNEL32!HeapDestroy` at `0x18000e8f8`
- `KERNEL32!HeapDestroy` at `0x18000e8f8`
- `KERNEL32!GetProcessHeap` at `0x18000e8e6`
- `KERNEL32!GetProcessHeap` at `0x18000e8e6`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18000e803`
- `KERNEL32!DisableThreadLibraryCalls` at `0x18000e803`
- `KERNEL32!CloseHandle` at `0x18000e95a`
- `KERNEL32!CloseHandle` at `0x18000e95a`
- `ADVAPI32!RegisterTraceGuidsW` at `0x18000e88c`
- `ADVAPI32!RegisterTraceGuidsW` at `0x18000e88c`
- `ADVAPI32!UnregisterTraceGuids` at `0x18000e923`
- `ADVAPI32!UnregisterTraceGuids` at `0x18000e923`

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
    qword_180070D30 = 0;
    v3 = (ULONG64 *)&WPP_MAIN_CB;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_CtlGuid;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    v4 = (const GUID **)&WPP_REGISTRATION_GUIDS;
    WPP_MAIN_CB = 0;
    qword_180070D38 = 1;
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
    dword_180070958 = 0;
    InitializeEventLog(&lpMem);
    if ( lpMem )
      FreeFaxRegistry(lpMem);
  }
  else if ( !fdwReason )
  {
    FXSEVENTFree(hinstDLL, fdwReason, lpvReserved);
    if ( hHeap )
    {
      if ( hHeap != GetProcessHeap() )
        HeapDestroy(hHeap);
      hHeap = 0;
    }
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
0x18000e7e4  mov     [rsp+arg_0], rbx
0x18000e7e9  mov     [rsp+arg_10], rsi
0x18000e7ee  push    rdi
0x18000e7ef  sub     rsp, 50h
0x18000e7f3  xor     ebx, ebx
0x18000e7f5  cmp     edx, 1
0x18000e7f8  jnz     loc_18000E8D0
0x18000e7fe  mov     [rsp+58h+lpMem], rbx
0x18000e803  call    cs:__imp_DisableThreadLibraryCalls
0x18000e809  call    debugOpenLogFile
0x18000e80e  lea     rax, WPP_ThisDir_CTLGUID_CtlGuid
0x18000e815  mov     cs:qword_180070D30, rbx
0x18000e81c  lea     rdi, WPP_MAIN_CB
0x18000e823  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000e82a  mov     cs:WPP_GLOBAL_Control, rdi
0x18000e831  lea     rsi, WPP_REGISTRATION_GUIDS
0x18000e838  mov     cs:WPP_MAIN_CB, rbx
0x18000e83f  mov     cs:qword_180070D38, 1
0x18000e84a  mov     r8, [rsi]; ControlGuid
0x18000e84d  lea     rax, [rdi+8]
0x18000e851  mov     [rsp+58h+RegistrationHandle], rax; RegistrationHandle
0x18000e856  lea     rcx, WppControlCallback; RequestAddress
0x18000e85d  mov     [rsp+58h+MofResourceName], rbx; MofResourceName
0x18000e862  lea     rax, [rsp+58h+var_18]
0x18000e867  mov     [rsp+58h+var_18.Guid], r8
0x18000e86c  lea     rsi, [rsi+8]
0x18000e870  mov     [rsp+58h+var_18.RegHandle], rbx
0x18000e875  mov     r9d, 1; GuidCount
0x18000e87b  mov     [rsp+58h+MofImagePath], rbx; MofImagePath
0x18000e880  mov     rdx, rdi; RequestContext
0x18000e883  mov     [rsp+58h+TraceGuidReg], rax; TraceGuidReg
0x18000e888  mov     [rdi+20h], r8
0x18000e88c  call    cs:__imp_RegisterTraceGuidsW
0x18000e892  mov     rdi, [rdi]
0x18000e895  test    rdi, rdi
0x18000e898  jnz     short loc_18000E84A
0x18000e89a  lea     rcx, [rsp+58h+lpMem]
0x18000e89f  mov     cs:hEventLog, rbx
0x18000e8a6  mov     cs:?gs_pFaxCategory@@3PEAU_FAX_LOG_CATEGORYW@@EA, rbx; _FAX_LOG_CATEGORYW * gs_pFaxCategory
0x18000e8ad  mov     cs:dword_180070958, ebx
0x18000e8b3  call    InitializeEventLog
0x18000e8b8  mov     rcx, [rsp+58h+lpMem]; lpMem
0x18000e8bd  test    rcx, rcx
0x18000e8c0  jz      loc_18000E967
0x18000e8c6  call    FreeFaxRegistry
0x18000e8cb  jmp     loc_18000E967
0x18000e8d0  test    edx, edx
0x18000e8d2  jnz     loc_18000E967
0x18000e8d8  call    FXSEVENTFree
0x18000e8dd  cmp     cs:hHeap, rbx
0x18000e8e4  jz      short loc_18000E905
0x18000e8e6  call    cs:__imp_GetProcessHeap
0x18000e8ec  mov     rcx, cs:hHeap; hHeap
0x18000e8f3  cmp     rcx, rax
0x18000e8f6  jz      short loc_18000E8FE
0x18000e8f8  call    cs:__imp_HeapDestroy
0x18000e8fe  mov     cs:hHeap, rbx
0x18000e905  mov     rdi, cs:WPP_GLOBAL_Control
0x18000e90c  lea     rsi, WPP_GLOBAL_Control
0x18000e913  cmp     rdi, rsi
0x18000e916  jz      short loc_18000E93C
0x18000e918  jmp     short loc_18000E930
0x18000e91a  mov     rcx, [rdi+8]; RegistrationHandle
0x18000e91e  test    rcx, rcx
0x18000e921  jz      short loc_18000E92D
0x18000e923  call    cs:__imp_UnregisterTraceGuids
0x18000e929  mov     [rdi+8], rbx
0x18000e92d  mov     rdi, [rdi]
0x18000e930  test    rdi, rdi
0x18000e933  jnz     short loc_18000E91A
0x18000e935  mov     cs:WPP_GLOBAL_Control, rsi
0x18000e93c  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000e940  mov     ecx, ebx
0x18000e942  lock xadd cs:?g_iLogFileRefCount@@3JA, ecx; long g_iLogFileRefCount
0x18000e94a  add     ecx, ebx
0x18000e94c  jnz     short loc_18000E967
0x18000e94e  mov     rcx, cs:?g_hLogFile@@3PEAXEA; hObject
0x18000e955  cmp     rcx, rbx
0x18000e958  jz      short loc_18000E967
0x18000e95a  call    cs:__imp_CloseHandle
0x18000e960  mov     cs:?g_hLogFile@@3PEAXEA, rbx; void * g_hLogFile
0x18000e967  mov     rbx, [rsp+58h+arg_0]
0x18000e96c  mov     eax, 1
0x18000e971  mov     rsi, [rsp+58h+arg_10]
0x18000e976  add     rsp, 50h
0x18000e97a  pop     rdi
0x18000e97b  retn
```
