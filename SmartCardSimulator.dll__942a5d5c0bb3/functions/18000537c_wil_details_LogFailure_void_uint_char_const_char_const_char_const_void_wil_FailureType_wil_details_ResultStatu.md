# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000537c`
- end: `0x180005675`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180003b44`
- `0x180003ea0`

## callees

- `0x180003a7c`
- `0x1800049e4`
- `0x1800051b8`
- `0x18000537c`
- `0x180005a44`
- `0x180005a60`
- `0x180005a74`
- `0x180005a90`
- `0x1800067b0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000549f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000549f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800055be`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800055be`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005630`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005630`

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
0x18000537c  mov     [rsp+arg_10], rbx
0x180005381  mov     [rsp+arg_8], edx
0x180005385  mov     [rsp+arg_0], rcx
0x18000538a  push    rbp
0x18000538b  push    rsi
0x18000538c  push    rdi
0x18000538d  push    r12
0x18000538f  push    r13
0x180005391  push    r14
0x180005393  push    r15
0x180005395  sub     rsp, 40h
0x180005399  mov     r12, r9
0x18000539c  mov     r13, r8
0x18000539f  mov     r10, rcx
0x1800053a2  xor     eax, eax
0x1800053a4  mov     rsi, [rsp+78h+lpOutputString]
0x1800053ac  mov     [rsi], ax
0x1800053af  mov     rax, [rsp+78h+arg_60]
0x1800053b7  mov     byte ptr [rax], 0
0x1800053ba  mov     r14, [rsp+78h+arg_38]
0x1800053c2  mov     edi, [r14]
0x1800053c5  mov     rbx, [rsp+78h+arg_78]
0x1800053cd  mov     [rbx+8], edi
0x1800053d0  mov     eax, [r14+4]
0x1800053d4  mov     [rbx+0Ch], eax
0x1800053d7  xor     ebp, ebp
0x1800053d9  mov     r15d, [rsp+78h+arg_30]
0x1800053e1  mov     ecx, r15d
0x1800053e4  test    r15d, r15d
0x1800053e7  jz      short loc_18000544F
0x1800053e9  sub     ecx, 1
0x1800053ec  jz      short loc_180005446
0x1800053ee  sub     ecx, 1
0x1800053f1  jz      short loc_180005401
0x1800053f3  cmp     ecx, 1
0x1800053f6  jnz     short loc_180005458
0x1800053f8  mov     ecx, edi; this
0x1800053fa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800053ff  jmp     short loc_180005456
0x180005401  test    edi, edi
0x180005403  js      short loc_18000543D
0x180005405  mov     edi, 8007029Ch
0x18000540a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000540e  mov     rax, [rsp+78h+arg_28]
0x180005416  mov     [rsp+78h+var_50], rax; __int64
0x18000541b  mov     rax, [rsp+78h+arg_20]
0x180005423  mov     [rsp+78h+var_58], rax; __int64
0x180005428  mov     rcx, r10; int
0x18000542b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005430  mov     [rbx+8], edi
0x180005433  mov     ecx, edi; this
0x180005435  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000543a  mov     [rbx+0Ch], eax
0x18000543d  mov     ecx, edi; this
0x18000543f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005444  jmp     short loc_180005456
0x180005446  mov     ecx, edi; this
0x180005448  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000544d  jmp     short loc_180005456
0x18000544f  mov     ecx, edi; this
0x180005451  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005456  mov     ebp, eax
0x180005458  mov     [rbx], r15d
0x18000545b  mov     eax, [rsp+78h+arg_70]
0x180005462  mov     [rbx+4], eax
0x180005465  cmp     dword ptr [r14+8], 1
0x18000546a  jnz     short loc_180005472
0x18000546c  or      eax, 8
0x18000546f  mov     [rbx+4], eax
0x180005472  mov     eax, 1
0x180005477  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000547f  inc     eax
0x180005481  mov     [rbx+10h], eax
0x180005484  mov     rax, [rsp+78h+arg_40]
0x18000548c  xor     edi, edi
0x18000548e  test    rax, rax
0x180005491  jz      short loc_180005498
0x180005493  cmp     [rax], di
0x180005496  jnz     short loc_18000549B
0x180005498  mov     rax, rdi
0x18000549b  mov     [rbx+18h], rax
0x18000549f  call    cs:__imp_GetCurrentThreadId
0x1800054a5  mov     [rbx+20h], eax
0x1800054a8  mov     [rbx+38h], r13
0x1800054ac  mov     eax, [rsp+78h+arg_8]
0x1800054b3  mov     [rbx+40h], eax
0x1800054b6  mov     [rbx+44h], ebp
0x1800054b9  mov     rax, [rsp+78h+arg_20]
0x1800054c1  mov     [rbx+28h], rax
0x1800054c5  mov     [rbx+30h], r12
0x1800054c9  mov     rax, [rsp+78h+arg_28]
0x1800054d1  mov     [rbx+88h], rax
0x1800054d8  mov     rax, [rsp+78h+arg_0]
0x1800054e0  mov     [rbx+90h], rax
0x1800054e7  mov     [rbx+48h], rdi
0x1800054eb  xorps   xmm0, xmm0
0x1800054ee  xor     eax, eax
0x1800054f0  movups  xmmword ptr [rbx+68h], xmm0
0x1800054f4  mov     [rbx+78h], rax
0x1800054f8  movups  xmmword ptr [rbx+50h], xmm0
0x1800054fc  mov     [rbx+60h], rax
0x180005500  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005507  test    rax, rax
0x18000550a  jz      short loc_180005513
0x18000550c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005511  jmp     short loc_180005516
0x180005513  mov     rax, rdi
0x180005516  mov     [rbx+80h], rax
0x18000551d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005524  test    rax, rax
0x180005527  jz      short loc_180005531
0x180005529  mov     rcx, rbx
0x18000552c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005531  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005538  test    rax, rax
0x18000553b  jz      short loc_180005553
0x18000553d  mov     r8d, 400h
0x180005543  mov     rdx, [rsp+78h+arg_60]
0x18000554b  mov     rcx, rbx
0x18000554e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005553  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000555a  test    rax, rax
0x18000555d  jz      short loc_180005567
0x18000555f  mov     rcx, rbx
0x180005562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005567  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000556e  test    rax, rax
0x180005571  jz      short loc_180005581
0x180005573  test    byte ptr [rbx+4], 2
0x180005577  jnz     short loc_180005581
0x180005579  mov     rcx, rbx
0x18000557c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005581  cmp     [rbx+8], edi
0x180005584  jl      short loc_1800055A0
0x180005586  cmp     r15d, 3
0x18000558a  jnz     loc_18000566F
0x180005590  mov     ecx, 8000FFFFh; this
0x180005595  mov     [rbx+8], ecx
0x180005598  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000559d  mov     [rbx+0Ch], eax
0x1800055a0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800055a7  jnz     short loc_1800055C8
0x1800055a9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800055b0  test    rax, rax
0x1800055b3  jz      short loc_1800055BE
0x1800055b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055ba  test    al, al
0x1800055bc  jmp     short loc_1800055C6
0x1800055be  call    cs:__imp_IsDebuggerPresent
0x1800055c4  test    eax, eax
0x1800055c6  jz      short loc_1800055CE
0x1800055c8  test    byte ptr [rbx+4], 2
0x1800055cc  jz      short loc_1800055F2
0x1800055ce  mov     rax, cs:g_pfnResultLoggingCallback
0x1800055d5  test    rax, rax
0x1800055d8  jz      short loc_180005636
0x1800055da  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800055e1  jnz     short loc_180005636
0x1800055e3  xor     r8d, r8d
0x1800055e6  xor     edx, edx
0x1800055e8  mov     rcx, rbx
0x1800055eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055f0  jmp     short loc_180005636
0x1800055f2  mov     ebp, 800h
0x1800055f7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800055fe  test    rax, rax
0x180005601  jz      short loc_18000561A
0x180005603  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000560a  jnz     short loc_18000561A
0x18000560c  mov     r8d, ebp
0x18000560f  mov     rdx, rsi
0x180005612  mov     rcx, rbx
0x180005615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000561a  cmp     [rsi], di
0x18000561d  jnz     short loc_18000562D
0x18000561f  mov     r8, rbx; unsigned __int64
0x180005622  mov     rdx, rbp; unsigned __int16 *
0x180005625  mov     rcx, rsi; this
0x180005628  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000562d  mov     rcx, rsi; lpOutputString
0x180005630  call    cs:__imp_OutputDebugStringW
0x180005636  test    byte ptr [rbx+4], 4
0x18000563a  jnz     short loc_180005645
0x18000563c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005643  jz      short loc_180005657
0x180005645  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000564c  test    rax, rax
0x18000564f  jz      short loc_180005657
0x180005651  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005656  nop
0x180005657  mov     rbx, [rsp+78h+arg_10]
0x18000565f  add     rsp, 40h
0x180005663  pop     r15
0x180005665  pop     r14
0x180005667  pop     r13
0x180005669  pop     r12
0x18000566b  pop     rdi
0x18000566c  pop     rsi
0x18000566d  pop     rbp
0x18000566e  retn
0x18000566f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
