# WppEnable(void)

- ea: `0x180005f28`
- end: `0x180005ff1`
- name: `?WppEnable@@YAXXZ`
- size: `201`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180005958`
- `0x180006040`

## callees

- `0x180005f28`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180005fd1`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x180005fd1`

## pseudocode

```c
void WppEnable(void)
{
  ULONG64 *v0; // rbx
  const GUID **v1; // rdi
  const GUID *v2; // r8
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-18h] BYREF

  if ( !g_bWppEnabled )
  {
    qword_18000E470 = 0;
    v0 = (ULONG64 *)&WPP_MAIN_CB;
    WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_ApxGuid;
    WPP_GLOBAL_Control = &WPP_MAIN_CB;
    v1 = (const GUID **)&WPP_REGISTRATION_GUIDS;
    WPP_MAIN_CB = 0;
    qword_18000E478 = 1;
    do
    {
      v2 = *v1;
      TraceGuidReg.Guid = v2;
      ++v1;
      TraceGuidReg.RegHandle = 0;
      v0[4] = (ULONG64)v2;
      RegisterTraceGuidsW(WppControlCallback, v0, v2, 1u, &TraceGuidReg, 0, 0, v0 + 1);
      v0 = (ULONG64 *)*v0;
    }
    while ( v0 );
    g_bWppEnabled = 1;
  }
}

```

## disassembly

```asm
0x180005f28  mov     [rsp+arg_0], rbx
0x180005f2d  push    rdi
0x180005f2e  sub     rsp, 50h
0x180005f32  cmp     cs:?g_bWppEnabled@@3_NA, 0; bool g_bWppEnabled
0x180005f39  jnz     loc_180005FE6
0x180005f3f  lea     rax, WPP_ThisDir_CTLGUID_ApxGuid
0x180005f46  mov     cs:qword_18000E470, 0
0x180005f51  lea     rbx, WPP_MAIN_CB
0x180005f58  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x180005f5f  mov     cs:WPP_GLOBAL_Control, rbx
0x180005f66  lea     rdi, WPP_REGISTRATION_GUIDS
0x180005f6d  mov     cs:WPP_MAIN_CB, 0
0x180005f78  mov     cs:qword_18000E478, 1
0x180005f83  mov     r8, [rdi]; ControlGuid
0x180005f86  lea     rax, [rbx+8]
0x180005f8a  mov     [rsp+58h+RegistrationHandle], rax; RegistrationHandle
0x180005f8f  lea     rcx, WppControlCallback; RequestAddress
0x180005f96  mov     [rsp+58h+MofResourceName], 0; MofResourceName
0x180005f9f  lea     rax, [rsp+58h+var_18]
0x180005fa4  mov     [rsp+58h+var_18.Guid], r8
0x180005fa9  lea     rdi, [rdi+8]
0x180005fad  mov     [rsp+58h+var_18.RegHandle], 0
0x180005fb6  mov     r9d, 1; GuidCount
0x180005fbc  mov     [rsp+58h+MofImagePath], 0; MofImagePath
0x180005fc5  mov     rdx, rbx; RequestContext
0x180005fc8  mov     [rsp+58h+TraceGuidReg], rax; TraceGuidReg
0x180005fcd  mov     [rbx+20h], r8
0x180005fd1  call    cs:__imp_RegisterTraceGuidsW
0x180005fd7  mov     rbx, [rbx]
0x180005fda  test    rbx, rbx
0x180005fdd  jnz     short loc_180005F83
0x180005fdf  mov     cs:?g_bWppEnabled@@3_NA, 1; bool g_bWppEnabled
0x180005fe6  mov     rbx, [rsp+58h+arg_0]
0x180005feb  add     rsp, 50h
0x180005fef  pop     rdi
0x180005ff0  retn
```
