# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800aaf1c`
- end: `0x1800ab211`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800a8510`
- `0x1800a85c0`
- `0x1800a86b4`

## callees

- `0x1800a8464`
- `0x1800aa334`
- `0x1800aab40`
- `0x1800aaf1c`
- `0x1800abcc8`
- `0x1800abcf0`
- `0x1800abdac`
- `0x1800abdc8`
- `0x1800adab8`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ab03f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ab03f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ab160`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ab160`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ab1d2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ab1d2`

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
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x1800aaf1c  mov     [rsp+arg_10], rbx
0x1800aaf21  mov     [rsp+arg_8], edx
0x1800aaf25  mov     [rsp+arg_0], rcx
0x1800aaf2a  push    rbp
0x1800aaf2b  push    rsi
0x1800aaf2c  push    rdi
0x1800aaf2d  push    r12
0x1800aaf2f  push    r13
0x1800aaf31  push    r14
0x1800aaf33  push    r15
0x1800aaf35  sub     rsp, 40h
0x1800aaf39  mov     r12, r9
0x1800aaf3c  mov     r13, r8
0x1800aaf3f  mov     r10, rcx
0x1800aaf42  xor     eax, eax
0x1800aaf44  mov     rsi, [rsp+78h+lpOutputString]
0x1800aaf4c  mov     [rsi], ax
0x1800aaf4f  mov     rax, [rsp+78h+arg_60]
0x1800aaf57  mov     byte ptr [rax], 0
0x1800aaf5a  mov     r14, [rsp+78h+arg_38]
0x1800aaf62  mov     edi, [r14]
0x1800aaf65  mov     rbx, [rsp+78h+arg_78]
0x1800aaf6d  mov     [rbx+8], edi
0x1800aaf70  mov     eax, [r14+4]
0x1800aaf74  mov     [rbx+0Ch], eax
0x1800aaf77  xor     ebp, ebp
0x1800aaf79  mov     r15d, [rsp+78h+arg_30]
0x1800aaf81  mov     ecx, r15d
0x1800aaf84  test    r15d, r15d
0x1800aaf87  jz      short loc_1800AAFEF
0x1800aaf89  sub     ecx, 1
0x1800aaf8c  jz      short loc_1800AAFE6
0x1800aaf8e  sub     ecx, 1
0x1800aaf91  jz      short loc_1800AAFA1
0x1800aaf93  cmp     ecx, 1
0x1800aaf96  jnz     short loc_1800AAFF8
0x1800aaf98  mov     ecx, edi; this
0x1800aaf9a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800aaf9f  jmp     short loc_1800AAFF6
0x1800aafa1  test    edi, edi
0x1800aafa3  js      short loc_1800AAFDD
0x1800aafa5  mov     edi, 8007029Ch
0x1800aafaa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800aafae  mov     rax, [rsp+78h+arg_28]
0x1800aafb6  mov     [rsp+78h+var_50], rax; __int64
0x1800aafbb  mov     rax, [rsp+78h+arg_20]
0x1800aafc3  mov     [rsp+78h+var_58], rax; __int64
0x1800aafc8  mov     rcx, r10; int
0x1800aafcb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800aafd0  mov     [rbx+8], edi
0x1800aafd3  mov     ecx, edi; this
0x1800aafd5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800aafda  mov     [rbx+0Ch], eax
0x1800aafdd  mov     ecx, edi; this
0x1800aafdf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800aafe4  jmp     short loc_1800AAFF6
0x1800aafe6  mov     ecx, edi; this
0x1800aafe8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800aafed  jmp     short loc_1800AAFF6
0x1800aafef  mov     ecx, edi; this
0x1800aaff1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800aaff6  mov     ebp, eax
0x1800aaff8  mov     [rbx], r15d
0x1800aaffb  mov     eax, [rsp+78h+arg_70]
0x1800ab002  mov     [rbx+4], eax
0x1800ab005  cmp     dword ptr [r14+8], 1
0x1800ab00a  jnz     short loc_1800AB012
0x1800ab00c  or      eax, 8
0x1800ab00f  mov     [rbx+4], eax
0x1800ab012  mov     eax, 1
0x1800ab017  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800ab01f  inc     eax
0x1800ab021  mov     [rbx+10h], eax
0x1800ab024  mov     rax, [rsp+78h+arg_40]
0x1800ab02c  xor     edi, edi
0x1800ab02e  test    rax, rax
0x1800ab031  jz      short loc_1800AB038
0x1800ab033  cmp     [rax], di
0x1800ab036  jnz     short loc_1800AB03B
0x1800ab038  mov     rax, rdi
0x1800ab03b  mov     [rbx+18h], rax
0x1800ab03f  call    cs:__imp_GetCurrentThreadId
0x1800ab045  mov     [rbx+20h], eax
0x1800ab048  mov     [rbx+38h], r13
0x1800ab04c  mov     eax, [rsp+78h+arg_8]
0x1800ab053  mov     [rbx+40h], eax
0x1800ab056  mov     [rbx+44h], ebp
0x1800ab059  mov     rax, [rsp+78h+arg_20]
0x1800ab061  mov     [rbx+28h], rax
0x1800ab065  mov     [rbx+30h], r12
0x1800ab069  mov     rax, [rsp+78h+arg_28]
0x1800ab071  mov     [rbx+88h], rax
0x1800ab078  mov     rax, [rsp+78h+arg_0]
0x1800ab080  mov     [rbx+90h], rax
0x1800ab087  mov     [rbx+48h], rdi
0x1800ab08b  xorps   xmm0, xmm0
0x1800ab08e  xor     eax, eax
0x1800ab090  movups  xmmword ptr [rbx+68h], xmm0
0x1800ab094  mov     [rbx+78h], rax
0x1800ab098  movups  xmmword ptr [rbx+50h], xmm0
0x1800ab09c  mov     [rbx+60h], rax
0x1800ab0a0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800ab0a7  test    rax, rax
0x1800ab0aa  jz      short loc_1800AB0B3
0x1800ab0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab0b1  jmp     short loc_1800AB0B6
0x1800ab0b3  mov     rax, rdi
0x1800ab0b6  mov     [rbx+80h], rax
0x1800ab0bd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800ab0c4  test    rax, rax
0x1800ab0c7  jz      short loc_1800AB0D1
0x1800ab0c9  mov     rcx, rbx
0x1800ab0cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab0d1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800ab0d8  test    rax, rax
0x1800ab0db  jz      short loc_1800AB0F3
0x1800ab0dd  mov     r8d, 400h
0x1800ab0e3  mov     rdx, [rsp+78h+arg_60]
0x1800ab0eb  mov     rcx, rbx
0x1800ab0ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab0f3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800ab0fa  test    rax, rax
0x1800ab0fd  jz      short loc_1800AB107
0x1800ab0ff  mov     rcx, rbx
0x1800ab102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab107  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800ab10e  test    rax, rax
0x1800ab111  jz      short loc_1800AB121
0x1800ab113  test    byte ptr [rbx+4], 2
0x1800ab117  jnz     short loc_1800AB121
0x1800ab119  mov     rcx, rbx
0x1800ab11c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab121  cmp     [rbx+8], edi
0x1800ab124  jl      short loc_1800AB142
0x1800ab126  cmp     r15d, 3
0x1800ab12a  jz      short loc_1800AB132
0x1800ab12c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800ab132  mov     ecx, 8000FFFFh; this
0x1800ab137  mov     [rbx+8], ecx
0x1800ab13a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800ab13f  mov     [rbx+0Ch], eax
0x1800ab142  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800ab149  jnz     short loc_1800AB16A
0x1800ab14b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800ab152  test    rax, rax
0x1800ab155  jz      short loc_1800AB160
0x1800ab157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab15c  test    al, al
0x1800ab15e  jmp     short loc_1800AB168
0x1800ab160  call    cs:__imp_IsDebuggerPresent
0x1800ab166  test    eax, eax
0x1800ab168  jz      short loc_1800AB170
0x1800ab16a  test    byte ptr [rbx+4], 2
0x1800ab16e  jz      short loc_1800AB194
0x1800ab170  mov     rax, cs:g_pfnResultLoggingCallback
0x1800ab177  test    rax, rax
0x1800ab17a  jz      short loc_1800AB1D8
0x1800ab17c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800ab183  jnz     short loc_1800AB1D8
0x1800ab185  xor     r8d, r8d
0x1800ab188  xor     edx, edx
0x1800ab18a  mov     rcx, rbx
0x1800ab18d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab192  jmp     short loc_1800AB1D8
0x1800ab194  mov     ebp, 800h
0x1800ab199  mov     rax, cs:g_pfnResultLoggingCallback
0x1800ab1a0  test    rax, rax
0x1800ab1a3  jz      short loc_1800AB1BC
0x1800ab1a5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800ab1ac  jnz     short loc_1800AB1BC
0x1800ab1ae  mov     r8d, ebp
0x1800ab1b1  mov     rdx, rsi
0x1800ab1b4  mov     rcx, rbx
0x1800ab1b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab1bc  cmp     [rsi], di
0x1800ab1bf  jnz     short loc_1800AB1CF
0x1800ab1c1  mov     r8, rbx; unsigned __int64
0x1800ab1c4  mov     rdx, rbp; wchar_t *
0x1800ab1c7  mov     rcx, rsi; this
0x1800ab1ca  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800ab1cf  mov     rcx, rsi; lpOutputString
0x1800ab1d2  call    cs:__imp_OutputDebugStringW
0x1800ab1d8  test    byte ptr [rbx+4], 4
0x1800ab1dc  jnz     short loc_1800AB1E7
0x1800ab1de  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800ab1e5  jz      short loc_1800AB1F9
0x1800ab1e7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800ab1ee  test    rax, rax
0x1800ab1f1  jz      short loc_1800AB1F9
0x1800ab1f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ab1f8  nop
0x1800ab1f9  mov     rbx, [rsp+78h+arg_10]
0x1800ab201  add     rsp, 40h
0x1800ab205  pop     r15
0x1800ab207  pop     r14
0x1800ab209  pop     r13
0x1800ab20b  pop     r12
0x1800ab20d  pop     rdi
0x1800ab20e  pop     rsi
0x1800ab20f  pop     rbp
0x1800ab210  retn
```
