# wil::details::static_lazy<DirectXDatabaseUpdaterLogging>::get(void (*)(void))

- ea: `0x14000e1c0`
- end: `0x14000e27a`
- name: `?get@?$static_lazy@VDirectXDatabaseUpdaterLogging@@@details@wil@@QEAAPEAVDirectXDatabaseUpdaterLogging@@P6AXXZ@Z`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000946c`

## callees

- `0x1400031f8`
- `0x140005ed4`
- `0x14000e1c0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000e1f6`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000e1f6`

## pseudocode

```c
__int64 *__fastcall wil::details::static_lazy<DirectXDatabaseUpdaterLogging>::get(__int64 a1, void (__cdecl *a2)())
{
  union _RTL_RUN_ONCE *v4; // [rsp+20h] [rbp-18h] BYREF
  int v5; // [rsp+28h] [rbp-10h]
  BOOL v6; // [rsp+40h] [rbp+8h] BYREF
  int v7; // [rsp+44h] [rbp+Ch]
  __int64 *v8; // [rsp+50h] [rbp+18h] BYREF

  v7 = HIDWORD(a1);
  v8 = 0;
  v6 = 0;
  if ( InitOnceBeginInitialize(&`DirectXDatabaseUpdaterLogging::Instance'::`2'::wrapper, 0, &v6, (LPVOID *)&v8) && v6 )
  {
    v4 = &`DirectXDatabaseUpdaterLogging::Instance'::`2'::wrapper;
    v8 = &qword_140025448;
    qword_140025448 = (__int64)&DirectXDatabaseUpdaterLogging::`vftable';
    qword_140025450 = 0;
    byte_140025458 = 0;
    dword_14002545C = 0;
    qword_140025460 = (__int64)&`DirectXDatabaseUpdaterLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(a2);
    v5 = 0;
    wil::details::static_lazy<DirectXDatabaseUpdaterLogging>::Completer::~Completer(&v4);
  }
  return v8;
}

```

## disassembly

```asm
0x14000e1c0  mov     rax, rsp
0x14000e1c3  mov     [rax+10h], rbx
0x14000e1c7  mov     [rax+8], rcx
0x14000e1cb  push    rsi
0x14000e1cc  sub     rsp, 30h
0x14000e1d0  mov     rbx, rdx
0x14000e1d3  mov     qword ptr [rax+18h], 0
0x14000e1db  lea     rsi, ?wrapper@?1??Instance@DirectXDatabaseUpdaterLogging@@KAPEAV2@XZ@4V?$static_lazy@VDirectXDatabaseUpdaterLogging@@@details@wil@@A; wil::details::static_lazy<DirectXDatabaseUpdaterLogging> `DirectXDatabaseUpdaterLogging::Instance(void)'::`2'::wrapper
0x14000e1e2  mov     dword ptr [rax+8], 0
0x14000e1e9  mov     rcx, rsi; lpInitOnce
0x14000e1ec  lea     r9, [rax+18h]; lpContext
0x14000e1f0  lea     r8, [rax+8]; fPending
0x14000e1f4  xor     edx, edx; dwFlags
0x14000e1f6  call    cs:__imp_InitOnceBeginInitialize
0x14000e1fc  test    eax, eax
0x14000e1fe  jz      short loc_14000E26A
0x14000e200  cmp     [rsp+38h+arg_0], 0
0x14000e205  jz      short loc_14000E26A
0x14000e207  lea     rax, qword_140025448
0x14000e20e  mov     [rsp+38h+var_18], rsi
0x14000e213  mov     [rsp+38h+arg_10], rax
0x14000e218  lea     rax, ??_7DirectXDatabaseUpdaterLogging@@6B@; const DirectXDatabaseUpdaterLogging::`vftable'
0x14000e21f  mov     cs:qword_140025448, rax
0x14000e226  mov     cs:qword_140025450, 0
0x14000e231  mov     cs:byte_140025458, 0
0x14000e238  mov     cs:dword_14002545C, 0
0x14000e242  lea     rax, ?__hInner@?1???0StaticHandle@DirectXDatabaseUpdaterLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `DirectXDatabaseUpdaterLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14000e249  mov     rcx, rbx; void (__cdecl *)()
0x14000e24c  mov     cs:qword_140025460, rax
0x14000e253  call    atexit
0x14000e258  lea     rcx, [rsp+38h+var_18]
0x14000e25d  mov     [rsp+38h+var_10], 0
0x14000e265  call    ??1Completer@?$static_lazy@VDirectXDatabaseUpdaterLogging@@@details@wil@@QEAA@XZ; wil::details::static_lazy<DirectXDatabaseUpdaterLogging>::Completer::~Completer(void)
0x14000e26a  mov     rax, [rsp+38h+arg_10]
0x14000e26f  mov     rbx, [rsp+38h+arg_8]
0x14000e274  add     rsp, 30h
0x14000e278  pop     rsi
0x14000e279  retn
```
