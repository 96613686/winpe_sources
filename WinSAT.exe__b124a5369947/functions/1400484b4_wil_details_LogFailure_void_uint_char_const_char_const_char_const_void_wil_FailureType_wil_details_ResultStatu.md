# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400484b4`
- end: `0x1400487ad`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400445ec`
- `0x140044938`

## callees

- `0x14004452c`
- `0x140046a24`
- `0x140047f74`
- `0x1400484b4`
- `0x1400491a8`
- `0x1400491d0`
- `0x140049308`
- `0x140049324`
- `0x14004ae94`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400485d7`
- `KERNEL32!GetCurrentThreadId` at `0x1400485d7`
- `KERNEL32!IsDebuggerPresent` at `0x1400486f6`
- `KERNEL32!IsDebuggerPresent` at `0x1400486f6`
- `KERNEL32!OutputDebugStringW` at `0x140048768`
- `KERNEL32!OutputDebugStringW` at `0x140048768`

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
0x1400484b4  mov     [rsp+arg_10], rbx
0x1400484b9  mov     [rsp+arg_8], edx
0x1400484bd  mov     [rsp+arg_0], rcx
0x1400484c2  push    rbp
0x1400484c3  push    rsi
0x1400484c4  push    rdi
0x1400484c5  push    r12
0x1400484c7  push    r13
0x1400484c9  push    r14
0x1400484cb  push    r15
0x1400484cd  sub     rsp, 40h
0x1400484d1  mov     r12, r9
0x1400484d4  mov     r13, r8
0x1400484d7  mov     r10, rcx
0x1400484da  xor     eax, eax
0x1400484dc  mov     rsi, [rsp+78h+lpOutputString]
0x1400484e4  mov     [rsi], ax
0x1400484e7  mov     rax, [rsp+78h+arg_60]
0x1400484ef  mov     byte ptr [rax], 0
0x1400484f2  mov     r14, [rsp+78h+arg_38]
0x1400484fa  mov     edi, [r14]
0x1400484fd  mov     rbx, [rsp+78h+arg_78]
0x140048505  mov     [rbx+8], edi
0x140048508  mov     eax, [r14+4]
0x14004850c  mov     [rbx+0Ch], eax
0x14004850f  xor     ebp, ebp
0x140048511  mov     r15d, [rsp+78h+arg_30]
0x140048519  mov     ecx, r15d
0x14004851c  test    r15d, r15d
0x14004851f  jz      short loc_140048587
0x140048521  sub     ecx, 1
0x140048524  jz      short loc_14004857E
0x140048526  sub     ecx, 1
0x140048529  jz      short loc_140048539
0x14004852b  cmp     ecx, 1
0x14004852e  jnz     short loc_140048590
0x140048530  mov     ecx, edi; this
0x140048532  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140048537  jmp     short loc_14004858E
0x140048539  test    edi, edi
0x14004853b  js      short loc_140048575
0x14004853d  mov     edi, 8007029Ch
0x140048542  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140048546  mov     rax, [rsp+78h+arg_28]
0x14004854e  mov     [rsp+78h+var_50], rax; __int64
0x140048553  mov     rax, [rsp+78h+arg_20]
0x14004855b  mov     [rsp+78h+var_58], rax; __int64
0x140048560  mov     rcx, r10; int
0x140048563  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140048568  mov     [rbx+8], edi
0x14004856b  mov     ecx, edi; this
0x14004856d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140048572  mov     [rbx+0Ch], eax
0x140048575  mov     ecx, edi; this
0x140048577  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14004857c  jmp     short loc_14004858E
0x14004857e  mov     ecx, edi; this
0x140048580  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140048585  jmp     short loc_14004858E
0x140048587  mov     ecx, edi; this
0x140048589  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14004858e  mov     ebp, eax
0x140048590  mov     [rbx], r15d
0x140048593  mov     eax, [rsp+78h+arg_70]
0x14004859a  mov     [rbx+4], eax
0x14004859d  cmp     dword ptr [r14+8], 1
0x1400485a2  jnz     short loc_1400485AA
0x1400485a4  or      eax, 8
0x1400485a7  mov     [rbx+4], eax
0x1400485aa  mov     eax, 1
0x1400485af  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400485b7  inc     eax
0x1400485b9  mov     [rbx+10h], eax
0x1400485bc  mov     rax, [rsp+78h+arg_40]
0x1400485c4  xor     edi, edi
0x1400485c6  test    rax, rax
0x1400485c9  jz      short loc_1400485D0
0x1400485cb  cmp     [rax], di
0x1400485ce  jnz     short loc_1400485D3
0x1400485d0  mov     rax, rdi
0x1400485d3  mov     [rbx+18h], rax
0x1400485d7  call    cs:__imp_GetCurrentThreadId
0x1400485dd  mov     [rbx+20h], eax
0x1400485e0  mov     [rbx+38h], r13
0x1400485e4  mov     eax, [rsp+78h+arg_8]
0x1400485eb  mov     [rbx+40h], eax
0x1400485ee  mov     [rbx+44h], ebp
0x1400485f1  mov     rax, [rsp+78h+arg_20]
0x1400485f9  mov     [rbx+28h], rax
0x1400485fd  mov     [rbx+30h], r12
0x140048601  mov     rax, [rsp+78h+arg_28]
0x140048609  mov     [rbx+88h], rax
0x140048610  mov     rax, [rsp+78h+arg_0]
0x140048618  mov     [rbx+90h], rax
0x14004861f  mov     [rbx+48h], rdi
0x140048623  xorps   xmm0, xmm0
0x140048626  xor     eax, eax
0x140048628  movups  xmmword ptr [rbx+68h], xmm0
0x14004862c  mov     [rbx+78h], rax
0x140048630  movups  xmmword ptr [rbx+50h], xmm0
0x140048634  mov     [rbx+60h], rax
0x140048638  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14004863f  test    rax, rax
0x140048642  jz      short loc_14004864B
0x140048644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048649  jmp     short loc_14004864E
0x14004864b  mov     rax, rdi
0x14004864e  mov     [rbx+80h], rax
0x140048655  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14004865c  test    rax, rax
0x14004865f  jz      short loc_140048669
0x140048661  mov     rcx, rbx
0x140048664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048669  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140048670  test    rax, rax
0x140048673  jz      short loc_14004868B
0x140048675  mov     r8d, 400h
0x14004867b  mov     rdx, [rsp+78h+arg_60]
0x140048683  mov     rcx, rbx
0x140048686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004868b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140048692  test    rax, rax
0x140048695  jz      short loc_14004869F
0x140048697  mov     rcx, rbx
0x14004869a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004869f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400486a6  test    rax, rax
0x1400486a9  jz      short loc_1400486B9
0x1400486ab  test    byte ptr [rbx+4], 2
0x1400486af  jnz     short loc_1400486B9
0x1400486b1  mov     rcx, rbx
0x1400486b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400486b9  cmp     [rbx+8], edi
0x1400486bc  jl      short loc_1400486D8
0x1400486be  cmp     r15d, 3
0x1400486c2  jnz     loc_1400487A7
0x1400486c8  mov     ecx, 8000FFFFh; this
0x1400486cd  mov     [rbx+8], ecx
0x1400486d0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400486d5  mov     [rbx+0Ch], eax
0x1400486d8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400486df  jnz     short loc_140048700
0x1400486e1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400486e8  test    rax, rax
0x1400486eb  jz      short loc_1400486F6
0x1400486ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400486f2  test    al, al
0x1400486f4  jmp     short loc_1400486FE
0x1400486f6  call    cs:__imp_IsDebuggerPresent
0x1400486fc  test    eax, eax
0x1400486fe  jz      short loc_140048706
0x140048700  test    byte ptr [rbx+4], 2
0x140048704  jz      short loc_14004872A
0x140048706  mov     rax, cs:g_pfnResultLoggingCallback
0x14004870d  test    rax, rax
0x140048710  jz      short loc_14004876E
0x140048712  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140048719  jnz     short loc_14004876E
0x14004871b  xor     r8d, r8d
0x14004871e  xor     edx, edx
0x140048720  mov     rcx, rbx
0x140048723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048728  jmp     short loc_14004876E
0x14004872a  mov     ebp, 800h
0x14004872f  mov     rax, cs:g_pfnResultLoggingCallback
0x140048736  test    rax, rax
0x140048739  jz      short loc_140048752
0x14004873b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140048742  jnz     short loc_140048752
0x140048744  mov     r8d, ebp
0x140048747  mov     rdx, rsi
0x14004874a  mov     rcx, rbx
0x14004874d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140048752  cmp     [rsi], di
0x140048755  jnz     short loc_140048765
0x140048757  mov     r8, rbx; unsigned __int64
0x14004875a  mov     rdx, rbp; unsigned __int16 *
0x14004875d  mov     rcx, rsi; this
0x140048760  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140048765  mov     rcx, rsi; lpOutputString
0x140048768  call    cs:__imp_OutputDebugStringW
0x14004876e  test    byte ptr [rbx+4], 4
0x140048772  jnz     short loc_14004877D
0x140048774  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14004877b  jz      short loc_14004878F
0x14004877d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140048784  test    rax, rax
0x140048787  jz      short loc_14004878F
0x140048789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004878e  nop
0x14004878f  mov     rbx, [rsp+78h+arg_10]
0x140048797  add     rsp, 40h
0x14004879b  pop     r15
0x14004879d  pop     r14
0x14004879f  pop     r13
0x1400487a1  pop     r12
0x1400487a3  pop     rdi
0x1400487a4  pop     rsi
0x1400487a5  pop     rbp
0x1400487a6  retn
0x1400487a7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
