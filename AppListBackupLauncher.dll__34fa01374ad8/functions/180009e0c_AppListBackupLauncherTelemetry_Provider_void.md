# AppListBackupLauncherTelemetry::Provider(void)

- ea: `0x180009e0c`
- end: `0x180009ebe`
- name: `?Provider@AppListBackupLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ`
- size: `178`
- prototype: `const struct _tlgProvider_t *(void)`
- caller_count: `9`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800033b8`
- `0x18000344c`
- `0x1800034e0`
- `0x18000355c`
- `0x1800058f0`
- `0x1800097b0`
- `0x18000ca14`
- `0x18000cc18`
- `0x18000ce20`

## callees

- `0x180002718`
- `0x180005d88`
- `0x180009e0c`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009e37`
- `api-ms-win-core-synch-l1-2-0!InitOnceBeginInitialize` at `0x180009e37`

## pseudocode

```c
const struct _tlgProvider_t *AppListBackupLauncherTelemetry::Provider(void)
{
  union _RTL_RUN_ONCE *v1; // [rsp+20h] [rbp-18h] BYREF
  int v2; // [rsp+28h] [rbp-10h]
  BOOL v3; // [rsp+40h] [rbp+8h] BYREF
  __int64 *v4; // [rsp+48h] [rbp+10h] BYREF

  v4 = 0;
  v3 = 0;
  if ( InitOnceBeginInitialize(&`AppListBackupLauncherTelemetry::Instance'::`2'::wrapper, 0, &v3, (LPVOID *)&v4) && v3 )
  {
    v1 = &`AppListBackupLauncherTelemetry::Instance'::`2'::wrapper;
    v4 = &qword_180019A70;
    qword_180019A70 = (__int64)&AppListBackupLauncherTelemetry::`vftable';
    qword_180019A78 = 0;
    byte_180019A80 = 0;
    dword_180019A84 = 0;
    qword_180019A88 = (__int64)&`AppListBackupLauncherTelemetry::StaticHandle::StaticHandle'::`2'::__hInner;
    atexit(_lambda_0674764cb4251821d5b23d1f729f03c6_::_lambda_invoker_cdecl_);
    v2 = 0;
    wil::details::static_lazy<AppListBackupLauncherTelemetry>::Completer::~Completer(&v1);
  }
  return (const struct _tlgProvider_t *)v4[1];
}

```

## disassembly

```asm
0x180009e0c  mov     rax, rsp
0x180009e0f  push    rdi
0x180009e10  sub     rsp, 30h
0x180009e14  lea     rdi, ?wrapper@?1??Instance@AppListBackupLauncherTelemetry@@KAPEAV2@XZ@4V?$static_lazy@VAppListBackupLauncherTelemetry@@@details@wil@@A; wil::details::static_lazy<AppListBackupLauncherTelemetry> `AppListBackupLauncherTelemetry::Instance(void)'::`2'::wrapper
0x180009e1b  mov     qword ptr [rax+10h], 0
0x180009e23  mov     rcx, rdi; lpInitOnce
0x180009e26  mov     dword ptr [rax+8], 0
0x180009e2d  lea     r9, [rax+10h]; lpContext
0x180009e31  xor     edx, edx; dwFlags
0x180009e33  lea     r8, [rax+8]; fPending
0x180009e37  call    cs:__imp_InitOnceBeginInitialize
0x180009e3d  test    eax, eax
0x180009e3f  jz      short loc_180009EAF
0x180009e41  cmp     [rsp+38h+arg_0], 0
0x180009e46  jz      short loc_180009EAF
0x180009e48  lea     rax, qword_180019A70
0x180009e4f  mov     [rsp+38h+var_18], rdi
0x180009e54  mov     [rsp+38h+arg_8], rax
0x180009e59  lea     rax, ??_7AppListBackupLauncherTelemetry@@6B@; const AppListBackupLauncherTelemetry::`vftable'
0x180009e60  mov     cs:qword_180019A70, rax
0x180009e67  mov     cs:qword_180019A78, 0
0x180009e72  mov     cs:byte_180019A80, 0
0x180009e79  mov     cs:dword_180019A84, 0
0x180009e83  lea     rax, ?__hInner@?1???0StaticHandle@AppListBackupLauncherTelemetry@@QEAA@XZ@4U_tlgProvider_t@@A; _tlgProvider_t `AppListBackupLauncherTelemetry::StaticHandle::StaticHandle(void)'::`2'::__hInner
0x180009e8a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0674764cb4251821d5b23d1f729f03c6_@@CA@XZ; void (__cdecl *)()
0x180009e91  mov     cs:qword_180019A88, rax
0x180009e98  call    atexit
0x180009e9d  lea     rcx, [rsp+38h+var_18]
0x180009ea2  mov     [rsp+38h+var_10], 0
0x180009eaa  call    ??1Completer@?$static_lazy@VAppListBackupLauncherTelemetry@@@details@wil@@QEAA@XZ; wil::details::static_lazy<AppListBackupLauncherTelemetry>::Completer::~Completer(void)
0x180009eaf  mov     rax, [rsp+38h+arg_8]
0x180009eb4  mov     rax, [rax+8]
0x180009eb8  add     rsp, 30h
0x180009ebc  pop     rdi
0x180009ebd  retn
```
