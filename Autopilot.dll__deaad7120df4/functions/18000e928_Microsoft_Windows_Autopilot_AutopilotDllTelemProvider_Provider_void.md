# Microsoft::Windows::Autopilot::AutopilotDllTelemProvider::Provider(void)

- ea: `0x18000e928`
- end: `0x18000e9ee`
- name: `?Provider@AutopilotDllTelemProvider@Autopilot@Windows@Microsoft@@SAPEBU_tlgProvider_t@@XZ`
- size: `198`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cb38`
- `0x18000ddcc`

## callees

- `0x1800049e8`
- `0x18000e928`
- `0x18000fd60`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e950`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e950`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e9d2`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e9d2`

## pseudocode

```c
const struct _tlgProvider_t *Microsoft::Windows::Autopilot::AutopilotDllTelemProvider::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( __std_init_once_begin_initialize(
         &`Microsoft::Windows::Autopilot::AutopilotDllTelemProvider::Instance'::`2'::wrapper,
         0,
         &v2,
         (LPVOID *)&v3)
    && v2 )
  {
    qword_180044C18 = 0;
    v3 = &qword_180044C10;
    qword_180044C10 = &AutoPilotTelemProvider::`vftable';
    byte_180044C20 = 0;
    dword_180044C24 = 0;
    qword_180044C28 = (struct _tlgProvider_t *)&`Microsoft::Windows::Autopilot::AutopilotDllTelemProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8b82a2507aa0fd11996f21ede248e4b0_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180044C10, qword_180044C28, v0);
    InitOnceComplete(
      &`Microsoft::Windows::Autopilot::AutopilotDllTelemProvider::Instance'::`2'::wrapper,
      0,
      &qword_180044C10);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x18000e928  mov     rax, rsp
0x18000e92b  push    rbx
0x18000e92c  sub     rsp, 20h
0x18000e930  lea     r9, [rax+10h]; lpContext
0x18000e934  mov     qword ptr [rax+10h], 0
0x18000e93c  lea     r8, [rax+8]; fPending
0x18000e940  mov     dword ptr [rax+8], 0
0x18000e947  xor     edx, edx; dwFlags
0x18000e949  lea     rcx, ?wrapper@?1??Instance@AutopilotDllTelemProvider@Autopilot@Windows@Microsoft@@KAPEAV2345@XZ@4V?$static_lazy@VAutopilotDllTelemProvider@Autopilot@Windows@Microsoft@@@details@wil@@A; lpInitOnce
0x18000e950  call    cs:__imp___std_init_once_begin_initialize
0x18000e957  nop     dword ptr [rax+rax+00h]
0x18000e95c  test    eax, eax
0x18000e95e  jz      short loc_18000E9DE
0x18000e960  cmp     [rsp+28h+arg_0], 0
0x18000e965  jz      short loc_18000E9DE
0x18000e967  lea     rbx, qword_180044C10
0x18000e96e  mov     cs:qword_180044C18, 0
0x18000e979  lea     rax, ??_7AutoPilotTelemProvider@@6B@; const AutoPilotTelemProvider::`vftable'
0x18000e980  mov     [rsp+28h+arg_8], rbx
0x18000e985  mov     cs:qword_180044C10, rax
0x18000e98c  mov     cs:byte_180044C20, 0
0x18000e993  mov     cs:dword_180044C24, 0
0x18000e99d  lea     rax, ?__hInner@?1???0StaticHandle@AutopilotDllTelemProvider@Autopilot@Windows@Microsoft@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `Microsoft::Windows::Autopilot::AutopilotDllTelemProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000e9a4  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8b82a2507aa0fd11996f21ede248e4b0_@@CA@XZ; void (__cdecl *)()
0x18000e9ab  mov     cs:qword_180044C28, rax
0x18000e9b2  call    atexit
0x18000e9b7  mov     rdx, cs:qword_180044C28; struct _tlgProvider_t *
0x18000e9be  mov     rcx, rbx; this
0x18000e9c1  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000e9c6  mov     r8, rbx; lpContext
0x18000e9c9  lea     rcx, ?wrapper@?1??Instance@AutopilotDllTelemProvider@Autopilot@Windows@Microsoft@@KAPEAV2345@XZ@4V?$static_lazy@VAutopilotDllTelemProvider@Autopilot@Windows@Microsoft@@@details@wil@@A; lpInitOnce
0x18000e9d0  xor     edx, edx; dwFlags
0x18000e9d2  call    cs:__imp_InitOnceComplete
0x18000e9d9  nop     dword ptr [rax+rax+00h]
0x18000e9de  mov     rax, [rsp+28h+arg_8]
0x18000e9e3  mov     rax, [rax+8]
0x18000e9e7  add     rsp, 20h
0x18000e9eb  pop     rbx
0x18000e9ec  retn
```
