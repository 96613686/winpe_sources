# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001f740`
- end: `0x18001fa35`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18001cff0`
- `0x18001d0a0`
- `0x18001d194`

## callees

- `0x18001cf44`
- `0x18001e9a4`
- `0x18001f17c`
- `0x18001f740`
- `0x180020680`
- `0x1800206a0`
- `0x18002075c`
- `0x180020778`
- `0x180022588`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f863`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f863`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001f984`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001f984`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001f9f6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001f9f6`

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
0x18001f740  mov     [rsp+arg_10], rbx
0x18001f745  mov     [rsp+arg_8], edx
0x18001f749  mov     [rsp+arg_0], rcx
0x18001f74e  push    rbp
0x18001f74f  push    rsi
0x18001f750  push    rdi
0x18001f751  push    r12
0x18001f753  push    r13
0x18001f755  push    r14
0x18001f757  push    r15
0x18001f759  sub     rsp, 40h
0x18001f75d  mov     r12, r9
0x18001f760  mov     r13, r8
0x18001f763  mov     r10, rcx
0x18001f766  xor     eax, eax
0x18001f768  mov     rsi, [rsp+78h+lpOutputString]
0x18001f770  mov     [rsi], ax
0x18001f773  mov     rax, [rsp+78h+arg_60]
0x18001f77b  mov     byte ptr [rax], 0
0x18001f77e  mov     r14, [rsp+78h+arg_38]
0x18001f786  mov     edi, [r14]
0x18001f789  mov     rbx, [rsp+78h+arg_78]
0x18001f791  mov     [rbx+8], edi
0x18001f794  mov     eax, [r14+4]
0x18001f798  mov     [rbx+0Ch], eax
0x18001f79b  xor     ebp, ebp
0x18001f79d  mov     r15d, [rsp+78h+arg_30]
0x18001f7a5  mov     ecx, r15d
0x18001f7a8  test    r15d, r15d
0x18001f7ab  jz      short loc_18001F813
0x18001f7ad  sub     ecx, 1
0x18001f7b0  jz      short loc_18001F80A
0x18001f7b2  sub     ecx, 1
0x18001f7b5  jz      short loc_18001F7C5
0x18001f7b7  cmp     ecx, 1
0x18001f7ba  jnz     short loc_18001F81C
0x18001f7bc  mov     ecx, edi; this
0x18001f7be  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001f7c3  jmp     short loc_18001F81A
0x18001f7c5  test    edi, edi
0x18001f7c7  js      short loc_18001F801
0x18001f7c9  mov     edi, 8007029Ch
0x18001f7ce  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001f7d2  mov     rax, [rsp+78h+arg_28]
0x18001f7da  mov     [rsp+78h+var_50], rax; __int64
0x18001f7df  mov     rax, [rsp+78h+arg_20]
0x18001f7e7  mov     [rsp+78h+var_58], rax; __int64
0x18001f7ec  mov     rcx, r10; int
0x18001f7ef  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001f7f4  mov     [rbx+8], edi
0x18001f7f7  mov     ecx, edi; this
0x18001f7f9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001f7fe  mov     [rbx+0Ch], eax
0x18001f801  mov     ecx, edi; this
0x18001f803  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001f808  jmp     short loc_18001F81A
0x18001f80a  mov     ecx, edi; this
0x18001f80c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001f811  jmp     short loc_18001F81A
0x18001f813  mov     ecx, edi; this
0x18001f815  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001f81a  mov     ebp, eax
0x18001f81c  mov     [rbx], r15d
0x18001f81f  mov     eax, [rsp+78h+arg_70]
0x18001f826  mov     [rbx+4], eax
0x18001f829  cmp     dword ptr [r14+8], 1
0x18001f82e  jnz     short loc_18001F836
0x18001f830  or      eax, 8
0x18001f833  mov     [rbx+4], eax
0x18001f836  mov     eax, 1
0x18001f83b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001f843  inc     eax
0x18001f845  mov     [rbx+10h], eax
0x18001f848  mov     rax, [rsp+78h+arg_40]
0x18001f850  xor     edi, edi
0x18001f852  test    rax, rax
0x18001f855  jz      short loc_18001F85C
0x18001f857  cmp     [rax], di
0x18001f85a  jnz     short loc_18001F85F
0x18001f85c  mov     rax, rdi
0x18001f85f  mov     [rbx+18h], rax
0x18001f863  call    cs:__imp_GetCurrentThreadId
0x18001f869  mov     [rbx+20h], eax
0x18001f86c  mov     [rbx+38h], r13
0x18001f870  mov     eax, [rsp+78h+arg_8]
0x18001f877  mov     [rbx+40h], eax
0x18001f87a  mov     [rbx+44h], ebp
0x18001f87d  mov     rax, [rsp+78h+arg_20]
0x18001f885  mov     [rbx+28h], rax
0x18001f889  mov     [rbx+30h], r12
0x18001f88d  mov     rax, [rsp+78h+arg_28]
0x18001f895  mov     [rbx+88h], rax
0x18001f89c  mov     rax, [rsp+78h+arg_0]
0x18001f8a4  mov     [rbx+90h], rax
0x18001f8ab  mov     [rbx+48h], rdi
0x18001f8af  xorps   xmm0, xmm0
0x18001f8b2  xor     eax, eax
0x18001f8b4  movups  xmmword ptr [rbx+68h], xmm0
0x18001f8b8  mov     [rbx+78h], rax
0x18001f8bc  movups  xmmword ptr [rbx+50h], xmm0
0x18001f8c0  mov     [rbx+60h], rax
0x18001f8c4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001f8cb  test    rax, rax
0x18001f8ce  jz      short loc_18001F8D7
0x18001f8d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8d5  jmp     short loc_18001F8DA
0x18001f8d7  mov     rax, rdi
0x18001f8da  mov     [rbx+80h], rax
0x18001f8e1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001f8e8  test    rax, rax
0x18001f8eb  jz      short loc_18001F8F5
0x18001f8ed  mov     rcx, rbx
0x18001f8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8f5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001f8fc  test    rax, rax
0x18001f8ff  jz      short loc_18001F917
0x18001f901  mov     r8d, 400h
0x18001f907  mov     rdx, [rsp+78h+arg_60]
0x18001f90f  mov     rcx, rbx
0x18001f912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f917  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001f91e  test    rax, rax
0x18001f921  jz      short loc_18001F92B
0x18001f923  mov     rcx, rbx
0x18001f926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f92b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001f932  test    rax, rax
0x18001f935  jz      short loc_18001F945
0x18001f937  test    byte ptr [rbx+4], 2
0x18001f93b  jnz     short loc_18001F945
0x18001f93d  mov     rcx, rbx
0x18001f940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f945  cmp     [rbx+8], edi
0x18001f948  jl      short loc_18001F966
0x18001f94a  cmp     r15d, 3
0x18001f94e  jz      short loc_18001F956
0x18001f950  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001f956  mov     ecx, 8000FFFFh; this
0x18001f95b  mov     [rbx+8], ecx
0x18001f95e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001f963  mov     [rbx+0Ch], eax
0x18001f966  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001f96d  jnz     short loc_18001F98E
0x18001f96f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001f976  test    rax, rax
0x18001f979  jz      short loc_18001F984
0x18001f97b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f980  test    al, al
0x18001f982  jmp     short loc_18001F98C
0x18001f984  call    cs:__imp_IsDebuggerPresent
0x18001f98a  test    eax, eax
0x18001f98c  jz      short loc_18001F994
0x18001f98e  test    byte ptr [rbx+4], 2
0x18001f992  jz      short loc_18001F9B8
0x18001f994  mov     rax, cs:g_pfnResultLoggingCallback
0x18001f99b  test    rax, rax
0x18001f99e  jz      short loc_18001F9FC
0x18001f9a0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001f9a7  jnz     short loc_18001F9FC
0x18001f9a9  xor     r8d, r8d
0x18001f9ac  xor     edx, edx
0x18001f9ae  mov     rcx, rbx
0x18001f9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9b6  jmp     short loc_18001F9FC
0x18001f9b8  mov     ebp, 800h
0x18001f9bd  mov     rax, cs:g_pfnResultLoggingCallback
0x18001f9c4  test    rax, rax
0x18001f9c7  jz      short loc_18001F9E0
0x18001f9c9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001f9d0  jnz     short loc_18001F9E0
0x18001f9d2  mov     r8d, ebp
0x18001f9d5  mov     rdx, rsi
0x18001f9d8  mov     rcx, rbx
0x18001f9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9e0  cmp     [rsi], di
0x18001f9e3  jnz     short loc_18001F9F3
0x18001f9e5  mov     r8, rbx; unsigned __int64
0x18001f9e8  mov     rdx, rbp; unsigned __int16 *
0x18001f9eb  mov     rcx, rsi; this
0x18001f9ee  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001f9f3  mov     rcx, rsi; lpOutputString
0x18001f9f6  call    cs:__imp_OutputDebugStringW
0x18001f9fc  test    byte ptr [rbx+4], 4
0x18001fa00  jnz     short loc_18001FA0B
0x18001fa02  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001fa09  jz      short loc_18001FA1D
0x18001fa0b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001fa12  test    rax, rax
0x18001fa15  jz      short loc_18001FA1D
0x18001fa17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa1c  nop
0x18001fa1d  mov     rbx, [rsp+78h+arg_10]
0x18001fa25  add     rsp, 40h
0x18001fa29  pop     r15
0x18001fa2b  pop     r14
0x18001fa2d  pop     r13
0x18001fa2f  pop     r12
0x18001fa31  pop     rdi
0x18001fa32  pop     rsi
0x18001fa33  pop     rbp
0x18001fa34  retn
```
