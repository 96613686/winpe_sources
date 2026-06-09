# wpc::Logging::WpcBaseLogger::Provider(void)

- ea: `0x18006f7e8`
- end: `0x18006f8d1`
- name: `?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `12`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18006b0a8`
- `0x18006b128`
- `0x18006f150`
- `0x18006f4a0`
- `0x18006f8d8`
- `0x18006fb40`
- `0x18007048c`
- `0x1800705d4`
- `0x180070718`
- `0x180070840`
- `0x180070970`
- `0x180070bf0`

## callees

- `0x180001748`
- `0x1800064d8`
- `0x18006f7e8`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18006f8bc`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18006f8bc`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18006f810`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18006f810`

## pseudocode

```c
const struct _tlgProvider_t *wpc::Logging::WpcBaseLogger::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( __std_init_once_begin_initialize(&`wpc::Logging::WpcBaseLogger::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2)
    && v1 )
  {
    qword_1801093B0 = 0;
    v2 = &qword_1801093A8;
    qword_1801093A8 = (__int64)&wpc::Logging::WpcBaseLogger::`vftable';
    byte_1801093B8 = 0;
    dword_1801093BC = 0;
    qword_1801093C0 = &`wpc::Logging::WpcBaseLogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_59955177f92948a0ddb59c07058884af_::_lambda_invoker_cdecl_);
    qword_1801093B0 = (__int64)qword_1801093C0;
    byte_1801093B8 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_1801093C0);
    dword_1801093BC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1801093A8 + 8))(&qword_1801093A8);
    InitOnceComplete(&`wpc::Logging::WpcBaseLogger::Instance'::`2'::wrapper, 0, &qword_1801093A8);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x18006f7e8  mov     rax, rsp
0x18006f7eb  push    rbx
0x18006f7ec  sub     rsp, 20h
0x18006f7f0  lea     r9, [rax+10h]; lpContext
0x18006f7f4  mov     qword ptr [rax+10h], 0
0x18006f7fc  lea     r8, [rax+8]; fPending
0x18006f800  mov     dword ptr [rax+8], 0
0x18006f807  xor     edx, edx; dwFlags
0x18006f809  lea     rcx, ?wrapper@?1??Instance@WpcBaseLogger@Logging@wpc@@KAPEAV234@XZ@4V?$static_lazy@VWpcBaseLogger@Logging@wpc@@@details@wil@@A; lpInitOnce
0x18006f810  call    cs:__imp___std_init_once_begin_initialize
0x18006f816  test    eax, eax
0x18006f818  jz      loc_18006F8C2
0x18006f81e  cmp     [rsp+28h+arg_0], 0
0x18006f823  jz      loc_18006F8C2
0x18006f829  lea     rbx, qword_1801093A8
0x18006f830  mov     cs:qword_1801093B0, 0
0x18006f83b  lea     rax, ??_7WpcBaseLogger@Logging@wpc@@6B@; const wpc::Logging::WpcBaseLogger::`vftable'
0x18006f842  mov     [rsp+28h+arg_8], rbx
0x18006f847  mov     cs:qword_1801093A8, rax
0x18006f84e  mov     cs:byte_1801093B8, 0
0x18006f855  mov     cs:dword_1801093BC, 0
0x18006f85f  lea     rax, ?__hInner@?1???0StaticHandle@WpcBaseLogger@Logging@wpc@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wpc::Logging::WpcBaseLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18006f866  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_59955177f92948a0ddb59c07058884af_@@CA@XZ; void (__cdecl *)()
0x18006f86d  mov     cs:qword_1801093C0, rax
0x18006f874  call    atexit
0x18006f879  mov     rcx, cs:qword_1801093C0; CallbackContext
0x18006f880  mov     cs:qword_1801093B0, rcx
0x18006f887  mov     cs:byte_1801093B8, 1
0x18006f88e  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18006f893  mov     rax, cs:qword_1801093A8
0x18006f89a  mov     rcx, rbx
0x18006f89d  mov     cs:dword_1801093BC, 1
0x18006f8a7  mov     rax, [rax+8]
0x18006f8ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f8b0  mov     r8, rbx; lpContext
0x18006f8b3  lea     rcx, ?wrapper@?1??Instance@WpcBaseLogger@Logging@wpc@@KAPEAV234@XZ@4V?$static_lazy@VWpcBaseLogger@Logging@wpc@@@details@wil@@A; lpInitOnce
0x18006f8ba  xor     edx, edx; dwFlags
0x18006f8bc  call    cs:__imp_InitOnceComplete
0x18006f8c2  mov     rax, [rsp+28h+arg_8]
0x18006f8c7  mov     rax, [rax+8]
0x18006f8cb  add     rsp, 20h
0x18006f8cf  pop     rbx
0x18006f8d0  retn
```
