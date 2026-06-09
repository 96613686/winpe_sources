# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1801b5c14`
- end: `0x1801b5f54`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `832`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1801b4ab0`
- `0x1801b4bb4`
- `0x1801b5b24`

## callees

- `0x1801b5970`
- `0x1801b5c14`
- `0x1801b5f5c`
- `0x180202b98`
- `0x18022aac8`
- `0x18022b4d8`
- `0x18022b500`
- `0x18022b514`
- `0x18022be3c`
- `0x1802b6010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801b5ce4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801b5ce4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1802b2374`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1802b2374`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1801b5dd9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1801b5dd9`

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
  _WORD *v20; // rax
  DWORD CurrentThreadId; // eax
  int v22; // edx
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  int v27; // eax
  int v28; // edx
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
        v27 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v28);
        }
        v27 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v27 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_5;
    }
  }
  else
  {
    v27 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v27;
LABEL_5:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v20 = a9;
  if ( !a9 || !*a9 )
    v20 = 0;
  *(_QWORD *)(a16 + 24) = v20;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v22);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (wil::g_pfnIsDebuggerPresent
      ? (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0)
      : (v26 = !IsDebuggerPresent()),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
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
0x1801b5c14  mov     [rsp+arg_10], rbx
0x1801b5c19  mov     [rsp+arg_8], edx
0x1801b5c1d  mov     [rsp+arg_0], rcx
0x1801b5c22  push    rbp
0x1801b5c23  push    rsi
0x1801b5c24  push    rdi
0x1801b5c25  push    r12
0x1801b5c27  push    r13
0x1801b5c29  push    r14
0x1801b5c2b  push    r15
0x1801b5c2d  sub     rsp, 40h
0x1801b5c31  mov     r14, [rsp+78h+arg_38]
0x1801b5c39  xor     eax, eax
0x1801b5c3b  mov     rbx, [rsp+78h+arg_78]
0x1801b5c43  xor     ebp, ebp
0x1801b5c45  mov     r15d, [rsp+78h+arg_30]
0x1801b5c4d  mov     r10, rcx
0x1801b5c50  mov     rsi, [rsp+78h+lpOutputString]
0x1801b5c58  mov     r12, r9
0x1801b5c5b  mov     r13, r8
0x1801b5c5e  mov     ecx, r15d
0x1801b5c61  mov     [rsi], ax
0x1801b5c64  mov     rax, [rsp+78h+arg_60]
0x1801b5c6c  mov     byte ptr [rax], 0
0x1801b5c6f  mov     edi, [r14]
0x1801b5c72  mov     [rbx+8], edi
0x1801b5c75  mov     eax, [r14+4]
0x1801b5c79  mov     [rbx+0Ch], eax
0x1801b5c7c  test    r15d, r15d
0x1801b5c7f  jz      loc_1801B5ECF
0x1801b5c85  sub     ecx, 1
0x1801b5c88  jz      loc_1801B5E2B
0x1801b5c8e  sub     ecx, 1
0x1801b5c91  jz      loc_1801B5E86
0x1801b5c97  cmp     ecx, 1
0x1801b5c9a  jz      loc_1801B5E7D
0x1801b5ca0  mov     eax, [rsp+78h+arg_70]
0x1801b5ca7  mov     [rbx+4], eax
0x1801b5caa  mov     [rbx], r15d
0x1801b5cad  cmp     dword ptr [r14+8], 1
0x1801b5cb2  jz      loc_1801B5EDB
0x1801b5cb8  mov     eax, 1
0x1801b5cbd  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1801b5cc5  inc     eax
0x1801b5cc7  xor     edi, edi
0x1801b5cc9  mov     [rbx+10h], eax
0x1801b5ccc  mov     rax, [rsp+78h+arg_40]
0x1801b5cd4  test    rax, rax
0x1801b5cd7  jnz     loc_1801B5EE6
0x1801b5cdd  mov     rax, rdi
0x1801b5ce0  mov     [rbx+18h], rax
0x1801b5ce4  call    cs:__imp_GetCurrentThreadId
0x1801b5cea  mov     [rbx+38h], r13
0x1801b5cee  xorps   xmm0, xmm0
0x1801b5cf1  mov     [rbx+20h], eax
0x1801b5cf4  mov     eax, [rsp+78h+arg_8]
0x1801b5cfb  mov     [rbx+40h], eax
0x1801b5cfe  mov     rax, [rsp+78h+arg_20]
0x1801b5d06  mov     [rbx+28h], rax
0x1801b5d0a  mov     rax, [rsp+78h+arg_28]
0x1801b5d12  mov     [rbx+88h], rax
0x1801b5d19  mov     rax, [rsp+78h+arg_0]
0x1801b5d21  mov     [rbx+90h], rax
0x1801b5d28  xor     eax, eax
0x1801b5d2a  mov     [rbx+44h], ebp
0x1801b5d2d  mov     [rbx+30h], r12
0x1801b5d31  mov     [rbx+48h], rdi
0x1801b5d35  movups  xmmword ptr [rbx+68h], xmm0
0x1801b5d39  mov     [rbx+78h], rax
0x1801b5d3d  movups  xmmword ptr [rbx+50h], xmm0
0x1801b5d41  mov     [rbx+60h], rax
0x1801b5d45  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1801b5d4c  test    rax, rax
0x1801b5d4f  jz      loc_1801B5E75
0x1801b5d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5d5a  mov     [rbx+80h], rax
0x1801b5d61  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1801b5d68  test    rax, rax
0x1801b5d6b  jz      short loc_1801B5D75
0x1801b5d6d  mov     rcx, rbx
0x1801b5d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5d75  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1801b5d7c  test    rax, rax
0x1801b5d7f  jz      short loc_1801B5D97
0x1801b5d81  mov     rdx, [rsp+78h+arg_60]
0x1801b5d89  mov     r8d, 400h
0x1801b5d8f  mov     rcx, rbx
0x1801b5d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5d97  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1801b5d9e  test    rax, rax
0x1801b5da1  jz      short loc_1801B5DAB
0x1801b5da3  mov     rcx, rbx
0x1801b5da6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5dab  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1801b5db2  test    rax, rax
0x1801b5db5  jnz     loc_1801B5EF4
0x1801b5dbb  cmp     [rbx+8], edi
0x1801b5dbe  jge     loc_1801B5F0B
0x1801b5dc4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1801b5dcb  jnz     short loc_1801B5E39
0x1801b5dcd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1801b5dd4  test    rax, rax
0x1801b5dd7  jnz     short loc_1801B5E22
0x1801b5dd9  call    cs:__imp_IsDebuggerPresent
0x1801b5ddf  test    eax, eax
0x1801b5de1  jnz     short loc_1801B5E39
0x1801b5de3  mov     rax, cs:g_pfnResultLoggingCallback
0x1801b5dea  test    rax, rax
0x1801b5ded  jnz     loc_1801B5F1B
0x1801b5df3  test    byte ptr [rbx+4], 4
0x1801b5df7  jnz     loc_1801B5F3A
0x1801b5dfd  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1801b5e04  jnz     loc_1801B5F3A
0x1801b5e0a  mov     rbx, [rsp+78h+arg_10]
0x1801b5e12  add     rsp, 40h
0x1801b5e16  pop     r15
0x1801b5e18  pop     r14
0x1801b5e1a  pop     r13
0x1801b5e1c  pop     r12
0x1801b5e1e  pop     rdi
0x1801b5e1f  pop     rsi
0x1801b5e20  pop     rbp
0x1801b5e21  retn
0x1801b5e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5e27  test    al, al
0x1801b5e29  jmp     short loc_1801B5DE1
0x1801b5e2b  mov     ecx, edi; this
0x1801b5e2d  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1801b5e32  mov     ebp, eax
0x1801b5e34  jmp     loc_1801B5CA0
0x1801b5e39  test    byte ptr [rbx+4], 2
0x1801b5e3d  jnz     short loc_1801B5DE3
0x1801b5e3f  mov     rax, cs:g_pfnResultLoggingCallback
0x1801b5e46  mov     ebp, 800h
0x1801b5e4b  test    rax, rax
0x1801b5e4e  jz      loc_1802B235E
0x1801b5e54  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1801b5e5b  jnz     loc_1802B235E
0x1801b5e61  mov     r8d, ebp
0x1801b5e64  mov     rdx, rsi
0x1801b5e67  mov     rcx, rbx
0x1801b5e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5e6f  nop
0x1801b5e70  jmp     loc_1802B235E
0x1801b5e75  mov     rax, rdi
0x1801b5e78  jmp     loc_1801B5D5A
0x1801b5e7d  mov     ecx, edi; this
0x1801b5e7f  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1801b5e84  jmp     short loc_1801B5E32
0x1801b5e86  test    edi, edi
0x1801b5e88  js      loc_1802B233C
0x1801b5e8e  mov     rax, [rsp+78h+arg_28]
0x1801b5e96  mov     edi, 8007029Ch
0x1801b5e9b  mov     [rsp+78h+var_40], ebp
0x1801b5e9f  mov     rcx, r10; int
0x1801b5ea2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1801b5ea6  mov     [rsp+78h+var_50], rax; __int64
0x1801b5eab  mov     rax, [rsp+78h+arg_20]
0x1801b5eb3  mov     [rsp+78h+var_58], rax; __int64
0x1801b5eb8  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1801b5ebd  mov     ecx, edi; this
0x1801b5ebf  mov     [rbx+8], edi
0x1801b5ec2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1801b5ec7  mov     [rbx+0Ch], eax
0x1801b5eca  jmp     loc_1802B233C
0x1801b5ecf  mov     ecx, edi; this
0x1801b5ed1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1801b5ed6  jmp     loc_1801B5E32
0x1801b5edb  or      eax, 8
0x1801b5ede  mov     [rbx+4], eax
0x1801b5ee1  jmp     loc_1801B5CB8
0x1801b5ee6  cmp     [rax], di
0x1801b5ee9  jnz     loc_1801B5CE0
0x1801b5eef  jmp     loc_1801B5CDD
0x1801b5ef4  test    byte ptr [rbx+4], 2
0x1801b5ef8  jnz     loc_1801B5DBB
0x1801b5efe  mov     rcx, rbx
0x1801b5f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5f06  jmp     loc_1801B5DBB
0x1801b5f0b  cmp     r15d, 3
0x1801b5f0f  jz      loc_1802B2349
0x1801b5f15  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1801b5f1b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1801b5f22  jnz     loc_1801B5DF3
0x1801b5f28  xor     r8d, r8d
0x1801b5f2b  xor     edx, edx
0x1801b5f2d  mov     rcx, rbx
0x1801b5f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5f35  jmp     loc_1801B5DF3
0x1801b5f3a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1801b5f41  test    rax, rax
0x1801b5f44  jz      loc_1801B5E0A
0x1801b5f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801b5f4f  jmp     loc_1801B5E0A
0x1802b233c  mov     ecx, edi; this
0x1802b233e  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1802b2343  nop
0x1802b2344  jmp     loc_1801B5E32
0x1802b2349  mov     ecx, 8000FFFFh; this
0x1802b234e  mov     [rbx+8], ecx
0x1802b2351  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1802b2356  mov     [rbx+0Ch], eax
0x1802b2359  jmp     loc_1801B5DC4
0x1802b235e  cmp     [rsi], di
0x1802b2361  jnz     short loc_1802B2371
0x1802b2363  mov     r8, rbx; unsigned __int64
0x1802b2366  mov     rdx, rbp; unsigned __int16 *
0x1802b2369  mov     rcx, rsi; this
0x1802b236c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1802b2371  mov     rcx, rsi; lpOutputString
0x1802b2374  call    cs:__imp_OutputDebugStringW
0x1802b237a  nop
0x1802b237b  jmp     loc_1801B5DF3
```
