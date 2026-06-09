# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180012bbc`
- end: `0x180012eb4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180003d20`
- `0x180004064`

## callees

- `0x180003c60`
- `0x180006ca0`
- `0x1800076a0`
- `0x180012bbc`
- `0x180014f80`
- `0x180014fa0`
- `0x1800150f0`
- `0x18001510c`
- `0x18001b4c8`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012cdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012cdf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180012dfe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180012dfe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180012e70`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180012e70`

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
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
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
0x180012bbc  mov     [rsp+arg_10], rbx
0x180012bc1  mov     [rsp+arg_8], edx
0x180012bc5  mov     [rsp+arg_0], rcx
0x180012bca  push    rbp
0x180012bcb  push    rsi
0x180012bcc  push    rdi
0x180012bcd  push    r12
0x180012bcf  push    r13
0x180012bd1  push    r14
0x180012bd3  push    r15
0x180012bd5  sub     rsp, 40h
0x180012bd9  mov     r14, [rsp+78h+arg_38]
0x180012be1  xor     eax, eax
0x180012be3  mov     rbx, [rsp+78h+arg_78]
0x180012beb  xor     ebp, ebp
0x180012bed  mov     r15d, [rsp+78h+arg_30]
0x180012bf5  mov     r10, rcx
0x180012bf8  mov     rsi, [rsp+78h+lpOutputString]
0x180012c00  mov     r12, r9
0x180012c03  mov     r13, r8
0x180012c06  mov     ecx, r15d
0x180012c09  mov     [rsi], ax
0x180012c0c  mov     rax, [rsp+78h+arg_60]
0x180012c14  mov     byte ptr [rax], 0
0x180012c17  mov     edi, [r14]
0x180012c1a  mov     [rbx+8], edi
0x180012c1d  mov     eax, [r14+4]
0x180012c21  mov     [rbx+0Ch], eax
0x180012c24  test    r15d, r15d
0x180012c27  jz      short loc_180012C8F
0x180012c29  sub     ecx, 1
0x180012c2c  jz      short loc_180012C86
0x180012c2e  sub     ecx, 1
0x180012c31  jz      short loc_180012C41
0x180012c33  cmp     ecx, 1
0x180012c36  jnz     short loc_180012C98
0x180012c38  mov     ecx, edi; this
0x180012c3a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180012c3f  jmp     short loc_180012C96
0x180012c41  test    edi, edi
0x180012c43  js      short loc_180012C7D
0x180012c45  mov     rax, [rsp+78h+arg_28]
0x180012c4d  mov     edi, 8007029Ch
0x180012c52  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180012c56  mov     rcx, r10; int
0x180012c59  mov     [rsp+78h+var_50], rax; __int64
0x180012c5e  mov     rax, [rsp+78h+arg_20]
0x180012c66  mov     [rsp+78h+var_58], rax; __int64
0x180012c6b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180012c70  mov     ecx, edi; this
0x180012c72  mov     [rbx+8], edi
0x180012c75  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180012c7a  mov     [rbx+0Ch], eax
0x180012c7d  mov     ecx, edi; this
0x180012c7f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180012c84  jmp     short loc_180012C96
0x180012c86  mov     ecx, edi; this
0x180012c88  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180012c8d  jmp     short loc_180012C96
0x180012c8f  mov     ecx, edi; this
0x180012c91  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180012c96  mov     ebp, eax
0x180012c98  mov     eax, [rsp+78h+arg_70]
0x180012c9f  mov     [rbx+4], eax
0x180012ca2  mov     [rbx], r15d
0x180012ca5  cmp     dword ptr [r14+8], 1
0x180012caa  jnz     short loc_180012CB2
0x180012cac  or      eax, 8
0x180012caf  mov     [rbx+4], eax
0x180012cb2  mov     eax, 1
0x180012cb7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180012cbf  inc     eax
0x180012cc1  xor     edi, edi
0x180012cc3  mov     [rbx+10h], eax
0x180012cc6  mov     rax, [rsp+78h+arg_40]
0x180012cce  test    rax, rax
0x180012cd1  jz      short loc_180012CD8
0x180012cd3  cmp     [rax], di
0x180012cd6  jnz     short loc_180012CDB
0x180012cd8  mov     rax, rdi
0x180012cdb  mov     [rbx+18h], rax
0x180012cdf  call    cs:__imp_GetCurrentThreadId
0x180012ce5  mov     [rbx+38h], r13
0x180012ce9  xorps   xmm0, xmm0
0x180012cec  mov     [rbx+20h], eax
0x180012cef  mov     eax, [rsp+78h+arg_8]
0x180012cf6  mov     [rbx+40h], eax
0x180012cf9  mov     rax, [rsp+78h+arg_20]
0x180012d01  mov     [rbx+28h], rax
0x180012d05  mov     rax, [rsp+78h+arg_28]
0x180012d0d  mov     [rbx+88h], rax
0x180012d14  mov     rax, [rsp+78h+arg_0]
0x180012d1c  mov     [rbx+90h], rax
0x180012d23  xor     eax, eax
0x180012d25  mov     [rbx+44h], ebp
0x180012d28  mov     [rbx+30h], r12
0x180012d2c  mov     [rbx+48h], rdi
0x180012d30  movups  xmmword ptr [rbx+68h], xmm0
0x180012d34  mov     [rbx+78h], rax
0x180012d38  movups  xmmword ptr [rbx+50h], xmm0
0x180012d3c  mov     [rbx+60h], rax
0x180012d40  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180012d47  test    rax, rax
0x180012d4a  jz      short loc_180012D53
0x180012d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d51  jmp     short loc_180012D56
0x180012d53  mov     rax, rdi
0x180012d56  mov     [rbx+80h], rax
0x180012d5d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180012d64  test    rax, rax
0x180012d67  jz      short loc_180012D71
0x180012d69  mov     rcx, rbx
0x180012d6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d71  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180012d78  test    rax, rax
0x180012d7b  jz      short loc_180012D93
0x180012d7d  mov     rdx, [rsp+78h+arg_60]
0x180012d85  mov     r8d, 400h
0x180012d8b  mov     rcx, rbx
0x180012d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d93  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012d9a  test    rax, rax
0x180012d9d  jz      short loc_180012DA7
0x180012d9f  mov     rcx, rbx
0x180012da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012da7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012dae  test    rax, rax
0x180012db1  jz      short loc_180012DC1
0x180012db3  test    byte ptr [rbx+4], 2
0x180012db7  jnz     short loc_180012DC1
0x180012db9  mov     rcx, rbx
0x180012dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dc1  cmp     [rbx+8], edi
0x180012dc4  jl      short loc_180012DE0
0x180012dc6  cmp     r15d, 3
0x180012dca  jnz     loc_180012EAE
0x180012dd0  mov     ecx, 8000FFFFh; this
0x180012dd5  mov     [rbx+8], ecx
0x180012dd8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180012ddd  mov     [rbx+0Ch], eax
0x180012de0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180012de7  jnz     short loc_180012E08
0x180012de9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180012df0  test    rax, rax
0x180012df3  jz      short loc_180012DFE
0x180012df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dfa  test    al, al
0x180012dfc  jmp     short loc_180012E06
0x180012dfe  call    cs:__imp_IsDebuggerPresent
0x180012e04  test    eax, eax
0x180012e06  jz      short loc_180012E0E
0x180012e08  test    byte ptr [rbx+4], 2
0x180012e0c  jz      short loc_180012E32
0x180012e0e  mov     rax, cs:g_pfnResultLoggingCallback
0x180012e15  test    rax, rax
0x180012e18  jz      short loc_180012E76
0x180012e1a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180012e21  jnz     short loc_180012E76
0x180012e23  xor     r8d, r8d
0x180012e26  xor     edx, edx
0x180012e28  mov     rcx, rbx
0x180012e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e30  jmp     short loc_180012E76
0x180012e32  mov     rax, cs:g_pfnResultLoggingCallback
0x180012e39  mov     ebp, 800h
0x180012e3e  test    rax, rax
0x180012e41  jz      short loc_180012E5A
0x180012e43  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180012e4a  jnz     short loc_180012E5A
0x180012e4c  mov     r8d, ebp
0x180012e4f  mov     rdx, rsi
0x180012e52  mov     rcx, rbx
0x180012e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e5a  cmp     [rsi], di
0x180012e5d  jnz     short loc_180012E6D
0x180012e5f  mov     r8, rbx; unsigned __int64
0x180012e62  mov     rdx, rbp; unsigned __int16 *
0x180012e65  mov     rcx, rsi; this
0x180012e68  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180012e6d  mov     rcx, rsi; lpOutputString
0x180012e70  call    cs:__imp_OutputDebugStringW
0x180012e76  test    byte ptr [rbx+4], 4
0x180012e7a  jnz     short loc_180012E85
0x180012e7c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180012e83  jz      short loc_180012E96
0x180012e85  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180012e8c  test    rax, rax
0x180012e8f  jz      short loc_180012E96
0x180012e91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e96  mov     rbx, [rsp+78h+arg_10]
0x180012e9e  add     rsp, 40h
0x180012ea2  pop     r15
0x180012ea4  pop     r14
0x180012ea6  pop     r13
0x180012ea8  pop     r12
0x180012eaa  pop     rdi
0x180012eab  pop     rsi
0x180012eac  pop     rbp
0x180012ead  retn
0x180012eae  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
