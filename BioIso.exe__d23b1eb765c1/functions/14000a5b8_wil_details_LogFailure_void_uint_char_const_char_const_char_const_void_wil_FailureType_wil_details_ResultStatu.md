# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000a5b8`
- end: `0x14000a8c0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `776`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x14000a4b8`
- `0x140025264`
- `0x140025324`
- `0x14002a63c`

## callees

- `0x140003bf0`
- `0x14000a5b8`
- `0x14002518c`
- `0x1400266d4`
- `0x140027ac4`
- `0x140027af0`
- `0x140027bb4`
- `0x140027bd4`
- `0x140029658`
- `0x140085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a6db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a6db`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000a802`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000a802`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000a87a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000a87a`

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
0x14000a5b8  mov     [rsp+arg_10], rbx
0x14000a5bd  mov     [rsp+arg_8], edx
0x14000a5c1  mov     [rsp+arg_0], rcx
0x14000a5c6  push    rbp
0x14000a5c7  push    rsi
0x14000a5c8  push    rdi
0x14000a5c9  push    r12
0x14000a5cb  push    r13
0x14000a5cd  push    r14
0x14000a5cf  push    r15
0x14000a5d1  sub     rsp, 40h
0x14000a5d5  mov     r12, r9
0x14000a5d8  mov     r13, r8
0x14000a5db  mov     r10, rcx
0x14000a5de  xor     eax, eax
0x14000a5e0  mov     rsi, [rsp+78h+lpOutputString]
0x14000a5e8  mov     [rsi], ax
0x14000a5eb  mov     rax, [rsp+78h+arg_60]
0x14000a5f3  mov     byte ptr [rax], 0
0x14000a5f6  mov     r14, [rsp+78h+arg_38]
0x14000a5fe  mov     edi, [r14]
0x14000a601  mov     rbx, [rsp+78h+arg_78]
0x14000a609  mov     [rbx+8], edi
0x14000a60c  mov     eax, [r14+4]
0x14000a610  mov     [rbx+0Ch], eax
0x14000a613  xor     ebp, ebp
0x14000a615  mov     r15d, [rsp+78h+arg_30]
0x14000a61d  mov     ecx, r15d
0x14000a620  test    r15d, r15d
0x14000a623  jz      short loc_14000A68B
0x14000a625  sub     ecx, 1
0x14000a628  jz      short loc_14000A682
0x14000a62a  sub     ecx, 1
0x14000a62d  jz      short loc_14000A63D
0x14000a62f  cmp     ecx, 1
0x14000a632  jnz     short loc_14000A694
0x14000a634  mov     ecx, edi; this
0x14000a636  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000a63b  jmp     short loc_14000A692
0x14000a63d  test    edi, edi
0x14000a63f  js      short loc_14000A679
0x14000a641  mov     edi, 8007029Ch
0x14000a646  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000a64a  mov     rax, [rsp+78h+arg_28]
0x14000a652  mov     [rsp+78h+var_50], rax; __int64
0x14000a657  mov     rax, [rsp+78h+arg_20]
0x14000a65f  mov     [rsp+78h+var_58], rax; __int64
0x14000a664  mov     rcx, r10; int
0x14000a667  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000a66c  mov     [rbx+8], edi
0x14000a66f  mov     ecx, edi; this
0x14000a671  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000a676  mov     [rbx+0Ch], eax
0x14000a679  mov     ecx, edi; this
0x14000a67b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000a680  jmp     short loc_14000A692
0x14000a682  mov     ecx, edi; this
0x14000a684  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000a689  jmp     short loc_14000A692
0x14000a68b  mov     ecx, edi; this
0x14000a68d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000a692  mov     ebp, eax
0x14000a694  mov     [rbx], r15d
0x14000a697  mov     eax, [rsp+78h+arg_70]
0x14000a69e  mov     [rbx+4], eax
0x14000a6a1  cmp     dword ptr [r14+8], 1
0x14000a6a6  jnz     short loc_14000A6AE
0x14000a6a8  or      eax, 8
0x14000a6ab  mov     [rbx+4], eax
0x14000a6ae  mov     eax, 1
0x14000a6b3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000a6bb  inc     eax
0x14000a6bd  mov     [rbx+10h], eax
0x14000a6c0  mov     rax, [rsp+78h+arg_40]
0x14000a6c8  xor     edi, edi
0x14000a6ca  test    rax, rax
0x14000a6cd  jz      short loc_14000A6D4
0x14000a6cf  cmp     [rax], di
0x14000a6d2  jnz     short loc_14000A6D7
0x14000a6d4  mov     rax, rdi
0x14000a6d7  mov     [rbx+18h], rax
0x14000a6db  call    cs:__imp_GetCurrentThreadId
0x14000a6e2  nop     dword ptr [rax+rax+00h]
0x14000a6e7  mov     [rbx+20h], eax
0x14000a6ea  mov     [rbx+38h], r13
0x14000a6ee  mov     eax, [rsp+78h+arg_8]
0x14000a6f5  mov     [rbx+40h], eax
0x14000a6f8  mov     [rbx+44h], ebp
0x14000a6fb  mov     rax, [rsp+78h+arg_20]
0x14000a703  mov     [rbx+28h], rax
0x14000a707  mov     [rbx+30h], r12
0x14000a70b  mov     rax, [rsp+78h+arg_28]
0x14000a713  mov     [rbx+88h], rax
0x14000a71a  mov     rax, [rsp+78h+arg_0]
0x14000a722  mov     [rbx+90h], rax
0x14000a729  mov     [rbx+48h], rdi
0x14000a72d  xorps   xmm0, xmm0
0x14000a730  xor     eax, eax
0x14000a732  movups  xmmword ptr [rbx+68h], xmm0
0x14000a736  mov     [rbx+78h], rax
0x14000a73a  movups  xmmword ptr [rbx+50h], xmm0
0x14000a73e  mov     [rbx+60h], rax
0x14000a742  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000a749  test    rax, rax
0x14000a74c  jz      short loc_14000A755
0x14000a74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a753  jmp     short loc_14000A758
0x14000a755  mov     rax, rdi
0x14000a758  mov     [rbx+80h], rax
0x14000a75f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000a766  test    rax, rax
0x14000a769  jz      short loc_14000A773
0x14000a76b  mov     rcx, rbx
0x14000a76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a773  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000a77a  test    rax, rax
0x14000a77d  jz      short loc_14000A795
0x14000a77f  mov     r8d, 400h
0x14000a785  mov     rdx, [rsp+78h+arg_60]
0x14000a78d  mov     rcx, rbx
0x14000a790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a795  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a79c  test    rax, rax
0x14000a79f  jz      short loc_14000A7A9
0x14000a7a1  mov     rcx, rbx
0x14000a7a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7a9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a7b0  test    rax, rax
0x14000a7b3  jz      short loc_14000A7C3
0x14000a7b5  test    byte ptr [rbx+4], 2
0x14000a7b9  jnz     short loc_14000A7C3
0x14000a7bb  mov     rcx, rbx
0x14000a7be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7c3  cmp     [rbx+8], edi
0x14000a7c6  jl      short loc_14000A7E4
0x14000a7c8  cmp     r15d, 3
0x14000a7cc  jz      short loc_14000A7D4
0x14000a7ce  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000a7d4  mov     ecx, 8000FFFFh; this
0x14000a7d9  mov     [rbx+8], ecx
0x14000a7dc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000a7e1  mov     [rbx+0Ch], eax
0x14000a7e4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000a7eb  jnz     short loc_14000A812
0x14000a7ed  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000a7f4  test    rax, rax
0x14000a7f7  jz      short loc_14000A802
0x14000a7f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7fe  test    al, al
0x14000a800  jmp     short loc_14000A810
0x14000a802  call    cs:__imp_IsDebuggerPresent
0x14000a809  nop     dword ptr [rax+rax+00h]
0x14000a80e  test    eax, eax
0x14000a810  jz      short loc_14000A818
0x14000a812  test    byte ptr [rbx+4], 2
0x14000a816  jz      short loc_14000A83C
0x14000a818  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a81f  test    rax, rax
0x14000a822  jz      short loc_14000A886
0x14000a824  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000a82b  jnz     short loc_14000A886
0x14000a82d  xor     r8d, r8d
0x14000a830  xor     edx, edx
0x14000a832  mov     rcx, rbx
0x14000a835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a83a  jmp     short loc_14000A886
0x14000a83c  mov     ebp, 800h
0x14000a841  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a848  test    rax, rax
0x14000a84b  jz      short loc_14000A864
0x14000a84d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000a854  jnz     short loc_14000A864
0x14000a856  mov     r8d, ebp
0x14000a859  mov     rdx, rsi
0x14000a85c  mov     rcx, rbx
0x14000a85f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a864  cmp     [rsi], di
0x14000a867  jnz     short loc_14000A877
0x14000a869  mov     r8, rbx; unsigned __int64
0x14000a86c  mov     rdx, rbp; unsigned __int16 *
0x14000a86f  mov     rcx, rsi; this
0x14000a872  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000a877  mov     rcx, rsi; lpOutputString
0x14000a87a  call    cs:__imp_OutputDebugStringW
0x14000a881  nop     dword ptr [rax+rax+00h]
0x14000a886  test    byte ptr [rbx+4], 4
0x14000a88a  jnz     short loc_14000A895
0x14000a88c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000a893  jz      short loc_14000A8A7
0x14000a895  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000a89c  test    rax, rax
0x14000a89f  jz      short loc_14000A8A7
0x14000a8a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a8a6  nop
0x14000a8a7  mov     rbx, [rsp+78h+arg_10]
0x14000a8af  add     rsp, 40h
0x14000a8b3  pop     r15
0x14000a8b5  pop     r14
0x14000a8b7  pop     r13
0x14000a8b9  pop     r12
0x14000a8bb  pop     rdi
0x14000a8bc  pop     rsi
0x14000a8bd  pop     rbp
0x14000a8be  retn
```
