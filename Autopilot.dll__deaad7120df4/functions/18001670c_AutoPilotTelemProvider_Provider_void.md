# AutoPilotTelemProvider::Provider(void)

- ea: `0x18001670c`
- end: `0x1800167d2`
- name: `?Provider@AutoPilotTelemProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `198`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014fb0`
- `0x180016390`
- `0x1800167d8`
- `0x180016ce4`
- `0x180016ebc`
- `0x180017360`
- `0x180018568`

## callees

- `0x1800049e8`
- `0x18000fd60`
- `0x18001670c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180016734`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180016734`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800167b6`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x1800167b6`

## pseudocode

```c
const struct _tlgProvider_t *AutoPilotTelemProvider::Provider(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( __std_init_once_begin_initialize(&`AutoPilotTelemProvider::Instance'::`2'::wrapper, 0, &v2, (LPVOID *)&v3) && v2 )
  {
    qword_180044AA8 = 0;
    v3 = &qword_180044AA0;
    qword_180044AA0 = &AutoPilotTelemProvider::`vftable';
    byte_180044AB0 = 0;
    dword_180044AB4 = 0;
    qword_180044AB8 = (struct _tlgProvider_t *)&`AutoPilotTelemProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_1aef734b6af38396df4f2a61358db069_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180044AA0, qword_180044AB8, v0);
    InitOnceComplete(&`AutoPilotTelemProvider::Instance'::`2'::wrapper, 0, &qword_180044AA0);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x18001670c  mov     rax, rsp
0x18001670f  push    rbx
0x180016710  sub     rsp, 20h
0x180016714  lea     r9, [rax+10h]; lpContext
0x180016718  mov     qword ptr [rax+10h], 0
0x180016720  lea     r8, [rax+8]; fPending
0x180016724  mov     dword ptr [rax+8], 0
0x18001672b  xor     edx, edx; dwFlags
0x18001672d  lea     rcx, ?wrapper@?1??Instance@AutoPilotTelemProvider@@KAPEAV2@XZ@4V?$static_lazy@VAutoPilotTelemProvider@@@details@wil@@A; lpInitOnce
0x180016734  call    cs:__imp___std_init_once_begin_initialize
0x18001673b  nop     dword ptr [rax+rax+00h]
0x180016740  test    eax, eax
0x180016742  jz      short loc_1800167C2
0x180016744  cmp     [rsp+28h+arg_0], 0
0x180016749  jz      short loc_1800167C2
0x18001674b  lea     rbx, qword_180044AA0
0x180016752  mov     cs:qword_180044AA8, 0
0x18001675d  lea     rax, ??_7AutoPilotTelemProvider@@6B@; const AutoPilotTelemProvider::`vftable'
0x180016764  mov     [rsp+28h+arg_8], rbx
0x180016769  mov     cs:qword_180044AA0, rax
0x180016770  mov     cs:byte_180044AB0, 0
0x180016777  mov     cs:dword_180044AB4, 0
0x180016781  lea     rax, ?__hInner@?1???0StaticHandle@AutoPilotTelemProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `AutoPilotTelemProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180016788  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1aef734b6af38396df4f2a61358db069_@@CA@XZ; void (__cdecl *)()
0x18001678f  mov     cs:qword_180044AB8, rax
0x180016796  call    atexit
0x18001679b  mov     rdx, cs:qword_180044AB8; struct _tlgProvider_t *
0x1800167a2  mov     rcx, rbx; this
0x1800167a5  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x1800167aa  mov     r8, rbx; lpContext
0x1800167ad  lea     rcx, ?wrapper@?1??Instance@AutoPilotTelemProvider@@KAPEAV2@XZ@4V?$static_lazy@VAutoPilotTelemProvider@@@details@wil@@A; lpInitOnce
0x1800167b4  xor     edx, edx; dwFlags
0x1800167b6  call    cs:__imp_InitOnceComplete
0x1800167bd  nop     dword ptr [rax+rax+00h]
0x1800167c2  mov     rax, [rsp+28h+arg_8]
0x1800167c7  mov     rax, [rax+8]
0x1800167cb  add     rsp, 20h
0x1800167cf  pop     rbx
0x1800167d0  retn
```
