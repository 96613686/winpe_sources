# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006248`
- end: `0x180006541`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180005500`
- `0x18000586c`
- `0x1800088f8`

## callees

- `0x180005498`
- `0x180005dc8`
- `0x180006084`
- `0x180006248`
- `0x1800066b8`
- `0x1800066e0`
- `0x1800066f4`
- `0x180006710`
- `0x180006e44`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000636b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000636b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000648a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000648a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800064fc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800064fc`

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
      wil::details::in1diag3::FailFastImmediate_Unexpected(v24);
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
0x180006248  mov     [rsp+arg_10], rbx
0x18000624d  mov     [rsp+arg_8], edx
0x180006251  mov     [rsp+arg_0], rcx
0x180006256  push    rbp
0x180006257  push    rsi
0x180006258  push    rdi
0x180006259  push    r12
0x18000625b  push    r13
0x18000625d  push    r14
0x18000625f  push    r15
0x180006261  sub     rsp, 40h
0x180006265  mov     r12, r9
0x180006268  mov     r13, r8
0x18000626b  mov     r10, rcx
0x18000626e  xor     eax, eax
0x180006270  mov     rsi, [rsp+78h+lpOutputString]
0x180006278  mov     [rsi], ax
0x18000627b  mov     rax, [rsp+78h+arg_60]
0x180006283  mov     byte ptr [rax], 0
0x180006286  mov     r14, [rsp+78h+arg_38]
0x18000628e  mov     edi, [r14]
0x180006291  mov     rbx, [rsp+78h+arg_78]
0x180006299  mov     [rbx+8], edi
0x18000629c  mov     eax, [r14+4]
0x1800062a0  mov     [rbx+0Ch], eax
0x1800062a3  xor     ebp, ebp
0x1800062a5  mov     r15d, [rsp+78h+arg_30]
0x1800062ad  mov     ecx, r15d
0x1800062b0  test    r15d, r15d
0x1800062b3  jz      short loc_18000631B
0x1800062b5  sub     ecx, 1
0x1800062b8  jz      short loc_180006312
0x1800062ba  sub     ecx, 1
0x1800062bd  jz      short loc_1800062CD
0x1800062bf  cmp     ecx, 1
0x1800062c2  jnz     short loc_180006324
0x1800062c4  mov     ecx, edi; this
0x1800062c6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800062cb  jmp     short loc_180006322
0x1800062cd  test    edi, edi
0x1800062cf  js      short loc_180006309
0x1800062d1  mov     edi, 8007029Ch
0x1800062d6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800062da  mov     rax, [rsp+78h+arg_28]
0x1800062e2  mov     [rsp+78h+var_50], rax; __int64
0x1800062e7  mov     rax, [rsp+78h+arg_20]
0x1800062ef  mov     [rsp+78h+var_58], rax; __int64
0x1800062f4  mov     rcx, r10; int
0x1800062f7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800062fc  mov     [rbx+8], edi
0x1800062ff  mov     ecx, edi; this
0x180006301  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006306  mov     [rbx+0Ch], eax
0x180006309  mov     ecx, edi; this
0x18000630b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006310  jmp     short loc_180006322
0x180006312  mov     ecx, edi; this
0x180006314  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006319  jmp     short loc_180006322
0x18000631b  mov     ecx, edi; this
0x18000631d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006322  mov     ebp, eax
0x180006324  mov     [rbx], r15d
0x180006327  mov     eax, [rsp+78h+arg_70]
0x18000632e  mov     [rbx+4], eax
0x180006331  cmp     dword ptr [r14+8], 1
0x180006336  jnz     short loc_18000633E
0x180006338  or      eax, 8
0x18000633b  mov     [rbx+4], eax
0x18000633e  mov     eax, 1
0x180006343  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000634b  inc     eax
0x18000634d  mov     [rbx+10h], eax
0x180006350  mov     rax, [rsp+78h+arg_40]
0x180006358  xor     edi, edi
0x18000635a  test    rax, rax
0x18000635d  jz      short loc_180006364
0x18000635f  cmp     [rax], di
0x180006362  jnz     short loc_180006367
0x180006364  mov     rax, rdi
0x180006367  mov     [rbx+18h], rax
0x18000636b  call    cs:__imp_GetCurrentThreadId
0x180006371  mov     [rbx+20h], eax
0x180006374  mov     [rbx+38h], r13
0x180006378  mov     eax, [rsp+78h+arg_8]
0x18000637f  mov     [rbx+40h], eax
0x180006382  mov     [rbx+44h], ebp
0x180006385  mov     rax, [rsp+78h+arg_20]
0x18000638d  mov     [rbx+28h], rax
0x180006391  mov     [rbx+30h], r12
0x180006395  mov     rax, [rsp+78h+arg_28]
0x18000639d  mov     [rbx+88h], rax
0x1800063a4  mov     rax, [rsp+78h+arg_0]
0x1800063ac  mov     [rbx+90h], rax
0x1800063b3  mov     [rbx+48h], rdi
0x1800063b7  xorps   xmm0, xmm0
0x1800063ba  xor     eax, eax
0x1800063bc  movups  xmmword ptr [rbx+68h], xmm0
0x1800063c0  mov     [rbx+78h], rax
0x1800063c4  movups  xmmword ptr [rbx+50h], xmm0
0x1800063c8  mov     [rbx+60h], rax
0x1800063cc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800063d3  test    rax, rax
0x1800063d6  jz      short loc_1800063DF
0x1800063d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063dd  jmp     short loc_1800063E2
0x1800063df  mov     rax, rdi
0x1800063e2  mov     [rbx+80h], rax
0x1800063e9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800063f0  test    rax, rax
0x1800063f3  jz      short loc_1800063FD
0x1800063f5  mov     rcx, rbx
0x1800063f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063fd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006404  test    rax, rax
0x180006407  jz      short loc_18000641F
0x180006409  mov     r8d, 400h
0x18000640f  mov     rdx, [rsp+78h+arg_60]
0x180006417  mov     rcx, rbx
0x18000641a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000641f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006426  test    rax, rax
0x180006429  jz      short loc_180006433
0x18000642b  mov     rcx, rbx
0x18000642e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006433  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000643a  test    rax, rax
0x18000643d  jz      short loc_18000644D
0x18000643f  test    byte ptr [rbx+4], 2
0x180006443  jnz     short loc_18000644D
0x180006445  mov     rcx, rbx
0x180006448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000644d  cmp     [rbx+8], edi
0x180006450  jl      short loc_18000646C
0x180006452  cmp     r15d, 3
0x180006456  jnz     loc_18000653B
0x18000645c  mov     ecx, 8000FFFFh; this
0x180006461  mov     [rbx+8], ecx
0x180006464  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006469  mov     [rbx+0Ch], eax
0x18000646c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006473  jnz     short loc_180006494
0x180006475  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000647c  test    rax, rax
0x18000647f  jz      short loc_18000648A
0x180006481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006486  test    al, al
0x180006488  jmp     short loc_180006492
0x18000648a  call    cs:__imp_IsDebuggerPresent
0x180006490  test    eax, eax
0x180006492  jz      short loc_18000649A
0x180006494  test    byte ptr [rbx+4], 2
0x180006498  jz      short loc_1800064BE
0x18000649a  mov     rax, cs:g_pfnResultLoggingCallback
0x1800064a1  test    rax, rax
0x1800064a4  jz      short loc_180006502
0x1800064a6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800064ad  jnz     short loc_180006502
0x1800064af  xor     r8d, r8d
0x1800064b2  xor     edx, edx
0x1800064b4  mov     rcx, rbx
0x1800064b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064bc  jmp     short loc_180006502
0x1800064be  mov     ebp, 800h
0x1800064c3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800064ca  test    rax, rax
0x1800064cd  jz      short loc_1800064E6
0x1800064cf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800064d6  jnz     short loc_1800064E6
0x1800064d8  mov     r8d, ebp
0x1800064db  mov     rdx, rsi
0x1800064de  mov     rcx, rbx
0x1800064e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e6  cmp     [rsi], di
0x1800064e9  jnz     short loc_1800064F9
0x1800064eb  mov     r8, rbx; unsigned __int64
0x1800064ee  mov     rdx, rbp; unsigned __int16 *
0x1800064f1  mov     rcx, rsi; this
0x1800064f4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800064f9  mov     rcx, rsi; lpOutputString
0x1800064fc  call    cs:__imp_OutputDebugStringW
0x180006502  test    byte ptr [rbx+4], 4
0x180006506  jnz     short loc_180006511
0x180006508  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000650f  jz      short loc_180006523
0x180006511  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006518  test    rax, rax
0x18000651b  jz      short loc_180006523
0x18000651d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006522  nop
0x180006523  mov     rbx, [rsp+78h+arg_10]
0x18000652b  add     rsp, 40h
0x18000652f  pop     r15
0x180006531  pop     r14
0x180006533  pop     r13
0x180006535  pop     r12
0x180006537  pop     rdi
0x180006538  pop     rsi
0x180006539  pop     rbp
0x18000653a  retn
0x18000653b  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
