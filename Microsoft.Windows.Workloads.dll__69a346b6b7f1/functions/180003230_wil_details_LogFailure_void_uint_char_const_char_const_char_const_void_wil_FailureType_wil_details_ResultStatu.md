# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180003230`
- end: `0x180003548`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `792`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002cb0`

## callees

- `0x180002c70`
- `0x180002c90`
- `0x180002da0`
- `0x180002e10`
- `0x180002e30`
- `0x180002e40`
- `0x180002f70`
- `0x180003230`
- `0x1800039f0`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180003486`
- `KERNEL32!IsDebuggerPresent` at `0x180003486`
- `KERNEL32!GetCurrentThreadId` at `0x180003354`
- `KERNEL32!GetCurrentThreadId` at `0x180003354`
- `KERNEL32!OutputDebugStringW` at `0x180003502`
- `KERNEL32!OutputDebugStringW` at `0x180003502`

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
  int IsDebuggerPresent; // esi
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  wil::details *v25; // [rsp+30h] [rbp-48h]

  IsDebuggerPresent = 0;
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
          LODWORD(v25) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v25);
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
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22)),
         IsDebuggerPresent))
    && (*(_BYTE *)(a16 + 4) & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(a16, 0, 0);
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
0x180003230  mov     [rsp+arg_18], rbx
0x180003235  mov     [rsp+arg_10], r8
0x18000323a  mov     [rsp+arg_8], edx
0x18000323e  mov     [rsp+arg_0], rcx
0x180003243  push    rbp
0x180003244  push    rsi
0x180003245  push    rdi
0x180003246  push    r12
0x180003248  push    r13
0x18000324a  push    r14
0x18000324c  push    r15
0x18000324e  sub     rsp, 40h
0x180003252  mov     r13, r9
0x180003255  mov     r10, rcx
0x180003258  xor     esi, esi
0x18000325a  mov     r14, [rsp+78h+lpOutputString]
0x180003262  mov     [r14], si
0x180003266  mov     rax, [rsp+78h+arg_60]
0x18000326e  mov     [rax], sil
0x180003271  mov     r15, [rsp+78h+arg_38]
0x180003279  mov     edi, [r15]
0x18000327c  mov     rbx, [rsp+78h+arg_78]
0x180003284  mov     [rbx+8], edi
0x180003287  mov     eax, [r15+4]
0x18000328b  mov     [rbx+0Ch], eax
0x18000328e  mov     ebp, esi
0x180003290  mov     r12d, [rsp+78h+arg_30]
0x180003298  mov     ecx, r12d
0x18000329b  test    r12d, r12d
0x18000329e  jz      short loc_180003306
0x1800032a0  sub     ecx, 1
0x1800032a3  jz      short loc_1800032FD
0x1800032a5  sub     ecx, 1
0x1800032a8  jz      short loc_1800032B8
0x1800032aa  cmp     ecx, 1
0x1800032ad  jnz     short loc_18000330F
0x1800032af  mov     ecx, edi; this
0x1800032b1  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800032b6  jmp     short loc_18000330D
0x1800032b8  test    edi, edi
0x1800032ba  js      short loc_1800032F4
0x1800032bc  mov     edi, 8007029Ch
0x1800032c1  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800032c5  mov     rax, [rsp+78h+arg_28]
0x1800032cd  mov     [rsp+78h+var_50], rax; __int64
0x1800032d2  mov     rax, [rsp+78h+arg_20]
0x1800032da  mov     [rsp+78h+var_58], rax; __int64
0x1800032df  mov     rcx, r10; int
0x1800032e2  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800032e7  mov     [rbx+8], edi
0x1800032ea  mov     ecx, edi; this
0x1800032ec  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800032f1  mov     [rbx+0Ch], eax
0x1800032f4  mov     ecx, edi; this
0x1800032f6  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800032fb  jmp     short loc_18000330D
0x1800032fd  mov     ecx, edi; this
0x1800032ff  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003304  jmp     short loc_18000330D
0x180003306  mov     ecx, edi; this
0x180003308  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000330d  mov     ebp, eax
0x18000330f  mov     [rbx], r12d
0x180003312  mov     eax, [rsp+78h+arg_70]
0x180003319  mov     [rbx+4], eax
0x18000331c  cmp     dword ptr [r15+8], 1
0x180003321  jnz     short loc_180003329
0x180003323  or      eax, 8
0x180003326  mov     [rbx+4], eax
0x180003329  mov     eax, 1
0x18000332e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003336  inc     eax
0x180003338  mov     [rbx+10h], eax
0x18000333b  mov     rax, [rsp+78h+arg_40]
0x180003343  test    rax, rax
0x180003346  jz      short loc_18000334D
0x180003348  cmp     [rax], si
0x18000334b  jnz     short loc_180003350
0x18000334d  mov     rax, rsi
0x180003350  mov     [rbx+18h], rax
0x180003354  call    cs:__imp_GetCurrentThreadId
0x18000335a  mov     [rbx+20h], eax
0x18000335d  mov     rax, [rsp+78h+arg_10]
0x180003365  mov     [rbx+38h], rax
0x180003369  mov     eax, [rsp+78h+arg_8]
0x180003370  mov     [rbx+40h], eax
0x180003373  mov     [rbx+44h], ebp
0x180003376  mov     rax, [rsp+78h+arg_20]
0x18000337e  mov     [rbx+28h], rax
0x180003382  mov     [rbx+30h], r13
0x180003386  mov     rax, [rsp+78h+arg_28]
0x18000338e  mov     [rbx+88h], rax
0x180003395  mov     rax, [rsp+78h+arg_0]
0x18000339d  mov     [rbx+90h], rax
0x1800033a4  mov     [rbx+48h], rsi
0x1800033a8  xorps   xmm0, xmm0
0x1800033ab  xor     eax, eax
0x1800033ad  movups  xmmword ptr [rbx+68h], xmm0
0x1800033b1  mov     [rbx+78h], rax
0x1800033b5  movups  xmmword ptr [rbx+50h], xmm0
0x1800033b9  mov     [rbx+60h], rax
0x1800033bd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800033c4  test    rax, rax
0x1800033c7  jz      short loc_1800033D1
0x1800033c9  call    cs:__guard_dispatch_icall_fptr
0x1800033cf  jmp     short loc_1800033D4
0x1800033d1  mov     rax, rsi
0x1800033d4  mov     [rbx+80h], rax
0x1800033db  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800033e2  test    rax, rax
0x1800033e5  jz      short loc_1800033F0
0x1800033e7  mov     rcx, rbx
0x1800033ea  call    cs:__guard_dispatch_icall_fptr
0x1800033f0  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800033f7  test    rax, rax
0x1800033fa  jz      short loc_180003413
0x1800033fc  mov     r8d, 400h
0x180003402  mov     rdx, [rsp+78h+arg_60]
0x18000340a  mov     rcx, rbx
0x18000340d  call    cs:__guard_dispatch_icall_fptr
0x180003413  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000341a  test    rax, rax
0x18000341d  jz      short loc_180003428
0x18000341f  mov     rcx, rbx
0x180003422  call    cs:__guard_dispatch_icall_fptr
0x180003428  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000342f  test    rax, rax
0x180003432  jz      short loc_180003443
0x180003434  test    byte ptr [rbx+4], 2
0x180003438  jnz     short loc_180003443
0x18000343a  mov     rcx, rbx
0x18000343d  call    cs:__guard_dispatch_icall_fptr
0x180003443  cmp     [rbx+8], esi
0x180003446  jl      short loc_180003466
0x180003448  cmp     r12d, 3
0x18000344c  jnz     loc_180003542
0x180003452  mov     dword ptr [rbx+8], 8000FFFFh
0x180003459  mov     ecx, 8000FFFFh; this
0x18000345e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180003463  mov     [rbx+0Ch], eax
0x180003466  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, sil; bool wil::g_fIsDebuggerPresent
0x18000346d  jnz     short loc_180003496
0x18000346f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003476  test    rax, rax
0x180003479  jz      short loc_180003486
0x18000347b  call    cs:__guard_dispatch_icall_fptr
0x180003481  movzx   esi, al
0x180003484  jmp     short loc_180003492
0x180003486  call    cs:__imp_IsDebuggerPresent
0x18000348c  test    eax, eax
0x18000348e  setnz   sil
0x180003492  test    esi, esi
0x180003494  jz      short loc_18000349C
0x180003496  test    byte ptr [rbx+4], 2
0x18000349a  jz      short loc_1800034C1
0x18000349c  mov     rax, cs:g_pfnResultLoggingCallback
0x1800034a3  test    rax, rax
0x1800034a6  jz      short loc_180003508
0x1800034a8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1800034af  jnz     short loc_180003508
0x1800034b1  xor     r8d, r8d
0x1800034b4  xor     edx, edx
0x1800034b6  mov     rcx, rbx
0x1800034b9  call    cs:__guard_dispatch_icall_fptr
0x1800034bf  jmp     short loc_180003508
0x1800034c1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800034c8  test    rax, rax
0x1800034cb  jz      short loc_1800034E8
0x1800034cd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1800034d4  jnz     short loc_1800034E8
0x1800034d6  mov     r8d, 800h
0x1800034dc  mov     rdx, r14
0x1800034df  mov     rcx, rbx
0x1800034e2  call    cs:__guard_dispatch_icall_fptr
0x1800034e8  cmp     word ptr [r14], 0
0x1800034ed  jnz     short loc_1800034FF
0x1800034ef  mov     r8, rbx; unsigned __int64
0x1800034f2  mov     edx, 800h; wchar_t *
0x1800034f7  mov     rcx, r14; this
0x1800034fa  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800034ff  mov     rcx, r14; lpOutputString
0x180003502  call    cs:__imp_OutputDebugStringW
0x180003508  test    byte ptr [rbx+4], 4
0x18000350c  jnz     short loc_180003517
0x18000350e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x180003515  jz      short loc_18000352A
0x180003517  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000351e  test    rax, rax
0x180003521  jz      short loc_18000352A
0x180003523  call    cs:__guard_dispatch_icall_fptr
0x180003529  nop
0x18000352a  mov     rbx, [rsp+78h+arg_18]
0x180003532  add     rsp, 40h
0x180003536  pop     r15
0x180003538  pop     r14
0x18000353a  pop     r13
0x18000353c  pop     r12
0x18000353e  pop     rdi
0x18000353f  pop     rsi
0x180003540  pop     rbp
0x180003541  retn
0x180003542  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
