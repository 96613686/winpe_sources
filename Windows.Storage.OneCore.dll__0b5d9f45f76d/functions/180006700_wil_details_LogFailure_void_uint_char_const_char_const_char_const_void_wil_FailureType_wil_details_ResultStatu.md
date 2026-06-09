# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006700`
- end: `0x1800069f9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180003f78`
- `0x1800042e4`
- `0x18000ab18`

## callees

- `0x180003eb0`
- `0x180005a94`
- `0x180006318`
- `0x180006700`
- `0x1800075d8`
- `0x180007600`
- `0x180007750`
- `0x18000776c`
- `0x180009510`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006823`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006823`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800069b4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800069b4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006942`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006942`

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
0x180006700  mov     [rsp+arg_10], rbx
0x180006705  mov     [rsp+arg_8], edx
0x180006709  mov     [rsp+arg_0], rcx
0x18000670e  push    rbp
0x18000670f  push    rsi
0x180006710  push    rdi
0x180006711  push    r12
0x180006713  push    r13
0x180006715  push    r14
0x180006717  push    r15
0x180006719  sub     rsp, 40h
0x18000671d  mov     r12, r9
0x180006720  mov     r13, r8
0x180006723  mov     r10, rcx
0x180006726  xor     eax, eax
0x180006728  mov     rsi, [rsp+78h+lpOutputString]
0x180006730  mov     [rsi], ax
0x180006733  mov     rax, [rsp+78h+arg_60]
0x18000673b  mov     byte ptr [rax], 0
0x18000673e  mov     r14, [rsp+78h+arg_38]
0x180006746  mov     edi, [r14]
0x180006749  mov     rbx, [rsp+78h+arg_78]
0x180006751  mov     [rbx+8], edi
0x180006754  mov     eax, [r14+4]
0x180006758  mov     [rbx+0Ch], eax
0x18000675b  xor     ebp, ebp
0x18000675d  mov     r15d, [rsp+78h+arg_30]
0x180006765  mov     ecx, r15d
0x180006768  test    r15d, r15d
0x18000676b  jz      short loc_1800067D3
0x18000676d  sub     ecx, 1
0x180006770  jz      short loc_1800067CA
0x180006772  sub     ecx, 1
0x180006775  jz      short loc_180006785
0x180006777  cmp     ecx, 1
0x18000677a  jnz     short loc_1800067DC
0x18000677c  mov     ecx, edi; this
0x18000677e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006783  jmp     short loc_1800067DA
0x180006785  test    edi, edi
0x180006787  js      short loc_1800067C1
0x180006789  mov     edi, 8007029Ch
0x18000678e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006792  mov     rax, [rsp+78h+arg_28]
0x18000679a  mov     [rsp+78h+var_50], rax; __int64
0x18000679f  mov     rax, [rsp+78h+arg_20]
0x1800067a7  mov     [rsp+78h+var_58], rax; __int64
0x1800067ac  mov     rcx, r10; int
0x1800067af  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800067b4  mov     [rbx+8], edi
0x1800067b7  mov     ecx, edi; this
0x1800067b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800067be  mov     [rbx+0Ch], eax
0x1800067c1  mov     ecx, edi; this
0x1800067c3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800067c8  jmp     short loc_1800067DA
0x1800067ca  mov     ecx, edi; this
0x1800067cc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800067d1  jmp     short loc_1800067DA
0x1800067d3  mov     ecx, edi; this
0x1800067d5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800067da  mov     ebp, eax
0x1800067dc  mov     [rbx], r15d
0x1800067df  mov     eax, [rsp+78h+arg_70]
0x1800067e6  mov     [rbx+4], eax
0x1800067e9  cmp     dword ptr [r14+8], 1
0x1800067ee  jnz     short loc_1800067F6
0x1800067f0  or      eax, 8
0x1800067f3  mov     [rbx+4], eax
0x1800067f6  mov     eax, 1
0x1800067fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006803  inc     eax
0x180006805  mov     [rbx+10h], eax
0x180006808  mov     rax, [rsp+78h+arg_40]
0x180006810  xor     edi, edi
0x180006812  test    rax, rax
0x180006815  jz      short loc_18000681C
0x180006817  cmp     [rax], di
0x18000681a  jnz     short loc_18000681F
0x18000681c  mov     rax, rdi
0x18000681f  mov     [rbx+18h], rax
0x180006823  call    cs:__imp_GetCurrentThreadId
0x180006829  mov     [rbx+20h], eax
0x18000682c  mov     [rbx+38h], r13
0x180006830  mov     eax, [rsp+78h+arg_8]
0x180006837  mov     [rbx+40h], eax
0x18000683a  mov     [rbx+44h], ebp
0x18000683d  mov     rax, [rsp+78h+arg_20]
0x180006845  mov     [rbx+28h], rax
0x180006849  mov     [rbx+30h], r12
0x18000684d  mov     rax, [rsp+78h+arg_28]
0x180006855  mov     [rbx+88h], rax
0x18000685c  mov     rax, [rsp+78h+arg_0]
0x180006864  mov     [rbx+90h], rax
0x18000686b  mov     [rbx+48h], rdi
0x18000686f  xorps   xmm0, xmm0
0x180006872  xor     eax, eax
0x180006874  movups  xmmword ptr [rbx+68h], xmm0
0x180006878  mov     [rbx+78h], rax
0x18000687c  movups  xmmword ptr [rbx+50h], xmm0
0x180006880  mov     [rbx+60h], rax
0x180006884  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000688b  test    rax, rax
0x18000688e  jz      short loc_180006897
0x180006890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006895  jmp     short loc_18000689A
0x180006897  mov     rax, rdi
0x18000689a  mov     [rbx+80h], rax
0x1800068a1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800068a8  test    rax, rax
0x1800068ab  jz      short loc_1800068B5
0x1800068ad  mov     rcx, rbx
0x1800068b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068b5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800068bc  test    rax, rax
0x1800068bf  jz      short loc_1800068D7
0x1800068c1  mov     r8d, 400h
0x1800068c7  mov     rdx, [rsp+78h+arg_60]
0x1800068cf  mov     rcx, rbx
0x1800068d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068d7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800068de  test    rax, rax
0x1800068e1  jz      short loc_1800068EB
0x1800068e3  mov     rcx, rbx
0x1800068e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068eb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800068f2  test    rax, rax
0x1800068f5  jz      short loc_180006905
0x1800068f7  test    byte ptr [rbx+4], 2
0x1800068fb  jnz     short loc_180006905
0x1800068fd  mov     rcx, rbx
0x180006900  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006905  cmp     [rbx+8], edi
0x180006908  jl      short loc_180006924
0x18000690a  cmp     r15d, 3
0x18000690e  jnz     loc_1800069F3
0x180006914  mov     ecx, 8000FFFFh; this
0x180006919  mov     [rbx+8], ecx
0x18000691c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006921  mov     [rbx+0Ch], eax
0x180006924  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000692b  jnz     short loc_18000694C
0x18000692d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006934  test    rax, rax
0x180006937  jz      short loc_180006942
0x180006939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000693e  test    al, al
0x180006940  jmp     short loc_18000694A
0x180006942  call    cs:__imp_IsDebuggerPresent
0x180006948  test    eax, eax
0x18000694a  jz      short loc_180006952
0x18000694c  test    byte ptr [rbx+4], 2
0x180006950  jz      short loc_180006976
0x180006952  mov     rax, cs:g_pfnResultLoggingCallback
0x180006959  test    rax, rax
0x18000695c  jz      short loc_1800069BA
0x18000695e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006965  jnz     short loc_1800069BA
0x180006967  xor     r8d, r8d
0x18000696a  xor     edx, edx
0x18000696c  mov     rcx, rbx
0x18000696f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006974  jmp     short loc_1800069BA
0x180006976  mov     ebp, 800h
0x18000697b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006982  test    rax, rax
0x180006985  jz      short loc_18000699E
0x180006987  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000698e  jnz     short loc_18000699E
0x180006990  mov     r8d, ebp
0x180006993  mov     rdx, rsi
0x180006996  mov     rcx, rbx
0x180006999  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000699e  cmp     [rsi], di
0x1800069a1  jnz     short loc_1800069B1
0x1800069a3  mov     r8, rbx; unsigned __int64
0x1800069a6  mov     rdx, rbp; unsigned __int16 *
0x1800069a9  mov     rcx, rsi; this
0x1800069ac  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800069b1  mov     rcx, rsi; lpOutputString
0x1800069b4  call    cs:__imp_OutputDebugStringW
0x1800069ba  test    byte ptr [rbx+4], 4
0x1800069be  jnz     short loc_1800069C9
0x1800069c0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800069c7  jz      short loc_1800069DB
0x1800069c9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800069d0  test    rax, rax
0x1800069d3  jz      short loc_1800069DB
0x1800069d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069da  nop
0x1800069db  mov     rbx, [rsp+78h+arg_10]
0x1800069e3  add     rsp, 40h
0x1800069e7  pop     r15
0x1800069e9  pop     r14
0x1800069eb  pop     r13
0x1800069ed  pop     r12
0x1800069ef  pop     rdi
0x1800069f0  pop     rsi
0x1800069f1  pop     rbp
0x1800069f2  retn
0x1800069f3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
