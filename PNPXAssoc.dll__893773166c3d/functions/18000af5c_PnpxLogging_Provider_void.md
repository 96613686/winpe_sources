# PnpxLogging::Provider(void)

- ea: `0x18000af5c`
- end: `0x18000b00e`
- name: `?Provider@PnpxLogging@@SAPEBU_tlgProvider_t@@XZ`
- size: `178`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000959c`
- `0x180009748`

## callees

- `0x180001f84`
- `0x18000a170`
- `0x18000af5c`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x18000af84`
- `KERNEL32!InitOnceBeginInitialize` at `0x18000af84`
- `KERNEL32!InitOnceComplete` at `0x18000aff9`
- `KERNEL32!InitOnceComplete` at `0x18000aff9`

## pseudocode

```c
const struct _tlgProvider_t *PnpxLogging::Provider(void)
{
  WINBOOL v1; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v2; // [rsp+38h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 0;
  if ( InitOnceBeginInitialize(&`PnpxLogging::Instance'::`2'::wrapper, 0, &v1, (LPVOID *)&v2) && v1 )
  {
    qword_18001ACD0 = 0;
    v2 = &qword_18001ACC8;
    qword_18001ACC8 = &wil::TraceLoggingProvider::`vftable';
    byte_18001ACD8 = 0;
    dword_18001ACDC = 0;
    qword_18001ACE0 = (__int64)&`PnpxLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_81cb19f63afa0abe41d87c3a9d221c3d_::_lambda_invoker_cdecl_);
    PnpxLogging::Create((PnpxLogging *)&qword_18001ACC8);
    InitOnceComplete(&`PnpxLogging::Instance'::`2'::wrapper, 0, &qword_18001ACC8);
  }
  return (const struct _tlgProvider_t *)v2[1];
}

```

## disassembly

```asm
0x18000af5c  mov     rax, rsp
0x18000af5f  push    rbx
0x18000af60  sub     rsp, 20h
0x18000af64  lea     r9, [rax+10h]; lpContext
0x18000af68  mov     qword ptr [rax+10h], 0
0x18000af70  lea     r8, [rax+8]; fPending
0x18000af74  mov     dword ptr [rax+8], 0
0x18000af7b  xor     edx, edx; dwFlags
0x18000af7d  lea     rcx, ?wrapper@?1??Instance@PnpxLogging@@KAPEAV2@XZ@4V?$static_lazy@VPnpxLogging@@@details@wil@@A; lpInitOnce
0x18000af84  call    cs:__imp_InitOnceBeginInitialize
0x18000af8a  test    eax, eax
0x18000af8c  jz      short loc_18000AFFF
0x18000af8e  cmp     [rsp+28h+arg_0], 0
0x18000af93  jz      short loc_18000AFFF
0x18000af95  lea     rbx, qword_18001ACC8
0x18000af9c  mov     cs:qword_18001ACD0, 0
0x18000afa7  lea     rax, ??_7TraceLoggingProvider@wil@@6B@; const wil::TraceLoggingProvider::`vftable'
0x18000afae  mov     [rsp+28h+arg_8], rbx
0x18000afb3  mov     cs:qword_18001ACC8, rax
0x18000afba  mov     cs:byte_18001ACD8, 0
0x18000afc1  mov     cs:dword_18001ACDC, 0
0x18000afcb  lea     rax, ?__hInner@?1???0StaticHandle@PnpxLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `PnpxLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x18000afd2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_81cb19f63afa0abe41d87c3a9d221c3d_@@CA@XZ; void (__cdecl *)()
0x18000afd9  mov     cs:qword_18001ACE0, rax
0x18000afe0  call    atexit
0x18000afe5  mov     rcx, rbx; this
0x18000afe8  call    ?Create@PnpxLogging@@IEAAXXZ; PnpxLogging::Create(void)
0x18000afed  mov     r8, rbx; lpContext
0x18000aff0  lea     rcx, ?wrapper@?1??Instance@PnpxLogging@@KAPEAV2@XZ@4V?$static_lazy@VPnpxLogging@@@details@wil@@A; lpInitOnce
0x18000aff7  xor     edx, edx; dwFlags
0x18000aff9  call    cs:__imp_InitOnceComplete
0x18000afff  mov     rax, [rsp+28h+arg_8]
0x18000b004  mov     rax, [rax+8]
0x18000b008  add     rsp, 20h
0x18000b00c  pop     rbx
0x18000b00d  retn
```
