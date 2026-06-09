# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140005cd4`
- end: `0x140005fcc`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140004758`

## callees

- `0x14000419c`
- `0x140005374`
- `0x140005b10`
- `0x140005cd4`
- `0x1400060f8`
- `0x140006120`
- `0x140006134`
- `0x140006150`
- `0x140006abc`
- `0x140007010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005df7`
- `KERNEL32!GetCurrentThreadId` at `0x140005df7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005f88`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005f88`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005f16`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005f16`

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
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
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
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x140005cd4  mov     [rsp+arg_10], rbx
0x140005cd9  mov     [rsp+arg_8], edx
0x140005cdd  mov     [rsp+arg_0], rcx
0x140005ce2  push    rbp
0x140005ce3  push    rsi
0x140005ce4  push    rdi
0x140005ce5  push    r12
0x140005ce7  push    r13
0x140005ce9  push    r14
0x140005ceb  push    r15
0x140005ced  sub     rsp, 40h
0x140005cf1  mov     r14, [rsp+78h+arg_38]
0x140005cf9  xor     eax, eax
0x140005cfb  mov     rbx, [rsp+78h+arg_78]
0x140005d03  xor     ebp, ebp
0x140005d05  mov     r15d, [rsp+78h+arg_30]
0x140005d0d  mov     r10, rcx
0x140005d10  mov     rsi, [rsp+78h+lpOutputString]
0x140005d18  mov     r12, r9
0x140005d1b  mov     r13, r8
0x140005d1e  mov     ecx, r15d
0x140005d21  mov     [rsi], ax
0x140005d24  mov     rax, [rsp+78h+arg_60]
0x140005d2c  mov     byte ptr [rax], 0
0x140005d2f  mov     edi, [r14]
0x140005d32  mov     [rbx+8], edi
0x140005d35  mov     eax, [r14+4]
0x140005d39  mov     [rbx+0Ch], eax
0x140005d3c  test    r15d, r15d
0x140005d3f  jz      short loc_140005DA7
0x140005d41  sub     ecx, 1
0x140005d44  jz      short loc_140005D9E
0x140005d46  sub     ecx, 1
0x140005d49  jz      short loc_140005D59
0x140005d4b  cmp     ecx, 1
0x140005d4e  jnz     short loc_140005DB0
0x140005d50  mov     ecx, edi; this
0x140005d52  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140005d57  jmp     short loc_140005DAE
0x140005d59  test    edi, edi
0x140005d5b  js      short loc_140005D95
0x140005d5d  mov     rax, [rsp+78h+arg_28]
0x140005d65  mov     edi, 8007029Ch
0x140005d6a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140005d6e  mov     rcx, r10; int
0x140005d71  mov     [rsp+78h+var_50], rax; __int64
0x140005d76  mov     rax, [rsp+78h+arg_20]
0x140005d7e  mov     [rsp+78h+var_58], rax; __int64
0x140005d83  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140005d88  mov     ecx, edi; this
0x140005d8a  mov     [rbx+8], edi
0x140005d8d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005d92  mov     [rbx+0Ch], eax
0x140005d95  mov     ecx, edi; this
0x140005d97  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140005d9c  jmp     short loc_140005DAE
0x140005d9e  mov     ecx, edi; this
0x140005da0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140005da5  jmp     short loc_140005DAE
0x140005da7  mov     ecx, edi; this
0x140005da9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140005dae  mov     ebp, eax
0x140005db0  mov     eax, [rsp+78h+arg_70]
0x140005db7  mov     [rbx+4], eax
0x140005dba  mov     [rbx], r15d
0x140005dbd  cmp     dword ptr [r14+8], 1
0x140005dc2  jnz     short loc_140005DCA
0x140005dc4  or      eax, 8
0x140005dc7  mov     [rbx+4], eax
0x140005dca  mov     eax, 1
0x140005dcf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140005dd7  inc     eax
0x140005dd9  xor     edi, edi
0x140005ddb  mov     [rbx+10h], eax
0x140005dde  mov     rax, [rsp+78h+arg_40]
0x140005de6  test    rax, rax
0x140005de9  jz      short loc_140005DF0
0x140005deb  cmp     [rax], di
0x140005dee  jnz     short loc_140005DF3
0x140005df0  mov     rax, rdi
0x140005df3  mov     [rbx+18h], rax
0x140005df7  call    cs:__imp_GetCurrentThreadId
0x140005dfd  mov     [rbx+38h], r13
0x140005e01  xorps   xmm0, xmm0
0x140005e04  mov     [rbx+20h], eax
0x140005e07  mov     eax, [rsp+78h+arg_8]
0x140005e0e  mov     [rbx+40h], eax
0x140005e11  mov     rax, [rsp+78h+arg_20]
0x140005e19  mov     [rbx+28h], rax
0x140005e1d  mov     rax, [rsp+78h+arg_28]
0x140005e25  mov     [rbx+88h], rax
0x140005e2c  mov     rax, [rsp+78h+arg_0]
0x140005e34  mov     [rbx+90h], rax
0x140005e3b  xor     eax, eax
0x140005e3d  mov     [rbx+44h], ebp
0x140005e40  mov     [rbx+30h], r12
0x140005e44  mov     [rbx+48h], rdi
0x140005e48  movups  xmmword ptr [rbx+68h], xmm0
0x140005e4c  mov     [rbx+78h], rax
0x140005e50  movups  xmmword ptr [rbx+50h], xmm0
0x140005e54  mov     [rbx+60h], rax
0x140005e58  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005e5f  test    rax, rax
0x140005e62  jz      short loc_140005E6B
0x140005e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e69  jmp     short loc_140005E6E
0x140005e6b  mov     rax, rdi
0x140005e6e  mov     [rbx+80h], rax
0x140005e75  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140005e7c  test    rax, rax
0x140005e7f  jz      short loc_140005E89
0x140005e81  mov     rcx, rbx
0x140005e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e89  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140005e90  test    rax, rax
0x140005e93  jz      short loc_140005EAB
0x140005e95  mov     rdx, [rsp+78h+arg_60]
0x140005e9d  mov     r8d, 400h
0x140005ea3  mov     rcx, rbx
0x140005ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005eab  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005eb2  test    rax, rax
0x140005eb5  jz      short loc_140005EBF
0x140005eb7  mov     rcx, rbx
0x140005eba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ebf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005ec6  test    rax, rax
0x140005ec9  jz      short loc_140005ED9
0x140005ecb  test    byte ptr [rbx+4], 2
0x140005ecf  jnz     short loc_140005ED9
0x140005ed1  mov     rcx, rbx
0x140005ed4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ed9  cmp     [rbx+8], edi
0x140005edc  jl      short loc_140005EF8
0x140005ede  cmp     r15d, 3
0x140005ee2  jnz     loc_140005FC6
0x140005ee8  mov     ecx, 8000FFFFh; this
0x140005eed  mov     [rbx+8], ecx
0x140005ef0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005ef5  mov     [rbx+0Ch], eax
0x140005ef8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140005eff  jnz     short loc_140005F20
0x140005f01  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005f08  test    rax, rax
0x140005f0b  jz      short loc_140005F16
0x140005f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f12  test    al, al
0x140005f14  jmp     short loc_140005F1E
0x140005f16  call    cs:__imp_IsDebuggerPresent
0x140005f1c  test    eax, eax
0x140005f1e  jz      short loc_140005F26
0x140005f20  test    byte ptr [rbx+4], 2
0x140005f24  jz      short loc_140005F4A
0x140005f26  mov     rax, cs:g_pfnResultLoggingCallback
0x140005f2d  test    rax, rax
0x140005f30  jz      short loc_140005F8E
0x140005f32  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005f39  jnz     short loc_140005F8E
0x140005f3b  xor     r8d, r8d
0x140005f3e  xor     edx, edx
0x140005f40  mov     rcx, rbx
0x140005f43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f48  jmp     short loc_140005F8E
0x140005f4a  mov     rax, cs:g_pfnResultLoggingCallback
0x140005f51  mov     ebp, 800h
0x140005f56  test    rax, rax
0x140005f59  jz      short loc_140005F72
0x140005f5b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005f62  jnz     short loc_140005F72
0x140005f64  mov     r8d, ebp
0x140005f67  mov     rdx, rsi
0x140005f6a  mov     rcx, rbx
0x140005f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f72  cmp     [rsi], di
0x140005f75  jnz     short loc_140005F85
0x140005f77  mov     r8, rbx; unsigned __int64
0x140005f7a  mov     rdx, rbp; unsigned __int16 *
0x140005f7d  mov     rcx, rsi; this
0x140005f80  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140005f85  mov     rcx, rsi; lpOutputString
0x140005f88  call    cs:__imp_OutputDebugStringW
0x140005f8e  test    byte ptr [rbx+4], 4
0x140005f92  jnz     short loc_140005F9D
0x140005f94  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140005f9b  jz      short loc_140005FAE
0x140005f9d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140005fa4  test    rax, rax
0x140005fa7  jz      short loc_140005FAE
0x140005fa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fae  mov     rbx, [rsp+78h+arg_10]
0x140005fb6  add     rsp, 40h
0x140005fba  pop     r15
0x140005fbc  pop     r14
0x140005fbe  pop     r13
0x140005fc0  pop     r12
0x140005fc2  pop     rdi
0x140005fc3  pop     rsi
0x140005fc4  pop     rbp
0x140005fc5  retn
0x140005fc6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
