# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18003c2bc`
- end: `0x18003c5d5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `793`
- prototype: ``
- caller_count: `6`
- callee_count: `10`
- tags: ``

## callers

- `0x1800397ac`
- `0x180039890`
- `0x180039bb4`
- `0x180039cf0`
- `0x18007ba08`
- `0x18009c5d4`

## callees

- `0x1800399e4`
- `0x18003b7e8`
- `0x18003bdb0`
- `0x18003c2bc`
- `0x18003cd68`
- `0x18003cd90`
- `0x18003cda4`
- `0x18003cdc0`
- `0x18003e508`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003c590`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003c590`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003c50b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003c50b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c3df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c3df`

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
        char a10,
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  unsigned int v18; // edi
  int v19; // esi
  int v20; // eax
  int v21; // edx
  char v22; // di
  _WORD *v23; // rax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

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
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
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
  v22 = 1;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v23 = a9;
  if ( !a9 || !*a9 )
    v23 = 0;
  *(_QWORD *)(a16 + 24) = v23;
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
  if ( wil::details::g_pfnOriginateCallback && !a10 && (*(_BYTE *)(a16 + 4) & 2) == 0 )
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
    v22 = 0;
  }
  if ( a10 || v22 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v26);
    if ( v22 )
      OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(a16, 0, 0);
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
0x18003c2bc  mov     [rsp+arg_10], rbx
0x18003c2c1  mov     [rsp+arg_8], edx
0x18003c2c5  mov     [rsp+arg_0], rcx
0x18003c2ca  push    rbp
0x18003c2cb  push    rsi
0x18003c2cc  push    rdi
0x18003c2cd  push    r12
0x18003c2cf  push    r13
0x18003c2d1  push    r14
0x18003c2d3  push    r15
0x18003c2d5  sub     rsp, 40h
0x18003c2d9  mov     r12, r9
0x18003c2dc  mov     r13, r8
0x18003c2df  mov     r10, rcx
0x18003c2e2  xor     eax, eax
0x18003c2e4  mov     r14, [rsp+78h+lpOutputString]
0x18003c2ec  mov     [r14], ax
0x18003c2f0  mov     rax, [rsp+78h+arg_60]
0x18003c2f8  mov     byte ptr [rax], 0
0x18003c2fb  mov     r15, [rsp+78h+arg_38]
0x18003c303  mov     edi, [r15]
0x18003c306  mov     rbx, [rsp+78h+arg_78]
0x18003c30e  mov     [rbx+8], edi
0x18003c311  mov     eax, [r15+4]
0x18003c315  mov     [rbx+0Ch], eax
0x18003c318  xor     esi, esi
0x18003c31a  mov     ebp, [rsp+78h+arg_30]
0x18003c321  mov     ecx, ebp
0x18003c323  test    ebp, ebp
0x18003c325  jz      short loc_18003C38D
0x18003c327  sub     ecx, 1
0x18003c32a  jz      short loc_18003C384
0x18003c32c  sub     ecx, 1
0x18003c32f  jz      short loc_18003C33F
0x18003c331  cmp     ecx, 1
0x18003c334  jnz     short loc_18003C396
0x18003c336  mov     ecx, edi; this
0x18003c338  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003c33d  jmp     short loc_18003C394
0x18003c33f  test    edi, edi
0x18003c341  js      short loc_18003C37B
0x18003c343  mov     edi, 8007029Ch
0x18003c348  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003c34c  mov     rax, [rsp+78h+arg_28]
0x18003c354  mov     [rsp+78h+var_50], rax; __int64
0x18003c359  mov     rax, [rsp+78h+arg_20]
0x18003c361  mov     [rsp+78h+var_58], rax; __int64
0x18003c366  mov     rcx, r10; int
0x18003c369  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18003c36e  mov     [rbx+8], edi
0x18003c371  mov     ecx, edi; this
0x18003c373  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003c378  mov     [rbx+0Ch], eax
0x18003c37b  mov     ecx, edi; this
0x18003c37d  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18003c382  jmp     short loc_18003C394
0x18003c384  mov     ecx, edi; this
0x18003c386  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003c38b  jmp     short loc_18003C394
0x18003c38d  mov     ecx, edi; this
0x18003c38f  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18003c394  mov     esi, eax
0x18003c396  mov     [rbx], ebp
0x18003c398  mov     eax, [rsp+78h+arg_70]
0x18003c39f  mov     [rbx+4], eax
0x18003c3a2  mov     edi, 1
0x18003c3a7  cmp     [r15+8], edi
0x18003c3ab  jnz     short loc_18003C3B3
0x18003c3ad  or      eax, 8
0x18003c3b0  mov     [rbx+4], eax
0x18003c3b3  mov     eax, edi
0x18003c3b5  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003c3bd  add     eax, edi
0x18003c3bf  mov     [rbx+10h], eax
0x18003c3c2  mov     rax, [rsp+78h+arg_40]
0x18003c3ca  xor     r15d, r15d
0x18003c3cd  test    rax, rax
0x18003c3d0  jz      short loc_18003C3D8
0x18003c3d2  cmp     [rax], r15w
0x18003c3d6  jnz     short loc_18003C3DB
0x18003c3d8  mov     rax, r15
0x18003c3db  mov     [rbx+18h], rax
0x18003c3df  call    cs:__imp_GetCurrentThreadId
0x18003c3e5  mov     [rbx+20h], eax
0x18003c3e8  mov     [rbx+38h], r13
0x18003c3ec  mov     eax, [rsp+78h+arg_8]
0x18003c3f3  mov     [rbx+40h], eax
0x18003c3f6  mov     [rbx+44h], esi
0x18003c3f9  mov     rax, [rsp+78h+arg_20]
0x18003c401  mov     [rbx+28h], rax
0x18003c405  mov     [rbx+30h], r12
0x18003c409  mov     rax, [rsp+78h+arg_28]
0x18003c411  mov     [rbx+88h], rax
0x18003c418  mov     rax, [rsp+78h+arg_0]
0x18003c420  mov     [rbx+90h], rax
0x18003c427  mov     [rbx+48h], r15
0x18003c42b  xorps   xmm0, xmm0
0x18003c42e  xor     eax, eax
0x18003c430  movups  xmmword ptr [rbx+68h], xmm0
0x18003c434  mov     [rbx+78h], rax
0x18003c438  movups  xmmword ptr [rbx+50h], xmm0
0x18003c43c  mov     [rbx+60h], rax
0x18003c440  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003c447  test    rax, rax
0x18003c44a  jz      short loc_18003C453
0x18003c44c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c451  jmp     short loc_18003C456
0x18003c453  mov     rax, r15
0x18003c456  mov     [rbx+80h], rax
0x18003c45d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003c464  test    rax, rax
0x18003c467  jz      short loc_18003C471
0x18003c469  mov     rcx, rbx
0x18003c46c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c471  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003c478  test    rax, rax
0x18003c47b  jz      short loc_18003C493
0x18003c47d  mov     r8d, 400h
0x18003c483  mov     rdx, [rsp+78h+arg_60]
0x18003c48b  mov     rcx, rbx
0x18003c48e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c493  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003c49a  test    rax, rax
0x18003c49d  jz      short loc_18003C4A7
0x18003c49f  mov     rcx, rbx
0x18003c4a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4a7  mov     sil, [rsp+78h+arg_48]
0x18003c4af  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003c4b6  test    rax, rax
0x18003c4b9  jz      short loc_18003C4CE
0x18003c4bb  test    sil, sil
0x18003c4be  jnz     short loc_18003C4CE
0x18003c4c0  test    byte ptr [rbx+4], 2
0x18003c4c4  jnz     short loc_18003C4CE
0x18003c4c6  mov     rcx, rbx
0x18003c4c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c4ce  cmp     [rbx+8], r15d
0x18003c4d2  jl      short loc_18003C4ED
0x18003c4d4  cmp     ebp, 3
0x18003c4d7  jnz     loc_18003C5CF
0x18003c4dd  mov     ecx, 8000FFFFh; this
0x18003c4e2  mov     [rbx+8], ecx
0x18003c4e5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003c4ea  mov     [rbx+0Ch], eax
0x18003c4ed  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18003c4f4  jnz     short loc_18003C515
0x18003c4f6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003c4fd  test    rax, rax
0x18003c500  jz      short loc_18003C50B
0x18003c502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c507  test    al, al
0x18003c509  jmp     short loc_18003C513
0x18003c50b  call    cs:__imp_IsDebuggerPresent
0x18003c511  test    eax, eax
0x18003c513  jz      short loc_18003C51B
0x18003c515  test    byte ptr [rbx+4], 2
0x18003c519  jz      short loc_18003C51E
0x18003c51b  mov     dil, r15b
0x18003c51e  test    sil, sil
0x18003c521  jnz     short loc_18003C54C
0x18003c523  test    dil, dil
0x18003c526  jnz     short loc_18003C54C
0x18003c528  mov     rax, cs:g_pfnResultLoggingCallback
0x18003c52f  test    rax, rax
0x18003c532  jz      short loc_18003C596
0x18003c534  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003c53b  jnz     short loc_18003C596
0x18003c53d  xor     r8d, r8d
0x18003c540  xor     edx, edx
0x18003c542  mov     rcx, rbx
0x18003c545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c54a  jmp     short loc_18003C596
0x18003c54c  mov     esi, 800h
0x18003c551  mov     rax, cs:g_pfnResultLoggingCallback
0x18003c558  test    rax, rax
0x18003c55b  jz      short loc_18003C574
0x18003c55d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003c564  jnz     short loc_18003C574
0x18003c566  mov     r8d, esi
0x18003c569  mov     rdx, r14
0x18003c56c  mov     rcx, rbx
0x18003c56f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c574  cmp     [r14], r15w
0x18003c578  jnz     short loc_18003C588
0x18003c57a  mov     r8, rbx; unsigned __int64
0x18003c57d  mov     rdx, rsi; wchar_t *
0x18003c580  mov     rcx, r14; this
0x18003c583  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18003c588  test    dil, dil
0x18003c58b  jz      short loc_18003C596
0x18003c58d  mov     rcx, r14; lpOutputString
0x18003c590  call    cs:__imp_OutputDebugStringW
0x18003c596  test    byte ptr [rbx+4], 4
0x18003c59a  jnz     short loc_18003C5A5
0x18003c59c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18003c5a3  jz      short loc_18003C5B7
0x18003c5a5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003c5ac  test    rax, rax
0x18003c5af  jz      short loc_18003C5B7
0x18003c5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c5b6  nop
0x18003c5b7  mov     rbx, [rsp+78h+arg_10]
0x18003c5bf  add     rsp, 40h
0x18003c5c3  pop     r15
0x18003c5c5  pop     r14
0x18003c5c7  pop     r13
0x18003c5c9  pop     r12
0x18003c5cb  pop     rdi
0x18003c5cc  pop     rsi
0x18003c5cd  pop     rbp
0x18003c5ce  retn
0x18003c5cf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
