# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140059f00`
- end: `0x14005a127`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `551`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400596a8`

## callees

- `0x140009698`
- `0x14000c710`
- `0x140059a10`
- `0x140059f00`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140059f73`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140059f73`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14005a073`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14005a073`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14005a0e7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14005a0e7`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        unsigned int *a8,
        __int64 a9,
        __int64 a10,
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        __int64 a15,
        unsigned __int64 a16)
{
  wil::details *v17; // rcx
  int v18; // r14d
  __int64 v19; // rdx
  signed __int32 v20; // ecx
  DWORD CurrentThreadId; // eax
  unsigned __int16 *v22; // rdx
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v17 = (wil::details *)*a8;
  *(_DWORD *)(a16 + 8) = (_DWORD)v17;
  *(_DWORD *)(a16 + 12) = a8[1];
  v18 = wil::details::RecordReturn(v17, (int)a8);
  *(_QWORD *)a16 = 1;
  if ( *(_DWORD *)(v19 + 8) == 1 )
    *(_DWORD *)(a16 + 4) = 8;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  *(_QWORD *)(a16 + 24) = 0;
  *(_DWORD *)(a16 + 16) = v20;
  CurrentThreadId = GetCurrentThreadId();
  *(_DWORD *)(a16 + 64) = 172;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_QWORD *)(a16 + 56) = "onecore\\shell\\lib\\calleridentity\\calleridentity.cpp";
  *(_QWORD *)(a16 + 136) = a6;
  *(_DWORD *)(a16 + 68) = v18;
  *(_QWORD *)(a16 + 40) = 0;
  *(_QWORD *)(a16 + 48) = 0;
  *(_QWORD *)(a16 + 144) = a1;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
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
      wil::GetFailureLogString(lpOutputString, v22, a16, v24);
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
0x140059f00  push    rbx
0x140059f02  push    rbp
0x140059f03  push    rsi
0x140059f04  push    rdi
0x140059f05  push    r14
0x140059f07  push    r15
0x140059f09  sub     rsp, 28h
0x140059f0d  mov     rdx, [rsp+58h+arg_38]; int
0x140059f15  xor     r15d, r15d
0x140059f18  mov     rbx, [rsp+58h+arg_78]
0x140059f20  mov     rbp, rcx
0x140059f23  mov     rdi, [rsp+58h+lpOutputString]
0x140059f2b  mov     rsi, [rsp+58h+arg_60]
0x140059f33  mov     [rdi], r15w
0x140059f37  mov     [rsi], r15b
0x140059f3a  mov     ecx, [rdx]; this
0x140059f3c  mov     [rbx+8], ecx
0x140059f3f  mov     eax, [rdx+4]
0x140059f42  mov     [rbx+0Ch], eax
0x140059f45  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140059f4a  mov     r14d, eax
0x140059f4d  lea     eax, [r15+1]
0x140059f51  mov     [rbx], rax
0x140059f54  cmp     [rdx+8], eax
0x140059f57  jnz     short loc_140059F60
0x140059f59  mov     dword ptr [rbx+4], 8
0x140059f60  mov     ecx, eax
0x140059f62  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140059f6a  add     ecx, eax
0x140059f6c  mov     [rbx+18h], r15
0x140059f70  mov     [rbx+10h], ecx
0x140059f73  call    cs:__imp_GetCurrentThreadId
0x140059f7a  nop     dword ptr [rax+rax+00h]
0x140059f7f  mov     dword ptr [rbx+40h], 0ACh
0x140059f86  xorps   xmm0, xmm0
0x140059f89  mov     [rbx+20h], eax
0x140059f8c  lea     rax, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x140059f93  mov     [rbx+38h], rax
0x140059f97  mov     rax, [rsp+58h+arg_28]
0x140059f9f  mov     [rbx+88h], rax
0x140059fa6  xor     eax, eax
0x140059fa8  mov     [rbx+44h], r14d
0x140059fac  mov     [rbx+28h], r15
0x140059fb0  mov     [rbx+30h], r15
0x140059fb4  mov     [rbx+90h], rbp
0x140059fbb  mov     [rbx+48h], r15
0x140059fbf  movups  xmmword ptr [rbx+68h], xmm0
0x140059fc3  mov     [rbx+78h], rax
0x140059fc7  movups  xmmword ptr [rbx+50h], xmm0
0x140059fcb  mov     [rbx+60h], rax
0x140059fcf  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140059fd6  test    rax, rax
0x140059fd9  jz      short loc_140059FE2
0x140059fdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140059fe0  jmp     short loc_140059FE5
0x140059fe2  mov     rax, r15
0x140059fe5  mov     [rbx+80h], rax
0x140059fec  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140059ff3  test    rax, rax
0x140059ff6  jz      short loc_14005A000
0x140059ff8  mov     rcx, rbx
0x140059ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a000  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14005a007  test    rax, rax
0x14005a00a  jz      short loc_14005A01D
0x14005a00c  mov     r8d, 400h
0x14005a012  mov     rdx, rsi
0x14005a015  mov     rcx, rbx
0x14005a018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a01d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14005a024  test    rax, rax
0x14005a027  jz      short loc_14005A031
0x14005a029  mov     rcx, rbx
0x14005a02c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a031  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14005a038  test    rax, rax
0x14005a03b  jz      short loc_14005A04B
0x14005a03d  test    byte ptr [rbx+4], 2
0x14005a041  jnz     short loc_14005A04B
0x14005a043  mov     rcx, rbx
0x14005a046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a04b  cmp     [rbx+8], r15d
0x14005a04f  jge     loc_14005A121
0x14005a055  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x14005a05c  jnz     short loc_14005A083
0x14005a05e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14005a065  test    rax, rax
0x14005a068  jz      short loc_14005A073
0x14005a06a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a06f  test    al, al
0x14005a071  jmp     short loc_14005A081
0x14005a073  call    cs:__imp_IsDebuggerPresent
0x14005a07a  nop     dword ptr [rax+rax+00h]
0x14005a07f  test    eax, eax
0x14005a081  jz      short loc_14005A089
0x14005a083  test    byte ptr [rbx+4], 2
0x14005a087  jz      short loc_14005A0AD
0x14005a089  mov     rax, cs:g_pfnResultLoggingCallback
0x14005a090  test    rax, rax
0x14005a093  jz      short loc_14005A0F3
0x14005a095  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14005a09c  jnz     short loc_14005A0F3
0x14005a09e  xor     r8d, r8d
0x14005a0a1  xor     edx, edx
0x14005a0a3  mov     rcx, rbx
0x14005a0a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a0ab  jmp     short loc_14005A0F3
0x14005a0ad  mov     rax, cs:g_pfnResultLoggingCallback
0x14005a0b4  test    rax, rax
0x14005a0b7  jz      short loc_14005A0D3
0x14005a0b9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14005a0c0  jnz     short loc_14005A0D3
0x14005a0c2  mov     r8d, 800h
0x14005a0c8  mov     rdx, rdi
0x14005a0cb  mov     rcx, rbx
0x14005a0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a0d3  cmp     [rdi], r15w
0x14005a0d7  jnz     short loc_14005A0E4
0x14005a0d9  mov     r8, rbx; unsigned __int64
0x14005a0dc  mov     rcx, rdi; this
0x14005a0df  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14005a0e4  mov     rcx, rdi; lpOutputString
0x14005a0e7  call    cs:__imp_OutputDebugStringW
0x14005a0ee  nop     dword ptr [rax+rax+00h]
0x14005a0f3  test    byte ptr [rbx+4], 4
0x14005a0f7  jnz     short loc_14005A102
0x14005a0f9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x14005a100  jz      short loc_14005A113
0x14005a102  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14005a109  test    rax, rax
0x14005a10c  jz      short loc_14005A113
0x14005a10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005a113  add     rsp, 28h
0x14005a117  pop     r15
0x14005a119  pop     r14
0x14005a11b  pop     rdi
0x14005a11c  pop     rsi
0x14005a11d  pop     rbp
0x14005a11e  pop     rbx
0x14005a11f  retn
0x14005a121  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
