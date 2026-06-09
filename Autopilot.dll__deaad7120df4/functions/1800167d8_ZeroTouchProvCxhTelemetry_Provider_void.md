# ZeroTouchProvCxhTelemetry::Provider(void)

- ea: `0x1800167d8`
- end: `0x1800168b9`
- name: `?Provider@ZeroTouchProvCxhTelemetry@@SAPEBU_tlgProvider_t@@XZ`
- size: `225`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180015f48`
- `0x1800161c8`
- `0x18001625c`
- `0x1800168c0`
- `0x18001c070`

## callees

- `0x1800049e8`
- `0x18001670c`
- `0x1800167d8`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180016800`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180016800`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001689d`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x18001689d`

## pseudocode

```c
const struct _tlgProvider_t *ZeroTouchProvCxhTelemetry::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  __int64 *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( __std_init_once_begin_initialize(&`ZeroTouchProvCxhTelemetry::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2)
    && v1 )
  {
    qword_180044A88 = 0;
    qword_180044A80 = (__int64)&ZeroTouchProvCxhTelemetry::`vftable';
    v2 = &qword_180044A80;
    byte_180044A90 = 0;
    dword_180044A94 = 0;
    atexit(_lambda_83e41ce2d9c84e0531eaa5aafac1b80d_::_lambda_invoker_cdecl_);
    qword_180044A88 = (__int64)AutoPilotTelemProvider::Provider();
    byte_180044A90 = 0;
    dword_180044A94 = 1;
    (*(void (__fastcall **)(__int64 *))(qword_180044A80 + 8))(&qword_180044A80);
    InitOnceComplete(&`ZeroTouchProvCxhTelemetry::Instance'::`2'::wrapper, 0, &qword_180044A80);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x1800167d8  mov     rax, rsp
0x1800167db  push    rbx
0x1800167dc  sub     rsp, 20h
0x1800167e0  lea     r9, [rax+10h]; lpContext
0x1800167e4  mov     qword ptr [rax+10h], 0
0x1800167ec  lea     r8, [rax+8]; fPending
0x1800167f0  mov     dword ptr [rax+8], 0
0x1800167f7  xor     edx, edx; dwFlags
0x1800167f9  lea     rcx, ?wrapper@?1??Instance@ZeroTouchProvCxhTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VZeroTouchProvCxhTelemetry@@@details@wil@@A; lpInitOnce
0x180016800  call    cs:__imp___std_init_once_begin_initialize
0x180016807  nop     dword ptr [rax+rax+00h]
0x18001680c  test    eax, eax
0x18001680e  jz      loc_1800168A9
0x180016814  cmp     [rsp+28h+arg_0], 0
0x180016819  jz      loc_1800168A9
0x18001681f  lea     rax, ??_7ZeroTouchProvCxhTelemetry@@6B@; const ZeroTouchProvCxhTelemetry::`vftable'
0x180016826  mov     cs:qword_180044A88, 0
0x180016831  lea     rbx, qword_180044A80
0x180016838  mov     cs:qword_180044A80, rax
0x18001683f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_83e41ce2d9c84e0531eaa5aafac1b80d_@@CA@XZ; void (__cdecl *)()
0x180016846  mov     [rsp+28h+arg_8], rbx
0x18001684b  mov     cs:byte_180044A90, 0
0x180016852  mov     cs:dword_180044A94, 0
0x18001685c  call    atexit
0x180016861  call    ?Provider@AutoPilotTelemProvider@@SAPEBU_tlgProvider_t@@XZ; AutoPilotTelemProvider::Provider(void)
0x180016866  mov     cs:qword_180044A88, rax
0x18001686d  mov     rcx, rbx
0x180016870  mov     rax, cs:qword_180044A80
0x180016877  mov     cs:byte_180044A90, 0
0x18001687e  mov     cs:dword_180044A94, 1
0x180016888  mov     rax, [rax+8]
0x18001688c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016891  mov     r8, rbx; lpContext
0x180016894  lea     rcx, ?wrapper@?1??Instance@ZeroTouchProvCxhTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VZeroTouchProvCxhTelemetry@@@details@wil@@A; lpInitOnce
0x18001689b  xor     edx, edx; dwFlags
0x18001689d  call    cs:__imp_InitOnceComplete
0x1800168a4  nop     dword ptr [rax+rax+00h]
0x1800168a9  mov     rax, [rsp+28h+arg_8]
0x1800168ae  mov     rax, [rax+8]
0x1800168b2  add     rsp, 20h
0x1800168b6  pop     rbx
0x1800168b7  retn
```
