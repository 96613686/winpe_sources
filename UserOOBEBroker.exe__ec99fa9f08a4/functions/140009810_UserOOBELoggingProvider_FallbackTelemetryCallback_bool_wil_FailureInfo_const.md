# UserOOBELoggingProvider::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x140009810`
- end: `0x1400098ef`
- name: `?FallbackTelemetryCallback@UserOOBELoggingProvider@@SAX_NAEBUFailureInfo@wil@@@Z`
- size: `223`
- prototype: `void __fastcall(bool, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140002534`
- `0x140009810`
- `0x14000bdf0`
- `0x14000f010`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x140009846`
- `KERNEL32!InitOnceBeginInitialize` at `0x140009846`
- `KERNEL32!InitOnceComplete` at `0x1400098c2`
- `KERNEL32!InitOnceComplete` at `0x1400098c2`

## pseudocode

```c
void __fastcall UserOOBELoggingProvider::FallbackTelemetryCallback(char a1, const struct wil::FailureInfo *a2)
{
  __int64 v4; // rdx
  void (*v5)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  BOOL v6; // [rsp+40h] [rbp+18h] BYREF
  LPVOID v7; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v6 = 0;
  if ( InitOnceBeginInitialize(&`UserOOBELoggingProvider::Instance'::`2'::wrapper, 0, &v6, &v7) && v6 )
  {
    qword_140017CD8 = 0;
    v7 = &qword_140017CD0;
    qword_140017CD0 = &wil::details::FeatureLogging::`vftable';
    byte_140017CE0 = 0;
    dword_140017CE4 = 0;
    qword_140017CE8 = (struct _tlgProvider_t *)&`UserOOBELoggingProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_60eb96f055f4c24abaa472c7ceb402f2_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_140017CD0, qword_140017CE8, v5);
    InitOnceComplete(&`UserOOBELoggingProvider::Instance'::`2'::wrapper, 0, &qword_140017CD0);
  }
  LOBYTE(v4) = a1;
  (*(void (__fastcall **)(LPVOID, __int64, const struct wil::FailureInfo *))(*(_QWORD *)v7 + 16LL))(v7, v4, a2);
}

```

## disassembly

```asm
0x140009810  mov     rax, rsp
0x140009813  mov     [rax+8], rbx
0x140009817  mov     [rax+10h], rsi
0x14000981b  push    rdi
0x14000981c  sub     rsp, 20h
0x140009820  mov     rbx, rdx
0x140009823  mov     qword ptr [rax+20h], 0
0x14000982b  mov     dil, cl
0x14000982e  mov     dword ptr [rax+18h], 0
0x140009835  xor     edx, edx; dwFlags
0x140009837  lea     rcx, ?wrapper@?1??Instance@UserOOBELoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VUserOOBELoggingProvider@@@details@wil@@A; lpInitOnce
0x14000983e  lea     r9, [rax+20h]; lpContext
0x140009842  lea     r8, [rax+18h]; fPending
0x140009846  call    cs:__imp_InitOnceBeginInitialize
0x14000984c  test    eax, eax
0x14000984e  jz      short loc_1400098C8
0x140009850  cmp     [rsp+28h+arg_10], 0
0x140009855  jz      short loc_1400098C8
0x140009857  lea     rsi, qword_140017CD0
0x14000985e  mov     cs:qword_140017CD8, 0
0x140009869  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x140009870  mov     [rsp+28h+arg_18], rsi
0x140009875  mov     cs:qword_140017CD0, rax
0x14000987c  mov     cs:byte_140017CE0, 0
0x140009883  mov     cs:dword_140017CE4, 0
0x14000988d  lea     rax, ?__hInner@?1???0StaticHandle@UserOOBELoggingProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `UserOOBELoggingProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140009894  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_60eb96f055f4c24abaa472c7ceb402f2_@@CA@XZ; void (__cdecl *)()
0x14000989b  mov     cs:qword_140017CE8, rax
0x1400098a2  call    atexit
0x1400098a7  mov     rdx, cs:qword_140017CE8; struct _tlgProvider_t *
0x1400098ae  mov     rcx, rsi; this
0x1400098b1  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1400098b6  mov     r8, rsi; lpContext
0x1400098b9  lea     rcx, ?wrapper@?1??Instance@UserOOBELoggingProvider@@KAPEAV2@XZ@4V?$static_lazy@VUserOOBELoggingProvider@@@details@wil@@A; lpInitOnce
0x1400098c0  xor     edx, edx; dwFlags
0x1400098c2  call    cs:__imp_InitOnceComplete
0x1400098c8  mov     rcx, [rsp+28h+arg_18]
0x1400098cd  mov     r8, rbx
0x1400098d0  mov     dl, dil
0x1400098d3  mov     rax, [rcx]
0x1400098d6  mov     rax, [rax+10h]
0x1400098da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400098df  mov     rbx, [rsp+28h+arg_0]
0x1400098e4  mov     rsi, [rsp+28h+arg_8]
0x1400098e9  add     rsp, 20h
0x1400098ed  pop     rdi
0x1400098ee  retn
```
