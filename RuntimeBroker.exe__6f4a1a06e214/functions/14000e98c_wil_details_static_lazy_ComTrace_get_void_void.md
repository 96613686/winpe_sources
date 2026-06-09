# wil::details::static_lazy<ComTrace>::get(void (*)(void))

- ea: `0x14000e98c`
- end: `0x14000ea46`
- name: `?get@?$static_lazy@VComTrace@@@details@wil@@QEAAPEAVComTrace@@P6AXXZ@Z`
- size: `186`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x14000df04`
- `0x14000e06c`
- `0x14000e7cc`
- `0x14000eb14`

## callees

- `0x140008f18`
- `0x14000db3c`
- `0x14000e98c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000e9c2`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000e9c2`

## pseudocode

```c
__int64 *__fastcall wil::details::static_lazy<ComTrace>::get(__int64 a1, void (__cdecl *a2)())
{
  union _RTL_RUN_ONCE *v4; // [rsp+20h] [rbp-18h] BYREF
  int v5; // [rsp+28h] [rbp-10h]
  WINBOOL v6; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+44h] [rbp+Ch]
  __int64 *v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = HIDWORD(a1);
  v8 = 0;
  v6 = 0;
  if ( InitOnceBeginInitialize(&`ComTrace::Instance'::`2'::wrapper, 0, &v6, (LPVOID *)&v8) && v6 )
  {
    v4 = &`ComTrace::Instance'::`2'::wrapper;
    v8 = &qword_140018790;
    qword_140018790 = (__int64)&ComTrace::`vftable';
    qword_140018798 = 0;
    byte_1400187A0 = 0;
    dword_1400187A4 = 0;
    qword_1400187A8 = (__int64)&`ComTrace::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(a2);
    v5 = 0;
    wil::details::static_lazy<ComTrace>::Completer::~Completer(&v4);
  }
  return v8;
}

```

## disassembly

```asm
0x14000e98c  mov     rax, rsp
0x14000e98f  mov     [rax+10h], rbx
0x14000e993  mov     [rax+8], rcx
0x14000e997  push    rsi
0x14000e998  sub     rsp, 30h
0x14000e99c  mov     rbx, rdx
0x14000e99f  mov     qword ptr [rax+18h], 0
0x14000e9a7  lea     rsi, ?wrapper@?1??Instance@ComTrace@@KAPEAV2@XZ@4V?$static_lazy@VComTrace@@@details@wil@@A; wil::details::static_lazy<ComTrace> `ComTrace::Instance(void)'::`2'::wrapper
0x14000e9ae  mov     dword ptr [rax+8], 0
0x14000e9b5  mov     rcx, rsi; lpInitOnce
0x14000e9b8  lea     r9, [rax+18h]; lpContext
0x14000e9bc  lea     r8, [rax+8]; fPending
0x14000e9c0  xor     edx, edx; dwFlags
0x14000e9c2  call    cs:__imp_InitOnceBeginInitialize
0x14000e9c8  test    eax, eax
0x14000e9ca  jz      short loc_14000EA36
0x14000e9cc  cmp     [rsp+38h+arg_0], 0
0x14000e9d1  jz      short loc_14000EA36
0x14000e9d3  lea     rax, qword_140018790
0x14000e9da  mov     [rsp+38h+var_18], rsi
0x14000e9df  mov     [rsp+38h+arg_10], rax
0x14000e9e4  lea     rax, ??_7ComTrace@@6B@; const ComTrace::`vftable'
0x14000e9eb  mov     cs:qword_140018790, rax
0x14000e9f2  mov     cs:qword_140018798, 0
0x14000e9fd  mov     cs:byte_1400187A0, 0
0x14000ea04  mov     cs:dword_1400187A4, 0
0x14000ea0e  lea     rax, ?__hInner@?1???0StaticHandle@ComTrace@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `ComTrace::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14000ea15  mov     rcx, rbx; void (__cdecl *)()
0x14000ea18  mov     cs:qword_1400187A8, rax
0x14000ea1f  call    atexit
0x14000ea24  lea     rcx, [rsp+38h+var_18]
0x14000ea29  mov     [rsp+38h+var_10], 0
0x14000ea31  call    ??1Completer@?$static_lazy@VComTrace@@@details@wil@@QEAA@XZ; wil::details::static_lazy<ComTrace>::Completer::~Completer(void)
0x14000ea36  mov     rax, [rsp+38h+arg_10]
0x14000ea3b  mov     rbx, [rsp+38h+arg_8]
0x14000ea40  add     rsp, 30h
0x14000ea44  pop     rsi
0x14000ea45  retn
```
