# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140005524`
- end: `0x14000581c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400030a0`
- `0x1400033ec`

## callees

- `0x140002fe0`
- `0x1400048e4`
- `0x140005144`
- `0x140005524`
- `0x140006344`
- `0x140006360`
- `0x1400064b0`
- `0x1400064cc`
- `0x140007d28`
- `0x140047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005647`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005647`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400057d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400057d8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005766`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005766`

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
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x140005524  mov     [rsp+arg_10], rbx
0x140005529  mov     [rsp+arg_8], edx
0x14000552d  mov     [rsp+arg_0], rcx
0x140005532  push    rbp
0x140005533  push    rsi
0x140005534  push    rdi
0x140005535  push    r12
0x140005537  push    r13
0x140005539  push    r14
0x14000553b  push    r15
0x14000553d  sub     rsp, 40h
0x140005541  mov     r14, [rsp+78h+arg_38]
0x140005549  xor     eax, eax
0x14000554b  mov     rbx, [rsp+78h+arg_78]
0x140005553  xor     ebp, ebp
0x140005555  mov     r15d, [rsp+78h+arg_30]
0x14000555d  mov     r10, rcx
0x140005560  mov     rsi, [rsp+78h+lpOutputString]
0x140005568  mov     r12, r9
0x14000556b  mov     r13, r8
0x14000556e  mov     ecx, r15d
0x140005571  mov     [rsi], ax
0x140005574  mov     rax, [rsp+78h+arg_60]
0x14000557c  mov     byte ptr [rax], 0
0x14000557f  mov     edi, [r14]
0x140005582  mov     [rbx+8], edi
0x140005585  mov     eax, [r14+4]
0x140005589  mov     [rbx+0Ch], eax
0x14000558c  test    r15d, r15d
0x14000558f  jz      short loc_1400055F7
0x140005591  sub     ecx, 1
0x140005594  jz      short loc_1400055EE
0x140005596  sub     ecx, 1
0x140005599  jz      short loc_1400055A9
0x14000559b  cmp     ecx, 1
0x14000559e  jnz     short loc_140005600
0x1400055a0  mov     ecx, edi; this
0x1400055a2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400055a7  jmp     short loc_1400055FE
0x1400055a9  test    edi, edi
0x1400055ab  js      short loc_1400055E5
0x1400055ad  mov     rax, [rsp+78h+arg_28]
0x1400055b5  mov     edi, 8007029Ch
0x1400055ba  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400055be  mov     rcx, r10; int
0x1400055c1  mov     [rsp+78h+var_50], rax; __int64
0x1400055c6  mov     rax, [rsp+78h+arg_20]
0x1400055ce  mov     [rsp+78h+var_58], rax; __int64
0x1400055d3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400055d8  mov     ecx, edi; this
0x1400055da  mov     [rbx+8], edi
0x1400055dd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400055e2  mov     [rbx+0Ch], eax
0x1400055e5  mov     ecx, edi; this
0x1400055e7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400055ec  jmp     short loc_1400055FE
0x1400055ee  mov     ecx, edi; this
0x1400055f0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400055f5  jmp     short loc_1400055FE
0x1400055f7  mov     ecx, edi; this
0x1400055f9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400055fe  mov     ebp, eax
0x140005600  mov     eax, [rsp+78h+arg_70]
0x140005607  mov     [rbx+4], eax
0x14000560a  mov     [rbx], r15d
0x14000560d  cmp     dword ptr [r14+8], 1
0x140005612  jnz     short loc_14000561A
0x140005614  or      eax, 8
0x140005617  mov     [rbx+4], eax
0x14000561a  mov     eax, 1
0x14000561f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140005627  inc     eax
0x140005629  xor     edi, edi
0x14000562b  mov     [rbx+10h], eax
0x14000562e  mov     rax, [rsp+78h+arg_40]
0x140005636  test    rax, rax
0x140005639  jz      short loc_140005640
0x14000563b  cmp     [rax], di
0x14000563e  jnz     short loc_140005643
0x140005640  mov     rax, rdi
0x140005643  mov     [rbx+18h], rax
0x140005647  call    cs:__imp_GetCurrentThreadId
0x14000564d  mov     [rbx+38h], r13
0x140005651  xorps   xmm0, xmm0
0x140005654  mov     [rbx+20h], eax
0x140005657  mov     eax, [rsp+78h+arg_8]
0x14000565e  mov     [rbx+40h], eax
0x140005661  mov     rax, [rsp+78h+arg_20]
0x140005669  mov     [rbx+28h], rax
0x14000566d  mov     rax, [rsp+78h+arg_28]
0x140005675  mov     [rbx+88h], rax
0x14000567c  mov     rax, [rsp+78h+arg_0]
0x140005684  mov     [rbx+90h], rax
0x14000568b  xor     eax, eax
0x14000568d  mov     [rbx+44h], ebp
0x140005690  mov     [rbx+30h], r12
0x140005694  mov     [rbx+48h], rdi
0x140005698  movups  xmmword ptr [rbx+68h], xmm0
0x14000569c  mov     [rbx+78h], rax
0x1400056a0  movups  xmmword ptr [rbx+50h], xmm0
0x1400056a4  mov     [rbx+60h], rax
0x1400056a8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400056af  test    rax, rax
0x1400056b2  jz      short loc_1400056BB
0x1400056b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400056b9  jmp     short loc_1400056BE
0x1400056bb  mov     rax, rdi
0x1400056be  mov     [rbx+80h], rax
0x1400056c5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400056cc  test    rax, rax
0x1400056cf  jz      short loc_1400056D9
0x1400056d1  mov     rcx, rbx
0x1400056d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400056d9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400056e0  test    rax, rax
0x1400056e3  jz      short loc_1400056FB
0x1400056e5  mov     rdx, [rsp+78h+arg_60]
0x1400056ed  mov     r8d, 400h
0x1400056f3  mov     rcx, rbx
0x1400056f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400056fb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005702  test    rax, rax
0x140005705  jz      short loc_14000570F
0x140005707  mov     rcx, rbx
0x14000570a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000570f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005716  test    rax, rax
0x140005719  jz      short loc_140005729
0x14000571b  test    byte ptr [rbx+4], 2
0x14000571f  jnz     short loc_140005729
0x140005721  mov     rcx, rbx
0x140005724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005729  cmp     [rbx+8], edi
0x14000572c  jl      short loc_140005748
0x14000572e  cmp     r15d, 3
0x140005732  jnz     loc_140005816
0x140005738  mov     ecx, 8000FFFFh; this
0x14000573d  mov     [rbx+8], ecx
0x140005740  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005745  mov     [rbx+0Ch], eax
0x140005748  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000574f  jnz     short loc_140005770
0x140005751  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005758  test    rax, rax
0x14000575b  jz      short loc_140005766
0x14000575d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005762  test    al, al
0x140005764  jmp     short loc_14000576E
0x140005766  call    cs:__imp_IsDebuggerPresent
0x14000576c  test    eax, eax
0x14000576e  jz      short loc_140005776
0x140005770  test    byte ptr [rbx+4], 2
0x140005774  jz      short loc_14000579A
0x140005776  mov     rax, cs:g_pfnResultLoggingCallback
0x14000577d  test    rax, rax
0x140005780  jz      short loc_1400057DE
0x140005782  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005789  jnz     short loc_1400057DE
0x14000578b  xor     r8d, r8d
0x14000578e  xor     edx, edx
0x140005790  mov     rcx, rbx
0x140005793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005798  jmp     short loc_1400057DE
0x14000579a  mov     rax, cs:g_pfnResultLoggingCallback
0x1400057a1  mov     ebp, 800h
0x1400057a6  test    rax, rax
0x1400057a9  jz      short loc_1400057C2
0x1400057ab  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400057b2  jnz     short loc_1400057C2
0x1400057b4  mov     r8d, ebp
0x1400057b7  mov     rdx, rsi
0x1400057ba  mov     rcx, rbx
0x1400057bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400057c2  cmp     [rsi], di
0x1400057c5  jnz     short loc_1400057D5
0x1400057c7  mov     r8, rbx; unsigned __int64
0x1400057ca  mov     rdx, rbp; unsigned __int16 *
0x1400057cd  mov     rcx, rsi; this
0x1400057d0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400057d5  mov     rcx, rsi; lpOutputString
0x1400057d8  call    cs:__imp_OutputDebugStringW
0x1400057de  test    byte ptr [rbx+4], 4
0x1400057e2  jnz     short loc_1400057ED
0x1400057e4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400057eb  jz      short loc_1400057FE
0x1400057ed  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400057f4  test    rax, rax
0x1400057f7  jz      short loc_1400057FE
0x1400057f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400057fe  mov     rbx, [rsp+78h+arg_10]
0x140005806  add     rsp, 40h
0x14000580a  pop     r15
0x14000580c  pop     r14
0x14000580e  pop     r13
0x140005810  pop     r12
0x140005812  pop     rdi
0x140005813  pop     rsi
0x140005814  pop     rbp
0x140005815  retn
0x140005816  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
