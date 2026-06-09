# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005388`
- end: `0x180005681`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003b44`

## callees

- `0x180003588`
- `0x180004a24`
- `0x1800051c4`
- `0x180005388`
- `0x1800058cc`
- `0x1800058f0`
- `0x180005904`
- `0x180005920`
- `0x1800069ac`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800054ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800054ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000563c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000563c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800055ca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800055ca`

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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x180005388  mov     [rsp+arg_10], rbx
0x18000538d  mov     [rsp+arg_8], edx
0x180005391  mov     [rsp+arg_0], rcx
0x180005396  push    rbp
0x180005397  push    rsi
0x180005398  push    rdi
0x180005399  push    r12
0x18000539b  push    r13
0x18000539d  push    r14
0x18000539f  push    r15
0x1800053a1  sub     rsp, 40h
0x1800053a5  mov     r12, r9
0x1800053a8  mov     r13, r8
0x1800053ab  mov     r10, rcx
0x1800053ae  xor     eax, eax
0x1800053b0  mov     rsi, [rsp+78h+lpOutputString]
0x1800053b8  mov     [rsi], ax
0x1800053bb  mov     rax, [rsp+78h+arg_60]
0x1800053c3  mov     byte ptr [rax], 0
0x1800053c6  mov     r14, [rsp+78h+arg_38]
0x1800053ce  mov     edi, [r14]
0x1800053d1  mov     rbx, [rsp+78h+arg_78]
0x1800053d9  mov     [rbx+8], edi
0x1800053dc  mov     eax, [r14+4]
0x1800053e0  mov     [rbx+0Ch], eax
0x1800053e3  xor     ebp, ebp
0x1800053e5  mov     r15d, [rsp+78h+arg_30]
0x1800053ed  mov     ecx, r15d
0x1800053f0  test    r15d, r15d
0x1800053f3  jz      short loc_18000545B
0x1800053f5  sub     ecx, 1
0x1800053f8  jz      short loc_180005452
0x1800053fa  sub     ecx, 1
0x1800053fd  jz      short loc_18000540D
0x1800053ff  cmp     ecx, 1
0x180005402  jnz     short loc_180005464
0x180005404  mov     ecx, edi; this
0x180005406  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000540b  jmp     short loc_180005462
0x18000540d  test    edi, edi
0x18000540f  js      short loc_180005449
0x180005411  mov     edi, 8007029Ch
0x180005416  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000541a  mov     rax, [rsp+78h+arg_28]
0x180005422  mov     [rsp+78h+var_50], rax; __int64
0x180005427  mov     rax, [rsp+78h+arg_20]
0x18000542f  mov     [rsp+78h+var_58], rax; __int64
0x180005434  mov     rcx, r10; int
0x180005437  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000543c  mov     [rbx+8], edi
0x18000543f  mov     ecx, edi; this
0x180005441  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005446  mov     [rbx+0Ch], eax
0x180005449  mov     ecx, edi; this
0x18000544b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005450  jmp     short loc_180005462
0x180005452  mov     ecx, edi; this
0x180005454  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005459  jmp     short loc_180005462
0x18000545b  mov     ecx, edi; this
0x18000545d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005462  mov     ebp, eax
0x180005464  mov     [rbx], r15d
0x180005467  mov     eax, [rsp+78h+arg_70]
0x18000546e  mov     [rbx+4], eax
0x180005471  cmp     dword ptr [r14+8], 1
0x180005476  jnz     short loc_18000547E
0x180005478  or      eax, 8
0x18000547b  mov     [rbx+4], eax
0x18000547e  mov     eax, 1
0x180005483  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000548b  inc     eax
0x18000548d  mov     [rbx+10h], eax
0x180005490  mov     rax, [rsp+78h+arg_40]
0x180005498  xor     edi, edi
0x18000549a  test    rax, rax
0x18000549d  jz      short loc_1800054A4
0x18000549f  cmp     [rax], di
0x1800054a2  jnz     short loc_1800054A7
0x1800054a4  mov     rax, rdi
0x1800054a7  mov     [rbx+18h], rax
0x1800054ab  call    cs:__imp_GetCurrentThreadId
0x1800054b1  mov     [rbx+20h], eax
0x1800054b4  mov     [rbx+38h], r13
0x1800054b8  mov     eax, [rsp+78h+arg_8]
0x1800054bf  mov     [rbx+40h], eax
0x1800054c2  mov     [rbx+44h], ebp
0x1800054c5  mov     rax, [rsp+78h+arg_20]
0x1800054cd  mov     [rbx+28h], rax
0x1800054d1  mov     [rbx+30h], r12
0x1800054d5  mov     rax, [rsp+78h+arg_28]
0x1800054dd  mov     [rbx+88h], rax
0x1800054e4  mov     rax, [rsp+78h+arg_0]
0x1800054ec  mov     [rbx+90h], rax
0x1800054f3  mov     [rbx+48h], rdi
0x1800054f7  xorps   xmm0, xmm0
0x1800054fa  xor     eax, eax
0x1800054fc  movups  xmmword ptr [rbx+68h], xmm0
0x180005500  mov     [rbx+78h], rax
0x180005504  movups  xmmword ptr [rbx+50h], xmm0
0x180005508  mov     [rbx+60h], rax
0x18000550c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005513  test    rax, rax
0x180005516  jz      short loc_18000551F
0x180005518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000551d  jmp     short loc_180005522
0x18000551f  mov     rax, rdi
0x180005522  mov     [rbx+80h], rax
0x180005529  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005530  test    rax, rax
0x180005533  jz      short loc_18000553D
0x180005535  mov     rcx, rbx
0x180005538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000553d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005544  test    rax, rax
0x180005547  jz      short loc_18000555F
0x180005549  mov     r8d, 400h
0x18000554f  mov     rdx, [rsp+78h+arg_60]
0x180005557  mov     rcx, rbx
0x18000555a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000555f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005566  test    rax, rax
0x180005569  jz      short loc_180005573
0x18000556b  mov     rcx, rbx
0x18000556e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005573  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000557a  test    rax, rax
0x18000557d  jz      short loc_18000558D
0x18000557f  test    byte ptr [rbx+4], 2
0x180005583  jnz     short loc_18000558D
0x180005585  mov     rcx, rbx
0x180005588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000558d  cmp     [rbx+8], edi
0x180005590  jl      short loc_1800055AC
0x180005592  cmp     r15d, 3
0x180005596  jnz     loc_18000567B
0x18000559c  mov     ecx, 8000FFFFh; this
0x1800055a1  mov     [rbx+8], ecx
0x1800055a4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800055a9  mov     [rbx+0Ch], eax
0x1800055ac  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800055b3  jnz     short loc_1800055D4
0x1800055b5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800055bc  test    rax, rax
0x1800055bf  jz      short loc_1800055CA
0x1800055c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055c6  test    al, al
0x1800055c8  jmp     short loc_1800055D2
0x1800055ca  call    cs:__imp_IsDebuggerPresent
0x1800055d0  test    eax, eax
0x1800055d2  jz      short loc_1800055DA
0x1800055d4  test    byte ptr [rbx+4], 2
0x1800055d8  jz      short loc_1800055FE
0x1800055da  mov     rax, cs:g_pfnResultLoggingCallback
0x1800055e1  test    rax, rax
0x1800055e4  jz      short loc_180005642
0x1800055e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800055ed  jnz     short loc_180005642
0x1800055ef  xor     r8d, r8d
0x1800055f2  xor     edx, edx
0x1800055f4  mov     rcx, rbx
0x1800055f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055fc  jmp     short loc_180005642
0x1800055fe  mov     ebp, 800h
0x180005603  mov     rax, cs:g_pfnResultLoggingCallback
0x18000560a  test    rax, rax
0x18000560d  jz      short loc_180005626
0x18000560f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005616  jnz     short loc_180005626
0x180005618  mov     r8d, ebp
0x18000561b  mov     rdx, rsi
0x18000561e  mov     rcx, rbx
0x180005621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005626  cmp     [rsi], di
0x180005629  jnz     short loc_180005639
0x18000562b  mov     r8, rbx; unsigned __int64
0x18000562e  mov     rdx, rbp; unsigned __int16 *
0x180005631  mov     rcx, rsi; this
0x180005634  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005639  mov     rcx, rsi; lpOutputString
0x18000563c  call    cs:__imp_OutputDebugStringW
0x180005642  test    byte ptr [rbx+4], 4
0x180005646  jnz     short loc_180005651
0x180005648  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000564f  jz      short loc_180005663
0x180005651  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005658  test    rax, rax
0x18000565b  jz      short loc_180005663
0x18000565d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005662  nop
0x180005663  mov     rbx, [rsp+78h+arg_10]
0x18000566b  add     rsp, 40h
0x18000566f  pop     r15
0x180005671  pop     r14
0x180005673  pop     r13
0x180005675  pop     r12
0x180005677  pop     rdi
0x180005678  pop     rsi
0x180005679  pop     rbp
0x18000567a  retn
0x18000567b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
