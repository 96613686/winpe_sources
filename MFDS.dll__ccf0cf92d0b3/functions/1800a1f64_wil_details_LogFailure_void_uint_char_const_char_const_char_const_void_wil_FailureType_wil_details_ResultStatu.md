# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800a1f64`
- end: `0x1800a226f`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18009b5b4`
- `0x18009b90c`

## callees

- `0x18006e23c`
- `0x18009b4fc`
- `0x18009ed74`
- `0x1800a1f64`
- `0x1800a2cb4`
- `0x1800a2ce0`
- `0x1800a2cf4`
- `0x1800a2d14`
- `0x1800a364c`
- `0x1800c9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a2087`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a2087`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a2224`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a2224`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a21ac`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a21ac`

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
0x1800a1f64  mov     [rsp+arg_10], rbx
0x1800a1f69  mov     [rsp+arg_8], edx
0x1800a1f6d  mov     [rsp+arg_0], rcx
0x1800a1f72  push    rbp
0x1800a1f73  push    rsi
0x1800a1f74  push    rdi
0x1800a1f75  push    r12
0x1800a1f77  push    r13
0x1800a1f79  push    r14
0x1800a1f7b  push    r15
0x1800a1f7d  sub     rsp, 40h
0x1800a1f81  mov     r14, [rsp+78h+arg_38]
0x1800a1f89  xor     eax, eax
0x1800a1f8b  mov     rbx, [rsp+78h+arg_78]
0x1800a1f93  xor     ebp, ebp
0x1800a1f95  mov     r15d, [rsp+78h+arg_30]
0x1800a1f9d  mov     r10, rcx
0x1800a1fa0  mov     rsi, [rsp+78h+lpOutputString]
0x1800a1fa8  mov     r12, r9
0x1800a1fab  mov     r13, r8
0x1800a1fae  mov     ecx, r15d
0x1800a1fb1  mov     [rsi], ax
0x1800a1fb4  mov     rax, [rsp+78h+arg_60]
0x1800a1fbc  mov     byte ptr [rax], 0
0x1800a1fbf  mov     edi, [r14]
0x1800a1fc2  mov     [rbx+8], edi
0x1800a1fc5  mov     eax, [r14+4]
0x1800a1fc9  mov     [rbx+0Ch], eax
0x1800a1fcc  test    r15d, r15d
0x1800a1fcf  jz      short loc_1800A2037
0x1800a1fd1  sub     ecx, 1
0x1800a1fd4  jz      short loc_1800A202E
0x1800a1fd6  sub     ecx, 1
0x1800a1fd9  jz      short loc_1800A1FE9
0x1800a1fdb  cmp     ecx, 1
0x1800a1fde  jnz     short loc_1800A2040
0x1800a1fe0  mov     ecx, edi; this
0x1800a1fe2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800a1fe7  jmp     short loc_1800A203E
0x1800a1fe9  test    edi, edi
0x1800a1feb  js      short loc_1800A2025
0x1800a1fed  mov     rax, [rsp+78h+arg_28]
0x1800a1ff5  mov     edi, 8007029Ch
0x1800a1ffa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800a1ffe  mov     rcx, r10; int
0x1800a2001  mov     [rsp+78h+var_50], rax; __int64
0x1800a2006  mov     rax, [rsp+78h+arg_20]
0x1800a200e  mov     [rsp+78h+var_58], rax; __int64
0x1800a2013  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800a2018  mov     ecx, edi; this
0x1800a201a  mov     [rbx+8], edi
0x1800a201d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800a2022  mov     [rbx+0Ch], eax
0x1800a2025  mov     ecx, edi; this
0x1800a2027  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800a202c  jmp     short loc_1800A203E
0x1800a202e  mov     ecx, edi; this
0x1800a2030  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800a2035  jmp     short loc_1800A203E
0x1800a2037  mov     ecx, edi; this
0x1800a2039  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800a203e  mov     ebp, eax
0x1800a2040  mov     eax, [rsp+78h+arg_70]
0x1800a2047  mov     [rbx+4], eax
0x1800a204a  mov     [rbx], r15d
0x1800a204d  cmp     dword ptr [r14+8], 1
0x1800a2052  jnz     short loc_1800A205A
0x1800a2054  or      eax, 8
0x1800a2057  mov     [rbx+4], eax
0x1800a205a  mov     eax, 1
0x1800a205f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800a2067  inc     eax
0x1800a2069  xor     edi, edi
0x1800a206b  mov     [rbx+10h], eax
0x1800a206e  mov     rax, [rsp+78h+arg_40]
0x1800a2076  test    rax, rax
0x1800a2079  jz      short loc_1800A2080
0x1800a207b  cmp     [rax], di
0x1800a207e  jnz     short loc_1800A2083
0x1800a2080  mov     rax, rdi
0x1800a2083  mov     [rbx+18h], rax
0x1800a2087  call    cs:__imp_GetCurrentThreadId
0x1800a208e  nop     dword ptr [rax+rax+00h]
0x1800a2093  mov     [rbx+38h], r13
0x1800a2097  xorps   xmm0, xmm0
0x1800a209a  mov     [rbx+20h], eax
0x1800a209d  mov     eax, [rsp+78h+arg_8]
0x1800a20a4  mov     [rbx+40h], eax
0x1800a20a7  mov     rax, [rsp+78h+arg_20]
0x1800a20af  mov     [rbx+28h], rax
0x1800a20b3  mov     rax, [rsp+78h+arg_28]
0x1800a20bb  mov     [rbx+88h], rax
0x1800a20c2  mov     rax, [rsp+78h+arg_0]
0x1800a20ca  mov     [rbx+90h], rax
0x1800a20d1  xor     eax, eax
0x1800a20d3  mov     [rbx+44h], ebp
0x1800a20d6  mov     [rbx+30h], r12
0x1800a20da  mov     [rbx+48h], rdi
0x1800a20de  movups  xmmword ptr [rbx+68h], xmm0
0x1800a20e2  mov     [rbx+78h], rax
0x1800a20e6  movups  xmmword ptr [rbx+50h], xmm0
0x1800a20ea  mov     [rbx+60h], rax
0x1800a20ee  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800a20f5  test    rax, rax
0x1800a20f8  jz      short loc_1800A2101
0x1800a20fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a20ff  jmp     short loc_1800A2104
0x1800a2101  mov     rax, rdi
0x1800a2104  mov     [rbx+80h], rax
0x1800a210b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800a2112  test    rax, rax
0x1800a2115  jz      short loc_1800A211F
0x1800a2117  mov     rcx, rbx
0x1800a211a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a211f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800a2126  test    rax, rax
0x1800a2129  jz      short loc_1800A2141
0x1800a212b  mov     rdx, [rsp+78h+arg_60]
0x1800a2133  mov     r8d, 400h
0x1800a2139  mov     rcx, rbx
0x1800a213c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2141  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800a2148  test    rax, rax
0x1800a214b  jz      short loc_1800A2155
0x1800a214d  mov     rcx, rbx
0x1800a2150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2155  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800a215c  test    rax, rax
0x1800a215f  jz      short loc_1800A216F
0x1800a2161  test    byte ptr [rbx+4], 2
0x1800a2165  jnz     short loc_1800A216F
0x1800a2167  mov     rcx, rbx
0x1800a216a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a216f  cmp     [rbx+8], edi
0x1800a2172  jl      short loc_1800A218E
0x1800a2174  cmp     r15d, 3
0x1800a2178  jnz     loc_1800A2269
0x1800a217e  mov     ecx, 8000FFFFh; this
0x1800a2183  mov     [rbx+8], ecx
0x1800a2186  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800a218b  mov     [rbx+0Ch], eax
0x1800a218e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800a2195  jnz     short loc_1800A21BC
0x1800a2197  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800a219e  test    rax, rax
0x1800a21a1  jz      short loc_1800A21AC
0x1800a21a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a21a8  test    al, al
0x1800a21aa  jmp     short loc_1800A21BA
0x1800a21ac  call    cs:__imp_IsDebuggerPresent
0x1800a21b3  nop     dword ptr [rax+rax+00h]
0x1800a21b8  test    eax, eax
0x1800a21ba  jz      short loc_1800A21C2
0x1800a21bc  test    byte ptr [rbx+4], 2
0x1800a21c0  jz      short loc_1800A21E6
0x1800a21c2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a21c9  test    rax, rax
0x1800a21cc  jz      short loc_1800A2230
0x1800a21ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800a21d5  jnz     short loc_1800A2230
0x1800a21d7  xor     r8d, r8d
0x1800a21da  xor     edx, edx
0x1800a21dc  mov     rcx, rbx
0x1800a21df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a21e4  jmp     short loc_1800A2230
0x1800a21e6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a21ed  mov     ebp, 800h
0x1800a21f2  test    rax, rax
0x1800a21f5  jz      short loc_1800A220E
0x1800a21f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800a21fe  jnz     short loc_1800A220E
0x1800a2200  mov     r8d, ebp
0x1800a2203  mov     rdx, rsi
0x1800a2206  mov     rcx, rbx
0x1800a2209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a220e  cmp     [rsi], di
0x1800a2211  jnz     short loc_1800A2221
0x1800a2213  mov     r8, rbx; unsigned __int64
0x1800a2216  mov     rdx, rbp; unsigned __int16 *
0x1800a2219  mov     rcx, rsi; this
0x1800a221c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800a2221  mov     rcx, rsi; lpOutputString
0x1800a2224  call    cs:__imp_OutputDebugStringW
0x1800a222b  nop     dword ptr [rax+rax+00h]
0x1800a2230  test    byte ptr [rbx+4], 4
0x1800a2234  jnz     short loc_1800A223F
0x1800a2236  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800a223d  jz      short loc_1800A2250
0x1800a223f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800a2246  test    rax, rax
0x1800a2249  jz      short loc_1800A2250
0x1800a224b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a2250  mov     rbx, [rsp+78h+arg_10]
0x1800a2258  add     rsp, 40h
0x1800a225c  pop     r15
0x1800a225e  pop     r14
0x1800a2260  pop     r13
0x1800a2262  pop     r12
0x1800a2264  pop     rdi
0x1800a2265  pop     rsi
0x1800a2266  pop     rbp
0x1800a2267  retn
0x1800a2269  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
