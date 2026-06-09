# RulesEngine::~RulesEngine(void)

- ea: `0x180013bd0`
- end: `0x180013d7e`
- name: `??1RulesEngine@@QEAA@XZ`
- size: `430`
- prototype: `void __fastcall(RulesEngine *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18000c6ec`
- `0x18000d650`
- `0x18000f158`

## callees

- `0x180008ea8`
- `0x180013bd0`
- `0x180070188`
- `0x1800dddf4`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013d46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013d54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013d46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180013d54`
- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x180013bf0`
- `api-ms-win-oobe-notification-l1-1-0!UnregisterWaitUntilOOBECompleted` at `0x180013bf0`

## pseudocode

```c
void __fastcall RulesEngine::~RulesEngine(RulesEngine *this)
{
  UsoScheduler *v2; // rdi
  void *v3; // rdi
  void *v4; // rdi
  void *v5; // rdi
  void *v6; // rdi
  void *v7; // rdi
  void *v8; // rdi
  void *v9; // rdi
  void (__fastcall ***v10)(_QWORD, __int64); // rcx
  void (__fastcall ***v11)(_QWORD, __int64); // rcx
  void (__fastcall ***v12)(_QWORD, __int64); // rcx
  void (__fastcall ***v13)(_QWORD, __int64); // rcx
  void *v14; // rcx
  unsigned int v15; // r8d
  const char *v16; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( _InterlockedExchange64(&qword_1801500D8, 0) )
    UnregisterWaitUntilOOBECompleted();
  v2 = (UsoScheduler *)*((_QWORD *)this + 14);
  if ( v2 )
  {
    UsoScheduler::~UsoScheduler(v2);
    operator delete(v2, (const struct std::nothrow_t *)0x128);
  }
  v3 = (void *)*((_QWORD *)this + 13);
  if ( v3 )
  {
    UsoScheduler::~UsoScheduler(*((UsoScheduler **)this + 13));
    operator delete(v3, (const struct std::nothrow_t *)0x128);
  }
  v4 = (void *)*((_QWORD *)this + 12);
  if ( v4 )
  {
    UsoScheduler::~UsoScheduler(*((UsoScheduler **)this + 12));
    operator delete(v4, (const struct std::nothrow_t *)0x128);
  }
  v5 = (void *)*((_QWORD *)this + 11);
  if ( v5 )
  {
    UsoScheduler::~UsoScheduler(*((UsoScheduler **)this + 11));
    operator delete(v5, (const struct std::nothrow_t *)0x128);
  }
  v6 = (void *)*((_QWORD *)this + 10);
  if ( v6 )
  {
    UsoScheduler::~UsoScheduler(*((UsoScheduler **)this + 10));
    operator delete(v6, (const struct std::nothrow_t *)0x128);
  }
  v7 = (void *)*((_QWORD *)this + 9);
  if ( v7 )
  {
    UsoScheduler::~UsoScheduler(*((UsoScheduler **)this + 9));
    operator delete(v7, (const struct std::nothrow_t *)0x128);
  }
  v8 = (void *)*((_QWORD *)this + 8);
  if ( v8 )
  {
    UsoScheduler::~UsoScheduler(*((UsoScheduler **)this + 8));
    operator delete(v8, (const struct std::nothrow_t *)0x128);
  }
  v9 = (void *)*((_QWORD *)this + 7);
  if ( v9 )
  {
    UsoScheduler::~UsoScheduler(*((UsoScheduler **)this + 7));
    operator delete(v9, (const struct std::nothrow_t *)0x128);
  }
  v10 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 5);
  if ( v10 )
    (**v10)(v10, 1);
  v11 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 4);
  if ( v11 )
    (**v11)(v11, 1);
  v12 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 3);
  if ( v12 )
    (**v12)(v12, 1);
  v13 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 2);
  if ( v13 )
    (**v13)(v13, 1);
  v14 = (void *)*((_QWORD *)this + 1);
  if ( v14 && v14 != (void *)-1LL )
    CloseHandle(v14);
  if ( *(_QWORD *)this )
  {
    if ( !CloseHandle(*(HANDLE *)this) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v15, v16);
  }
}

```

## disassembly

```asm
0x180013bd0  mov     [rsp+arg_0], rbx
0x180013bd5  mov     [rsp+arg_8], rsi
0x180013bda  push    rdi
0x180013bdb  sub     rsp, 20h
0x180013bdf  mov     rbx, rcx
0x180013be2  xor     ecx, ecx
0x180013be4  xchg    rcx, cs:qword_1801500D8
0x180013beb  test    rcx, rcx
0x180013bee  jz      short loc_180013BF6
0x180013bf0  call    cs:__imp_UnregisterWaitUntilOOBECompleted
0x180013bf6  mov     rdi, [rbx+70h]
0x180013bfa  mov     esi, 128h
0x180013bff  test    rdi, rdi
0x180013c02  jz      short loc_180013C16
0x180013c04  mov     rcx, rdi; this
0x180013c07  call    ??1UsoScheduler@@QEAA@XZ; UsoScheduler::~UsoScheduler(void)
0x180013c0c  mov     edx, esi; struct std::nothrow_t *
0x180013c0e  mov     rcx, rdi; void *
0x180013c11  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013c16  mov     rdi, [rbx+68h]
0x180013c1a  test    rdi, rdi
0x180013c1d  jz      short loc_180013C32
0x180013c1f  mov     rcx, rdi; this
0x180013c22  call    ??1UsoScheduler@@QEAA@XZ; UsoScheduler::~UsoScheduler(void)
0x180013c27  mov     rdx, rsi; struct std::nothrow_t *
0x180013c2a  mov     rcx, rdi; void *
0x180013c2d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013c32  mov     rdi, [rbx+60h]
0x180013c36  test    rdi, rdi
0x180013c39  jz      short loc_180013C4E
0x180013c3b  mov     rcx, rdi; this
0x180013c3e  call    ??1UsoScheduler@@QEAA@XZ; UsoScheduler::~UsoScheduler(void)
0x180013c43  mov     rdx, rsi; struct std::nothrow_t *
0x180013c46  mov     rcx, rdi; void *
0x180013c49  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013c4e  mov     rdi, [rbx+58h]
0x180013c52  test    rdi, rdi
0x180013c55  jz      short loc_180013C6A
0x180013c57  mov     rcx, rdi; this
0x180013c5a  call    ??1UsoScheduler@@QEAA@XZ; UsoScheduler::~UsoScheduler(void)
0x180013c5f  mov     rdx, rsi; struct std::nothrow_t *
0x180013c62  mov     rcx, rdi; void *
0x180013c65  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013c6a  mov     rdi, [rbx+50h]
0x180013c6e  test    rdi, rdi
0x180013c71  jz      short loc_180013C86
0x180013c73  mov     rcx, rdi; this
0x180013c76  call    ??1UsoScheduler@@QEAA@XZ; UsoScheduler::~UsoScheduler(void)
0x180013c7b  mov     rdx, rsi; struct std::nothrow_t *
0x180013c7e  mov     rcx, rdi; void *
0x180013c81  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013c86  mov     rdi, [rbx+48h]
0x180013c8a  test    rdi, rdi
0x180013c8d  jz      short loc_180013CA2
0x180013c8f  mov     rcx, rdi; this
0x180013c92  call    ??1UsoScheduler@@QEAA@XZ; UsoScheduler::~UsoScheduler(void)
0x180013c97  mov     rdx, rsi; struct std::nothrow_t *
0x180013c9a  mov     rcx, rdi; void *
0x180013c9d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013ca2  mov     rdi, [rbx+40h]
0x180013ca6  test    rdi, rdi
0x180013ca9  jz      short loc_180013CBE
0x180013cab  mov     rcx, rdi; this
0x180013cae  call    ??1UsoScheduler@@QEAA@XZ; UsoScheduler::~UsoScheduler(void)
0x180013cb3  mov     rdx, rsi; struct std::nothrow_t *
0x180013cb6  mov     rcx, rdi; void *
0x180013cb9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013cbe  mov     rdi, [rbx+38h]
0x180013cc2  test    rdi, rdi
0x180013cc5  jz      short loc_180013CDA
0x180013cc7  mov     rcx, rdi; this
0x180013cca  call    ??1UsoScheduler@@QEAA@XZ; UsoScheduler::~UsoScheduler(void)
0x180013ccf  mov     rdx, rsi; struct std::nothrow_t *
0x180013cd2  mov     rcx, rdi; void *
0x180013cd5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180013cda  mov     rcx, [rbx+28h]
0x180013cde  mov     edi, 1
0x180013ce3  test    rcx, rcx
0x180013ce6  jz      short loc_180013CF5
0x180013ce8  mov     rax, [rcx]
0x180013ceb  mov     edx, edi
0x180013ced  mov     rax, [rax]
0x180013cf0  call    _guard_dispatch_icall
0x180013cf5  mov     rcx, [rbx+20h]
0x180013cf9  test    rcx, rcx
0x180013cfc  jz      short loc_180013D0B
0x180013cfe  mov     rax, [rcx]
0x180013d01  mov     edx, edi
0x180013d03  mov     rax, [rax]
0x180013d06  call    _guard_dispatch_icall
0x180013d0b  mov     rcx, [rbx+18h]
0x180013d0f  test    rcx, rcx
0x180013d12  jz      short loc_180013D21
0x180013d14  mov     rax, [rcx]
0x180013d17  mov     edx, edi
0x180013d19  mov     rax, [rax]
0x180013d1c  call    _guard_dispatch_icall
0x180013d21  mov     rcx, [rbx+10h]
0x180013d25  test    rcx, rcx
0x180013d28  jz      short loc_180013D37
0x180013d2a  mov     rax, [rcx]
0x180013d2d  mov     edx, edi
0x180013d2f  mov     rax, [rax]
0x180013d32  call    _guard_dispatch_icall
0x180013d37  mov     rcx, [rbx+8]; hObject
0x180013d3b  test    rcx, rcx
0x180013d3e  jz      short loc_180013D4C
0x180013d40  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180013d44  jz      short loc_180013D4C
0x180013d46  call    cs:__imp_CloseHandle
0x180013d4c  mov     rcx, [rbx]; hObject
0x180013d4f  test    rcx, rcx
0x180013d52  jz      short loc_180013D5E
0x180013d54  call    cs:__imp_CloseHandle
0x180013d5a  test    eax, eax
0x180013d5c  jz      short loc_180013D6E
0x180013d5e  mov     rbx, [rsp+28h+arg_0]
0x180013d63  mov     rsi, [rsp+28h+arg_8]
0x180013d68  add     rsp, 20h
0x180013d6c  pop     rdi
0x180013d6d  retn
0x180013d6e  mov     rcx, [rsp+28h]; this
0x180013d73  mov     edx, 9D1h; void *
0x180013d78  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
