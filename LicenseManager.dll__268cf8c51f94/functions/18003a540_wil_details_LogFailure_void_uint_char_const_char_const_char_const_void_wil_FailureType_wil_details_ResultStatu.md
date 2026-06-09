# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18003a540`
- end: `0x18003a839`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18003a234`
- `0x18003a338`
- `0x18003a434`
- `0x180069268`

## callees

- `0x18002fb00`
- `0x18003a540`
- `0x1800426a0`
- `0x1800433b8`
- `0x180044a60`
- `0x1800696f8`
- `0x180082bc8`
- `0x180083330`
- `0x180083710`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a667`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003a667`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003a7fa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003a7fa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003a788`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003a788`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int *a8,
        _WORD *a9,
        __int64 a10,
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v19 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v19 = v20;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v19;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a16 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a16, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a16);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x18003a540  mov     [rsp+arg_10], rbx
0x18003a545  mov     [rsp+arg_8], edx
0x18003a549  mov     [rsp+arg_0], rcx
0x18003a54e  push    rbp
0x18003a54f  push    rsi
0x18003a550  push    rdi
0x18003a551  push    r12
0x18003a553  push    r13
0x18003a555  push    r14
0x18003a557  push    r15
0x18003a559  sub     rsp, 40h
0x18003a55d  mov     r12, r9
0x18003a560  mov     r13, r8
0x18003a563  mov     r10, rcx
0x18003a566  xor     eax, eax
0x18003a568  mov     rsi, [rsp+78h+lpOutputString]
0x18003a570  mov     [rsi], ax
0x18003a573  mov     rax, [rsp+78h+arg_60]
0x18003a57b  mov     byte ptr [rax], 0
0x18003a57e  mov     r14, [rsp+78h+arg_38]
0x18003a586  mov     edi, [r14]
0x18003a589  mov     rbx, [rsp+78h+arg_78]
0x18003a591  mov     [rbx+8], edi
0x18003a594  mov     eax, [r14+4]
0x18003a598  mov     [rbx+0Ch], eax
0x18003a59b  xor     ebp, ebp
0x18003a59d  mov     r15d, [rsp+78h+arg_30]
0x18003a5a5  mov     ecx, r15d
0x18003a5a8  test    r15d, r15d
0x18003a5ab  jz      short loc_18003A617
0x18003a5ad  sub     ecx, 1
0x18003a5b0  jz      short loc_18003A60E
0x18003a5b2  sub     ecx, 1
0x18003a5b5  jz      short loc_18003A5C5
0x18003a5b7  cmp     ecx, 1
0x18003a5ba  jnz     short loc_18003A620
0x18003a5bc  mov     ecx, edi; this
0x18003a5be  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003a5c3  jmp     short loc_18003A61E
0x18003a5c5  test    edi, edi
0x18003a5c7  js      short loc_18003A605
0x18003a5c9  mov     [rsp+78h+var_40], ebp
0x18003a5cd  mov     edi, 8007029Ch
0x18003a5d2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003a5d6  mov     rax, [rsp+78h+arg_28]
0x18003a5de  mov     [rsp+78h+var_50], rax; __int64
0x18003a5e3  mov     rax, [rsp+78h+arg_20]
0x18003a5eb  mov     [rsp+78h+var_58], rax; __int64
0x18003a5f0  mov     rcx, r10; int
0x18003a5f3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18003a5f8  mov     [rbx+8], edi
0x18003a5fb  mov     ecx, edi; this
0x18003a5fd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003a602  mov     [rbx+0Ch], eax
0x18003a605  mov     ecx, edi; this
0x18003a607  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18003a60c  jmp     short loc_18003A61E
0x18003a60e  mov     ecx, edi; this
0x18003a610  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003a615  jmp     short loc_18003A61E
0x18003a617  mov     ecx, edi; this
0x18003a619  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18003a61e  mov     ebp, eax
0x18003a620  mov     [rbx], r15d
0x18003a623  mov     eax, [rsp+78h+arg_70]
0x18003a62a  mov     [rbx+4], eax
0x18003a62d  cmp     dword ptr [r14+8], 1
0x18003a632  jnz     short loc_18003A63A
0x18003a634  or      eax, 8
0x18003a637  mov     [rbx+4], eax
0x18003a63a  mov     eax, 1
0x18003a63f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003a647  inc     eax
0x18003a649  mov     [rbx+10h], eax
0x18003a64c  mov     rax, [rsp+78h+arg_40]
0x18003a654  xor     edi, edi
0x18003a656  test    rax, rax
0x18003a659  jz      short loc_18003A660
0x18003a65b  cmp     [rax], di
0x18003a65e  jnz     short loc_18003A663
0x18003a660  mov     rax, rdi
0x18003a663  mov     [rbx+18h], rax
0x18003a667  call    cs:__imp_GetCurrentThreadId
0x18003a66d  mov     [rbx+20h], eax
0x18003a670  mov     [rbx+38h], r13
0x18003a674  mov     eax, [rsp+78h+arg_8]
0x18003a67b  mov     [rbx+40h], eax
0x18003a67e  mov     [rbx+44h], ebp
0x18003a681  mov     rax, [rsp+78h+arg_20]
0x18003a689  mov     [rbx+28h], rax
0x18003a68d  mov     [rbx+30h], r12
0x18003a691  mov     rax, [rsp+78h+arg_28]
0x18003a699  mov     [rbx+88h], rax
0x18003a6a0  mov     rax, [rsp+78h+arg_0]
0x18003a6a8  mov     [rbx+90h], rax
0x18003a6af  mov     [rbx+48h], rdi
0x18003a6b3  xorps   xmm0, xmm0
0x18003a6b6  xor     eax, eax
0x18003a6b8  movups  xmmword ptr [rbx+68h], xmm0
0x18003a6bc  mov     [rbx+78h], rax
0x18003a6c0  movups  xmmword ptr [rbx+50h], xmm0
0x18003a6c4  mov     [rbx+60h], rax
0x18003a6c8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003a6cf  test    rax, rax
0x18003a6d2  jz      short loc_18003A6DB
0x18003a6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6d9  jmp     short loc_18003A6DE
0x18003a6db  mov     rax, rdi
0x18003a6de  mov     [rbx+80h], rax
0x18003a6e5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003a6ec  test    rax, rax
0x18003a6ef  jz      short loc_18003A6F9
0x18003a6f1  mov     rcx, rbx
0x18003a6f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a6f9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003a700  test    rax, rax
0x18003a703  jz      short loc_18003A71B
0x18003a705  mov     r8d, 400h
0x18003a70b  mov     rdx, [rsp+78h+arg_60]
0x18003a713  mov     rcx, rbx
0x18003a716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a71b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003a722  test    rax, rax
0x18003a725  jz      short loc_18003A72F
0x18003a727  mov     rcx, rbx
0x18003a72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a72f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003a736  test    rax, rax
0x18003a739  jz      short loc_18003A749
0x18003a73b  test    byte ptr [rbx+4], 2
0x18003a73f  jnz     short loc_18003A749
0x18003a741  mov     rcx, rbx
0x18003a744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a749  cmp     [rbx+8], edi
0x18003a74c  jl      short loc_18003A76A
0x18003a74e  cmp     r15d, 3
0x18003a752  jz      short loc_18003A75A
0x18003a754  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18003a75a  mov     ecx, 8000FFFFh; this
0x18003a75f  mov     [rbx+8], ecx
0x18003a762  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003a767  mov     [rbx+0Ch], eax
0x18003a76a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18003a771  jnz     short loc_18003A792
0x18003a773  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003a77a  test    rax, rax
0x18003a77d  jz      short loc_18003A788
0x18003a77f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a784  test    al, al
0x18003a786  jmp     short loc_18003A790
0x18003a788  call    cs:__imp_IsDebuggerPresent
0x18003a78e  test    eax, eax
0x18003a790  jz      short loc_18003A798
0x18003a792  test    byte ptr [rbx+4], 2
0x18003a796  jz      short loc_18003A7BC
0x18003a798  mov     rax, cs:g_pfnResultLoggingCallback
0x18003a79f  test    rax, rax
0x18003a7a2  jz      short loc_18003A800
0x18003a7a4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003a7ab  jnz     short loc_18003A800
0x18003a7ad  xor     r8d, r8d
0x18003a7b0  xor     edx, edx
0x18003a7b2  mov     rcx, rbx
0x18003a7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a7ba  jmp     short loc_18003A800
0x18003a7bc  mov     ebp, 800h
0x18003a7c1  mov     rax, cs:g_pfnResultLoggingCallback
0x18003a7c8  test    rax, rax
0x18003a7cb  jz      short loc_18003A7E4
0x18003a7cd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003a7d4  jnz     short loc_18003A7E4
0x18003a7d6  mov     r8d, ebp
0x18003a7d9  mov     rdx, rsi
0x18003a7dc  mov     rcx, rbx
0x18003a7df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a7e4  cmp     [rsi], di
0x18003a7e7  jnz     short loc_18003A7F7
0x18003a7e9  mov     r8, rbx; unsigned __int64
0x18003a7ec  mov     rdx, rbp; unsigned __int16 *
0x18003a7ef  mov     rcx, rsi; this
0x18003a7f2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003a7f7  mov     rcx, rsi; lpOutputString
0x18003a7fa  call    cs:__imp_OutputDebugStringW
0x18003a800  test    byte ptr [rbx+4], 4
0x18003a804  jnz     short loc_18003A80F
0x18003a806  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18003a80d  jz      short loc_18003A821
0x18003a80f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003a816  test    rax, rax
0x18003a819  jz      short loc_18003A821
0x18003a81b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a820  nop
0x18003a821  mov     rbx, [rsp+78h+arg_10]
0x18003a829  add     rsp, 40h
0x18003a82d  pop     r15
0x18003a82f  pop     r14
0x18003a831  pop     r13
0x18003a833  pop     r12
0x18003a835  pop     rdi
0x18003a836  pop     rsi
0x18003a837  pop     rbp
0x18003a838  retn
```
