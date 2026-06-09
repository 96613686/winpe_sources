# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180058514`
- end: `0x18005881c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `776`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180058254`
- `0x180058354`
- `0x1800781e4`
- `0x1800782a4`

## callees

- `0x180053998`
- `0x180055e24`
- `0x180058514`
- `0x18005cc64`
- `0x18006d994`
- `0x180078128`
- `0x18007946c`
- `0x180079490`
- `0x18007a3d8`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058637`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058637`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005875e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005875e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800587d6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800587d6`

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
0x180058514  mov     [rsp+arg_10], rbx
0x180058519  mov     [rsp+arg_8], edx
0x18005851d  mov     [rsp+arg_0], rcx
0x180058522  push    rbp
0x180058523  push    rsi
0x180058524  push    rdi
0x180058525  push    r12
0x180058527  push    r13
0x180058529  push    r14
0x18005852b  push    r15
0x18005852d  sub     rsp, 40h
0x180058531  mov     r12, r9
0x180058534  mov     r13, r8
0x180058537  mov     r10, rcx
0x18005853a  xor     eax, eax
0x18005853c  mov     rsi, [rsp+78h+lpOutputString]
0x180058544  mov     [rsi], ax
0x180058547  mov     rax, [rsp+78h+arg_60]
0x18005854f  mov     byte ptr [rax], 0
0x180058552  mov     r14, [rsp+78h+arg_38]
0x18005855a  mov     edi, [r14]
0x18005855d  mov     rbx, [rsp+78h+arg_78]
0x180058565  mov     [rbx+8], edi
0x180058568  mov     eax, [r14+4]
0x18005856c  mov     [rbx+0Ch], eax
0x18005856f  xor     ebp, ebp
0x180058571  mov     r15d, [rsp+78h+arg_30]
0x180058579  mov     ecx, r15d
0x18005857c  test    r15d, r15d
0x18005857f  jz      short loc_1800585E7
0x180058581  sub     ecx, 1
0x180058584  jz      short loc_1800585DE
0x180058586  sub     ecx, 1
0x180058589  jz      short loc_180058599
0x18005858b  cmp     ecx, 1
0x18005858e  jnz     short loc_1800585F0
0x180058590  mov     ecx, edi; this
0x180058592  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180058597  jmp     short loc_1800585EE
0x180058599  test    edi, edi
0x18005859b  js      short loc_1800585D5
0x18005859d  mov     edi, 8007029Ch
0x1800585a2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800585a6  mov     rax, [rsp+78h+arg_28]
0x1800585ae  mov     [rsp+78h+var_50], rax; __int64
0x1800585b3  mov     rax, [rsp+78h+arg_20]
0x1800585bb  mov     [rsp+78h+var_58], rax; __int64
0x1800585c0  mov     rcx, r10; int
0x1800585c3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800585c8  mov     [rbx+8], edi
0x1800585cb  mov     ecx, edi; this
0x1800585cd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800585d2  mov     [rbx+0Ch], eax
0x1800585d5  mov     ecx, edi; this
0x1800585d7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800585dc  jmp     short loc_1800585EE
0x1800585de  mov     ecx, edi; this
0x1800585e0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800585e5  jmp     short loc_1800585EE
0x1800585e7  mov     ecx, edi; this
0x1800585e9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800585ee  mov     ebp, eax
0x1800585f0  mov     [rbx], r15d
0x1800585f3  mov     eax, [rsp+78h+arg_70]
0x1800585fa  mov     [rbx+4], eax
0x1800585fd  cmp     dword ptr [r14+8], 1
0x180058602  jnz     short loc_18005860A
0x180058604  or      eax, 8
0x180058607  mov     [rbx+4], eax
0x18005860a  mov     eax, 1
0x18005860f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180058617  inc     eax
0x180058619  mov     [rbx+10h], eax
0x18005861c  mov     rax, [rsp+78h+arg_40]
0x180058624  xor     edi, edi
0x180058626  test    rax, rax
0x180058629  jz      short loc_180058630
0x18005862b  cmp     [rax], di
0x18005862e  jnz     short loc_180058633
0x180058630  mov     rax, rdi
0x180058633  mov     [rbx+18h], rax
0x180058637  call    cs:__imp_GetCurrentThreadId
0x18005863e  nop     dword ptr [rax+rax+00h]
0x180058643  mov     [rbx+20h], eax
0x180058646  mov     [rbx+38h], r13
0x18005864a  mov     eax, [rsp+78h+arg_8]
0x180058651  mov     [rbx+40h], eax
0x180058654  mov     [rbx+44h], ebp
0x180058657  mov     rax, [rsp+78h+arg_20]
0x18005865f  mov     [rbx+28h], rax
0x180058663  mov     [rbx+30h], r12
0x180058667  mov     rax, [rsp+78h+arg_28]
0x18005866f  mov     [rbx+88h], rax
0x180058676  mov     rax, [rsp+78h+arg_0]
0x18005867e  mov     [rbx+90h], rax
0x180058685  mov     [rbx+48h], rdi
0x180058689  xorps   xmm0, xmm0
0x18005868c  xor     eax, eax
0x18005868e  movups  xmmword ptr [rbx+68h], xmm0
0x180058692  mov     [rbx+78h], rax
0x180058696  movups  xmmword ptr [rbx+50h], xmm0
0x18005869a  mov     [rbx+60h], rax
0x18005869e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800586a5  test    rax, rax
0x1800586a8  jz      short loc_1800586B1
0x1800586aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800586af  jmp     short loc_1800586B4
0x1800586b1  mov     rax, rdi
0x1800586b4  mov     [rbx+80h], rax
0x1800586bb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800586c2  test    rax, rax
0x1800586c5  jz      short loc_1800586CF
0x1800586c7  mov     rcx, rbx
0x1800586ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800586cf  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800586d6  test    rax, rax
0x1800586d9  jz      short loc_1800586F1
0x1800586db  mov     r8d, 400h
0x1800586e1  mov     rdx, [rsp+78h+arg_60]
0x1800586e9  mov     rcx, rbx
0x1800586ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800586f1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800586f8  test    rax, rax
0x1800586fb  jz      short loc_180058705
0x1800586fd  mov     rcx, rbx
0x180058700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058705  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005870c  test    rax, rax
0x18005870f  jz      short loc_18005871F
0x180058711  test    byte ptr [rbx+4], 2
0x180058715  jnz     short loc_18005871F
0x180058717  mov     rcx, rbx
0x18005871a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005871f  cmp     [rbx+8], edi
0x180058722  jl      short loc_180058740
0x180058724  cmp     r15d, 3
0x180058728  jz      short loc_180058730
0x18005872a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180058730  mov     ecx, 8000FFFFh; this
0x180058735  mov     [rbx+8], ecx
0x180058738  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005873d  mov     [rbx+0Ch], eax
0x180058740  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180058747  jnz     short loc_18005876E
0x180058749  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180058750  test    rax, rax
0x180058753  jz      short loc_18005875E
0x180058755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005875a  test    al, al
0x18005875c  jmp     short loc_18005876C
0x18005875e  call    cs:__imp_IsDebuggerPresent
0x180058765  nop     dword ptr [rax+rax+00h]
0x18005876a  test    eax, eax
0x18005876c  jz      short loc_180058774
0x18005876e  test    byte ptr [rbx+4], 2
0x180058772  jz      short loc_180058798
0x180058774  mov     rax, cs:g_pfnResultLoggingCallback
0x18005877b  test    rax, rax
0x18005877e  jz      short loc_1800587E2
0x180058780  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180058787  jnz     short loc_1800587E2
0x180058789  xor     r8d, r8d
0x18005878c  xor     edx, edx
0x18005878e  mov     rcx, rbx
0x180058791  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058796  jmp     short loc_1800587E2
0x180058798  mov     ebp, 800h
0x18005879d  mov     rax, cs:g_pfnResultLoggingCallback
0x1800587a4  test    rax, rax
0x1800587a7  jz      short loc_1800587C0
0x1800587a9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800587b0  jnz     short loc_1800587C0
0x1800587b2  mov     r8d, ebp
0x1800587b5  mov     rdx, rsi
0x1800587b8  mov     rcx, rbx
0x1800587bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800587c0  cmp     [rsi], di
0x1800587c3  jnz     short loc_1800587D3
0x1800587c5  mov     r8, rbx; unsigned __int64
0x1800587c8  mov     rdx, rbp; unsigned __int16 *
0x1800587cb  mov     rcx, rsi; this
0x1800587ce  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800587d3  mov     rcx, rsi; lpOutputString
0x1800587d6  call    cs:__imp_OutputDebugStringW
0x1800587dd  nop     dword ptr [rax+rax+00h]
0x1800587e2  test    byte ptr [rbx+4], 4
0x1800587e6  jnz     short loc_1800587F1
0x1800587e8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800587ef  jz      short loc_180058803
0x1800587f1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800587f8  test    rax, rax
0x1800587fb  jz      short loc_180058803
0x1800587fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058802  nop
0x180058803  mov     rbx, [rsp+78h+arg_10]
0x18005880b  add     rsp, 40h
0x18005880f  pop     r15
0x180058811  pop     r14
0x180058813  pop     r13
0x180058815  pop     r12
0x180058817  pop     rdi
0x180058818  pop     rsi
0x180058819  pop     rbp
0x18005881a  retn
```
