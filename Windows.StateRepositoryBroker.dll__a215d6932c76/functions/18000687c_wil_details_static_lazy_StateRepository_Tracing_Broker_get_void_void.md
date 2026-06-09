# wil::details::static_lazy<StateRepository::Tracing::Broker>::get(void (*)(void))

- ea: `0x18000687c`
- end: `0x180006936`
- name: `?get@?$static_lazy@VBroker@Tracing@StateRepository@@@details@wil@@QEAAPEAVBroker@Tracing@StateRepository@@P6AXXZ@Z`
- size: `186`
- prototype: `__int64 *__fastcall(__int64, void (__cdecl *)())`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003a00`

## callees

- `0x180002134`
- `0x180003f8c`
- `0x18000687c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800068b2`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800068b2`

## pseudocode

```c
__int64 *__fastcall wil::details::static_lazy<StateRepository::Tracing::Broker>::get(__int64 a1, void (__cdecl *a2)())
{
  union _RTL_RUN_ONCE *v4; // [rsp+20h] [rbp-18h] BYREF
  int v5; // [rsp+28h] [rbp-10h]
  BOOL v6; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+44h] [rbp+Ch]
  __int64 *v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = HIDWORD(a1);
  v8 = 0;
  v6 = 0;
  if ( InitOnceBeginInitialize(&`StateRepository::Tracing::Broker::Instance'::`2'::wrapper, 0, &v6, (LPVOID *)&v8) && v6 )
  {
    v4 = &`StateRepository::Tracing::Broker::Instance'::`2'::wrapper;
    v8 = &qword_180013398;
    qword_180013398 = (__int64)&StateRepository::Tracing::Broker::`vftable';
    qword_1800133A0 = 0;
    byte_1800133A8 = 0;
    dword_1800133AC = 0;
    qword_1800133B0 = (__int64)&`StateRepository::Tracing::Broker::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(a2);
    v5 = 0;
    wil::details::static_lazy<StateRepository::Tracing::Broker>::Completer::~Completer(&v4);
  }
  return v8;
}

```

## disassembly

```asm
0x18000687c  mov     rax, rsp
0x18000687f  mov     [rax+10h], rbx
0x180006883  mov     [rax+8], rcx
0x180006887  push    rsi
0x180006888  sub     rsp, 30h
0x18000688c  mov     rbx, rdx
0x18000688f  mov     qword ptr [rax+18h], 0
0x180006897  lea     rsi, ?wrapper@?1??Instance@Broker@Tracing@StateRepository@@KAPEAV234@XZ@4V?$static_lazy@VBroker@Tracing@StateRepository@@@details@wil@@A; wil::details::static_lazy<StateRepository::Tracing::Broker> `StateRepository::Tracing::Broker::Instance(void)'::`2'::wrapper
0x18000689e  mov     dword ptr [rax+8], 0
0x1800068a5  mov     rcx, rsi; lpInitOnce
0x1800068a8  lea     r9, [rax+18h]; lpContext
0x1800068ac  lea     r8, [rax+8]; fPending
0x1800068b0  xor     edx, edx; dwFlags
0x1800068b2  call    cs:__imp_InitOnceBeginInitialize
0x1800068b8  test    eax, eax
0x1800068ba  jz      short loc_180006926
0x1800068bc  cmp     [rsp+38h+arg_0], 0
0x1800068c1  jz      short loc_180006926
0x1800068c3  lea     rax, qword_180013398
0x1800068ca  mov     [rsp+38h+var_18], rsi
0x1800068cf  mov     [rsp+38h+arg_10], rax
0x1800068d4  lea     rax, ??_7Broker@Tracing@StateRepository@@6B@; const StateRepository::Tracing::Broker::`vftable'
0x1800068db  mov     cs:qword_180013398, rax
0x1800068e2  mov     cs:qword_1800133A0, 0
0x1800068ed  mov     cs:byte_1800133A8, 0
0x1800068f4  mov     cs:dword_1800133AC, 0
0x1800068fe  lea     rax, ?__hInner@?1???0StaticHandle@Broker@Tracing@StateRepository@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `StateRepository::Tracing::Broker::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180006905  mov     rcx, rbx; void (__cdecl *)()
0x180006908  mov     cs:qword_1800133B0, rax
0x18000690f  call    atexit
0x180006914  lea     rcx, [rsp+38h+var_18]
0x180006919  mov     [rsp+38h+var_10], 0
0x180006921  call    ??1Completer@?$static_lazy@VBroker@Tracing@StateRepository@@@details@wil@@QEAA@XZ; wil::details::static_lazy<StateRepository::Tracing::Broker>::Completer::~Completer(void)
0x180006926  mov     rax, [rsp+38h+arg_10]
0x18000692b  mov     rbx, [rsp+38h+arg_8]
0x180006930  add     rsp, 30h
0x180006934  pop     rsi
0x180006935  retn
```
