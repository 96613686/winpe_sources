# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800055c0`
- end: `0x180005866`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005274`

## callees

- `0x180003980`
- `0x180004344`
- `0x1800055c0`
- `0x180005dc8`
- `0x180006710`
- `0x180006d68`
- `0x180006e44`
- `0x180031d20`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005686`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005686`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000577b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000577b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005805`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005805`

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
    wil::details::in1diag3::FailFastImmediate_Unexpected(v15);
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
0x1800055c0  push    rbp
0x1800055c2  push    rbx
0x1800055c3  push    rsi
0x1800055c4  push    rdi
0x1800055c5  push    r12
0x1800055c7  push    r14
0x1800055c9  push    r15
0x1800055cb  lea     rbp, [rsp-13D0h]
0x1800055d3  mov     eax, 14D0h
0x1800055d8  call    _alloca_probe
0x1800055dd  sub     rsp, rax
0x1800055e0  mov     rax, cs:__security_cookie
0x1800055e7  xor     rax, rsp
0x1800055ea  mov     [rbp+1400h+var_40], rax
0x1800055f1  mov     rsi, r8
0x1800055f4  mov     edi, edx
0x1800055f6  mov     rbx, rcx
0x1800055f9  mov     r14, [rbp+1400h+arg_28]
0x180005600  xor     edx, edx; Val
0x180005602  mov     r8d, 98h; Size
0x180005608  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000560d  call    memset_0
0x180005612  nop
0x180005613  xor     r12d, r12d
0x180005616  mov     [rbp+1400h+OutputString], r12w
0x18000561e  mov     [rbp+1400h+var_1440], r12b
0x180005622  mov     rdx, [rbp+1400h+arg_30]; int
0x180005629  mov     ecx, [rdx]; this
0x18000562b  mov     [rsp+1500h+var_14D8], ecx
0x18000562f  mov     eax, [rdx+4]
0x180005632  mov     [rsp+1500h+var_14D4], eax
0x180005636  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000563b  mov     r15d, eax
0x18000563e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005646  mov     ecx, r12d
0x180005649  lea     eax, [r12+8]
0x18000564e  cmp     dword ptr [rdx+8], 1
0x180005652  cmovz   ecx, eax
0x180005655  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005659  lea     ecx, [rax-7]
0x18000565c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005664  inc     ecx
0x180005666  mov     [rsp+1500h+var_14D0], ecx
0x18000566a  mov     rcx, [rbp+1400h+arg_38]
0x180005671  test    rcx, rcx
0x180005674  jz      short loc_180005681
0x180005676  cmp     [rcx], r12w
0x18000567a  mov     [rsp+1500h+var_14C8], rcx
0x18000567f  jnz     short loc_180005686
0x180005681  mov     [rsp+1500h+var_14C8], r12
0x180005686  call    cs:__imp_GetCurrentThreadId
0x18000568c  mov     [rsp+1500h+var_14C0], eax
0x180005690  mov     [rsp+1500h+var_14A8], rsi
0x180005695  mov     [rsp+1500h+var_14A0], edi
0x180005699  mov     [rsp+1500h+var_149C], r15d
0x18000569e  mov     [rsp+1500h+var_14B8], r12
0x1800056a3  mov     [rsp+1500h+var_14B0], r12
0x1800056a8  mov     [rbp+1400h+var_1458], r14
0x1800056ac  mov     [rbp+1400h+var_1450], rbx
0x1800056b0  mov     [rsp+1500h+var_1498], r12
0x1800056b5  xorps   xmm0, xmm0
0x1800056b8  xor     eax, eax
0x1800056ba  movups  [rbp+1400h+var_1478], xmm0
0x1800056be  mov     [rbp+1400h+var_1468], rax
0x1800056c2  xorps   xmm1, xmm1
0x1800056c5  movups  [rsp+1500h+var_1490], xmm1
0x1800056ca  mov     [rbp+1400h+var_1480], rax
0x1800056ce  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800056d5  test    rax, rax
0x1800056d8  jz      short loc_1800056E5
0x1800056da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056df  mov     [rbp+1400h+var_1460], rax
0x1800056e3  jmp     short loc_1800056E9
0x1800056e5  mov     [rbp+1400h+var_1460], r12
0x1800056e9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800056f0  test    rax, rax
0x1800056f3  jz      short loc_1800056FF
0x1800056f5  lea     rcx, [rsp+1500h+var_14E0]
0x1800056fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ff  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005706  test    rax, rax
0x180005709  jz      short loc_18000571F
0x18000570b  mov     r8d, 400h
0x180005711  lea     rdx, [rbp+1400h+var_1440]
0x180005715  lea     rcx, [rsp+1500h+var_14E0]
0x18000571a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000571f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005726  test    rax, rax
0x180005729  jz      short loc_180005735
0x18000572b  lea     rcx, [rsp+1500h+var_14E0]
0x180005730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005735  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000573c  test    rax, rax
0x18000573f  jz      short loc_180005752
0x180005741  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005746  jnz     short loc_180005752
0x180005748  lea     rcx, [rsp+1500h+var_14E0]
0x18000574d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005752  cmp     [rsp+1500h+var_14D8], r12d
0x180005757  jge     loc_180005860
0x18000575d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005764  jnz     short loc_180005785
0x180005766  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000576d  test    rax, rax
0x180005770  jz      short loc_18000577B
0x180005772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005777  test    al, al
0x180005779  jmp     short loc_180005783
0x18000577b  call    cs:__imp_IsDebuggerPresent
0x180005781  test    eax, eax
0x180005783  jz      short loc_18000578C
0x180005785  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000578a  jz      short loc_1800057B2
0x18000578c  mov     rax, cs:g_pfnResultLoggingCallback
0x180005793  test    rax, rax
0x180005796  jz      short loc_18000580B
0x180005798  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000579f  jnz     short loc_18000580B
0x1800057a1  xor     r8d, r8d
0x1800057a4  xor     edx, edx
0x1800057a6  lea     rcx, [rsp+1500h+var_14E0]
0x1800057ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057b0  jmp     short loc_18000580B
0x1800057b2  mov     ebx, 800h
0x1800057b7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800057be  test    rax, rax
0x1800057c1  jz      short loc_1800057E0
0x1800057c3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800057ca  jnz     short loc_1800057E0
0x1800057cc  mov     r8d, ebx
0x1800057cf  lea     rdx, [rbp+1400h+OutputString]
0x1800057d6  lea     rcx, [rsp+1500h+var_14E0]
0x1800057db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057e0  cmp     [rbp+1400h+OutputString], r12w
0x1800057e8  jnz     short loc_1800057FE
0x1800057ea  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800057ef  mov     rdx, rbx; unsigned __int16 *
0x1800057f2  lea     rcx, [rbp+1400h+OutputString]; this
0x1800057f9  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800057fe  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180005805  call    cs:__imp_OutputDebugStringW
0x18000580b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180005810  jnz     short loc_18000581B
0x180005812  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180005819  jz      short loc_18000582D
0x18000581b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005822  test    rax, rax
0x180005825  jz      short loc_18000582D
0x180005827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000582c  nop
0x18000582d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005832  jnz     short loc_180005855
0x180005834  mov     rcx, [rbp+1400h+var_40]
0x18000583b  xor     rcx, rsp; StackCookie
0x18000583e  call    __security_check_cookie
0x180005843  add     rsp, 14D0h
0x18000584a  pop     r15
0x18000584c  pop     r14
0x18000584e  pop     r12
0x180005850  pop     rdi
0x180005851  pop     rsi
0x180005852  pop     rbx
0x180005853  pop     rbp
0x180005854  retn
0x180005855  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000585a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005860  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
