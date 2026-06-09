# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400563c4`
- end: `0x1400565d8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140055bb4`

## callees

- `0x140009668`
- `0x14000c59c`
- `0x140055f0c`
- `0x1400563c4`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140056437`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140056437`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140056531`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140056531`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14005659f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14005659f`

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
0x1400563c4  push    rbx
0x1400563c6  push    rbp
0x1400563c7  push    rsi
0x1400563c8  push    rdi
0x1400563c9  push    r14
0x1400563cb  push    r15
0x1400563cd  sub     rsp, 28h
0x1400563d1  mov     rdx, [rsp+58h+arg_38]; int
0x1400563d9  xor     r15d, r15d
0x1400563dc  mov     rbx, [rsp+58h+arg_78]
0x1400563e4  mov     rbp, rcx
0x1400563e7  mov     rdi, [rsp+58h+lpOutputString]
0x1400563ef  mov     rsi, [rsp+58h+arg_60]
0x1400563f7  mov     [rdi], r15w
0x1400563fb  mov     [rsi], r15b
0x1400563fe  mov     ecx, [rdx]; this
0x140056400  mov     [rbx+8], ecx
0x140056403  mov     eax, [rdx+4]
0x140056406  mov     [rbx+0Ch], eax
0x140056409  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14005640e  mov     r14d, eax
0x140056411  lea     eax, [r15+1]
0x140056415  mov     [rbx], rax
0x140056418  cmp     [rdx+8], eax
0x14005641b  jnz     short loc_140056424
0x14005641d  mov     dword ptr [rbx+4], 8
0x140056424  mov     ecx, eax
0x140056426  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14005642e  add     ecx, eax
0x140056430  mov     [rbx+18h], r15
0x140056434  mov     [rbx+10h], ecx
0x140056437  call    cs:__imp_GetCurrentThreadId
0x14005643d  mov     dword ptr [rbx+40h], 0ACh
0x140056444  xorps   xmm0, xmm0
0x140056447  mov     [rbx+20h], eax
0x14005644a  lea     rax, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x140056451  mov     [rbx+38h], rax
0x140056455  mov     rax, [rsp+58h+arg_28]
0x14005645d  mov     [rbx+88h], rax
0x140056464  xor     eax, eax
0x140056466  mov     [rbx+44h], r14d
0x14005646a  mov     [rbx+28h], r15
0x14005646e  mov     [rbx+30h], r15
0x140056472  mov     [rbx+90h], rbp
0x140056479  mov     [rbx+48h], r15
0x14005647d  movups  xmmword ptr [rbx+68h], xmm0
0x140056481  mov     [rbx+78h], rax
0x140056485  movups  xmmword ptr [rbx+50h], xmm0
0x140056489  mov     [rbx+60h], rax
0x14005648d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140056494  test    rax, rax
0x140056497  jz      short loc_1400564A0
0x140056499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005649e  jmp     short loc_1400564A3
0x1400564a0  mov     rax, r15
0x1400564a3  mov     [rbx+80h], rax
0x1400564aa  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400564b1  test    rax, rax
0x1400564b4  jz      short loc_1400564BE
0x1400564b6  mov     rcx, rbx
0x1400564b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400564be  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400564c5  test    rax, rax
0x1400564c8  jz      short loc_1400564DB
0x1400564ca  mov     r8d, 400h
0x1400564d0  mov     rdx, rsi
0x1400564d3  mov     rcx, rbx
0x1400564d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400564db  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400564e2  test    rax, rax
0x1400564e5  jz      short loc_1400564EF
0x1400564e7  mov     rcx, rbx
0x1400564ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400564ef  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400564f6  test    rax, rax
0x1400564f9  jz      short loc_140056509
0x1400564fb  test    byte ptr [rbx+4], 2
0x1400564ff  jnz     short loc_140056509
0x140056501  mov     rcx, rbx
0x140056504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056509  cmp     [rbx+8], r15d
0x14005650d  jge     loc_1400565D2
0x140056513  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x14005651a  jnz     short loc_14005653B
0x14005651c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140056523  test    rax, rax
0x140056526  jz      short loc_140056531
0x140056528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005652d  test    al, al
0x14005652f  jmp     short loc_140056539
0x140056531  call    cs:__imp_IsDebuggerPresent
0x140056537  test    eax, eax
0x140056539  jz      short loc_140056541
0x14005653b  test    byte ptr [rbx+4], 2
0x14005653f  jz      short loc_140056565
0x140056541  mov     rax, cs:g_pfnResultLoggingCallback
0x140056548  test    rax, rax
0x14005654b  jz      short loc_1400565A5
0x14005654d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140056554  jnz     short loc_1400565A5
0x140056556  xor     r8d, r8d
0x140056559  xor     edx, edx
0x14005655b  mov     rcx, rbx
0x14005655e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140056563  jmp     short loc_1400565A5
0x140056565  mov     rax, cs:g_pfnResultLoggingCallback
0x14005656c  test    rax, rax
0x14005656f  jz      short loc_14005658B
0x140056571  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140056578  jnz     short loc_14005658B
0x14005657a  mov     r8d, 800h
0x140056580  mov     rdx, rdi
0x140056583  mov     rcx, rbx
0x140056586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005658b  cmp     [rdi], r15w
0x14005658f  jnz     short loc_14005659C
0x140056591  mov     r8, rbx; unsigned __int64
0x140056594  mov     rcx, rdi; this
0x140056597  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14005659c  mov     rcx, rdi; lpOutputString
0x14005659f  call    cs:__imp_OutputDebugStringW
0x1400565a5  test    byte ptr [rbx+4], 4
0x1400565a9  jnz     short loc_1400565B4
0x1400565ab  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1400565b2  jz      short loc_1400565C5
0x1400565b4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400565bb  test    rax, rax
0x1400565be  jz      short loc_1400565C5
0x1400565c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400565c5  add     rsp, 28h
0x1400565c9  pop     r15
0x1400565cb  pop     r14
0x1400565cd  pop     rdi
0x1400565ce  pop     rsi
0x1400565cf  pop     rbp
0x1400565d0  pop     rbx
0x1400565d1  retn
0x1400565d2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
