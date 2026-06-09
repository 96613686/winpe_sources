# Microsoft::Windows::Autopilot::AutopilotDllTelemetryUtils::Instance(void)

- ea: `0x18000dd5c`
- end: `0x18000de2c`
- name: `?Instance@AutopilotDllTelemetryUtils@Autopilot@Windows@Microsoft@@KAPEAV1234@XZ`
- size: `208`
- prototype: `struct Microsoft::Windows::Autopilot::AutopilotDllTelemetryUtils *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ca60`

## callees

- `0x1800049c8`
- `0x18000dd5c`
- `0x18000e7fc`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000dd84`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000dd84`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000de1b`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000de1b`

## pseudocode

```c
struct Microsoft::Windows::Autopilot::AutopilotDllTelemetryUtils *Microsoft::Windows::Autopilot::AutopilotDllTelemetryUtils::Instance(
        void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( __std_init_once_begin_initialize(
         &`Microsoft::Windows::Autopilot::AutopilotDllTelemetryUtils::Instance'::`2'::wrapper,
         0,
         &v1,
         (LPVOID *)&v2)
    && v1 )
  {
    qword_180043C40 = 0;
    qword_180043C38 = (__int64)&ZeroTouchProvCxhTelemetry::`vftable';
    v2 = &qword_180043C38;
    byte_180043C48 = 0;
    dword_180043C4C = 0;
    atexit(_lambda_a5fa82a532c4efc3e16b1e0f7f0dd834_::_lambda_invoker_cdecl_);
    qword_180043C40 = (__int64)Microsoft::Windows::Autopilot::AutopilotDllTelemProvider::Provider();
    byte_180043C48 = 0;
    dword_180043C4C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180043C38 + 8))(&qword_180043C38);
    InitOnceComplete(
      &`Microsoft::Windows::Autopilot::AutopilotDllTelemetryUtils::Instance'::`2'::wrapper,
      0,
      &qword_180043C38);
  }
  return (struct Microsoft::Windows::Autopilot::AutopilotDllTelemetryUtils *)v2;
}

```

## disassembly

```asm
0x18000dd5c  mov     rax, rsp
0x18000dd5f  push    rbx
0x18000dd60  sub     rsp, 20h
0x18000dd64  lea     r9, [rax+10h]; lpContext
0x18000dd68  mov     qword ptr [rax+10h], 0
0x18000dd70  lea     r8, [rax+8]; fPending
0x18000dd74  mov     dword ptr [rax+8], 0
0x18000dd7b  xor     edx, edx; dwFlags
0x18000dd7d  lea     rcx, ?wrapper@?1??Instance@AutopilotDllTelemetryUtils@Autopilot@Windows@Microsoft@@KAPEAV2345@XZ@4V?$static_lazy@VAutopilotDllTelemetryUtils@Autopilot@Windows@Microsoft@@@details@wil@@A; lpInitOnce
0x18000dd84  call    cs:__imp___std_init_once_begin_initialize
0x18000dd8a  test    eax, eax
0x18000dd8c  jz      loc_18000DE21
0x18000dd92  cmp     [rsp+28h+arg_0], 0
0x18000dd97  jz      loc_18000DE21
0x18000dd9d  lea     rax, ??_7ZeroTouchProvCxhTelemetry@@6B@; const ZeroTouchProvCxhTelemetry::`vftable'
0x18000dda4  mov     cs:qword_180043C40, 0
0x18000ddaf  lea     rbx, qword_180043C38
0x18000ddb6  mov     cs:qword_180043C38, rax
0x18000ddbd  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_a5fa82a532c4efc3e16b1e0f7f0dd834_@@CA@XZ; void (__cdecl *)()
0x18000ddc4  mov     [rsp+28h+arg_8], rbx
0x18000ddc9  mov     cs:byte_180043C48, 0
0x18000ddd0  mov     cs:dword_180043C4C, 0
0x18000ddda  call    atexit
0x18000dddf  call    ?Provider@AutopilotDllTelemProvider@Autopilot@Windows@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::Windows::Autopilot::AutopilotDllTelemProvider::Provider(void)
0x18000dde4  mov     cs:qword_180043C40, rax
0x18000ddeb  mov     rcx, rbx
0x18000ddee  mov     rax, cs:qword_180043C38
0x18000ddf5  mov     cs:byte_180043C48, 0
0x18000ddfc  mov     cs:dword_180043C4C, 1
0x18000de06  mov     rax, [rax+8]
0x18000de0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de0f  mov     r8, rbx; lpContext
0x18000de12  lea     rcx, ?wrapper@?1??Instance@AutopilotDllTelemetryUtils@Autopilot@Windows@Microsoft@@KAPEAV2345@XZ@4V?$static_lazy@VAutopilotDllTelemetryUtils@Autopilot@Windows@Microsoft@@@details@wil@@A; lpInitOnce
0x18000de19  xor     edx, edx; dwFlags
0x18000de1b  call    cs:__imp_InitOnceComplete
0x18000de21  mov     rax, [rsp+28h+arg_8]
0x18000de26  add     rsp, 20h
0x18000de2a  pop     rbx
0x18000de2b  retn
```
