# StorageReserveTelemetry::Internal::SRProvider::Instance(void)

- ea: `0x180028644`
- end: `0x180028732`
- name: `?Instance@SRProvider@Internal@StorageReserveTelemetry@@KAPEAV123@XZ`
- size: `238`
- prototype: `struct StorageReserveTelemetry::Internal::SRProvider *(void)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800255a4`
- `0x180025630`
- `0x1800262e0`
- `0x180027414`
- `0x1800287e4`
- `0x18002a1fc`

## callees

- `0x180003870`
- `0x180003c64`
- `0x180028644`
- `0x18002939c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180028714`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180028714`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002867d`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18002867d`

## pseudocode

```c
struct StorageReserveTelemetry::Internal::SRProvider *StorageReserveTelemetry::Internal::SRProvider::Instance(void)
{
  LPVOID Context; // [rsp+20h] [rbp-28h] BYREF
  WINBOOL fPending; // [rsp+28h] [rbp-20h] BYREF

  Context = 0;
  fPending = 0;
  if ( InitOnceBeginInitialize(
         &`StorageReserveTelemetry::Internal::SRProvider::Instance'::`2'::wrapper,
         0,
         &fPending,
         &Context)
    && fPending )
  {
    qword_18004ECE0 = 0;
    qword_18004ECD8 = (__int64)&StorageReserveTelemetry::Internal::SRProvider::`vftable';
    Context = &qword_18004ECD8;
    byte_18004ECE8 = 0;
    dword_18004ECEC = 0;
    atexit(_lambda_b01128ea9ababb6150e25f025fb26e9a_::_lambda_invoker_cdecl_);
    qword_18004ECE0 = (__int64)StorageReserveTelemetry::Internal::StorageReserveProvider::Provider();
    byte_18004ECE8 = 0;
    dword_18004ECEC = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18004ECD8 + 8))(&qword_18004ECD8);
    InitOnceComplete(&`StorageReserveTelemetry::Internal::SRProvider::Instance'::`2'::wrapper, 0, &qword_18004ECD8);
  }
  return (struct StorageReserveTelemetry::Internal::SRProvider *)Context;
}

```

## disassembly

```asm
0x180028644  push    rbx
0x180028646  sub     rsp, 40h
0x18002864a  mov     rax, cs:__security_cookie
0x180028651  xor     rax, rsp
0x180028654  mov     [rsp+48h+var_18], rax
0x180028659  lea     r9, [rsp+48h+Context]; lpContext
0x18002865e  mov     [rsp+48h+Context], 0
0x180028667  lea     r8, [rsp+48h+fPending]; fPending
0x18002866c  mov     [rsp+48h+fPending], 0
0x180028674  xor     edx, edx; dwFlags
0x180028676  lea     rcx, ?wrapper@?1??Instance@SRProvider@Internal@StorageReserveTelemetry@@KAPEAV234@XZ@4V?$static_lazy@VSRProvider@Internal@StorageReserveTelemetry@@@details@wil@@A; lpInitOnce
0x18002867d  call    cs:__imp_InitOnceBeginInitialize
0x180028683  test    eax, eax
0x180028685  jz      loc_18002871A
0x18002868b  cmp     [rsp+48h+fPending], 0
0x180028690  jz      loc_18002871A
0x180028696  lea     rax, ??_7SRProvider@Internal@StorageReserveTelemetry@@6B@; const StorageReserveTelemetry::Internal::SRProvider::`vftable'
0x18002869d  mov     cs:qword_18004ECE0, 0
0x1800286a8  lea     rbx, qword_18004ECD8
0x1800286af  mov     cs:qword_18004ECD8, rax
0x1800286b6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_b01128ea9ababb6150e25f025fb26e9a_@@CA@XZ; void (__cdecl *)()
0x1800286bd  mov     [rsp+48h+Context], rbx
0x1800286c2  mov     cs:byte_18004ECE8, 0
0x1800286c9  mov     cs:dword_18004ECEC, 0
0x1800286d3  call    atexit
0x1800286d8  call    ?Provider@StorageReserveProvider@Internal@StorageReserveTelemetry@@SAPEBU_tlgProvider_t@@XZ; StorageReserveTelemetry::Internal::StorageReserveProvider::Provider(void)
0x1800286dd  mov     cs:qword_18004ECE0, rax
0x1800286e4  mov     rcx, rbx
0x1800286e7  mov     rax, cs:qword_18004ECD8
0x1800286ee  mov     cs:byte_18004ECE8, 0
0x1800286f5  mov     cs:dword_18004ECEC, 1
0x1800286ff  mov     rax, [rax+8]
0x180028703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028708  mov     r8, rbx; lpContext
0x18002870b  lea     rcx, ?wrapper@?1??Instance@SRProvider@Internal@StorageReserveTelemetry@@KAPEAV234@XZ@4V?$static_lazy@VSRProvider@Internal@StorageReserveTelemetry@@@details@wil@@A; lpInitOnce
0x180028712  xor     edx, edx; dwFlags
0x180028714  call    cs:__imp_InitOnceComplete
0x18002871a  mov     rax, [rsp+48h+Context]
0x18002871f  mov     rcx, [rsp+48h+var_18]
0x180028724  xor     rcx, rsp; StackCookie
0x180028727  call    __security_check_cookie
0x18002872c  add     rsp, 40h
0x180028730  pop     rbx
0x180028731  retn
```
