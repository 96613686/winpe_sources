# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180012b20`
- end: `0x180012d9a`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `634`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180012da0`

## callees

- `0x180002b40`
- `0x180002c80`
- `0x180002f90`
- `0x180003350`
- `0x180012b20`
- `0x180018ce0`
- `0x18001cdf0`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180012d66`
- `KERNEL32!OutputDebugStringW` at `0x180012d66`
- `KERNEL32!GetCurrentThreadId` at `0x180012bc6`
- `KERNEL32!GetCurrentThreadId` at `0x180012bc6`
- `KERNEL32!IsDebuggerPresent` at `0x180012cd4`
- `KERNEL32!IsDebuggerPresent` at `0x180012cd4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int IsDebuggerPresent; // edi
  int v12; // r13d
  int v13; // ecx
  bool v14; // zf
  const struct wil::FailureInfo *v15; // rdx
  __int64 v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  IsDebuggerPresent = 0;
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, a2);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v14 = *a8 == 0, v23 = a8, v14) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16)),
         IsDebuggerPresent))
    && (v19 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v16);
  }
  wil::details::WilFailFast((wil::details *)&v18, v15);
}

```

## disassembly

```asm
0x180012b20  mov     [rsp-8+arg_18], rbx
0x180012b25  push    rbp
0x180012b26  push    rsi
0x180012b27  push    rdi
0x180012b28  push    r12
0x180012b2a  push    r13
0x180012b2c  push    r14
0x180012b2e  push    r15
0x180012b30  lea     rbp, [rsp-13C0h]
0x180012b38  mov     eax, 14C0h
0x180012b3d  call    _alloca_probe
0x180012b42  sub     rsp, rax
0x180012b45  mov     r15, r8
0x180012b48  mov     r14d, edx
0x180012b4b  mov     rsi, rcx
0x180012b4e  mov     r12, [rbp+13F0h+arg_28]
0x180012b55  xor     edi, edi
0x180012b57  mov     [rbp+13F0h+OutputString], di
0x180012b5e  mov     [rbp+13F0h+var_1430], dil
0x180012b62  mov     rbx, [rbp+13F0h+arg_30]
0x180012b69  mov     ecx, [rbx]; this
0x180012b6b  mov     [rsp+14F0h+var_14C8], ecx
0x180012b6f  mov     eax, [rbx+4]
0x180012b72  mov     [rsp+14F0h+var_14C4], eax
0x180012b76  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180012b7b  mov     r13d, eax
0x180012b7e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180012b86  mov     ecx, edi
0x180012b88  mov     eax, 8
0x180012b8d  cmp     dword ptr [rbx+8], 1
0x180012b91  cmovz   ecx, eax
0x180012b94  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180012b98  mov     ecx, 1
0x180012b9d  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180012ba5  inc     ecx
0x180012ba7  mov     [rsp+14F0h+var_14C0], ecx
0x180012bab  mov     rcx, [rbp+13F0h+arg_38]
0x180012bb2  test    rcx, rcx
0x180012bb5  jz      short loc_180012BC1
0x180012bb7  cmp     [rcx], di
0x180012bba  mov     [rsp+14F0h+var_14B8], rcx
0x180012bbf  jnz     short loc_180012BC6
0x180012bc1  mov     [rsp+14F0h+var_14B8], rdi
0x180012bc6  call    cs:__imp_GetCurrentThreadId
0x180012bcc  mov     [rsp+14F0h+var_14B0], eax
0x180012bd0  mov     [rsp+14F0h+var_1498], r15
0x180012bd5  mov     [rsp+14F0h+var_1490], r14d
0x180012bda  mov     [rsp+14F0h+var_148C], r13d
0x180012bdf  mov     [rsp+14F0h+var_14A8], rdi
0x180012be4  mov     [rsp+14F0h+var_14A0], rdi
0x180012be9  mov     [rbp+13F0h+var_1448], r12
0x180012bed  mov     [rbp+13F0h+var_1440], rsi
0x180012bf1  mov     [rsp+14F0h+var_1488], rdi
0x180012bf6  xorps   xmm0, xmm0
0x180012bf9  xor     eax, eax
0x180012bfb  movups  [rbp+13F0h+var_1468], xmm0
0x180012bff  mov     [rbp+13F0h+var_1458], rax
0x180012c03  xorps   xmm1, xmm1
0x180012c06  movups  [rsp+14F0h+var_1480], xmm1
0x180012c0b  mov     [rbp+13F0h+var_1470], rax
0x180012c0f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180012c16  test    rax, rax
0x180012c19  jz      short loc_180012C27
0x180012c1b  call    cs:__guard_dispatch_icall_fptr
0x180012c21  mov     [rbp+13F0h+var_1450], rax
0x180012c25  jmp     short loc_180012C2B
0x180012c27  mov     [rbp+13F0h+var_1450], rdi
0x180012c2b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180012c32  test    rax, rax
0x180012c35  jz      short loc_180012C42
0x180012c37  lea     rcx, [rsp+14F0h+var_14D0]
0x180012c3c  call    cs:__guard_dispatch_icall_fptr
0x180012c42  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180012c49  test    rax, rax
0x180012c4c  jz      short loc_180012C63
0x180012c4e  mov     r8d, 400h
0x180012c54  lea     rdx, [rbp+13F0h+var_1430]
0x180012c58  lea     rcx, [rsp+14F0h+var_14D0]
0x180012c5d  call    cs:__guard_dispatch_icall_fptr
0x180012c63  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012c6a  test    rax, rax
0x180012c6d  jz      short loc_180012C7A
0x180012c6f  lea     rcx, [rsp+14F0h+var_14D0]
0x180012c74  call    cs:__guard_dispatch_icall_fptr
0x180012c7a  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012c81  test    rax, rax
0x180012c84  jz      short loc_180012C98
0x180012c86  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180012c8b  jnz     short loc_180012C98
0x180012c8d  lea     rcx, [rsp+14F0h+var_14D0]
0x180012c92  call    cs:__guard_dispatch_icall_fptr
0x180012c98  cmp     [rsp+14F0h+var_14C8], edi
0x180012c9c  jl      short loc_180012CB4
0x180012c9e  mov     [rsp+14F0h+var_14C8], 8000FFFFh
0x180012ca6  mov     ecx, 8000FFFFh; this
0x180012cab  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180012cb0  mov     [rsp+14F0h+var_14C4], eax
0x180012cb4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180012cbb  jnz     short loc_180012CE4
0x180012cbd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180012cc4  test    rax, rax
0x180012cc7  jz      short loc_180012CD4
0x180012cc9  call    cs:__guard_dispatch_icall_fptr
0x180012ccf  movzx   edi, al
0x180012cd2  jmp     short loc_180012CE0
0x180012cd4  call    cs:__imp_IsDebuggerPresent
0x180012cda  test    eax, eax
0x180012cdc  setnz   dil
0x180012ce0  test    edi, edi
0x180012ce2  jz      short loc_180012CEB
0x180012ce4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180012ce9  jz      short loc_180012D12
0x180012ceb  mov     rax, cs:g_pfnResultLoggingCallback
0x180012cf2  test    rax, rax
0x180012cf5  jz      short loc_180012D6C
0x180012cf7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180012cfe  jnz     short loc_180012D6C
0x180012d00  xor     r8d, r8d
0x180012d03  xor     edx, edx
0x180012d05  lea     rcx, [rsp+14F0h+var_14D0]
0x180012d0a  call    cs:__guard_dispatch_icall_fptr
0x180012d10  jmp     short loc_180012D6C
0x180012d12  mov     rax, cs:g_pfnResultLoggingCallback
0x180012d19  test    rax, rax
0x180012d1c  jz      short loc_180012D3F
0x180012d1e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180012d25  jnz     short loc_180012D3F
0x180012d27  mov     r8d, 800h
0x180012d2d  lea     rdx, [rbp+13F0h+OutputString]
0x180012d34  lea     rcx, [rsp+14F0h+var_14D0]
0x180012d39  call    cs:__guard_dispatch_icall_fptr
0x180012d3f  cmp     [rbp+13F0h+OutputString], 0
0x180012d47  jnz     short loc_180012D5F
0x180012d49  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180012d4e  mov     edx, 800h; wchar_t *
0x180012d53  lea     rcx, [rbp+13F0h+OutputString]; this
0x180012d5a  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180012d5f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180012d66  call    cs:__imp_OutputDebugStringW
0x180012d6c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180012d71  jnz     short loc_180012D7C
0x180012d73  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x180012d7a  jz      short loc_180012D8F
0x180012d7c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180012d83  test    rax, rax
0x180012d86  jz      short loc_180012D8F
0x180012d88  call    cs:__guard_dispatch_icall_fptr
0x180012d8e  nop
0x180012d8f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180012d94  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
