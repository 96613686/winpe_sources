# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180003f64`
- end: `0x18000425d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002778`

## callees

- `0x1800021b4`
- `0x180003604`
- `0x180003da0`
- `0x180003f64`
- `0x18000449c`
- `0x1800044c0`
- `0x1800044d4`
- `0x1800044f0`
- `0x1800054ec`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004087`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004087`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004218`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004218`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800041a6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800041a6`

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
0x180003f64  mov     [rsp+arg_10], rbx
0x180003f69  mov     [rsp+arg_8], edx
0x180003f6d  mov     [rsp+arg_0], rcx
0x180003f72  push    rbp
0x180003f73  push    rsi
0x180003f74  push    rdi
0x180003f75  push    r12
0x180003f77  push    r13
0x180003f79  push    r14
0x180003f7b  push    r15
0x180003f7d  sub     rsp, 40h
0x180003f81  mov     r12, r9
0x180003f84  mov     r13, r8
0x180003f87  mov     r10, rcx
0x180003f8a  xor     eax, eax
0x180003f8c  mov     rsi, [rsp+78h+lpOutputString]
0x180003f94  mov     [rsi], ax
0x180003f97  mov     rax, [rsp+78h+arg_60]
0x180003f9f  mov     byte ptr [rax], 0
0x180003fa2  mov     r14, [rsp+78h+arg_38]
0x180003faa  mov     edi, [r14]
0x180003fad  mov     rbx, [rsp+78h+arg_78]
0x180003fb5  mov     [rbx+8], edi
0x180003fb8  mov     eax, [r14+4]
0x180003fbc  mov     [rbx+0Ch], eax
0x180003fbf  xor     ebp, ebp
0x180003fc1  mov     r15d, [rsp+78h+arg_30]
0x180003fc9  mov     ecx, r15d
0x180003fcc  test    r15d, r15d
0x180003fcf  jz      short loc_180004037
0x180003fd1  sub     ecx, 1
0x180003fd4  jz      short loc_18000402E
0x180003fd6  sub     ecx, 1
0x180003fd9  jz      short loc_180003FE9
0x180003fdb  cmp     ecx, 1
0x180003fde  jnz     short loc_180004040
0x180003fe0  mov     ecx, edi; this
0x180003fe2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180003fe7  jmp     short loc_18000403E
0x180003fe9  test    edi, edi
0x180003feb  js      short loc_180004025
0x180003fed  mov     edi, 8007029Ch
0x180003ff2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180003ff6  mov     rax, [rsp+78h+arg_28]
0x180003ffe  mov     [rsp+78h+var_50], rax; __int64
0x180004003  mov     rax, [rsp+78h+arg_20]
0x18000400b  mov     [rsp+78h+var_58], rax; __int64
0x180004010  mov     rcx, r10; int
0x180004013  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004018  mov     [rbx+8], edi
0x18000401b  mov     ecx, edi; this
0x18000401d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004022  mov     [rbx+0Ch], eax
0x180004025  mov     ecx, edi; this
0x180004027  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000402c  jmp     short loc_18000403E
0x18000402e  mov     ecx, edi; this
0x180004030  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004035  jmp     short loc_18000403E
0x180004037  mov     ecx, edi; this
0x180004039  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000403e  mov     ebp, eax
0x180004040  mov     [rbx], r15d
0x180004043  mov     eax, [rsp+78h+arg_70]
0x18000404a  mov     [rbx+4], eax
0x18000404d  cmp     dword ptr [r14+8], 1
0x180004052  jnz     short loc_18000405A
0x180004054  or      eax, 8
0x180004057  mov     [rbx+4], eax
0x18000405a  mov     eax, 1
0x18000405f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004067  inc     eax
0x180004069  mov     [rbx+10h], eax
0x18000406c  mov     rax, [rsp+78h+arg_40]
0x180004074  xor     edi, edi
0x180004076  test    rax, rax
0x180004079  jz      short loc_180004080
0x18000407b  cmp     [rax], di
0x18000407e  jnz     short loc_180004083
0x180004080  mov     rax, rdi
0x180004083  mov     [rbx+18h], rax
0x180004087  call    cs:__imp_GetCurrentThreadId
0x18000408d  mov     [rbx+20h], eax
0x180004090  mov     [rbx+38h], r13
0x180004094  mov     eax, [rsp+78h+arg_8]
0x18000409b  mov     [rbx+40h], eax
0x18000409e  mov     [rbx+44h], ebp
0x1800040a1  mov     rax, [rsp+78h+arg_20]
0x1800040a9  mov     [rbx+28h], rax
0x1800040ad  mov     [rbx+30h], r12
0x1800040b1  mov     rax, [rsp+78h+arg_28]
0x1800040b9  mov     [rbx+88h], rax
0x1800040c0  mov     rax, [rsp+78h+arg_0]
0x1800040c8  mov     [rbx+90h], rax
0x1800040cf  mov     [rbx+48h], rdi
0x1800040d3  xorps   xmm0, xmm0
0x1800040d6  xor     eax, eax
0x1800040d8  movups  xmmword ptr [rbx+68h], xmm0
0x1800040dc  mov     [rbx+78h], rax
0x1800040e0  movups  xmmword ptr [rbx+50h], xmm0
0x1800040e4  mov     [rbx+60h], rax
0x1800040e8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800040ef  test    rax, rax
0x1800040f2  jz      short loc_1800040FB
0x1800040f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040f9  jmp     short loc_1800040FE
0x1800040fb  mov     rax, rdi
0x1800040fe  mov     [rbx+80h], rax
0x180004105  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000410c  test    rax, rax
0x18000410f  jz      short loc_180004119
0x180004111  mov     rcx, rbx
0x180004114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004119  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004120  test    rax, rax
0x180004123  jz      short loc_18000413B
0x180004125  mov     r8d, 400h
0x18000412b  mov     rdx, [rsp+78h+arg_60]
0x180004133  mov     rcx, rbx
0x180004136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000413b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004142  test    rax, rax
0x180004145  jz      short loc_18000414F
0x180004147  mov     rcx, rbx
0x18000414a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000414f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004156  test    rax, rax
0x180004159  jz      short loc_180004169
0x18000415b  test    byte ptr [rbx+4], 2
0x18000415f  jnz     short loc_180004169
0x180004161  mov     rcx, rbx
0x180004164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004169  cmp     [rbx+8], edi
0x18000416c  jl      short loc_180004188
0x18000416e  cmp     r15d, 3
0x180004172  jnz     loc_180004257
0x180004178  mov     ecx, 8000FFFFh; this
0x18000417d  mov     [rbx+8], ecx
0x180004180  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004185  mov     [rbx+0Ch], eax
0x180004188  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000418f  jnz     short loc_1800041B0
0x180004191  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004198  test    rax, rax
0x18000419b  jz      short loc_1800041A6
0x18000419d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041a2  test    al, al
0x1800041a4  jmp     short loc_1800041AE
0x1800041a6  call    cs:__imp_IsDebuggerPresent
0x1800041ac  test    eax, eax
0x1800041ae  jz      short loc_1800041B6
0x1800041b0  test    byte ptr [rbx+4], 2
0x1800041b4  jz      short loc_1800041DA
0x1800041b6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800041bd  test    rax, rax
0x1800041c0  jz      short loc_18000421E
0x1800041c2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800041c9  jnz     short loc_18000421E
0x1800041cb  xor     r8d, r8d
0x1800041ce  xor     edx, edx
0x1800041d0  mov     rcx, rbx
0x1800041d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041d8  jmp     short loc_18000421E
0x1800041da  mov     ebp, 800h
0x1800041df  mov     rax, cs:g_pfnResultLoggingCallback
0x1800041e6  test    rax, rax
0x1800041e9  jz      short loc_180004202
0x1800041eb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800041f2  jnz     short loc_180004202
0x1800041f4  mov     r8d, ebp
0x1800041f7  mov     rdx, rsi
0x1800041fa  mov     rcx, rbx
0x1800041fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004202  cmp     [rsi], di
0x180004205  jnz     short loc_180004215
0x180004207  mov     r8, rbx; unsigned __int64
0x18000420a  mov     rdx, rbp; unsigned __int16 *
0x18000420d  mov     rcx, rsi; this
0x180004210  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004215  mov     rcx, rsi; lpOutputString
0x180004218  call    cs:__imp_OutputDebugStringW
0x18000421e  test    byte ptr [rbx+4], 4
0x180004222  jnz     short loc_18000422D
0x180004224  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000422b  jz      short loc_18000423F
0x18000422d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004234  test    rax, rax
0x180004237  jz      short loc_18000423F
0x180004239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000423e  nop
0x18000423f  mov     rbx, [rsp+78h+arg_10]
0x180004247  add     rsp, 40h
0x18000424b  pop     r15
0x18000424d  pop     r14
0x18000424f  pop     r13
0x180004251  pop     r12
0x180004253  pop     rdi
0x180004254  pop     rsi
0x180004255  pop     rbp
0x180004256  retn
0x180004257  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
