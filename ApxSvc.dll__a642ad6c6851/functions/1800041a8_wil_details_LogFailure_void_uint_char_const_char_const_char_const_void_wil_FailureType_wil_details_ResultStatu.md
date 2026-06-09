# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800041a8`
- end: `0x1800044a1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002968`

## callees

- `0x1800023ac`
- `0x180003844`
- `0x180003fe4`
- `0x1800041a8`
- `0x1800046ec`
- `0x180004710`
- `0x180004724`
- `0x180004740`
- `0x18000572c`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800042cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800042cb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800043ea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800043ea`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000445c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000445c`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x1800041a8  mov     [rsp+arg_10], rbx
0x1800041ad  mov     [rsp+arg_8], edx
0x1800041b1  mov     [rsp+arg_0], rcx
0x1800041b6  push    rbp
0x1800041b7  push    rsi
0x1800041b8  push    rdi
0x1800041b9  push    r12
0x1800041bb  push    r13
0x1800041bd  push    r14
0x1800041bf  push    r15
0x1800041c1  sub     rsp, 40h
0x1800041c5  mov     r12, r9
0x1800041c8  mov     r13, r8
0x1800041cb  mov     r10, rcx
0x1800041ce  xor     eax, eax
0x1800041d0  mov     rsi, [rsp+78h+lpOutputString]
0x1800041d8  mov     [rsi], ax
0x1800041db  mov     rax, [rsp+78h+arg_60]
0x1800041e3  mov     byte ptr [rax], 0
0x1800041e6  mov     r14, [rsp+78h+arg_38]
0x1800041ee  mov     edi, [r14]
0x1800041f1  mov     rbx, [rsp+78h+arg_78]
0x1800041f9  mov     [rbx+8], edi
0x1800041fc  mov     eax, [r14+4]
0x180004200  mov     [rbx+0Ch], eax
0x180004203  xor     ebp, ebp
0x180004205  mov     r15d, [rsp+78h+arg_30]
0x18000420d  mov     ecx, r15d
0x180004210  test    r15d, r15d
0x180004213  jz      short loc_18000427B
0x180004215  sub     ecx, 1
0x180004218  jz      short loc_180004272
0x18000421a  sub     ecx, 1
0x18000421d  jz      short loc_18000422D
0x18000421f  cmp     ecx, 1
0x180004222  jnz     short loc_180004284
0x180004224  mov     ecx, edi; this
0x180004226  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000422b  jmp     short loc_180004282
0x18000422d  test    edi, edi
0x18000422f  js      short loc_180004269
0x180004231  mov     edi, 8007029Ch
0x180004236  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000423a  mov     rax, [rsp+78h+arg_28]
0x180004242  mov     [rsp+78h+var_50], rax; __int64
0x180004247  mov     rax, [rsp+78h+arg_20]
0x18000424f  mov     [rsp+78h+var_58], rax; __int64
0x180004254  mov     rcx, r10; int
0x180004257  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000425c  mov     [rbx+8], edi
0x18000425f  mov     ecx, edi; this
0x180004261  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004266  mov     [rbx+0Ch], eax
0x180004269  mov     ecx, edi; this
0x18000426b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004270  jmp     short loc_180004282
0x180004272  mov     ecx, edi; this
0x180004274  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004279  jmp     short loc_180004282
0x18000427b  mov     ecx, edi; this
0x18000427d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004282  mov     ebp, eax
0x180004284  mov     [rbx], r15d
0x180004287  mov     eax, [rsp+78h+arg_70]
0x18000428e  mov     [rbx+4], eax
0x180004291  cmp     dword ptr [r14+8], 1
0x180004296  jnz     short loc_18000429E
0x180004298  or      eax, 8
0x18000429b  mov     [rbx+4], eax
0x18000429e  mov     eax, 1
0x1800042a3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800042ab  inc     eax
0x1800042ad  mov     [rbx+10h], eax
0x1800042b0  mov     rax, [rsp+78h+arg_40]
0x1800042b8  xor     edi, edi
0x1800042ba  test    rax, rax
0x1800042bd  jz      short loc_1800042C4
0x1800042bf  cmp     [rax], di
0x1800042c2  jnz     short loc_1800042C7
0x1800042c4  mov     rax, rdi
0x1800042c7  mov     [rbx+18h], rax
0x1800042cb  call    cs:__imp_GetCurrentThreadId
0x1800042d1  mov     [rbx+20h], eax
0x1800042d4  mov     [rbx+38h], r13
0x1800042d8  mov     eax, [rsp+78h+arg_8]
0x1800042df  mov     [rbx+40h], eax
0x1800042e2  mov     [rbx+44h], ebp
0x1800042e5  mov     rax, [rsp+78h+arg_20]
0x1800042ed  mov     [rbx+28h], rax
0x1800042f1  mov     [rbx+30h], r12
0x1800042f5  mov     rax, [rsp+78h+arg_28]
0x1800042fd  mov     [rbx+88h], rax
0x180004304  mov     rax, [rsp+78h+arg_0]
0x18000430c  mov     [rbx+90h], rax
0x180004313  mov     [rbx+48h], rdi
0x180004317  xorps   xmm0, xmm0
0x18000431a  xor     eax, eax
0x18000431c  movups  xmmword ptr [rbx+68h], xmm0
0x180004320  mov     [rbx+78h], rax
0x180004324  movups  xmmword ptr [rbx+50h], xmm0
0x180004328  mov     [rbx+60h], rax
0x18000432c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004333  test    rax, rax
0x180004336  jz      short loc_18000433F
0x180004338  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000433d  jmp     short loc_180004342
0x18000433f  mov     rax, rdi
0x180004342  mov     [rbx+80h], rax
0x180004349  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004350  test    rax, rax
0x180004353  jz      short loc_18000435D
0x180004355  mov     rcx, rbx
0x180004358  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000435d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004364  test    rax, rax
0x180004367  jz      short loc_18000437F
0x180004369  mov     r8d, 400h
0x18000436f  mov     rdx, [rsp+78h+arg_60]
0x180004377  mov     rcx, rbx
0x18000437a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000437f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004386  test    rax, rax
0x180004389  jz      short loc_180004393
0x18000438b  mov     rcx, rbx
0x18000438e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004393  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000439a  test    rax, rax
0x18000439d  jz      short loc_1800043AD
0x18000439f  test    byte ptr [rbx+4], 2
0x1800043a3  jnz     short loc_1800043AD
0x1800043a5  mov     rcx, rbx
0x1800043a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043ad  cmp     [rbx+8], edi
0x1800043b0  jl      short loc_1800043CC
0x1800043b2  cmp     r15d, 3
0x1800043b6  jnz     loc_18000449B
0x1800043bc  mov     ecx, 8000FFFFh; this
0x1800043c1  mov     [rbx+8], ecx
0x1800043c4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800043c9  mov     [rbx+0Ch], eax
0x1800043cc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800043d3  jnz     short loc_1800043F4
0x1800043d5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800043dc  test    rax, rax
0x1800043df  jz      short loc_1800043EA
0x1800043e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043e6  test    al, al
0x1800043e8  jmp     short loc_1800043F2
0x1800043ea  call    cs:__imp_IsDebuggerPresent
0x1800043f0  test    eax, eax
0x1800043f2  jz      short loc_1800043FA
0x1800043f4  test    byte ptr [rbx+4], 2
0x1800043f8  jz      short loc_18000441E
0x1800043fa  mov     rax, cs:g_pfnResultLoggingCallback
0x180004401  test    rax, rax
0x180004404  jz      short loc_180004462
0x180004406  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000440d  jnz     short loc_180004462
0x18000440f  xor     r8d, r8d
0x180004412  xor     edx, edx
0x180004414  mov     rcx, rbx
0x180004417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000441c  jmp     short loc_180004462
0x18000441e  mov     ebp, 800h
0x180004423  mov     rax, cs:g_pfnResultLoggingCallback
0x18000442a  test    rax, rax
0x18000442d  jz      short loc_180004446
0x18000442f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004436  jnz     short loc_180004446
0x180004438  mov     r8d, ebp
0x18000443b  mov     rdx, rsi
0x18000443e  mov     rcx, rbx
0x180004441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004446  cmp     [rsi], di
0x180004449  jnz     short loc_180004459
0x18000444b  mov     r8, rbx; unsigned __int64
0x18000444e  mov     rdx, rbp; unsigned __int16 *
0x180004451  mov     rcx, rsi; this
0x180004454  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004459  mov     rcx, rsi; lpOutputString
0x18000445c  call    cs:__imp_OutputDebugStringW
0x180004462  test    byte ptr [rbx+4], 4
0x180004466  jnz     short loc_180004471
0x180004468  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000446f  jz      short loc_180004483
0x180004471  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004478  test    rax, rax
0x18000447b  jz      short loc_180004483
0x18000447d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004482  nop
0x180004483  mov     rbx, [rsp+78h+arg_10]
0x18000448b  add     rsp, 40h
0x18000448f  pop     r15
0x180004491  pop     r14
0x180004493  pop     r13
0x180004495  pop     r12
0x180004497  pop     rdi
0x180004498  pop     rsi
0x180004499  pop     rbp
0x18000449a  retn
0x18000449b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
