# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800032d0`
- end: `0x18000355d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002db0`

## callees

- `0x180001e20`
- `0x180002ac8`
- `0x1800032d0`
- `0x180004444`
- `0x180005340`
- `0x1800062b0`
- `0x18000638c`
- `0x180010010`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000337e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000337e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003472`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003472`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800034fc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800034fc`

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
0x1800032d0  push    rbp
0x1800032d2  push    rbx
0x1800032d3  push    rsi
0x1800032d4  push    rdi
0x1800032d5  push    r12
0x1800032d7  push    r14
0x1800032d9  push    r15
0x1800032db  lea     rbp, [rsp-13D0h]
0x1800032e3  mov     eax, 14D0h
0x1800032e8  call    _alloca_probe
0x1800032ed  sub     rsp, rax
0x1800032f0  mov     rax, cs:__security_cookie
0x1800032f7  xor     rax, rsp
0x1800032fa  mov     [rbp+1400h+var_40], rax
0x180003301  mov     r14, r8
0x180003304  mov     esi, edx
0x180003306  mov     r15, rcx
0x180003309  mov     rdi, [rbp+1400h+arg_28]
0x180003310  xor     edx, edx; Val
0x180003312  mov     r8d, 98h; Size
0x180003318  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000331d  call    memset_0
0x180003322  nop
0x180003323  xor     r12d, r12d
0x180003326  mov     [rbp+1400h+OutputString], r12w
0x18000332e  mov     [rbp+1400h+var_1440], r12b
0x180003332  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180003339  mov     ecx, [rdx]; this
0x18000333b  mov     [rsp+1500h+var_14D8], ecx
0x18000333f  mov     eax, [rdx+4]
0x180003342  mov     [rsp+1500h+var_14D4], eax
0x180003346  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000334b  mov     ebx, eax
0x18000334d  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003355  mov     ecx, r12d
0x180003358  lea     eax, [r12+8]
0x18000335d  cmp     dword ptr [rdx+8], 1
0x180003361  cmovz   ecx, eax
0x180003364  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003368  lea     ecx, [rax-7]
0x18000336b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003373  inc     ecx
0x180003375  mov     [rsp+1500h+var_14D0], ecx
0x180003379  mov     [rsp+1500h+var_14C8], r12
0x18000337e  call    cs:__imp_GetCurrentThreadId
0x180003384  mov     [rsp+1500h+var_14C0], eax
0x180003388  mov     [rsp+1500h+var_14A8], r14
0x18000338d  mov     [rsp+1500h+var_14A0], esi
0x180003391  mov     [rsp+1500h+var_149C], ebx
0x180003395  mov     [rsp+1500h+var_14B8], r12
0x18000339a  mov     [rsp+1500h+var_14B0], r12
0x18000339f  mov     [rbp+1400h+var_1458], rdi
0x1800033a3  mov     [rbp+1400h+var_1450], r15
0x1800033a7  mov     [rsp+1500h+var_1498], r12
0x1800033ac  xorps   xmm0, xmm0
0x1800033af  xor     eax, eax
0x1800033b1  movups  [rbp+1400h+var_1478], xmm0
0x1800033b5  mov     [rbp+1400h+var_1468], rax
0x1800033b9  xorps   xmm1, xmm1
0x1800033bc  movups  [rsp+1500h+var_1490], xmm1
0x1800033c1  mov     [rbp+1400h+var_1480], rax
0x1800033c5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800033cc  test    rax, rax
0x1800033cf  jz      short loc_1800033DC
0x1800033d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033d6  mov     [rbp+1400h+var_1460], rax
0x1800033da  jmp     short loc_1800033E0
0x1800033dc  mov     [rbp+1400h+var_1460], r12
0x1800033e0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800033e7  test    rax, rax
0x1800033ea  jz      short loc_1800033F6
0x1800033ec  lea     rcx, [rsp+1500h+var_14E0]
0x1800033f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033f6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800033fd  test    rax, rax
0x180003400  jz      short loc_180003416
0x180003402  mov     r8d, 400h
0x180003408  lea     rdx, [rbp+1400h+var_1440]
0x18000340c  lea     rcx, [rsp+1500h+var_14E0]
0x180003411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003416  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000341d  test    rax, rax
0x180003420  jz      short loc_18000342C
0x180003422  lea     rcx, [rsp+1500h+var_14E0]
0x180003427  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000342c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003433  test    rax, rax
0x180003436  jz      short loc_180003449
0x180003438  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000343d  jnz     short loc_180003449
0x18000343f  lea     rcx, [rsp+1500h+var_14E0]
0x180003444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003449  cmp     [rsp+1500h+var_14D8], r12d
0x18000344e  jge     loc_180003557
0x180003454  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000345b  jnz     short loc_18000347C
0x18000345d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003464  test    rax, rax
0x180003467  jz      short loc_180003472
0x180003469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000346e  test    al, al
0x180003470  jmp     short loc_18000347A
0x180003472  call    cs:__imp_IsDebuggerPresent
0x180003478  test    eax, eax
0x18000347a  jz      short loc_180003483
0x18000347c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003481  jz      short loc_1800034A9
0x180003483  mov     rax, cs:g_pfnResultLoggingCallback
0x18000348a  test    rax, rax
0x18000348d  jz      short loc_180003502
0x18000348f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003496  jnz     short loc_180003502
0x180003498  xor     r8d, r8d
0x18000349b  xor     edx, edx
0x18000349d  lea     rcx, [rsp+1500h+var_14E0]
0x1800034a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034a7  jmp     short loc_180003502
0x1800034a9  mov     ebx, 800h
0x1800034ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800034b5  test    rax, rax
0x1800034b8  jz      short loc_1800034D7
0x1800034ba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800034c1  jnz     short loc_1800034D7
0x1800034c3  mov     r8d, ebx
0x1800034c6  lea     rdx, [rbp+1400h+OutputString]
0x1800034cd  lea     rcx, [rsp+1500h+var_14E0]
0x1800034d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034d7  cmp     [rbp+1400h+OutputString], r12w
0x1800034df  jnz     short loc_1800034F5
0x1800034e1  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800034e6  mov     rdx, rbx; unsigned __int16 *
0x1800034e9  lea     rcx, [rbp+1400h+OutputString]; this
0x1800034f0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800034f5  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800034fc  call    cs:__imp_OutputDebugStringW
0x180003502  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003507  jnz     short loc_180003512
0x180003509  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003510  jz      short loc_180003524
0x180003512  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003519  test    rax, rax
0x18000351c  jz      short loc_180003524
0x18000351e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003523  nop
0x180003524  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003529  jnz     short loc_18000354C
0x18000352b  mov     rcx, [rbp+1400h+var_40]
0x180003532  xor     rcx, rsp; StackCookie
0x180003535  call    __security_check_cookie
0x18000353a  add     rsp, 14D0h
0x180003541  pop     r15
0x180003543  pop     r14
0x180003545  pop     r12
0x180003547  pop     rdi
0x180003548  pop     rsi
0x180003549  pop     rbx
0x18000354a  pop     rbp
0x18000354b  retn
0x18000354c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003551  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003557  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
