# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000823c`
- end: `0x18000853d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000518c`

## callees

- `0x180004b84`
- `0x1800075f4`
- `0x180007f7c`
- `0x18000823c`
- `0x180009014`
- `0x180009030`
- `0x18000916c`
- `0x180009188`
- `0x18000bf6c`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008367`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008367`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800084f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800084f8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008486`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008486`

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
  wil::details *v26; // [rsp+30h] [rbp-58h]

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v23);
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
0x18000823c  mov     rax, rsp
0x18000823f  mov     [rax+10h], edx
0x180008242  mov     [rax+8], rcx
0x180008246  push    rbp
0x180008247  push    rsi
0x180008248  push    rdi
0x180008249  push    r12
0x18000824b  push    r13
0x18000824d  push    r14
0x18000824f  push    r15
0x180008251  sub     rsp, 50h
0x180008255  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18000825d  mov     [rax+18h], rbx
0x180008261  mov     r12, r9
0x180008264  mov     r13, r8
0x180008267  mov     r10, rcx
0x18000826a  xor     eax, eax
0x18000826c  mov     rsi, [rsp+88h+lpOutputString]
0x180008274  mov     [rsi], ax
0x180008277  mov     rax, [rsp+88h+arg_60]
0x18000827f  mov     byte ptr [rax], 0
0x180008282  mov     r14, [rsp+88h+arg_38]
0x18000828a  mov     edi, [r14]
0x18000828d  mov     rbx, [rsp+88h+arg_78]
0x180008295  mov     [rbx+8], edi
0x180008298  mov     eax, [r14+4]
0x18000829c  mov     [rbx+0Ch], eax
0x18000829f  xor     ebp, ebp
0x1800082a1  mov     r15d, [rsp+88h+arg_30]
0x1800082a9  mov     ecx, r15d
0x1800082ac  test    r15d, r15d
0x1800082af  jz      short loc_180008317
0x1800082b1  sub     ecx, 1
0x1800082b4  jz      short loc_18000830E
0x1800082b6  sub     ecx, 1
0x1800082b9  jz      short loc_1800082C9
0x1800082bb  cmp     ecx, 1
0x1800082be  jnz     short loc_180008320
0x1800082c0  mov     ecx, edi; this
0x1800082c2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800082c7  jmp     short loc_18000831E
0x1800082c9  test    edi, edi
0x1800082cb  js      short loc_180008305
0x1800082cd  mov     edi, 8007029Ch
0x1800082d2  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x1800082d6  mov     rax, [rsp+88h+arg_28]
0x1800082de  mov     [rsp+88h+var_60], rax; __int64
0x1800082e3  mov     rax, [rsp+88h+arg_20]
0x1800082eb  mov     [rsp+88h+var_68], rax; __int64
0x1800082f0  mov     rcx, r10; int
0x1800082f3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800082f8  mov     [rbx+8], edi
0x1800082fb  mov     ecx, edi; this
0x1800082fd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008302  mov     [rbx+0Ch], eax
0x180008305  mov     ecx, edi; this
0x180008307  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000830c  jmp     short loc_18000831E
0x18000830e  mov     ecx, edi; this
0x180008310  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008315  jmp     short loc_18000831E
0x180008317  mov     ecx, edi; this
0x180008319  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000831e  mov     ebp, eax
0x180008320  mov     [rbx], r15d
0x180008323  mov     eax, [rsp+88h+arg_70]
0x18000832a  mov     [rbx+4], eax
0x18000832d  cmp     dword ptr [r14+8], 1
0x180008332  jnz     short loc_18000833A
0x180008334  or      eax, 8
0x180008337  mov     [rbx+4], eax
0x18000833a  mov     eax, 1
0x18000833f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008347  inc     eax
0x180008349  mov     [rbx+10h], eax
0x18000834c  mov     rax, [rsp+88h+arg_40]
0x180008354  xor     edi, edi
0x180008356  test    rax, rax
0x180008359  jz      short loc_180008360
0x18000835b  cmp     [rax], di
0x18000835e  jnz     short loc_180008363
0x180008360  mov     rax, rdi
0x180008363  mov     [rbx+18h], rax
0x180008367  call    cs:__imp_GetCurrentThreadId
0x18000836d  mov     [rbx+20h], eax
0x180008370  mov     [rbx+38h], r13
0x180008374  mov     eax, [rsp+88h+arg_8]
0x18000837b  mov     [rbx+40h], eax
0x18000837e  mov     [rbx+44h], ebp
0x180008381  mov     rax, [rsp+88h+arg_20]
0x180008389  mov     [rbx+28h], rax
0x18000838d  mov     [rbx+30h], r12
0x180008391  mov     rax, [rsp+88h+arg_28]
0x180008399  mov     [rbx+88h], rax
0x1800083a0  mov     rax, [rsp+88h+arg_0]
0x1800083a8  mov     [rbx+90h], rax
0x1800083af  mov     [rbx+48h], rdi
0x1800083b3  xorps   xmm0, xmm0
0x1800083b6  xor     eax, eax
0x1800083b8  movups  xmmword ptr [rbx+68h], xmm0
0x1800083bc  mov     [rbx+78h], rax
0x1800083c0  movups  xmmword ptr [rbx+50h], xmm0
0x1800083c4  mov     [rbx+60h], rax
0x1800083c8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800083cf  test    rax, rax
0x1800083d2  jz      short loc_1800083DB
0x1800083d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083d9  jmp     short loc_1800083DE
0x1800083db  mov     rax, rdi
0x1800083de  mov     [rbx+80h], rax
0x1800083e5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800083ec  test    rax, rax
0x1800083ef  jz      short loc_1800083F9
0x1800083f1  mov     rcx, rbx
0x1800083f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083f9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008400  test    rax, rax
0x180008403  jz      short loc_18000841B
0x180008405  mov     r8d, 400h
0x18000840b  mov     rdx, [rsp+88h+arg_60]
0x180008413  mov     rcx, rbx
0x180008416  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000841b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008422  test    rax, rax
0x180008425  jz      short loc_18000842F
0x180008427  mov     rcx, rbx
0x18000842a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000842f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008436  test    rax, rax
0x180008439  jz      short loc_180008449
0x18000843b  test    byte ptr [rbx+4], 2
0x18000843f  jnz     short loc_180008449
0x180008441  mov     rcx, rbx
0x180008444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008449  cmp     [rbx+8], edi
0x18000844c  jl      short loc_180008468
0x18000844e  cmp     r15d, 3
0x180008452  jnz     loc_180008537
0x180008458  mov     ecx, 8000FFFFh; this
0x18000845d  mov     [rbx+8], ecx
0x180008460  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008465  mov     [rbx+0Ch], eax
0x180008468  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000846f  jnz     short loc_180008490
0x180008471  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008478  test    rax, rax
0x18000847b  jz      short loc_180008486
0x18000847d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008482  test    al, al
0x180008484  jmp     short loc_18000848E
0x180008486  call    cs:__imp_IsDebuggerPresent
0x18000848c  test    eax, eax
0x18000848e  jz      short loc_180008496
0x180008490  test    byte ptr [rbx+4], 2
0x180008494  jz      short loc_1800084BA
0x180008496  mov     rax, cs:g_pfnResultLoggingCallback
0x18000849d  test    rax, rax
0x1800084a0  jz      short loc_1800084FE
0x1800084a2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800084a9  jnz     short loc_1800084FE
0x1800084ab  xor     r8d, r8d
0x1800084ae  xor     edx, edx
0x1800084b0  mov     rcx, rbx
0x1800084b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084b8  jmp     short loc_1800084FE
0x1800084ba  mov     ebp, 800h
0x1800084bf  mov     rax, cs:g_pfnResultLoggingCallback
0x1800084c6  test    rax, rax
0x1800084c9  jz      short loc_1800084E2
0x1800084cb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800084d2  jnz     short loc_1800084E2
0x1800084d4  mov     r8d, ebp
0x1800084d7  mov     rdx, rsi
0x1800084da  mov     rcx, rbx
0x1800084dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084e2  cmp     [rsi], di
0x1800084e5  jnz     short loc_1800084F5
0x1800084e7  mov     r8, rbx; unsigned __int64
0x1800084ea  mov     rdx, rbp; wchar_t *
0x1800084ed  mov     rcx, rsi; this
0x1800084f0  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800084f5  mov     rcx, rsi; lpOutputString
0x1800084f8  call    cs:__imp_OutputDebugStringW
0x1800084fe  test    byte ptr [rbx+4], 4
0x180008502  jnz     short loc_18000850D
0x180008504  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000850b  jz      short loc_18000851F
0x18000850d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008514  test    rax, rax
0x180008517  jz      short loc_18000851F
0x180008519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000851e  nop
0x18000851f  mov     rbx, [rsp+88h+arg_10]
0x180008527  add     rsp, 50h
0x18000852b  pop     r15
0x18000852d  pop     r14
0x18000852f  pop     r13
0x180008531  pop     r12
0x180008533  pop     rdi
0x180008534  pop     rsi
0x180008535  pop     rbp
0x180008536  retn
0x180008537  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
