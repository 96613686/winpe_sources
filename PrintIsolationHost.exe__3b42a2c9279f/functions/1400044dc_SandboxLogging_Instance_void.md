# SandboxLogging::Instance(void)

- ea: `0x1400044dc`
- end: `0x140004591`
- name: `?Instance@SandboxLogging@@KAPEAV1@XZ`
- size: `181`
- prototype: `struct SandboxLogging *(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140003830`
- `0x140005e14`
- `0x14000634c`
- `0x140006454`

## callees

- `0x140001f44`
- `0x1400044dc`
- `0x140004bcc`

## import_xrefs

- `KERNEL32!InitOnceBeginInitialize` at `0x140004504`
- `KERNEL32!InitOnceBeginInitialize` at `0x140004504`
- `KERNEL32!InitOnceComplete` at `0x140004580`
- `KERNEL32!InitOnceComplete` at `0x140004580`

## pseudocode

```c
struct SandboxLogging *SandboxLogging::Instance(void)
{
  void (*v0)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *); // r8
  WINBOOL v2; // [rsp+30h] [rbp+8h] BYREF
  LPVOID v3; // [rsp+38h] [rbp+10h] BYREF

  v3 = 0;
  v2 = 0;
  if ( InitOnceBeginInitialize(&`SandboxLogging::Instance'::`2'::wrapper, 0, &v2, &v3) && v2 )
  {
    qword_14000C3D0 = 0;
    v3 = &qword_14000C3C8;
    qword_14000C3C8 = &SandboxLogging::`vftable';
    byte_14000C3D8 = 0;
    dword_14000C3DC = 0;
    qword_14000C3E0 = (struct _tlgProvider_t *)&`SandboxLogging::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_faf7c1d3cf9d7eb9e3371f994615d904_::_lambda_invoker_cdecl_);
    wil::TraceLoggingProvider::Register((wil::TraceLoggingProvider *)&qword_14000C3C8, qword_14000C3E0, v0);
    InitOnceComplete(&`SandboxLogging::Instance'::`2'::wrapper, 0, &qword_14000C3C8);
  }
  return (struct SandboxLogging *)v3;
}

```

## disassembly

```asm
0x1400044dc  mov     rax, rsp
0x1400044df  push    rbx
0x1400044e0  sub     rsp, 20h
0x1400044e4  lea     r9, [rax+10h]; lpContext
0x1400044e8  mov     qword ptr [rax+10h], 0
0x1400044f0  lea     r8, [rax+8]; fPending
0x1400044f4  mov     dword ptr [rax+8], 0
0x1400044fb  xor     edx, edx; dwFlags
0x1400044fd  lea     rcx, ?wrapper@?1??Instance@SandboxLogging@@KAPEAV2@XZ@4V?$static_lazy@VSandboxLogging@@@details@wil@@A; lpInitOnce
0x140004504  call    cs:__imp_InitOnceBeginInitialize
0x14000450a  test    eax, eax
0x14000450c  jz      short loc_140004586
0x14000450e  cmp     [rsp+28h+arg_0], 0
0x140004513  jz      short loc_140004586
0x140004515  lea     rbx, qword_14000C3C8
0x14000451c  mov     cs:qword_14000C3D0, 0
0x140004527  lea     rax, ??_7SandboxLogging@@6B@; const SandboxLogging::`vftable'
0x14000452e  mov     [rsp+28h+arg_8], rbx
0x140004533  mov     cs:qword_14000C3C8, rax
0x14000453a  mov     cs:byte_14000C3D8, 0
0x140004541  mov     cs:dword_14000C3DC, 0
0x14000454b  lea     rax, ?__hInner@?1???0StaticHandle@SandboxLogging@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `SandboxLogging::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x140004552  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_faf7c1d3cf9d7eb9e3371f994615d904_@@CA@XZ; void (__cdecl *)()
0x140004559  mov     cs:qword_14000C3E0, rax
0x140004560  call    atexit
0x140004565  mov     rdx, cs:qword_14000C3E0; struct _tlgProvider_t *
0x14000456c  mov     rcx, rbx; this
0x14000456f  call    ?Register@TraceLoggingProvider@wil@@IEAAXQEBU_tlgProvider_t@@P6AXPEBU_GUID@@KE_K2PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z@Z; wil::TraceLoggingProvider::Register(_tlgProvider_t const * const,void (*)(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *))
0x140004574  mov     r8, rbx; lpContext
0x140004577  lea     rcx, ?wrapper@?1??Instance@SandboxLogging@@KAPEAV2@XZ@4V?$static_lazy@VSandboxLogging@@@details@wil@@A; lpInitOnce
0x14000457e  xor     edx, edx; dwFlags
0x140004580  call    cs:__imp_InitOnceComplete
0x140004586  mov     rax, [rsp+28h+arg_8]
0x14000458b  add     rsp, 20h
0x14000458f  pop     rbx
0x140004590  retn
```
