# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005344`
- end: `0x18000563d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002c08`

## callees

- `0x180002614`
- `0x1800049e4`
- `0x180005180`
- `0x180005344`
- `0x180005d94`
- `0x180005db0`
- `0x180005edc`
- `0x180005ef8`
- `0x1800083fc`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005467`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005467`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005586`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005586`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800055f8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800055f8`

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
0x180005344  mov     [rsp+arg_10], rbx
0x180005349  mov     [rsp+arg_8], edx
0x18000534d  mov     [rsp+arg_0], rcx
0x180005352  push    rbp
0x180005353  push    rsi
0x180005354  push    rdi
0x180005355  push    r12
0x180005357  push    r13
0x180005359  push    r14
0x18000535b  push    r15
0x18000535d  sub     rsp, 40h
0x180005361  mov     r12, r9
0x180005364  mov     r13, r8
0x180005367  mov     r10, rcx
0x18000536a  xor     eax, eax
0x18000536c  mov     rsi, [rsp+78h+lpOutputString]
0x180005374  mov     [rsi], ax
0x180005377  mov     rax, [rsp+78h+arg_60]
0x18000537f  mov     byte ptr [rax], 0
0x180005382  mov     r14, [rsp+78h+arg_38]
0x18000538a  mov     edi, [r14]
0x18000538d  mov     rbx, [rsp+78h+arg_78]
0x180005395  mov     [rbx+8], edi
0x180005398  mov     eax, [r14+4]
0x18000539c  mov     [rbx+0Ch], eax
0x18000539f  xor     ebp, ebp
0x1800053a1  mov     r15d, [rsp+78h+arg_30]
0x1800053a9  mov     ecx, r15d
0x1800053ac  test    r15d, r15d
0x1800053af  jz      short loc_180005417
0x1800053b1  sub     ecx, 1
0x1800053b4  jz      short loc_18000540E
0x1800053b6  sub     ecx, 1
0x1800053b9  jz      short loc_1800053C9
0x1800053bb  cmp     ecx, 1
0x1800053be  jnz     short loc_180005420
0x1800053c0  mov     ecx, edi; this
0x1800053c2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800053c7  jmp     short loc_18000541E
0x1800053c9  test    edi, edi
0x1800053cb  js      short loc_180005405
0x1800053cd  mov     edi, 8007029Ch
0x1800053d2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800053d6  mov     rax, [rsp+78h+arg_28]
0x1800053de  mov     [rsp+78h+var_50], rax; __int64
0x1800053e3  mov     rax, [rsp+78h+arg_20]
0x1800053eb  mov     [rsp+78h+var_58], rax; __int64
0x1800053f0  mov     rcx, r10; int
0x1800053f3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800053f8  mov     [rbx+8], edi
0x1800053fb  mov     ecx, edi; this
0x1800053fd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005402  mov     [rbx+0Ch], eax
0x180005405  mov     ecx, edi; this
0x180005407  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000540c  jmp     short loc_18000541E
0x18000540e  mov     ecx, edi; this
0x180005410  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005415  jmp     short loc_18000541E
0x180005417  mov     ecx, edi; this
0x180005419  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000541e  mov     ebp, eax
0x180005420  mov     [rbx], r15d
0x180005423  mov     eax, [rsp+78h+arg_70]
0x18000542a  mov     [rbx+4], eax
0x18000542d  cmp     dword ptr [r14+8], 1
0x180005432  jnz     short loc_18000543A
0x180005434  or      eax, 8
0x180005437  mov     [rbx+4], eax
0x18000543a  mov     eax, 1
0x18000543f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005447  inc     eax
0x180005449  mov     [rbx+10h], eax
0x18000544c  mov     rax, [rsp+78h+arg_40]
0x180005454  xor     edi, edi
0x180005456  test    rax, rax
0x180005459  jz      short loc_180005460
0x18000545b  cmp     [rax], di
0x18000545e  jnz     short loc_180005463
0x180005460  mov     rax, rdi
0x180005463  mov     [rbx+18h], rax
0x180005467  call    cs:__imp_GetCurrentThreadId
0x18000546d  mov     [rbx+20h], eax
0x180005470  mov     [rbx+38h], r13
0x180005474  mov     eax, [rsp+78h+arg_8]
0x18000547b  mov     [rbx+40h], eax
0x18000547e  mov     [rbx+44h], ebp
0x180005481  mov     rax, [rsp+78h+arg_20]
0x180005489  mov     [rbx+28h], rax
0x18000548d  mov     [rbx+30h], r12
0x180005491  mov     rax, [rsp+78h+arg_28]
0x180005499  mov     [rbx+88h], rax
0x1800054a0  mov     rax, [rsp+78h+arg_0]
0x1800054a8  mov     [rbx+90h], rax
0x1800054af  mov     [rbx+48h], rdi
0x1800054b3  xorps   xmm0, xmm0
0x1800054b6  xor     eax, eax
0x1800054b8  movups  xmmword ptr [rbx+68h], xmm0
0x1800054bc  mov     [rbx+78h], rax
0x1800054c0  movups  xmmword ptr [rbx+50h], xmm0
0x1800054c4  mov     [rbx+60h], rax
0x1800054c8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800054cf  test    rax, rax
0x1800054d2  jz      short loc_1800054DB
0x1800054d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054d9  jmp     short loc_1800054DE
0x1800054db  mov     rax, rdi
0x1800054de  mov     [rbx+80h], rax
0x1800054e5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800054ec  test    rax, rax
0x1800054ef  jz      short loc_1800054F9
0x1800054f1  mov     rcx, rbx
0x1800054f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054f9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005500  test    rax, rax
0x180005503  jz      short loc_18000551B
0x180005505  mov     r8d, 400h
0x18000550b  mov     rdx, [rsp+78h+arg_60]
0x180005513  mov     rcx, rbx
0x180005516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000551b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005522  test    rax, rax
0x180005525  jz      short loc_18000552F
0x180005527  mov     rcx, rbx
0x18000552a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000552f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005536  test    rax, rax
0x180005539  jz      short loc_180005549
0x18000553b  test    byte ptr [rbx+4], 2
0x18000553f  jnz     short loc_180005549
0x180005541  mov     rcx, rbx
0x180005544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005549  cmp     [rbx+8], edi
0x18000554c  jl      short loc_180005568
0x18000554e  cmp     r15d, 3
0x180005552  jnz     loc_180005637
0x180005558  mov     ecx, 8000FFFFh; this
0x18000555d  mov     [rbx+8], ecx
0x180005560  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005565  mov     [rbx+0Ch], eax
0x180005568  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000556f  jnz     short loc_180005590
0x180005571  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005578  test    rax, rax
0x18000557b  jz      short loc_180005586
0x18000557d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005582  test    al, al
0x180005584  jmp     short loc_18000558E
0x180005586  call    cs:__imp_IsDebuggerPresent
0x18000558c  test    eax, eax
0x18000558e  jz      short loc_180005596
0x180005590  test    byte ptr [rbx+4], 2
0x180005594  jz      short loc_1800055BA
0x180005596  mov     rax, cs:g_pfnResultLoggingCallback
0x18000559d  test    rax, rax
0x1800055a0  jz      short loc_1800055FE
0x1800055a2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800055a9  jnz     short loc_1800055FE
0x1800055ab  xor     r8d, r8d
0x1800055ae  xor     edx, edx
0x1800055b0  mov     rcx, rbx
0x1800055b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055b8  jmp     short loc_1800055FE
0x1800055ba  mov     ebp, 800h
0x1800055bf  mov     rax, cs:g_pfnResultLoggingCallback
0x1800055c6  test    rax, rax
0x1800055c9  jz      short loc_1800055E2
0x1800055cb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800055d2  jnz     short loc_1800055E2
0x1800055d4  mov     r8d, ebp
0x1800055d7  mov     rdx, rsi
0x1800055da  mov     rcx, rbx
0x1800055dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055e2  cmp     [rsi], di
0x1800055e5  jnz     short loc_1800055F5
0x1800055e7  mov     r8, rbx; unsigned __int64
0x1800055ea  mov     rdx, rbp; unsigned __int16 *
0x1800055ed  mov     rcx, rsi; this
0x1800055f0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800055f5  mov     rcx, rsi; lpOutputString
0x1800055f8  call    cs:__imp_OutputDebugStringW
0x1800055fe  test    byte ptr [rbx+4], 4
0x180005602  jnz     short loc_18000560D
0x180005604  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000560b  jz      short loc_18000561F
0x18000560d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005614  test    rax, rax
0x180005617  jz      short loc_18000561F
0x180005619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000561e  nop
0x18000561f  mov     rbx, [rsp+78h+arg_10]
0x180005627  add     rsp, 40h
0x18000562b  pop     r15
0x18000562d  pop     r14
0x18000562f  pop     r13
0x180005631  pop     r12
0x180005633  pop     rdi
0x180005634  pop     rsi
0x180005635  pop     rbp
0x180005636  retn
0x180005637  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
