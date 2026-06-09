# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180025c6c`
- end: `0x180025f65`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, WCHAR *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180023760`
- `0x180023aa4`

## callees

- `0x18001bf8c`
- `0x1800236a0`
- `0x180025284`
- `0x180025c6c`
- `0x180026804`
- `0x180026820`
- `0x180026970`
- `0x18002698c`
- `0x180028308`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025d8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025d8f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025f20`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025f20`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180025eae`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180025eae`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW(lpOutputString);
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
0x180025c6c  mov     [rsp+arg_10], rbx
0x180025c71  mov     [rsp+arg_8], edx
0x180025c75  mov     [rsp+arg_0], rcx
0x180025c7a  push    rbp
0x180025c7b  push    rsi
0x180025c7c  push    rdi
0x180025c7d  push    r12
0x180025c7f  push    r13
0x180025c81  push    r14
0x180025c83  push    r15
0x180025c85  sub     rsp, 40h
0x180025c89  mov     r12, r9
0x180025c8c  mov     r13, r8
0x180025c8f  mov     r10, rcx
0x180025c92  xor     eax, eax
0x180025c94  mov     rsi, [rsp+78h+lpOutputString]
0x180025c9c  mov     [rsi], ax
0x180025c9f  mov     rax, [rsp+78h+arg_60]
0x180025ca7  mov     byte ptr [rax], 0
0x180025caa  mov     r14, [rsp+78h+arg_38]
0x180025cb2  mov     edi, [r14]
0x180025cb5  mov     rbx, [rsp+78h+arg_78]
0x180025cbd  mov     [rbx+8], edi
0x180025cc0  mov     eax, [r14+4]
0x180025cc4  mov     [rbx+0Ch], eax
0x180025cc7  xor     ebp, ebp
0x180025cc9  mov     r15d, [rsp+78h+arg_30]
0x180025cd1  mov     ecx, r15d
0x180025cd4  test    r15d, r15d
0x180025cd7  jz      short loc_180025D3F
0x180025cd9  sub     ecx, 1
0x180025cdc  jz      short loc_180025D36
0x180025cde  sub     ecx, 1
0x180025ce1  jz      short loc_180025CF1
0x180025ce3  cmp     ecx, 1
0x180025ce6  jnz     short loc_180025D48
0x180025ce8  mov     ecx, edi; this
0x180025cea  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180025cef  jmp     short loc_180025D46
0x180025cf1  test    edi, edi
0x180025cf3  js      short loc_180025D2D
0x180025cf5  mov     edi, 8007029Ch
0x180025cfa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180025cfe  mov     rax, [rsp+78h+arg_28]
0x180025d06  mov     [rsp+78h+var_50], rax; __int64
0x180025d0b  mov     rax, [rsp+78h+arg_20]
0x180025d13  mov     [rsp+78h+var_58], rax; __int64
0x180025d18  mov     rcx, r10; int
0x180025d1b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180025d20  mov     [rbx+8], edi
0x180025d23  mov     ecx, edi; this
0x180025d25  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180025d2a  mov     [rbx+0Ch], eax
0x180025d2d  mov     ecx, edi; this
0x180025d2f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180025d34  jmp     short loc_180025D46
0x180025d36  mov     ecx, edi; this
0x180025d38  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180025d3d  jmp     short loc_180025D46
0x180025d3f  mov     ecx, edi; this
0x180025d41  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180025d46  mov     ebp, eax
0x180025d48  mov     [rbx], r15d
0x180025d4b  mov     eax, [rsp+78h+arg_70]
0x180025d52  mov     [rbx+4], eax
0x180025d55  cmp     dword ptr [r14+8], 1
0x180025d5a  jnz     short loc_180025D62
0x180025d5c  or      eax, 8
0x180025d5f  mov     [rbx+4], eax
0x180025d62  mov     eax, 1
0x180025d67  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180025d6f  inc     eax
0x180025d71  mov     [rbx+10h], eax
0x180025d74  mov     rax, [rsp+78h+arg_40]
0x180025d7c  xor     edi, edi
0x180025d7e  test    rax, rax
0x180025d81  jz      short loc_180025D88
0x180025d83  cmp     [rax], di
0x180025d86  jnz     short loc_180025D8B
0x180025d88  mov     rax, rdi
0x180025d8b  mov     [rbx+18h], rax
0x180025d8f  call    cs:__imp_GetCurrentThreadId
0x180025d95  mov     [rbx+20h], eax
0x180025d98  mov     [rbx+38h], r13
0x180025d9c  mov     eax, [rsp+78h+arg_8]
0x180025da3  mov     [rbx+40h], eax
0x180025da6  mov     [rbx+44h], ebp
0x180025da9  mov     rax, [rsp+78h+arg_20]
0x180025db1  mov     [rbx+28h], rax
0x180025db5  mov     [rbx+30h], r12
0x180025db9  mov     rax, [rsp+78h+arg_28]
0x180025dc1  mov     [rbx+88h], rax
0x180025dc8  mov     rax, [rsp+78h+arg_0]
0x180025dd0  mov     [rbx+90h], rax
0x180025dd7  mov     [rbx+48h], rdi
0x180025ddb  xorps   xmm0, xmm0
0x180025dde  xor     eax, eax
0x180025de0  movups  xmmword ptr [rbx+68h], xmm0
0x180025de4  mov     [rbx+78h], rax
0x180025de8  movups  xmmword ptr [rbx+50h], xmm0
0x180025dec  mov     [rbx+60h], rax
0x180025df0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180025df7  test    rax, rax
0x180025dfa  jz      short loc_180025E03
0x180025dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e01  jmp     short loc_180025E06
0x180025e03  mov     rax, rdi
0x180025e06  mov     [rbx+80h], rax
0x180025e0d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180025e14  test    rax, rax
0x180025e17  jz      short loc_180025E21
0x180025e19  mov     rcx, rbx
0x180025e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e21  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180025e28  test    rax, rax
0x180025e2b  jz      short loc_180025E43
0x180025e2d  mov     r8d, 400h
0x180025e33  mov     rdx, [rsp+78h+arg_60]
0x180025e3b  mov     rcx, rbx
0x180025e3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e43  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025e4a  test    rax, rax
0x180025e4d  jz      short loc_180025E57
0x180025e4f  mov     rcx, rbx
0x180025e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e57  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025e5e  test    rax, rax
0x180025e61  jz      short loc_180025E71
0x180025e63  test    byte ptr [rbx+4], 2
0x180025e67  jnz     short loc_180025E71
0x180025e69  mov     rcx, rbx
0x180025e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025e71  cmp     [rbx+8], edi
0x180025e74  jl      short loc_180025E90
0x180025e76  cmp     r15d, 3
0x180025e7a  jnz     loc_180025F5F
0x180025e80  mov     ecx, 8000FFFFh; this
0x180025e85  mov     [rbx+8], ecx
0x180025e88  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180025e8d  mov     [rbx+0Ch], eax
0x180025e90  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180025e97  jnz     short loc_180025EB8
0x180025e99  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180025ea0  test    rax, rax
0x180025ea3  jz      short loc_180025EAE
0x180025ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025eaa  test    al, al
0x180025eac  jmp     short loc_180025EB6
0x180025eae  call    cs:__imp_IsDebuggerPresent
0x180025eb4  test    eax, eax
0x180025eb6  jz      short loc_180025EBE
0x180025eb8  test    byte ptr [rbx+4], 2
0x180025ebc  jz      short loc_180025EE2
0x180025ebe  mov     rax, cs:g_pfnResultLoggingCallback
0x180025ec5  test    rax, rax
0x180025ec8  jz      short loc_180025F26
0x180025eca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180025ed1  jnz     short loc_180025F26
0x180025ed3  xor     r8d, r8d
0x180025ed6  xor     edx, edx
0x180025ed8  mov     rcx, rbx
0x180025edb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ee0  jmp     short loc_180025F26
0x180025ee2  mov     ebp, 800h
0x180025ee7  mov     rax, cs:g_pfnResultLoggingCallback
0x180025eee  test    rax, rax
0x180025ef1  jz      short loc_180025F0A
0x180025ef3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180025efa  jnz     short loc_180025F0A
0x180025efc  mov     r8d, ebp
0x180025eff  mov     rdx, rsi
0x180025f02  mov     rcx, rbx
0x180025f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f0a  cmp     [rsi], di
0x180025f0d  jnz     short loc_180025F1D
0x180025f0f  mov     r8, rbx; unsigned __int64
0x180025f12  mov     rdx, rbp; unsigned __int16 *
0x180025f15  mov     rcx, rsi; pszDest
0x180025f18  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180025f1d  mov     rcx, rsi; lpOutputString
0x180025f20  call    cs:__imp_OutputDebugStringW
0x180025f26  test    byte ptr [rbx+4], 4
0x180025f2a  jnz     short loc_180025F35
0x180025f2c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180025f33  jz      short loc_180025F47
0x180025f35  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180025f3c  test    rax, rax
0x180025f3f  jz      short loc_180025F47
0x180025f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025f46  nop
0x180025f47  mov     rbx, [rsp+78h+arg_10]
0x180025f4f  add     rsp, 40h
0x180025f53  pop     r15
0x180025f55  pop     r14
0x180025f57  pop     r13
0x180025f59  pop     r12
0x180025f5b  pop     rdi
0x180025f5c  pop     rsi
0x180025f5d  pop     rbp
0x180025f5e  retn
0x180025f5f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
