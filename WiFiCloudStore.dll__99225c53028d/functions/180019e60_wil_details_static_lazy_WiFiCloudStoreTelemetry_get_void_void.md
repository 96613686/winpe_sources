# wil::details::static_lazy<WiFiCloudStoreTelemetry>::get(void (*)(void))

- ea: `0x180019e60`
- end: `0x180019f51`
- name: `?get@?$static_lazy@VWiFiCloudStoreTelemetry@@@details@wil@@QEAAPEAVWiFiCloudStoreTelemetry@@P6AXXZ@Z`
- size: `241`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180019e40`
- `0x18002d390`

## callees

- `0x180019e60`
- `0x180019f58`
- `0x18002a3e0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180019e93`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180019e93`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180019f3b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180019f3b`

## pseudocode

```c
__int64 *__fastcall wil::details::static_lazy<WiFiCloudStoreTelemetry>::get(__int64 a1, void (__cdecl *a2)())
{
  WINBOOL v4; // [rsp+30h] [rbp+8h] BYREF
  int v5; // [rsp+34h] [rbp+Ch]
  __int64 *v6; // [rsp+40h] [rbp+18h] BYREF

  v5 = HIDWORD(a1);
  v6 = 0;
  v4 = 0;
  if ( InitOnceBeginInitialize(&`WiFiCloudStoreTelemetry::Instance'::`2'::wrapper, 0, &v4, (LPVOID *)&v6) && v4 )
  {
    qword_180052770 = 0;
    v6 = &qword_180052768;
    qword_180052768 = (__int64)&WiFiCloudStoreTelemetry::`vftable';
    byte_180052778 = 0;
    dword_18005277C = 0;
    CallbackContext = &`WiFiCloudStoreTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(a2);
    qword_180052770 = (__int64)CallbackContext;
    byte_180052778 = 1;
    TraceLoggingRegisterEx_EventRegister_EventSetInformation(CallbackContext);
    dword_18005277C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180052768 + 8))(&qword_180052768);
    InitOnceComplete(&`WiFiCloudStoreTelemetry::Instance'::`2'::wrapper, 0, &qword_180052768);
  }
  return v6;
}

```

## disassembly

```asm
0x180019e60  mov     rax, rsp
0x180019e63  mov     [rax+10h], rbx
0x180019e67  mov     [rax+8], rcx
0x180019e6b  push    rdi
0x180019e6c  sub     rsp, 20h
0x180019e70  mov     rbx, rdx
0x180019e73  mov     qword ptr [rax+18h], 0
0x180019e7b  xor     edx, edx; dwFlags
0x180019e7d  mov     dword ptr [rax+8], 0
0x180019e84  lea     r9, [rax+18h]; lpContext
0x180019e88  lea     r8, [rax+8]; fPending
0x180019e8c  lea     rcx, ?wrapper@?1??Instance@WiFiCloudStoreTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VWiFiCloudStoreTelemetry@@@details@wil@@A; lpInitOnce
0x180019e93  call    cs:__imp_InitOnceBeginInitialize
0x180019e99  test    eax, eax
0x180019e9b  jz      loc_180019F41
0x180019ea1  cmp     [rsp+28h+arg_0], 0
0x180019ea6  jz      loc_180019F41
0x180019eac  lea     rdi, qword_180052768
0x180019eb3  mov     cs:qword_180052770, 0
0x180019ebe  lea     rax, ??_7WiFiCloudStoreTelemetry@@6B@; const WiFiCloudStoreTelemetry::`vftable'
0x180019ec5  mov     [rsp+28h+arg_10], rdi
0x180019eca  mov     cs:qword_180052768, rax
0x180019ed1  mov     cs:byte_180052778, 0
0x180019ed8  mov     cs:dword_18005277C, 0
0x180019ee2  lea     rax, ?__hInner@?1???0StaticHandle@WiFiCloudStoreTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `WiFiCloudStoreTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180019ee9  mov     rcx, rbx; void (__cdecl *)()
0x180019eec  mov     cs:CallbackContext, rax
0x180019ef3  call    atexit
0x180019ef8  mov     rcx, cs:CallbackContext; CallbackContext
0x180019eff  mov     cs:qword_180052770, rcx
0x180019f06  mov     cs:byte_180052778, 1
0x180019f0d  call    TraceLoggingRegisterEx_EventRegister_EventSetInformation
0x180019f12  mov     rax, cs:qword_180052768
0x180019f19  mov     rcx, rdi
0x180019f1c  mov     cs:dword_18005277C, 1
0x180019f26  mov     rax, [rax+8]
0x180019f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019f2f  mov     r8, rdi; lpContext
0x180019f32  lea     rcx, ?wrapper@?1??Instance@WiFiCloudStoreTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VWiFiCloudStoreTelemetry@@@details@wil@@A; lpInitOnce
0x180019f39  xor     edx, edx; dwFlags
0x180019f3b  call    cs:__imp_InitOnceComplete
0x180019f41  mov     rax, [rsp+28h+arg_10]
0x180019f46  mov     rbx, [rsp+28h+arg_8]
0x180019f4b  add     rsp, 20h
0x180019f4f  pop     rdi
0x180019f50  retn
```
