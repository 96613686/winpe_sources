# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004068`
- end: `0x140004361`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002778`

## callees

- `0x1400021bc`
- `0x140003704`
- `0x140003ea4`
- `0x140004068`
- `0x1400045ac`
- `0x1400045d0`
- `0x1400045e4`
- `0x140004600`
- `0x1400055dc`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000418b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000418b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000431c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000431c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400042aa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400042aa`

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
0x140004068  mov     [rsp+arg_10], rbx
0x14000406d  mov     [rsp+arg_8], edx
0x140004071  mov     [rsp+arg_0], rcx
0x140004076  push    rbp
0x140004077  push    rsi
0x140004078  push    rdi
0x140004079  push    r12
0x14000407b  push    r13
0x14000407d  push    r14
0x14000407f  push    r15
0x140004081  sub     rsp, 40h
0x140004085  mov     r12, r9
0x140004088  mov     r13, r8
0x14000408b  mov     r10, rcx
0x14000408e  xor     eax, eax
0x140004090  mov     rsi, [rsp+78h+lpOutputString]
0x140004098  mov     [rsi], ax
0x14000409b  mov     rax, [rsp+78h+arg_60]
0x1400040a3  mov     byte ptr [rax], 0
0x1400040a6  mov     r14, [rsp+78h+arg_38]
0x1400040ae  mov     edi, [r14]
0x1400040b1  mov     rbx, [rsp+78h+arg_78]
0x1400040b9  mov     [rbx+8], edi
0x1400040bc  mov     eax, [r14+4]
0x1400040c0  mov     [rbx+0Ch], eax
0x1400040c3  xor     ebp, ebp
0x1400040c5  mov     r15d, [rsp+78h+arg_30]
0x1400040cd  mov     ecx, r15d
0x1400040d0  test    r15d, r15d
0x1400040d3  jz      short loc_14000413B
0x1400040d5  sub     ecx, 1
0x1400040d8  jz      short loc_140004132
0x1400040da  sub     ecx, 1
0x1400040dd  jz      short loc_1400040ED
0x1400040df  cmp     ecx, 1
0x1400040e2  jnz     short loc_140004144
0x1400040e4  mov     ecx, edi; this
0x1400040e6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400040eb  jmp     short loc_140004142
0x1400040ed  test    edi, edi
0x1400040ef  js      short loc_140004129
0x1400040f1  mov     edi, 8007029Ch
0x1400040f6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400040fa  mov     rax, [rsp+78h+arg_28]
0x140004102  mov     [rsp+78h+var_50], rax; __int64
0x140004107  mov     rax, [rsp+78h+arg_20]
0x14000410f  mov     [rsp+78h+var_58], rax; __int64
0x140004114  mov     rcx, r10; int
0x140004117  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000411c  mov     [rbx+8], edi
0x14000411f  mov     ecx, edi; this
0x140004121  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004126  mov     [rbx+0Ch], eax
0x140004129  mov     ecx, edi; this
0x14000412b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004130  jmp     short loc_140004142
0x140004132  mov     ecx, edi; this
0x140004134  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004139  jmp     short loc_140004142
0x14000413b  mov     ecx, edi; this
0x14000413d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004142  mov     ebp, eax
0x140004144  mov     [rbx], r15d
0x140004147  mov     eax, [rsp+78h+arg_70]
0x14000414e  mov     [rbx+4], eax
0x140004151  cmp     dword ptr [r14+8], 1
0x140004156  jnz     short loc_14000415E
0x140004158  or      eax, 8
0x14000415b  mov     [rbx+4], eax
0x14000415e  mov     eax, 1
0x140004163  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000416b  inc     eax
0x14000416d  mov     [rbx+10h], eax
0x140004170  mov     rax, [rsp+78h+arg_40]
0x140004178  xor     edi, edi
0x14000417a  test    rax, rax
0x14000417d  jz      short loc_140004184
0x14000417f  cmp     [rax], di
0x140004182  jnz     short loc_140004187
0x140004184  mov     rax, rdi
0x140004187  mov     [rbx+18h], rax
0x14000418b  call    cs:__imp_GetCurrentThreadId
0x140004191  mov     [rbx+20h], eax
0x140004194  mov     [rbx+38h], r13
0x140004198  mov     eax, [rsp+78h+arg_8]
0x14000419f  mov     [rbx+40h], eax
0x1400041a2  mov     [rbx+44h], ebp
0x1400041a5  mov     rax, [rsp+78h+arg_20]
0x1400041ad  mov     [rbx+28h], rax
0x1400041b1  mov     [rbx+30h], r12
0x1400041b5  mov     rax, [rsp+78h+arg_28]
0x1400041bd  mov     [rbx+88h], rax
0x1400041c4  mov     rax, [rsp+78h+arg_0]
0x1400041cc  mov     [rbx+90h], rax
0x1400041d3  mov     [rbx+48h], rdi
0x1400041d7  xorps   xmm0, xmm0
0x1400041da  xor     eax, eax
0x1400041dc  movups  xmmword ptr [rbx+68h], xmm0
0x1400041e0  mov     [rbx+78h], rax
0x1400041e4  movups  xmmword ptr [rbx+50h], xmm0
0x1400041e8  mov     [rbx+60h], rax
0x1400041ec  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400041f3  test    rax, rax
0x1400041f6  jz      short loc_1400041FF
0x1400041f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041fd  jmp     short loc_140004202
0x1400041ff  mov     rax, rdi
0x140004202  mov     [rbx+80h], rax
0x140004209  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004210  test    rax, rax
0x140004213  jz      short loc_14000421D
0x140004215  mov     rcx, rbx
0x140004218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000421d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004224  test    rax, rax
0x140004227  jz      short loc_14000423F
0x140004229  mov     r8d, 400h
0x14000422f  mov     rdx, [rsp+78h+arg_60]
0x140004237  mov     rcx, rbx
0x14000423a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000423f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004246  test    rax, rax
0x140004249  jz      short loc_140004253
0x14000424b  mov     rcx, rbx
0x14000424e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004253  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000425a  test    rax, rax
0x14000425d  jz      short loc_14000426D
0x14000425f  test    byte ptr [rbx+4], 2
0x140004263  jnz     short loc_14000426D
0x140004265  mov     rcx, rbx
0x140004268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000426d  cmp     [rbx+8], edi
0x140004270  jl      short loc_14000428C
0x140004272  cmp     r15d, 3
0x140004276  jnz     loc_14000435B
0x14000427c  mov     ecx, 8000FFFFh; this
0x140004281  mov     [rbx+8], ecx
0x140004284  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004289  mov     [rbx+0Ch], eax
0x14000428c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140004293  jnz     short loc_1400042B4
0x140004295  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000429c  test    rax, rax
0x14000429f  jz      short loc_1400042AA
0x1400042a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042a6  test    al, al
0x1400042a8  jmp     short loc_1400042B2
0x1400042aa  call    cs:__imp_IsDebuggerPresent
0x1400042b0  test    eax, eax
0x1400042b2  jz      short loc_1400042BA
0x1400042b4  test    byte ptr [rbx+4], 2
0x1400042b8  jz      short loc_1400042DE
0x1400042ba  mov     rax, cs:g_pfnResultLoggingCallback
0x1400042c1  test    rax, rax
0x1400042c4  jz      short loc_140004322
0x1400042c6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400042cd  jnz     short loc_140004322
0x1400042cf  xor     r8d, r8d
0x1400042d2  xor     edx, edx
0x1400042d4  mov     rcx, rbx
0x1400042d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042dc  jmp     short loc_140004322
0x1400042de  mov     ebp, 800h
0x1400042e3  mov     rax, cs:g_pfnResultLoggingCallback
0x1400042ea  test    rax, rax
0x1400042ed  jz      short loc_140004306
0x1400042ef  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400042f6  jnz     short loc_140004306
0x1400042f8  mov     r8d, ebp
0x1400042fb  mov     rdx, rsi
0x1400042fe  mov     rcx, rbx
0x140004301  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004306  cmp     [rsi], di
0x140004309  jnz     short loc_140004319
0x14000430b  mov     r8, rbx; unsigned __int64
0x14000430e  mov     rdx, rbp; unsigned __int16 *
0x140004311  mov     rcx, rsi; this
0x140004314  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004319  mov     rcx, rsi; lpOutputString
0x14000431c  call    cs:__imp_OutputDebugStringW
0x140004322  test    byte ptr [rbx+4], 4
0x140004326  jnz     short loc_140004331
0x140004328  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000432f  jz      short loc_140004343
0x140004331  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004338  test    rax, rax
0x14000433b  jz      short loc_140004343
0x14000433d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004342  nop
0x140004343  mov     rbx, [rsp+78h+arg_10]
0x14000434b  add     rsp, 40h
0x14000434f  pop     r15
0x140004351  pop     r14
0x140004353  pop     r13
0x140004355  pop     r12
0x140004357  pop     rdi
0x140004358  pop     rsi
0x140004359  pop     rbp
0x14000435a  retn
0x14000435b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
