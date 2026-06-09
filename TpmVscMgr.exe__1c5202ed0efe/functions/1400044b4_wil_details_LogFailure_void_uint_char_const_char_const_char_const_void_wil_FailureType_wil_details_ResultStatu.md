# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400044b4`
- end: `0x1400047ad`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002cb4`

## callees

- `0x1400026d0`
- `0x140003b54`
- `0x1400042f0`
- `0x1400044b4`
- `0x140004a34`
- `0x140004a50`
- `0x140004a64`
- `0x140004a80`
- `0x140005bac`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400045d7`
- `KERNEL32!GetCurrentThreadId` at `0x1400045d7`
- `KERNEL32!OutputDebugStringW` at `0x140004768`
- `KERNEL32!OutputDebugStringW` at `0x140004768`
- `KERNEL32!IsDebuggerPresent` at `0x1400046f6`
- `KERNEL32!IsDebuggerPresent` at `0x1400046f6`

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
0x1400044b4  mov     [rsp+arg_10], rbx
0x1400044b9  mov     [rsp+arg_8], edx
0x1400044bd  mov     [rsp+arg_0], rcx
0x1400044c2  push    rbp
0x1400044c3  push    rsi
0x1400044c4  push    rdi
0x1400044c5  push    r12
0x1400044c7  push    r13
0x1400044c9  push    r14
0x1400044cb  push    r15
0x1400044cd  sub     rsp, 40h
0x1400044d1  mov     r12, r9
0x1400044d4  mov     r13, r8
0x1400044d7  mov     r10, rcx
0x1400044da  xor     eax, eax
0x1400044dc  mov     rsi, [rsp+78h+lpOutputString]
0x1400044e4  mov     [rsi], ax
0x1400044e7  mov     rax, [rsp+78h+arg_60]
0x1400044ef  mov     byte ptr [rax], 0
0x1400044f2  mov     r14, [rsp+78h+arg_38]
0x1400044fa  mov     edi, [r14]
0x1400044fd  mov     rbx, [rsp+78h+arg_78]
0x140004505  mov     [rbx+8], edi
0x140004508  mov     eax, [r14+4]
0x14000450c  mov     [rbx+0Ch], eax
0x14000450f  xor     ebp, ebp
0x140004511  mov     r15d, [rsp+78h+arg_30]
0x140004519  mov     ecx, r15d
0x14000451c  test    r15d, r15d
0x14000451f  jz      short loc_140004587
0x140004521  sub     ecx, 1
0x140004524  jz      short loc_14000457E
0x140004526  sub     ecx, 1
0x140004529  jz      short loc_140004539
0x14000452b  cmp     ecx, 1
0x14000452e  jnz     short loc_140004590
0x140004530  mov     ecx, edi; this
0x140004532  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004537  jmp     short loc_14000458E
0x140004539  test    edi, edi
0x14000453b  js      short loc_140004575
0x14000453d  mov     edi, 8007029Ch
0x140004542  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140004546  mov     rax, [rsp+78h+arg_28]
0x14000454e  mov     [rsp+78h+var_50], rax; __int64
0x140004553  mov     rax, [rsp+78h+arg_20]
0x14000455b  mov     [rsp+78h+var_58], rax; __int64
0x140004560  mov     rcx, r10; int
0x140004563  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004568  mov     [rbx+8], edi
0x14000456b  mov     ecx, edi; this
0x14000456d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004572  mov     [rbx+0Ch], eax
0x140004575  mov     ecx, edi; this
0x140004577  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000457c  jmp     short loc_14000458E
0x14000457e  mov     ecx, edi; this
0x140004580  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004585  jmp     short loc_14000458E
0x140004587  mov     ecx, edi; this
0x140004589  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000458e  mov     ebp, eax
0x140004590  mov     [rbx], r15d
0x140004593  mov     eax, [rsp+78h+arg_70]
0x14000459a  mov     [rbx+4], eax
0x14000459d  cmp     dword ptr [r14+8], 1
0x1400045a2  jnz     short loc_1400045AA
0x1400045a4  or      eax, 8
0x1400045a7  mov     [rbx+4], eax
0x1400045aa  mov     eax, 1
0x1400045af  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400045b7  inc     eax
0x1400045b9  mov     [rbx+10h], eax
0x1400045bc  mov     rax, [rsp+78h+arg_40]
0x1400045c4  xor     edi, edi
0x1400045c6  test    rax, rax
0x1400045c9  jz      short loc_1400045D0
0x1400045cb  cmp     [rax], di
0x1400045ce  jnz     short loc_1400045D3
0x1400045d0  mov     rax, rdi
0x1400045d3  mov     [rbx+18h], rax
0x1400045d7  call    cs:__imp_GetCurrentThreadId
0x1400045dd  mov     [rbx+20h], eax
0x1400045e0  mov     [rbx+38h], r13
0x1400045e4  mov     eax, [rsp+78h+arg_8]
0x1400045eb  mov     [rbx+40h], eax
0x1400045ee  mov     [rbx+44h], ebp
0x1400045f1  mov     rax, [rsp+78h+arg_20]
0x1400045f9  mov     [rbx+28h], rax
0x1400045fd  mov     [rbx+30h], r12
0x140004601  mov     rax, [rsp+78h+arg_28]
0x140004609  mov     [rbx+88h], rax
0x140004610  mov     rax, [rsp+78h+arg_0]
0x140004618  mov     [rbx+90h], rax
0x14000461f  mov     [rbx+48h], rdi
0x140004623  xorps   xmm0, xmm0
0x140004626  xor     eax, eax
0x140004628  movups  xmmword ptr [rbx+68h], xmm0
0x14000462c  mov     [rbx+78h], rax
0x140004630  movups  xmmword ptr [rbx+50h], xmm0
0x140004634  mov     [rbx+60h], rax
0x140004638  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000463f  test    rax, rax
0x140004642  jz      short loc_14000464B
0x140004644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004649  jmp     short loc_14000464E
0x14000464b  mov     rax, rdi
0x14000464e  mov     [rbx+80h], rax
0x140004655  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000465c  test    rax, rax
0x14000465f  jz      short loc_140004669
0x140004661  mov     rcx, rbx
0x140004664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004669  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004670  test    rax, rax
0x140004673  jz      short loc_14000468B
0x140004675  mov     r8d, 400h
0x14000467b  mov     rdx, [rsp+78h+arg_60]
0x140004683  mov     rcx, rbx
0x140004686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000468b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004692  test    rax, rax
0x140004695  jz      short loc_14000469F
0x140004697  mov     rcx, rbx
0x14000469a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000469f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400046a6  test    rax, rax
0x1400046a9  jz      short loc_1400046B9
0x1400046ab  test    byte ptr [rbx+4], 2
0x1400046af  jnz     short loc_1400046B9
0x1400046b1  mov     rcx, rbx
0x1400046b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046b9  cmp     [rbx+8], edi
0x1400046bc  jl      short loc_1400046D8
0x1400046be  cmp     r15d, 3
0x1400046c2  jnz     loc_1400047A7
0x1400046c8  mov     ecx, 8000FFFFh; this
0x1400046cd  mov     [rbx+8], ecx
0x1400046d0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400046d5  mov     [rbx+0Ch], eax
0x1400046d8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400046df  jnz     short loc_140004700
0x1400046e1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400046e8  test    rax, rax
0x1400046eb  jz      short loc_1400046F6
0x1400046ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046f2  test    al, al
0x1400046f4  jmp     short loc_1400046FE
0x1400046f6  call    cs:__imp_IsDebuggerPresent
0x1400046fc  test    eax, eax
0x1400046fe  jz      short loc_140004706
0x140004700  test    byte ptr [rbx+4], 2
0x140004704  jz      short loc_14000472A
0x140004706  mov     rax, cs:g_pfnResultLoggingCallback
0x14000470d  test    rax, rax
0x140004710  jz      short loc_14000476E
0x140004712  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004719  jnz     short loc_14000476E
0x14000471b  xor     r8d, r8d
0x14000471e  xor     edx, edx
0x140004720  mov     rcx, rbx
0x140004723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004728  jmp     short loc_14000476E
0x14000472a  mov     ebp, 800h
0x14000472f  mov     rax, cs:g_pfnResultLoggingCallback
0x140004736  test    rax, rax
0x140004739  jz      short loc_140004752
0x14000473b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004742  jnz     short loc_140004752
0x140004744  mov     r8d, ebp
0x140004747  mov     rdx, rsi
0x14000474a  mov     rcx, rbx
0x14000474d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004752  cmp     [rsi], di
0x140004755  jnz     short loc_140004765
0x140004757  mov     r8, rbx; unsigned __int64
0x14000475a  mov     rdx, rbp; unsigned __int16 *
0x14000475d  mov     rcx, rsi; this
0x140004760  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004765  mov     rcx, rsi; lpOutputString
0x140004768  call    cs:__imp_OutputDebugStringW
0x14000476e  test    byte ptr [rbx+4], 4
0x140004772  jnz     short loc_14000477D
0x140004774  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000477b  jz      short loc_14000478F
0x14000477d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004784  test    rax, rax
0x140004787  jz      short loc_14000478F
0x140004789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000478e  nop
0x14000478f  mov     rbx, [rsp+78h+arg_10]
0x140004797  add     rsp, 40h
0x14000479b  pop     r15
0x14000479d  pop     r14
0x14000479f  pop     r13
0x1400047a1  pop     r12
0x1400047a3  pop     rdi
0x1400047a4  pop     rsi
0x1400047a5  pop     rbp
0x1400047a6  retn
0x1400047a7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
