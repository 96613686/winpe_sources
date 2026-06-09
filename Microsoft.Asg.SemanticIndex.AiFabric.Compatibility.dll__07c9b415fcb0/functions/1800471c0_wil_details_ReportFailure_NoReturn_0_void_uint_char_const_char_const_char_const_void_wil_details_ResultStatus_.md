# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800471c0`
- end: `0x180047483`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `707`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180047490`

## callees

- `0x18000d2b0`
- `0x18000d4b0`
- `0x18000d590`
- `0x18000dba0`
- `0x18000dbf0`
- `0x1800471c0`
- `0x1801f7d30`
- `0x180242120`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180047415`
- `KERNEL32!OutputDebugStringW` at `0x180047415`
- `KERNEL32!GetCurrentThreadId` at `0x180047266`
- `KERNEL32!GetCurrentThreadId` at `0x180047266`
- `KERNEL32!IsDebuggerPresent` at `0x180047368`
- `KERNEL32!IsDebuggerPresent` at `0x180047368`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // si
  int IsDebuggerPresent; // edi
  int v12; // ebx
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v10 = g_pfnThrowPlatformException && wil::g_fResultThrowPlatformException;
  IsDebuggerPresent = 0;
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v21 = v13;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v12;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  v18 = (wil::g_fIsDebuggerPresent
      || (!wil::g_pfnIsDebuggerPresent
        ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
        : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16)),
          IsDebuggerPresent))
     && wil::g_fResultOutputDebugString
     && (v21 & 2) == 0;
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (wchar_t *)0x800, (__int64)&v20, v17);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0, v17);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v15);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v15);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x1800471c0  mov     [rsp-8+arg_18], rbx
0x1800471c5  push    rbp
0x1800471c6  push    rsi
0x1800471c7  push    rdi
0x1800471c8  push    r12
0x1800471ca  push    r13
0x1800471cc  push    r14
0x1800471ce  push    r15
0x1800471d0  lea     rbp, [rsp-13C0h]
0x1800471d8  mov     eax, 14C0h
0x1800471dd  call    _alloca_probe
0x1800471e2  sub     rsp, rax
0x1800471e5  mov     r12, r8
0x1800471e8  mov     r15d, edx
0x1800471eb  mov     r14, rcx
0x1800471ee  mov     r13, [rbp+13F0h+arg_28]
0x1800471f5  cmp     cs:g_pfnThrowPlatformException, 0
0x1800471fd  jz      short loc_18004720D
0x1800471ff  cmp     cs:?g_fResultThrowPlatformException@wil@@3_NA, 0; bool wil::g_fResultThrowPlatformException
0x180047206  jz      short loc_18004720D
0x180047208  mov     sil, 1
0x18004720b  jmp     short loc_180047210
0x18004720d  xor     sil, sil
0x180047210  xor     edi, edi
0x180047212  mov     [rbp+13F0h+OutputString], di
0x180047219  mov     [rbp+13F0h+var_1430], dil
0x18004721d  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180047224  mov     ecx, [rdx]; this
0x180047226  mov     [rsp+14F0h+var_14C8], ecx
0x18004722a  mov     eax, [rdx+4]
0x18004722d  mov     [rsp+14F0h+var_14C4], eax
0x180047231  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180047236  mov     ebx, eax
0x180047238  mov     dword ptr [rsp+14F0h+var_14D0], edi
0x18004723c  mov     ecx, edi
0x18004723e  mov     eax, 8
0x180047243  cmp     dword ptr [rdx+8], 1
0x180047247  cmovz   ecx, eax
0x18004724a  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18004724e  mov     ecx, 1
0x180047253  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18004725b  inc     ecx
0x18004725d  mov     [rsp+14F0h+var_14C0], ecx
0x180047261  mov     [rsp+14F0h+var_14B8], rdi
0x180047266  call    cs:__imp_GetCurrentThreadId
0x18004726c  mov     [rsp+14F0h+var_14B0], eax
0x180047270  mov     [rsp+14F0h+var_1498], r12
0x180047275  mov     [rsp+14F0h+var_1490], r15d
0x18004727a  mov     [rsp+14F0h+var_148C], ebx
0x18004727e  mov     [rsp+14F0h+var_14A8], rdi
0x180047283  mov     [rsp+14F0h+var_14A0], rdi
0x180047288  mov     [rbp+13F0h+var_1448], r13
0x18004728c  mov     [rbp+13F0h+var_1440], r14
0x180047290  mov     [rsp+14F0h+var_1488], rdi
0x180047295  xorps   xmm0, xmm0
0x180047298  xor     eax, eax
0x18004729a  movups  [rbp+13F0h+var_1468], xmm0
0x18004729e  mov     [rbp+13F0h+var_1458], rax
0x1800472a2  xorps   xmm1, xmm1
0x1800472a5  movups  [rsp+14F0h+var_1480], xmm1
0x1800472aa  mov     [rbp+13F0h+var_1470], rax
0x1800472ae  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800472b5  test    rax, rax
0x1800472b8  jz      short loc_1800472C6
0x1800472ba  call    cs:__guard_dispatch_icall_fptr
0x1800472c0  mov     [rbp+13F0h+var_1450], rax
0x1800472c4  jmp     short loc_1800472CA
0x1800472c6  mov     [rbp+13F0h+var_1450], rdi
0x1800472ca  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800472d1  test    rax, rax
0x1800472d4  jz      short loc_1800472E1
0x1800472d6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800472db  call    cs:__guard_dispatch_icall_fptr
0x1800472e1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800472e8  test    rax, rax
0x1800472eb  jz      short loc_180047302
0x1800472ed  mov     r8d, 400h
0x1800472f3  lea     rdx, [rbp+13F0h+var_1430]
0x1800472f7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800472fc  call    cs:__guard_dispatch_icall_fptr
0x180047302  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180047309  test    rax, rax
0x18004730c  jz      short loc_180047319
0x18004730e  lea     rcx, [rsp+14F0h+var_14D0]
0x180047313  call    cs:__guard_dispatch_icall_fptr
0x180047319  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180047320  test    rax, rax
0x180047323  jz      short loc_18004733C
0x180047325  test    sil, sil
0x180047328  jnz     short loc_18004733C
0x18004732a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18004732f  jnz     short loc_18004733C
0x180047331  lea     rcx, [rsp+14F0h+var_14D0]
0x180047336  call    cs:__guard_dispatch_icall_fptr
0x18004733c  cmp     [rsp+14F0h+var_14C8], edi
0x180047340  jl      short loc_180047348
0x180047342  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180047348  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18004734f  jnz     short loc_180047378
0x180047351  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180047358  test    rax, rax
0x18004735b  jz      short loc_180047368
0x18004735d  call    cs:__guard_dispatch_icall_fptr
0x180047363  movzx   edi, al
0x180047366  jmp     short loc_180047374
0x180047368  call    cs:__imp_IsDebuggerPresent
0x18004736e  test    eax, eax
0x180047370  setnz   dil
0x180047374  test    edi, edi
0x180047376  jz      short loc_18004738C
0x180047378  cmp     cs:?g_fResultOutputDebugString@wil@@3_NA, 0; bool wil::g_fResultOutputDebugString
0x18004737f  jz      short loc_18004738C
0x180047381  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180047386  jnz     short loc_18004738C
0x180047388  mov     bl, 1
0x18004738a  jmp     short loc_18004738E
0x18004738c  xor     bl, bl
0x18004738e  test    sil, sil
0x180047391  jnz     short loc_1800473BD
0x180047393  test    bl, bl
0x180047395  jnz     short loc_1800473BD
0x180047397  mov     rax, cs:g_pfnResultLoggingCallback
0x18004739e  test    rax, rax
0x1800473a1  jz      short loc_18004741B
0x1800473a3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x1800473a9  jnz     short loc_18004741B
0x1800473ab  xor     r8d, r8d
0x1800473ae  xor     edx, edx
0x1800473b0  lea     rcx, [rsp+14F0h+var_14D0]
0x1800473b5  call    cs:__guard_dispatch_icall_fptr
0x1800473bb  jmp     short loc_18004741B
0x1800473bd  mov     rax, cs:g_pfnResultLoggingCallback
0x1800473c4  test    rax, rax
0x1800473c7  jz      short loc_1800473EA
0x1800473c9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1800473d0  jnz     short loc_1800473EA
0x1800473d2  mov     r8d, 800h
0x1800473d8  lea     rdx, [rbp+13F0h+OutputString]
0x1800473df  lea     rcx, [rsp+14F0h+var_14D0]
0x1800473e4  call    cs:__guard_dispatch_icall_fptr
0x1800473ea  cmp     [rbp+13F0h+OutputString], 0
0x1800473f2  jnz     short loc_18004740A
0x1800473f4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800473f9  mov     edx, 800h; wchar_t *
0x1800473fe  lea     rcx, [rbp+13F0h+OutputString]; Buffer
0x180047405  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18004740a  test    bl, bl
0x18004740c  jz      short loc_18004741B
0x18004740e  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180047415  call    cs:__imp_OutputDebugStringW
0x18004741b  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180047420  jnz     short loc_18004742B
0x180047422  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x180047429  jz      short loc_18004743E
0x18004742b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180047432  test    rax, rax
0x180047435  jz      short loc_18004743E
0x180047437  call    cs:__guard_dispatch_icall_fptr
0x18004743d  nop
0x18004743e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180047443  jz      short loc_180047450
0x180047445  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18004744a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180047450  test    sil, sil
0x180047453  jz      short loc_18004746E
0x180047455  lea     rdx, [rbp+13F0h+OutputString]
0x18004745c  lea     rcx, [rsp+14F0h+var_14D0]
0x180047461  mov     rax, cs:g_pfnThrowPlatformException
0x180047468  call    cs:__guard_dispatch_icall_fptr
0x18004746e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180047473  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180047478  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18004747d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
