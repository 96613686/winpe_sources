# wil::details::FeatureLogging::Instance(void)

- ea: `0x18001513c`
- end: `0x180015221`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `229`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012f30`

## callees

- `0x1800015b4`
- `0x180005564`
- `0x18001513c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180015164`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180015164`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180015210`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180015210`

## pseudocode

```c
struct wil::details::FeatureLogging *wil::details::FeatureLogging::Instance(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_1800A5358 = 0;
    v2 = &qword_1800A5350;
    qword_1800A5350 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_1800A5360 = 0;
    dword_1800A5364 = 0;
    qword_1800A5368 = &`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    qword_1800A5358 = (__int64)qword_1800A5368;
    byte_1800A5360 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_1800A5368);
    dword_1800A5364 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_1800A5350 + 8))(&qword_1800A5350);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_1800A5350);
  }
  return (struct wil::details::FeatureLogging *)v2;
}

```

## disassembly

```asm
0x18001513c  mov     rax, rsp
0x18001513f  push    rbx
0x180015140  sub     rsp, 20h
0x180015144  lea     r9, [rax+10h]; lpContext
0x180015148  mov     qword ptr [rax+10h], 0
0x180015150  lea     r8, [rax+8]; fPending
0x180015154  mov     dword ptr [rax+8], 0
0x18001515b  xor     edx, edx; dwFlags
0x18001515d  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x180015164  call    cs:__imp_InitOnceBeginInitialize
0x18001516a  test    eax, eax
0x18001516c  jz      loc_180015216
0x180015172  cmp     [rsp+28h+arg_0], 0
0x180015177  jz      loc_180015216
0x18001517d  lea     rbx, qword_1800A5350
0x180015184  mov     cs:qword_1800A5358, 0
0x18001518f  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x180015196  mov     [rsp+28h+arg_8], rbx
0x18001519b  mov     cs:qword_1800A5350, rax
0x1800151a2  mov     cs:byte_1800A5360, 0
0x1800151a9  mov     cs:dword_1800A5364, 0
0x1800151b3  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800151ba  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x1800151c1  mov     cs:qword_1800A5368, rax
0x1800151c8  call    atexit
0x1800151cd  mov     rcx, cs:qword_1800A5368; CallbackContext
0x1800151d4  mov     cs:qword_1800A5358, rcx
0x1800151db  mov     cs:byte_1800A5360, 1
0x1800151e2  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x1800151e7  mov     rax, cs:qword_1800A5350
0x1800151ee  mov     rcx, rbx
0x1800151f1  mov     cs:dword_1800A5364, 1
0x1800151fb  mov     rax, [rax+8]
0x1800151ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015204  mov     r8, rbx; lpContext
0x180015207  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x18001520e  xor     edx, edx; dwFlags
0x180015210  call    cs:__imp_InitOnceComplete
0x180015216  mov     rax, [rsp+28h+arg_8]
0x18001521b  add     rsp, 20h
0x18001521f  pop     rbx
0x180015220  retn
```
