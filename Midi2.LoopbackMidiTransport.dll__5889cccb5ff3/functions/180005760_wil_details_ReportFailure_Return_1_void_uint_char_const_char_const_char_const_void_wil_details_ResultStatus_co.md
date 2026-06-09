# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005760`
- end: `0x180005a06`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005230`

## callees

- `0x180004180`
- `0x18000500c`
- `0x180005760`
- `0x180007b74`
- `0x180009010`
- `0x18000b0d0`
- `0x18000b1c4`
- `0x1800300d0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005826`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005826`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000591b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000591b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800059a5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800059a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180005760  push    rbp
0x180005762  push    rbx
0x180005763  push    rsi
0x180005764  push    rdi
0x180005765  push    r12
0x180005767  push    r14
0x180005769  push    r15
0x18000576b  lea     rbp, [rsp-13D0h]
0x180005773  mov     eax, 14D0h
0x180005778  call    _alloca_probe
0x18000577d  sub     rsp, rax
0x180005780  mov     rax, cs:__security_cookie
0x180005787  xor     rax, rsp
0x18000578a  mov     [rbp+1400h+var_40], rax
0x180005791  mov     rsi, r8
0x180005794  mov     edi, edx
0x180005796  mov     rbx, rcx
0x180005799  mov     r14, [rbp+1400h+arg_28]
0x1800057a0  xor     edx, edx; Val
0x1800057a2  mov     r8d, 98h; Size
0x1800057a8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800057ad  call    memset_0
0x1800057b2  nop
0x1800057b3  xor     r12d, r12d
0x1800057b6  mov     [rbp+1400h+OutputString], r12w
0x1800057be  mov     [rbp+1400h+var_1440], r12b
0x1800057c2  mov     rdx, [rbp+1400h+arg_30]; int
0x1800057c9  mov     ecx, [rdx]; this
0x1800057cb  mov     [rsp+1500h+var_14D8], ecx
0x1800057cf  mov     eax, [rdx+4]
0x1800057d2  mov     [rsp+1500h+var_14D4], eax
0x1800057d6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800057db  mov     r15d, eax
0x1800057de  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800057e6  mov     ecx, r12d
0x1800057e9  lea     eax, [r12+8]
0x1800057ee  cmp     dword ptr [rdx+8], 1
0x1800057f2  cmovz   ecx, eax
0x1800057f5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800057f9  lea     ecx, [rax-7]
0x1800057fc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005804  inc     ecx
0x180005806  mov     [rsp+1500h+var_14D0], ecx
0x18000580a  mov     rcx, [rbp+1400h+arg_38]
0x180005811  test    rcx, rcx
0x180005814  jz      short loc_180005821
0x180005816  cmp     [rcx], r12w
0x18000581a  mov     [rsp+1500h+var_14C8], rcx
0x18000581f  jnz     short loc_180005826
0x180005821  mov     [rsp+1500h+var_14C8], r12
0x180005826  call    cs:__imp_GetCurrentThreadId
0x18000582c  mov     [rsp+1500h+var_14C0], eax
0x180005830  mov     [rsp+1500h+var_14A8], rsi
0x180005835  mov     [rsp+1500h+var_14A0], edi
0x180005839  mov     [rsp+1500h+var_149C], r15d
0x18000583e  mov     [rsp+1500h+var_14B8], r12
0x180005843  mov     [rsp+1500h+var_14B0], r12
0x180005848  mov     [rbp+1400h+var_1458], r14
0x18000584c  mov     [rbp+1400h+var_1450], rbx
0x180005850  mov     [rsp+1500h+var_1498], r12
0x180005855  xorps   xmm0, xmm0
0x180005858  xor     eax, eax
0x18000585a  movups  [rbp+1400h+var_1478], xmm0
0x18000585e  mov     [rbp+1400h+var_1468], rax
0x180005862  xorps   xmm1, xmm1
0x180005865  movups  [rsp+1500h+var_1490], xmm1
0x18000586a  mov     [rbp+1400h+var_1480], rax
0x18000586e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005875  test    rax, rax
0x180005878  jz      short loc_180005885
0x18000587a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000587f  mov     [rbp+1400h+var_1460], rax
0x180005883  jmp     short loc_180005889
0x180005885  mov     [rbp+1400h+var_1460], r12
0x180005889  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005890  test    rax, rax
0x180005893  jz      short loc_18000589F
0x180005895  lea     rcx, [rsp+1500h+var_14E0]
0x18000589a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000589f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800058a6  test    rax, rax
0x1800058a9  jz      short loc_1800058BF
0x1800058ab  mov     r8d, 400h
0x1800058b1  lea     rdx, [rbp+1400h+var_1440]
0x1800058b5  lea     rcx, [rsp+1500h+var_14E0]
0x1800058ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058bf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800058c6  test    rax, rax
0x1800058c9  jz      short loc_1800058D5
0x1800058cb  lea     rcx, [rsp+1500h+var_14E0]
0x1800058d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058d5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800058dc  test    rax, rax
0x1800058df  jz      short loc_1800058F2
0x1800058e1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800058e6  jnz     short loc_1800058F2
0x1800058e8  lea     rcx, [rsp+1500h+var_14E0]
0x1800058ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058f2  cmp     [rsp+1500h+var_14D8], r12d
0x1800058f7  jge     loc_180005A00
0x1800058fd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005904  jnz     short loc_180005925
0x180005906  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000590d  test    rax, rax
0x180005910  jz      short loc_18000591B
0x180005912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005917  test    al, al
0x180005919  jmp     short loc_180005923
0x18000591b  call    cs:__imp_IsDebuggerPresent
0x180005921  test    eax, eax
0x180005923  jz      short loc_18000592C
0x180005925  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000592a  jz      short loc_180005952
0x18000592c  mov     rax, cs:g_pfnResultLoggingCallback
0x180005933  test    rax, rax
0x180005936  jz      short loc_1800059AB
0x180005938  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000593f  jnz     short loc_1800059AB
0x180005941  xor     r8d, r8d
0x180005944  xor     edx, edx
0x180005946  lea     rcx, [rsp+1500h+var_14E0]
0x18000594b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005950  jmp     short loc_1800059AB
0x180005952  mov     ebx, 800h
0x180005957  mov     rax, cs:g_pfnResultLoggingCallback
0x18000595e  test    rax, rax
0x180005961  jz      short loc_180005980
0x180005963  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000596a  jnz     short loc_180005980
0x18000596c  mov     r8d, ebx
0x18000596f  lea     rdx, [rbp+1400h+OutputString]
0x180005976  lea     rcx, [rsp+1500h+var_14E0]
0x18000597b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005980  cmp     [rbp+1400h+OutputString], r12w
0x180005988  jnz     short loc_18000599E
0x18000598a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000598f  mov     rdx, rbx; unsigned __int16 *
0x180005992  lea     rcx, [rbp+1400h+OutputString]; this
0x180005999  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000599e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800059a5  call    cs:__imp_OutputDebugStringW
0x1800059ab  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800059b0  jnz     short loc_1800059BB
0x1800059b2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800059b9  jz      short loc_1800059CD
0x1800059bb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800059c2  test    rax, rax
0x1800059c5  jz      short loc_1800059CD
0x1800059c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059cc  nop
0x1800059cd  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800059d2  jnz     short loc_1800059F5
0x1800059d4  mov     rcx, [rbp+1400h+var_40]
0x1800059db  xor     rcx, rsp; StackCookie
0x1800059de  call    __security_check_cookie
0x1800059e3  add     rsp, 14D0h
0x1800059ea  pop     r15
0x1800059ec  pop     r14
0x1800059ee  pop     r12
0x1800059f0  pop     rdi
0x1800059f1  pop     rsi
0x1800059f2  pop     rbx
0x1800059f3  pop     rbp
0x1800059f4  retn
0x1800059f5  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800059fa  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005a00  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
