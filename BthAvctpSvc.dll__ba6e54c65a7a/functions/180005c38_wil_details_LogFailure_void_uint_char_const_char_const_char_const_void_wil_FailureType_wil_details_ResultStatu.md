# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005c38`
- end: `0x180005f31`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180003468`
- `0x1800037d4`
- `0x18000a7b0`

## callees

- `0x18000339c`
- `0x180004fe4`
- `0x180005850`
- `0x180005c38`
- `0x180006b10`
- `0x180006b30`
- `0x180006c80`
- `0x180006c9c`
- `0x180008984`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d5b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d5b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005e7a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005e7a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005eec`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005eec`

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
0x180005c38  mov     [rsp+arg_10], rbx
0x180005c3d  mov     [rsp+arg_8], edx
0x180005c41  mov     [rsp+arg_0], rcx
0x180005c46  push    rbp
0x180005c47  push    rsi
0x180005c48  push    rdi
0x180005c49  push    r12
0x180005c4b  push    r13
0x180005c4d  push    r14
0x180005c4f  push    r15
0x180005c51  sub     rsp, 40h
0x180005c55  mov     r12, r9
0x180005c58  mov     r13, r8
0x180005c5b  mov     r10, rcx
0x180005c5e  xor     eax, eax
0x180005c60  mov     rsi, [rsp+78h+lpOutputString]
0x180005c68  mov     [rsi], ax
0x180005c6b  mov     rax, [rsp+78h+arg_60]
0x180005c73  mov     byte ptr [rax], 0
0x180005c76  mov     r14, [rsp+78h+arg_38]
0x180005c7e  mov     edi, [r14]
0x180005c81  mov     rbx, [rsp+78h+arg_78]
0x180005c89  mov     [rbx+8], edi
0x180005c8c  mov     eax, [r14+4]
0x180005c90  mov     [rbx+0Ch], eax
0x180005c93  xor     ebp, ebp
0x180005c95  mov     r15d, [rsp+78h+arg_30]
0x180005c9d  mov     ecx, r15d
0x180005ca0  test    r15d, r15d
0x180005ca3  jz      short loc_180005D0B
0x180005ca5  sub     ecx, 1
0x180005ca8  jz      short loc_180005D02
0x180005caa  sub     ecx, 1
0x180005cad  jz      short loc_180005CBD
0x180005caf  cmp     ecx, 1
0x180005cb2  jnz     short loc_180005D14
0x180005cb4  mov     ecx, edi; this
0x180005cb6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005cbb  jmp     short loc_180005D12
0x180005cbd  test    edi, edi
0x180005cbf  js      short loc_180005CF9
0x180005cc1  mov     edi, 8007029Ch
0x180005cc6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005cca  mov     rax, [rsp+78h+arg_28]
0x180005cd2  mov     [rsp+78h+var_50], rax; __int64
0x180005cd7  mov     rax, [rsp+78h+arg_20]
0x180005cdf  mov     [rsp+78h+var_58], rax; __int64
0x180005ce4  mov     rcx, r10; int
0x180005ce7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005cec  mov     [rbx+8], edi
0x180005cef  mov     ecx, edi; this
0x180005cf1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005cf6  mov     [rbx+0Ch], eax
0x180005cf9  mov     ecx, edi; this
0x180005cfb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005d00  jmp     short loc_180005D12
0x180005d02  mov     ecx, edi; this
0x180005d04  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005d09  jmp     short loc_180005D12
0x180005d0b  mov     ecx, edi; this
0x180005d0d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005d12  mov     ebp, eax
0x180005d14  mov     [rbx], r15d
0x180005d17  mov     eax, [rsp+78h+arg_70]
0x180005d1e  mov     [rbx+4], eax
0x180005d21  cmp     dword ptr [r14+8], 1
0x180005d26  jnz     short loc_180005D2E
0x180005d28  or      eax, 8
0x180005d2b  mov     [rbx+4], eax
0x180005d2e  mov     eax, 1
0x180005d33  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005d3b  inc     eax
0x180005d3d  mov     [rbx+10h], eax
0x180005d40  mov     rax, [rsp+78h+arg_40]
0x180005d48  xor     edi, edi
0x180005d4a  test    rax, rax
0x180005d4d  jz      short loc_180005D54
0x180005d4f  cmp     [rax], di
0x180005d52  jnz     short loc_180005D57
0x180005d54  mov     rax, rdi
0x180005d57  mov     [rbx+18h], rax
0x180005d5b  call    cs:__imp_GetCurrentThreadId
0x180005d61  mov     [rbx+20h], eax
0x180005d64  mov     [rbx+38h], r13
0x180005d68  mov     eax, [rsp+78h+arg_8]
0x180005d6f  mov     [rbx+40h], eax
0x180005d72  mov     [rbx+44h], ebp
0x180005d75  mov     rax, [rsp+78h+arg_20]
0x180005d7d  mov     [rbx+28h], rax
0x180005d81  mov     [rbx+30h], r12
0x180005d85  mov     rax, [rsp+78h+arg_28]
0x180005d8d  mov     [rbx+88h], rax
0x180005d94  mov     rax, [rsp+78h+arg_0]
0x180005d9c  mov     [rbx+90h], rax
0x180005da3  mov     [rbx+48h], rdi
0x180005da7  xorps   xmm0, xmm0
0x180005daa  xor     eax, eax
0x180005dac  movups  xmmword ptr [rbx+68h], xmm0
0x180005db0  mov     [rbx+78h], rax
0x180005db4  movups  xmmword ptr [rbx+50h], xmm0
0x180005db8  mov     [rbx+60h], rax
0x180005dbc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005dc3  test    rax, rax
0x180005dc6  jz      short loc_180005DCF
0x180005dc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dcd  jmp     short loc_180005DD2
0x180005dcf  mov     rax, rdi
0x180005dd2  mov     [rbx+80h], rax
0x180005dd9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005de0  test    rax, rax
0x180005de3  jz      short loc_180005DED
0x180005de5  mov     rcx, rbx
0x180005de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ded  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005df4  test    rax, rax
0x180005df7  jz      short loc_180005E0F
0x180005df9  mov     r8d, 400h
0x180005dff  mov     rdx, [rsp+78h+arg_60]
0x180005e07  mov     rcx, rbx
0x180005e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e0f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005e16  test    rax, rax
0x180005e19  jz      short loc_180005E23
0x180005e1b  mov     rcx, rbx
0x180005e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e23  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005e2a  test    rax, rax
0x180005e2d  jz      short loc_180005E3D
0x180005e2f  test    byte ptr [rbx+4], 2
0x180005e33  jnz     short loc_180005E3D
0x180005e35  mov     rcx, rbx
0x180005e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e3d  cmp     [rbx+8], edi
0x180005e40  jl      short loc_180005E5C
0x180005e42  cmp     r15d, 3
0x180005e46  jnz     loc_180005F2B
0x180005e4c  mov     ecx, 8000FFFFh; this
0x180005e51  mov     [rbx+8], ecx
0x180005e54  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005e59  mov     [rbx+0Ch], eax
0x180005e5c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005e63  jnz     short loc_180005E84
0x180005e65  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005e6c  test    rax, rax
0x180005e6f  jz      short loc_180005E7A
0x180005e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e76  test    al, al
0x180005e78  jmp     short loc_180005E82
0x180005e7a  call    cs:__imp_IsDebuggerPresent
0x180005e80  test    eax, eax
0x180005e82  jz      short loc_180005E8A
0x180005e84  test    byte ptr [rbx+4], 2
0x180005e88  jz      short loc_180005EAE
0x180005e8a  mov     rax, cs:g_pfnResultLoggingCallback
0x180005e91  test    rax, rax
0x180005e94  jz      short loc_180005EF2
0x180005e96  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005e9d  jnz     short loc_180005EF2
0x180005e9f  xor     r8d, r8d
0x180005ea2  xor     edx, edx
0x180005ea4  mov     rcx, rbx
0x180005ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eac  jmp     short loc_180005EF2
0x180005eae  mov     ebp, 800h
0x180005eb3  mov     rax, cs:g_pfnResultLoggingCallback
0x180005eba  test    rax, rax
0x180005ebd  jz      short loc_180005ED6
0x180005ebf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005ec6  jnz     short loc_180005ED6
0x180005ec8  mov     r8d, ebp
0x180005ecb  mov     rdx, rsi
0x180005ece  mov     rcx, rbx
0x180005ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ed6  cmp     [rsi], di
0x180005ed9  jnz     short loc_180005EE9
0x180005edb  mov     r8, rbx; unsigned __int64
0x180005ede  mov     rdx, rbp; unsigned __int16 *
0x180005ee1  mov     rcx, rsi; this
0x180005ee4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005ee9  mov     rcx, rsi; lpOutputString
0x180005eec  call    cs:__imp_OutputDebugStringW
0x180005ef2  test    byte ptr [rbx+4], 4
0x180005ef6  jnz     short loc_180005F01
0x180005ef8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005eff  jz      short loc_180005F13
0x180005f01  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005f08  test    rax, rax
0x180005f0b  jz      short loc_180005F13
0x180005f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f12  nop
0x180005f13  mov     rbx, [rsp+78h+arg_10]
0x180005f1b  add     rsp, 40h
0x180005f1f  pop     r15
0x180005f21  pop     r14
0x180005f23  pop     r13
0x180005f25  pop     r12
0x180005f27  pop     rdi
0x180005f28  pop     rsi
0x180005f29  pop     rbp
0x180005f2a  retn
0x180005f2b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
