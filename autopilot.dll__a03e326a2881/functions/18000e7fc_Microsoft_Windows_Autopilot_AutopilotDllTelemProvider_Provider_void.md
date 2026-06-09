# Microsoft::Windows::Autopilot::AutopilotDllTelemProvider::Provider(void)

- ea: `0x18000e7fc`
- end: `0x18000e8b5`
- name: `?Provider@AutopilotDllTelemProvider@Autopilot@Windows@Microsoft@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ca98`
- `0x18000dd5c`

## callees

- `0x1800049c8`
- `0x18000e7fc`
- `0x18000fca8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e824`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000e824`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e8a0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000e8a0`

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
    qword_180043C18 = 0;
    v3 = &qword_180043C10;
    qword_180043C10 = &AutoPilotTelemProvider::`vftable';
    byte_180043C20 = 0;
    dword_180043C24 = 0;
    qword_180043C28 = (struct _tlgProvider_t *)&`Microsoft::Windows::Autopilot::AutopilotDllTelemProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8b82a2507aa0fd11996f21ede248e4b0_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180043C10, qword_180043C28, v0);
    InitOnceComplete(
      &`Microsoft::Windows::Autopilot::AutopilotDllTelemProvider::Instance'::`2'::wrapper,
      0,
      &qword_180043C10);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x18000e7fc  mov     rax, rsp
0x18000e7ff  push    rbx
0x18000e800  sub     rsp, 20h
0x18000e804  lea     r9, [rax+10h]; lpContext
0x18000e808  mov     qword ptr [rax+10h], 0
0x18000e810  lea     r8, [rax+8]; fPending
0x18000e814  mov     dword ptr [rax+8], 0
0x18000e81b  xor     edx, edx; dwFlags
0x18000e81d  lea     rcx, ?wrapper@?1??Instance@AutopilotDllTelemProvider@Autopilot@Windows@Microsoft@@KAPEAV2345@XZ@4V?$static_lazy@VAutopilotDllTelemProvider@Autopilot@Windows@Microsoft@@@details@wil@@A; lpInitOnce
0x18000e824  call    cs:__imp___std_init_once_begin_initialize
0x18000e82a  test    eax, eax
0x18000e82c  jz      short loc_18000E8A6
0x18000e82e  cmp     [rsp+28h+arg_0], 0
0x18000e833  jz      short loc_18000E8A6
0x18000e835  lea     rbx, qword_180043C10
0x18000e83c  mov     cs:qword_180043C18, 0
0x18000e847  lea     rax, ??_7AutoPilotTelemProvider@@6B@; const AutoPilotTelemProvider::`vftable'
0x18000e84e  mov     [rsp+28h+arg_8], rbx
0x18000e853  mov     cs:qword_180043C10, rax
0x18000e85a  mov     cs:byte_180043C20, 0
0x18000e861  mov     cs:dword_180043C24, 0
0x18000e86b  lea     rax, ?__hInner@?1???0StaticHandle@AutopilotDllTelemProvider@Autopilot@Windows@Microsoft@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `Microsoft::Windows::Autopilot::AutopilotDllTelemProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000e872  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8b82a2507aa0fd11996f21ede248e4b0_@@CA@XZ; void (__cdecl *)()
0x18000e879  mov     cs:qword_180043C28, rax
0x18000e880  call    atexit
0x18000e885  mov     rdx, cs:qword_180043C28; struct _tlgProvider_t *
0x18000e88c  mov     rcx, rbx; this
0x18000e88f  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18000e894  mov     r8, rbx; lpContext
0x18000e897  lea     rcx, ?wrapper@?1??Instance@AutopilotDllTelemProvider@Autopilot@Windows@Microsoft@@KAPEAV2345@XZ@4V?$static_lazy@VAutopilotDllTelemProvider@Autopilot@Windows@Microsoft@@@details@wil@@A; lpInitOnce
0x18000e89e  xor     edx, edx; dwFlags
0x18000e8a0  call    cs:__imp_InitOnceComplete
0x18000e8a6  mov     rax, [rsp+28h+arg_8]
0x18000e8ab  mov     rax, [rax+8]
0x18000e8af  add     rsp, 20h
0x18000e8b3  pop     rbx
0x18000e8b4  retn
```
