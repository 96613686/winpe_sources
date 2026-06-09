# wil::details::static_lazy<USPTelemetry>::get(void (*)(void))

- ea: `0x18000881c`
- end: `0x1800088d6`
- name: `?get@?$static_lazy@VUSPTelemetry@@@details@wil@@QEAAPEAVUSPTelemetry@@P6AXXZ@Z`
- size: `186`
- prototype: `__int64 *__fastcall(__int64, void (__cdecl *)())`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800078f4`
- `0x180007c4c`

## callees

- `0x1800021a4`
- `0x180007434`
- `0x18000881c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008852`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180008852`

## pseudocode

```c
__int64 *__fastcall wil::details::static_lazy<USPTelemetry>::get(__int64 a1, void (__cdecl *a2)())
{
  __int64 v3; // rdx
  void (*v4)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  union _RTL_RUN_ONCE *v6; // [rsp+20h] [rbp-18h] BYREF
  int v7; // [rsp+28h] [rbp-10h]
  WINBOOL v8; // [rsp+40h] [rbp+8h] BYREF
  int v9; // [rsp+44h] [rbp+Ch]
  __int64 *v10; // [rsp+50h] [rbp+18h] BYREF

  v9 = HIDWORD(a1);
  v10 = 0;
  v8 = 0;
  if ( InitOnceBeginInitialize(&`USPTelemetry::Instance'::`2'::wrapper, 0, &v8, (LPVOID *)&v10) && v8 )
  {
    v6 = &`USPTelemetry::Instance'::`2'::wrapper;
    v10 = &qword_180015B38;
    qword_180015B38 = (__int64)&wil::TraceLoggingProvider::`vftable';
    qword_180015B40 = 0;
    byte_180015B48 = 0;
    dword_180015B4C = 0;
    qword_180015B50 = (__int64)&`USPTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(a2);
    v7 = 0;
    wil::details::static_lazy<ControlPanelNavigationTelemetry>::Completer::~Completer(&v6, v3, v4);
  }
  return v10;
}

```

## disassembly

```asm
0x18000881c  mov     rax, rsp
0x18000881f  mov     [rax+10h], rbx
0x180008823  mov     [rax+8], rcx
0x180008827  push    rsi
0x180008828  sub     rsp, 30h
0x18000882c  mov     rbx, rdx
0x18000882f  mov     qword ptr [rax+18h], 0
0x180008837  lea     rsi, ?wrapper@?1??Instance@USPTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VUSPTelemetry@@@details@wil@@A; wil::details::static_lazy<USPTelemetry> `USPTelemetry::Instance(void)'::`2'::wrapper
0x18000883e  mov     dword ptr [rax+8], 0
0x180008845  mov     rcx, rsi; lpInitOnce
0x180008848  lea     r9, [rax+18h]; lpContext
0x18000884c  lea     r8, [rax+8]; fPending
0x180008850  xor     edx, edx; dwFlags
0x180008852  call    cs:__imp_InitOnceBeginInitialize
0x180008858  test    eax, eax
0x18000885a  jz      short loc_1800088C6
0x18000885c  cmp     [rsp+38h+arg_0], 0
0x180008861  jz      short loc_1800088C6
0x180008863  lea     rax, qword_180015B38
0x18000886a  mov     [rsp+38h+var_18], rsi
0x18000886f  mov     [rsp+38h+arg_10], rax
0x180008874  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x18000887b  mov     cs:qword_180015B38, rax
0x180008882  mov     cs:qword_180015B40, 0
0x18000888d  mov     cs:byte_180015B48, 0
0x180008894  mov     cs:dword_180015B4C, 0
0x18000889e  lea     rax, ?__hInner@?1???0StaticHandle@USPTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `USPTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800088a5  mov     rcx, rbx; void (__cdecl *)()
0x1800088a8  mov     cs:qword_180015B50, rax
0x1800088af  call    atexit
0x1800088b4  lea     rcx, [rsp+38h+var_18]
0x1800088b9  mov     [rsp+38h+var_10], 0
0x1800088c1  call    ??1Completer@?$static_lazy@VControlPanelNavigationTelemetry@@@details@wil@@QEAA@XZ; wil::details::static_lazy<ControlPanelNavigationTelemetry>::Completer::~Completer(void)
0x1800088c6  mov     rax, [rsp+38h+arg_10]
0x1800088cb  mov     rbx, [rsp+38h+arg_8]
0x1800088d0  add     rsp, 30h
0x1800088d4  pop     rsi
0x1800088d5  retn
```
