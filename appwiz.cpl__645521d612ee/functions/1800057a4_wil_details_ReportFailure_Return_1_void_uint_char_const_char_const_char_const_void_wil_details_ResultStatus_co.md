# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800057a4`
- end: `0x180005a2f`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005468`

## callees

- `0x1800057a4`
- `0x180006434`
- `0x1800074b0`
- `0x180007d18`
- `0x180007ed4`
- `0x1800582a2`
- `0x1800582e0`
- `0x1800583a0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005851`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005851`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005945`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005945`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800059cf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800059cf`

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
0x1800057a4  push    rbp
0x1800057a6  push    rbx
0x1800057a7  push    rsi
0x1800057a8  push    rdi
0x1800057a9  push    r12
0x1800057ab  push    r14
0x1800057ad  push    r15
0x1800057af  lea     rbp, [rsp-13D0h]
0x1800057b7  mov     eax, 14D0h
0x1800057bc  call    _alloca_probe
0x1800057c1  sub     rsp, rax
0x1800057c4  mov     rax, cs:__security_cookie
0x1800057cb  xor     rax, rsp
0x1800057ce  mov     [rbp+1400h+var_40], rax
0x1800057d5  mov     rdi, [rbp+1400h+arg_28]
0x1800057dc  mov     r14, r8
0x1800057df  mov     esi, edx
0x1800057e1  mov     r15, rcx
0x1800057e4  xor     edx, edx; Val
0x1800057e6  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800057eb  mov     r8d, 98h; Size
0x1800057f1  call    memset_0
0x1800057f6  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800057fd  xor     r12d, r12d
0x180005800  mov     [rbp+1400h+OutputString], r12w
0x180005808  mov     [rbp+1400h+var_1440], r12b
0x18000580c  mov     ecx, [rdx]; this
0x18000580e  mov     eax, [rdx+4]
0x180005811  mov     [rsp+1500h+var_14D8], ecx
0x180005815  mov     [rsp+1500h+var_14D4], eax
0x180005819  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000581e  cmp     dword ptr [rdx+8], 1
0x180005822  mov     ebx, eax
0x180005824  lea     eax, [r12+8]
0x180005829  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005831  mov     ecx, r12d
0x180005834  cmovz   ecx, eax
0x180005837  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000583b  lea     ecx, [rax-7]
0x18000583e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005846  inc     ecx
0x180005848  mov     [rsp+1500h+var_14C8], r12
0x18000584d  mov     [rsp+1500h+var_14D0], ecx
0x180005851  call    cs:__imp_GetCurrentThreadId
0x180005857  xorps   xmm0, xmm0
0x18000585a  mov     [rsp+1500h+var_14A8], r14
0x18000585f  mov     [rsp+1500h+var_14C0], eax
0x180005863  xorps   xmm1, xmm1
0x180005866  xor     eax, eax
0x180005868  mov     [rsp+1500h+var_14A0], esi
0x18000586c  mov     [rbp+1400h+var_1468], rax
0x180005870  mov     [rbp+1400h+var_1480], rax
0x180005874  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000587b  mov     [rsp+1500h+var_149C], ebx
0x18000587f  mov     [rsp+1500h+var_14B8], r12
0x180005884  mov     [rsp+1500h+var_14B0], r12
0x180005889  mov     [rbp+1400h+var_1458], rdi
0x18000588d  mov     [rbp+1400h+var_1450], r15
0x180005891  mov     [rsp+1500h+var_1498], r12
0x180005896  movups  [rbp+1400h+var_1478], xmm0
0x18000589a  movups  [rsp+1500h+var_1490], xmm1
0x18000589f  test    rax, rax
0x1800058a2  jz      short loc_1800058AF
0x1800058a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058a9  mov     [rbp+1400h+var_1460], rax
0x1800058ad  jmp     short loc_1800058B3
0x1800058af  mov     [rbp+1400h+var_1460], r12
0x1800058b3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800058ba  test    rax, rax
0x1800058bd  jz      short loc_1800058C9
0x1800058bf  lea     rcx, [rsp+1500h+var_14E0]
0x1800058c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058c9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800058d0  test    rax, rax
0x1800058d3  jz      short loc_1800058E9
0x1800058d5  mov     r8d, 400h
0x1800058db  lea     rdx, [rbp+1400h+var_1440]
0x1800058df  lea     rcx, [rsp+1500h+var_14E0]
0x1800058e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058e9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800058f0  test    rax, rax
0x1800058f3  jz      short loc_1800058FF
0x1800058f5  lea     rcx, [rsp+1500h+var_14E0]
0x1800058fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058ff  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005906  test    rax, rax
0x180005909  jz      short loc_18000591C
0x18000590b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005910  jnz     short loc_18000591C
0x180005912  lea     rcx, [rsp+1500h+var_14E0]
0x180005917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000591c  cmp     [rsp+1500h+var_14D8], r12d
0x180005921  jge     loc_180005A1E
0x180005927  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000592e  jnz     short loc_18000594F
0x180005930  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005937  test    rax, rax
0x18000593a  jz      short loc_180005945
0x18000593c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005941  test    al, al
0x180005943  jmp     short loc_18000594D
0x180005945  call    cs:__imp_IsDebuggerPresent
0x18000594b  test    eax, eax
0x18000594d  jz      short loc_180005956
0x18000594f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005954  jz      short loc_18000597C
0x180005956  mov     rax, cs:g_pfnResultLoggingCallback
0x18000595d  test    rax, rax
0x180005960  jz      short loc_1800059D5
0x180005962  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005969  jnz     short loc_1800059D5
0x18000596b  xor     r8d, r8d
0x18000596e  lea     rcx, [rsp+1500h+var_14E0]
0x180005973  xor     edx, edx
0x180005975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000597a  jmp     short loc_1800059D5
0x18000597c  mov     rax, cs:g_pfnResultLoggingCallback
0x180005983  mov     ebx, 800h
0x180005988  test    rax, rax
0x18000598b  jz      short loc_1800059AA
0x18000598d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005994  jnz     short loc_1800059AA
0x180005996  mov     r8d, ebx
0x180005999  lea     rdx, [rbp+1400h+OutputString]
0x1800059a0  lea     rcx, [rsp+1500h+var_14E0]
0x1800059a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059aa  cmp     [rbp+1400h+OutputString], r12w
0x1800059b2  jnz     short loc_1800059C8
0x1800059b4  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800059b9  mov     rdx, rbx; unsigned __int16 *
0x1800059bc  lea     rcx, [rbp+1400h+OutputString]; this
0x1800059c3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800059c8  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800059cf  call    cs:__imp_OutputDebugStringW
0x1800059d5  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800059da  jnz     short loc_1800059E5
0x1800059dc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800059e3  jz      short loc_1800059F6
0x1800059e5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800059ec  test    rax, rax
0x1800059ef  jz      short loc_1800059F6
0x1800059f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059f6  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800059fb  jnz     short loc_180005A24
0x1800059fd  mov     rcx, [rbp+1400h+var_40]
0x180005a04  xor     rcx, rsp; StackCookie
0x180005a07  call    __security_check_cookie
0x180005a0c  add     rsp, 14D0h
0x180005a13  pop     r15
0x180005a15  pop     r14
0x180005a17  pop     r12
0x180005a19  pop     rdi
0x180005a1a  pop     rsi
0x180005a1b  pop     rbx
0x180005a1c  pop     rbp
0x180005a1d  retn
0x180005a1e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005a24  lea     rcx, [rsp+1500h+var_14E0]; this
0x180005a29  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
