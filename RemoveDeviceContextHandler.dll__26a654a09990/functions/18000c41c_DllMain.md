# DllMain

- ea: `0x18000c41c`
- end: `0x18000c58b`
- name: `DllMain`
- size: `367`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001f04`

## callees

- `0x18000c41c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c51f`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c51f`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18000c55a`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x18000c55a`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18000c50e`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x18000c50e`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  BOOL v4; // ebx
  ULONG64 *v5; // rdi
  const GUID **v6; // r14
  const GUID *v7; // r8
  _QWORD *v8; // rdi
  TRACEHANDLE v9; // rcx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-38h] BYREF

  if ( fdwReason != 1 )
  {
    if ( !fdwReason )
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
      {
        while ( v8 )
        {
          v9 = v8[1];
          if ( v9 )
          {
            UnregisterTraceGuids(v9);
            v8[1] = 0;
          }
          v8 = (_QWORD *)*v8;
        }
        WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
      }
    }
    g_hinst = hinstDLL;
    return 1;
  }
  v4 = 0;
  qword_180014A68 = 1;
  qword_180014A60 = 0;
  WPP_MAIN_CB = (__int64)&qword_180014A78;
  v5 = (ULONG64 *)&WPP_MAIN_CB;
  qword_180014A88 = 0;
  qword_180014A78 = (__int64)&qword_180014AA0;
  v6 = (const GUID **)&WPP_REGISTRATION_GUIDS;
  qword_180014A90 = 1;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ShellTraceProvider;
  qword_180014AD8 = (__int64)WPP_ThisDir_CTLGUID_ShellPerfTraceProvider;
  qword_180014AE0 = (__int64)WPP_ThisDir_CTLGUID_ShellTraceHomeGroupProvider;
  qword_180014AB0 = 0;
  qword_180014AA0 = 0;
  qword_180014AB8 = 1;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  do
  {
    v7 = *v6;
    TraceGuidReg.Guid = v7;
    ++v6;
    TraceGuidReg.RegHandle = 0;
    v5[4] = (ULONG64)v7;
    RegisterTraceGuidsW(WppControlCallback, v5, v7, 1u, &TraceGuidReg, 0, 0, v5 + 1);
    v5 = (ULONG64 *)*v5;
  }
  while ( v5 );
  DisableThreadLibraryCalls(hinstDLL);
  g_hinst = hinstDLL;
  if ( !ATL::CAtlBaseModule::m_bInitFailed )
    return 1;
  return v4;
}

```

## disassembly

```asm
0x18000c41c  push    rbx
0x18000c41e  push    rsi
0x18000c41f  push    rdi
0x18000c420  push    r14
0x18000c422  sub     rsp, 58h
0x18000c426  mov     rsi, rcx
0x18000c429  cmp     edx, 1
0x18000c42c  jnz     loc_18000C536
0x18000c432  xor     ebx, ebx
0x18000c434  mov     cs:qword_180014A68, 1
0x18000c43f  lea     rax, qword_180014A78
0x18000c446  mov     cs:qword_180014A60, rbx
0x18000c44d  mov     cs:WPP_MAIN_CB, rax
0x18000c454  lea     rdi, WPP_MAIN_CB
0x18000c45b  lea     rax, qword_180014AA0
0x18000c462  mov     cs:qword_180014A88, rbx
0x18000c469  mov     cs:qword_180014A78, rax
0x18000c470  lea     r14, WPP_REGISTRATION_GUIDS
0x18000c477  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceProvider
0x18000c47e  mov     cs:qword_180014A90, 1
0x18000c489  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000c490  lea     rax, WPP_ThisDir_CTLGUID_ShellPerfTraceProvider
0x18000c497  mov     cs:qword_180014AD8, rax
0x18000c49e  lea     rax, WPP_ThisDir_CTLGUID_ShellTraceHomeGroupProvider
0x18000c4a5  mov     cs:qword_180014AE0, rax
0x18000c4ac  mov     cs:qword_180014AB0, rbx
0x18000c4b3  mov     cs:qword_180014AA0, rbx
0x18000c4ba  mov     cs:qword_180014AB8, 1
0x18000c4c5  mov     cs:WPP_GLOBAL_Control, rdi
0x18000c4cc  mov     r8, [r14]; ControlGuid
0x18000c4cf  lea     rax, [rdi+8]
0x18000c4d3  mov     [rsp+78h+RegistrationHandle], rax; RegistrationHandle
0x18000c4d8  lea     rcx, WppControlCallback; RequestAddress
0x18000c4df  mov     [rsp+78h+MofResourceName], rbx; MofResourceName
0x18000c4e4  lea     rax, [rsp+78h+var_38]
0x18000c4e9  mov     [rsp+78h+var_38.Guid], r8
0x18000c4ee  lea     r14, [r14+8]
0x18000c4f2  mov     [rsp+78h+var_38.RegHandle], rbx
0x18000c4f7  mov     r9d, 1; GuidCount
0x18000c4fd  mov     [rsp+78h+MofImagePath], rbx; MofImagePath
0x18000c502  mov     rdx, rdi; RequestContext
0x18000c505  mov     [rsp+78h+TraceGuidReg], rax; TraceGuidReg
0x18000c50a  mov     [rdi+20h], r8
0x18000c50e  call    cs:__imp_RegisterTraceGuidsW
0x18000c514  mov     rdi, [rdi]
0x18000c517  test    rdi, rdi
0x18000c51a  jnz     short loc_18000C4CC
0x18000c51c  mov     rcx, rsi; hLibModule
0x18000c51f  call    cs:__imp_DisableThreadLibraryCalls
0x18000c525  cmp     cs:?m_bInitFailed@CAtlBaseModule@ATL@@2_NA, bl; bool ATL::CAtlBaseModule::m_bInitFailed
0x18000c52b  mov     cs:g_hinst, rsi
0x18000c532  jz      short loc_18000C57A
0x18000c534  jmp     short loc_18000C57F
0x18000c536  xor     ebx, ebx
0x18000c538  test    edx, edx
0x18000c53a  jnz     short loc_18000C573
0x18000c53c  mov     rdi, cs:WPP_GLOBAL_Control
0x18000c543  lea     r14, WPP_GLOBAL_Control
0x18000c54a  cmp     rdi, r14
0x18000c54d  jz      short loc_18000C573
0x18000c54f  jmp     short loc_18000C567
0x18000c551  mov     rcx, [rdi+8]; RegistrationHandle
0x18000c555  test    rcx, rcx
0x18000c558  jz      short loc_18000C564
0x18000c55a  call    cs:__imp_UnregisterTraceGuids
0x18000c560  mov     [rdi+8], rbx
0x18000c564  mov     rdi, [rdi]
0x18000c567  test    rdi, rdi
0x18000c56a  jnz     short loc_18000C551
0x18000c56c  mov     cs:WPP_GLOBAL_Control, r14
0x18000c573  mov     cs:g_hinst, rsi
0x18000c57a  mov     ebx, 1
0x18000c57f  mov     eax, ebx
0x18000c581  add     rsp, 58h
0x18000c585  pop     r14
0x18000c587  pop     rdi
0x18000c588  pop     rsi
0x18000c589  pop     rbx
0x18000c58a  retn
```
