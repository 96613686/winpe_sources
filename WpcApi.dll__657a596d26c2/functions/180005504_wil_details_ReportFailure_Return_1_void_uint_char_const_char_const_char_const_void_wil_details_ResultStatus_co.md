# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005504`
- end: `0x1800057aa`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004f90`

## callees

- `0x1800032a0`
- `0x180003d14`
- `0x180005504`
- `0x1800076e4`
- `0x180008f20`
- `0x18000a4f0`
- `0x18000a8dc`
- `0x180028fe0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055ca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800056bf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800056bf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005749`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005749`

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
0x180005504  push    rbp
0x180005506  push    rbx
0x180005507  push    rsi
0x180005508  push    rdi
0x180005509  push    r12
0x18000550b  push    r14
0x18000550d  push    r15
0x18000550f  lea     rbp, [rsp-13D0h]
0x180005517  mov     eax, 14D0h
0x18000551c  call    _alloca_probe
0x180005521  sub     rsp, rax
0x180005524  mov     rax, cs:__security_cookie
0x18000552b  xor     rax, rsp
0x18000552e  mov     [rbp+1400h+var_40], rax
0x180005535  mov     rsi, r8
0x180005538  mov     edi, edx
0x18000553a  mov     rbx, rcx
0x18000553d  mov     r14, [rbp+1400h+arg_28]
0x180005544  xor     edx, edx; Val
0x180005546  mov     r8d, 98h; Size
0x18000554c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180005551  call    memset_0
0x180005556  nop
0x180005557  xor     r12d, r12d
0x18000555a  mov     [rbp+1400h+OutputString], r12w
0x180005562  mov     [rbp+1400h+var_1440], r12b
0x180005566  mov     rdx, [rbp+1400h+arg_30]; int
0x18000556d  mov     ecx, [rdx]; this
0x18000556f  mov     [rsp+1500h+var_14D8], ecx
0x180005573  mov     eax, [rdx+4]
0x180005576  mov     [rsp+1500h+var_14D4], eax
0x18000557a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000557f  mov     r15d, eax
0x180005582  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000558a  mov     ecx, r12d
0x18000558d  lea     eax, [r12+8]
0x180005592  cmp     dword ptr [rdx+8], 1
0x180005596  cmovz   ecx, eax
0x180005599  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000559d  lea     ecx, [rax-7]
0x1800055a0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800055a8  inc     ecx
0x1800055aa  mov     [rsp+1500h+var_14D0], ecx
0x1800055ae  mov     rcx, [rbp+1400h+arg_38]
0x1800055b5  test    rcx, rcx
0x1800055b8  jz      short loc_1800055C5
0x1800055ba  cmp     [rcx], r12w
0x1800055be  mov     [rsp+1500h+var_14C8], rcx
0x1800055c3  jnz     short loc_1800055CA
0x1800055c5  mov     [rsp+1500h+var_14C8], r12
0x1800055ca  call    cs:__imp_GetCurrentThreadId
0x1800055d0  mov     [rsp+1500h+var_14C0], eax
0x1800055d4  mov     [rsp+1500h+var_14A8], rsi
0x1800055d9  mov     [rsp+1500h+var_14A0], edi
0x1800055dd  mov     [rsp+1500h+var_149C], r15d
0x1800055e2  mov     [rsp+1500h+var_14B8], r12
0x1800055e7  mov     [rsp+1500h+var_14B0], r12
0x1800055ec  mov     [rbp+1400h+var_1458], r14
0x1800055f0  mov     [rbp+1400h+var_1450], rbx
0x1800055f4  mov     [rsp+1500h+var_1498], r12
0x1800055f9  xorps   xmm0, xmm0
0x1800055fc  xor     eax, eax
0x1800055fe  movups  [rbp+1400h+var_1478], xmm0
0x180005602  mov     [rbp+1400h+var_1468], rax
0x180005606  xorps   xmm1, xmm1
0x180005609  movups  [rsp+1500h+var_1490], xmm1
0x18000560e  mov     [rbp+1400h+var_1480], rax
0x180005612  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005619  test    rax, rax
0x18000561c  jz      short loc_180005629
0x18000561e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005623  mov     [rbp+1400h+var_1460], rax
0x180005627  jmp     short loc_18000562D
0x180005629  mov     [rbp+1400h+var_1460], r12
0x18000562d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005634  test    rax, rax
0x180005637  jz      short loc_180005643
0x180005639  lea     rcx, [rsp+1500h+var_14E0]
0x18000563e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005643  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000564a  test    rax, rax
0x18000564d  jz      short loc_180005663
0x18000564f  mov     r8d, 400h
0x180005655  lea     rdx, [rbp+1400h+var_1440]
0x180005659  lea     rcx, [rsp+1500h+var_14E0]
0x18000565e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005663  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000566a  test    rax, rax
0x18000566d  jz      short loc_180005679
0x18000566f  lea     rcx, [rsp+1500h+var_14E0]
0x180005674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005679  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005680  test    rax, rax
0x180005683  jz      short loc_180005696
0x180005685  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000568a  jnz     short loc_180005696
0x18000568c  lea     rcx, [rsp+1500h+var_14E0]
0x180005691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005696  cmp     [rsp+1500h+var_14D8], r12d
0x18000569b  jge     loc_1800057A4
0x1800056a1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800056a8  jnz     short loc_1800056C9
0x1800056aa  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800056b1  test    rax, rax
0x1800056b4  jz      short loc_1800056BF
0x1800056b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056bb  test    al, al
0x1800056bd  jmp     short loc_1800056C7
0x1800056bf  call    cs:__imp_IsDebuggerPresent
0x1800056c5  test    eax, eax
0x1800056c7  jz      short loc_1800056D0
0x1800056c9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800056ce  jz      short loc_1800056F6
0x1800056d0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800056d7  test    rax, rax
0x1800056da  jz      short loc_18000574F
0x1800056dc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800056e3  jnz     short loc_18000574F
0x1800056e5  xor     r8d, r8d
0x1800056e8  xor     edx, edx
0x1800056ea  lea     rcx, [rsp+1500h+var_14E0]
0x1800056ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056f4  jmp     short loc_18000574F
0x1800056f6  mov     ebx, 800h
0x1800056fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180005702  test    rax, rax
0x180005705  jz      short loc_180005724
0x180005707  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000570e  jnz     short loc_180005724
0x180005710  mov     r8d, ebx
0x180005713  lea     rdx, [rbp+1400h+OutputString]
0x18000571a  lea     rcx, [rsp+1500h+var_14E0]
0x18000571f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005724  cmp     [rbp+1400h+OutputString], r12w
0x18000572c  jnz     short loc_180005742
0x18000572e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180005733  mov     rdx, rbx; unsigned __int16 *
0x180005736  lea     rcx, [rbp+1400h+OutputString]; this
0x18000573d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005742  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180005749  call    cs:__imp_OutputDebugStringW
0x18000574f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180005754  jnz     short loc_18000575F
0x180005756  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000575d  jz      short loc_180005771
0x18000575f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005766  test    rax, rax
0x180005769  jz      short loc_180005771
0x18000576b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005770  nop
0x180005771  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005776  jnz     short loc_180005799
0x180005778  mov     rcx, [rbp+1400h+var_40]
0x18000577f  xor     rcx, rsp; StackCookie
0x180005782  call    __security_check_cookie
0x180005787  add     rsp, 14D0h
0x18000578e  pop     r15
0x180005790  pop     r14
0x180005792  pop     r12
0x180005794  pop     rdi
0x180005795  pop     rsi
0x180005796  pop     rbx
0x180005797  pop     rbp
0x180005798  retn
0x180005799  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000579e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800057a4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
