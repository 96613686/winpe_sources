# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18003d3ec`
- end: `0x18003d6fb`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `783`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18003ce74`
- `0x180040500`

## callees

- `0x1800117e8`
- `0x18003cb6c`
- `0x18003d120`
- `0x18003d3ec`
- `0x18003d758`
- `0x18003d780`
- `0x18003d794`
- `0x18003d7b4`
- `0x18003d9e8`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18003d6b0`
- `KERNEL32!OutputDebugStringW` at `0x18003d6b0`
- `KERNEL32!GetCurrentThreadId` at `0x18003d513`
- `KERNEL32!GetCurrentThreadId` at `0x18003d513`
- `KERNEL32!IsDebuggerPresent` at `0x18003d638`
- `KERNEL32!IsDebuggerPresent` at `0x18003d638`

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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v26);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x18003d3ec  mov     [rsp+arg_10], rbx
0x18003d3f1  mov     [rsp+arg_8], edx
0x18003d3f5  mov     [rsp+arg_0], rcx
0x18003d3fa  push    rbp
0x18003d3fb  push    rsi
0x18003d3fc  push    rdi
0x18003d3fd  push    r12
0x18003d3ff  push    r13
0x18003d401  push    r14
0x18003d403  push    r15
0x18003d405  sub     rsp, 40h
0x18003d409  mov     r14, [rsp+78h+arg_38]
0x18003d411  xor     eax, eax
0x18003d413  mov     rbx, [rsp+78h+arg_78]
0x18003d41b  xor     ebp, ebp
0x18003d41d  mov     r15d, [rsp+78h+arg_30]
0x18003d425  mov     r10, rcx
0x18003d428  mov     rsi, [rsp+78h+lpOutputString]
0x18003d430  mov     r12, r9
0x18003d433  mov     r13, r8
0x18003d436  mov     ecx, r15d
0x18003d439  mov     [rsi], ax
0x18003d43c  mov     rax, [rsp+78h+arg_60]
0x18003d444  mov     byte ptr [rax], 0
0x18003d447  mov     edi, [r14]
0x18003d44a  mov     [rbx+8], edi
0x18003d44d  mov     eax, [r14+4]
0x18003d451  mov     [rbx+0Ch], eax
0x18003d454  test    r15d, r15d
0x18003d457  jz      short loc_18003D4C3
0x18003d459  sub     ecx, 1
0x18003d45c  jz      short loc_18003D4BA
0x18003d45e  sub     ecx, 1
0x18003d461  jz      short loc_18003D471
0x18003d463  cmp     ecx, 1
0x18003d466  jnz     short loc_18003D4CC
0x18003d468  mov     ecx, edi; this
0x18003d46a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003d46f  jmp     short loc_18003D4CA
0x18003d471  test    edi, edi
0x18003d473  js      short loc_18003D4B1
0x18003d475  mov     rax, [rsp+78h+arg_28]
0x18003d47d  mov     edi, 8007029Ch
0x18003d482  mov     [rsp+78h+var_40], ebp
0x18003d486  mov     rcx, r10; int
0x18003d489  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003d48d  mov     [rsp+78h+var_50], rax; __int64
0x18003d492  mov     rax, [rsp+78h+arg_20]
0x18003d49a  mov     [rsp+78h+var_58], rax; __int64
0x18003d49f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18003d4a4  mov     ecx, edi; this
0x18003d4a6  mov     [rbx+8], edi
0x18003d4a9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003d4ae  mov     [rbx+0Ch], eax
0x18003d4b1  mov     ecx, edi; this
0x18003d4b3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18003d4b8  jmp     short loc_18003D4CA
0x18003d4ba  mov     ecx, edi; this
0x18003d4bc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003d4c1  jmp     short loc_18003D4CA
0x18003d4c3  mov     ecx, edi; this
0x18003d4c5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18003d4ca  mov     ebp, eax
0x18003d4cc  mov     eax, [rsp+78h+arg_70]
0x18003d4d3  mov     [rbx+4], eax
0x18003d4d6  mov     [rbx], r15d
0x18003d4d9  cmp     dword ptr [r14+8], 1
0x18003d4de  jnz     short loc_18003D4E6
0x18003d4e0  or      eax, 8
0x18003d4e3  mov     [rbx+4], eax
0x18003d4e6  mov     eax, 1
0x18003d4eb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003d4f3  inc     eax
0x18003d4f5  xor     edi, edi
0x18003d4f7  mov     [rbx+10h], eax
0x18003d4fa  mov     rax, [rsp+78h+arg_40]
0x18003d502  test    rax, rax
0x18003d505  jz      short loc_18003D50C
0x18003d507  cmp     [rax], di
0x18003d50a  jnz     short loc_18003D50F
0x18003d50c  mov     rax, rdi
0x18003d50f  mov     [rbx+18h], rax
0x18003d513  call    cs:__imp_GetCurrentThreadId
0x18003d51a  nop     dword ptr [rax+rax+00h]
0x18003d51f  mov     [rbx+38h], r13
0x18003d523  xorps   xmm0, xmm0
0x18003d526  mov     [rbx+20h], eax
0x18003d529  mov     eax, [rsp+78h+arg_8]
0x18003d530  mov     [rbx+40h], eax
0x18003d533  mov     rax, [rsp+78h+arg_20]
0x18003d53b  mov     [rbx+28h], rax
0x18003d53f  mov     rax, [rsp+78h+arg_28]
0x18003d547  mov     [rbx+88h], rax
0x18003d54e  mov     rax, [rsp+78h+arg_0]
0x18003d556  mov     [rbx+90h], rax
0x18003d55d  xor     eax, eax
0x18003d55f  mov     [rbx+44h], ebp
0x18003d562  mov     [rbx+30h], r12
0x18003d566  mov     [rbx+48h], rdi
0x18003d56a  movups  xmmword ptr [rbx+68h], xmm0
0x18003d56e  mov     [rbx+78h], rax
0x18003d572  movups  xmmword ptr [rbx+50h], xmm0
0x18003d576  mov     [rbx+60h], rax
0x18003d57a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003d581  test    rax, rax
0x18003d584  jz      short loc_18003D58D
0x18003d586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d58b  jmp     short loc_18003D590
0x18003d58d  mov     rax, rdi
0x18003d590  mov     [rbx+80h], rax
0x18003d597  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003d59e  test    rax, rax
0x18003d5a1  jz      short loc_18003D5AB
0x18003d5a3  mov     rcx, rbx
0x18003d5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5ab  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003d5b2  test    rax, rax
0x18003d5b5  jz      short loc_18003D5CD
0x18003d5b7  mov     rdx, [rsp+78h+arg_60]
0x18003d5bf  mov     r8d, 400h
0x18003d5c5  mov     rcx, rbx
0x18003d5c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5cd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003d5d4  test    rax, rax
0x18003d5d7  jz      short loc_18003D5E1
0x18003d5d9  mov     rcx, rbx
0x18003d5dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5e1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003d5e8  test    rax, rax
0x18003d5eb  jz      short loc_18003D5FB
0x18003d5ed  test    byte ptr [rbx+4], 2
0x18003d5f1  jnz     short loc_18003D5FB
0x18003d5f3  mov     rcx, rbx
0x18003d5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5fb  cmp     [rbx+8], edi
0x18003d5fe  jl      short loc_18003D61A
0x18003d600  cmp     r15d, 3
0x18003d604  jnz     loc_18003D6F5
0x18003d60a  mov     ecx, 8000FFFFh; this
0x18003d60f  mov     [rbx+8], ecx
0x18003d612  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003d617  mov     [rbx+0Ch], eax
0x18003d61a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18003d621  jnz     short loc_18003D648
0x18003d623  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003d62a  test    rax, rax
0x18003d62d  jz      short loc_18003D638
0x18003d62f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d634  test    al, al
0x18003d636  jmp     short loc_18003D646
0x18003d638  call    cs:__imp_IsDebuggerPresent
0x18003d63f  nop     dword ptr [rax+rax+00h]
0x18003d644  test    eax, eax
0x18003d646  jz      short loc_18003D64E
0x18003d648  test    byte ptr [rbx+4], 2
0x18003d64c  jz      short loc_18003D672
0x18003d64e  mov     rax, cs:g_pfnResultLoggingCallback
0x18003d655  test    rax, rax
0x18003d658  jz      short loc_18003D6BC
0x18003d65a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003d661  jnz     short loc_18003D6BC
0x18003d663  xor     r8d, r8d
0x18003d666  xor     edx, edx
0x18003d668  mov     rcx, rbx
0x18003d66b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d670  jmp     short loc_18003D6BC
0x18003d672  mov     rax, cs:g_pfnResultLoggingCallback
0x18003d679  mov     ebp, 800h
0x18003d67e  test    rax, rax
0x18003d681  jz      short loc_18003D69A
0x18003d683  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003d68a  jnz     short loc_18003D69A
0x18003d68c  mov     r8d, ebp
0x18003d68f  mov     rdx, rsi
0x18003d692  mov     rcx, rbx
0x18003d695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d69a  cmp     [rsi], di
0x18003d69d  jnz     short loc_18003D6AD
0x18003d69f  mov     r8, rbx; unsigned __int64
0x18003d6a2  mov     rdx, rbp; wchar_t *
0x18003d6a5  mov     rcx, rsi; this
0x18003d6a8  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18003d6ad  mov     rcx, rsi; lpOutputString
0x18003d6b0  call    cs:__imp_OutputDebugStringW
0x18003d6b7  nop     dword ptr [rax+rax+00h]
0x18003d6bc  test    byte ptr [rbx+4], 4
0x18003d6c0  jnz     short loc_18003D6CB
0x18003d6c2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18003d6c9  jz      short loc_18003D6DC
0x18003d6cb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003d6d2  test    rax, rax
0x18003d6d5  jz      short loc_18003D6DC
0x18003d6d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6dc  mov     rbx, [rsp+78h+arg_10]
0x18003d6e4  add     rsp, 40h
0x18003d6e8  pop     r15
0x18003d6ea  pop     r14
0x18003d6ec  pop     r13
0x18003d6ee  pop     r12
0x18003d6f0  pop     rdi
0x18003d6f1  pop     rsi
0x18003d6f2  pop     rbp
0x18003d6f3  retn
0x18003d6f5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
