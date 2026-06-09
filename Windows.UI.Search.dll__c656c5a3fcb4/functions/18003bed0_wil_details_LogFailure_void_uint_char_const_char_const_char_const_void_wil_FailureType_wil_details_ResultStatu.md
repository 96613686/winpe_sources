# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18003bed0`
- end: `0x18003c0c6`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `502`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18003a83c`

## callees

- `0x180007b94`
- `0x180009078`
- `0x18000b444`
- `0x18003b6ec`
- `0x18003bed0`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bf43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003bf43`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003c068`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003c068`

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
  wil::details::in1diag3 *v20; // rcx
  __int64 ModuleName; // rax
  unsigned __int16 *v22; // rdx
  __int64 v23; // rcx
  const struct wil::FailureInfo *v24; // r9

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v17 = (wil::details *)*a8;
  *(_DWORD *)(a16 + 8) = (_DWORD)v17;
  *(_DWORD *)(a16 + 12) = a8[1];
  v18 = wil::details::RecordReturn(v17, (int)a8);
  *(_QWORD *)a16 = 1;
  if ( *(_DWORD *)(v19 + 8) == 1 )
    *(_DWORD *)(a16 + 4) = 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  *(_QWORD *)(a16 + 24) = 0;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = "onecore\\shell\\lib\\calleridentity\\calleridentity.cpp";
  *(_DWORD *)(a16 + 64) = 172;
  *(_DWORD *)(a16 + 68) = v18;
  *(_QWORD *)(a16 + 40) = 0;
  *(_QWORD *)(a16 + 48) = 0;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v20);
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v20);
  if ( !wil::details::IsDebuggerPresent(v20) || (*(_BYTE *)(a16 + 4) & 2) != 0 )
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
0x18003bed0  push    rbx
0x18003bed2  push    rbp
0x18003bed3  push    rsi
0x18003bed4  push    rdi
0x18003bed5  push    r14
0x18003bed7  push    r15
0x18003bed9  sub     rsp, 28h
0x18003bedd  mov     rbp, rcx
0x18003bee0  xor     r15d, r15d
0x18003bee3  mov     rdi, [rsp+58h+lpOutputString]
0x18003beeb  mov     [rdi], r15w
0x18003beef  mov     rsi, [rsp+58h+arg_60]
0x18003bef7  mov     [rsi], r15b
0x18003befa  mov     rdx, [rsp+58h+arg_38]; int
0x18003bf02  mov     ecx, [rdx]; this
0x18003bf04  mov     rbx, [rsp+58h+arg_78]
0x18003bf0c  mov     [rbx+8], ecx
0x18003bf0f  mov     eax, [rdx+4]
0x18003bf12  mov     [rbx+0Ch], eax
0x18003bf15  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003bf1a  mov     r14d, eax
0x18003bf1d  lea     eax, [r15+1]
0x18003bf21  mov     [rbx], rax
0x18003bf24  cmp     [rdx+8], eax
0x18003bf27  jnz     short loc_18003BF30
0x18003bf29  mov     dword ptr [rbx+4], 8
0x18003bf30  mov     ecx, eax
0x18003bf32  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003bf3a  add     ecx, eax
0x18003bf3c  mov     [rbx+10h], ecx
0x18003bf3f  mov     [rbx+18h], r15
0x18003bf43  call    cs:__imp_GetCurrentThreadId
0x18003bf49  mov     [rbx+20h], eax
0x18003bf4c  lea     rax, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x18003bf53  mov     [rbx+38h], rax
0x18003bf57  mov     dword ptr [rbx+40h], 0ACh
0x18003bf5e  mov     [rbx+44h], r14d
0x18003bf62  mov     [rbx+28h], r15
0x18003bf66  mov     [rbx+30h], r15
0x18003bf6a  mov     rax, [rsp+58h+arg_28]
0x18003bf72  mov     [rbx+88h], rax
0x18003bf79  mov     [rbx+90h], rbp
0x18003bf80  mov     [rbx+48h], r15
0x18003bf84  xorps   xmm0, xmm0
0x18003bf87  xor     eax, eax
0x18003bf89  movups  xmmword ptr [rbx+68h], xmm0
0x18003bf8d  mov     [rbx+78h], rax
0x18003bf91  movups  xmmword ptr [rbx+50h], xmm0
0x18003bf95  mov     [rbx+60h], rax
0x18003bf99  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003bfa0  test    rax, rax
0x18003bfa3  jz      short loc_18003BFAC
0x18003bfa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfaa  jmp     short loc_18003BFAF
0x18003bfac  mov     rax, r15
0x18003bfaf  mov     [rbx+80h], rax
0x18003bfb6  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003bfbd  test    rax, rax
0x18003bfc0  jz      short loc_18003BFCA
0x18003bfc2  mov     rcx, rbx
0x18003bfc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfca  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003bfd1  test    rax, rax
0x18003bfd4  jz      short loc_18003BFE7
0x18003bfd6  mov     r8d, 400h
0x18003bfdc  mov     rdx, rsi
0x18003bfdf  mov     rcx, rbx
0x18003bfe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bfe7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003bfee  test    rax, rax
0x18003bff1  jz      short loc_18003BFFB
0x18003bff3  mov     rcx, rbx
0x18003bff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bffb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003c002  test    rax, rax
0x18003c005  jz      short loc_18003C015
0x18003c007  test    byte ptr [rbx+4], 2
0x18003c00b  jnz     short loc_18003C015
0x18003c00d  mov     rcx, rbx
0x18003c010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c015  cmp     [rbx+8], r15d
0x18003c019  jge     loc_18003C0C0
0x18003c01f  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x18003c024  test    al, al
0x18003c026  jz      short loc_18003C070
0x18003c028  test    byte ptr [rbx+4], 2
0x18003c02c  jnz     short loc_18003C070
0x18003c02e  mov     rax, cs:g_pfnResultLoggingCallback
0x18003c035  test    rax, rax
0x18003c038  jz      short loc_18003C054
0x18003c03a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003c041  jnz     short loc_18003C054
0x18003c043  mov     r8d, 800h
0x18003c049  mov     rdx, rdi
0x18003c04c  mov     rcx, rbx
0x18003c04f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c054  cmp     [rdi], r15w
0x18003c058  jnz     short loc_18003C065
0x18003c05a  mov     r8, rbx; unsigned __int64
0x18003c05d  mov     rcx, rdi; this
0x18003c060  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003c065  mov     rcx, rdi; lpOutputString
0x18003c068  call    cs:__imp_OutputDebugStringW
0x18003c06e  jmp     short loc_18003C092
0x18003c070  mov     rax, cs:g_pfnResultLoggingCallback
0x18003c077  test    rax, rax
0x18003c07a  jz      short loc_18003C092
0x18003c07c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003c083  jnz     short loc_18003C092
0x18003c085  xor     r8d, r8d
0x18003c088  xor     edx, edx
0x18003c08a  mov     rcx, rbx
0x18003c08d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c092  test    byte ptr [rbx+4], 4
0x18003c096  jnz     short loc_18003C0A1
0x18003c098  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18003c09f  jz      short loc_18003C0B3
0x18003c0a1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003c0a8  test    rax, rax
0x18003c0ab  jz      short loc_18003C0B3
0x18003c0ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c0b2  nop
0x18003c0b3  add     rsp, 28h
0x18003c0b7  pop     r15
0x18003c0b9  pop     r14
0x18003c0bb  pop     rdi
0x18003c0bc  pop     rsi
0x18003c0bd  pop     rbp
0x18003c0be  pop     rbx
0x18003c0bf  retn
0x18003c0c0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
