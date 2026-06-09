# Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry::Instance(void)

- ea: `0x1800e8a1c`
- end: `0x1800e8ad1`
- name: `?Instance@CapabilityAccessManagerDesktopTelemetry@Telemetry@Storage@Desktop@CapabilityAccess@Internal@Windows@@KAPEAV1234567@XZ`
- size: `181`
- prototype: `struct Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry *(void)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800e7960`
- `0x1800e8df0`
- `0x1800ed840`
- `0x1800f274c`
- `0x1800f6584`
- `0x1800f694c`

## callees

- `0x180003410`
- `0x1800e8a1c`
- `0x1800ea3e8`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800e8a44`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800e8a44`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800e8ac0`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800e8ac0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
struct Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry *Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry::Instance(
        void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(
         &`Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry::Instance'::`2'::wrapper,
         0,
         &v2,
         &v3)
    && v2 )
  {
    qword_180140108 = 0;
    v3 = &qword_180140100;
    qword_180140100 = &Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry::`vftable';
    byte_180140110 = 0;
    dword_180140114 = 0;
    qword_180140118 = (struct _tlgProvider_t *)&`Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_37c0d1939438d742488c5f7801ee7ab7_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180140100, qword_180140118, v0);
    InitOnceComplete(
      &`Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry::Instance'::`2'::wrapper,
      0,
      &qword_180140100);
  }
  return (struct Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry *)v3;
}

```

## disassembly

```asm
0x1800e8a1c  mov     rax, rsp
0x1800e8a1f  push    rbx
0x1800e8a20  sub     rsp, 20h
0x1800e8a24  lea     r9, [rax+10h]; lpContext
0x1800e8a28  mov     qword ptr [rax+10h], 0
0x1800e8a30  lea     r8, [rax+8]; fPending
0x1800e8a34  mov     dword ptr [rax+8], 0
0x1800e8a3b  xor     edx, edx; dwFlags
0x1800e8a3d  lea     rcx, ?wrapper@?1??Instance@CapabilityAccessManagerDesktopTelemetry@Telemetry@Storage@Desktop@CapabilityAccess@Internal@Windows@@KAPEAV2345678@XZ@4V?$static_lazy@VCapabilityAccessManagerDesktopTelemetry@Telemetry@Storage@Desktop@CapabilityAccess@Internal@Windows@@@details@wil@@A; lpInitOnce
0x1800e8a44  call    cs:__imp_InitOnceBeginInitialize
0x1800e8a4a  test    eax, eax
0x1800e8a4c  jz      short loc_1800E8AC6
0x1800e8a4e  cmp     [rsp+28h+arg_0], 0
0x1800e8a53  jz      short loc_1800E8AC6
0x1800e8a55  lea     rbx, qword_180140100
0x1800e8a5c  mov     cs:qword_180140108, 0
0x1800e8a67  lea     rax, ??_7CapabilityAccessManagerDesktopTelemetry@Telemetry@Storage@Desktop@CapabilityAccess@Internal@Windows@@6B@; const Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry::`vftable'
0x1800e8a6e  mov     [rsp+28h+arg_8], rbx
0x1800e8a73  mov     cs:qword_180140100, rax
0x1800e8a7a  mov     cs:byte_180140110, 0
0x1800e8a81  mov     cs:dword_180140114, 0
0x1800e8a8b  lea     rax, ?__hInner@?1???0StaticHandle@CapabilityAccessManagerDesktopTelemetry@Telemetry@Storage@Desktop@CapabilityAccess@Internal@Windows@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `Windows::Internal::CapabilityAccess::Desktop::Storage::Telemetry::CapabilityAccessManagerDesktopTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800e8a92  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_37c0d1939438d742488c5f7801ee7ab7_@@CA@XZ; void (__cdecl *)()
0x1800e8a99  mov     cs:qword_180140118, rax
0x1800e8aa0  call    atexit
0x1800e8aa5  mov     rdx, cs:qword_180140118; struct _tlgProvider_t *
0x1800e8aac  mov     rcx, rbx; this
0x1800e8aaf  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800e8ab4  mov     r8, rbx; lpContext
0x1800e8ab7  lea     rcx, ?wrapper@?1??Instance@CapabilityAccessManagerDesktopTelemetry@Telemetry@Storage@Desktop@CapabilityAccess@Internal@Windows@@KAPEAV2345678@XZ@4V?$static_lazy@VCapabilityAccessManagerDesktopTelemetry@Telemetry@Storage@Desktop@CapabilityAccess@Internal@Windows@@@details@wil@@A; lpInitOnce
0x1800e8abe  xor     edx, edx; dwFlags
0x1800e8ac0  call    cs:__imp_InitOnceComplete
0x1800e8ac6  mov     rax, [rsp+28h+arg_8]
0x1800e8acb  add     rsp, 20h
0x1800e8acf  pop     rbx
0x1800e8ad0  retn
```
