# RestartSystem

- ea: `0x14002027c`
- end: `0x1400203af`
- name: `RestartSystem`
- size: `307`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x14000ceb4`

## callees

- `0x1400023e0`
- `0x1400054b0`
- `0x140016a40`
- `0x140016fb4`
- `0x140017538`
- `0x14001b210`
- `0x14001c6e8`
- `0x14002027c`
- `0x1400203b8`
- `0x1400206cc`

## import_xrefs

- `api-ms-win-core-shutdown-l1-1-1!InitiateShutdownW` at `0x140020344`
- `api-ms-win-core-shutdown-l1-1-1!InitiateShutdownW` at `0x140020344`

## string_xrefs

- `0x1400202cb`: `Failed to enable shutdown privileges.`
- `0x140020373`: `Unable to disable shutdown privilege`

## pseudocode

```c
__int64 __fastcall RestartSystem(int a1, int a2, int a3, int a4)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  struct _TOKEN_PRIVILEGES *v8; // rsi
  unsigned int v9; // edi
  DWORD v10; // eax
  __int64 v11; // rcx
  int *v12; // r8
  int v13; // ebx
  unsigned int v14; // eax
  int dwReason; // [rsp+20h] [rbp-38h]
  int v16[2]; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES *v17; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v17 = 0;
  v4 = SetPrivilegesById(a1, a2, a3, a4, (__int64)&v17);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v8 = v17;
    *(_QWORD *)v16 = v17;
    v9 = 0;
    v10 = InitiateShutdownW(0, 0, 0, 0x10007u, 0x80020003);
    v13 = v10;
    if ( v10 )
    {
      LogAdapter::TraceAtLevelWin32<unsigned long,>(v11, v10, v12);
      if ( v13 > 0 )
        v9 = (unsigned __int16)v13 | 0x80070000;
      else
        v9 = v13;
    }
    v14 = SetPrivileges(v11, v8, 0);
    LogAdapter::TraceAtLevelIfFailed<long,>(2, v14, "Unable to disable shutdown privilege");
    Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close((void **)v16);
    return v9;
  }
  else
  {
    LODWORD(v17) = v4;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to enable shutdown privileges.");
      *(_QWORD *)v16 = &v17;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        v6,
        3,
        (__int64)": {}",
        (__int64)v16);
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x102,
      (unsigned int)"onecore\\base\\cbs\\util\\cbspriv.cpp",
      (const char *)v5,
      dwReason);
    return v5;
  }
}

```

## disassembly

```asm
0x14002027c  mov     r11, rsp
0x14002027f  mov     [r11+8], rbx
0x140020283  mov     [r11+10h], rsi
0x140020287  push    rdi
0x140020288  sub     rsp, 50h
0x14002028c  mov     rax, cs:__security_cookie
0x140020293  xor     rax, rsp
0x140020296  mov     [rsp+58h+var_18], rax
0x14002029b  lea     rax, [r11-20h]
0x14002029f  mov     qword ptr [r11-20h], 0
0x1400202a7  mov     [r11-38h], rax
0x1400202ab  call    SetPrivilegesById
0x1400202b0  mov     ebx, eax
0x1400202b2  test    eax, eax
0x1400202b4  jns     short loc_140020323
0x1400202b6  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400202bd  mov     dword ptr [rsp+58h+var_20], eax
0x1400202c1  test    rcx, rcx
0x1400202c4  jz      short loc_140020306
0x1400202c6  mov     edi, 3
0x1400202cb  lea     r9, aFailedToEnable; "Failed to enable shutdown privileges."
0x1400202d2  mov     r8d, edi
0x1400202d5  xor     edx, edx
0x1400202d7  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1400202dc  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1400202e3  lea     rax, [rsp+58h+var_20]
0x1400202e8  mov     qword ptr [rsp+58h+var_28], rax
0x1400202ed  lea     r9, asc_1400353E8; ": {}"
0x1400202f4  lea     rax, [rsp+58h+var_28]
0x1400202f9  mov     r8d, edi
0x1400202fc  mov     qword ptr [rsp+58h+dwReason], rax; int
0x140020301  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140020306  mov     rcx, [rsp+58h]; this
0x14002030b  lea     r8, aOnecoreBaseCbs_11; "onecore\\base\\cbs\\util\\cbspriv.cpp"
0x140020312  mov     r9d, ebx; char *
0x140020315  mov     edx, 102h; void *
0x14002031a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002031f  mov     eax, ebx
0x140020321  jmp     short loc_140020392
0x140020323  mov     rsi, [rsp+58h+var_20]
0x140020328  mov     r9d, 10007h; dwShutdownFlags
0x14002032e  xor     r8d, r8d; dwGracePeriod
0x140020331  mov     qword ptr [rsp+58h+var_28], rsi
0x140020336  xor     edx, edx; lpMessage
0x140020338  mov     [rsp+58h+dwReason], 80020003h; dwReason
0x140020340  xor     ecx, ecx; lpMachineName
0x140020342  xor     edi, edi
0x140020344  call    cs:__imp_InitiateShutdownW
0x14002034a  mov     ebx, eax
0x14002034c  test    eax, eax
0x14002034e  jz      short loc_140020368
0x140020350  mov     edx, eax
0x140020352  call    ??$TraceAtLevelWin32@K$$V@LogAdapter@@YAXW4LogLevel@0@KQEBD@Z; LogAdapter::TraceAtLevelWin32<ulong,>(LogAdapter::LogLevel,ulong,char const * const)
0x140020357  test    ebx, ebx
0x140020359  jg      short loc_14002035F
0x14002035b  mov     edi, ebx
0x14002035d  jmp     short loc_140020368
0x14002035f  movzx   edi, bx
0x140020362  or      edi, 80070000h
0x140020368  xor     r8d, r8d
0x14002036b  mov     rdx, rsi
0x14002036e  call    SetPrivileges
0x140020373  lea     r8, aUnableToDisabl; "Unable to disable shutdown privilege"
0x14002037a  mov     edx, eax
0x14002037c  mov     ecx, 2
0x140020381  call    ??$TraceAtLevelIfFailed@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelIfFailed<long,>(LogAdapter::LogLevel,long,char const * const)
0x140020386  lea     rcx, [rsp+58h+var_28]
0x14002038b  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@V?$AutoNewArrayPtr@_W@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,Windows::AutoNewArrayPtr<wchar_t>>::Close(void)
0x140020390  mov     eax, edi
0x140020392  mov     rcx, [rsp+58h+var_18]
0x140020397  xor     rcx, rsp; StackCookie
0x14002039a  call    __security_check_cookie
0x14002039f  mov     rbx, [rsp+58h+arg_0]
0x1400203a4  mov     rsi, [rsp+58h+arg_8]
0x1400203a9  add     rsp, 50h
0x1400203ad  pop     rdi
0x1400203ae  retn
```
