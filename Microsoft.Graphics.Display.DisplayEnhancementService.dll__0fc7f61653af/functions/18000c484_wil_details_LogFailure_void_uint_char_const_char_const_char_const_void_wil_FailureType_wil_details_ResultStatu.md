# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000c484`
- end: `0x18000c77d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800083f8`
- `0x1800084b8`
- `0x18000889c`

## callees

- `0x180008250`
- `0x18000b0f4`
- `0x18000b9a8`
- `0x18000c484`
- `0x18000d4a4`
- `0x18000d4c0`
- `0x18000d610`
- `0x18000d62c`
- `0x18000f8a0`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c5a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c5a7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c738`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c738`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c6c6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c6c6`

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x18000c484  mov     [rsp+arg_10], rbx
0x18000c489  mov     [rsp+arg_8], edx
0x18000c48d  mov     [rsp+arg_0], rcx
0x18000c492  push    rbp
0x18000c493  push    rsi
0x18000c494  push    rdi
0x18000c495  push    r12
0x18000c497  push    r13
0x18000c499  push    r14
0x18000c49b  push    r15
0x18000c49d  sub     rsp, 40h
0x18000c4a1  mov     r12, r9
0x18000c4a4  mov     r13, r8
0x18000c4a7  mov     r10, rcx
0x18000c4aa  xor     eax, eax
0x18000c4ac  mov     rsi, [rsp+78h+lpOutputString]
0x18000c4b4  mov     [rsi], ax
0x18000c4b7  mov     rax, [rsp+78h+arg_60]
0x18000c4bf  mov     byte ptr [rax], 0
0x18000c4c2  mov     r14, [rsp+78h+arg_38]
0x18000c4ca  mov     edi, [r14]
0x18000c4cd  mov     rbx, [rsp+78h+arg_78]
0x18000c4d5  mov     [rbx+8], edi
0x18000c4d8  mov     eax, [r14+4]
0x18000c4dc  mov     [rbx+0Ch], eax
0x18000c4df  xor     ebp, ebp
0x18000c4e1  mov     r15d, [rsp+78h+arg_30]
0x18000c4e9  mov     ecx, r15d
0x18000c4ec  test    r15d, r15d
0x18000c4ef  jz      short loc_18000C557
0x18000c4f1  sub     ecx, 1
0x18000c4f4  jz      short loc_18000C54E
0x18000c4f6  sub     ecx, 1
0x18000c4f9  jz      short loc_18000C509
0x18000c4fb  cmp     ecx, 1
0x18000c4fe  jnz     short loc_18000C560
0x18000c500  mov     ecx, edi; this
0x18000c502  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000c507  jmp     short loc_18000C55E
0x18000c509  test    edi, edi
0x18000c50b  js      short loc_18000C545
0x18000c50d  mov     edi, 8007029Ch
0x18000c512  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000c516  mov     rax, [rsp+78h+arg_28]
0x18000c51e  mov     [rsp+78h+var_50], rax; __int64
0x18000c523  mov     rax, [rsp+78h+arg_20]
0x18000c52b  mov     [rsp+78h+var_58], rax; __int64
0x18000c530  mov     rcx, r10; int
0x18000c533  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000c538  mov     [rbx+8], edi
0x18000c53b  mov     ecx, edi; this
0x18000c53d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c542  mov     [rbx+0Ch], eax
0x18000c545  mov     ecx, edi; this
0x18000c547  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000c54c  jmp     short loc_18000C55E
0x18000c54e  mov     ecx, edi; this
0x18000c550  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000c555  jmp     short loc_18000C55E
0x18000c557  mov     ecx, edi; this
0x18000c559  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000c55e  mov     ebp, eax
0x18000c560  mov     [rbx], r15d
0x18000c563  mov     eax, [rsp+78h+arg_70]
0x18000c56a  mov     [rbx+4], eax
0x18000c56d  cmp     dword ptr [r14+8], 1
0x18000c572  jnz     short loc_18000C57A
0x18000c574  or      eax, 8
0x18000c577  mov     [rbx+4], eax
0x18000c57a  mov     eax, 1
0x18000c57f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000c587  inc     eax
0x18000c589  mov     [rbx+10h], eax
0x18000c58c  mov     rax, [rsp+78h+arg_40]
0x18000c594  xor     edi, edi
0x18000c596  test    rax, rax
0x18000c599  jz      short loc_18000C5A0
0x18000c59b  cmp     [rax], di
0x18000c59e  jnz     short loc_18000C5A3
0x18000c5a0  mov     rax, rdi
0x18000c5a3  mov     [rbx+18h], rax
0x18000c5a7  call    cs:__imp_GetCurrentThreadId
0x18000c5ad  mov     [rbx+20h], eax
0x18000c5b0  mov     [rbx+38h], r13
0x18000c5b4  mov     eax, [rsp+78h+arg_8]
0x18000c5bb  mov     [rbx+40h], eax
0x18000c5be  mov     [rbx+44h], ebp
0x18000c5c1  mov     rax, [rsp+78h+arg_20]
0x18000c5c9  mov     [rbx+28h], rax
0x18000c5cd  mov     [rbx+30h], r12
0x18000c5d1  mov     rax, [rsp+78h+arg_28]
0x18000c5d9  mov     [rbx+88h], rax
0x18000c5e0  mov     rax, [rsp+78h+arg_0]
0x18000c5e8  mov     [rbx+90h], rax
0x18000c5ef  mov     [rbx+48h], rdi
0x18000c5f3  xorps   xmm0, xmm0
0x18000c5f6  xor     eax, eax
0x18000c5f8  movups  xmmword ptr [rbx+68h], xmm0
0x18000c5fc  mov     [rbx+78h], rax
0x18000c600  movups  xmmword ptr [rbx+50h], xmm0
0x18000c604  mov     [rbx+60h], rax
0x18000c608  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000c60f  test    rax, rax
0x18000c612  jz      short loc_18000C61B
0x18000c614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c619  jmp     short loc_18000C61E
0x18000c61b  mov     rax, rdi
0x18000c61e  mov     [rbx+80h], rax
0x18000c625  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000c62c  test    rax, rax
0x18000c62f  jz      short loc_18000C639
0x18000c631  mov     rcx, rbx
0x18000c634  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c639  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000c640  test    rax, rax
0x18000c643  jz      short loc_18000C65B
0x18000c645  mov     r8d, 400h
0x18000c64b  mov     rdx, [rsp+78h+arg_60]
0x18000c653  mov     rcx, rbx
0x18000c656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c65b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c662  test    rax, rax
0x18000c665  jz      short loc_18000C66F
0x18000c667  mov     rcx, rbx
0x18000c66a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c66f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c676  test    rax, rax
0x18000c679  jz      short loc_18000C689
0x18000c67b  test    byte ptr [rbx+4], 2
0x18000c67f  jnz     short loc_18000C689
0x18000c681  mov     rcx, rbx
0x18000c684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c689  cmp     [rbx+8], edi
0x18000c68c  jl      short loc_18000C6A8
0x18000c68e  cmp     r15d, 3
0x18000c692  jnz     loc_18000C777
0x18000c698  mov     ecx, 8000FFFFh; this
0x18000c69d  mov     [rbx+8], ecx
0x18000c6a0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c6a5  mov     [rbx+0Ch], eax
0x18000c6a8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000c6af  jnz     short loc_18000C6D0
0x18000c6b1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000c6b8  test    rax, rax
0x18000c6bb  jz      short loc_18000C6C6
0x18000c6bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6c2  test    al, al
0x18000c6c4  jmp     short loc_18000C6CE
0x18000c6c6  call    cs:__imp_IsDebuggerPresent
0x18000c6cc  test    eax, eax
0x18000c6ce  jz      short loc_18000C6D6
0x18000c6d0  test    byte ptr [rbx+4], 2
0x18000c6d4  jz      short loc_18000C6FA
0x18000c6d6  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c6dd  test    rax, rax
0x18000c6e0  jz      short loc_18000C73E
0x18000c6e2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000c6e9  jnz     short loc_18000C73E
0x18000c6eb  xor     r8d, r8d
0x18000c6ee  xor     edx, edx
0x18000c6f0  mov     rcx, rbx
0x18000c6f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6f8  jmp     short loc_18000C73E
0x18000c6fa  mov     ebp, 800h
0x18000c6ff  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c706  test    rax, rax
0x18000c709  jz      short loc_18000C722
0x18000c70b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000c712  jnz     short loc_18000C722
0x18000c714  mov     r8d, ebp
0x18000c717  mov     rdx, rsi
0x18000c71a  mov     rcx, rbx
0x18000c71d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c722  cmp     [rsi], di
0x18000c725  jnz     short loc_18000C735
0x18000c727  mov     r8, rbx; unsigned __int64
0x18000c72a  mov     rdx, rbp; unsigned __int16 *
0x18000c72d  mov     rcx, rsi; this
0x18000c730  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000c735  mov     rcx, rsi; lpOutputString
0x18000c738  call    cs:__imp_OutputDebugStringW
0x18000c73e  test    byte ptr [rbx+4], 4
0x18000c742  jnz     short loc_18000C74D
0x18000c744  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000c74b  jz      short loc_18000C75F
0x18000c74d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000c754  test    rax, rax
0x18000c757  jz      short loc_18000C75F
0x18000c759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c75e  nop
0x18000c75f  mov     rbx, [rsp+78h+arg_10]
0x18000c767  add     rsp, 40h
0x18000c76b  pop     r15
0x18000c76d  pop     r14
0x18000c76f  pop     r13
0x18000c771  pop     r12
0x18000c773  pop     rdi
0x18000c774  pop     rsi
0x18000c775  pop     rbp
0x18000c776  retn
0x18000c777  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
