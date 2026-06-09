# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006270`
- end: `0x180006569`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180005cd0`
- `0x180005d90`
- `0x180006148`

## callees

- `0x180004214`
- `0x180004650`
- `0x180004b70`
- `0x180005c08`
- `0x180006270`
- `0x180006570`
- `0x18000658c`
- `0x1800065a8`
- `0x1800066fc`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006393`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006393`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006524`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006524`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800064b2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800064b2`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
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
0x180006270  mov     [rsp+arg_10], rbx
0x180006275  mov     [rsp+arg_8], edx
0x180006279  mov     [rsp+arg_0], rcx
0x18000627e  push    rbp
0x18000627f  push    rsi
0x180006280  push    rdi
0x180006281  push    r12
0x180006283  push    r13
0x180006285  push    r14
0x180006287  push    r15
0x180006289  sub     rsp, 40h
0x18000628d  mov     r12, r9
0x180006290  mov     r13, r8
0x180006293  mov     r10, rcx
0x180006296  xor     eax, eax
0x180006298  mov     rsi, [rsp+78h+lpOutputString]
0x1800062a0  mov     [rsi], ax
0x1800062a3  mov     rax, [rsp+78h+arg_60]
0x1800062ab  mov     byte ptr [rax], 0
0x1800062ae  mov     r14, [rsp+78h+arg_38]
0x1800062b6  mov     edi, [r14]
0x1800062b9  mov     rbx, [rsp+78h+arg_78]
0x1800062c1  mov     [rbx+8], edi
0x1800062c4  mov     eax, [r14+4]
0x1800062c8  mov     [rbx+0Ch], eax
0x1800062cb  xor     ebp, ebp
0x1800062cd  mov     r15d, [rsp+78h+arg_30]
0x1800062d5  mov     ecx, r15d
0x1800062d8  test    r15d, r15d
0x1800062db  jz      short loc_180006343
0x1800062dd  sub     ecx, 1
0x1800062e0  jz      short loc_18000633A
0x1800062e2  sub     ecx, 1
0x1800062e5  jz      short loc_1800062F5
0x1800062e7  cmp     ecx, 1
0x1800062ea  jnz     short loc_18000634C
0x1800062ec  mov     ecx, edi; this
0x1800062ee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800062f3  jmp     short loc_18000634A
0x1800062f5  test    edi, edi
0x1800062f7  js      short loc_180006331
0x1800062f9  mov     edi, 8007029Ch
0x1800062fe  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006302  mov     rax, [rsp+78h+arg_28]
0x18000630a  mov     [rsp+78h+var_50], rax; __int64
0x18000630f  mov     rax, [rsp+78h+arg_20]
0x180006317  mov     [rsp+78h+var_58], rax; __int64
0x18000631c  mov     rcx, r10; int
0x18000631f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006324  mov     [rbx+8], edi
0x180006327  mov     ecx, edi; this
0x180006329  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000632e  mov     [rbx+0Ch], eax
0x180006331  mov     ecx, edi; this
0x180006333  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006338  jmp     short loc_18000634A
0x18000633a  mov     ecx, edi; this
0x18000633c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006341  jmp     short loc_18000634A
0x180006343  mov     ecx, edi; this
0x180006345  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000634a  mov     ebp, eax
0x18000634c  mov     [rbx], r15d
0x18000634f  mov     eax, [rsp+78h+arg_70]
0x180006356  mov     [rbx+4], eax
0x180006359  cmp     dword ptr [r14+8], 1
0x18000635e  jnz     short loc_180006366
0x180006360  or      eax, 8
0x180006363  mov     [rbx+4], eax
0x180006366  mov     eax, 1
0x18000636b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006373  inc     eax
0x180006375  mov     [rbx+10h], eax
0x180006378  mov     rax, [rsp+78h+arg_40]
0x180006380  xor     edi, edi
0x180006382  test    rax, rax
0x180006385  jz      short loc_18000638C
0x180006387  cmp     [rax], di
0x18000638a  jnz     short loc_18000638F
0x18000638c  mov     rax, rdi
0x18000638f  mov     [rbx+18h], rax
0x180006393  call    cs:__imp_GetCurrentThreadId
0x180006399  mov     [rbx+20h], eax
0x18000639c  mov     [rbx+38h], r13
0x1800063a0  mov     eax, [rsp+78h+arg_8]
0x1800063a7  mov     [rbx+40h], eax
0x1800063aa  mov     [rbx+44h], ebp
0x1800063ad  mov     rax, [rsp+78h+arg_20]
0x1800063b5  mov     [rbx+28h], rax
0x1800063b9  mov     [rbx+30h], r12
0x1800063bd  mov     rax, [rsp+78h+arg_28]
0x1800063c5  mov     [rbx+88h], rax
0x1800063cc  mov     rax, [rsp+78h+arg_0]
0x1800063d4  mov     [rbx+90h], rax
0x1800063db  mov     [rbx+48h], rdi
0x1800063df  xorps   xmm0, xmm0
0x1800063e2  xor     eax, eax
0x1800063e4  movups  xmmword ptr [rbx+68h], xmm0
0x1800063e8  mov     [rbx+78h], rax
0x1800063ec  movups  xmmword ptr [rbx+50h], xmm0
0x1800063f0  mov     [rbx+60h], rax
0x1800063f4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800063fb  test    rax, rax
0x1800063fe  jz      short loc_180006407
0x180006400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006405  jmp     short loc_18000640A
0x180006407  mov     rax, rdi
0x18000640a  mov     [rbx+80h], rax
0x180006411  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006418  test    rax, rax
0x18000641b  jz      short loc_180006425
0x18000641d  mov     rcx, rbx
0x180006420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006425  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000642c  test    rax, rax
0x18000642f  jz      short loc_180006447
0x180006431  mov     r8d, 400h
0x180006437  mov     rdx, [rsp+78h+arg_60]
0x18000643f  mov     rcx, rbx
0x180006442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006447  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000644e  test    rax, rax
0x180006451  jz      short loc_18000645B
0x180006453  mov     rcx, rbx
0x180006456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000645b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006462  test    rax, rax
0x180006465  jz      short loc_180006475
0x180006467  test    byte ptr [rbx+4], 2
0x18000646b  jnz     short loc_180006475
0x18000646d  mov     rcx, rbx
0x180006470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006475  cmp     [rbx+8], edi
0x180006478  jl      short loc_180006494
0x18000647a  cmp     r15d, 3
0x18000647e  jnz     loc_180006563
0x180006484  mov     ecx, 8000FFFFh; this
0x180006489  mov     [rbx+8], ecx
0x18000648c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006491  mov     [rbx+0Ch], eax
0x180006494  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000649b  jnz     short loc_1800064BC
0x18000649d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800064a4  test    rax, rax
0x1800064a7  jz      short loc_1800064B2
0x1800064a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064ae  test    al, al
0x1800064b0  jmp     short loc_1800064BA
0x1800064b2  call    cs:__imp_IsDebuggerPresent
0x1800064b8  test    eax, eax
0x1800064ba  jz      short loc_1800064C2
0x1800064bc  test    byte ptr [rbx+4], 2
0x1800064c0  jz      short loc_1800064E6
0x1800064c2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800064c9  test    rax, rax
0x1800064cc  jz      short loc_18000652A
0x1800064ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800064d5  jnz     short loc_18000652A
0x1800064d7  xor     r8d, r8d
0x1800064da  xor     edx, edx
0x1800064dc  mov     rcx, rbx
0x1800064df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e4  jmp     short loc_18000652A
0x1800064e6  mov     ebp, 800h
0x1800064eb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800064f2  test    rax, rax
0x1800064f5  jz      short loc_18000650E
0x1800064f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800064fe  jnz     short loc_18000650E
0x180006500  mov     r8d, ebp
0x180006503  mov     rdx, rsi
0x180006506  mov     rcx, rbx
0x180006509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000650e  cmp     [rsi], di
0x180006511  jnz     short loc_180006521
0x180006513  mov     r8, rbx; unsigned __int64
0x180006516  mov     rdx, rbp; unsigned __int16 *
0x180006519  mov     rcx, rsi; this
0x18000651c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006521  mov     rcx, rsi; lpOutputString
0x180006524  call    cs:__imp_OutputDebugStringW
0x18000652a  test    byte ptr [rbx+4], 4
0x18000652e  jnz     short loc_180006539
0x180006530  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006537  jz      short loc_18000654B
0x180006539  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006540  test    rax, rax
0x180006543  jz      short loc_18000654B
0x180006545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000654a  nop
0x18000654b  mov     rbx, [rsp+78h+arg_10]
0x180006553  add     rsp, 40h
0x180006557  pop     r15
0x180006559  pop     r14
0x18000655b  pop     r13
0x18000655d  pop     r12
0x18000655f  pop     rdi
0x180006560  pop     rsi
0x180006561  pop     rbp
0x180006562  retn
0x180006563  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
