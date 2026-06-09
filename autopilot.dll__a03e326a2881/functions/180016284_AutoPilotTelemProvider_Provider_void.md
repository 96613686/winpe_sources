# AutoPilotTelemProvider::Provider(void)

- ea: `0x180016284`
- end: `0x18001633d`
- name: `?Provider@AutoPilotTelemProvider@@SAPEBU_tlgProvider_t@@XZ`
- size: `185`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `7`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180014bc4`
- `0x180015f10`
- `0x180016344`
- `0x180016838`
- `0x1800169c0`
- `0x180016e50`
- `0x180018024`

## callees

- `0x1800049c8`
- `0x18000fca8`
- `0x180016284`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800162ac`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x1800162ac`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016328`
- `api-ms-win-core-synch-l1-2-0!InitOnceComplete` at `0x180016328`

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
    qword_180043AA8 = 0;
    v3 = &qword_180043AA0;
    qword_180043AA0 = &AutoPilotTelemProvider::`vftable';
    byte_180043AB0 = 0;
    dword_180043AB4 = 0;
    qword_180043AB8 = (struct _tlgProvider_t *)&`AutoPilotTelemProvider::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_1aef734b6af38396df4f2a61358db069_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_180043AA0, qword_180043AB8, v0);
    InitOnceComplete(&`AutoPilotTelemProvider::Instance'::`2'::wrapper, 0, &qword_180043AA0);
  }
  return (const struct _tlgProvider_t *)v3[1];
}

```

## disassembly

```asm
0x180016284  mov     rax, rsp
0x180016287  push    rbx
0x180016288  sub     rsp, 20h
0x18001628c  lea     r9, [rax+10h]; lpContext
0x180016290  mov     qword ptr [rax+10h], 0
0x180016298  lea     r8, [rax+8]; fPending
0x18001629c  mov     dword ptr [rax+8], 0
0x1800162a3  xor     edx, edx; dwFlags
0x1800162a5  lea     rcx, ?wrapper@?1??Instance@AutoPilotTelemProvider@@KAPEAV2@XZ@4V?$static_lazy@VAutoPilotTelemProvider@@@details@wil@@A; lpInitOnce
0x1800162ac  call    cs:__imp___std_init_once_begin_initialize
0x1800162b2  test    eax, eax
0x1800162b4  jz      short loc_18001632E
0x1800162b6  cmp     [rsp+28h+arg_0], 0
0x1800162bb  jz      short loc_18001632E
0x1800162bd  lea     rbx, qword_180043AA0
0x1800162c4  mov     cs:qword_180043AA8, 0
0x1800162cf  lea     rax, ??_7AutoPilotTelemProvider@@6B@; const AutoPilotTelemProvider::`vftable'
0x1800162d6  mov     [rsp+28h+arg_8], rbx
0x1800162db  mov     cs:qword_180043AA0, rax
0x1800162e2  mov     cs:byte_180043AB0, 0
0x1800162e9  mov     cs:dword_180043AB4, 0
0x1800162f3  lea     rax, ?__hInner@?1???0StaticHandle@AutoPilotTelemProvider@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `AutoPilotTelemProvider::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x1800162fa  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1aef734b6af38396df4f2a61358db069_@@CA@XZ; void (__cdecl *)()
0x180016301  mov     cs:qword_180043AB8, rax
0x180016308  call    atexit
0x18001630d  mov     rdx, cs:qword_180043AB8; struct _tlgProvider_t *
0x180016314  mov     rcx, rbx; this
0x180016317  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x18001631c  mov     r8, rbx; lpContext
0x18001631f  lea     rcx, ?wrapper@?1??Instance@AutoPilotTelemProvider@@KAPEAV2@XZ@4V?$static_lazy@VAutoPilotTelemProvider@@@details@wil@@A; lpInitOnce
0x180016326  xor     edx, edx; dwFlags
0x180016328  call    cs:__imp_InitOnceComplete
0x18001632e  mov     rax, [rsp+28h+arg_8]
0x180016333  mov     rax, [rax+8]
0x180016337  add     rsp, 20h
0x18001633b  pop     rbx
0x18001633c  retn
```
