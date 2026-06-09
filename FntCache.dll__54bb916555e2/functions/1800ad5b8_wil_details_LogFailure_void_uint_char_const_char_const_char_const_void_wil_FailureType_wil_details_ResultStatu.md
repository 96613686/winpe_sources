# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800ad5b8`
- end: `0x1800ad8ad`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800ab9ec`
- `0x1800aba9c`
- `0x1800abb8c`

## callees

- `0x1800a874c`
- `0x1800ab93c`
- `0x1800acd44`
- `0x1800ad5b8`
- `0x1800ae1f8`
- `0x1800ae220`
- `0x1800ae2dc`
- `0x1800ae2f8`
- `0x1800af840`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ad6db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800ad6db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ad86e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800ad86e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ad7fc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800ad7fc`

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
        WCHAR *lpOutputString,
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

  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    OutputDebugStringW(lpOutputString);
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
0x1800ad5b8  mov     [rsp+arg_10], rbx
0x1800ad5bd  mov     [rsp+arg_8], edx
0x1800ad5c1  mov     [rsp+arg_0], rcx
0x1800ad5c6  push    rbp
0x1800ad5c7  push    rsi
0x1800ad5c8  push    rdi
0x1800ad5c9  push    r12
0x1800ad5cb  push    r13
0x1800ad5cd  push    r14
0x1800ad5cf  push    r15
0x1800ad5d1  sub     rsp, 40h
0x1800ad5d5  mov     r12, r9
0x1800ad5d8  mov     r13, r8
0x1800ad5db  mov     r10, rcx
0x1800ad5de  xor     eax, eax
0x1800ad5e0  mov     rsi, [rsp+78h+lpOutputString]
0x1800ad5e8  mov     [rsi], ax
0x1800ad5eb  mov     rax, [rsp+78h+arg_60]
0x1800ad5f3  mov     byte ptr [rax], 0
0x1800ad5f6  mov     r14, [rsp+78h+arg_38]
0x1800ad5fe  mov     edi, [r14]
0x1800ad601  mov     rbx, [rsp+78h+arg_78]
0x1800ad609  mov     [rbx+8], edi
0x1800ad60c  mov     eax, [r14+4]
0x1800ad610  mov     [rbx+0Ch], eax
0x1800ad613  xor     ebp, ebp
0x1800ad615  mov     r15d, [rsp+78h+arg_30]
0x1800ad61d  mov     ecx, r15d
0x1800ad620  test    r15d, r15d
0x1800ad623  jz      short loc_1800AD68B
0x1800ad625  sub     ecx, 1
0x1800ad628  jz      short loc_1800AD682
0x1800ad62a  sub     ecx, 1
0x1800ad62d  jz      short loc_1800AD63D
0x1800ad62f  cmp     ecx, 1
0x1800ad632  jnz     short loc_1800AD694
0x1800ad634  mov     ecx, edi; this
0x1800ad636  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800ad63b  jmp     short loc_1800AD692
0x1800ad63d  test    edi, edi
0x1800ad63f  js      short loc_1800AD679
0x1800ad641  mov     edi, 8007029Ch
0x1800ad646  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800ad64a  mov     rax, [rsp+78h+arg_28]
0x1800ad652  mov     [rsp+78h+var_50], rax; __int64
0x1800ad657  mov     rax, [rsp+78h+arg_20]
0x1800ad65f  mov     [rsp+78h+var_58], rax; __int64
0x1800ad664  mov     rcx, r10; int
0x1800ad667  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800ad66c  mov     [rbx+8], edi
0x1800ad66f  mov     ecx, edi; this
0x1800ad671  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800ad676  mov     [rbx+0Ch], eax
0x1800ad679  mov     ecx, edi; this
0x1800ad67b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800ad680  jmp     short loc_1800AD692
0x1800ad682  mov     ecx, edi; this
0x1800ad684  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800ad689  jmp     short loc_1800AD692
0x1800ad68b  mov     ecx, edi; this
0x1800ad68d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800ad692  mov     ebp, eax
0x1800ad694  mov     [rbx], r15d
0x1800ad697  mov     eax, [rsp+78h+arg_70]
0x1800ad69e  mov     [rbx+4], eax
0x1800ad6a1  cmp     dword ptr [r14+8], 1
0x1800ad6a6  jnz     short loc_1800AD6AE
0x1800ad6a8  or      eax, 8
0x1800ad6ab  mov     [rbx+4], eax
0x1800ad6ae  mov     eax, 1
0x1800ad6b3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800ad6bb  inc     eax
0x1800ad6bd  mov     [rbx+10h], eax
0x1800ad6c0  mov     rax, [rsp+78h+arg_40]
0x1800ad6c8  xor     edi, edi
0x1800ad6ca  test    rax, rax
0x1800ad6cd  jz      short loc_1800AD6D4
0x1800ad6cf  cmp     [rax], di
0x1800ad6d2  jnz     short loc_1800AD6D7
0x1800ad6d4  mov     rax, rdi
0x1800ad6d7  mov     [rbx+18h], rax
0x1800ad6db  call    cs:__imp_GetCurrentThreadId
0x1800ad6e1  mov     [rbx+20h], eax
0x1800ad6e4  mov     [rbx+38h], r13
0x1800ad6e8  mov     eax, [rsp+78h+arg_8]
0x1800ad6ef  mov     [rbx+40h], eax
0x1800ad6f2  mov     [rbx+44h], ebp
0x1800ad6f5  mov     rax, [rsp+78h+arg_20]
0x1800ad6fd  mov     [rbx+28h], rax
0x1800ad701  mov     [rbx+30h], r12
0x1800ad705  mov     rax, [rsp+78h+arg_28]
0x1800ad70d  mov     [rbx+88h], rax
0x1800ad714  mov     rax, [rsp+78h+arg_0]
0x1800ad71c  mov     [rbx+90h], rax
0x1800ad723  mov     [rbx+48h], rdi
0x1800ad727  xorps   xmm0, xmm0
0x1800ad72a  xor     eax, eax
0x1800ad72c  movups  xmmword ptr [rbx+68h], xmm0
0x1800ad730  mov     [rbx+78h], rax
0x1800ad734  movups  xmmword ptr [rbx+50h], xmm0
0x1800ad738  mov     [rbx+60h], rax
0x1800ad73c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800ad743  test    rax, rax
0x1800ad746  jz      short loc_1800AD74F
0x1800ad748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad74d  jmp     short loc_1800AD752
0x1800ad74f  mov     rax, rdi
0x1800ad752  mov     [rbx+80h], rax
0x1800ad759  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800ad760  test    rax, rax
0x1800ad763  jz      short loc_1800AD76D
0x1800ad765  mov     rcx, rbx
0x1800ad768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad76d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800ad774  test    rax, rax
0x1800ad777  jz      short loc_1800AD78F
0x1800ad779  mov     r8d, 400h
0x1800ad77f  mov     rdx, [rsp+78h+arg_60]
0x1800ad787  mov     rcx, rbx
0x1800ad78a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad78f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800ad796  test    rax, rax
0x1800ad799  jz      short loc_1800AD7A3
0x1800ad79b  mov     rcx, rbx
0x1800ad79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad7a3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800ad7aa  test    rax, rax
0x1800ad7ad  jz      short loc_1800AD7BD
0x1800ad7af  test    byte ptr [rbx+4], 2
0x1800ad7b3  jnz     short loc_1800AD7BD
0x1800ad7b5  mov     rcx, rbx
0x1800ad7b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad7bd  cmp     [rbx+8], edi
0x1800ad7c0  jl      short loc_1800AD7DE
0x1800ad7c2  cmp     r15d, 3
0x1800ad7c6  jz      short loc_1800AD7CE
0x1800ad7c8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800ad7ce  mov     ecx, 8000FFFFh; this
0x1800ad7d3  mov     [rbx+8], ecx
0x1800ad7d6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800ad7db  mov     [rbx+0Ch], eax
0x1800ad7de  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800ad7e5  jnz     short loc_1800AD806
0x1800ad7e7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800ad7ee  test    rax, rax
0x1800ad7f1  jz      short loc_1800AD7FC
0x1800ad7f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad7f8  test    al, al
0x1800ad7fa  jmp     short loc_1800AD804
0x1800ad7fc  call    cs:__imp_IsDebuggerPresent
0x1800ad802  test    eax, eax
0x1800ad804  jz      short loc_1800AD80C
0x1800ad806  test    byte ptr [rbx+4], 2
0x1800ad80a  jz      short loc_1800AD830
0x1800ad80c  mov     rax, cs:g_pfnResultLoggingCallback
0x1800ad813  test    rax, rax
0x1800ad816  jz      short loc_1800AD874
0x1800ad818  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800ad81f  jnz     short loc_1800AD874
0x1800ad821  xor     r8d, r8d
0x1800ad824  xor     edx, edx
0x1800ad826  mov     rcx, rbx
0x1800ad829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad82e  jmp     short loc_1800AD874
0x1800ad830  mov     ebp, 800h
0x1800ad835  mov     rax, cs:g_pfnResultLoggingCallback
0x1800ad83c  test    rax, rax
0x1800ad83f  jz      short loc_1800AD858
0x1800ad841  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800ad848  jnz     short loc_1800AD858
0x1800ad84a  mov     r8d, ebp
0x1800ad84d  mov     rdx, rsi
0x1800ad850  mov     rcx, rbx
0x1800ad853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad858  cmp     [rsi], di
0x1800ad85b  jnz     short loc_1800AD86B
0x1800ad85d  mov     r8, rbx; unsigned __int64
0x1800ad860  mov     rdx, rbp; wchar_t *
0x1800ad863  mov     rcx, rsi; pszDest
0x1800ad866  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800ad86b  mov     rcx, rsi; lpOutputString
0x1800ad86e  call    cs:__imp_OutputDebugStringW
0x1800ad874  test    byte ptr [rbx+4], 4
0x1800ad878  jnz     short loc_1800AD883
0x1800ad87a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800ad881  jz      short loc_1800AD895
0x1800ad883  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800ad88a  test    rax, rax
0x1800ad88d  jz      short loc_1800AD895
0x1800ad88f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad894  nop
0x1800ad895  mov     rbx, [rsp+78h+arg_10]
0x1800ad89d  add     rsp, 40h
0x1800ad8a1  pop     r15
0x1800ad8a3  pop     r14
0x1800ad8a5  pop     r13
0x1800ad8a7  pop     r12
0x1800ad8a9  pop     rdi
0x1800ad8aa  pop     rsi
0x1800ad8ab  pop     rbp
0x1800ad8ac  retn
```
