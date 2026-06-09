# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002840`
- end: `0x140002acd`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002374`

## callees

- `0x140002840`
- `0x140004274`
- `0x140005a00`
- `0x140006c38`
- `0x140006f90`
- `0x140009696`
- `0x1400096d0`
- `0x140009790`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400028ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400028ee`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400029e2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400029e2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002a6c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002a6c`

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
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x140002840  push    rbp
0x140002842  push    rbx
0x140002843  push    rsi
0x140002844  push    rdi
0x140002845  push    r12
0x140002847  push    r14
0x140002849  push    r15
0x14000284b  lea     rbp, [rsp-13D0h]
0x140002853  mov     eax, 14D0h
0x140002858  call    _alloca_probe
0x14000285d  sub     rsp, rax
0x140002860  mov     rax, cs:__security_cookie
0x140002867  xor     rax, rsp
0x14000286a  mov     [rbp+1400h+var_40], rax
0x140002871  mov     r14, r8
0x140002874  mov     esi, edx
0x140002876  mov     r15, rcx
0x140002879  mov     rdi, [rbp+1400h+arg_28]
0x140002880  xor     edx, edx; Val
0x140002882  mov     r8d, 98h; Size
0x140002888  lea     rcx, [rsp+1500h+var_14E0]; void *
0x14000288d  call    memset_0
0x140002892  nop
0x140002893  xor     r12d, r12d
0x140002896  mov     [rbp+1400h+OutputString], r12w
0x14000289e  mov     [rbp+1400h+var_1440], r12b
0x1400028a2  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1400028a9  mov     ecx, [rdx]; this
0x1400028ab  mov     [rsp+1500h+var_14D8], ecx
0x1400028af  mov     eax, [rdx+4]
0x1400028b2  mov     [rsp+1500h+var_14D4], eax
0x1400028b6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400028bb  mov     ebx, eax
0x1400028bd  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1400028c5  mov     ecx, r12d
0x1400028c8  lea     eax, [r12+8]
0x1400028cd  cmp     dword ptr [rdx+8], 1
0x1400028d1  cmovz   ecx, eax
0x1400028d4  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1400028d8  lea     ecx, [rax-7]
0x1400028db  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400028e3  inc     ecx
0x1400028e5  mov     [rsp+1500h+var_14D0], ecx
0x1400028e9  mov     [rsp+1500h+var_14C8], r12
0x1400028ee  call    cs:__imp_GetCurrentThreadId
0x1400028f4  mov     [rsp+1500h+var_14C0], eax
0x1400028f8  mov     [rsp+1500h+var_14A8], r14
0x1400028fd  mov     [rsp+1500h+var_14A0], esi
0x140002901  mov     [rsp+1500h+var_149C], ebx
0x140002905  mov     [rsp+1500h+var_14B8], r12
0x14000290a  mov     [rsp+1500h+var_14B0], r12
0x14000290f  mov     [rbp+1400h+var_1458], rdi
0x140002913  mov     [rbp+1400h+var_1450], r15
0x140002917  mov     [rsp+1500h+var_1498], r12
0x14000291c  xorps   xmm0, xmm0
0x14000291f  xor     eax, eax
0x140002921  movups  [rbp+1400h+var_1478], xmm0
0x140002925  mov     [rbp+1400h+var_1468], rax
0x140002929  xorps   xmm1, xmm1
0x14000292c  movups  [rsp+1500h+var_1490], xmm1
0x140002931  mov     [rbp+1400h+var_1480], rax
0x140002935  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000293c  test    rax, rax
0x14000293f  jz      short loc_14000294C
0x140002941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002946  mov     [rbp+1400h+var_1460], rax
0x14000294a  jmp     short loc_140002950
0x14000294c  mov     [rbp+1400h+var_1460], r12
0x140002950  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002957  test    rax, rax
0x14000295a  jz      short loc_140002966
0x14000295c  lea     rcx, [rsp+1500h+var_14E0]
0x140002961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002966  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000296d  test    rax, rax
0x140002970  jz      short loc_140002986
0x140002972  mov     r8d, 400h
0x140002978  lea     rdx, [rbp+1400h+var_1440]
0x14000297c  lea     rcx, [rsp+1500h+var_14E0]
0x140002981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002986  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000298d  test    rax, rax
0x140002990  jz      short loc_14000299C
0x140002992  lea     rcx, [rsp+1500h+var_14E0]
0x140002997  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000299c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400029a3  test    rax, rax
0x1400029a6  jz      short loc_1400029B9
0x1400029a8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400029ad  jnz     short loc_1400029B9
0x1400029af  lea     rcx, [rsp+1500h+var_14E0]
0x1400029b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029b9  cmp     [rsp+1500h+var_14D8], r12d
0x1400029be  jge     loc_140002AC7
0x1400029c4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400029cb  jnz     short loc_1400029EC
0x1400029cd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400029d4  test    rax, rax
0x1400029d7  jz      short loc_1400029E2
0x1400029d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029de  test    al, al
0x1400029e0  jmp     short loc_1400029EA
0x1400029e2  call    cs:__imp_IsDebuggerPresent
0x1400029e8  test    eax, eax
0x1400029ea  jz      short loc_1400029F3
0x1400029ec  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400029f1  jz      short loc_140002A19
0x1400029f3  mov     rax, cs:g_pfnResultLoggingCallback
0x1400029fa  test    rax, rax
0x1400029fd  jz      short loc_140002A72
0x1400029ff  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002a06  jnz     short loc_140002A72
0x140002a08  xor     r8d, r8d
0x140002a0b  xor     edx, edx
0x140002a0d  lea     rcx, [rsp+1500h+var_14E0]
0x140002a12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a17  jmp     short loc_140002A72
0x140002a19  mov     ebx, 800h
0x140002a1e  mov     rax, cs:g_pfnResultLoggingCallback
0x140002a25  test    rax, rax
0x140002a28  jz      short loc_140002A47
0x140002a2a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002a31  jnz     short loc_140002A47
0x140002a33  mov     r8d, ebx
0x140002a36  lea     rdx, [rbp+1400h+OutputString]
0x140002a3d  lea     rcx, [rsp+1500h+var_14E0]
0x140002a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a47  cmp     [rbp+1400h+OutputString], r12w
0x140002a4f  jnz     short loc_140002A65
0x140002a51  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140002a56  mov     rdx, rbx; unsigned __int16 *
0x140002a59  lea     rcx, [rbp+1400h+OutputString]; this
0x140002a60  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002a65  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140002a6c  call    cs:__imp_OutputDebugStringW
0x140002a72  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140002a77  jnz     short loc_140002A82
0x140002a79  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140002a80  jz      short loc_140002A94
0x140002a82  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002a89  test    rax, rax
0x140002a8c  jz      short loc_140002A94
0x140002a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a93  nop
0x140002a94  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140002a99  jnz     short loc_140002ABC
0x140002a9b  mov     rcx, [rbp+1400h+var_40]
0x140002aa2  xor     rcx, rsp; StackCookie
0x140002aa5  call    __security_check_cookie
0x140002aaa  add     rsp, 14D0h
0x140002ab1  pop     r15
0x140002ab3  pop     r14
0x140002ab5  pop     r12
0x140002ab7  pop     rdi
0x140002ab8  pop     rsi
0x140002ab9  pop     rbx
0x140002aba  pop     rbp
0x140002abb  retn
0x140002abc  lea     rcx, [rsp+1500h+var_14E0]; this
0x140002ac1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002ac7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
