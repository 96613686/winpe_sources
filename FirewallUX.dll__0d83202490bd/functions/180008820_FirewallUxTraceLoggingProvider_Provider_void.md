# FirewallUxTraceLoggingProvider::Provider(void)

- ea: `0x180008820`
- end: `0x1800088d9`
- name: `?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `36`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005764`
- `0x180006d30`
- `0x1800084b0`
- `0x18000a040`
- `0x18000fdd0`
- `0x1800123e0`
- `0x180012eb8`
- `0x180013344`
- `0x180013488`
- `0x1800135a0`
- `0x1800139a4`
- `0x180018360`
- `0x180018648`
- `0x180019ec0`
- `0x18001aaf0`
- `0x18001ab70`
- `0x18001abf0`
- `0x18001aca4`
- `0x18001ad24`
- `0x18001ada4`
- `0x18001ae24`
- `0x18001aea4`
- `0x18001af58`
- `0x18001afd8`
- `0x18001b08c`
- `0x18001b764`
- `0x18001cdc0`
- `0x18001de64`
- `0x18001f6f4`
- `0x180020088`
- `0x18002028c`
- `0x1800203d0`
- `0x180020650`
- `0x1800209d4`
- `0x1800229a0`
- `0x180028ab4`

## callees

- `0x1800025d8`
- `0x180008820`
- `0x180008bbc`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800088c4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800088c4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008848`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008848`

## pseudocode

```c
const struct _tlgProvider_t *FirewallUxTraceLoggingProvider::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( __std_init_once_begin_initialize(
         &`FirewallUxTraceLoggingProvider::Instance'::`2'::wrapper,
         0,
         &v2,
         (LPVOID *)&v3)
    && v2 )
  {
    qword_18003BFF8 = 0;
    v3 = &qword_18003BFF0;
    qword_18003BFF0 = &NetworkingTriageScenario::FirewallUX::`vftable';
    byte_18003C000 = 0;
    dword_18003C004 = 0;
    qword_18003C008 = (struct _tlgProvider_t *)&`FirewallUxTraceLoggingProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`FirewallUxTraceLoggingProvider::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18003BFF0, qword_18003C008, v0);
    InitOnceComplete(&`FirewallUxTraceLoggingProvider::Instance'::`2'::wrapper, 0, &qword_18003BFF0);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x180008820  mov     rax, rsp
0x180008823  push    rbx
0x180008824  sub     rsp, 20h
0x180008828  lea     r9, [rax+10h]; lpContext
0x18000882c  mov     qword ptr [rax+10h], 0
0x180008834  lea     r8, [rax+8]; fPending
0x180008838  mov     dword ptr [rax+8], 0
0x18000883f  xor     edx, edx; dwFlags
0x180008841  lea     rcx, ?wrapper@?1??Instance@FirewallUxTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VFirewallUxTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x180008848  call    cs:__imp___std_init_once_begin_initialize
0x18000884e  test    eax, eax
0x180008850  jz      short loc_1800088CA
0x180008852  cmp     [rsp+28h+arg_0], 0
0x180008857  jz      short loc_1800088CA
0x180008859  lea     rbx, qword_18003BFF0
0x180008860  mov     cs:qword_18003BFF8, 0
0x18000886b  lea     rax, ??_7FirewallUX@NetworkingTriageScenario@@6B@; const NetworkingTriageScenario::FirewallUX::`vftable'
0x180008872  mov     [rsp+28h+arg_8], rbx
0x180008877  mov     cs:qword_18003BFF0, rax
0x18000887e  mov     cs:byte_18003C000, 0
0x180008885  mov     cs:dword_18003C004, 0
0x18000888f  lea     rax, ?__hInner@?1???0StaticHandle@FirewallUxTraceLoggingProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `FirewallUxTraceLoggingProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180008896  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@FirewallUxTraceLoggingProvider@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x18000889d  mov     cs:qword_18003C008, rax
0x1800088a4  call    atexit
0x1800088a9  mov     rdx, cs:qword_18003C008; struct _tlgProvider_t *
0x1800088b0  mov     rcx, rbx; this
0x1800088b3  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800088b8  mov     r8, rbx; lpContext
0x1800088bb  lea     rcx, ?wrapper@?1??Instance@FirewallUxTraceLoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VFirewallUxTraceLoggingProvider@@@details@wil@@A; lpInitOnce
0x1800088c2  xor     edx, edx; dwFlags
0x1800088c4  call    cs:__imp_InitOnceComplete
0x1800088ca  mov     rax, [rsp+28h+arg_8]
0x1800088cf  mov     rax, [rax+8]
0x1800088d3  add     rsp, 20h
0x1800088d7  pop     rbx
0x1800088d8  retn
```
