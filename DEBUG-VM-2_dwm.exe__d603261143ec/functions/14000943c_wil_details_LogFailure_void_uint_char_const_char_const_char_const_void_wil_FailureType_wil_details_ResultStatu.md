# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000943c`
- end: `0x140009734`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140006e90`
- `0x1400071d4`

## callees

- `0x140004ba0`
- `0x140006dd0`
- `0x140008a44`
- `0x14000943c`
- `0x140009f24`
- `0x140009f40`
- `0x14000a090`
- `0x14000a0ac`
- `0x14000b874`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000955f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000955f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000967e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000967e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400096f0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400096f0`

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
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
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
0x14000943c  mov     [rsp+arg_10], rbx
0x140009441  mov     [rsp+arg_8], edx
0x140009445  mov     [rsp+arg_0], rcx
0x14000944a  push    rbp
0x14000944b  push    rsi
0x14000944c  push    rdi
0x14000944d  push    r12
0x14000944f  push    r13
0x140009451  push    r14
0x140009453  push    r15
0x140009455  sub     rsp, 40h
0x140009459  mov     r14, [rsp+78h+arg_38]
0x140009461  xor     eax, eax
0x140009463  mov     rbx, [rsp+78h+arg_78]
0x14000946b  xor     ebp, ebp
0x14000946d  mov     r15d, [rsp+78h+arg_30]
0x140009475  mov     r10, rcx
0x140009478  mov     rsi, [rsp+78h+lpOutputString]
0x140009480  mov     r12, r9
0x140009483  mov     r13, r8
0x140009486  mov     ecx, r15d
0x140009489  mov     [rsi], ax
0x14000948c  mov     rax, [rsp+78h+arg_60]
0x140009494  mov     byte ptr [rax], 0
0x140009497  mov     edi, [r14]
0x14000949a  mov     [rbx+8], edi
0x14000949d  mov     eax, [r14+4]
0x1400094a1  mov     [rbx+0Ch], eax
0x1400094a4  test    r15d, r15d
0x1400094a7  jz      short loc_14000950F
0x1400094a9  sub     ecx, 1
0x1400094ac  jz      short loc_140009506
0x1400094ae  sub     ecx, 1
0x1400094b1  jz      short loc_1400094C1
0x1400094b3  cmp     ecx, 1
0x1400094b6  jnz     short loc_140009518
0x1400094b8  mov     ecx, edi; this
0x1400094ba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400094bf  jmp     short loc_140009516
0x1400094c1  test    edi, edi
0x1400094c3  js      short loc_1400094FD
0x1400094c5  mov     rax, [rsp+78h+arg_28]
0x1400094cd  mov     edi, 8007029Ch
0x1400094d2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400094d6  mov     rcx, r10; int
0x1400094d9  mov     [rsp+78h+var_50], rax; __int64
0x1400094de  mov     rax, [rsp+78h+arg_20]
0x1400094e6  mov     [rsp+78h+var_58], rax; __int64
0x1400094eb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400094f0  mov     ecx, edi; this
0x1400094f2  mov     [rbx+8], edi
0x1400094f5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400094fa  mov     [rbx+0Ch], eax
0x1400094fd  mov     ecx, edi; this
0x1400094ff  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140009504  jmp     short loc_140009516
0x140009506  mov     ecx, edi; this
0x140009508  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000950d  jmp     short loc_140009516
0x14000950f  mov     ecx, edi; this
0x140009511  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140009516  mov     ebp, eax
0x140009518  mov     eax, [rsp+78h+arg_70]
0x14000951f  mov     [rbx+4], eax
0x140009522  mov     [rbx], r15d
0x140009525  cmp     dword ptr [r14+8], 1
0x14000952a  jnz     short loc_140009532
0x14000952c  or      eax, 8
0x14000952f  mov     [rbx+4], eax
0x140009532  mov     eax, 1
0x140009537  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000953f  inc     eax
0x140009541  xor     edi, edi
0x140009543  mov     [rbx+10h], eax
0x140009546  mov     rax, [rsp+78h+arg_40]
0x14000954e  test    rax, rax
0x140009551  jz      short loc_140009558
0x140009553  cmp     [rax], di
0x140009556  jnz     short loc_14000955B
0x140009558  mov     rax, rdi
0x14000955b  mov     [rbx+18h], rax
0x14000955f  call    cs:__imp_GetCurrentThreadId
0x140009565  mov     [rbx+38h], r13
0x140009569  xorps   xmm0, xmm0
0x14000956c  mov     [rbx+20h], eax
0x14000956f  mov     eax, [rsp+78h+arg_8]
0x140009576  mov     [rbx+40h], eax
0x140009579  mov     rax, [rsp+78h+arg_20]
0x140009581  mov     [rbx+28h], rax
0x140009585  mov     rax, [rsp+78h+arg_28]
0x14000958d  mov     [rbx+88h], rax
0x140009594  mov     rax, [rsp+78h+arg_0]
0x14000959c  mov     [rbx+90h], rax
0x1400095a3  xor     eax, eax
0x1400095a5  mov     [rbx+44h], ebp
0x1400095a8  mov     [rbx+30h], r12
0x1400095ac  mov     [rbx+48h], rdi
0x1400095b0  movups  xmmword ptr [rbx+68h], xmm0
0x1400095b4  mov     [rbx+78h], rax
0x1400095b8  movups  xmmword ptr [rbx+50h], xmm0
0x1400095bc  mov     [rbx+60h], rax
0x1400095c0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400095c7  test    rax, rax
0x1400095ca  jz      short loc_1400095D3
0x1400095cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095d1  jmp     short loc_1400095D6
0x1400095d3  mov     rax, rdi
0x1400095d6  mov     [rbx+80h], rax
0x1400095dd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400095e4  test    rax, rax
0x1400095e7  jz      short loc_1400095F1
0x1400095e9  mov     rcx, rbx
0x1400095ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400095f1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400095f8  test    rax, rax
0x1400095fb  jz      short loc_140009613
0x1400095fd  mov     rdx, [rsp+78h+arg_60]
0x140009605  mov     r8d, 400h
0x14000960b  mov     rcx, rbx
0x14000960e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009613  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000961a  test    rax, rax
0x14000961d  jz      short loc_140009627
0x14000961f  mov     rcx, rbx
0x140009622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009627  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000962e  test    rax, rax
0x140009631  jz      short loc_140009641
0x140009633  test    byte ptr [rbx+4], 2
0x140009637  jnz     short loc_140009641
0x140009639  mov     rcx, rbx
0x14000963c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009641  cmp     [rbx+8], edi
0x140009644  jl      short loc_140009660
0x140009646  cmp     r15d, 3
0x14000964a  jnz     loc_14000972E
0x140009650  mov     ecx, 8000FFFFh; this
0x140009655  mov     [rbx+8], ecx
0x140009658  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000965d  mov     [rbx+0Ch], eax
0x140009660  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140009667  jnz     short loc_140009688
0x140009669  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140009670  test    rax, rax
0x140009673  jz      short loc_14000967E
0x140009675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000967a  test    al, al
0x14000967c  jmp     short loc_140009686
0x14000967e  call    cs:__imp_IsDebuggerPresent
0x140009684  test    eax, eax
0x140009686  jz      short loc_14000968E
0x140009688  test    byte ptr [rbx+4], 2
0x14000968c  jz      short loc_1400096B2
0x14000968e  mov     rax, cs:g_pfnResultLoggingCallback
0x140009695  test    rax, rax
0x140009698  jz      short loc_1400096F6
0x14000969a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400096a1  jnz     short loc_1400096F6
0x1400096a3  xor     r8d, r8d
0x1400096a6  xor     edx, edx
0x1400096a8  mov     rcx, rbx
0x1400096ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400096b0  jmp     short loc_1400096F6
0x1400096b2  mov     rax, cs:g_pfnResultLoggingCallback
0x1400096b9  mov     ebp, 800h
0x1400096be  test    rax, rax
0x1400096c1  jz      short loc_1400096DA
0x1400096c3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400096ca  jnz     short loc_1400096DA
0x1400096cc  mov     r8d, ebp
0x1400096cf  mov     rdx, rsi
0x1400096d2  mov     rcx, rbx
0x1400096d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400096da  cmp     [rsi], di
0x1400096dd  jnz     short loc_1400096ED
0x1400096df  mov     r8, rbx; unsigned __int64
0x1400096e2  mov     rdx, rbp; unsigned __int16 *
0x1400096e5  mov     rcx, rsi; this
0x1400096e8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400096ed  mov     rcx, rsi; lpOutputString
0x1400096f0  call    cs:__imp_OutputDebugStringW
0x1400096f6  test    byte ptr [rbx+4], 4
0x1400096fa  jnz     short loc_140009705
0x1400096fc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140009703  jz      short loc_140009716
0x140009705  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000970c  test    rax, rax
0x14000970f  jz      short loc_140009716
0x140009711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009716  mov     rbx, [rsp+78h+arg_10]
0x14000971e  add     rsp, 40h
0x140009722  pop     r15
0x140009724  pop     r14
0x140009726  pop     r13
0x140009728  pop     r12
0x14000972a  pop     rdi
0x14000972b  pop     rsi
0x14000972c  pop     rbp
0x14000972d  retn
0x14000972e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
