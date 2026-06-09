# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140008600`
- end: `0x1400088f9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x14000465c`
- `0x14000471c`
- `0x140004ad4`

## callees

- `0x14000453c`
- `0x140007224`
- `0x1400080fc`
- `0x140008600`
- `0x14000976c`
- `0x140009790`
- `0x1400098e0`
- `0x1400098fc`
- `0x14000dbf8`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008723`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008723`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140008842`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140008842`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400088b4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400088b4`

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
0x140008600  mov     [rsp+arg_10], rbx
0x140008605  mov     [rsp+arg_8], edx
0x140008609  mov     [rsp+arg_0], rcx
0x14000860e  push    rbp
0x14000860f  push    rsi
0x140008610  push    rdi
0x140008611  push    r12
0x140008613  push    r13
0x140008615  push    r14
0x140008617  push    r15
0x140008619  sub     rsp, 40h
0x14000861d  mov     r12, r9
0x140008620  mov     r13, r8
0x140008623  mov     r10, rcx
0x140008626  xor     eax, eax
0x140008628  mov     rsi, [rsp+78h+lpOutputString]
0x140008630  mov     [rsi], ax
0x140008633  mov     rax, [rsp+78h+arg_60]
0x14000863b  mov     byte ptr [rax], 0
0x14000863e  mov     r14, [rsp+78h+arg_38]
0x140008646  mov     edi, [r14]
0x140008649  mov     rbx, [rsp+78h+arg_78]
0x140008651  mov     [rbx+8], edi
0x140008654  mov     eax, [r14+4]
0x140008658  mov     [rbx+0Ch], eax
0x14000865b  xor     ebp, ebp
0x14000865d  mov     r15d, [rsp+78h+arg_30]
0x140008665  mov     ecx, r15d
0x140008668  test    r15d, r15d
0x14000866b  jz      short loc_1400086D3
0x14000866d  sub     ecx, 1
0x140008670  jz      short loc_1400086CA
0x140008672  sub     ecx, 1
0x140008675  jz      short loc_140008685
0x140008677  cmp     ecx, 1
0x14000867a  jnz     short loc_1400086DC
0x14000867c  mov     ecx, edi; this
0x14000867e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140008683  jmp     short loc_1400086DA
0x140008685  test    edi, edi
0x140008687  js      short loc_1400086C1
0x140008689  mov     edi, 8007029Ch
0x14000868e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140008692  mov     rax, [rsp+78h+arg_28]
0x14000869a  mov     [rsp+78h+var_50], rax; __int64
0x14000869f  mov     rax, [rsp+78h+arg_20]
0x1400086a7  mov     [rsp+78h+var_58], rax; __int64
0x1400086ac  mov     rcx, r10; int
0x1400086af  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400086b4  mov     [rbx+8], edi
0x1400086b7  mov     ecx, edi; this
0x1400086b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400086be  mov     [rbx+0Ch], eax
0x1400086c1  mov     ecx, edi; this
0x1400086c3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400086c8  jmp     short loc_1400086DA
0x1400086ca  mov     ecx, edi; this
0x1400086cc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400086d1  jmp     short loc_1400086DA
0x1400086d3  mov     ecx, edi; this
0x1400086d5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400086da  mov     ebp, eax
0x1400086dc  mov     [rbx], r15d
0x1400086df  mov     eax, [rsp+78h+arg_70]
0x1400086e6  mov     [rbx+4], eax
0x1400086e9  cmp     dword ptr [r14+8], 1
0x1400086ee  jnz     short loc_1400086F6
0x1400086f0  or      eax, 8
0x1400086f3  mov     [rbx+4], eax
0x1400086f6  mov     eax, 1
0x1400086fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140008703  inc     eax
0x140008705  mov     [rbx+10h], eax
0x140008708  mov     rax, [rsp+78h+arg_40]
0x140008710  xor     edi, edi
0x140008712  test    rax, rax
0x140008715  jz      short loc_14000871C
0x140008717  cmp     [rax], di
0x14000871a  jnz     short loc_14000871F
0x14000871c  mov     rax, rdi
0x14000871f  mov     [rbx+18h], rax
0x140008723  call    cs:__imp_GetCurrentThreadId
0x140008729  mov     [rbx+20h], eax
0x14000872c  mov     [rbx+38h], r13
0x140008730  mov     eax, [rsp+78h+arg_8]
0x140008737  mov     [rbx+40h], eax
0x14000873a  mov     [rbx+44h], ebp
0x14000873d  mov     rax, [rsp+78h+arg_20]
0x140008745  mov     [rbx+28h], rax
0x140008749  mov     [rbx+30h], r12
0x14000874d  mov     rax, [rsp+78h+arg_28]
0x140008755  mov     [rbx+88h], rax
0x14000875c  mov     rax, [rsp+78h+arg_0]
0x140008764  mov     [rbx+90h], rax
0x14000876b  mov     [rbx+48h], rdi
0x14000876f  xorps   xmm0, xmm0
0x140008772  xor     eax, eax
0x140008774  movups  xmmword ptr [rbx+68h], xmm0
0x140008778  mov     [rbx+78h], rax
0x14000877c  movups  xmmword ptr [rbx+50h], xmm0
0x140008780  mov     [rbx+60h], rax
0x140008784  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000878b  test    rax, rax
0x14000878e  jz      short loc_140008797
0x140008790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008795  jmp     short loc_14000879A
0x140008797  mov     rax, rdi
0x14000879a  mov     [rbx+80h], rax
0x1400087a1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400087a8  test    rax, rax
0x1400087ab  jz      short loc_1400087B5
0x1400087ad  mov     rcx, rbx
0x1400087b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400087b5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400087bc  test    rax, rax
0x1400087bf  jz      short loc_1400087D7
0x1400087c1  mov     r8d, 400h
0x1400087c7  mov     rdx, [rsp+78h+arg_60]
0x1400087cf  mov     rcx, rbx
0x1400087d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400087d7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400087de  test    rax, rax
0x1400087e1  jz      short loc_1400087EB
0x1400087e3  mov     rcx, rbx
0x1400087e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400087eb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400087f2  test    rax, rax
0x1400087f5  jz      short loc_140008805
0x1400087f7  test    byte ptr [rbx+4], 2
0x1400087fb  jnz     short loc_140008805
0x1400087fd  mov     rcx, rbx
0x140008800  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008805  cmp     [rbx+8], edi
0x140008808  jl      short loc_140008824
0x14000880a  cmp     r15d, 3
0x14000880e  jnz     loc_1400088F3
0x140008814  mov     ecx, 8000FFFFh; this
0x140008819  mov     [rbx+8], ecx
0x14000881c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140008821  mov     [rbx+0Ch], eax
0x140008824  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000882b  jnz     short loc_14000884C
0x14000882d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140008834  test    rax, rax
0x140008837  jz      short loc_140008842
0x140008839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000883e  test    al, al
0x140008840  jmp     short loc_14000884A
0x140008842  call    cs:__imp_IsDebuggerPresent
0x140008848  test    eax, eax
0x14000884a  jz      short loc_140008852
0x14000884c  test    byte ptr [rbx+4], 2
0x140008850  jz      short loc_140008876
0x140008852  mov     rax, cs:g_pfnResultLoggingCallback
0x140008859  test    rax, rax
0x14000885c  jz      short loc_1400088BA
0x14000885e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140008865  jnz     short loc_1400088BA
0x140008867  xor     r8d, r8d
0x14000886a  xor     edx, edx
0x14000886c  mov     rcx, rbx
0x14000886f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008874  jmp     short loc_1400088BA
0x140008876  mov     ebp, 800h
0x14000887b  mov     rax, cs:g_pfnResultLoggingCallback
0x140008882  test    rax, rax
0x140008885  jz      short loc_14000889E
0x140008887  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000888e  jnz     short loc_14000889E
0x140008890  mov     r8d, ebp
0x140008893  mov     rdx, rsi
0x140008896  mov     rcx, rbx
0x140008899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000889e  cmp     [rsi], di
0x1400088a1  jnz     short loc_1400088B1
0x1400088a3  mov     r8, rbx; unsigned __int64
0x1400088a6  mov     rdx, rbp; unsigned __int16 *
0x1400088a9  mov     rcx, rsi; this
0x1400088ac  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400088b1  mov     rcx, rsi; lpOutputString
0x1400088b4  call    cs:__imp_OutputDebugStringW
0x1400088ba  test    byte ptr [rbx+4], 4
0x1400088be  jnz     short loc_1400088C9
0x1400088c0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400088c7  jz      short loc_1400088DB
0x1400088c9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400088d0  test    rax, rax
0x1400088d3  jz      short loc_1400088DB
0x1400088d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400088da  nop
0x1400088db  mov     rbx, [rsp+78h+arg_10]
0x1400088e3  add     rsp, 40h
0x1400088e7  pop     r15
0x1400088e9  pop     r14
0x1400088eb  pop     r13
0x1400088ed  pop     r12
0x1400088ef  pop     rdi
0x1400088f0  pop     rsi
0x1400088f1  pop     rbp
0x1400088f2  retn
0x1400088f3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
