# FirewallUxTelemetry::FallbackTelemetryCallback(bool,wil::FailureInfo const &)

- ea: `0x180006d30`
- end: `0x180006e2a`
- name: `?FallbackTelemetryCallback@FirewallUxTelemetry@@SAX_NAEBUFailureInfo@wil@@@Z`
- size: `250`
- prototype: `void __fastcall(char, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800025d8`
- `0x180006d30`
- `0x180008820`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006dfd`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180006dfd`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006d66`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180006d66`

## pseudocode

```c
void __fastcall FirewallUxTelemetry::FallbackTelemetryCallback(char a1, const struct wil::FailureInfo *a2)
{
  __int64 v4; // rdx
  WINBOOL v5; // [rsp+40h] [rbp+18h] BYREF
  __int64 *v6; // [rsp+48h] [rbp+20h] BYREF

  v6 = 0;
  v5 = 0;
  if ( __std_init_once_begin_initialize(&`FirewallUxTelemetry::Instance'::`2'::wrapper, 0, &v5, (LPVOID *)&v6) && v5 )
  {
    qword_18003BEC8 = 0;
    qword_18003BEC0 = (__int64)&FirewallUxTelemetry::`vftable';
    v6 = &qword_18003BEC0;
    byte_18003BED0 = 0;
    dword_18003BED4 = 0;
    atexit(`FirewallUxTelemetry::Instance'::`2'::_lambda_1_::_lambda_invoker_cdecl_);
    qword_18003BEC8 = (__int64)FirewallUxTraceLoggingProvider::Provider();
    byte_18003BED0 = 0;
    dword_18003BED4 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_18003BEC0 + 8))(&qword_18003BEC0);
    InitOnceComplete(&`FirewallUxTelemetry::Instance'::`2'::wrapper, 0, &qword_18003BEC0);
  }
  LOBYTE(v4) = a1;
  (*(void (__fastcall **)(__int64 *, __int64, const struct wil::FailureInfo *))(*v6 + 16))(v6, v4, a2);
}

```

## disassembly

```asm
0x180006d30  mov     rax, rsp
0x180006d33  mov     [rax+8], rbx
0x180006d37  mov     [rax+10h], rsi
0x180006d3b  push    rdi
0x180006d3c  sub     rsp, 20h
0x180006d40  mov     rbx, rdx
0x180006d43  mov     qword ptr [rax+20h], 0
0x180006d4b  mov     dil, cl
0x180006d4e  mov     dword ptr [rax+18h], 0
0x180006d55  xor     edx, edx; dwFlags
0x180006d57  lea     rcx, ?wrapper@?1??Instance@FirewallUxTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VFirewallUxTelemetry@@@details@wil@@A; lpInitOnce
0x180006d5e  lea     r9, [rax+20h]; lpContext
0x180006d62  lea     r8, [rax+18h]; fPending
0x180006d66  call    cs:__imp___std_init_once_begin_initialize
0x180006d6c  test    eax, eax
0x180006d6e  jz      loc_180006E03
0x180006d74  cmp     [rsp+28h+arg_10], 0
0x180006d79  jz      loc_180006E03
0x180006d7f  lea     rax, ??_7FirewallUxTelemetry@@6B@; const FirewallUxTelemetry::`vftable'
0x180006d86  mov     cs:qword_18003BEC8, 0
0x180006d91  lea     rsi, qword_18003BEC0
0x180006d98  mov     cs:qword_18003BEC0, rax
0x180006d9f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Instance@FirewallUxTelemetry@@KAPEAV3@XZ@SA@XZ; void (__cdecl *)()
0x180006da6  mov     [rsp+28h+arg_18], rsi
0x180006dab  mov     cs:byte_18003BED0, 0
0x180006db2  mov     cs:dword_18003BED4, 0
0x180006dbc  call    atexit
0x180006dc1  call    ?Provider@FirewallUxTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; FirewallUxTraceLoggingProvider::Provider(void)
0x180006dc6  mov     cs:qword_18003BEC8, rax
0x180006dcd  mov     rcx, rsi
0x180006dd0  mov     rax, cs:qword_18003BEC0
0x180006dd7  mov     cs:byte_18003BED0, 0
0x180006dde  mov     cs:dword_18003BED4, 1
0x180006de8  mov     rax, [rax+8]
0x180006dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006df1  mov     r8, rsi; lpContext
0x180006df4  lea     rcx, ?wrapper@?1??Instance@FirewallUxTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VFirewallUxTelemetry@@@details@wil@@A; lpInitOnce
0x180006dfb  xor     edx, edx; dwFlags
0x180006dfd  call    cs:__imp_InitOnceComplete
0x180006e03  mov     rcx, [rsp+28h+arg_18]
0x180006e08  mov     r8, rbx
0x180006e0b  mov     dl, dil
0x180006e0e  mov     rax, [rcx]
0x180006e11  mov     rax, [rax+10h]
0x180006e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e1a  mov     rbx, [rsp+28h+arg_0]
0x180006e1f  mov     rsi, [rsp+28h+arg_8]
0x180006e24  add     rsp, 20h
0x180006e28  pop     rdi
0x180006e29  retn
```
