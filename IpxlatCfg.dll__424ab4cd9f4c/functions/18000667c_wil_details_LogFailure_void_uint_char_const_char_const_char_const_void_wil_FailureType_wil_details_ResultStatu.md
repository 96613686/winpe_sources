# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000667c`
- end: `0x180006975`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003c28`

## callees

- `0x180003664`
- `0x180005c34`
- `0x1800063d0`
- `0x18000667c`
- `0x180007330`
- `0x180007350`
- `0x18000747c`
- `0x180007498`
- `0x180009bbc`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006930`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006930`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800068be`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800068be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000679f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000679f`

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
0x18000667c  mov     [rsp+arg_10], rbx
0x180006681  mov     [rsp+arg_8], edx
0x180006685  mov     [rsp+arg_0], rcx
0x18000668a  push    rbp
0x18000668b  push    rsi
0x18000668c  push    rdi
0x18000668d  push    r12
0x18000668f  push    r13
0x180006691  push    r14
0x180006693  push    r15
0x180006695  sub     rsp, 40h
0x180006699  mov     r12, r9
0x18000669c  mov     r13, r8
0x18000669f  mov     r10, rcx
0x1800066a2  xor     eax, eax
0x1800066a4  mov     rsi, [rsp+78h+lpOutputString]
0x1800066ac  mov     [rsi], ax
0x1800066af  mov     rax, [rsp+78h+arg_60]
0x1800066b7  mov     byte ptr [rax], 0
0x1800066ba  mov     r14, [rsp+78h+arg_38]
0x1800066c2  mov     edi, [r14]
0x1800066c5  mov     rbx, [rsp+78h+arg_78]
0x1800066cd  mov     [rbx+8], edi
0x1800066d0  mov     eax, [r14+4]
0x1800066d4  mov     [rbx+0Ch], eax
0x1800066d7  xor     ebp, ebp
0x1800066d9  mov     r15d, [rsp+78h+arg_30]
0x1800066e1  mov     ecx, r15d
0x1800066e4  test    r15d, r15d
0x1800066e7  jz      short loc_18000674F
0x1800066e9  sub     ecx, 1
0x1800066ec  jz      short loc_180006746
0x1800066ee  sub     ecx, 1
0x1800066f1  jz      short loc_180006701
0x1800066f3  cmp     ecx, 1
0x1800066f6  jnz     short loc_180006758
0x1800066f8  mov     ecx, edi; this
0x1800066fa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800066ff  jmp     short loc_180006756
0x180006701  test    edi, edi
0x180006703  js      short loc_18000673D
0x180006705  mov     edi, 8007029Ch
0x18000670a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000670e  mov     rax, [rsp+78h+arg_28]
0x180006716  mov     [rsp+78h+var_50], rax; __int64
0x18000671b  mov     rax, [rsp+78h+arg_20]
0x180006723  mov     [rsp+78h+var_58], rax; __int64
0x180006728  mov     rcx, r10; int
0x18000672b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006730  mov     [rbx+8], edi
0x180006733  mov     ecx, edi; this
0x180006735  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000673a  mov     [rbx+0Ch], eax
0x18000673d  mov     ecx, edi; this
0x18000673f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006744  jmp     short loc_180006756
0x180006746  mov     ecx, edi; this
0x180006748  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000674d  jmp     short loc_180006756
0x18000674f  mov     ecx, edi; this
0x180006751  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006756  mov     ebp, eax
0x180006758  mov     [rbx], r15d
0x18000675b  mov     eax, [rsp+78h+arg_70]
0x180006762  mov     [rbx+4], eax
0x180006765  cmp     dword ptr [r14+8], 1
0x18000676a  jnz     short loc_180006772
0x18000676c  or      eax, 8
0x18000676f  mov     [rbx+4], eax
0x180006772  mov     eax, 1
0x180006777  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000677f  inc     eax
0x180006781  mov     [rbx+10h], eax
0x180006784  mov     rax, [rsp+78h+arg_40]
0x18000678c  xor     edi, edi
0x18000678e  test    rax, rax
0x180006791  jz      short loc_180006798
0x180006793  cmp     [rax], di
0x180006796  jnz     short loc_18000679B
0x180006798  mov     rax, rdi
0x18000679b  mov     [rbx+18h], rax
0x18000679f  call    cs:__imp_GetCurrentThreadId
0x1800067a5  mov     [rbx+20h], eax
0x1800067a8  mov     [rbx+38h], r13
0x1800067ac  mov     eax, [rsp+78h+arg_8]
0x1800067b3  mov     [rbx+40h], eax
0x1800067b6  mov     [rbx+44h], ebp
0x1800067b9  mov     rax, [rsp+78h+arg_20]
0x1800067c1  mov     [rbx+28h], rax
0x1800067c5  mov     [rbx+30h], r12
0x1800067c9  mov     rax, [rsp+78h+arg_28]
0x1800067d1  mov     [rbx+88h], rax
0x1800067d8  mov     rax, [rsp+78h+arg_0]
0x1800067e0  mov     [rbx+90h], rax
0x1800067e7  mov     [rbx+48h], rdi
0x1800067eb  xorps   xmm0, xmm0
0x1800067ee  xor     eax, eax
0x1800067f0  movups  xmmword ptr [rbx+68h], xmm0
0x1800067f4  mov     [rbx+78h], rax
0x1800067f8  movups  xmmword ptr [rbx+50h], xmm0
0x1800067fc  mov     [rbx+60h], rax
0x180006800  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006807  test    rax, rax
0x18000680a  jz      short loc_180006813
0x18000680c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006811  jmp     short loc_180006816
0x180006813  mov     rax, rdi
0x180006816  mov     [rbx+80h], rax
0x18000681d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006824  test    rax, rax
0x180006827  jz      short loc_180006831
0x180006829  mov     rcx, rbx
0x18000682c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006831  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006838  test    rax, rax
0x18000683b  jz      short loc_180006853
0x18000683d  mov     r8d, 400h
0x180006843  mov     rdx, [rsp+78h+arg_60]
0x18000684b  mov     rcx, rbx
0x18000684e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006853  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000685a  test    rax, rax
0x18000685d  jz      short loc_180006867
0x18000685f  mov     rcx, rbx
0x180006862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006867  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000686e  test    rax, rax
0x180006871  jz      short loc_180006881
0x180006873  test    byte ptr [rbx+4], 2
0x180006877  jnz     short loc_180006881
0x180006879  mov     rcx, rbx
0x18000687c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006881  cmp     [rbx+8], edi
0x180006884  jl      short loc_1800068A0
0x180006886  cmp     r15d, 3
0x18000688a  jnz     loc_18000696F
0x180006890  mov     ecx, 8000FFFFh; this
0x180006895  mov     [rbx+8], ecx
0x180006898  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000689d  mov     [rbx+0Ch], eax
0x1800068a0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800068a7  jnz     short loc_1800068C8
0x1800068a9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800068b0  test    rax, rax
0x1800068b3  jz      short loc_1800068BE
0x1800068b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068ba  test    al, al
0x1800068bc  jmp     short loc_1800068C6
0x1800068be  call    cs:__imp_IsDebuggerPresent
0x1800068c4  test    eax, eax
0x1800068c6  jz      short loc_1800068CE
0x1800068c8  test    byte ptr [rbx+4], 2
0x1800068cc  jz      short loc_1800068F2
0x1800068ce  mov     rax, cs:g_pfnResultLoggingCallback
0x1800068d5  test    rax, rax
0x1800068d8  jz      short loc_180006936
0x1800068da  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800068e1  jnz     short loc_180006936
0x1800068e3  xor     r8d, r8d
0x1800068e6  xor     edx, edx
0x1800068e8  mov     rcx, rbx
0x1800068eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068f0  jmp     short loc_180006936
0x1800068f2  mov     ebp, 800h
0x1800068f7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800068fe  test    rax, rax
0x180006901  jz      short loc_18000691A
0x180006903  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000690a  jnz     short loc_18000691A
0x18000690c  mov     r8d, ebp
0x18000690f  mov     rdx, rsi
0x180006912  mov     rcx, rbx
0x180006915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000691a  cmp     [rsi], di
0x18000691d  jnz     short loc_18000692D
0x18000691f  mov     r8, rbx; unsigned __int64
0x180006922  mov     rdx, rbp; unsigned __int16 *
0x180006925  mov     rcx, rsi; this
0x180006928  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000692d  mov     rcx, rsi; lpOutputString
0x180006930  call    cs:__imp_OutputDebugStringW
0x180006936  test    byte ptr [rbx+4], 4
0x18000693a  jnz     short loc_180006945
0x18000693c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006943  jz      short loc_180006957
0x180006945  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000694c  test    rax, rax
0x18000694f  jz      short loc_180006957
0x180006951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006956  nop
0x180006957  mov     rbx, [rsp+78h+arg_10]
0x18000695f  add     rsp, 40h
0x180006963  pop     r15
0x180006965  pop     r14
0x180006967  pop     r13
0x180006969  pop     r12
0x18000696b  pop     rdi
0x18000696c  pop     rsi
0x18000696d  pop     rbp
0x18000696e  retn
0x18000696f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
