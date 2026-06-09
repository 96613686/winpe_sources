# wil::details::FeatureLogging::Instance(void)

- ea: `0x14000ceb0`
- end: `0x14000cf95`
- name: `?Instance@FeatureLogging@details@wil@@KAPEAV123@XZ`
- size: `229`
- prototype: `struct wil::details::FeatureLogging *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000c6f0`

## callees

- `0x140001858`
- `0x140002db8`
- `0x14000ceb0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000cf84`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x14000cf84`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000ced8`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x14000ced8`

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
    qword_140020748 = 0;
    v2 = &qword_140020740;
    qword_140020740 = (__int64)&wil::details::FeatureLogging::`vftable';
    byte_140020750 = 0;
    dword_140020754 = 0;
    qword_140020758 = &`wil::details::FeatureLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_::_lambda_invoker_cdecl_);
    qword_140020748 = (__int64)qword_140020758;
    byte_140020750 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(qword_140020758);
    dword_140020754 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_140020740 + 8))(&qword_140020740);
    InitOnceComplete(&`wil::details::FeatureLogging::Instance'::`2'::wrapper, 0, &qword_140020740);
  }
  return (struct wil::details::FeatureLogging *)v2;
}

```

## disassembly

```asm
0x14000ceb0  mov     rax, rsp
0x14000ceb3  push    rbx
0x14000ceb4  sub     rsp, 20h
0x14000ceb8  lea     r9, [rax+10h]; lpContext
0x14000cebc  mov     qword ptr [rax+10h], 0
0x14000cec4  lea     r8, [rax+8]; fPending
0x14000cec8  mov     dword ptr [rax+8], 0
0x14000cecf  xor     edx, edx; dwFlags
0x14000ced1  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x14000ced8  call    cs:__imp_InitOnceBeginInitialize
0x14000cede  test    eax, eax
0x14000cee0  jz      loc_14000CF8A
0x14000cee6  cmp     [rsp+28h+arg_0], 0
0x14000ceeb  jz      loc_14000CF8A
0x14000cef1  lea     rbx, qword_140020740
0x14000cef8  mov     cs:qword_140020748, 0
0x14000cf03  lea     rax, ??_7FeatureLogging@details@wil@@6B@; const wil::details::FeatureLogging::`vftable'
0x14000cf0a  mov     [rsp+28h+arg_8], rbx
0x14000cf0f  mov     cs:qword_140020740, rax
0x14000cf16  mov     cs:byte_140020750, 0
0x14000cf1d  mov     cs:dword_140020754, 0
0x14000cf27  lea     rax, ?__hInner@?1???0StaticHandle@FeatureLogging@details@wil@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `wil::details::FeatureLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x14000cf2e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_120d0c6b51dc644cb63ed5c7fc62f6c3_@@CA@XZ; void (__cdecl *)()
0x14000cf35  mov     cs:qword_140020758, rax
0x14000cf3c  call    atexit
0x14000cf41  mov     rcx, cs:qword_140020758; CallbackContext
0x14000cf48  mov     cs:qword_140020748, rcx
0x14000cf4f  mov     cs:byte_140020750, 1
0x14000cf56  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x14000cf5b  mov     rax, cs:qword_140020740
0x14000cf62  mov     rcx, rbx
0x14000cf65  mov     cs:dword_140020754, 1
0x14000cf6f  mov     rax, [rax+8]
0x14000cf73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cf78  mov     r8, rbx; lpContext
0x14000cf7b  lea     rcx, ?wrapper@?1??Instance@FeatureLogging@details@wil@@KAPEAV234@XZ@4V?$static_lazy@VFeatureLogging@details@wil@@@34@A; lpInitOnce
0x14000cf82  xor     edx, edx; dwFlags
0x14000cf84  call    cs:__imp_InitOnceComplete
0x14000cf8a  mov     rax, [rsp+28h+arg_8]
0x14000cf8f  add     rsp, 20h
0x14000cf93  pop     rbx
0x14000cf94  retn
```
