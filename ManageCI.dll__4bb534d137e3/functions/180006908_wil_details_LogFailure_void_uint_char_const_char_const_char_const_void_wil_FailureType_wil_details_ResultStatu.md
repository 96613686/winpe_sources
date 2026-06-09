# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006908`
- end: `0x180006c01`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000418c`
- `0x18000424c`
- `0x1800046a4`

## callees

- `0x180004058`
- `0x180005f24`
- `0x180006744`
- `0x180006908`
- `0x1800070ec`
- `0x180007110`
- `0x180007124`
- `0x180007140`
- `0x18000822c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006a2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006a2b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006bbc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006bbc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006b4a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006b4a`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
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
0x180006908  mov     [rsp+arg_10], rbx
0x18000690d  mov     [rsp+arg_8], edx
0x180006911  mov     [rsp+arg_0], rcx
0x180006916  push    rbp
0x180006917  push    rsi
0x180006918  push    rdi
0x180006919  push    r12
0x18000691b  push    r13
0x18000691d  push    r14
0x18000691f  push    r15
0x180006921  sub     rsp, 40h
0x180006925  mov     r12, r9
0x180006928  mov     r13, r8
0x18000692b  mov     r10, rcx
0x18000692e  xor     eax, eax
0x180006930  mov     rsi, [rsp+78h+lpOutputString]
0x180006938  mov     [rsi], ax
0x18000693b  mov     rax, [rsp+78h+arg_60]
0x180006943  mov     byte ptr [rax], 0
0x180006946  mov     r14, [rsp+78h+arg_38]
0x18000694e  mov     edi, [r14]
0x180006951  mov     rbx, [rsp+78h+arg_78]
0x180006959  mov     [rbx+8], edi
0x18000695c  mov     eax, [r14+4]
0x180006960  mov     [rbx+0Ch], eax
0x180006963  xor     ebp, ebp
0x180006965  mov     r15d, [rsp+78h+arg_30]
0x18000696d  mov     ecx, r15d
0x180006970  test    r15d, r15d
0x180006973  jz      short loc_1800069DB
0x180006975  sub     ecx, 1
0x180006978  jz      short loc_1800069D2
0x18000697a  sub     ecx, 1
0x18000697d  jz      short loc_18000698D
0x18000697f  cmp     ecx, 1
0x180006982  jnz     short loc_1800069E4
0x180006984  mov     ecx, edi; this
0x180006986  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000698b  jmp     short loc_1800069E2
0x18000698d  test    edi, edi
0x18000698f  js      short loc_1800069C9
0x180006991  mov     edi, 8007029Ch
0x180006996  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000699a  mov     rax, [rsp+78h+arg_28]
0x1800069a2  mov     [rsp+78h+var_50], rax; __int64
0x1800069a7  mov     rax, [rsp+78h+arg_20]
0x1800069af  mov     [rsp+78h+var_58], rax; __int64
0x1800069b4  mov     rcx, r10; int
0x1800069b7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800069bc  mov     [rbx+8], edi
0x1800069bf  mov     ecx, edi; this
0x1800069c1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800069c6  mov     [rbx+0Ch], eax
0x1800069c9  mov     ecx, edi; this
0x1800069cb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800069d0  jmp     short loc_1800069E2
0x1800069d2  mov     ecx, edi; this
0x1800069d4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800069d9  jmp     short loc_1800069E2
0x1800069db  mov     ecx, edi; this
0x1800069dd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800069e2  mov     ebp, eax
0x1800069e4  mov     [rbx], r15d
0x1800069e7  mov     eax, [rsp+78h+arg_70]
0x1800069ee  mov     [rbx+4], eax
0x1800069f1  cmp     dword ptr [r14+8], 1
0x1800069f6  jnz     short loc_1800069FE
0x1800069f8  or      eax, 8
0x1800069fb  mov     [rbx+4], eax
0x1800069fe  mov     eax, 1
0x180006a03  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006a0b  inc     eax
0x180006a0d  mov     [rbx+10h], eax
0x180006a10  mov     rax, [rsp+78h+arg_40]
0x180006a18  xor     edi, edi
0x180006a1a  test    rax, rax
0x180006a1d  jz      short loc_180006A24
0x180006a1f  cmp     [rax], di
0x180006a22  jnz     short loc_180006A27
0x180006a24  mov     rax, rdi
0x180006a27  mov     [rbx+18h], rax
0x180006a2b  call    cs:__imp_GetCurrentThreadId
0x180006a31  mov     [rbx+20h], eax
0x180006a34  mov     [rbx+38h], r13
0x180006a38  mov     eax, [rsp+78h+arg_8]
0x180006a3f  mov     [rbx+40h], eax
0x180006a42  mov     [rbx+44h], ebp
0x180006a45  mov     rax, [rsp+78h+arg_20]
0x180006a4d  mov     [rbx+28h], rax
0x180006a51  mov     [rbx+30h], r12
0x180006a55  mov     rax, [rsp+78h+arg_28]
0x180006a5d  mov     [rbx+88h], rax
0x180006a64  mov     rax, [rsp+78h+arg_0]
0x180006a6c  mov     [rbx+90h], rax
0x180006a73  mov     [rbx+48h], rdi
0x180006a77  xorps   xmm0, xmm0
0x180006a7a  xor     eax, eax
0x180006a7c  movups  xmmword ptr [rbx+68h], xmm0
0x180006a80  mov     [rbx+78h], rax
0x180006a84  movups  xmmword ptr [rbx+50h], xmm0
0x180006a88  mov     [rbx+60h], rax
0x180006a8c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006a93  test    rax, rax
0x180006a96  jz      short loc_180006A9F
0x180006a98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a9d  jmp     short loc_180006AA2
0x180006a9f  mov     rax, rdi
0x180006aa2  mov     [rbx+80h], rax
0x180006aa9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006ab0  test    rax, rax
0x180006ab3  jz      short loc_180006ABD
0x180006ab5  mov     rcx, rbx
0x180006ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006abd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006ac4  test    rax, rax
0x180006ac7  jz      short loc_180006ADF
0x180006ac9  mov     r8d, 400h
0x180006acf  mov     rdx, [rsp+78h+arg_60]
0x180006ad7  mov     rcx, rbx
0x180006ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006adf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006ae6  test    rax, rax
0x180006ae9  jz      short loc_180006AF3
0x180006aeb  mov     rcx, rbx
0x180006aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006af3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006afa  test    rax, rax
0x180006afd  jz      short loc_180006B0D
0x180006aff  test    byte ptr [rbx+4], 2
0x180006b03  jnz     short loc_180006B0D
0x180006b05  mov     rcx, rbx
0x180006b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b0d  cmp     [rbx+8], edi
0x180006b10  jl      short loc_180006B2C
0x180006b12  cmp     r15d, 3
0x180006b16  jnz     loc_180006BFB
0x180006b1c  mov     ecx, 8000FFFFh; this
0x180006b21  mov     [rbx+8], ecx
0x180006b24  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006b29  mov     [rbx+0Ch], eax
0x180006b2c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006b33  jnz     short loc_180006B54
0x180006b35  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006b3c  test    rax, rax
0x180006b3f  jz      short loc_180006B4A
0x180006b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b46  test    al, al
0x180006b48  jmp     short loc_180006B52
0x180006b4a  call    cs:__imp_IsDebuggerPresent
0x180006b50  test    eax, eax
0x180006b52  jz      short loc_180006B5A
0x180006b54  test    byte ptr [rbx+4], 2
0x180006b58  jz      short loc_180006B7E
0x180006b5a  mov     rax, cs:g_pfnResultLoggingCallback
0x180006b61  test    rax, rax
0x180006b64  jz      short loc_180006BC2
0x180006b66  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006b6d  jnz     short loc_180006BC2
0x180006b6f  xor     r8d, r8d
0x180006b72  xor     edx, edx
0x180006b74  mov     rcx, rbx
0x180006b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b7c  jmp     short loc_180006BC2
0x180006b7e  mov     ebp, 800h
0x180006b83  mov     rax, cs:g_pfnResultLoggingCallback
0x180006b8a  test    rax, rax
0x180006b8d  jz      short loc_180006BA6
0x180006b8f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006b96  jnz     short loc_180006BA6
0x180006b98  mov     r8d, ebp
0x180006b9b  mov     rdx, rsi
0x180006b9e  mov     rcx, rbx
0x180006ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ba6  cmp     [rsi], di
0x180006ba9  jnz     short loc_180006BB9
0x180006bab  mov     r8, rbx; unsigned __int64
0x180006bae  mov     rdx, rbp; unsigned __int16 *
0x180006bb1  mov     rcx, rsi; this
0x180006bb4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006bb9  mov     rcx, rsi; lpOutputString
0x180006bbc  call    cs:__imp_OutputDebugStringW
0x180006bc2  test    byte ptr [rbx+4], 4
0x180006bc6  jnz     short loc_180006BD1
0x180006bc8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006bcf  jz      short loc_180006BE3
0x180006bd1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006bd8  test    rax, rax
0x180006bdb  jz      short loc_180006BE3
0x180006bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006be2  nop
0x180006be3  mov     rbx, [rsp+78h+arg_10]
0x180006beb  add     rsp, 40h
0x180006bef  pop     r15
0x180006bf1  pop     r14
0x180006bf3  pop     r13
0x180006bf5  pop     r12
0x180006bf7  pop     rdi
0x180006bf8  pop     rsi
0x180006bf9  pop     rbp
0x180006bfa  retn
0x180006bfb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
