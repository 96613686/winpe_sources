# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800027cc`
- end: `0x180002a62`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800022ac`

## callees

- `0x1800027cc`
- `0x1800062b4`
- `0x180008838`
- `0x18000ae90`
- `0x18000b3b8`
- `0x18000f5c2`
- `0x18000f5f0`
- `0x18000f680`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180002877`
- `KERNEL32!GetCurrentThreadId` at `0x180002877`
- `KERNEL32!IsDebuggerPresent` at `0x180002972`
- `KERNEL32!IsDebuggerPresent` at `0x180002972`
- `KERNEL32!OutputDebugStringW` at `0x1800029fc`
- `KERNEL32!OutputDebugStringW` at `0x1800029fc`

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
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x1800027cc  mov     [rsp-8+arg_10], rbx
0x1800027d1  push    rbp
0x1800027d2  push    rsi
0x1800027d3  push    rdi
0x1800027d4  push    r14
0x1800027d6  push    r15
0x1800027d8  lea     rbp, [rsp-13D0h]
0x1800027e0  mov     eax, 14D0h
0x1800027e5  call    _alloca_probe
0x1800027ea  sub     rsp, rax
0x1800027ed  mov     rax, cs:__security_cookie
0x1800027f4  xor     rax, rsp
0x1800027f7  mov     [rbp+13F0h+var_30], rax
0x1800027fe  mov     esi, edx
0x180002800  mov     r14, rcx
0x180002803  mov     rdi, [rbp+13F0h+arg_28]
0x18000280a  xor     edx, edx; Val
0x18000280c  mov     r8d, 98h; Size
0x180002812  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002817  call    memset_0
0x18000281c  nop
0x18000281d  xor     r15d, r15d
0x180002820  mov     [rbp+13F0h+OutputString], r15w
0x180002828  mov     [rbp+13F0h+var_1430], r15b
0x18000282c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002833  mov     ecx, [rdx]; this
0x180002835  mov     [rsp+14F0h+var_14C8], ecx
0x180002839  mov     eax, [rdx+4]
0x18000283c  mov     [rsp+14F0h+var_14C4], eax
0x180002840  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002845  mov     ebx, eax
0x180002847  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000284f  mov     ecx, r15d
0x180002852  lea     eax, [r15+8]
0x180002856  cmp     dword ptr [rdx+8], 1
0x18000285a  cmovz   ecx, eax
0x18000285d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002861  lea     ecx, [rax-7]
0x180002864  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000286c  inc     ecx
0x18000286e  mov     [rsp+14F0h+var_14C0], ecx
0x180002872  mov     [rsp+14F0h+var_14B8], r15
0x180002877  call    cs:__imp_GetCurrentThreadId
0x18000287d  mov     [rsp+14F0h+var_14B0], eax
0x180002881  lea     rax, aWil; "wil"
0x180002888  mov     [rsp+14F0h+var_1498], rax
0x18000288d  mov     [rsp+14F0h+var_1490], esi
0x180002891  mov     [rsp+14F0h+var_148C], ebx
0x180002895  mov     [rsp+14F0h+var_14A8], r15
0x18000289a  mov     [rsp+14F0h+var_14A0], r15
0x18000289f  mov     [rbp+13F0h+var_1448], rdi
0x1800028a3  mov     [rbp+13F0h+var_1440], r14
0x1800028a7  mov     [rsp+14F0h+var_1488], r15
0x1800028ac  xorps   xmm0, xmm0
0x1800028af  xor     eax, eax
0x1800028b1  movups  [rbp+13F0h+var_1468], xmm0
0x1800028b5  mov     [rbp+13F0h+var_1458], rax
0x1800028b9  xorps   xmm1, xmm1
0x1800028bc  movups  [rsp+14F0h+var_1480], xmm1
0x1800028c1  mov     [rbp+13F0h+var_1470], rax
0x1800028c5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800028cc  test    rax, rax
0x1800028cf  jz      short loc_1800028DC
0x1800028d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028d6  mov     [rbp+13F0h+var_1450], rax
0x1800028da  jmp     short loc_1800028E0
0x1800028dc  mov     [rbp+13F0h+var_1450], r15
0x1800028e0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800028e7  test    rax, rax
0x1800028ea  jz      short loc_1800028F6
0x1800028ec  lea     rcx, [rsp+14F0h+var_14D0]
0x1800028f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028f6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800028fd  test    rax, rax
0x180002900  jz      short loc_180002916
0x180002902  mov     r8d, 400h
0x180002908  lea     rdx, [rbp+13F0h+var_1430]
0x18000290c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002916  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000291d  test    rax, rax
0x180002920  jz      short loc_18000292C
0x180002922  lea     rcx, [rsp+14F0h+var_14D0]
0x180002927  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000292c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002933  test    rax, rax
0x180002936  jz      short loc_180002949
0x180002938  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000293d  jnz     short loc_180002949
0x18000293f  lea     rcx, [rsp+14F0h+var_14D0]
0x180002944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002949  cmp     [rsp+14F0h+var_14C8], r15d
0x18000294e  jge     loc_180002A5C
0x180002954  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000295b  jnz     short loc_18000297C
0x18000295d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002964  test    rax, rax
0x180002967  jz      short loc_180002972
0x180002969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000296e  test    al, al
0x180002970  jmp     short loc_18000297A
0x180002972  call    cs:__imp_IsDebuggerPresent
0x180002978  test    eax, eax
0x18000297a  jz      short loc_180002983
0x18000297c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002981  jz      short loc_1800029A9
0x180002983  mov     rax, cs:g_pfnResultLoggingCallback
0x18000298a  test    rax, rax
0x18000298d  jz      short loc_180002A02
0x18000298f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002996  jnz     short loc_180002A02
0x180002998  xor     r8d, r8d
0x18000299b  xor     edx, edx
0x18000299d  lea     rcx, [rsp+14F0h+var_14D0]
0x1800029a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029a7  jmp     short loc_180002A02
0x1800029a9  mov     ebx, 800h
0x1800029ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800029b5  test    rax, rax
0x1800029b8  jz      short loc_1800029D7
0x1800029ba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800029c1  jnz     short loc_1800029D7
0x1800029c3  mov     r8d, ebx
0x1800029c6  lea     rdx, [rbp+13F0h+OutputString]
0x1800029cd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800029d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d7  cmp     [rbp+13F0h+OutputString], r15w
0x1800029df  jnz     short loc_1800029F5
0x1800029e1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800029e6  mov     rdx, rbx; wchar_t *
0x1800029e9  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800029f0  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800029f5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800029fc  call    cs:__imp_OutputDebugStringW
0x180002a02  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002a07  jnz     short loc_180002A12
0x180002a09  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002a10  jz      short loc_180002A24
0x180002a12  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002a19  test    rax, rax
0x180002a1c  jz      short loc_180002A24
0x180002a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a23  nop
0x180002a24  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002a29  jnz     short loc_180002A51
0x180002a2b  mov     rcx, [rbp+13F0h+var_30]
0x180002a32  xor     rcx, rsp; StackCookie
0x180002a35  call    __security_check_cookie
0x180002a3a  mov     rbx, [rsp+14F0h+arg_10]
0x180002a42  add     rsp, 14D0h
0x180002a49  pop     r15
0x180002a4b  pop     r14
0x180002a4d  pop     rdi
0x180002a4e  pop     rsi
0x180002a4f  pop     rbp
0x180002a50  retn
0x180002a51  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002a56  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002a5c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
