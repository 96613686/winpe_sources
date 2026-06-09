# wpc::Sync::Internal::SyncLogger::Provider(void)

- ea: `0x18001a04c`
- end: `0x18001a135`
- name: `?Provider@SyncLogger@Internal@Sync@wpc@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `57`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800199b8`
- `0x18002a0ac`
- `0x18002a12c`
- `0x18002af30`
- `0x18002b280`
- `0x18002b5f4`
- `0x18002b85c`
- `0x18002b988`
- `0x18002bad0`
- `0x18002bc2c`
- `0x18002bd54`
- `0x18002bea0`
- `0x18002c140`
- `0x18002c9dc`
- `0x1800718ec`
- `0x1800733a0`
- `0x180073484`
- `0x180075eb8`
- `0x180075fe4`
- `0x1800760d0`
- `0x180078a38`
- `0x180078d78`
- `0x18007f3fc`
- `0x180080908`
- `0x1800809ec`
- `0x180080ad0`
- `0x180080bb4`
- `0x180080c98`
- `0x180080d7c`
- `0x18008303c`
- `0x180083184`
- `0x1800832cc`
- `0x180083414`
- `0x18008355c`
- `0x1800836a4`
- `0x1800837ec`
- `0x180083934`
- `0x180083a7c`
- `0x180083bc4`
- `0x180083cc8`
- `0x180083dcc`
- `0x180083ed0`
- `0x180083fd4`
- `0x1800840d8`
- `0x1800841dc`
- `0x1800842e0`
- `0x180084560`
- `0x1800847e0`
- `0x180084a60`
- `0x180084ce0`

## callees

- `0x180001748`
- `0x1800064d8`
- `0x18001a04c`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001a120`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001a120`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001a074`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18001a074`

## pseudocode

```c
const struct _tlgProvider_t *wpc::Sync::Internal::SyncLogger::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( __std_init_once_begin_initialize(
         &`wpc::Sync::Internal::SyncLogger::Instance'::`2'::wrapper,
         0,
         &v1,
         (LPVOID *)&v2)
    && v1 )
  {
    qword_180109258 = 0;
    v2 = &qword_180109250;
    qword_180109250 = (__int64)&wpc::Sync::Internal::SyncLogger::`vftable';
    byte_180109260 = 0;
    dword_180109264 = 0;
    CallbackContext = &`wpc::Sync::Internal::SyncLogger::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_f7b6c66afa7dc9f145e615a46aaa3349_::_lambda_invoker_cdecl_);
    qword_180109258 = (__int64)CallbackContext;
    byte_180109260 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_180109264 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180109250 + 8))(&qword_180109250);
    InitOnceComplete(&`wpc::Sync::Internal::SyncLogger::Instance'::`2'::wrapper, 0, &qword_180109250);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x18001a04c  mov     rax, rsp
0x18001a04f  push    rbx
0x18001a050  sub     rsp, 20h
0x18001a054  lea     r9, [rax+10h]; lpContext
0x18001a058  mov     qword ptr [rax+10h], 0
0x18001a060  lea     r8, [rax+8]; fPending
0x18001a064  mov     dword ptr [rax+8], 0
0x18001a06b  xor     edx, edx; dwFlags
0x18001a06d  lea     rcx, ?wrapper@?1??Instance@SyncLogger@Internal@Sync@wpc@@KAPEAV2345@XZ@4V?$static_lazy@VSyncLogger@Internal@Sync@wpc@@@details@wil@@A; lpInitOnce
0x18001a074  call    cs:__imp___std_init_once_begin_initialize
0x18001a07a  test    eax, eax
0x18001a07c  jz      loc_18001A126
0x18001a082  cmp     [rsp+28h+arg_0], 0
0x18001a087  jz      loc_18001A126
0x18001a08d  lea     rbx, qword_180109250
0x18001a094  mov     cs:qword_180109258, 0
0x18001a09f  lea     rax, ??_7SyncLogger@Internal@Sync@wpc@@6B@; const wpc::Sync::Internal::SyncLogger::`vftable'
0x18001a0a6  mov     [rsp+28h+arg_8], rbx
0x18001a0ab  mov     cs:qword_180109250, rax
0x18001a0b2  mov     cs:byte_180109260, 0
0x18001a0b9  mov     cs:dword_180109264, 0
0x18001a0c3  lea     rax, ?__hInner@?1???0StaticHandle@SyncLogger@Internal@Sync@wpc@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wpc::Sync::Internal::SyncLogger::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18001a0ca  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_f7b6c66afa7dc9f145e615a46aaa3349_@@CA@XZ; void (__cdecl *)()
0x18001a0d1  mov     cs:CallbackContext, rax
0x18001a0d8  call    atexit
0x18001a0dd  mov     rcx, cs:CallbackContext; CallbackContext
0x18001a0e4  mov     cs:qword_180109258, rcx
0x18001a0eb  mov     cs:byte_180109260, 1
0x18001a0f2  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x18001a0f7  mov     rax, cs:qword_180109250
0x18001a0fe  mov     rcx, rbx
0x18001a101  mov     cs:dword_180109264, 1
0x18001a10b  mov     rax, [rax+8]
0x18001a10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a114  mov     r8, rbx; lpContext
0x18001a117  lea     rcx, ?wrapper@?1??Instance@SyncLogger@Internal@Sync@wpc@@KAPEAV2345@XZ@4V?$static_lazy@VSyncLogger@Internal@Sync@wpc@@@details@wil@@A; lpInitOnce
0x18001a11e  xor     edx, edx; dwFlags
0x18001a120  call    cs:__imp_InitOnceComplete
0x18001a126  mov     rax, [rsp+28h+arg_8]
0x18001a12b  mov     rax, [rax+8]
0x18001a12f  add     rsp, 20h
0x18001a133  pop     rbx
0x18001a134  retn
```
