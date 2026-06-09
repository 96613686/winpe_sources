# Microsoft::Windows::Autopilot::AutopilotDllTelemetryUtils::Instance(void)

- ea: `0x18000ddcc`
- end: `0x18000dea9`
- name: `?Instance@AutopilotDllTelemetryUtils@Autopilot@Windows@Microsoft@@KAPEAV1234@XZ`
- size: `221`
- prototype: `struct Microsoft::Windows::Autopilot::AutopilotDllTelemetryUtils *(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000cb00`

## callees

- `0x1800049e8`
- `0x18000ddcc`
- `0x18000e928`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ddf4`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x18000ddf4`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000de91`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18000de91`

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
    qword_180044C40 = 0;
    qword_180044C38 = (__int64)&ZeroTouchProvCxhTelemetry::`vftable';
    v2 = &qword_180044C38;
    byte_180044C48 = 0;
    dword_180044C4C = 0;
    atexit(_lambda_a5fa82a532c4efc3e16b1e0f7f0dd834_::_lambda_invoker_cdecl_);
    qword_180044C40 = (__int64)Microsoft::Windows::Autopilot::AutopilotDllTelemProvider::Provider();
    byte_180044C48 = 0;
    dword_180044C4C = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180044C38 + 8))(&qword_180044C38);
    InitOnceComplete(
      &`Microsoft::Windows::Autopilot::AutopilotDllTelemetryUtils::Instance'::`2'::wrapper,
      0,
      &qword_180044C38);
  }
  return (struct Microsoft::Windows::Autopilot::AutopilotDllTelemetryUtils *)v2;
}

```

## disassembly

```asm
0x18000ddcc  mov     rax, rsp
0x18000ddcf  push    rbx
0x18000ddd0  sub     rsp, 20h
0x18000ddd4  lea     r9, [rax+10h]; lpContext
0x18000ddd8  mov     qword ptr [rax+10h], 0
0x18000dde0  lea     r8, [rax+8]; fPending
0x18000dde4  mov     dword ptr [rax+8], 0
0x18000ddeb  xor     edx, edx; dwFlags
0x18000dded  lea     rcx, ?wrapper@?1??Instance@AutopilotDllTelemetryUtils@Autopilot@Windows@Microsoft@@KAPEAV2345@XZ@4V?$static_lazy@VAutopilotDllTelemetryUtils@Autopilot@Windows@Microsoft@@@details@wil@@A; lpInitOnce
0x18000ddf4  call    cs:__imp___std_init_once_begin_initialize
0x18000ddfb  nop     dword ptr [rax+rax+00h]
0x18000de00  test    eax, eax
0x18000de02  jz      loc_18000DE9D
0x18000de08  cmp     [rsp+28h+arg_0], 0
0x18000de0d  jz      loc_18000DE9D
0x18000de13  lea     rax, ??_7ZeroTouchProvCxhTelemetry@@6B@; const ZeroTouchProvCxhTelemetry::`vftable'
0x18000de1a  mov     cs:qword_180044C40, 0
0x18000de25  lea     rbx, qword_180044C38
0x18000de2c  mov     cs:qword_180044C38, rax
0x18000de33  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_a5fa82a532c4efc3e16b1e0f7f0dd834_@@CA@XZ; void (__cdecl *)()
0x18000de3a  mov     [rsp+28h+arg_8], rbx
0x18000de3f  mov     cs:byte_180044C48, 0
0x18000de46  mov     cs:dword_180044C4C, 0
0x18000de50  call    atexit
0x18000de55  call    ?Provider@AutopilotDllTelemProvider@Autopilot@Windows@Microsoft@@SAPEBU_tlgProvider_t@@XZ; Microsoft::Windows::Autopilot::AutopilotDllTelemProvider::Provider(void)
0x18000de5a  mov     cs:qword_180044C40, rax
0x18000de61  mov     rcx, rbx
0x18000de64  mov     rax, cs:qword_180044C38
0x18000de6b  mov     cs:byte_180044C48, 0
0x18000de72  mov     cs:dword_180044C4C, 1
0x18000de7c  mov     rax, [rax+8]
0x18000de80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de85  mov     r8, rbx; lpContext
0x18000de88  lea     rcx, ?wrapper@?1??Instance@AutopilotDllTelemetryUtils@Autopilot@Windows@Microsoft@@KAPEAV2345@XZ@4V?$static_lazy@VAutopilotDllTelemetryUtils@Autopilot@Windows@Microsoft@@@details@wil@@A; lpInitOnce
0x18000de8f  xor     edx, edx; dwFlags
0x18000de91  call    cs:__imp_InitOnceComplete
0x18000de98  nop     dword ptr [rax+rax+00h]
0x18000de9d  mov     rax, [rsp+28h+arg_8]
0x18000dea2  add     rsp, 20h
0x18000dea6  pop     rbx
0x18000dea7  retn
```
