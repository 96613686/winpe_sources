# wil::details::static_lazy<CoreGlobConfigTraceLogging>::get(void (*)(void))

- ea: `0x18001e4b0`
- end: `0x18001e56a`
- name: `?get@?$static_lazy@VCoreGlobConfigTraceLogging@@@details@wil@@QEAAPEAVCoreGlobConfigTraceLogging@@P6AXXZ@Z`
- size: `186`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016fcc`
- `0x1800218b0`

## callees

- `0x180002730`
- `0x180011654`
- `0x18001e4b0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001e4e6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001e4e6`

## pseudocode

```c
__int64 *__fastcall wil::details::static_lazy<CoreGlobConfigTraceLogging>::get(__int64 a1, void (__cdecl *a2)())
{
  union _RTL_RUN_ONCE *v4; // [rsp+20h] [rbp-18h] BYREF
  int v5; // [rsp+28h] [rbp-10h]
  WINBOOL v6; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+44h] [rbp+Ch]
  __int64 *v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = HIDWORD(a1);
  v8 = 0;
  v6 = 0;
  if ( __std_init_once_begin_initialize(&`CoreGlobConfigTraceLogging::Instance'::`2'::wrapper, 0, &v6, (LPVOID *)&v8)
    && v6 )
  {
    v4 = &`CoreGlobConfigTraceLogging::Instance'::`2'::wrapper;
    v8 = &qword_180032D08;
    qword_180032D08 = (__int64)&CoreGlobConfigTraceLogging::`vftable';
    qword_180032D10 = 0;
    byte_180032D18 = 0;
    dword_180032D1C = 0;
    qword_180032D20 = (__int64)&`CoreGlobConfigTraceLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(a2);
    v5 = 0;
    wil::details::static_lazy<CoreGlobConfigTraceLogging>::Completer::~Completer(&v4);
  }
  return v8;
}

```

## disassembly

```asm
0x18001e4b0  mov     rax, rsp
0x18001e4b3  mov     [rax+10h], rbx
0x18001e4b7  mov     [rax+8], rcx
0x18001e4bb  push    rsi
0x18001e4bc  sub     rsp, 30h
0x18001e4c0  mov     rbx, rdx
0x18001e4c3  mov     qword ptr [rax+18h], 0
0x18001e4cb  lea     rsi, ?wrapper@?1??Instance@CoreGlobConfigTraceLogging@@KAPEAV2@XZ@4V?$static_lazy@VCoreGlobConfigTraceLogging@@@details@wil@@A; wil::details::static_lazy<CoreGlobConfigTraceLogging> `CoreGlobConfigTraceLogging::Instance(void)'::`2'::wrapper
0x18001e4d2  mov     dword ptr [rax+8], 0
0x18001e4d9  mov     rcx, rsi; lpInitOnce
0x18001e4dc  lea     r9, [rax+18h]; lpContext
0x18001e4e0  lea     r8, [rax+8]; fPending
0x18001e4e4  xor     edx, edx; dwFlags
0x18001e4e6  call    cs:__imp___std_init_once_begin_initialize
0x18001e4ec  test    eax, eax
0x18001e4ee  jz      short loc_18001E55A
0x18001e4f0  cmp     [rsp+38h+arg_0], 0
0x18001e4f5  jz      short loc_18001E55A
0x18001e4f7  lea     rax, qword_180032D08
0x18001e4fe  mov     [rsp+38h+var_18], rsi
0x18001e503  mov     [rsp+38h+arg_10], rax
0x18001e508  lea     rax, ??_7CoreGlobConfigTraceLogging@@6B@; const CoreGlobConfigTraceLogging::`vftable'
0x18001e50f  mov     cs:qword_180032D08, rax
0x18001e516  mov     cs:qword_180032D10, 0
0x18001e521  mov     cs:byte_180032D18, 0
0x18001e528  mov     cs:dword_180032D1C, 0
0x18001e532  lea     rax, ?__hInner@?1???0StaticHandle@CoreGlobConfigTraceLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `CoreGlobConfigTraceLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001e539  mov     rcx, rbx; void (__cdecl *)()
0x18001e53c  mov     cs:qword_180032D20, rax
0x18001e543  call    atexit
0x18001e548  lea     rcx, [rsp+38h+var_18]
0x18001e54d  mov     [rsp+38h+var_10], 0
0x18001e555  call    ??1Completer@?$static_lazy@VCoreGlobConfigTraceLogging@@@details@wil@@QEAA@XZ; wil::details::static_lazy<CoreGlobConfigTraceLogging>::Completer::~Completer(void)
0x18001e55a  mov     rax, [rsp+38h+arg_10]
0x18001e55f  mov     rbx, [rsp+38h+arg_8]
0x18001e564  add     rsp, 30h
0x18001e568  pop     rsi
0x18001e569  retn
```
