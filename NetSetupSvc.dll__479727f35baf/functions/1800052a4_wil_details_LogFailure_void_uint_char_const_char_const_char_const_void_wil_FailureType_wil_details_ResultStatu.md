# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800052a4`
- end: `0x18000559d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800038e0`
- `0x180003c24`
- `0x18001afb4`

## callees

- `0x180003820`
- `0x1800048a4`
- `0x1800050e0`
- `0x1800052a4`
- `0x1800059d0`
- `0x1800059f0`
- `0x180005a04`
- `0x180005a20`
- `0x180006830`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800053c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800053c7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005558`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005558`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800054e6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800054e6`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v23);
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
0x1800052a4  mov     [rsp+arg_10], rbx
0x1800052a9  mov     [rsp+arg_8], edx
0x1800052ad  mov     [rsp+arg_0], rcx
0x1800052b2  push    rbp
0x1800052b3  push    rsi
0x1800052b4  push    rdi
0x1800052b5  push    r12
0x1800052b7  push    r13
0x1800052b9  push    r14
0x1800052bb  push    r15
0x1800052bd  sub     rsp, 40h
0x1800052c1  mov     r12, r9
0x1800052c4  mov     r13, r8
0x1800052c7  mov     r10, rcx
0x1800052ca  xor     eax, eax
0x1800052cc  mov     rsi, [rsp+78h+lpOutputString]
0x1800052d4  mov     [rsi], ax
0x1800052d7  mov     rax, [rsp+78h+arg_60]
0x1800052df  mov     byte ptr [rax], 0
0x1800052e2  mov     r14, [rsp+78h+arg_38]
0x1800052ea  mov     edi, [r14]
0x1800052ed  mov     rbx, [rsp+78h+arg_78]
0x1800052f5  mov     [rbx+8], edi
0x1800052f8  mov     eax, [r14+4]
0x1800052fc  mov     [rbx+0Ch], eax
0x1800052ff  xor     ebp, ebp
0x180005301  mov     r15d, [rsp+78h+arg_30]
0x180005309  mov     ecx, r15d
0x18000530c  test    r15d, r15d
0x18000530f  jz      short loc_180005377
0x180005311  sub     ecx, 1
0x180005314  jz      short loc_18000536E
0x180005316  sub     ecx, 1
0x180005319  jz      short loc_180005329
0x18000531b  cmp     ecx, 1
0x18000531e  jnz     short loc_180005380
0x180005320  mov     ecx, edi; this
0x180005322  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005327  jmp     short loc_18000537E
0x180005329  test    edi, edi
0x18000532b  js      short loc_180005365
0x18000532d  mov     edi, 8007029Ch
0x180005332  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005336  mov     rax, [rsp+78h+arg_28]
0x18000533e  mov     [rsp+78h+var_50], rax; __int64
0x180005343  mov     rax, [rsp+78h+arg_20]
0x18000534b  mov     [rsp+78h+var_58], rax; __int64
0x180005350  mov     rcx, r10; int
0x180005353  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005358  mov     [rbx+8], edi
0x18000535b  mov     ecx, edi; this
0x18000535d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005362  mov     [rbx+0Ch], eax
0x180005365  mov     ecx, edi; this
0x180005367  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000536c  jmp     short loc_18000537E
0x18000536e  mov     ecx, edi; this
0x180005370  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005375  jmp     short loc_18000537E
0x180005377  mov     ecx, edi; this
0x180005379  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000537e  mov     ebp, eax
0x180005380  mov     [rbx], r15d
0x180005383  mov     eax, [rsp+78h+arg_70]
0x18000538a  mov     [rbx+4], eax
0x18000538d  cmp     dword ptr [r14+8], 1
0x180005392  jnz     short loc_18000539A
0x180005394  or      eax, 8
0x180005397  mov     [rbx+4], eax
0x18000539a  mov     eax, 1
0x18000539f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800053a7  inc     eax
0x1800053a9  mov     [rbx+10h], eax
0x1800053ac  mov     rax, [rsp+78h+arg_40]
0x1800053b4  xor     edi, edi
0x1800053b6  test    rax, rax
0x1800053b9  jz      short loc_1800053C0
0x1800053bb  cmp     [rax], di
0x1800053be  jnz     short loc_1800053C3
0x1800053c0  mov     rax, rdi
0x1800053c3  mov     [rbx+18h], rax
0x1800053c7  call    cs:__imp_GetCurrentThreadId
0x1800053cd  mov     [rbx+20h], eax
0x1800053d0  mov     [rbx+38h], r13
0x1800053d4  mov     eax, [rsp+78h+arg_8]
0x1800053db  mov     [rbx+40h], eax
0x1800053de  mov     [rbx+44h], ebp
0x1800053e1  mov     rax, [rsp+78h+arg_20]
0x1800053e9  mov     [rbx+28h], rax
0x1800053ed  mov     [rbx+30h], r12
0x1800053f1  mov     rax, [rsp+78h+arg_28]
0x1800053f9  mov     [rbx+88h], rax
0x180005400  mov     rax, [rsp+78h+arg_0]
0x180005408  mov     [rbx+90h], rax
0x18000540f  mov     [rbx+48h], rdi
0x180005413  xorps   xmm0, xmm0
0x180005416  xor     eax, eax
0x180005418  movups  xmmword ptr [rbx+68h], xmm0
0x18000541c  mov     [rbx+78h], rax
0x180005420  movups  xmmword ptr [rbx+50h], xmm0
0x180005424  mov     [rbx+60h], rax
0x180005428  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000542f  test    rax, rax
0x180005432  jz      short loc_18000543B
0x180005434  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005439  jmp     short loc_18000543E
0x18000543b  mov     rax, rdi
0x18000543e  mov     [rbx+80h], rax
0x180005445  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000544c  test    rax, rax
0x18000544f  jz      short loc_180005459
0x180005451  mov     rcx, rbx
0x180005454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005459  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005460  test    rax, rax
0x180005463  jz      short loc_18000547B
0x180005465  mov     r8d, 400h
0x18000546b  mov     rdx, [rsp+78h+arg_60]
0x180005473  mov     rcx, rbx
0x180005476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000547b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005482  test    rax, rax
0x180005485  jz      short loc_18000548F
0x180005487  mov     rcx, rbx
0x18000548a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000548f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005496  test    rax, rax
0x180005499  jz      short loc_1800054A9
0x18000549b  test    byte ptr [rbx+4], 2
0x18000549f  jnz     short loc_1800054A9
0x1800054a1  mov     rcx, rbx
0x1800054a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054a9  cmp     [rbx+8], edi
0x1800054ac  jl      short loc_1800054C8
0x1800054ae  cmp     r15d, 3
0x1800054b2  jnz     loc_180005597
0x1800054b8  mov     ecx, 8000FFFFh; this
0x1800054bd  mov     [rbx+8], ecx
0x1800054c0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800054c5  mov     [rbx+0Ch], eax
0x1800054c8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800054cf  jnz     short loc_1800054F0
0x1800054d1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800054d8  test    rax, rax
0x1800054db  jz      short loc_1800054E6
0x1800054dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054e2  test    al, al
0x1800054e4  jmp     short loc_1800054EE
0x1800054e6  call    cs:__imp_IsDebuggerPresent
0x1800054ec  test    eax, eax
0x1800054ee  jz      short loc_1800054F6
0x1800054f0  test    byte ptr [rbx+4], 2
0x1800054f4  jz      short loc_18000551A
0x1800054f6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800054fd  test    rax, rax
0x180005500  jz      short loc_18000555E
0x180005502  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005509  jnz     short loc_18000555E
0x18000550b  xor     r8d, r8d
0x18000550e  xor     edx, edx
0x180005510  mov     rcx, rbx
0x180005513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005518  jmp     short loc_18000555E
0x18000551a  mov     ebp, 800h
0x18000551f  mov     rax, cs:g_pfnResultLoggingCallback
0x180005526  test    rax, rax
0x180005529  jz      short loc_180005542
0x18000552b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005532  jnz     short loc_180005542
0x180005534  mov     r8d, ebp
0x180005537  mov     rdx, rsi
0x18000553a  mov     rcx, rbx
0x18000553d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005542  cmp     [rsi], di
0x180005545  jnz     short loc_180005555
0x180005547  mov     r8, rbx; unsigned __int64
0x18000554a  mov     rdx, rbp; wchar_t *
0x18000554d  mov     rcx, rsi; this
0x180005550  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005555  mov     rcx, rsi; lpOutputString
0x180005558  call    cs:__imp_OutputDebugStringW
0x18000555e  test    byte ptr [rbx+4], 4
0x180005562  jnz     short loc_18000556D
0x180005564  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000556b  jz      short loc_18000557F
0x18000556d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005574  test    rax, rax
0x180005577  jz      short loc_18000557F
0x180005579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000557e  nop
0x18000557f  mov     rbx, [rsp+78h+arg_10]
0x180005587  add     rsp, 40h
0x18000558b  pop     r15
0x18000558d  pop     r14
0x18000558f  pop     r13
0x180005591  pop     r12
0x180005593  pop     rdi
0x180005594  pop     rsi
0x180005595  pop     rbp
0x180005596  retn
0x180005597  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
