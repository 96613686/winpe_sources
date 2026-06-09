# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008470`
- end: `0x180008769`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180002ef8`
- `0x180006410`
- `0x18000677c`

## callees

- `0x180002d34`
- `0x180006348`
- `0x180007cc4`
- `0x180008470`
- `0x180008bb0`
- `0x180008bd0`
- `0x180008be4`
- `0x180008c00`
- `0x180009bb8`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008593`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008593`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008724`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008724`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800086b2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800086b2`

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
0x180008470  mov     [rsp+arg_10], rbx
0x180008475  mov     [rsp+arg_8], edx
0x180008479  mov     [rsp+arg_0], rcx
0x18000847e  push    rbp
0x18000847f  push    rsi
0x180008480  push    rdi
0x180008481  push    r12
0x180008483  push    r13
0x180008485  push    r14
0x180008487  push    r15
0x180008489  sub     rsp, 40h
0x18000848d  mov     r12, r9
0x180008490  mov     r13, r8
0x180008493  mov     r10, rcx
0x180008496  xor     eax, eax
0x180008498  mov     rsi, [rsp+78h+lpOutputString]
0x1800084a0  mov     [rsi], ax
0x1800084a3  mov     rax, [rsp+78h+arg_60]
0x1800084ab  mov     byte ptr [rax], 0
0x1800084ae  mov     r14, [rsp+78h+arg_38]
0x1800084b6  mov     edi, [r14]
0x1800084b9  mov     rbx, [rsp+78h+arg_78]
0x1800084c1  mov     [rbx+8], edi
0x1800084c4  mov     eax, [r14+4]
0x1800084c8  mov     [rbx+0Ch], eax
0x1800084cb  xor     ebp, ebp
0x1800084cd  mov     r15d, [rsp+78h+arg_30]
0x1800084d5  mov     ecx, r15d
0x1800084d8  test    r15d, r15d
0x1800084db  jz      short loc_180008543
0x1800084dd  sub     ecx, 1
0x1800084e0  jz      short loc_18000853A
0x1800084e2  sub     ecx, 1
0x1800084e5  jz      short loc_1800084F5
0x1800084e7  cmp     ecx, 1
0x1800084ea  jnz     short loc_18000854C
0x1800084ec  mov     ecx, edi; this
0x1800084ee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800084f3  jmp     short loc_18000854A
0x1800084f5  test    edi, edi
0x1800084f7  js      short loc_180008531
0x1800084f9  mov     edi, 8007029Ch
0x1800084fe  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180008502  mov     rax, [rsp+78h+arg_28]
0x18000850a  mov     [rsp+78h+var_50], rax; __int64
0x18000850f  mov     rax, [rsp+78h+arg_20]
0x180008517  mov     [rsp+78h+var_58], rax; __int64
0x18000851c  mov     rcx, r10; int
0x18000851f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008524  mov     [rbx+8], edi
0x180008527  mov     ecx, edi; this
0x180008529  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000852e  mov     [rbx+0Ch], eax
0x180008531  mov     ecx, edi; this
0x180008533  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008538  jmp     short loc_18000854A
0x18000853a  mov     ecx, edi; this
0x18000853c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008541  jmp     short loc_18000854A
0x180008543  mov     ecx, edi; this
0x180008545  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000854a  mov     ebp, eax
0x18000854c  mov     [rbx], r15d
0x18000854f  mov     eax, [rsp+78h+arg_70]
0x180008556  mov     [rbx+4], eax
0x180008559  cmp     dword ptr [r14+8], 1
0x18000855e  jnz     short loc_180008566
0x180008560  or      eax, 8
0x180008563  mov     [rbx+4], eax
0x180008566  mov     eax, 1
0x18000856b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008573  inc     eax
0x180008575  mov     [rbx+10h], eax
0x180008578  mov     rax, [rsp+78h+arg_40]
0x180008580  xor     edi, edi
0x180008582  test    rax, rax
0x180008585  jz      short loc_18000858C
0x180008587  cmp     [rax], di
0x18000858a  jnz     short loc_18000858F
0x18000858c  mov     rax, rdi
0x18000858f  mov     [rbx+18h], rax
0x180008593  call    cs:__imp_GetCurrentThreadId
0x180008599  mov     [rbx+20h], eax
0x18000859c  mov     [rbx+38h], r13
0x1800085a0  mov     eax, [rsp+78h+arg_8]
0x1800085a7  mov     [rbx+40h], eax
0x1800085aa  mov     [rbx+44h], ebp
0x1800085ad  mov     rax, [rsp+78h+arg_20]
0x1800085b5  mov     [rbx+28h], rax
0x1800085b9  mov     [rbx+30h], r12
0x1800085bd  mov     rax, [rsp+78h+arg_28]
0x1800085c5  mov     [rbx+88h], rax
0x1800085cc  mov     rax, [rsp+78h+arg_0]
0x1800085d4  mov     [rbx+90h], rax
0x1800085db  mov     [rbx+48h], rdi
0x1800085df  xorps   xmm0, xmm0
0x1800085e2  xor     eax, eax
0x1800085e4  movups  xmmword ptr [rbx+68h], xmm0
0x1800085e8  mov     [rbx+78h], rax
0x1800085ec  movups  xmmword ptr [rbx+50h], xmm0
0x1800085f0  mov     [rbx+60h], rax
0x1800085f4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800085fb  test    rax, rax
0x1800085fe  jz      short loc_180008607
0x180008600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008605  jmp     short loc_18000860A
0x180008607  mov     rax, rdi
0x18000860a  mov     [rbx+80h], rax
0x180008611  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008618  test    rax, rax
0x18000861b  jz      short loc_180008625
0x18000861d  mov     rcx, rbx
0x180008620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008625  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000862c  test    rax, rax
0x18000862f  jz      short loc_180008647
0x180008631  mov     r8d, 400h
0x180008637  mov     rdx, [rsp+78h+arg_60]
0x18000863f  mov     rcx, rbx
0x180008642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008647  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000864e  test    rax, rax
0x180008651  jz      short loc_18000865B
0x180008653  mov     rcx, rbx
0x180008656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000865b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008662  test    rax, rax
0x180008665  jz      short loc_180008675
0x180008667  test    byte ptr [rbx+4], 2
0x18000866b  jnz     short loc_180008675
0x18000866d  mov     rcx, rbx
0x180008670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008675  cmp     [rbx+8], edi
0x180008678  jl      short loc_180008694
0x18000867a  cmp     r15d, 3
0x18000867e  jnz     loc_180008763
0x180008684  mov     ecx, 8000FFFFh; this
0x180008689  mov     [rbx+8], ecx
0x18000868c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008691  mov     [rbx+0Ch], eax
0x180008694  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000869b  jnz     short loc_1800086BC
0x18000869d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800086a4  test    rax, rax
0x1800086a7  jz      short loc_1800086B2
0x1800086a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086ae  test    al, al
0x1800086b0  jmp     short loc_1800086BA
0x1800086b2  call    cs:__imp_IsDebuggerPresent
0x1800086b8  test    eax, eax
0x1800086ba  jz      short loc_1800086C2
0x1800086bc  test    byte ptr [rbx+4], 2
0x1800086c0  jz      short loc_1800086E6
0x1800086c2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800086c9  test    rax, rax
0x1800086cc  jz      short loc_18000872A
0x1800086ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800086d5  jnz     short loc_18000872A
0x1800086d7  xor     r8d, r8d
0x1800086da  xor     edx, edx
0x1800086dc  mov     rcx, rbx
0x1800086df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086e4  jmp     short loc_18000872A
0x1800086e6  mov     ebp, 800h
0x1800086eb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800086f2  test    rax, rax
0x1800086f5  jz      short loc_18000870E
0x1800086f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800086fe  jnz     short loc_18000870E
0x180008700  mov     r8d, ebp
0x180008703  mov     rdx, rsi
0x180008706  mov     rcx, rbx
0x180008709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000870e  cmp     [rsi], di
0x180008711  jnz     short loc_180008721
0x180008713  mov     r8, rbx; unsigned __int64
0x180008716  mov     rdx, rbp; unsigned __int16 *
0x180008719  mov     rcx, rsi; this
0x18000871c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008721  mov     rcx, rsi; lpOutputString
0x180008724  call    cs:__imp_OutputDebugStringW
0x18000872a  test    byte ptr [rbx+4], 4
0x18000872e  jnz     short loc_180008739
0x180008730  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008737  jz      short loc_18000874B
0x180008739  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008740  test    rax, rax
0x180008743  jz      short loc_18000874B
0x180008745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000874a  nop
0x18000874b  mov     rbx, [rsp+78h+arg_10]
0x180008753  add     rsp, 40h
0x180008757  pop     r15
0x180008759  pop     r14
0x18000875b  pop     r13
0x18000875d  pop     r12
0x18000875f  pop     rdi
0x180008760  pop     rsi
0x180008761  pop     rbp
0x180008762  retn
0x180008763  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
