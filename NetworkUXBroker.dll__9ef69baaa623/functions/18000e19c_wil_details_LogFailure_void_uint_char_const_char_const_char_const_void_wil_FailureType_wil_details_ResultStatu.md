# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000e19c`
- end: `0x18000e495`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000afa8`
- `0x18000b314`
- `0x180010ba0`

## callees

- `0x180005b94`
- `0x180005f7c`
- `0x180006300`
- `0x18000af44`
- `0x18000e19c`
- `0x18000e6f4`
- `0x18000e710`
- `0x18000e72c`
- `0x18000f034`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e2bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e2bf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e450`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e450`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e3de`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e3de`

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
0x18000e19c  mov     [rsp+arg_10], rbx
0x18000e1a1  mov     [rsp+arg_8], edx
0x18000e1a5  mov     [rsp+arg_0], rcx
0x18000e1aa  push    rbp
0x18000e1ab  push    rsi
0x18000e1ac  push    rdi
0x18000e1ad  push    r12
0x18000e1af  push    r13
0x18000e1b1  push    r14
0x18000e1b3  push    r15
0x18000e1b5  sub     rsp, 40h
0x18000e1b9  mov     r12, r9
0x18000e1bc  mov     r13, r8
0x18000e1bf  mov     r10, rcx
0x18000e1c2  xor     eax, eax
0x18000e1c4  mov     rsi, [rsp+78h+lpOutputString]
0x18000e1cc  mov     [rsi], ax
0x18000e1cf  mov     rax, [rsp+78h+arg_60]
0x18000e1d7  mov     byte ptr [rax], 0
0x18000e1da  mov     r14, [rsp+78h+arg_38]
0x18000e1e2  mov     edi, [r14]
0x18000e1e5  mov     rbx, [rsp+78h+arg_78]
0x18000e1ed  mov     [rbx+8], edi
0x18000e1f0  mov     eax, [r14+4]
0x18000e1f4  mov     [rbx+0Ch], eax
0x18000e1f7  xor     ebp, ebp
0x18000e1f9  mov     r15d, [rsp+78h+arg_30]
0x18000e201  mov     ecx, r15d
0x18000e204  test    r15d, r15d
0x18000e207  jz      short loc_18000E26F
0x18000e209  sub     ecx, 1
0x18000e20c  jz      short loc_18000E266
0x18000e20e  sub     ecx, 1
0x18000e211  jz      short loc_18000E221
0x18000e213  cmp     ecx, 1
0x18000e216  jnz     short loc_18000E278
0x18000e218  mov     ecx, edi; this
0x18000e21a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000e21f  jmp     short loc_18000E276
0x18000e221  test    edi, edi
0x18000e223  js      short loc_18000E25D
0x18000e225  mov     edi, 8007029Ch
0x18000e22a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000e22e  mov     rax, [rsp+78h+arg_28]
0x18000e236  mov     [rsp+78h+var_50], rax; __int64
0x18000e23b  mov     rax, [rsp+78h+arg_20]
0x18000e243  mov     [rsp+78h+var_58], rax; __int64
0x18000e248  mov     rcx, r10; int
0x18000e24b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000e250  mov     [rbx+8], edi
0x18000e253  mov     ecx, edi; this
0x18000e255  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e25a  mov     [rbx+0Ch], eax
0x18000e25d  mov     ecx, edi; this
0x18000e25f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000e264  jmp     short loc_18000E276
0x18000e266  mov     ecx, edi; this
0x18000e268  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000e26d  jmp     short loc_18000E276
0x18000e26f  mov     ecx, edi; this
0x18000e271  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000e276  mov     ebp, eax
0x18000e278  mov     [rbx], r15d
0x18000e27b  mov     eax, [rsp+78h+arg_70]
0x18000e282  mov     [rbx+4], eax
0x18000e285  cmp     dword ptr [r14+8], 1
0x18000e28a  jnz     short loc_18000E292
0x18000e28c  or      eax, 8
0x18000e28f  mov     [rbx+4], eax
0x18000e292  mov     eax, 1
0x18000e297  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000e29f  inc     eax
0x18000e2a1  mov     [rbx+10h], eax
0x18000e2a4  mov     rax, [rsp+78h+arg_40]
0x18000e2ac  xor     edi, edi
0x18000e2ae  test    rax, rax
0x18000e2b1  jz      short loc_18000E2B8
0x18000e2b3  cmp     [rax], di
0x18000e2b6  jnz     short loc_18000E2BB
0x18000e2b8  mov     rax, rdi
0x18000e2bb  mov     [rbx+18h], rax
0x18000e2bf  call    cs:__imp_GetCurrentThreadId
0x18000e2c5  mov     [rbx+20h], eax
0x18000e2c8  mov     [rbx+38h], r13
0x18000e2cc  mov     eax, [rsp+78h+arg_8]
0x18000e2d3  mov     [rbx+40h], eax
0x18000e2d6  mov     [rbx+44h], ebp
0x18000e2d9  mov     rax, [rsp+78h+arg_20]
0x18000e2e1  mov     [rbx+28h], rax
0x18000e2e5  mov     [rbx+30h], r12
0x18000e2e9  mov     rax, [rsp+78h+arg_28]
0x18000e2f1  mov     [rbx+88h], rax
0x18000e2f8  mov     rax, [rsp+78h+arg_0]
0x18000e300  mov     [rbx+90h], rax
0x18000e307  mov     [rbx+48h], rdi
0x18000e30b  xorps   xmm0, xmm0
0x18000e30e  xor     eax, eax
0x18000e310  movups  xmmword ptr [rbx+68h], xmm0
0x18000e314  mov     [rbx+78h], rax
0x18000e318  movups  xmmword ptr [rbx+50h], xmm0
0x18000e31c  mov     [rbx+60h], rax
0x18000e320  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000e327  test    rax, rax
0x18000e32a  jz      short loc_18000E333
0x18000e32c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e331  jmp     short loc_18000E336
0x18000e333  mov     rax, rdi
0x18000e336  mov     [rbx+80h], rax
0x18000e33d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e344  test    rax, rax
0x18000e347  jz      short loc_18000E351
0x18000e349  mov     rcx, rbx
0x18000e34c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e351  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e358  test    rax, rax
0x18000e35b  jz      short loc_18000E373
0x18000e35d  mov     r8d, 400h
0x18000e363  mov     rdx, [rsp+78h+arg_60]
0x18000e36b  mov     rcx, rbx
0x18000e36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e373  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e37a  test    rax, rax
0x18000e37d  jz      short loc_18000E387
0x18000e37f  mov     rcx, rbx
0x18000e382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e387  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e38e  test    rax, rax
0x18000e391  jz      short loc_18000E3A1
0x18000e393  test    byte ptr [rbx+4], 2
0x18000e397  jnz     short loc_18000E3A1
0x18000e399  mov     rcx, rbx
0x18000e39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3a1  cmp     [rbx+8], edi
0x18000e3a4  jl      short loc_18000E3C0
0x18000e3a6  cmp     r15d, 3
0x18000e3aa  jnz     loc_18000E48F
0x18000e3b0  mov     ecx, 8000FFFFh; this
0x18000e3b5  mov     [rbx+8], ecx
0x18000e3b8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e3bd  mov     [rbx+0Ch], eax
0x18000e3c0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000e3c7  jnz     short loc_18000E3E8
0x18000e3c9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e3d0  test    rax, rax
0x18000e3d3  jz      short loc_18000E3DE
0x18000e3d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e3da  test    al, al
0x18000e3dc  jmp     short loc_18000E3E6
0x18000e3de  call    cs:__imp_IsDebuggerPresent
0x18000e3e4  test    eax, eax
0x18000e3e6  jz      short loc_18000E3EE
0x18000e3e8  test    byte ptr [rbx+4], 2
0x18000e3ec  jz      short loc_18000E412
0x18000e3ee  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e3f5  test    rax, rax
0x18000e3f8  jz      short loc_18000E456
0x18000e3fa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e401  jnz     short loc_18000E456
0x18000e403  xor     r8d, r8d
0x18000e406  xor     edx, edx
0x18000e408  mov     rcx, rbx
0x18000e40b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e410  jmp     short loc_18000E456
0x18000e412  mov     ebp, 800h
0x18000e417  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e41e  test    rax, rax
0x18000e421  jz      short loc_18000E43A
0x18000e423  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e42a  jnz     short loc_18000E43A
0x18000e42c  mov     r8d, ebp
0x18000e42f  mov     rdx, rsi
0x18000e432  mov     rcx, rbx
0x18000e435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e43a  cmp     [rsi], di
0x18000e43d  jnz     short loc_18000E44D
0x18000e43f  mov     r8, rbx; unsigned __int64
0x18000e442  mov     rdx, rbp; unsigned __int16 *
0x18000e445  mov     rcx, rsi; this
0x18000e448  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000e44d  mov     rcx, rsi; lpOutputString
0x18000e450  call    cs:__imp_OutputDebugStringW
0x18000e456  test    byte ptr [rbx+4], 4
0x18000e45a  jnz     short loc_18000E465
0x18000e45c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000e463  jz      short loc_18000E477
0x18000e465  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e46c  test    rax, rax
0x18000e46f  jz      short loc_18000E477
0x18000e471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e476  nop
0x18000e477  mov     rbx, [rsp+78h+arg_10]
0x18000e47f  add     rsp, 40h
0x18000e483  pop     r15
0x18000e485  pop     r14
0x18000e487  pop     r13
0x18000e489  pop     r12
0x18000e48b  pop     rdi
0x18000e48c  pop     rsi
0x18000e48d  pop     rbp
0x18000e48e  retn
0x18000e48f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
