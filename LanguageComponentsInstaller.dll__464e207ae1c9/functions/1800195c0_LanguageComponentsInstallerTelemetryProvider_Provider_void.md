# LanguageComponentsInstallerTelemetryProvider::Provider(void)

- ea: `0x1800195c0`
- end: `0x180019697`
- name: `?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `215`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `14`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800121d8`
- `0x180018c50`
- `0x18001bb94`
- `0x18001bdc8`
- `0x18001c058`
- `0x18001c1d0`
- `0x18001c460`
- `0x180024938`
- `0x180024e50`
- `0x180025240`
- `0x1800253c8`
- `0x180025550`
- `0x180025660`
- `0x1800258e0`

## callees

- `0x180003520`
- `0x180003a08`
- `0x1800195c0`
- `0x18001a9c0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180019675`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180019675`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800195f9`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800195f9`

## pseudocode

```c
const struct _tlgProvider_t *LanguageComponentsInstallerTelemetryProvider::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(
         &`LanguageComponentsInstallerTelemetryProvider::Instance'::`2'::wrapper,
         0,
         &fPending,
         &Context)
    && fPending )
  {
    qword_1800378A8 = 0;
    Context = &qword_1800378A0;
    qword_1800378A0 = &wil::details::FeatureLogging::`vftable';
    byte_1800378B0 = 0;
    dword_1800378B4 = 0;
    qword_1800378B8 = (struct _tlgProvider_t *)&`LanguageComponentsInstallerTelemetryProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_3ffd2dbb9d2c673f3031976d196516f5_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_1800378A0, qword_1800378B8, v0);
    InitOnceComplete(&`LanguageComponentsInstallerTelemetryProvider::Instance'::`2'::wrapper, 0, &qword_1800378A0);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x1800195c0  push    rbx
0x1800195c2  sub     rsp, 40h
0x1800195c6  mov     rax, cs:__security_cookie
0x1800195cd  xor     rax, rsp
0x1800195d0  mov     [rsp+48h+var_18], rax
0x1800195d5  lea     r9, [rsp+48h+Context]; lpContext
0x1800195da  mov     [rsp+48h+Context], 0
0x1800195e3  lea     r8, [rsp+48h+fPending]; fPending
0x1800195e8  mov     [rsp+48h+fPending], 0
0x1800195f0  xor     edx, edx; dwFlags
0x1800195f2  lea     rcx, ?wrapper@?1??Instance@LanguageComponentsInstallerTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VLanguageComponentsInstallerTelemetryProvider@@@details@wil@@A; lpInitOnce
0x1800195f9  call    cs:__imp_InitOnceBeginInitialize
0x1800195ff  test    eax, eax
0x180019601  jz      short loc_18001967B
0x180019603  cmp     [rsp+48h+fPending], 0
0x180019608  jz      short loc_18001967B
0x18001960a  lea     rbx, qword_1800378A0
0x180019611  mov     cs:qword_1800378A8, 0
0x18001961c  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180019623  mov     [rsp+48h+Context], rbx
0x180019628  mov     cs:qword_1800378A0, rax
0x18001962f  mov     cs:byte_1800378B0, 0
0x180019636  mov     cs:dword_1800378B4, 0
0x180019640  lea     rax, ?__hInner@?1???0StaticHandle@LanguageComponentsInstallerTelemetryProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `LanguageComponentsInstallerTelemetryProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180019647  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_3ffd2dbb9d2c673f3031976d196516f5_@@CA@XZ; void (__cdecl *)()
0x18001964e  mov     cs:qword_1800378B8, rax
0x180019655  call    atexit
0x18001965a  mov     rdx, cs:qword_1800378B8; struct _tlgProvider_t *
0x180019661  mov     rcx, rbx; this
0x180019664  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x180019669  mov     r8, rbx; lpContext
0x18001966c  lea     rcx, ?wrapper@?1??Instance@LanguageComponentsInstallerTelemetryProvider@@KAPEAV2@XZ@4V?$static_lazy@VLanguageComponentsInstallerTelemetryProvider@@@details@wil@@A; lpInitOnce
0x180019673  xor     edx, edx; dwFlags
0x180019675  call    cs:__imp_InitOnceComplete
0x18001967b  mov     rax, [rsp+48h+Context]
0x180019680  mov     rax, [rax+8]
0x180019684  mov     rcx, [rsp+48h+var_18]
0x180019689  xor     rcx, rsp; StackCookie
0x18001968c  call    __security_check_cookie
0x180019691  add     rsp, 40h
0x180019695  pop     rbx
0x180019696  retn
```
