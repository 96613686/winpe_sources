# StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)

- ea: `0x18002939c`
- end: `0x1800294a3`
- name: `?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ`
- size: `263`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `36`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800255a4`
- `0x180025630`
- `0x180025d50`
- `0x180025dd0`
- `0x180026fd4`
- `0x1800273a8`
- `0x1800280b0`
- `0x180028644`
- `0x180028998`
- `0x180028ba0`
- `0x180028f00`
- `0x1800292fc`
- `0x1800294ac`
- `0x180029570`
- `0x1800295dc`
- `0x1800296f4`
- `0x180029aa8`
- `0x180029b1c`
- `0x180029b74`
- `0x18002a2e4`
- `0x18002a440`
- `0x18002a648`
- `0x18002a7a4`
- `0x18002a924`
- `0x18002aa80`
- `0x18002ac04`
- `0x18002afa8`
- `0x18002b4e4`
- `0x18002b8c4`
- `0x18002bc70`
- `0x18002bf10`
- `0x18002c1b0`
- `0x18002c450`
- `0x18002c730`
- `0x18002c9c4`
- `0x18002cfdc`

## callees

- `0x180001008`
- `0x180003870`
- `0x180003c64`
- `0x18002939c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180029481`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180029481`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800293d5`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800293d5`

## pseudocode

```c
const struct _tlgProvider_t *StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
{
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(
         &`StorageReserveTelemetry::Internal::StorageReserveProvider::Instance'::`2'::wrapper,
         0,
         &fPending,
         &Context)
    && fPending )
  {
    qword_18004ECB8 = 0;
    Context = &qword_18004ECB0;
    qword_18004ECB0 = (__int64)&StorageReserveTelemetry::Internal::SRProvider::`vftable';
    byte_18004ECC0 = 0;
    dword_18004ECC4 = 0;
    CallbackContext = &`StorageReserveTelemetry::Internal::StorageReserveProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_065ea1977240cc57f14256508f2150ba_::_lambda_invoker_cdecl_);
    qword_18004ECB8 = (__int64)CallbackContext;
    byte_18004ECC0 = 1;
    TraceLoggingRegisterEx_EventRegister_2U(CallbackContext);
    dword_18004ECC4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18004ECB0 + 8))(&qword_18004ECB0);
    InitOnceComplete(
      &`StorageReserveTelemetry::Internal::StorageReserveProvider::Instance'::`2'::wrapper,
      0,
      &qword_18004ECB0);
  }
  return (const struct _tlgProvider_t *)*((_QWORD *)Context + 1);
}

```

## disassembly

```asm
0x18002939c  push    rbx
0x18002939e  sub     rsp, 40h
0x1800293a2  mov     rax, cs:__security_cookie
0x1800293a9  xor     rax, rsp
0x1800293ac  mov     [rsp+48h+var_18], rax
0x1800293b1  lea     r9, [rsp+48h+Context]; lpContext
0x1800293b6  mov     [rsp+48h+Context], 0
0x1800293bf  lea     r8, [rsp+48h+fPending]; fPending
0x1800293c4  mov     [rsp+48h+fPending], 0
0x1800293cc  xor     edx, edx; dwFlags
0x1800293ce  lea     rcx, ?wrapper@?1??Instance@StorageReserveProvider@Internal@StorageReserveTelemetry@@KAPEAV234@XZ@4V?$static_lazy@VStorageReserveProvider@Internal@StorageReserveTelemetry@@@details@wil@@A; lpInitOnce
0x1800293d5  call    cs:__imp_InitOnceBeginInitialize
0x1800293db  test    eax, eax
0x1800293dd  jz      loc_180029487
0x1800293e3  cmp     [rsp+48h+fPending], 0
0x1800293e8  jz      loc_180029487
0x1800293ee  lea     rbx, qword_18004ECB0
0x1800293f5  mov     cs:qword_18004ECB8, 0
0x180029400  lea     rax, ??_7SRProvider@Internal@StorageReserveTelemetry@@6B@; const StorageReserveTelemetry::Internal::SRProvider::`vftable'
0x180029407  mov     [rsp+48h+Context], rbx
0x18002940c  mov     cs:qword_18004ECB0, rax
0x180029413  mov     cs:byte_18004ECC0, 0
0x18002941a  mov     cs:dword_18004ECC4, 0
0x180029424  lea     rax, ?__hInner@?1???0StaticHandle@StorageReserveProvider@Internal@StorageReserveTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `StorageReserveTelemetry::Internal::StorageReserveProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18002942b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_065ea1977240cc57f14256508f2150ba_@@CA@XZ; void (__cdecl *)()
0x180029432  mov     cs:CallbackContext, rax
0x180029439  call    atexit
0x18002943e  mov     rcx, cs:CallbackContext; CallbackContext
0x180029445  mov     cs:qword_18004ECB8, rcx
0x18002944c  mov     cs:byte_18004ECC0, 1
0x180029453  call    TraceLoggingRegisterEx_EventRegister_2U
0x180029458  mov     rax, cs:qword_18004ECB0
0x18002945f  mov     rcx, rbx
0x180029462  mov     cs:dword_18004ECC4, 1
0x18002946c  mov     rax, [rax+8]
0x180029470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029475  mov     r8, rbx; lpContext
0x180029478  lea     rcx, ?wrapper@?1??Instance@StorageReserveProvider@Internal@StorageReserveTelemetry@@KAPEAV234@XZ@4V?$static_lazy@VStorageReserveProvider@Internal@StorageReserveTelemetry@@@details@wil@@A; lpInitOnce
0x18002947f  xor     edx, edx; dwFlags
0x180029481  call    cs:__imp_InitOnceComplete
0x180029487  mov     rax, [rsp+48h+Context]
0x18002948c  mov     rax, [rax+8]
0x180029490  mov     rcx, [rsp+48h+var_18]
0x180029495  xor     rcx, rsp; StackCookie
0x180029498  call    __security_check_cookie
0x18002949d  add     rsp, 40h
0x1800294a1  pop     rbx
0x1800294a2  retn
```
