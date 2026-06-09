# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800083f8`
- end: `0x1800086f1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180005158`
- `0x1800054c4`
- `0x18000e754`

## callees

- `0x180004fd0`
- `0x1800074c4`
- `0x180007f1c`
- `0x1800083f8`
- `0x1800094cc`
- `0x1800094f0`
- `0x18000987c`
- `0x180009898`
- `0x18000bb40`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000851b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000851b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800086ac`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800086ac`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000863a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000863a`

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
      wil::details::in1diag3::FailFastImmediate_Unexpected(v24);
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
0x1800083f8  mov     [rsp+arg_10], rbx
0x1800083fd  mov     [rsp+arg_8], edx
0x180008401  mov     [rsp+arg_0], rcx
0x180008406  push    rbp
0x180008407  push    rsi
0x180008408  push    rdi
0x180008409  push    r12
0x18000840b  push    r13
0x18000840d  push    r14
0x18000840f  push    r15
0x180008411  sub     rsp, 40h
0x180008415  mov     r12, r9
0x180008418  mov     r13, r8
0x18000841b  mov     r10, rcx
0x18000841e  xor     eax, eax
0x180008420  mov     rsi, [rsp+78h+lpOutputString]
0x180008428  mov     [rsi], ax
0x18000842b  mov     rax, [rsp+78h+arg_60]
0x180008433  mov     byte ptr [rax], 0
0x180008436  mov     r14, [rsp+78h+arg_38]
0x18000843e  mov     edi, [r14]
0x180008441  mov     rbx, [rsp+78h+arg_78]
0x180008449  mov     [rbx+8], edi
0x18000844c  mov     eax, [r14+4]
0x180008450  mov     [rbx+0Ch], eax
0x180008453  xor     ebp, ebp
0x180008455  mov     r15d, [rsp+78h+arg_30]
0x18000845d  mov     ecx, r15d
0x180008460  test    r15d, r15d
0x180008463  jz      short loc_1800084CB
0x180008465  sub     ecx, 1
0x180008468  jz      short loc_1800084C2
0x18000846a  sub     ecx, 1
0x18000846d  jz      short loc_18000847D
0x18000846f  cmp     ecx, 1
0x180008472  jnz     short loc_1800084D4
0x180008474  mov     ecx, edi; this
0x180008476  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000847b  jmp     short loc_1800084D2
0x18000847d  test    edi, edi
0x18000847f  js      short loc_1800084B9
0x180008481  mov     edi, 8007029Ch
0x180008486  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000848a  mov     rax, [rsp+78h+arg_28]
0x180008492  mov     [rsp+78h+var_50], rax; __int64
0x180008497  mov     rax, [rsp+78h+arg_20]
0x18000849f  mov     [rsp+78h+var_58], rax; __int64
0x1800084a4  mov     rcx, r10; int
0x1800084a7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800084ac  mov     [rbx+8], edi
0x1800084af  mov     ecx, edi; this
0x1800084b1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800084b6  mov     [rbx+0Ch], eax
0x1800084b9  mov     ecx, edi; this
0x1800084bb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800084c0  jmp     short loc_1800084D2
0x1800084c2  mov     ecx, edi; this
0x1800084c4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800084c9  jmp     short loc_1800084D2
0x1800084cb  mov     ecx, edi; this
0x1800084cd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800084d2  mov     ebp, eax
0x1800084d4  mov     [rbx], r15d
0x1800084d7  mov     eax, [rsp+78h+arg_70]
0x1800084de  mov     [rbx+4], eax
0x1800084e1  cmp     dword ptr [r14+8], 1
0x1800084e6  jnz     short loc_1800084EE
0x1800084e8  or      eax, 8
0x1800084eb  mov     [rbx+4], eax
0x1800084ee  mov     eax, 1
0x1800084f3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800084fb  inc     eax
0x1800084fd  mov     [rbx+10h], eax
0x180008500  mov     rax, [rsp+78h+arg_40]
0x180008508  xor     edi, edi
0x18000850a  test    rax, rax
0x18000850d  jz      short loc_180008514
0x18000850f  cmp     [rax], di
0x180008512  jnz     short loc_180008517
0x180008514  mov     rax, rdi
0x180008517  mov     [rbx+18h], rax
0x18000851b  call    cs:__imp_GetCurrentThreadId
0x180008521  mov     [rbx+20h], eax
0x180008524  mov     [rbx+38h], r13
0x180008528  mov     eax, [rsp+78h+arg_8]
0x18000852f  mov     [rbx+40h], eax
0x180008532  mov     [rbx+44h], ebp
0x180008535  mov     rax, [rsp+78h+arg_20]
0x18000853d  mov     [rbx+28h], rax
0x180008541  mov     [rbx+30h], r12
0x180008545  mov     rax, [rsp+78h+arg_28]
0x18000854d  mov     [rbx+88h], rax
0x180008554  mov     rax, [rsp+78h+arg_0]
0x18000855c  mov     [rbx+90h], rax
0x180008563  mov     [rbx+48h], rdi
0x180008567  xorps   xmm0, xmm0
0x18000856a  xor     eax, eax
0x18000856c  movups  xmmword ptr [rbx+68h], xmm0
0x180008570  mov     [rbx+78h], rax
0x180008574  movups  xmmword ptr [rbx+50h], xmm0
0x180008578  mov     [rbx+60h], rax
0x18000857c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008583  test    rax, rax
0x180008586  jz      short loc_18000858F
0x180008588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000858d  jmp     short loc_180008592
0x18000858f  mov     rax, rdi
0x180008592  mov     [rbx+80h], rax
0x180008599  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800085a0  test    rax, rax
0x1800085a3  jz      short loc_1800085AD
0x1800085a5  mov     rcx, rbx
0x1800085a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085ad  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800085b4  test    rax, rax
0x1800085b7  jz      short loc_1800085CF
0x1800085b9  mov     r8d, 400h
0x1800085bf  mov     rdx, [rsp+78h+arg_60]
0x1800085c7  mov     rcx, rbx
0x1800085ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085cf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800085d6  test    rax, rax
0x1800085d9  jz      short loc_1800085E3
0x1800085db  mov     rcx, rbx
0x1800085de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085e3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800085ea  test    rax, rax
0x1800085ed  jz      short loc_1800085FD
0x1800085ef  test    byte ptr [rbx+4], 2
0x1800085f3  jnz     short loc_1800085FD
0x1800085f5  mov     rcx, rbx
0x1800085f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085fd  cmp     [rbx+8], edi
0x180008600  jl      short loc_18000861C
0x180008602  cmp     r15d, 3
0x180008606  jnz     loc_1800086EB
0x18000860c  mov     ecx, 8000FFFFh; this
0x180008611  mov     [rbx+8], ecx
0x180008614  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008619  mov     [rbx+0Ch], eax
0x18000861c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008623  jnz     short loc_180008644
0x180008625  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000862c  test    rax, rax
0x18000862f  jz      short loc_18000863A
0x180008631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008636  test    al, al
0x180008638  jmp     short loc_180008642
0x18000863a  call    cs:__imp_IsDebuggerPresent
0x180008640  test    eax, eax
0x180008642  jz      short loc_18000864A
0x180008644  test    byte ptr [rbx+4], 2
0x180008648  jz      short loc_18000866E
0x18000864a  mov     rax, cs:g_pfnResultLoggingCallback
0x180008651  test    rax, rax
0x180008654  jz      short loc_1800086B2
0x180008656  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000865d  jnz     short loc_1800086B2
0x18000865f  xor     r8d, r8d
0x180008662  xor     edx, edx
0x180008664  mov     rcx, rbx
0x180008667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000866c  jmp     short loc_1800086B2
0x18000866e  mov     ebp, 800h
0x180008673  mov     rax, cs:g_pfnResultLoggingCallback
0x18000867a  test    rax, rax
0x18000867d  jz      short loc_180008696
0x18000867f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008686  jnz     short loc_180008696
0x180008688  mov     r8d, ebp
0x18000868b  mov     rdx, rsi
0x18000868e  mov     rcx, rbx
0x180008691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008696  cmp     [rsi], di
0x180008699  jnz     short loc_1800086A9
0x18000869b  mov     r8, rbx; unsigned __int64
0x18000869e  mov     rdx, rbp; unsigned __int16 *
0x1800086a1  mov     rcx, rsi; this
0x1800086a4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800086a9  mov     rcx, rsi; lpOutputString
0x1800086ac  call    cs:__imp_OutputDebugStringW
0x1800086b2  test    byte ptr [rbx+4], 4
0x1800086b6  jnz     short loc_1800086C1
0x1800086b8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800086bf  jz      short loc_1800086D3
0x1800086c1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800086c8  test    rax, rax
0x1800086cb  jz      short loc_1800086D3
0x1800086cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086d2  nop
0x1800086d3  mov     rbx, [rsp+78h+arg_10]
0x1800086db  add     rsp, 40h
0x1800086df  pop     r15
0x1800086e1  pop     r14
0x1800086e3  pop     r13
0x1800086e5  pop     r12
0x1800086e7  pop     rdi
0x1800086e8  pop     rsi
0x1800086e9  pop     rbp
0x1800086ea  retn
0x1800086eb  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
