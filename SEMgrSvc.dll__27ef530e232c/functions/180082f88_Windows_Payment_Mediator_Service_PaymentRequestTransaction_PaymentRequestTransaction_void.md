# Windows::Payment::Mediator::Service::PaymentRequestTransaction::~PaymentRequestTransaction(void)

- ea: `0x180082f88`
- end: `0x18008308a`
- name: `??1PaymentRequestTransaction@Service@Mediator@Payment@Windows@@QEAA@XZ`
- size: `258`
- prototype: `void __fastcall(Windows::Payment::Mediator::Service::PaymentRequestTransaction *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, service_task`

## callers

- `0x18007e964`
- `0x18007f720`

## callees

- `0x1800049c4`
- `0x18000e4c8`
- `0x180013274`
- `0x180082f88`
- `0x180088fa0`
- `0x180088fd4`
- `0x180089134`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180083040`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180083040`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082fa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082fc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082fa1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180082fc0`

## pseudocode

```c
void __fastcall Windows::Payment::Mediator::Service::PaymentRequestTransaction::~PaymentRequestTransaction(
        Windows::Payment::Mediator::Service::PaymentRequestTransaction *this)
{
  void *v2; // rcx
  unsigned int v3; // r8d
  const char *v4; // r9
  void *v5; // rcx
  unsigned int v6; // r8d
  const char *v7; // r9
  void *v8; // rdi
  void *v9; // rdi
  void *v10; // rdi
  volatile signed __int32 *v11; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 19);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v3, v4);
  v5 = (void *)*((_QWORD *)this + 18);
  if ( v5 && !CloseHandle(v5) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v6, v7);
  v8 = (void *)*((_QWORD *)this + 16);
  if ( v8 )
  {
    FreePaymentServiceRequestChangeResult(*((struct _PaymentServiceRequestChangeResult **)this + 16));
    operator delete(v8);
  }
  v9 = (void *)*((_QWORD *)this + 15);
  if ( v9 )
  {
    FreePaymentServiceRequestChangeDetails(*((struct _PaymentServiceRequestChangeDetails **)this + 15));
    operator delete(v9);
  }
  v10 = (void *)*((_QWORD *)this + 14);
  if ( v10 )
  {
    FreePaymentServiceTransaction(*((struct _PaymentServiceTransaction **)this + 14));
    operator delete(v10);
  }
  std::wstring::~wstring((char *)this + 80);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  v11 = (volatile signed __int32 *)*((_QWORD *)this + 1);
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
  }
}

```

## disassembly

```asm
0x180082f88  mov     [rsp+arg_0], rbx
0x180082f8d  push    rdi
0x180082f8e  sub     rsp, 20h
0x180082f92  mov     rbx, rcx
0x180082f95  mov     rcx, [rcx+98h]; hObject
0x180082f9c  test    rcx, rcx
0x180082f9f  jz      short loc_180082FB4
0x180082fa1  call    cs:__imp_CloseHandle
0x180082fa7  mov     rcx, [rsp+28h]; this
0x180082fac  test    eax, eax
0x180082fae  jz      loc_18008307F
0x180082fb4  mov     rcx, [rbx+90h]; hObject
0x180082fbb  test    rcx, rcx
0x180082fbe  jz      short loc_180082FD3
0x180082fc0  call    cs:__imp_CloseHandle
0x180082fc6  mov     rcx, [rsp+28h]; this
0x180082fcb  test    eax, eax
0x180082fcd  jz      loc_180083074
0x180082fd3  mov     rdi, [rbx+80h]
0x180082fda  test    rdi, rdi
0x180082fdd  jz      short loc_180082FF5
0x180082fdf  mov     rcx, rdi; struct _PaymentServiceRequestChangeResult *
0x180082fe2  call    ?FreePaymentServiceRequestChangeResult@@YAXPEAU_PaymentServiceRequestChangeResult@@@Z; FreePaymentServiceRequestChangeResult(_PaymentServiceRequestChangeResult *)
0x180082fe7  nop
0x180082fe8  mov     edx, 70h ; 'p'
0x180082fed  mov     rcx, rdi; Block
0x180082ff0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180082ff5  mov     rdi, [rbx+78h]
0x180082ff9  test    rdi, rdi
0x180082ffc  jz      short loc_180083014
0x180082ffe  mov     rcx, rdi; struct _PaymentServiceRequestChangeDetails *
0x180083001  call    ?FreePaymentServiceRequestChangeDetails@@YAXPEAU_PaymentServiceRequestChangeDetails@@@Z; FreePaymentServiceRequestChangeDetails(_PaymentServiceRequestChangeDetails *)
0x180083006  nop
0x180083007  mov     edx, 58h ; 'X'
0x18008300c  mov     rcx, rdi; Block
0x18008300f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180083014  mov     rdi, [rbx+70h]
0x180083018  test    rdi, rdi
0x18008301b  jz      short loc_180083033
0x18008301d  mov     rcx, rdi; struct _PaymentServiceTransaction *
0x180083020  call    ?FreePaymentServiceTransaction@@YAXPEAU_PaymentServiceTransaction@@@Z; FreePaymentServiceTransaction(_PaymentServiceTransaction *)
0x180083025  nop
0x180083026  mov     edx, 0D0h
0x18008302b  mov     rcx, rdi; Block
0x18008302e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180083033  lea     rcx, [rbx+50h]
0x180083037  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008303c  lea     rcx, [rbx+10h]; lpCriticalSection
0x180083040  call    cs:__imp_DeleteCriticalSection
0x180083046  mov     rcx, [rbx+8]
0x18008304a  test    rcx, rcx
0x18008304d  jz      short loc_180083069
0x18008304f  or      eax, 0FFFFFFFFh
0x180083052  lock xadd [rcx+0Ch], eax
0x180083057  cmp     eax, 1
0x18008305a  jnz     short loc_180083069
0x18008305c  mov     rax, [rcx]
0x18008305f  mov     rax, [rax+8]
0x180083063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083068  nop
0x180083069  mov     rbx, [rsp+28h+arg_0]
0x18008306e  add     rsp, 20h
0x180083072  pop     rdi
0x180083073  retn
0x180083074  mov     edx, 0A0Bh; void *
0x180083079  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18008307f  mov     edx, 0A0Bh; void *
0x180083084  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
