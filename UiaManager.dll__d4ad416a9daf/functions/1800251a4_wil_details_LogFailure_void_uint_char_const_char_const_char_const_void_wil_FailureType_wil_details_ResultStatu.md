# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800251a4`
- end: `0x180025499`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180012f98`
- `0x180024d5c`
- `0x1800250a8`
- `0x18002a32c`

## callees

- `0x180010218`
- `0x180011f0c`
- `0x1800130b4`
- `0x180024ca4`
- `0x1800251a4`
- `0x1800254a0`
- `0x18004b3f8`
- `0x18004c3ac`
- `0x18004d9d4`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800252c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800252c7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800253e8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800253e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002545a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002545a`

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
0x1800251a4  mov     [rsp+arg_10], rbx
0x1800251a9  mov     [rsp+arg_8], edx
0x1800251ad  mov     [rsp+arg_0], rcx
0x1800251b2  push    rbp
0x1800251b3  push    rsi
0x1800251b4  push    rdi
0x1800251b5  push    r12
0x1800251b7  push    r13
0x1800251b9  push    r14
0x1800251bb  push    r15
0x1800251bd  sub     rsp, 40h
0x1800251c1  mov     r12, r9
0x1800251c4  mov     r13, r8
0x1800251c7  mov     r10, rcx
0x1800251ca  xor     eax, eax
0x1800251cc  mov     rsi, [rsp+78h+lpOutputString]
0x1800251d4  mov     [rsi], ax
0x1800251d7  mov     rax, [rsp+78h+arg_60]
0x1800251df  mov     byte ptr [rax], 0
0x1800251e2  mov     r14, [rsp+78h+arg_38]
0x1800251ea  mov     edi, [r14]
0x1800251ed  mov     rbx, [rsp+78h+arg_78]
0x1800251f5  mov     [rbx+8], edi
0x1800251f8  mov     eax, [r14+4]
0x1800251fc  mov     [rbx+0Ch], eax
0x1800251ff  xor     ebp, ebp
0x180025201  mov     r15d, [rsp+78h+arg_30]
0x180025209  mov     ecx, r15d
0x18002520c  test    r15d, r15d
0x18002520f  jz      short loc_180025277
0x180025211  sub     ecx, 1
0x180025214  jz      short loc_18002526E
0x180025216  sub     ecx, 1
0x180025219  jz      short loc_180025229
0x18002521b  cmp     ecx, 1
0x18002521e  jnz     short loc_180025280
0x180025220  mov     ecx, edi; this
0x180025222  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180025227  jmp     short loc_18002527E
0x180025229  test    edi, edi
0x18002522b  js      short loc_180025265
0x18002522d  mov     edi, 8007029Ch
0x180025232  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180025236  mov     rax, [rsp+78h+arg_28]
0x18002523e  mov     [rsp+78h+var_50], rax; __int64
0x180025243  mov     rax, [rsp+78h+arg_20]
0x18002524b  mov     [rsp+78h+var_58], rax; __int64
0x180025250  mov     rcx, r10; int
0x180025253  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180025258  mov     [rbx+8], edi
0x18002525b  mov     ecx, edi; this
0x18002525d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180025262  mov     [rbx+0Ch], eax
0x180025265  mov     ecx, edi; this
0x180025267  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18002526c  jmp     short loc_18002527E
0x18002526e  mov     ecx, edi; this
0x180025270  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180025275  jmp     short loc_18002527E
0x180025277  mov     ecx, edi; this
0x180025279  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002527e  mov     ebp, eax
0x180025280  mov     [rbx], r15d
0x180025283  mov     eax, [rsp+78h+arg_70]
0x18002528a  mov     [rbx+4], eax
0x18002528d  cmp     dword ptr [r14+8], 1
0x180025292  jnz     short loc_18002529A
0x180025294  or      eax, 8
0x180025297  mov     [rbx+4], eax
0x18002529a  mov     eax, 1
0x18002529f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800252a7  inc     eax
0x1800252a9  mov     [rbx+10h], eax
0x1800252ac  mov     rax, [rsp+78h+arg_40]
0x1800252b4  xor     edi, edi
0x1800252b6  test    rax, rax
0x1800252b9  jz      short loc_1800252C0
0x1800252bb  cmp     [rax], di
0x1800252be  jnz     short loc_1800252C3
0x1800252c0  mov     rax, rdi
0x1800252c3  mov     [rbx+18h], rax
0x1800252c7  call    cs:__imp_GetCurrentThreadId
0x1800252cd  mov     [rbx+20h], eax
0x1800252d0  mov     [rbx+38h], r13
0x1800252d4  mov     eax, [rsp+78h+arg_8]
0x1800252db  mov     [rbx+40h], eax
0x1800252de  mov     [rbx+44h], ebp
0x1800252e1  mov     rax, [rsp+78h+arg_20]
0x1800252e9  mov     [rbx+28h], rax
0x1800252ed  mov     [rbx+30h], r12
0x1800252f1  mov     rax, [rsp+78h+arg_28]
0x1800252f9  mov     [rbx+88h], rax
0x180025300  mov     rax, [rsp+78h+arg_0]
0x180025308  mov     [rbx+90h], rax
0x18002530f  mov     [rbx+48h], rdi
0x180025313  xorps   xmm0, xmm0
0x180025316  xor     eax, eax
0x180025318  movups  xmmword ptr [rbx+68h], xmm0
0x18002531c  mov     [rbx+78h], rax
0x180025320  movups  xmmword ptr [rbx+50h], xmm0
0x180025324  mov     [rbx+60h], rax
0x180025328  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002532f  test    rax, rax
0x180025332  jz      short loc_18002533B
0x180025334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025339  jmp     short loc_18002533E
0x18002533b  mov     rax, rdi
0x18002533e  mov     [rbx+80h], rax
0x180025345  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002534c  test    rax, rax
0x18002534f  jz      short loc_180025359
0x180025351  mov     rcx, rbx
0x180025354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025359  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180025360  test    rax, rax
0x180025363  jz      short loc_18002537B
0x180025365  mov     r8d, 400h
0x18002536b  mov     rdx, [rsp+78h+arg_60]
0x180025373  mov     rcx, rbx
0x180025376  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002537b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025382  test    rax, rax
0x180025385  jz      short loc_18002538F
0x180025387  mov     rcx, rbx
0x18002538a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002538f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025396  test    rax, rax
0x180025399  jz      short loc_1800253A9
0x18002539b  test    byte ptr [rbx+4], 2
0x18002539f  jnz     short loc_1800253A9
0x1800253a1  mov     rcx, rbx
0x1800253a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253a9  cmp     [rbx+8], edi
0x1800253ac  jl      short loc_1800253CA
0x1800253ae  cmp     r15d, 3
0x1800253b2  jz      short loc_1800253BA
0x1800253b4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800253ba  mov     ecx, 8000FFFFh; this
0x1800253bf  mov     [rbx+8], ecx
0x1800253c2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800253c7  mov     [rbx+0Ch], eax
0x1800253ca  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800253d1  jnz     short loc_1800253F2
0x1800253d3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800253da  test    rax, rax
0x1800253dd  jz      short loc_1800253E8
0x1800253df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800253e4  test    al, al
0x1800253e6  jmp     short loc_1800253F0
0x1800253e8  call    cs:__imp_IsDebuggerPresent
0x1800253ee  test    eax, eax
0x1800253f0  jz      short loc_1800253F8
0x1800253f2  test    byte ptr [rbx+4], 2
0x1800253f6  jz      short loc_18002541C
0x1800253f8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800253ff  test    rax, rax
0x180025402  jz      short loc_180025460
0x180025404  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002540b  jnz     short loc_180025460
0x18002540d  xor     r8d, r8d
0x180025410  xor     edx, edx
0x180025412  mov     rcx, rbx
0x180025415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002541a  jmp     short loc_180025460
0x18002541c  mov     ebp, 800h
0x180025421  mov     rax, cs:g_pfnResultLoggingCallback
0x180025428  test    rax, rax
0x18002542b  jz      short loc_180025444
0x18002542d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180025434  jnz     short loc_180025444
0x180025436  mov     r8d, ebp
0x180025439  mov     rdx, rsi
0x18002543c  mov     rcx, rbx
0x18002543f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025444  cmp     [rsi], di
0x180025447  jnz     short loc_180025457
0x180025449  mov     r8, rbx; unsigned __int64
0x18002544c  mov     rdx, rbp; unsigned __int16 *
0x18002544f  mov     rcx, rsi; this
0x180025452  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180025457  mov     rcx, rsi; lpOutputString
0x18002545a  call    cs:__imp_OutputDebugStringW
0x180025460  test    byte ptr [rbx+4], 4
0x180025464  jnz     short loc_18002546F
0x180025466  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18002546d  jz      short loc_180025481
0x18002546f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180025476  test    rax, rax
0x180025479  jz      short loc_180025481
0x18002547b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025480  nop
0x180025481  mov     rbx, [rsp+78h+arg_10]
0x180025489  add     rsp, 40h
0x18002548d  pop     r15
0x18002548f  pop     r14
0x180025491  pop     r13
0x180025493  pop     r12
0x180025495  pop     rdi
0x180025496  pop     rsi
0x180025497  pop     rbp
0x180025498  retn
```
