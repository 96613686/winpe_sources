# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800259f0`
- end: `0x180025ce5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x1800257cc`
- `0x1800258f4`
- `0x180040fc4`
- `0x18004808c`

## callees

- `0x180024adc`
- `0x1800259f0`
- `0x18002770c`
- `0x1800279cc`
- `0x180033e68`
- `0x180041670`
- `0x180041f74`
- `0x180041f90`
- `0x18004288c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025b13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025b13`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025ca6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025ca6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180025c34`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180025c34`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x1800259f0  mov     [rsp+arg_10], rbx
0x1800259f5  mov     [rsp+arg_8], edx
0x1800259f9  mov     [rsp+arg_0], rcx
0x1800259fe  push    rbp
0x1800259ff  push    rsi
0x180025a00  push    rdi
0x180025a01  push    r12
0x180025a03  push    r13
0x180025a05  push    r14
0x180025a07  push    r15
0x180025a09  sub     rsp, 40h
0x180025a0d  mov     r12, r9
0x180025a10  mov     r13, r8
0x180025a13  mov     r10, rcx
0x180025a16  xor     eax, eax
0x180025a18  mov     rsi, [rsp+78h+lpOutputString]
0x180025a20  mov     [rsi], ax
0x180025a23  mov     rax, [rsp+78h+arg_60]
0x180025a2b  mov     byte ptr [rax], 0
0x180025a2e  mov     r14, [rsp+78h+arg_38]
0x180025a36  mov     edi, [r14]
0x180025a39  mov     rbx, [rsp+78h+arg_78]
0x180025a41  mov     [rbx+8], edi
0x180025a44  mov     eax, [r14+4]
0x180025a48  mov     [rbx+0Ch], eax
0x180025a4b  xor     ebp, ebp
0x180025a4d  mov     r15d, [rsp+78h+arg_30]
0x180025a55  mov     ecx, r15d
0x180025a58  test    r15d, r15d
0x180025a5b  jz      short loc_180025AC3
0x180025a5d  sub     ecx, 1
0x180025a60  jz      short loc_180025ABA
0x180025a62  sub     ecx, 1
0x180025a65  jz      short loc_180025A75
0x180025a67  cmp     ecx, 1
0x180025a6a  jnz     short loc_180025ACC
0x180025a6c  mov     ecx, edi; this
0x180025a6e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180025a73  jmp     short loc_180025ACA
0x180025a75  test    edi, edi
0x180025a77  js      short loc_180025AB1
0x180025a79  mov     edi, 8007029Ch
0x180025a7e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180025a82  mov     rax, [rsp+78h+arg_28]
0x180025a8a  mov     [rsp+78h+var_50], rax; __int64
0x180025a8f  mov     rax, [rsp+78h+arg_20]
0x180025a97  mov     [rsp+78h+var_58], rax; __int64
0x180025a9c  mov     rcx, r10; int
0x180025a9f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180025aa4  mov     [rbx+8], edi
0x180025aa7  mov     ecx, edi; this
0x180025aa9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180025aae  mov     [rbx+0Ch], eax
0x180025ab1  mov     ecx, edi; this
0x180025ab3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180025ab8  jmp     short loc_180025ACA
0x180025aba  mov     ecx, edi; this
0x180025abc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180025ac1  jmp     short loc_180025ACA
0x180025ac3  mov     ecx, edi; this
0x180025ac5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180025aca  mov     ebp, eax
0x180025acc  mov     [rbx], r15d
0x180025acf  mov     eax, [rsp+78h+arg_70]
0x180025ad6  mov     [rbx+4], eax
0x180025ad9  cmp     dword ptr [r14+8], 1
0x180025ade  jnz     short loc_180025AE6
0x180025ae0  or      eax, 8
0x180025ae3  mov     [rbx+4], eax
0x180025ae6  mov     eax, 1
0x180025aeb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180025af3  inc     eax
0x180025af5  mov     [rbx+10h], eax
0x180025af8  mov     rax, [rsp+78h+arg_40]
0x180025b00  xor     edi, edi
0x180025b02  test    rax, rax
0x180025b05  jz      short loc_180025B0C
0x180025b07  cmp     [rax], di
0x180025b0a  jnz     short loc_180025B0F
0x180025b0c  mov     rax, rdi
0x180025b0f  mov     [rbx+18h], rax
0x180025b13  call    cs:__imp_GetCurrentThreadId
0x180025b19  mov     [rbx+20h], eax
0x180025b1c  mov     [rbx+38h], r13
0x180025b20  mov     eax, [rsp+78h+arg_8]
0x180025b27  mov     [rbx+40h], eax
0x180025b2a  mov     [rbx+44h], ebp
0x180025b2d  mov     rax, [rsp+78h+arg_20]
0x180025b35  mov     [rbx+28h], rax
0x180025b39  mov     [rbx+30h], r12
0x180025b3d  mov     rax, [rsp+78h+arg_28]
0x180025b45  mov     [rbx+88h], rax
0x180025b4c  mov     rax, [rsp+78h+arg_0]
0x180025b54  mov     [rbx+90h], rax
0x180025b5b  mov     [rbx+48h], rdi
0x180025b5f  xorps   xmm0, xmm0
0x180025b62  xor     eax, eax
0x180025b64  movups  xmmword ptr [rbx+68h], xmm0
0x180025b68  mov     [rbx+78h], rax
0x180025b6c  movups  xmmword ptr [rbx+50h], xmm0
0x180025b70  mov     [rbx+60h], rax
0x180025b74  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180025b7b  test    rax, rax
0x180025b7e  jz      short loc_180025B87
0x180025b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025b85  jmp     short loc_180025B8A
0x180025b87  mov     rax, rdi
0x180025b8a  mov     [rbx+80h], rax
0x180025b91  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180025b98  test    rax, rax
0x180025b9b  jz      short loc_180025BA5
0x180025b9d  mov     rcx, rbx
0x180025ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ba5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180025bac  test    rax, rax
0x180025baf  jz      short loc_180025BC7
0x180025bb1  mov     r8d, 400h
0x180025bb7  mov     rdx, [rsp+78h+arg_60]
0x180025bbf  mov     rcx, rbx
0x180025bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bc7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025bce  test    rax, rax
0x180025bd1  jz      short loc_180025BDB
0x180025bd3  mov     rcx, rbx
0x180025bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bdb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025be2  test    rax, rax
0x180025be5  jz      short loc_180025BF5
0x180025be7  test    byte ptr [rbx+4], 2
0x180025beb  jnz     short loc_180025BF5
0x180025bed  mov     rcx, rbx
0x180025bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025bf5  cmp     [rbx+8], edi
0x180025bf8  jl      short loc_180025C16
0x180025bfa  cmp     r15d, 3
0x180025bfe  jz      short loc_180025C06
0x180025c00  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180025c06  mov     ecx, 8000FFFFh; this
0x180025c0b  mov     [rbx+8], ecx
0x180025c0e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180025c13  mov     [rbx+0Ch], eax
0x180025c16  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180025c1d  jnz     short loc_180025C3E
0x180025c1f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180025c26  test    rax, rax
0x180025c29  jz      short loc_180025C34
0x180025c2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c30  test    al, al
0x180025c32  jmp     short loc_180025C3C
0x180025c34  call    cs:__imp_IsDebuggerPresent
0x180025c3a  test    eax, eax
0x180025c3c  jz      short loc_180025C44
0x180025c3e  test    byte ptr [rbx+4], 2
0x180025c42  jz      short loc_180025C68
0x180025c44  mov     rax, cs:g_pfnResultLoggingCallback
0x180025c4b  test    rax, rax
0x180025c4e  jz      short loc_180025CAC
0x180025c50  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180025c57  jnz     short loc_180025CAC
0x180025c59  xor     r8d, r8d
0x180025c5c  xor     edx, edx
0x180025c5e  mov     rcx, rbx
0x180025c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c66  jmp     short loc_180025CAC
0x180025c68  mov     ebp, 800h
0x180025c6d  mov     rax, cs:g_pfnResultLoggingCallback
0x180025c74  test    rax, rax
0x180025c77  jz      short loc_180025C90
0x180025c79  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180025c80  jnz     short loc_180025C90
0x180025c82  mov     r8d, ebp
0x180025c85  mov     rdx, rsi
0x180025c88  mov     rcx, rbx
0x180025c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c90  cmp     [rsi], di
0x180025c93  jnz     short loc_180025CA3
0x180025c95  mov     r8, rbx; unsigned __int64
0x180025c98  mov     rdx, rbp; unsigned __int16 *
0x180025c9b  mov     rcx, rsi; this
0x180025c9e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180025ca3  mov     rcx, rsi; lpOutputString
0x180025ca6  call    cs:__imp_OutputDebugStringW
0x180025cac  test    byte ptr [rbx+4], 4
0x180025cb0  jnz     short loc_180025CBB
0x180025cb2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180025cb9  jz      short loc_180025CCD
0x180025cbb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180025cc2  test    rax, rax
0x180025cc5  jz      short loc_180025CCD
0x180025cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ccc  nop
0x180025ccd  mov     rbx, [rsp+78h+arg_10]
0x180025cd5  add     rsp, 40h
0x180025cd9  pop     r15
0x180025cdb  pop     r14
0x180025cdd  pop     r13
0x180025cdf  pop     r12
0x180025ce1  pop     rdi
0x180025ce2  pop     rsi
0x180025ce3  pop     rbp
0x180025ce4  retn
```
