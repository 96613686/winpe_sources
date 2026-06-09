# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400052e0`
- end: `0x1400055d9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x140002684`
- `0x140002734`
- `0x140002ad4`

## callees

- `0x14000256c`
- `0x140004274`
- `0x1400050f0`
- `0x1400052e0`
- `0x1400059b4`
- `0x1400059d0`
- `0x1400059e4`
- `0x140005a00`
- `0x140006f90`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005403`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005403`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005522`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005522`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005594`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005594`

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
0x1400052e0  mov     [rsp+arg_10], rbx
0x1400052e5  mov     [rsp+arg_8], edx
0x1400052e9  mov     [rsp+arg_0], rcx
0x1400052ee  push    rbp
0x1400052ef  push    rsi
0x1400052f0  push    rdi
0x1400052f1  push    r12
0x1400052f3  push    r13
0x1400052f5  push    r14
0x1400052f7  push    r15
0x1400052f9  sub     rsp, 40h
0x1400052fd  mov     r12, r9
0x140005300  mov     r13, r8
0x140005303  mov     r10, rcx
0x140005306  xor     eax, eax
0x140005308  mov     rsi, [rsp+78h+lpOutputString]
0x140005310  mov     [rsi], ax
0x140005313  mov     rax, [rsp+78h+arg_60]
0x14000531b  mov     byte ptr [rax], 0
0x14000531e  mov     r14, [rsp+78h+arg_38]
0x140005326  mov     edi, [r14]
0x140005329  mov     rbx, [rsp+78h+arg_78]
0x140005331  mov     [rbx+8], edi
0x140005334  mov     eax, [r14+4]
0x140005338  mov     [rbx+0Ch], eax
0x14000533b  xor     ebp, ebp
0x14000533d  mov     r15d, [rsp+78h+arg_30]
0x140005345  mov     ecx, r15d
0x140005348  test    r15d, r15d
0x14000534b  jz      short loc_1400053B3
0x14000534d  sub     ecx, 1
0x140005350  jz      short loc_1400053AA
0x140005352  sub     ecx, 1
0x140005355  jz      short loc_140005365
0x140005357  cmp     ecx, 1
0x14000535a  jnz     short loc_1400053BC
0x14000535c  mov     ecx, edi; this
0x14000535e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140005363  jmp     short loc_1400053BA
0x140005365  test    edi, edi
0x140005367  js      short loc_1400053A1
0x140005369  mov     edi, 8007029Ch
0x14000536e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140005372  mov     rax, [rsp+78h+arg_28]
0x14000537a  mov     [rsp+78h+var_50], rax; __int64
0x14000537f  mov     rax, [rsp+78h+arg_20]
0x140005387  mov     [rsp+78h+var_58], rax; __int64
0x14000538c  mov     rcx, r10; int
0x14000538f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140005394  mov     [rbx+8], edi
0x140005397  mov     ecx, edi; this
0x140005399  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000539e  mov     [rbx+0Ch], eax
0x1400053a1  mov     ecx, edi; this
0x1400053a3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400053a8  jmp     short loc_1400053BA
0x1400053aa  mov     ecx, edi; this
0x1400053ac  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400053b1  jmp     short loc_1400053BA
0x1400053b3  mov     ecx, edi; this
0x1400053b5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400053ba  mov     ebp, eax
0x1400053bc  mov     [rbx], r15d
0x1400053bf  mov     eax, [rsp+78h+arg_70]
0x1400053c6  mov     [rbx+4], eax
0x1400053c9  cmp     dword ptr [r14+8], 1
0x1400053ce  jnz     short loc_1400053D6
0x1400053d0  or      eax, 8
0x1400053d3  mov     [rbx+4], eax
0x1400053d6  mov     eax, 1
0x1400053db  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400053e3  inc     eax
0x1400053e5  mov     [rbx+10h], eax
0x1400053e8  mov     rax, [rsp+78h+arg_40]
0x1400053f0  xor     edi, edi
0x1400053f2  test    rax, rax
0x1400053f5  jz      short loc_1400053FC
0x1400053f7  cmp     [rax], di
0x1400053fa  jnz     short loc_1400053FF
0x1400053fc  mov     rax, rdi
0x1400053ff  mov     [rbx+18h], rax
0x140005403  call    cs:__imp_GetCurrentThreadId
0x140005409  mov     [rbx+20h], eax
0x14000540c  mov     [rbx+38h], r13
0x140005410  mov     eax, [rsp+78h+arg_8]
0x140005417  mov     [rbx+40h], eax
0x14000541a  mov     [rbx+44h], ebp
0x14000541d  mov     rax, [rsp+78h+arg_20]
0x140005425  mov     [rbx+28h], rax
0x140005429  mov     [rbx+30h], r12
0x14000542d  mov     rax, [rsp+78h+arg_28]
0x140005435  mov     [rbx+88h], rax
0x14000543c  mov     rax, [rsp+78h+arg_0]
0x140005444  mov     [rbx+90h], rax
0x14000544b  mov     [rbx+48h], rdi
0x14000544f  xorps   xmm0, xmm0
0x140005452  xor     eax, eax
0x140005454  movups  xmmword ptr [rbx+68h], xmm0
0x140005458  mov     [rbx+78h], rax
0x14000545c  movups  xmmword ptr [rbx+50h], xmm0
0x140005460  mov     [rbx+60h], rax
0x140005464  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000546b  test    rax, rax
0x14000546e  jz      short loc_140005477
0x140005470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005475  jmp     short loc_14000547A
0x140005477  mov     rax, rdi
0x14000547a  mov     [rbx+80h], rax
0x140005481  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140005488  test    rax, rax
0x14000548b  jz      short loc_140005495
0x14000548d  mov     rcx, rbx
0x140005490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005495  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000549c  test    rax, rax
0x14000549f  jz      short loc_1400054B7
0x1400054a1  mov     r8d, 400h
0x1400054a7  mov     rdx, [rsp+78h+arg_60]
0x1400054af  mov     rcx, rbx
0x1400054b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400054b7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400054be  test    rax, rax
0x1400054c1  jz      short loc_1400054CB
0x1400054c3  mov     rcx, rbx
0x1400054c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400054cb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400054d2  test    rax, rax
0x1400054d5  jz      short loc_1400054E5
0x1400054d7  test    byte ptr [rbx+4], 2
0x1400054db  jnz     short loc_1400054E5
0x1400054dd  mov     rcx, rbx
0x1400054e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400054e5  cmp     [rbx+8], edi
0x1400054e8  jl      short loc_140005504
0x1400054ea  cmp     r15d, 3
0x1400054ee  jnz     loc_1400055D3
0x1400054f4  mov     ecx, 8000FFFFh; this
0x1400054f9  mov     [rbx+8], ecx
0x1400054fc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005501  mov     [rbx+0Ch], eax
0x140005504  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000550b  jnz     short loc_14000552C
0x14000550d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005514  test    rax, rax
0x140005517  jz      short loc_140005522
0x140005519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000551e  test    al, al
0x140005520  jmp     short loc_14000552A
0x140005522  call    cs:__imp_IsDebuggerPresent
0x140005528  test    eax, eax
0x14000552a  jz      short loc_140005532
0x14000552c  test    byte ptr [rbx+4], 2
0x140005530  jz      short loc_140005556
0x140005532  mov     rax, cs:g_pfnResultLoggingCallback
0x140005539  test    rax, rax
0x14000553c  jz      short loc_14000559A
0x14000553e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005545  jnz     short loc_14000559A
0x140005547  xor     r8d, r8d
0x14000554a  xor     edx, edx
0x14000554c  mov     rcx, rbx
0x14000554f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005554  jmp     short loc_14000559A
0x140005556  mov     ebp, 800h
0x14000555b  mov     rax, cs:g_pfnResultLoggingCallback
0x140005562  test    rax, rax
0x140005565  jz      short loc_14000557E
0x140005567  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000556e  jnz     short loc_14000557E
0x140005570  mov     r8d, ebp
0x140005573  mov     rdx, rsi
0x140005576  mov     rcx, rbx
0x140005579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000557e  cmp     [rsi], di
0x140005581  jnz     short loc_140005591
0x140005583  mov     r8, rbx; unsigned __int64
0x140005586  mov     rdx, rbp; unsigned __int16 *
0x140005589  mov     rcx, rsi; this
0x14000558c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140005591  mov     rcx, rsi; lpOutputString
0x140005594  call    cs:__imp_OutputDebugStringW
0x14000559a  test    byte ptr [rbx+4], 4
0x14000559e  jnz     short loc_1400055A9
0x1400055a0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400055a7  jz      short loc_1400055BB
0x1400055a9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400055b0  test    rax, rax
0x1400055b3  jz      short loc_1400055BB
0x1400055b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400055ba  nop
0x1400055bb  mov     rbx, [rsp+78h+arg_10]
0x1400055c3  add     rsp, 40h
0x1400055c7  pop     r15
0x1400055c9  pop     r14
0x1400055cb  pop     r13
0x1400055cd  pop     r12
0x1400055cf  pop     rdi
0x1400055d0  pop     rsi
0x1400055d1  pop     rbp
0x1400055d2  retn
0x1400055d3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
