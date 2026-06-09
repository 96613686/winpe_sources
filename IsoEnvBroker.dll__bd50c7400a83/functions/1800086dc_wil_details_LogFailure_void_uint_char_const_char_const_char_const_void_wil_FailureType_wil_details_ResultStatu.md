# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800086dc`
- end: `0x1800089d5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005b50`

## callees

- `0x18000555c`
- `0x180007be4`
- `0x180008430`
- `0x1800086dc`
- `0x180009390`
- `0x1800093b0`
- `0x1800094dc`
- `0x1800094f8`
- `0x18000bd88`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800087ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800087ff`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000891e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000891e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008990`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008990`

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x1800086dc  mov     [rsp+arg_10], rbx
0x1800086e1  mov     [rsp+arg_8], edx
0x1800086e5  mov     [rsp+arg_0], rcx
0x1800086ea  push    rbp
0x1800086eb  push    rsi
0x1800086ec  push    rdi
0x1800086ed  push    r12
0x1800086ef  push    r13
0x1800086f1  push    r14
0x1800086f3  push    r15
0x1800086f5  sub     rsp, 40h
0x1800086f9  mov     r12, r9
0x1800086fc  mov     r13, r8
0x1800086ff  mov     r10, rcx
0x180008702  xor     eax, eax
0x180008704  mov     rsi, [rsp+78h+lpOutputString]
0x18000870c  mov     [rsi], ax
0x18000870f  mov     rax, [rsp+78h+arg_60]
0x180008717  mov     byte ptr [rax], 0
0x18000871a  mov     r14, [rsp+78h+arg_38]
0x180008722  mov     edi, [r14]
0x180008725  mov     rbx, [rsp+78h+arg_78]
0x18000872d  mov     [rbx+8], edi
0x180008730  mov     eax, [r14+4]
0x180008734  mov     [rbx+0Ch], eax
0x180008737  xor     ebp, ebp
0x180008739  mov     r15d, [rsp+78h+arg_30]
0x180008741  mov     ecx, r15d
0x180008744  test    r15d, r15d
0x180008747  jz      short loc_1800087AF
0x180008749  sub     ecx, 1
0x18000874c  jz      short loc_1800087A6
0x18000874e  sub     ecx, 1
0x180008751  jz      short loc_180008761
0x180008753  cmp     ecx, 1
0x180008756  jnz     short loc_1800087B8
0x180008758  mov     ecx, edi; this
0x18000875a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000875f  jmp     short loc_1800087B6
0x180008761  test    edi, edi
0x180008763  js      short loc_18000879D
0x180008765  mov     edi, 8007029Ch
0x18000876a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000876e  mov     rax, [rsp+78h+arg_28]
0x180008776  mov     [rsp+78h+var_50], rax; __int64
0x18000877b  mov     rax, [rsp+78h+arg_20]
0x180008783  mov     [rsp+78h+var_58], rax; __int64
0x180008788  mov     rcx, r10; int
0x18000878b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008790  mov     [rbx+8], edi
0x180008793  mov     ecx, edi; this
0x180008795  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000879a  mov     [rbx+0Ch], eax
0x18000879d  mov     ecx, edi; this
0x18000879f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800087a4  jmp     short loc_1800087B6
0x1800087a6  mov     ecx, edi; this
0x1800087a8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800087ad  jmp     short loc_1800087B6
0x1800087af  mov     ecx, edi; this
0x1800087b1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800087b6  mov     ebp, eax
0x1800087b8  mov     [rbx], r15d
0x1800087bb  mov     eax, [rsp+78h+arg_70]
0x1800087c2  mov     [rbx+4], eax
0x1800087c5  cmp     dword ptr [r14+8], 1
0x1800087ca  jnz     short loc_1800087D2
0x1800087cc  or      eax, 8
0x1800087cf  mov     [rbx+4], eax
0x1800087d2  mov     eax, 1
0x1800087d7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800087df  inc     eax
0x1800087e1  mov     [rbx+10h], eax
0x1800087e4  mov     rax, [rsp+78h+arg_40]
0x1800087ec  xor     edi, edi
0x1800087ee  test    rax, rax
0x1800087f1  jz      short loc_1800087F8
0x1800087f3  cmp     [rax], di
0x1800087f6  jnz     short loc_1800087FB
0x1800087f8  mov     rax, rdi
0x1800087fb  mov     [rbx+18h], rax
0x1800087ff  call    cs:__imp_GetCurrentThreadId
0x180008805  mov     [rbx+20h], eax
0x180008808  mov     [rbx+38h], r13
0x18000880c  mov     eax, [rsp+78h+arg_8]
0x180008813  mov     [rbx+40h], eax
0x180008816  mov     [rbx+44h], ebp
0x180008819  mov     rax, [rsp+78h+arg_20]
0x180008821  mov     [rbx+28h], rax
0x180008825  mov     [rbx+30h], r12
0x180008829  mov     rax, [rsp+78h+arg_28]
0x180008831  mov     [rbx+88h], rax
0x180008838  mov     rax, [rsp+78h+arg_0]
0x180008840  mov     [rbx+90h], rax
0x180008847  mov     [rbx+48h], rdi
0x18000884b  xorps   xmm0, xmm0
0x18000884e  xor     eax, eax
0x180008850  movups  xmmword ptr [rbx+68h], xmm0
0x180008854  mov     [rbx+78h], rax
0x180008858  movups  xmmword ptr [rbx+50h], xmm0
0x18000885c  mov     [rbx+60h], rax
0x180008860  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008867  test    rax, rax
0x18000886a  jz      short loc_180008873
0x18000886c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008871  jmp     short loc_180008876
0x180008873  mov     rax, rdi
0x180008876  mov     [rbx+80h], rax
0x18000887d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008884  test    rax, rax
0x180008887  jz      short loc_180008891
0x180008889  mov     rcx, rbx
0x18000888c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008891  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008898  test    rax, rax
0x18000889b  jz      short loc_1800088B3
0x18000889d  mov     r8d, 400h
0x1800088a3  mov     rdx, [rsp+78h+arg_60]
0x1800088ab  mov     rcx, rbx
0x1800088ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088b3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800088ba  test    rax, rax
0x1800088bd  jz      short loc_1800088C7
0x1800088bf  mov     rcx, rbx
0x1800088c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088c7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800088ce  test    rax, rax
0x1800088d1  jz      short loc_1800088E1
0x1800088d3  test    byte ptr [rbx+4], 2
0x1800088d7  jnz     short loc_1800088E1
0x1800088d9  mov     rcx, rbx
0x1800088dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088e1  cmp     [rbx+8], edi
0x1800088e4  jl      short loc_180008900
0x1800088e6  cmp     r15d, 3
0x1800088ea  jnz     loc_1800089CF
0x1800088f0  mov     ecx, 8000FFFFh; this
0x1800088f5  mov     [rbx+8], ecx
0x1800088f8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800088fd  mov     [rbx+0Ch], eax
0x180008900  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008907  jnz     short loc_180008928
0x180008909  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008910  test    rax, rax
0x180008913  jz      short loc_18000891E
0x180008915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000891a  test    al, al
0x18000891c  jmp     short loc_180008926
0x18000891e  call    cs:__imp_IsDebuggerPresent
0x180008924  test    eax, eax
0x180008926  jz      short loc_18000892E
0x180008928  test    byte ptr [rbx+4], 2
0x18000892c  jz      short loc_180008952
0x18000892e  mov     rax, cs:g_pfnResultLoggingCallback
0x180008935  test    rax, rax
0x180008938  jz      short loc_180008996
0x18000893a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008941  jnz     short loc_180008996
0x180008943  xor     r8d, r8d
0x180008946  xor     edx, edx
0x180008948  mov     rcx, rbx
0x18000894b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008950  jmp     short loc_180008996
0x180008952  mov     ebp, 800h
0x180008957  mov     rax, cs:g_pfnResultLoggingCallback
0x18000895e  test    rax, rax
0x180008961  jz      short loc_18000897A
0x180008963  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000896a  jnz     short loc_18000897A
0x18000896c  mov     r8d, ebp
0x18000896f  mov     rdx, rsi
0x180008972  mov     rcx, rbx
0x180008975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000897a  cmp     [rsi], di
0x18000897d  jnz     short loc_18000898D
0x18000897f  mov     r8, rbx; unsigned __int64
0x180008982  mov     rdx, rbp; wchar_t *
0x180008985  mov     rcx, rsi; this
0x180008988  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000898d  mov     rcx, rsi; lpOutputString
0x180008990  call    cs:__imp_OutputDebugStringW
0x180008996  test    byte ptr [rbx+4], 4
0x18000899a  jnz     short loc_1800089A5
0x18000899c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800089a3  jz      short loc_1800089B7
0x1800089a5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800089ac  test    rax, rax
0x1800089af  jz      short loc_1800089B7
0x1800089b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800089b6  nop
0x1800089b7  mov     rbx, [rsp+78h+arg_10]
0x1800089bf  add     rsp, 40h
0x1800089c3  pop     r15
0x1800089c5  pop     r14
0x1800089c7  pop     r13
0x1800089c9  pop     r12
0x1800089cb  pop     rdi
0x1800089cc  pop     rsi
0x1800089cd  pop     rbp
0x1800089ce  retn
0x1800089cf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
