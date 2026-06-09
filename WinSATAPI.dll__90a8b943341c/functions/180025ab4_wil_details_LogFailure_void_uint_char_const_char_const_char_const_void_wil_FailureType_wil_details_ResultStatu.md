# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)

- ea: `0x180025ab4`
- end: `0x180025dc0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18002255c`
- `0x180022608`
- `0x1800226fc`

## callees

- `0x1800224b0`
- `0x180024c04`
- `0x180025690`
- `0x180025ab4`
- `0x1800267e8`
- `0x180026810`
- `0x180026998`
- `0x1800269b8`
- `0x180028774`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025bdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025bdb`
- `KERNEL32!IsDebuggerPresent` at `0x180025d01`
- `KERNEL32!IsDebuggerPresent` at `0x180025d01`
- `KERNEL32!OutputDebugStringW` at `0x180025d7a`
- `KERNEL32!OutputDebugStringW` at `0x180025d7a`

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
        unsigned __int64 a15)
{
  unsigned int v17; // edi
  int v18; // esi
  int v19; // eax
  int v20; // edx
  _WORD *v21; // rax
  int v22; // edx
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-58h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v17 = *a8;
  *(_DWORD *)(a15 + 8) = *a8;
  *(_DWORD *)(a15 + 12) = a8[1];
  v18 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v19 = wil::details::RecordReturn((wil::details *)v17, a2);
        break;
      case 2:
        if ( (v17 & 0x80000000) == 0 )
        {
          v17 = -2147024228;
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a15 + 8) = -2147024228;
          *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v20);
        }
        v19 = wil::details::RecordLog((wil::details *)v17, a2);
        break;
      case 3:
        v19 = wil::details::RecordFailFast((wil::details *)v17, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v19 = wil::details::RecordException((wil::details *)v17, a2);
  }
  v18 = v19;
LABEL_12:
  *(_DWORD *)a15 = a7;
  *(_DWORD *)(a15 + 4) = 0;
  if ( a8[2] == 1 )
    *(_DWORD *)(a15 + 4) = 8;
  *(_DWORD *)(a15 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a15 + 24) = v21;
  *(_DWORD *)(a15 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a15 + 56) = a3;
  *(_DWORD *)(a15 + 64) = a2;
  *(_DWORD *)(a15 + 68) = v18;
  *(_QWORD *)(a15 + 40) = a5;
  *(_QWORD *)(a15 + 48) = a4;
  *(_QWORD *)(a15 + 136) = a6;
  *(_QWORD *)(a15 + 144) = a1;
  *(_QWORD *)(a15 + 72) = 0;
  *(_OWORD *)(a15 + 104) = 0;
  *(_QWORD *)(a15 + 120) = 0;
  *(_OWORD *)(a15 + 80) = 0;
  *(_QWORD *)(a15 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a15 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a15, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a15);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a15 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a15);
  if ( *(int *)(a15 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a15 + 8) = -2147418113;
    *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v22);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v26)
    || (*(_BYTE *)(a15 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a15, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a15 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180025ab4  mov     rax, rsp
0x180025ab7  mov     [rax+10h], edx
0x180025aba  mov     [rax+8], rcx
0x180025abe  push    rbp
0x180025abf  push    rsi
0x180025ac0  push    rdi
0x180025ac1  push    r12
0x180025ac3  push    r13
0x180025ac5  push    r14
0x180025ac7  push    r15
0x180025ac9  sub     rsp, 50h
0x180025acd  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180025ad5  mov     [rax+18h], rbx
0x180025ad9  mov     r12, r9
0x180025adc  mov     r13, r8
0x180025adf  mov     r10, rcx
0x180025ae2  xor     r8d, r8d
0x180025ae5  mov     r14, [rsp+88h+lpOutputString]
0x180025aed  mov     [r14], r8w
0x180025af1  mov     rax, [rsp+88h+arg_60]
0x180025af9  mov     [rax], r8b
0x180025afc  mov     rbx, [rsp+88h+arg_70]
0x180025b04  mov     r15, [rsp+88h+arg_38]
0x180025b0c  mov     edi, [r15]
0x180025b0f  mov     [rbx+8], edi
0x180025b12  mov     eax, [r15+4]
0x180025b16  mov     [rbx+0Ch], eax
0x180025b19  mov     esi, r8d
0x180025b1c  mov     ebp, [rsp+88h+arg_30]
0x180025b23  mov     ecx, ebp
0x180025b25  test    ebp, ebp
0x180025b27  jz      short loc_180025B92
0x180025b29  sub     ecx, 1
0x180025b2c  jz      short loc_180025B89
0x180025b2e  sub     ecx, 1
0x180025b31  jz      short loc_180025B41
0x180025b33  cmp     ecx, 1
0x180025b36  jnz     short loc_180025B9B
0x180025b38  mov     ecx, edi; this
0x180025b3a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180025b3f  jmp     short loc_180025B99
0x180025b41  test    edi, edi
0x180025b43  js      short loc_180025B80
0x180025b45  mov     edi, 8007029Ch
0x180025b4a  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x180025b4e  mov     rax, [rsp+88h+arg_28]
0x180025b56  mov     [rsp+88h+var_60], rax; __int64
0x180025b5b  mov     rax, [rsp+88h+arg_20]
0x180025b63  mov     [rsp+88h+var_68], rax; __int64
0x180025b68  mov     r8, r13; int
0x180025b6b  mov     rcx, r10; int
0x180025b6e  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x180025b73  mov     [rbx+8], edi
0x180025b76  mov     ecx, edi; this
0x180025b78  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180025b7d  mov     [rbx+0Ch], eax
0x180025b80  mov     ecx, edi; this
0x180025b82  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180025b87  jmp     short loc_180025B99
0x180025b89  mov     ecx, edi; this
0x180025b8b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180025b90  jmp     short loc_180025B99
0x180025b92  mov     ecx, edi; this
0x180025b94  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180025b99  mov     esi, eax
0x180025b9b  mov     [rbx], ebp
0x180025b9d  xor     edi, edi
0x180025b9f  mov     [rbx+4], edi
0x180025ba2  cmp     dword ptr [r15+8], 1
0x180025ba7  jnz     short loc_180025BB0
0x180025ba9  mov     dword ptr [rbx+4], 8
0x180025bb0  mov     eax, 1
0x180025bb5  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180025bbd  inc     eax
0x180025bbf  mov     [rbx+10h], eax
0x180025bc2  mov     rax, [rsp+88h+arg_40]
0x180025bca  test    rax, rax
0x180025bcd  jz      short loc_180025BD4
0x180025bcf  cmp     [rax], di
0x180025bd2  jnz     short loc_180025BD7
0x180025bd4  mov     rax, rdi
0x180025bd7  mov     [rbx+18h], rax
0x180025bdb  call    cs:__imp_GetCurrentThreadId
0x180025be2  nop     dword ptr [rax+rax+00h]
0x180025be7  mov     [rbx+20h], eax
0x180025bea  mov     [rbx+38h], r13
0x180025bee  mov     eax, [rsp+88h+arg_8]
0x180025bf5  mov     [rbx+40h], eax
0x180025bf8  mov     [rbx+44h], esi
0x180025bfb  mov     rax, [rsp+88h+arg_20]
0x180025c03  mov     [rbx+28h], rax
0x180025c07  mov     [rbx+30h], r12
0x180025c0b  mov     rax, [rsp+88h+arg_28]
0x180025c13  mov     [rbx+88h], rax
0x180025c1a  mov     rax, [rsp+88h+arg_0]
0x180025c22  mov     [rbx+90h], rax
0x180025c29  mov     [rbx+48h], rdi
0x180025c2d  xorps   xmm0, xmm0
0x180025c30  xor     eax, eax
0x180025c32  movups  xmmword ptr [rbx+68h], xmm0
0x180025c36  mov     [rbx+78h], rax
0x180025c3a  movups  xmmword ptr [rbx+50h], xmm0
0x180025c3e  mov     [rbx+60h], rax
0x180025c42  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180025c49  test    rax, rax
0x180025c4c  jz      short loc_180025C55
0x180025c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c53  jmp     short loc_180025C58
0x180025c55  mov     rax, rdi
0x180025c58  mov     [rbx+80h], rax
0x180025c5f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180025c66  test    rax, rax
0x180025c69  jz      short loc_180025C73
0x180025c6b  mov     rcx, rbx
0x180025c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c73  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180025c7a  test    rax, rax
0x180025c7d  jz      short loc_180025C95
0x180025c7f  mov     r8d, 400h
0x180025c85  mov     rdx, [rsp+88h+arg_60]
0x180025c8d  mov     rcx, rbx
0x180025c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c95  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025c9c  test    rax, rax
0x180025c9f  jz      short loc_180025CA9
0x180025ca1  mov     rcx, rbx
0x180025ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ca9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025cb0  test    rax, rax
0x180025cb3  jz      short loc_180025CC3
0x180025cb5  test    byte ptr [rbx+4], 2
0x180025cb9  jnz     short loc_180025CC3
0x180025cbb  mov     rcx, rbx
0x180025cbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cc3  cmp     [rbx+8], edi
0x180025cc6  jl      short loc_180025CE3
0x180025cc8  cmp     ebp, 3
0x180025ccb  jz      short loc_180025CD3
0x180025ccd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180025cd3  mov     ecx, 8000FFFFh; this
0x180025cd8  mov     [rbx+8], ecx
0x180025cdb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180025ce0  mov     [rbx+0Ch], eax
0x180025ce3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180025cea  jnz     short loc_180025D11
0x180025cec  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180025cf3  test    rax, rax
0x180025cf6  jz      short loc_180025D01
0x180025cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025cfd  test    al, al
0x180025cff  jmp     short loc_180025D0F
0x180025d01  call    cs:__imp_IsDebuggerPresent
0x180025d08  nop     dword ptr [rax+rax+00h]
0x180025d0d  test    eax, eax
0x180025d0f  jz      short loc_180025D17
0x180025d11  test    byte ptr [rbx+4], 2
0x180025d15  jz      short loc_180025D3B
0x180025d17  mov     rax, cs:g_pfnResultLoggingCallback
0x180025d1e  test    rax, rax
0x180025d21  jz      short loc_180025D86
0x180025d23  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180025d2a  jnz     short loc_180025D86
0x180025d2c  xor     r8d, r8d
0x180025d2f  xor     edx, edx
0x180025d31  mov     rcx, rbx
0x180025d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d39  jmp     short loc_180025D86
0x180025d3b  mov     esi, 800h
0x180025d40  mov     rax, cs:g_pfnResultLoggingCallback
0x180025d47  test    rax, rax
0x180025d4a  jz      short loc_180025D63
0x180025d4c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180025d53  jnz     short loc_180025D63
0x180025d55  mov     r8d, esi
0x180025d58  mov     rdx, r14
0x180025d5b  mov     rcx, rbx
0x180025d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d63  cmp     [r14], di
0x180025d67  jnz     short loc_180025D77
0x180025d69  mov     r8, rbx; unsigned __int64
0x180025d6c  mov     rdx, rsi; unsigned __int16 *
0x180025d6f  mov     rcx, r14; this
0x180025d72  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180025d77  mov     rcx, r14; lpOutputString
0x180025d7a  call    cs:__imp_OutputDebugStringW
0x180025d81  nop     dword ptr [rax+rax+00h]
0x180025d86  test    byte ptr [rbx+4], 4
0x180025d8a  jnz     short loc_180025D95
0x180025d8c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180025d93  jz      short loc_180025DA7
0x180025d95  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180025d9c  test    rax, rax
0x180025d9f  jz      short loc_180025DA7
0x180025da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025da6  nop
0x180025da7  mov     rbx, [rsp+88h+arg_10]
0x180025daf  add     rsp, 50h
0x180025db3  pop     r15
0x180025db5  pop     r14
0x180025db7  pop     r13
0x180025db9  pop     r12
0x180025dbb  pop     rdi
0x180025dbc  pop     rsi
0x180025dbd  pop     rbp
0x180025dbe  retn
```
