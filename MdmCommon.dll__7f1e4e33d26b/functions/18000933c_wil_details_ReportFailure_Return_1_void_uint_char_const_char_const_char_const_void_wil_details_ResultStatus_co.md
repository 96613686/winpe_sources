# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000933c`
- end: `0x1800095e2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008e70`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x18000933c`
- `0x180009868`
- `0x18000aa60`
- `0x18000aa9c`
- `0x18000ab78`
- `0x18001d4b0`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009402`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009402`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009581`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009581`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800094f7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800094f7`

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
0x18000933c  push    rbp
0x18000933e  push    rbx
0x18000933f  push    rsi
0x180009340  push    rdi
0x180009341  push    r12
0x180009343  push    r14
0x180009345  push    r15
0x180009347  lea     rbp, [rsp-13D0h]
0x18000934f  mov     eax, 14D0h
0x180009354  call    _alloca_probe
0x180009359  sub     rsp, rax
0x18000935c  mov     rax, cs:__security_cookie
0x180009363  xor     rax, rsp
0x180009366  mov     [rbp+1400h+var_40], rax
0x18000936d  mov     rsi, r8
0x180009370  mov     edi, edx
0x180009372  mov     rbx, rcx
0x180009375  mov     r14, [rbp+1400h+arg_28]
0x18000937c  xor     edx, edx; Val
0x18000937e  mov     r8d, 98h; Size
0x180009384  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180009389  call    memset_0
0x18000938e  nop
0x18000938f  xor     r12d, r12d
0x180009392  mov     [rbp+1400h+OutputString], r12w
0x18000939a  mov     [rbp+1400h+var_1440], r12b
0x18000939e  mov     rdx, [rbp+1400h+arg_30]; int
0x1800093a5  mov     ecx, [rdx]; this
0x1800093a7  mov     [rsp+1500h+var_14D8], ecx
0x1800093ab  mov     eax, [rdx+4]
0x1800093ae  mov     [rsp+1500h+var_14D4], eax
0x1800093b2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800093b7  mov     r15d, eax
0x1800093ba  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800093c2  mov     ecx, r12d
0x1800093c5  lea     eax, [r12+8]
0x1800093ca  cmp     dword ptr [rdx+8], 1
0x1800093ce  cmovz   ecx, eax
0x1800093d1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800093d5  lea     ecx, [rax-7]
0x1800093d8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800093e0  inc     ecx
0x1800093e2  mov     [rsp+1500h+var_14D0], ecx
0x1800093e6  mov     rcx, [rbp+1400h+arg_38]
0x1800093ed  test    rcx, rcx
0x1800093f0  jz      short loc_1800093FD
0x1800093f2  cmp     [rcx], r12w
0x1800093f6  mov     [rsp+1500h+var_14C8], rcx
0x1800093fb  jnz     short loc_180009402
0x1800093fd  mov     [rsp+1500h+var_14C8], r12
0x180009402  call    cs:__imp_GetCurrentThreadId
0x180009408  mov     [rsp+1500h+var_14C0], eax
0x18000940c  mov     [rsp+1500h+var_14A8], rsi
0x180009411  mov     [rsp+1500h+var_14A0], edi
0x180009415  mov     [rsp+1500h+var_149C], r15d
0x18000941a  mov     [rsp+1500h+var_14B8], r12
0x18000941f  mov     [rsp+1500h+var_14B0], r12
0x180009424  mov     [rbp+1400h+var_1458], r14
0x180009428  mov     [rbp+1400h+var_1450], rbx
0x18000942c  mov     [rsp+1500h+var_1498], r12
0x180009431  xorps   xmm0, xmm0
0x180009434  xor     eax, eax
0x180009436  movups  [rbp+1400h+var_1478], xmm0
0x18000943a  mov     [rbp+1400h+var_1468], rax
0x18000943e  xorps   xmm1, xmm1
0x180009441  movups  [rsp+1500h+var_1490], xmm1
0x180009446  mov     [rbp+1400h+var_1480], rax
0x18000944a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009451  test    rax, rax
0x180009454  jz      short loc_180009461
0x180009456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000945b  mov     [rbp+1400h+var_1460], rax
0x18000945f  jmp     short loc_180009465
0x180009461  mov     [rbp+1400h+var_1460], r12
0x180009465  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000946c  test    rax, rax
0x18000946f  jz      short loc_18000947B
0x180009471  lea     rcx, [rsp+1500h+var_14E0]
0x180009476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000947b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009482  test    rax, rax
0x180009485  jz      short loc_18000949B
0x180009487  mov     r8d, 400h
0x18000948d  lea     rdx, [rbp+1400h+var_1440]
0x180009491  lea     rcx, [rsp+1500h+var_14E0]
0x180009496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000949b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800094a2  test    rax, rax
0x1800094a5  jz      short loc_1800094B1
0x1800094a7  lea     rcx, [rsp+1500h+var_14E0]
0x1800094ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094b1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800094b8  test    rax, rax
0x1800094bb  jz      short loc_1800094CE
0x1800094bd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800094c2  jnz     short loc_1800094CE
0x1800094c4  lea     rcx, [rsp+1500h+var_14E0]
0x1800094c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094ce  cmp     [rsp+1500h+var_14D8], r12d
0x1800094d3  jge     loc_1800095DC
0x1800094d9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800094e0  jnz     short loc_180009501
0x1800094e2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800094e9  test    rax, rax
0x1800094ec  jz      short loc_1800094F7
0x1800094ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094f3  test    al, al
0x1800094f5  jmp     short loc_1800094FF
0x1800094f7  call    cs:__imp_IsDebuggerPresent
0x1800094fd  test    eax, eax
0x1800094ff  jz      short loc_180009508
0x180009501  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180009506  jz      short loc_18000952E
0x180009508  mov     rax, cs:g_pfnResultLoggingCallback
0x18000950f  test    rax, rax
0x180009512  jz      short loc_180009587
0x180009514  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000951b  jnz     short loc_180009587
0x18000951d  xor     r8d, r8d
0x180009520  xor     edx, edx
0x180009522  lea     rcx, [rsp+1500h+var_14E0]
0x180009527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000952c  jmp     short loc_180009587
0x18000952e  mov     ebx, 800h
0x180009533  mov     rax, cs:g_pfnResultLoggingCallback
0x18000953a  test    rax, rax
0x18000953d  jz      short loc_18000955C
0x18000953f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180009546  jnz     short loc_18000955C
0x180009548  mov     r8d, ebx
0x18000954b  lea     rdx, [rbp+1400h+OutputString]
0x180009552  lea     rcx, [rsp+1500h+var_14E0]
0x180009557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000955c  cmp     [rbp+1400h+OutputString], r12w
0x180009564  jnz     short loc_18000957A
0x180009566  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000956b  mov     rdx, rbx; unsigned __int16 *
0x18000956e  lea     rcx, [rbp+1400h+OutputString]; this
0x180009575  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000957a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180009581  call    cs:__imp_OutputDebugStringW
0x180009587  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000958c  jnz     short loc_180009597
0x18000958e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180009595  jz      short loc_1800095A9
0x180009597  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000959e  test    rax, rax
0x1800095a1  jz      short loc_1800095A9
0x1800095a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095a8  nop
0x1800095a9  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800095ae  jnz     short loc_1800095D1
0x1800095b0  mov     rcx, [rbp+1400h+var_40]
0x1800095b7  xor     rcx, rsp; StackCookie
0x1800095ba  call    __security_check_cookie
0x1800095bf  add     rsp, 14D0h
0x1800095c6  pop     r15
0x1800095c8  pop     r14
0x1800095ca  pop     r12
0x1800095cc  pop     rdi
0x1800095cd  pop     rsi
0x1800095ce  pop     rbx
0x1800095cf  pop     rbp
0x1800095d0  retn
0x1800095d1  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800095d6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800095dc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
