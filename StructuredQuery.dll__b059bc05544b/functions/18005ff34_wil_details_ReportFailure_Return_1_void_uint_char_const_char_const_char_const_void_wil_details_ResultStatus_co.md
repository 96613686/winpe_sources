# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18005ff34`
- end: `0x1800601da`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180059164`

## callees

- `0x18005a480`
- `0x18005daf0`
- `0x18005e740`
- `0x18005ff34`
- `0x180062578`
- `0x180066c68`
- `0x180066fc0`
- `0x180084e10`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fffa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005fffa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800600ef`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800600ef`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180060179`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180060179`

## pseudocode

```c
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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
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
0x18005ff34  push    rbp
0x18005ff36  push    rbx
0x18005ff37  push    rsi
0x18005ff38  push    rdi
0x18005ff39  push    r12
0x18005ff3b  push    r14
0x18005ff3d  push    r15
0x18005ff3f  lea     rbp, [rsp-13D0h]
0x18005ff47  mov     eax, 14D0h
0x18005ff4c  call    _alloca_probe
0x18005ff51  sub     rsp, rax
0x18005ff54  mov     rax, cs:__security_cookie
0x18005ff5b  xor     rax, rsp
0x18005ff5e  mov     [rbp+1400h+var_40], rax
0x18005ff65  mov     rsi, r8
0x18005ff68  mov     edi, edx
0x18005ff6a  mov     rbx, rcx
0x18005ff6d  mov     r14, [rbp+1400h+arg_28]
0x18005ff74  xor     edx, edx; Val
0x18005ff76  mov     r8d, 98h; Size
0x18005ff7c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18005ff81  call    memset_0
0x18005ff86  nop
0x18005ff87  xor     r12d, r12d
0x18005ff8a  mov     [rbp+1400h+OutputString], r12w
0x18005ff92  mov     [rbp+1400h+var_1440], r12b
0x18005ff96  mov     rdx, [rbp+1400h+arg_30]; int
0x18005ff9d  mov     ecx, [rdx]; this
0x18005ff9f  mov     [rsp+1500h+var_14D8], ecx
0x18005ffa3  mov     eax, [rdx+4]
0x18005ffa6  mov     [rsp+1500h+var_14D4], eax
0x18005ffaa  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18005ffaf  mov     r15d, eax
0x18005ffb2  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18005ffba  mov     ecx, r12d
0x18005ffbd  lea     eax, [r12+8]
0x18005ffc2  cmp     dword ptr [rdx+8], 1
0x18005ffc6  cmovz   ecx, eax
0x18005ffc9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18005ffcd  lea     ecx, [rax-7]
0x18005ffd0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18005ffd8  inc     ecx
0x18005ffda  mov     [rsp+1500h+var_14D0], ecx
0x18005ffde  mov     rcx, [rbp+1400h+arg_38]
0x18005ffe5  test    rcx, rcx
0x18005ffe8  jz      short loc_18005FFF5
0x18005ffea  cmp     [rcx], r12w
0x18005ffee  mov     [rsp+1500h+var_14C8], rcx
0x18005fff3  jnz     short loc_18005FFFA
0x18005fff5  mov     [rsp+1500h+var_14C8], r12
0x18005fffa  call    cs:__imp_GetCurrentThreadId
0x180060000  mov     [rsp+1500h+var_14C0], eax
0x180060004  mov     [rsp+1500h+var_14A8], rsi
0x180060009  mov     [rsp+1500h+var_14A0], edi
0x18006000d  mov     [rsp+1500h+var_149C], r15d
0x180060012  mov     [rsp+1500h+var_14B8], r12
0x180060017  mov     [rsp+1500h+var_14B0], r12
0x18006001c  mov     [rbp+1400h+var_1458], r14
0x180060020  mov     [rbp+1400h+var_1450], rbx
0x180060024  mov     [rsp+1500h+var_1498], r12
0x180060029  xorps   xmm0, xmm0
0x18006002c  xor     eax, eax
0x18006002e  movups  [rbp+1400h+var_1478], xmm0
0x180060032  mov     [rbp+1400h+var_1468], rax
0x180060036  xorps   xmm1, xmm1
0x180060039  movups  [rsp+1500h+var_1490], xmm1
0x18006003e  mov     [rbp+1400h+var_1480], rax
0x180060042  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180060049  test    rax, rax
0x18006004c  jz      short loc_180060059
0x18006004e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060053  mov     [rbp+1400h+var_1460], rax
0x180060057  jmp     short loc_18006005D
0x180060059  mov     [rbp+1400h+var_1460], r12
0x18006005d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180060064  test    rax, rax
0x180060067  jz      short loc_180060073
0x180060069  lea     rcx, [rsp+1500h+var_14E0]
0x18006006e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060073  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18006007a  test    rax, rax
0x18006007d  jz      short loc_180060093
0x18006007f  mov     r8d, 400h
0x180060085  lea     rdx, [rbp+1400h+var_1440]
0x180060089  lea     rcx, [rsp+1500h+var_14E0]
0x18006008e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060093  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18006009a  test    rax, rax
0x18006009d  jz      short loc_1800600A9
0x18006009f  lea     rcx, [rsp+1500h+var_14E0]
0x1800600a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800600a9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800600b0  test    rax, rax
0x1800600b3  jz      short loc_1800600C6
0x1800600b5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800600ba  jnz     short loc_1800600C6
0x1800600bc  lea     rcx, [rsp+1500h+var_14E0]
0x1800600c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800600c6  cmp     [rsp+1500h+var_14D8], r12d
0x1800600cb  jge     loc_1800601D4
0x1800600d1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800600d8  jnz     short loc_1800600F9
0x1800600da  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800600e1  test    rax, rax
0x1800600e4  jz      short loc_1800600EF
0x1800600e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800600eb  test    al, al
0x1800600ed  jmp     short loc_1800600F7
0x1800600ef  call    cs:__imp_IsDebuggerPresent
0x1800600f5  test    eax, eax
0x1800600f7  jz      short loc_180060100
0x1800600f9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800600fe  jz      short loc_180060126
0x180060100  mov     rax, cs:g_pfnResultLoggingCallback
0x180060107  test    rax, rax
0x18006010a  jz      short loc_18006017F
0x18006010c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180060113  jnz     short loc_18006017F
0x180060115  xor     r8d, r8d
0x180060118  xor     edx, edx
0x18006011a  lea     rcx, [rsp+1500h+var_14E0]
0x18006011f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060124  jmp     short loc_18006017F
0x180060126  mov     ebx, 800h
0x18006012b  mov     rax, cs:g_pfnResultLoggingCallback
0x180060132  test    rax, rax
0x180060135  jz      short loc_180060154
0x180060137  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18006013e  jnz     short loc_180060154
0x180060140  mov     r8d, ebx
0x180060143  lea     rdx, [rbp+1400h+OutputString]
0x18006014a  lea     rcx, [rsp+1500h+var_14E0]
0x18006014f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180060154  cmp     [rbp+1400h+OutputString], r12w
0x18006015c  jnz     short loc_180060172
0x18006015e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180060163  mov     rdx, rbx; wchar_t *
0x180060166  lea     rcx, [rbp+1400h+OutputString]; this
0x18006016d  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180060172  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180060179  call    cs:__imp_OutputDebugStringW
0x18006017f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180060184  jnz     short loc_18006018F
0x180060186  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18006018d  jz      short loc_1800601A1
0x18006018f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180060196  test    rax, rax
0x180060199  jz      short loc_1800601A1
0x18006019b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800601a0  nop
0x1800601a1  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800601a6  jnz     short loc_1800601C9
0x1800601a8  mov     rcx, [rbp+1400h+var_40]
0x1800601af  xor     rcx, rsp; StackCookie
0x1800601b2  call    __security_check_cookie
0x1800601b7  add     rsp, 14D0h
0x1800601be  pop     r15
0x1800601c0  pop     r14
0x1800601c2  pop     r12
0x1800601c4  pop     rdi
0x1800601c5  pop     rsi
0x1800601c6  pop     rbx
0x1800601c7  pop     rbp
0x1800601c8  retn
0x1800601c9  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800601ce  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800601d4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
