# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007414`
- end: `0x1800076ba`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800070a4`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x180007414`
- `0x180008444`
- `0x1800095a0`
- `0x18000a1d8`
- `0x18000a394`
- `0x1800893b0`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800074da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800074da`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800075cf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800075cf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007659`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007659`

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
0x180007414  push    rbp
0x180007416  push    rbx
0x180007417  push    rsi
0x180007418  push    rdi
0x180007419  push    r12
0x18000741b  push    r14
0x18000741d  push    r15
0x18000741f  lea     rbp, [rsp-13D0h]
0x180007427  mov     eax, 14D0h
0x18000742c  call    _alloca_probe
0x180007431  sub     rsp, rax
0x180007434  mov     rax, cs:__security_cookie
0x18000743b  xor     rax, rsp
0x18000743e  mov     [rbp+1400h+var_40], rax
0x180007445  mov     rsi, r8
0x180007448  mov     edi, edx
0x18000744a  mov     rbx, rcx
0x18000744d  mov     r14, [rbp+1400h+arg_28]
0x180007454  xor     edx, edx; Val
0x180007456  mov     r8d, 98h; Size
0x18000745c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180007461  call    memset_0
0x180007466  nop
0x180007467  xor     r12d, r12d
0x18000746a  mov     [rbp+1400h+OutputString], r12w
0x180007472  mov     [rbp+1400h+var_1440], r12b
0x180007476  mov     rdx, [rbp+1400h+arg_30]; int
0x18000747d  mov     ecx, [rdx]; this
0x18000747f  mov     [rsp+1500h+var_14D8], ecx
0x180007483  mov     eax, [rdx+4]
0x180007486  mov     [rsp+1500h+var_14D4], eax
0x18000748a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000748f  mov     r15d, eax
0x180007492  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000749a  mov     ecx, r12d
0x18000749d  lea     eax, [r12+8]
0x1800074a2  cmp     dword ptr [rdx+8], 1
0x1800074a6  cmovz   ecx, eax
0x1800074a9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800074ad  lea     ecx, [rax-7]
0x1800074b0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800074b8  inc     ecx
0x1800074ba  mov     [rsp+1500h+var_14D0], ecx
0x1800074be  mov     rcx, [rbp+1400h+arg_38]
0x1800074c5  test    rcx, rcx
0x1800074c8  jz      short loc_1800074D5
0x1800074ca  cmp     [rcx], r12w
0x1800074ce  mov     [rsp+1500h+var_14C8], rcx
0x1800074d3  jnz     short loc_1800074DA
0x1800074d5  mov     [rsp+1500h+var_14C8], r12
0x1800074da  call    cs:__imp_GetCurrentThreadId
0x1800074e0  mov     [rsp+1500h+var_14C0], eax
0x1800074e4  mov     [rsp+1500h+var_14A8], rsi
0x1800074e9  mov     [rsp+1500h+var_14A0], edi
0x1800074ed  mov     [rsp+1500h+var_149C], r15d
0x1800074f2  mov     [rsp+1500h+var_14B8], r12
0x1800074f7  mov     [rsp+1500h+var_14B0], r12
0x1800074fc  mov     [rbp+1400h+var_1458], r14
0x180007500  mov     [rbp+1400h+var_1450], rbx
0x180007504  mov     [rsp+1500h+var_1498], r12
0x180007509  xorps   xmm0, xmm0
0x18000750c  xor     eax, eax
0x18000750e  movups  [rbp+1400h+var_1478], xmm0
0x180007512  mov     [rbp+1400h+var_1468], rax
0x180007516  xorps   xmm1, xmm1
0x180007519  movups  [rsp+1500h+var_1490], xmm1
0x18000751e  mov     [rbp+1400h+var_1480], rax
0x180007522  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007529  test    rax, rax
0x18000752c  jz      short loc_180007539
0x18000752e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007533  mov     [rbp+1400h+var_1460], rax
0x180007537  jmp     short loc_18000753D
0x180007539  mov     [rbp+1400h+var_1460], r12
0x18000753d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007544  test    rax, rax
0x180007547  jz      short loc_180007553
0x180007549  lea     rcx, [rsp+1500h+var_14E0]
0x18000754e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007553  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000755a  test    rax, rax
0x18000755d  jz      short loc_180007573
0x18000755f  mov     r8d, 400h
0x180007565  lea     rdx, [rbp+1400h+var_1440]
0x180007569  lea     rcx, [rsp+1500h+var_14E0]
0x18000756e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007573  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000757a  test    rax, rax
0x18000757d  jz      short loc_180007589
0x18000757f  lea     rcx, [rsp+1500h+var_14E0]
0x180007584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007589  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007590  test    rax, rax
0x180007593  jz      short loc_1800075A6
0x180007595  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000759a  jnz     short loc_1800075A6
0x18000759c  lea     rcx, [rsp+1500h+var_14E0]
0x1800075a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075a6  cmp     [rsp+1500h+var_14D8], r12d
0x1800075ab  jge     loc_1800076B4
0x1800075b1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800075b8  jnz     short loc_1800075D9
0x1800075ba  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800075c1  test    rax, rax
0x1800075c4  jz      short loc_1800075CF
0x1800075c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075cb  test    al, al
0x1800075cd  jmp     short loc_1800075D7
0x1800075cf  call    cs:__imp_IsDebuggerPresent
0x1800075d5  test    eax, eax
0x1800075d7  jz      short loc_1800075E0
0x1800075d9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800075de  jz      short loc_180007606
0x1800075e0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800075e7  test    rax, rax
0x1800075ea  jz      short loc_18000765F
0x1800075ec  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800075f3  jnz     short loc_18000765F
0x1800075f5  xor     r8d, r8d
0x1800075f8  xor     edx, edx
0x1800075fa  lea     rcx, [rsp+1500h+var_14E0]
0x1800075ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007604  jmp     short loc_18000765F
0x180007606  mov     ebx, 800h
0x18000760b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007612  test    rax, rax
0x180007615  jz      short loc_180007634
0x180007617  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000761e  jnz     short loc_180007634
0x180007620  mov     r8d, ebx
0x180007623  lea     rdx, [rbp+1400h+OutputString]
0x18000762a  lea     rcx, [rsp+1500h+var_14E0]
0x18000762f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007634  cmp     [rbp+1400h+OutputString], r12w
0x18000763c  jnz     short loc_180007652
0x18000763e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180007643  mov     rdx, rbx; unsigned __int16 *
0x180007646  lea     rcx, [rbp+1400h+OutputString]; this
0x18000764d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007652  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180007659  call    cs:__imp_OutputDebugStringW
0x18000765f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180007664  jnz     short loc_18000766F
0x180007666  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000766d  jz      short loc_180007681
0x18000766f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007676  test    rax, rax
0x180007679  jz      short loc_180007681
0x18000767b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007680  nop
0x180007681  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180007686  jnz     short loc_1800076A9
0x180007688  mov     rcx, [rbp+1400h+var_40]
0x18000768f  xor     rcx, rsp; StackCookie
0x180007692  call    __security_check_cookie
0x180007697  add     rsp, 14D0h
0x18000769e  pop     r15
0x1800076a0  pop     r14
0x1800076a2  pop     r12
0x1800076a4  pop     rdi
0x1800076a5  pop     rsi
0x1800076a6  pop     rbx
0x1800076a7  pop     rbp
0x1800076a8  retn
0x1800076a9  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800076ae  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800076b4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
