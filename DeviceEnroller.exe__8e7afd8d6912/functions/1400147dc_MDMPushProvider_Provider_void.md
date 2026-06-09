# MDMPushProvider::Provider(void)

- ea: `0x1400147dc`
- end: `0x1400148c5`
- name: `?Provider@MDMPushProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `233`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `31`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000af34`
- `0x14000afcc`
- `0x14000b064`
- `0x14000b0fc`
- `0x14000c008`
- `0x140013b30`
- `0x14001822c`
- `0x140018314`
- `0x140018470`
- `0x1400185d0`
- `0x140018870`
- `0x14001d478`
- `0x14001ebec`
- `0x140026780`
- `0x140026ad0`
- `0x14002801c`
- `0x14002896c`
- `0x140028ab0`
- `0x140028bf4`
- `0x140028d38`
- `0x140028e7c`
- `0x140028fc0`
- `0x140029124`
- `0x140029248`
- `0x140029378`
- `0x140029720`
- `0x1400299b0`
- `0x140029c40`
- `0x140029ed0`
- `0x14002a160`
- `0x14002a3f0`

## callees

- `0x140001f30`
- `0x140004588`
- `0x1400147dc`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140014804`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x140014804`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400148b0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1400148b0`

## pseudocode

```c
const struct _tlgProvider_t *MDMPushProvider::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`MDMPushProvider::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_14007E530 = 0;
    v2 = &qword_14007E528;
    qword_14007E528 = (__int64)&CDNDownloaderProvider::`vftable';
    byte_14007E538 = 0;
    dword_14007E53C = 0;
    CallbackContext = &`MDMPushProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_8e2e3e542c2dc97e9f262390b1f584c8_::_lambda_invoker_cdecl_);
    qword_14007E530 = (__int64)CallbackContext;
    byte_14007E538 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_14007E53C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_14007E528 + 8))(&qword_14007E528);
    InitOnceComplete(&`MDMPushProvider::Instance'::`2'::wrapper, 0, &qword_14007E528);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x1400147dc  mov     rax, rsp
0x1400147df  push    rbx
0x1400147e0  sub     rsp, 20h
0x1400147e4  lea     r9, [rax+10h]; lpContext
0x1400147e8  mov     qword ptr [rax+10h], 0
0x1400147f0  lea     r8, [rax+8]; fPending
0x1400147f4  mov     dword ptr [rax+8], 0
0x1400147fb  xor     edx, edx; dwFlags
0x1400147fd  lea     rcx, ?wrapper@?1??Instance@MDMPushProvider@@KAPEAV2@XZ@4V?$static_lazy@VMDMPushProvider@@@details@wil@@A; lpInitOnce
0x140014804  call    cs:__imp_InitOnceBeginInitialize
0x14001480a  test    eax, eax
0x14001480c  jz      loc_1400148B6
0x140014812  cmp     [rsp+28h+arg_0], 0
0x140014817  jz      loc_1400148B6
0x14001481d  lea     rbx, qword_14007E528
0x140014824  mov     cs:qword_14007E530, 0
0x14001482f  lea     rax, ??_7CDNDownloaderProvider@@6B@; const CDNDownloaderProvider::`vftable'
0x140014836  mov     [rsp+28h+arg_8], rbx
0x14001483b  mov     cs:qword_14007E528, rax
0x140014842  mov     cs:byte_14007E538, 0
0x140014849  mov     cs:dword_14007E53C, 0
0x140014853  lea     rax, ?__hInner@?1???0StaticHandle@MDMPushProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `MDMPushProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14001485a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_8e2e3e542c2dc97e9f262390b1f584c8_@@CA@XZ; void (__cdecl *)()
0x140014861  mov     cs:CallbackContext, rax
0x140014868  call    atexit
0x14001486d  mov     rcx, cs:CallbackContext; CallbackContext
0x140014874  mov     cs:qword_14007E530, rcx
0x14001487b  mov     cs:byte_14007E538, 1
0x140014882  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x140014887  mov     rax, cs:qword_14007E528
0x14001488e  mov     rcx, rbx
0x140014891  mov     cs:dword_14007E53C, 1
0x14001489b  mov     rax, [rax+8]
0x14001489f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400148a4  mov     r8, rbx; lpContext
0x1400148a7  lea     rcx, ?wrapper@?1??Instance@MDMPushProvider@@KAPEAV2@XZ@4V?$static_lazy@VMDMPushProvider@@@details@wil@@A; lpInitOnce
0x1400148ae  xor     edx, edx; dwFlags
0x1400148b0  call    cs:__imp_InitOnceComplete
0x1400148b6  mov     rax, [rsp+28h+arg_8]
0x1400148bb  mov     rax, [rax+8]
0x1400148bf  add     rsp, 20h
0x1400148c3  pop     rbx
0x1400148c4  retn
```
