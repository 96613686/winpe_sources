# DllMain

- ea: `0x180012e4c`
- end: `0x18001300b`
- name: `DllMain`
- size: `447`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180001824`

## callees

- `0x180012e4c`
- `0x180013128`
- `0x18001314c`

## import_xrefs

- `KERNEL32!SetLastError` at `0x180012f7c`
- `KERNEL32!SetLastError` at `0x180012f7c`
- `KERNEL32!DeleteCriticalSection` at `0x180012f96`
- `KERNEL32!DeleteCriticalSection` at `0x180012f96`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180012e87`
- `KERNEL32!InitializeCriticalSectionAndSpinCount` at `0x180012e87`
- `ADVAPI32!RegisterTraceGuidsW` at `0x180012f5a`
- `ADVAPI32!RegisterTraceGuidsW` at `0x180012f5a`
- `ADVAPI32!UnregisterTraceGuids` at `0x180012fdc`
- `ADVAPI32!UnregisterTraceGuids` at `0x180012fdc`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v3; // edi
  __int64 v4; // rdx
  __int64 v5; // rdx
  ULONG64 *v6; // rbx
  const GUID **v7; // rsi
  const GUID *v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  _QWORD *v11; // rbx
  TRACEHANDLE v12; // rcx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-18h] BYREF

  v3 = 1;
  if ( fdwReason )
  {
    if ( fdwReason == 1 )
    {
      if ( !InitializeCriticalSectionAndSpinCount(&g_Crit, 0xFA0u) )
      {
        SetLastError(0x45Au);
        return 0;
      }
      g_HaveCrit = 1;
      McGenEventRegister_EventRegister(&userpnp, v4, &userpnp_Context, &userpnp_Context);
      McGenEventRegister_EventRegister(
        &MICROSOFT_WINDOWS_DEVICESETUPMANAGER,
        v5,
        &MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context,
        &MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context);
      qword_18001EAF8 = 0;
      v6 = (ULONG64 *)&WPP_MAIN_CB;
      WPP_REGISTRATION_GUIDS = (__int64)&WPP_ThisDir_CTLGUID_Dmrc;
      WPP_GLOBAL_Control = &WPP_MAIN_CB;
      v7 = (const GUID **)&WPP_REGISTRATION_GUIDS;
      WPP_MAIN_CB = 0;
      qword_18001EB00 = 1;
      do
      {
        v8 = *v7;
        TraceGuidReg.Guid = v8;
        ++v7;
        TraceGuidReg.RegHandle = 0;
        v6[4] = (ULONG64)v8;
        RegisterTraceGuidsW(WppControlCallback, v6, v8, 1u, &TraceGuidReg, 0, 0, v6 + 1);
        v6 = (ULONG64 *)*v6;
      }
      while ( v6 );
      if ( ATL::CAtlBaseModule::m_bInitFailed )
        return 0;
    }
  }
  else
  {
    if ( g_HaveCrit )
    {
      DeleteCriticalSection(&g_Crit);
      g_HaveCrit = 0;
    }
    McGenEventUnregister_EventUnregister(&userpnp_Context, *(_QWORD *)&fdwReason, lpvReserved);
    McGenEventUnregister_EventUnregister(&MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context, v9, v10);
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      while ( v11 )
      {
        v12 = v11[1];
        if ( v12 )
        {
          UnregisterTraceGuids(v12);
          v11[1] = 0;
        }
        v11 = (_QWORD *)*v11;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180012e4c  mov     [rsp+arg_0], rbx
0x180012e51  mov     [rsp+arg_8], rsi
0x180012e56  push    rdi
0x180012e57  sub     rsp, 50h
0x180012e5b  mov     eax, edx
0x180012e5d  mov     edi, 1
0x180012e62  test    edx, edx
0x180012e64  jz      loc_180012F86
0x180012e6a  cmp     eax, edi
0x180012e6c  jz      short loc_180012E7B
0x180012e6e  cmp     edx, edi
0x180012e70  jnz     loc_180012FF9
0x180012e76  jmp     loc_180012F68
0x180012e7b  mov     edx, 0FA0h; dwSpinCount
0x180012e80  lea     rcx, ?g_Crit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180012e87  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180012e8d  test    eax, eax
0x180012e8f  jz      loc_180012F77
0x180012e95  lea     r9, userpnp_Context
0x180012e9c  mov     cs:?g_HaveCrit@@3HA, edi; int g_HaveCrit
0x180012ea2  lea     r8, userpnp_Context
0x180012ea9  lea     rcx, userpnp
0x180012eb0  call    McGenEventRegister_EventRegister
0x180012eb5  lea     r9, MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context
0x180012ebc  lea     r8, MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context
0x180012ec3  lea     rcx, MICROSOFT_WINDOWS_DEVICESETUPMANAGER
0x180012eca  call    McGenEventRegister_EventRegister
0x180012ecf  lea     rax, WPP_ThisDir_CTLGUID_Dmrc
0x180012ed6  mov     cs:qword_18001EAF8, 0
0x180012ee1  lea     rbx, WPP_MAIN_CB
0x180012ee8  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180012eef  mov     cs:WPP_GLOBAL_Control, rbx
0x180012ef6  lea     rsi, WPP_REGISTRATION_GUIDS
0x180012efd  mov     cs:WPP_MAIN_CB, 0
0x180012f08  mov     cs:qword_18001EB00, rdi
0x180012f0f  mov     r8, [rsi]; ControlGuid
0x180012f12  lea     rax, [rbx+8]
0x180012f16  mov     [rsp+58h+RegistrationHandle], rax; RegistrationHandle
0x180012f1b  lea     rcx, WppControlCallback; RequestAddress
0x180012f22  mov     [rsp+58h+MofResourceName], 0; MofResourceName
0x180012f2b  lea     rax, [rsp+58h+var_18]
0x180012f30  mov     [rsp+58h+var_18.Guid], r8
0x180012f35  lea     rsi, [rsi+8]
0x180012f39  mov     [rsp+58h+var_18.RegHandle], 0
0x180012f42  mov     r9d, edi; GuidCount
0x180012f45  mov     [rsp+58h+MofImagePath], 0; MofImagePath
0x180012f4e  mov     rdx, rbx; RequestContext
0x180012f51  mov     [rsp+58h+TraceGuidReg], rax; TraceGuidReg
0x180012f56  mov     [rbx+20h], r8
0x180012f5a  call    cs:__imp_RegisterTraceGuidsW
0x180012f60  mov     rbx, [rbx]
0x180012f63  test    rbx, rbx
0x180012f66  jnz     short loc_180012F0F
0x180012f68  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, 0; bool ATL::CAtlBaseModule::m_bInitFailed
0x180012f6f  jz      loc_180012FF9
0x180012f75  jmp     short loc_180012F82
0x180012f77  mov     ecx, 45Ah; dwErrCode
0x180012f7c  call    cs:__imp_SetLastError
0x180012f82  xor     edi, edi
0x180012f84  jmp     short loc_180012FF9
0x180012f86  cmp     cs:?g_HaveCrit@@3HA, 0; int g_HaveCrit
0x180012f8d  jz      short loc_180012FA6
0x180012f8f  lea     rcx, ?g_Crit@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180012f96  call    cs:__imp_DeleteCriticalSection
0x180012f9c  mov     cs:?g_HaveCrit@@3HA, 0; int g_HaveCrit
0x180012fa6  lea     rcx, userpnp_Context
0x180012fad  call    McGenEventUnregister_EventUnregister
0x180012fb2  lea     rcx, MICROSOFT_WINDOWS_DEVICESETUPMANAGER_Context
0x180012fb9  call    McGenEventUnregister_EventUnregister
0x180012fbe  mov     rbx, cs:WPP_GLOBAL_Control
0x180012fc5  lea     rsi, WPP_GLOBAL_Control
0x180012fcc  cmp     rbx, rsi
0x180012fcf  jz      short loc_180012FF9
0x180012fd1  jmp     short loc_180012FED
0x180012fd3  mov     rcx, [rbx+8]; RegistrationHandle
0x180012fd7  test    rcx, rcx
0x180012fda  jz      short loc_180012FEA
0x180012fdc  call    cs:__imp_UnregisterTraceGuids
0x180012fe2  mov     qword ptr [rbx+8], 0
0x180012fea  mov     rbx, [rbx]
0x180012fed  test    rbx, rbx
0x180012ff0  jnz     short loc_180012FD3
0x180012ff2  mov     cs:WPP_GLOBAL_Control, rsi
0x180012ff9  mov     rbx, [rsp+58h+arg_0]
0x180012ffe  mov     eax, edi
0x180013000  mov     rsi, [rsp+58h+arg_8]
0x180013005  add     rsp, 50h
0x180013009  pop     rdi
0x18001300a  retn
```
