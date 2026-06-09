# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000677c`
- end: `0x180006a07`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000625c`

## callees

- `0x180001dc0`
- `0x1800027c0`
- `0x18000677c`
- `0x18000a70c`
- `0x18000e2d4`
- `0x18000fbf8`
- `0x1800107a0`
- `0x1800187e0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000691d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000691d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800069a7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800069a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006829`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006829`

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
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x18000677c  push    rbp
0x18000677e  push    rbx
0x18000677f  push    rsi
0x180006780  push    rdi
0x180006781  push    r12
0x180006783  push    r14
0x180006785  push    r15
0x180006787  lea     rbp, [rsp-13D0h]
0x18000678f  mov     eax, 14D0h
0x180006794  call    _alloca_probe
0x180006799  sub     rsp, rax
0x18000679c  mov     rax, cs:__security_cookie
0x1800067a3  xor     rax, rsp
0x1800067a6  mov     [rbp+1400h+var_40], rax
0x1800067ad  mov     rdi, [rbp+1400h+arg_28]
0x1800067b4  mov     r14, r8
0x1800067b7  mov     esi, edx
0x1800067b9  mov     r15, rcx
0x1800067bc  xor     edx, edx; Val
0x1800067be  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800067c3  mov     r8d, 98h; Size
0x1800067c9  call    memset_0
0x1800067ce  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800067d5  xor     r12d, r12d
0x1800067d8  mov     [rbp+1400h+OutputString], r12w
0x1800067e0  mov     [rbp+1400h+var_1440], r12b
0x1800067e4  mov     ecx, [rdx]; this
0x1800067e6  mov     eax, [rdx+4]
0x1800067e9  mov     [rsp+1500h+var_14D8], ecx
0x1800067ed  mov     [rsp+1500h+var_14D4], eax
0x1800067f1  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800067f6  cmp     dword ptr [rdx+8], 1
0x1800067fa  mov     ebx, eax
0x1800067fc  lea     eax, [r12+8]
0x180006801  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180006809  mov     ecx, r12d
0x18000680c  cmovz   ecx, eax
0x18000680f  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180006813  lea     ecx, [rax-7]
0x180006816  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000681e  inc     ecx
0x180006820  mov     [rsp+1500h+var_14C8], r12
0x180006825  mov     [rsp+1500h+var_14D0], ecx
0x180006829  call    cs:__imp_GetCurrentThreadId
0x18000682f  xorps   xmm0, xmm0
0x180006832  mov     [rsp+1500h+var_14A8], r14
0x180006837  mov     [rsp+1500h+var_14C0], eax
0x18000683b  xorps   xmm1, xmm1
0x18000683e  xor     eax, eax
0x180006840  mov     [rsp+1500h+var_14A0], esi
0x180006844  mov     [rbp+1400h+var_1468], rax
0x180006848  mov     [rbp+1400h+var_1480], rax
0x18000684c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006853  mov     [rsp+1500h+var_149C], ebx
0x180006857  mov     [rsp+1500h+var_14B8], r12
0x18000685c  mov     [rsp+1500h+var_14B0], r12
0x180006861  mov     [rbp+1400h+var_1458], rdi
0x180006865  mov     [rbp+1400h+var_1450], r15
0x180006869  mov     [rsp+1500h+var_1498], r12
0x18000686e  movups  [rbp+1400h+var_1478], xmm0
0x180006872  movups  [rsp+1500h+var_1490], xmm1
0x180006877  test    rax, rax
0x18000687a  jz      short loc_180006887
0x18000687c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006881  mov     [rbp+1400h+var_1460], rax
0x180006885  jmp     short loc_18000688B
0x180006887  mov     [rbp+1400h+var_1460], r12
0x18000688b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006892  test    rax, rax
0x180006895  jz      short loc_1800068A1
0x180006897  lea     rcx, [rsp+1500h+var_14E0]
0x18000689c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068a1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800068a8  test    rax, rax
0x1800068ab  jz      short loc_1800068C1
0x1800068ad  mov     r8d, 400h
0x1800068b3  lea     rdx, [rbp+1400h+var_1440]
0x1800068b7  lea     rcx, [rsp+1500h+var_14E0]
0x1800068bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068c1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800068c8  test    rax, rax
0x1800068cb  jz      short loc_1800068D7
0x1800068cd  lea     rcx, [rsp+1500h+var_14E0]
0x1800068d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068d7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800068de  test    rax, rax
0x1800068e1  jz      short loc_1800068F4
0x1800068e3  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800068e8  jnz     short loc_1800068F4
0x1800068ea  lea     rcx, [rsp+1500h+var_14E0]
0x1800068ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068f4  cmp     [rsp+1500h+var_14D8], r12d
0x1800068f9  jge     loc_1800069F6
0x1800068ff  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180006906  jnz     short loc_180006927
0x180006908  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000690f  test    rax, rax
0x180006912  jz      short loc_18000691D
0x180006914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006919  test    al, al
0x18000691b  jmp     short loc_180006925
0x18000691d  call    cs:__imp_IsDebuggerPresent
0x180006923  test    eax, eax
0x180006925  jz      short loc_18000692E
0x180006927  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000692c  jz      short loc_180006954
0x18000692e  mov     rax, cs:g_pfnResultLoggingCallback
0x180006935  test    rax, rax
0x180006938  jz      short loc_1800069AD
0x18000693a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180006941  jnz     short loc_1800069AD
0x180006943  xor     r8d, r8d
0x180006946  lea     rcx, [rsp+1500h+var_14E0]
0x18000694b  xor     edx, edx
0x18000694d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006952  jmp     short loc_1800069AD
0x180006954  mov     rax, cs:g_pfnResultLoggingCallback
0x18000695b  mov     ebx, 800h
0x180006960  test    rax, rax
0x180006963  jz      short loc_180006982
0x180006965  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000696c  jnz     short loc_180006982
0x18000696e  mov     r8d, ebx
0x180006971  lea     rdx, [rbp+1400h+OutputString]
0x180006978  lea     rcx, [rsp+1500h+var_14E0]
0x18000697d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006982  cmp     [rbp+1400h+OutputString], r12w
0x18000698a  jnz     short loc_1800069A0
0x18000698c  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180006991  mov     rdx, rbx; unsigned __int16 *
0x180006994  lea     rcx, [rbp+1400h+OutputString]; this
0x18000699b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800069a0  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800069a7  call    cs:__imp_OutputDebugStringW
0x1800069ad  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800069b2  jnz     short loc_1800069BD
0x1800069b4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800069bb  jz      short loc_1800069CE
0x1800069bd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800069c4  test    rax, rax
0x1800069c7  jz      short loc_1800069CE
0x1800069c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069ce  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800069d3  jnz     short loc_1800069FC
0x1800069d5  mov     rcx, [rbp+1400h+var_40]
0x1800069dc  xor     rcx, rsp; StackCookie
0x1800069df  call    __security_check_cookie
0x1800069e4  add     rsp, 14D0h
0x1800069eb  pop     r15
0x1800069ed  pop     r14
0x1800069ef  pop     r12
0x1800069f1  pop     rdi
0x1800069f2  pop     rsi
0x1800069f3  pop     rbx
0x1800069f4  pop     rbp
0x1800069f5  retn
0x1800069f6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800069fc  lea     rcx, [rsp+1500h+var_14E0]; this
0x180006a01  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
