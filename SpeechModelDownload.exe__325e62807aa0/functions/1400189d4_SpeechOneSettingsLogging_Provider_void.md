# SpeechOneSettingsLogging::Provider(void)

- ea: `0x1400189d4`
- end: `0x140018a8d`
- name: `?Provider@SpeechOneSettingsLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013fcc`
- `0x140014080`
- `0x140015e08`
- `0x140015f50`
- `0x1400180f0`
- `0x140019160`
- `0x140019210`
- `0x1400192b0`
- `0x140019a70`
- `0x140019b20`
- `0x140019bc0`

## callees

- `0x1400028b8`
- `0x1400078fc`
- `0x1400189d4`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1400189fc`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1400189fc`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140018a78`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x140018a78`

## pseudocode

```c
const struct _tlgProvider_t *SpeechOneSettingsLogging::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`SpeechOneSettingsLogging::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_140030BE8 = 0;
    v3 = &qword_140030BE0;
    qword_140030BE0 = &FlightDataRecorderActivityClass::`vftable';
    byte_140030BF0 = 0;
    dword_140030BF4 = 0;
    qword_140030BF8 = (struct _tlgProvider_t *)&`SpeechOneSettingsLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_3906f298aabbccc326f87bb683f4abcd_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_140030BE0, qword_140030BF8, v0);
    InitOnceComplete(&`SpeechOneSettingsLogging::Instance'::`2'::wrapper, 0, &qword_140030BE0);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x1400189d4  mov     rax, rsp
0x1400189d7  push    rbx
0x1400189d8  sub     rsp, 20h
0x1400189dc  lea     r9, [rax+10h]; lpContext
0x1400189e0  mov     qword ptr [rax+10h], 0
0x1400189e8  lea     r8, [rax+8]; fPending
0x1400189ec  mov     dword ptr [rax+8], 0
0x1400189f3  xor     edx, edx; dwFlags
0x1400189f5  lea     rcx, ?wrapper@?1??Instance@SpeechOneSettingsLogging@@KAPEAV2@XZ@4V?$static_lazy@VSpeechOneSettingsLogging@@@details@wil@@A; lpInitOnce
0x1400189fc  call    cs:__imp_InitOnceBeginInitialize
0x140018a02  test    eax, eax
0x140018a04  jz      short loc_140018A7E
0x140018a06  cmp     [rsp+28h+arg_0], 0
0x140018a0b  jz      short loc_140018A7E
0x140018a0d  lea     rbx, qword_140030BE0
0x140018a14  mov     cs:qword_140030BE8, 0
0x140018a1f  lea     rax, ??_7FlightDataRecorderActivityClass@@6B@; const FlightDataRecorderActivityClass::`vftable'
0x140018a26  mov     [rsp+28h+arg_8], rbx
0x140018a2b  mov     cs:qword_140030BE0, rax
0x140018a32  mov     cs:byte_140030BF0, 0
0x140018a39  mov     cs:dword_140030BF4, 0
0x140018a43  lea     rax, ?__hInner@?1???0StaticHandle@SpeechOneSettingsLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `SpeechOneSettingsLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140018a4a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_3906f298aabbccc326f87bb683f4abcd_@@CA@XZ; void (__cdecl *)()
0x140018a51  mov     cs:qword_140030BF8, rax
0x140018a58  call    atexit
0x140018a5d  mov     rdx, cs:qword_140030BF8; struct _tlgProvider_t *
0x140018a64  mov     rcx, rbx; this
0x140018a67  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x140018a6c  mov     r8, rbx; lpContext
0x140018a6f  lea     rcx, ?wrapper@?1??Instance@SpeechOneSettingsLogging@@KAPEAV2@XZ@4V?$static_lazy@VSpeechOneSettingsLogging@@@details@wil@@A; lpInitOnce
0x140018a76  xor     edx, edx; dwFlags
0x140018a78  call    cs:__imp_InitOnceComplete
0x140018a7e  mov     rax, [rsp+28h+arg_8]
0x140018a83  mov     rax, [rax+8]
0x140018a87  add     rsp, 20h
0x140018a8b  pop     rbx
0x140018a8c  retn
```
