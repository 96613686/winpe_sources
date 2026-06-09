# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000a148`
- end: `0x18000a441`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180007334`
- `0x180007678`

## callees

- `0x180007274`
- `0x180009564`
- `0x180009dec`
- `0x18000a148`
- `0x18000a8e8`
- `0x18000a910`
- `0x18000a924`
- `0x18000a940`
- `0x18000c140`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a26b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a26b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a3fc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a3fc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a38a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a38a`

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
0x18000a148  mov     [rsp+arg_10], rbx
0x18000a14d  mov     [rsp+arg_8], edx
0x18000a151  mov     [rsp+arg_0], rcx
0x18000a156  push    rbp
0x18000a157  push    rsi
0x18000a158  push    rdi
0x18000a159  push    r12
0x18000a15b  push    r13
0x18000a15d  push    r14
0x18000a15f  push    r15
0x18000a161  sub     rsp, 40h
0x18000a165  mov     r12, r9
0x18000a168  mov     r13, r8
0x18000a16b  mov     r10, rcx
0x18000a16e  xor     eax, eax
0x18000a170  mov     rsi, [rsp+78h+lpOutputString]
0x18000a178  mov     [rsi], ax
0x18000a17b  mov     rax, [rsp+78h+arg_60]
0x18000a183  mov     byte ptr [rax], 0
0x18000a186  mov     r14, [rsp+78h+arg_38]
0x18000a18e  mov     edi, [r14]
0x18000a191  mov     rbx, [rsp+78h+arg_78]
0x18000a199  mov     [rbx+8], edi
0x18000a19c  mov     eax, [r14+4]
0x18000a1a0  mov     [rbx+0Ch], eax
0x18000a1a3  xor     ebp, ebp
0x18000a1a5  mov     r15d, [rsp+78h+arg_30]
0x18000a1ad  mov     ecx, r15d
0x18000a1b0  test    r15d, r15d
0x18000a1b3  jz      short loc_18000A21B
0x18000a1b5  sub     ecx, 1
0x18000a1b8  jz      short loc_18000A212
0x18000a1ba  sub     ecx, 1
0x18000a1bd  jz      short loc_18000A1CD
0x18000a1bf  cmp     ecx, 1
0x18000a1c2  jnz     short loc_18000A224
0x18000a1c4  mov     ecx, edi; this
0x18000a1c6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a1cb  jmp     short loc_18000A222
0x18000a1cd  test    edi, edi
0x18000a1cf  js      short loc_18000A209
0x18000a1d1  mov     edi, 8007029Ch
0x18000a1d6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a1da  mov     rax, [rsp+78h+arg_28]
0x18000a1e2  mov     [rsp+78h+var_50], rax; __int64
0x18000a1e7  mov     rax, [rsp+78h+arg_20]
0x18000a1ef  mov     [rsp+78h+var_58], rax; __int64
0x18000a1f4  mov     rcx, r10; int
0x18000a1f7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a1fc  mov     [rbx+8], edi
0x18000a1ff  mov     ecx, edi; this
0x18000a201  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a206  mov     [rbx+0Ch], eax
0x18000a209  mov     ecx, edi; this
0x18000a20b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a210  jmp     short loc_18000A222
0x18000a212  mov     ecx, edi; this
0x18000a214  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a219  jmp     short loc_18000A222
0x18000a21b  mov     ecx, edi; this
0x18000a21d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a222  mov     ebp, eax
0x18000a224  mov     [rbx], r15d
0x18000a227  mov     eax, [rsp+78h+arg_70]
0x18000a22e  mov     [rbx+4], eax
0x18000a231  cmp     dword ptr [r14+8], 1
0x18000a236  jnz     short loc_18000A23E
0x18000a238  or      eax, 8
0x18000a23b  mov     [rbx+4], eax
0x18000a23e  mov     eax, 1
0x18000a243  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a24b  inc     eax
0x18000a24d  mov     [rbx+10h], eax
0x18000a250  mov     rax, [rsp+78h+arg_40]
0x18000a258  xor     edi, edi
0x18000a25a  test    rax, rax
0x18000a25d  jz      short loc_18000A264
0x18000a25f  cmp     [rax], di
0x18000a262  jnz     short loc_18000A267
0x18000a264  mov     rax, rdi
0x18000a267  mov     [rbx+18h], rax
0x18000a26b  call    cs:__imp_GetCurrentThreadId
0x18000a271  mov     [rbx+20h], eax
0x18000a274  mov     [rbx+38h], r13
0x18000a278  mov     eax, [rsp+78h+arg_8]
0x18000a27f  mov     [rbx+40h], eax
0x18000a282  mov     [rbx+44h], ebp
0x18000a285  mov     rax, [rsp+78h+arg_20]
0x18000a28d  mov     [rbx+28h], rax
0x18000a291  mov     [rbx+30h], r12
0x18000a295  mov     rax, [rsp+78h+arg_28]
0x18000a29d  mov     [rbx+88h], rax
0x18000a2a4  mov     rax, [rsp+78h+arg_0]
0x18000a2ac  mov     [rbx+90h], rax
0x18000a2b3  mov     [rbx+48h], rdi
0x18000a2b7  xorps   xmm0, xmm0
0x18000a2ba  xor     eax, eax
0x18000a2bc  movups  xmmword ptr [rbx+68h], xmm0
0x18000a2c0  mov     [rbx+78h], rax
0x18000a2c4  movups  xmmword ptr [rbx+50h], xmm0
0x18000a2c8  mov     [rbx+60h], rax
0x18000a2cc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a2d3  test    rax, rax
0x18000a2d6  jz      short loc_18000A2DF
0x18000a2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2dd  jmp     short loc_18000A2E2
0x18000a2df  mov     rax, rdi
0x18000a2e2  mov     [rbx+80h], rax
0x18000a2e9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a2f0  test    rax, rax
0x18000a2f3  jz      short loc_18000A2FD
0x18000a2f5  mov     rcx, rbx
0x18000a2f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2fd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a304  test    rax, rax
0x18000a307  jz      short loc_18000A31F
0x18000a309  mov     r8d, 400h
0x18000a30f  mov     rdx, [rsp+78h+arg_60]
0x18000a317  mov     rcx, rbx
0x18000a31a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a31f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a326  test    rax, rax
0x18000a329  jz      short loc_18000A333
0x18000a32b  mov     rcx, rbx
0x18000a32e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a333  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a33a  test    rax, rax
0x18000a33d  jz      short loc_18000A34D
0x18000a33f  test    byte ptr [rbx+4], 2
0x18000a343  jnz     short loc_18000A34D
0x18000a345  mov     rcx, rbx
0x18000a348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a34d  cmp     [rbx+8], edi
0x18000a350  jl      short loc_18000A36C
0x18000a352  cmp     r15d, 3
0x18000a356  jnz     loc_18000A43B
0x18000a35c  mov     ecx, 8000FFFFh; this
0x18000a361  mov     [rbx+8], ecx
0x18000a364  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a369  mov     [rbx+0Ch], eax
0x18000a36c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a373  jnz     short loc_18000A394
0x18000a375  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a37c  test    rax, rax
0x18000a37f  jz      short loc_18000A38A
0x18000a381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a386  test    al, al
0x18000a388  jmp     short loc_18000A392
0x18000a38a  call    cs:__imp_IsDebuggerPresent
0x18000a390  test    eax, eax
0x18000a392  jz      short loc_18000A39A
0x18000a394  test    byte ptr [rbx+4], 2
0x18000a398  jz      short loc_18000A3BE
0x18000a39a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a3a1  test    rax, rax
0x18000a3a4  jz      short loc_18000A402
0x18000a3a6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a3ad  jnz     short loc_18000A402
0x18000a3af  xor     r8d, r8d
0x18000a3b2  xor     edx, edx
0x18000a3b4  mov     rcx, rbx
0x18000a3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3bc  jmp     short loc_18000A402
0x18000a3be  mov     ebp, 800h
0x18000a3c3  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a3ca  test    rax, rax
0x18000a3cd  jz      short loc_18000A3E6
0x18000a3cf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a3d6  jnz     short loc_18000A3E6
0x18000a3d8  mov     r8d, ebp
0x18000a3db  mov     rdx, rsi
0x18000a3de  mov     rcx, rbx
0x18000a3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3e6  cmp     [rsi], di
0x18000a3e9  jnz     short loc_18000A3F9
0x18000a3eb  mov     r8, rbx; unsigned __int64
0x18000a3ee  mov     rdx, rbp; unsigned __int16 *
0x18000a3f1  mov     rcx, rsi; this
0x18000a3f4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a3f9  mov     rcx, rsi; lpOutputString
0x18000a3fc  call    cs:__imp_OutputDebugStringW
0x18000a402  test    byte ptr [rbx+4], 4
0x18000a406  jnz     short loc_18000A411
0x18000a408  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a40f  jz      short loc_18000A423
0x18000a411  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a418  test    rax, rax
0x18000a41b  jz      short loc_18000A423
0x18000a41d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a422  nop
0x18000a423  mov     rbx, [rsp+78h+arg_10]
0x18000a42b  add     rsp, 40h
0x18000a42f  pop     r15
0x18000a431  pop     r14
0x18000a433  pop     r13
0x18000a435  pop     r12
0x18000a437  pop     rdi
0x18000a438  pop     rsi
0x18000a439  pop     rbp
0x18000a43a  retn
0x18000a43b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
