# NetworkingTriageScenario::FirewallUX::Provider(void)

- ea: `0x180012fe4`
- end: `0x18001309d`
- name: `?Provider@FirewallUX@NetworkingTriageScenario@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180012c04`
- `0x1800176e4`
- `0x180018568`
- `0x18001f27c`
- `0x18001f45c`
- `0x18001f53c`
- `0x18001f898`

## callees

- `0x1800025d8`
- `0x180008bbc`
- `0x180012fe4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180013088`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180013088`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001300c`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001300c`

## pseudocode

```c
const struct _tlgProvider_t *NetworkingTriageScenario::FirewallUX::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( __std_init_once_begin_initialize(
         &`NetworkingTriageScenario::FirewallUX::Instance'::`2'::wrapper,
         0,
         &v2,
         (LPVOID *)&v3)
    && v2 )
  {
    qword_18003C280 = 0;
    v3 = &qword_18003C278;
    qword_18003C278 = &NetworkingTriageScenario::FirewallUX::`vftable';
    byte_18003C288 = 0;
    dword_18003C28C = 0;
    qword_18003C290 = (struct _tlgProvider_t *)&`NetworkingTriageScenario::FirewallUX::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(`NetworkingTriageScenario::FirewallUX::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_18003C278, qword_18003C290, v0);
    InitOnceComplete(&`NetworkingTriageScenario::FirewallUX::Instance'::`2'::wrapper, 0, &qword_18003C278);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x180012fe4  mov     rax, rsp
0x180012fe7  push    rbx
0x180012fe8  sub     rsp, 20h
0x180012fec  lea     r9, [rax+10h]; lpContext
0x180012ff0  mov     qword ptr [rax+10h], 0
0x180012ff8  lea     r8, [rax+8]; fPending
0x180012ffc  mov     dword ptr [rax+8], 0
0x180013003  xor     edx, edx; dwFlags
0x180013005  lea     rcx, ?wrapper@?1??Instance@FirewallUX@NetworkingTriageScenario@@KAPEAV23@XZ@4V?$static_lazy@VFirewallUX@NetworkingTriageScenario@@@details@wil@@A; lpInitOnce
0x18001300c  call    cs:__imp___std_init_once_begin_initialize
0x180013012  test    eax, eax
0x180013014  jz      short loc_18001308E
0x180013016  cmp     [rsp+28h+arg_0], 0
0x18001301b  jz      short loc_18001308E
0x18001301d  lea     rbx, qword_18003C278
0x180013024  mov     cs:qword_18003C280, 0
0x18001302f  lea     rax, ??_7FirewallUX@NetworkingTriageScenario@@6B@; const NetworkingTriageScenario::FirewallUX::`vftable'
0x180013036  mov     [rsp+28h+arg_8], rbx
0x18001303b  mov     cs:qword_18003C278, rax
0x180013042  mov     cs:byte_18003C288, 0
0x180013049  mov     cs:dword_18003C28C, 0
0x180013053  lea     rax, ?__hInner@?1???0StaticHandle@FirewallUX@NetworkingTriageScenario@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `NetworkingTriageScenario::FirewallUX::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001305a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@FirewallUX@NetworkingTriageScenario@@KAPEAV34@XZ@SA@XZ; void (__cdecl *)()
0x180013061  mov     cs:qword_18003C290, rax
0x180013068  call    atexit
0x18001306d  mov     rdx, cs:qword_18003C290; struct _tlgProvider_t *
0x180013074  mov     rcx, rbx; this
0x180013077  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18001307c  mov     r8, rbx; lpContext
0x18001307f  lea     rcx, ?wrapper@?1??Instance@FirewallUX@NetworkingTriageScenario@@KAPEAV23@XZ@4V?$static_lazy@VFirewallUX@NetworkingTriageScenario@@@details@wil@@A; lpInitOnce
0x180013086  xor     edx, edx; dwFlags
0x180013088  call    cs:__imp_InitOnceComplete
0x18001308e  mov     rax, [rsp+28h+arg_8]
0x180013093  mov     rax, [rax+8]
0x180013097  add     rsp, 20h
0x18001309b  pop     rbx
0x18001309c  retn
```
