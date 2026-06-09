# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000284c`
- end: `0x180002ae2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800024e8`

## callees

- `0x18000284c`
- `0x1800036b4`
- `0x180004760`
- `0x180005318`
- `0x180005560`
- `0x18001dfe2`
- `0x18001e020`
- `0x18001e0e0`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800028f7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800029f2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800029f2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002a7c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002a7c`

## pseudocode

```c
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
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
0x18000284c  mov     [rsp-8+arg_10], rbx
0x180002851  push    rbp
0x180002852  push    rsi
0x180002853  push    rdi
0x180002854  push    r14
0x180002856  push    r15
0x180002858  lea     rbp, [rsp-13D0h]
0x180002860  mov     eax, 14D0h
0x180002865  call    _alloca_probe
0x18000286a  sub     rsp, rax
0x18000286d  mov     rax, cs:__security_cookie
0x180002874  xor     rax, rsp
0x180002877  mov     [rbp+13F0h+var_30], rax
0x18000287e  mov     esi, edx
0x180002880  mov     r14, rcx
0x180002883  mov     rdi, [rbp+13F0h+arg_28]
0x18000288a  xor     edx, edx; Val
0x18000288c  mov     r8d, 98h; Size
0x180002892  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002897  call    memset_0
0x18000289c  nop
0x18000289d  xor     r15d, r15d
0x1800028a0  mov     [rbp+13F0h+OutputString], r15w
0x1800028a8  mov     [rbp+13F0h+var_1430], r15b
0x1800028ac  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800028b3  mov     ecx, [rdx]; this
0x1800028b5  mov     [rsp+14F0h+var_14C8], ecx
0x1800028b9  mov     eax, [rdx+4]
0x1800028bc  mov     [rsp+14F0h+var_14C4], eax
0x1800028c0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800028c5  mov     ebx, eax
0x1800028c7  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800028cf  mov     ecx, r15d
0x1800028d2  lea     eax, [r15+8]
0x1800028d6  cmp     dword ptr [rdx+8], 1
0x1800028da  cmovz   ecx, eax
0x1800028dd  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800028e1  lea     ecx, [rax-7]
0x1800028e4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800028ec  inc     ecx
0x1800028ee  mov     [rsp+14F0h+var_14C0], ecx
0x1800028f2  mov     [rsp+14F0h+var_14B8], r15
0x1800028f7  call    cs:__imp_GetCurrentThreadId
0x1800028fd  mov     [rsp+14F0h+var_14B0], eax
0x180002901  lea     rax, aWil; "wil"
0x180002908  mov     [rsp+14F0h+var_1498], rax
0x18000290d  mov     [rsp+14F0h+var_1490], esi
0x180002911  mov     [rsp+14F0h+var_148C], ebx
0x180002915  mov     [rsp+14F0h+var_14A8], r15
0x18000291a  mov     [rsp+14F0h+var_14A0], r15
0x18000291f  mov     [rbp+13F0h+var_1448], rdi
0x180002923  mov     [rbp+13F0h+var_1440], r14
0x180002927  mov     [rsp+14F0h+var_1488], r15
0x18000292c  xorps   xmm0, xmm0
0x18000292f  xor     eax, eax
0x180002931  movups  [rbp+13F0h+var_1468], xmm0
0x180002935  mov     [rbp+13F0h+var_1458], rax
0x180002939  xorps   xmm1, xmm1
0x18000293c  movups  [rsp+14F0h+var_1480], xmm1
0x180002941  mov     [rbp+13F0h+var_1470], rax
0x180002945  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000294c  test    rax, rax
0x18000294f  jz      short loc_18000295C
0x180002951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002956  mov     [rbp+13F0h+var_1450], rax
0x18000295a  jmp     short loc_180002960
0x18000295c  mov     [rbp+13F0h+var_1450], r15
0x180002960  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002967  test    rax, rax
0x18000296a  jz      short loc_180002976
0x18000296c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002976  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000297d  test    rax, rax
0x180002980  jz      short loc_180002996
0x180002982  mov     r8d, 400h
0x180002988  lea     rdx, [rbp+13F0h+var_1430]
0x18000298c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002991  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002996  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000299d  test    rax, rax
0x1800029a0  jz      short loc_1800029AC
0x1800029a2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800029a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ac  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800029b3  test    rax, rax
0x1800029b6  jz      short loc_1800029C9
0x1800029b8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800029bd  jnz     short loc_1800029C9
0x1800029bf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800029c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029c9  cmp     [rsp+14F0h+var_14C8], r15d
0x1800029ce  jge     loc_180002ADC
0x1800029d4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800029db  jnz     short loc_1800029FC
0x1800029dd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800029e4  test    rax, rax
0x1800029e7  jz      short loc_1800029F2
0x1800029e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ee  test    al, al
0x1800029f0  jmp     short loc_1800029FA
0x1800029f2  call    cs:__imp_IsDebuggerPresent
0x1800029f8  test    eax, eax
0x1800029fa  jz      short loc_180002A03
0x1800029fc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002a01  jz      short loc_180002A29
0x180002a03  mov     rax, cs:g_pfnResultLoggingCallback
0x180002a0a  test    rax, rax
0x180002a0d  jz      short loc_180002A82
0x180002a0f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002a16  jnz     short loc_180002A82
0x180002a18  xor     r8d, r8d
0x180002a1b  xor     edx, edx
0x180002a1d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a27  jmp     short loc_180002A82
0x180002a29  mov     ebx, 800h
0x180002a2e  mov     rax, cs:g_pfnResultLoggingCallback
0x180002a35  test    rax, rax
0x180002a38  jz      short loc_180002A57
0x180002a3a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002a41  jnz     short loc_180002A57
0x180002a43  mov     r8d, ebx
0x180002a46  lea     rdx, [rbp+13F0h+OutputString]
0x180002a4d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a57  cmp     [rbp+13F0h+OutputString], r15w
0x180002a5f  jnz     short loc_180002A75
0x180002a61  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002a66  mov     rdx, rbx; unsigned __int16 *
0x180002a69  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002a70  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002a75  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002a7c  call    cs:__imp_OutputDebugStringW
0x180002a82  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002a87  jnz     short loc_180002A92
0x180002a89  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002a90  jz      short loc_180002AA4
0x180002a92  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002a99  test    rax, rax
0x180002a9c  jz      short loc_180002AA4
0x180002a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aa3  nop
0x180002aa4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002aa9  jnz     short loc_180002AD1
0x180002aab  mov     rcx, [rbp+13F0h+var_30]
0x180002ab2  xor     rcx, rsp; StackCookie
0x180002ab5  call    __security_check_cookie
0x180002aba  mov     rbx, [rsp+14F0h+arg_10]
0x180002ac2  add     rsp, 14D0h
0x180002ac9  pop     r15
0x180002acb  pop     r14
0x180002acd  pop     rdi
0x180002ace  pop     rsi
0x180002acf  pop     rbp
0x180002ad0  retn
0x180002ad1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002ad6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002adc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
