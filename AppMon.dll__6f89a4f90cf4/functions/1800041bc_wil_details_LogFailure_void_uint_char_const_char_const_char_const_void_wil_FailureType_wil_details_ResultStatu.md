# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800041bc`
- end: `0x1800044b1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180002b08`
- `0x180002bb8`
- `0x180002cac`
- `0x180006064`

## callees

- `0x180002a58`
- `0x180003824`
- `0x180003ff8`
- `0x1800041bc`
- `0x1800048a4`
- `0x1800048c0`
- `0x1800048d4`
- `0x1800048f0`
- `0x18000560c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800042df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800042df`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004472`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004472`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004400`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004400`

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
0x1800041bc  mov     [rsp+arg_10], rbx
0x1800041c1  mov     [rsp+arg_8], edx
0x1800041c5  mov     [rsp+arg_0], rcx
0x1800041ca  push    rbp
0x1800041cb  push    rsi
0x1800041cc  push    rdi
0x1800041cd  push    r12
0x1800041cf  push    r13
0x1800041d1  push    r14
0x1800041d3  push    r15
0x1800041d5  sub     rsp, 40h
0x1800041d9  mov     r12, r9
0x1800041dc  mov     r13, r8
0x1800041df  mov     r10, rcx
0x1800041e2  xor     eax, eax
0x1800041e4  mov     rsi, [rsp+78h+lpOutputString]
0x1800041ec  mov     [rsi], ax
0x1800041ef  mov     rax, [rsp+78h+arg_60]
0x1800041f7  mov     byte ptr [rax], 0
0x1800041fa  mov     r14, [rsp+78h+arg_38]
0x180004202  mov     edi, [r14]
0x180004205  mov     rbx, [rsp+78h+arg_78]
0x18000420d  mov     [rbx+8], edi
0x180004210  mov     eax, [r14+4]
0x180004214  mov     [rbx+0Ch], eax
0x180004217  xor     ebp, ebp
0x180004219  mov     r15d, [rsp+78h+arg_30]
0x180004221  mov     ecx, r15d
0x180004224  test    r15d, r15d
0x180004227  jz      short loc_18000428F
0x180004229  sub     ecx, 1
0x18000422c  jz      short loc_180004286
0x18000422e  sub     ecx, 1
0x180004231  jz      short loc_180004241
0x180004233  cmp     ecx, 1
0x180004236  jnz     short loc_180004298
0x180004238  mov     ecx, edi; this
0x18000423a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000423f  jmp     short loc_180004296
0x180004241  test    edi, edi
0x180004243  js      short loc_18000427D
0x180004245  mov     edi, 8007029Ch
0x18000424a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000424e  mov     rax, [rsp+78h+arg_28]
0x180004256  mov     [rsp+78h+var_50], rax; __int64
0x18000425b  mov     rax, [rsp+78h+arg_20]
0x180004263  mov     [rsp+78h+var_58], rax; __int64
0x180004268  mov     rcx, r10; int
0x18000426b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004270  mov     [rbx+8], edi
0x180004273  mov     ecx, edi; this
0x180004275  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000427a  mov     [rbx+0Ch], eax
0x18000427d  mov     ecx, edi; this
0x18000427f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004284  jmp     short loc_180004296
0x180004286  mov     ecx, edi; this
0x180004288  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000428d  jmp     short loc_180004296
0x18000428f  mov     ecx, edi; this
0x180004291  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004296  mov     ebp, eax
0x180004298  mov     [rbx], r15d
0x18000429b  mov     eax, [rsp+78h+arg_70]
0x1800042a2  mov     [rbx+4], eax
0x1800042a5  cmp     dword ptr [r14+8], 1
0x1800042aa  jnz     short loc_1800042B2
0x1800042ac  or      eax, 8
0x1800042af  mov     [rbx+4], eax
0x1800042b2  mov     eax, 1
0x1800042b7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800042bf  inc     eax
0x1800042c1  mov     [rbx+10h], eax
0x1800042c4  mov     rax, [rsp+78h+arg_40]
0x1800042cc  xor     edi, edi
0x1800042ce  test    rax, rax
0x1800042d1  jz      short loc_1800042D8
0x1800042d3  cmp     [rax], di
0x1800042d6  jnz     short loc_1800042DB
0x1800042d8  mov     rax, rdi
0x1800042db  mov     [rbx+18h], rax
0x1800042df  call    cs:__imp_GetCurrentThreadId
0x1800042e5  mov     [rbx+20h], eax
0x1800042e8  mov     [rbx+38h], r13
0x1800042ec  mov     eax, [rsp+78h+arg_8]
0x1800042f3  mov     [rbx+40h], eax
0x1800042f6  mov     [rbx+44h], ebp
0x1800042f9  mov     rax, [rsp+78h+arg_20]
0x180004301  mov     [rbx+28h], rax
0x180004305  mov     [rbx+30h], r12
0x180004309  mov     rax, [rsp+78h+arg_28]
0x180004311  mov     [rbx+88h], rax
0x180004318  mov     rax, [rsp+78h+arg_0]
0x180004320  mov     [rbx+90h], rax
0x180004327  mov     [rbx+48h], rdi
0x18000432b  xorps   xmm0, xmm0
0x18000432e  xor     eax, eax
0x180004330  movups  xmmword ptr [rbx+68h], xmm0
0x180004334  mov     [rbx+78h], rax
0x180004338  movups  xmmword ptr [rbx+50h], xmm0
0x18000433c  mov     [rbx+60h], rax
0x180004340  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004347  test    rax, rax
0x18000434a  jz      short loc_180004353
0x18000434c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004351  jmp     short loc_180004356
0x180004353  mov     rax, rdi
0x180004356  mov     [rbx+80h], rax
0x18000435d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004364  test    rax, rax
0x180004367  jz      short loc_180004371
0x180004369  mov     rcx, rbx
0x18000436c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004371  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004378  test    rax, rax
0x18000437b  jz      short loc_180004393
0x18000437d  mov     r8d, 400h
0x180004383  mov     rdx, [rsp+78h+arg_60]
0x18000438b  mov     rcx, rbx
0x18000438e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004393  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000439a  test    rax, rax
0x18000439d  jz      short loc_1800043A7
0x18000439f  mov     rcx, rbx
0x1800043a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043a7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800043ae  test    rax, rax
0x1800043b1  jz      short loc_1800043C1
0x1800043b3  test    byte ptr [rbx+4], 2
0x1800043b7  jnz     short loc_1800043C1
0x1800043b9  mov     rcx, rbx
0x1800043bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043c1  cmp     [rbx+8], edi
0x1800043c4  jl      short loc_1800043E2
0x1800043c6  cmp     r15d, 3
0x1800043ca  jz      short loc_1800043D2
0x1800043cc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800043d2  mov     ecx, 8000FFFFh; this
0x1800043d7  mov     [rbx+8], ecx
0x1800043da  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800043df  mov     [rbx+0Ch], eax
0x1800043e2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800043e9  jnz     short loc_18000440A
0x1800043eb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800043f2  test    rax, rax
0x1800043f5  jz      short loc_180004400
0x1800043f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043fc  test    al, al
0x1800043fe  jmp     short loc_180004408
0x180004400  call    cs:__imp_IsDebuggerPresent
0x180004406  test    eax, eax
0x180004408  jz      short loc_180004410
0x18000440a  test    byte ptr [rbx+4], 2
0x18000440e  jz      short loc_180004434
0x180004410  mov     rax, cs:g_pfnResultLoggingCallback
0x180004417  test    rax, rax
0x18000441a  jz      short loc_180004478
0x18000441c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004423  jnz     short loc_180004478
0x180004425  xor     r8d, r8d
0x180004428  xor     edx, edx
0x18000442a  mov     rcx, rbx
0x18000442d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004432  jmp     short loc_180004478
0x180004434  mov     ebp, 800h
0x180004439  mov     rax, cs:g_pfnResultLoggingCallback
0x180004440  test    rax, rax
0x180004443  jz      short loc_18000445C
0x180004445  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000444c  jnz     short loc_18000445C
0x18000444e  mov     r8d, ebp
0x180004451  mov     rdx, rsi
0x180004454  mov     rcx, rbx
0x180004457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000445c  cmp     [rsi], di
0x18000445f  jnz     short loc_18000446F
0x180004461  mov     r8, rbx; unsigned __int64
0x180004464  mov     rdx, rbp; unsigned __int16 *
0x180004467  mov     rcx, rsi; this
0x18000446a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000446f  mov     rcx, rsi; lpOutputString
0x180004472  call    cs:__imp_OutputDebugStringW
0x180004478  test    byte ptr [rbx+4], 4
0x18000447c  jnz     short loc_180004487
0x18000447e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004485  jz      short loc_180004499
0x180004487  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000448e  test    rax, rax
0x180004491  jz      short loc_180004499
0x180004493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004498  nop
0x180004499  mov     rbx, [rsp+78h+arg_10]
0x1800044a1  add     rsp, 40h
0x1800044a5  pop     r15
0x1800044a7  pop     r14
0x1800044a9  pop     r13
0x1800044ab  pop     r12
0x1800044ad  pop     rdi
0x1800044ae  pop     rsi
0x1800044af  pop     rbp
0x1800044b0  retn
```
