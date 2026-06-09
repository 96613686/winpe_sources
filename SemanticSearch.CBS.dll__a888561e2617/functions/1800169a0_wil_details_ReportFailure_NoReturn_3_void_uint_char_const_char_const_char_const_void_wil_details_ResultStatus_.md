# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800169a0`
- end: `0x180016c1a`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `634`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180016c20`

## callees

- `0x1800161a0`
- `0x180016290`
- `0x1800168c0`
- `0x1800169a0`
- `0x180016c60`
- `0x1800514d0`
- `0x18005e260`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180016be6`
- `KERNEL32!OutputDebugStringW` at `0x180016be6`
- `KERNEL32!GetCurrentThreadId` at `0x180016a46`
- `KERNEL32!GetCurrentThreadId` at `0x180016a46`
- `KERNEL32!IsDebuggerPresent` at `0x180016b54`
- `KERNEL32!IsDebuggerPresent` at `0x180016b54`

## pseudocode

```c
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
      wil::GetFailureLogString(OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v17);
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
0x1800169a0  mov     [rsp-8+arg_18], rbx
0x1800169a5  push    rbp
0x1800169a6  push    rsi
0x1800169a7  push    rdi
0x1800169a8  push    r12
0x1800169aa  push    r13
0x1800169ac  push    r14
0x1800169ae  push    r15
0x1800169b0  lea     rbp, [rsp-13C0h]
0x1800169b8  mov     eax, 14C0h
0x1800169bd  call    _alloca_probe
0x1800169c2  sub     rsp, rax
0x1800169c5  mov     r15, r8
0x1800169c8  mov     r14d, edx
0x1800169cb  mov     rsi, rcx
0x1800169ce  mov     r12, [rbp+13F0h+arg_28]
0x1800169d5  xor     edi, edi
0x1800169d7  mov     [rbp+13F0h+OutputString], di
0x1800169de  mov     [rbp+13F0h+var_1430], dil
0x1800169e2  mov     rbx, [rbp+13F0h+arg_30]
0x1800169e9  mov     ecx, [rbx]; this
0x1800169eb  mov     [rsp+14F0h+var_14C8], ecx
0x1800169ef  mov     eax, [rbx+4]
0x1800169f2  mov     [rsp+14F0h+var_14C4], eax
0x1800169f6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800169fb  mov     r13d, eax
0x1800169fe  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180016a06  mov     ecx, edi
0x180016a08  mov     eax, 8
0x180016a0d  cmp     dword ptr [rbx+8], 1
0x180016a11  cmovz   ecx, eax
0x180016a14  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180016a18  mov     ecx, 1
0x180016a1d  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180016a25  inc     ecx
0x180016a27  mov     [rsp+14F0h+var_14C0], ecx
0x180016a2b  mov     rcx, [rbp+13F0h+arg_38]
0x180016a32  test    rcx, rcx
0x180016a35  jz      short loc_180016A41
0x180016a37  cmp     [rcx], di
0x180016a3a  mov     [rsp+14F0h+var_14B8], rcx
0x180016a3f  jnz     short loc_180016A46
0x180016a41  mov     [rsp+14F0h+var_14B8], rdi
0x180016a46  call    cs:__imp_GetCurrentThreadId
0x180016a4c  mov     [rsp+14F0h+var_14B0], eax
0x180016a50  mov     [rsp+14F0h+var_1498], r15
0x180016a55  mov     [rsp+14F0h+var_1490], r14d
0x180016a5a  mov     [rsp+14F0h+var_148C], r13d
0x180016a5f  mov     [rsp+14F0h+var_14A8], rdi
0x180016a64  mov     [rsp+14F0h+var_14A0], rdi
0x180016a69  mov     [rbp+13F0h+var_1448], r12
0x180016a6d  mov     [rbp+13F0h+var_1440], rsi
0x180016a71  mov     [rsp+14F0h+var_1488], rdi
0x180016a76  xorps   xmm0, xmm0
0x180016a79  xor     eax, eax
0x180016a7b  movups  [rbp+13F0h+var_1468], xmm0
0x180016a7f  mov     [rbp+13F0h+var_1458], rax
0x180016a83  xorps   xmm1, xmm1
0x180016a86  movups  [rsp+14F0h+var_1480], xmm1
0x180016a8b  mov     [rbp+13F0h+var_1470], rax
0x180016a8f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180016a96  test    rax, rax
0x180016a99  jz      short loc_180016AA7
0x180016a9b  call    cs:__guard_dispatch_icall_fptr
0x180016aa1  mov     [rbp+13F0h+var_1450], rax
0x180016aa5  jmp     short loc_180016AAB
0x180016aa7  mov     [rbp+13F0h+var_1450], rdi
0x180016aab  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180016ab2  test    rax, rax
0x180016ab5  jz      short loc_180016AC2
0x180016ab7  lea     rcx, [rsp+14F0h+var_14D0]
0x180016abc  call    cs:__guard_dispatch_icall_fptr
0x180016ac2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180016ac9  test    rax, rax
0x180016acc  jz      short loc_180016AE3
0x180016ace  mov     r8d, 400h
0x180016ad4  lea     rdx, [rbp+13F0h+var_1430]
0x180016ad8  lea     rcx, [rsp+14F0h+var_14D0]
0x180016add  call    cs:__guard_dispatch_icall_fptr
0x180016ae3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180016aea  test    rax, rax
0x180016aed  jz      short loc_180016AFA
0x180016aef  lea     rcx, [rsp+14F0h+var_14D0]
0x180016af4  call    cs:__guard_dispatch_icall_fptr
0x180016afa  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180016b01  test    rax, rax
0x180016b04  jz      short loc_180016B18
0x180016b06  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180016b0b  jnz     short loc_180016B18
0x180016b0d  lea     rcx, [rsp+14F0h+var_14D0]
0x180016b12  call    cs:__guard_dispatch_icall_fptr
0x180016b18  cmp     [rsp+14F0h+var_14C8], edi
0x180016b1c  jl      short loc_180016B34
0x180016b1e  mov     [rsp+14F0h+var_14C8], 8000FFFFh
0x180016b26  mov     ecx, 8000FFFFh; this
0x180016b2b  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180016b30  mov     [rsp+14F0h+var_14C4], eax
0x180016b34  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180016b3b  jnz     short loc_180016B64
0x180016b3d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180016b44  test    rax, rax
0x180016b47  jz      short loc_180016B54
0x180016b49  call    cs:__guard_dispatch_icall_fptr
0x180016b4f  movzx   edi, al
0x180016b52  jmp     short loc_180016B60
0x180016b54  call    cs:__imp_IsDebuggerPresent
0x180016b5a  test    eax, eax
0x180016b5c  setnz   dil
0x180016b60  test    edi, edi
0x180016b62  jz      short loc_180016B6B
0x180016b64  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180016b69  jz      short loc_180016B92
0x180016b6b  mov     rax, cs:g_pfnResultLoggingCallback
0x180016b72  test    rax, rax
0x180016b75  jz      short loc_180016BEC
0x180016b77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180016b7e  jnz     short loc_180016BEC
0x180016b80  xor     r8d, r8d
0x180016b83  xor     edx, edx
0x180016b85  lea     rcx, [rsp+14F0h+var_14D0]
0x180016b8a  call    cs:__guard_dispatch_icall_fptr
0x180016b90  jmp     short loc_180016BEC
0x180016b92  mov     rax, cs:g_pfnResultLoggingCallback
0x180016b99  test    rax, rax
0x180016b9c  jz      short loc_180016BBF
0x180016b9e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180016ba5  jnz     short loc_180016BBF
0x180016ba7  mov     r8d, 800h
0x180016bad  lea     rdx, [rbp+13F0h+OutputString]
0x180016bb4  lea     rcx, [rsp+14F0h+var_14D0]
0x180016bb9  call    cs:__guard_dispatch_icall_fptr
0x180016bbf  cmp     [rbp+13F0h+OutputString], 0
0x180016bc7  jnz     short loc_180016BDF
0x180016bc9  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180016bce  mov     edx, 800h; wchar_t *
0x180016bd3  lea     rcx, [rbp+13F0h+OutputString]; Buffer
0x180016bda  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180016bdf  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180016be6  call    cs:__imp_OutputDebugStringW
0x180016bec  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180016bf1  jnz     short loc_180016BFC
0x180016bf3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x180016bfa  jz      short loc_180016C0F
0x180016bfc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180016c03  test    rax, rax
0x180016c06  jz      short loc_180016C0F
0x180016c08  call    cs:__guard_dispatch_icall_fptr
0x180016c0e  nop
0x180016c0f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180016c14  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
