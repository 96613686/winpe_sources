# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800056a4`
- end: `0x18000592f`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005374`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x1800056a4`
- `0x180006524`
- `0x1800076a0`
- `0x180007fe8`
- `0x1800080c4`
- `0x1800e91e0`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005751`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005751`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800058cf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800058cf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005845`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005845`

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
0x1800056a4  push    rbp
0x1800056a6  push    rbx
0x1800056a7  push    rsi
0x1800056a8  push    rdi
0x1800056a9  push    r12
0x1800056ab  push    r14
0x1800056ad  push    r15
0x1800056af  lea     rbp, [rsp-13D0h]
0x1800056b7  mov     eax, 14D0h
0x1800056bc  call    _alloca_probe
0x1800056c1  sub     rsp, rax
0x1800056c4  mov     rax, cs:__security_cookie
0x1800056cb  xor     rax, rsp
0x1800056ce  mov     [rbp+1400h+var_40], rax
0x1800056d5  mov     rdi, [rbp+1400h+arg_28]
0x1800056dc  mov     r14, r8
0x1800056df  mov     esi, edx
0x1800056e1  mov     r15, rcx
0x1800056e4  xor     edx, edx; Val
0x1800056e6  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800056eb  mov     r8d, 98h; Size
0x1800056f1  call    memset_0
0x1800056f6  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800056fd  xor     r12d, r12d
0x180005700  mov     [rbp+1400h+OutputString], r12w
0x180005708  mov     [rbp+1400h+var_1440], r12b
0x18000570c  mov     ecx, [rdx]; this
0x18000570e  mov     eax, [rdx+4]
0x180005711  mov     [rsp+1500h+var_14D8], ecx
0x180005715  mov     [rsp+1500h+var_14D4], eax
0x180005719  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000571e  cmp     dword ptr [rdx+8], 1
0x180005722  mov     ebx, eax
0x180005724  lea     eax, [r12+8]
0x180005729  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005731  mov     ecx, r12d
0x180005734  cmovz   ecx, eax
0x180005737  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000573b  lea     ecx, [rax-7]
0x18000573e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005746  inc     ecx
0x180005748  mov     [rsp+1500h+var_14C8], r12
0x18000574d  mov     [rsp+1500h+var_14D0], ecx
0x180005751  call    cs:__imp_GetCurrentThreadId
0x180005757  xorps   xmm0, xmm0
0x18000575a  mov     [rsp+1500h+var_14A8], r14
0x18000575f  mov     [rsp+1500h+var_14C0], eax
0x180005763  xorps   xmm1, xmm1
0x180005766  xor     eax, eax
0x180005768  mov     [rsp+1500h+var_14A0], esi
0x18000576c  mov     [rbp+1400h+var_1468], rax
0x180005770  mov     [rbp+1400h+var_1480], rax
0x180005774  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000577b  mov     [rsp+1500h+var_149C], ebx
0x18000577f  mov     [rsp+1500h+var_14B8], r12
0x180005784  mov     [rsp+1500h+var_14B0], r12
0x180005789  mov     [rbp+1400h+var_1458], rdi
0x18000578d  mov     [rbp+1400h+var_1450], r15
0x180005791  mov     [rsp+1500h+var_1498], r12
0x180005796  movups  [rbp+1400h+var_1478], xmm0
0x18000579a  movups  [rsp+1500h+var_1490], xmm1
0x18000579f  test    rax, rax
0x1800057a2  jz      short loc_1800057AF
0x1800057a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057a9  mov     [rbp+1400h+var_1460], rax
0x1800057ad  jmp     short loc_1800057B3
0x1800057af  mov     [rbp+1400h+var_1460], r12
0x1800057b3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800057ba  test    rax, rax
0x1800057bd  jz      short loc_1800057C9
0x1800057bf  lea     rcx, [rsp+1500h+var_14E0]
0x1800057c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057c9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800057d0  test    rax, rax
0x1800057d3  jz      short loc_1800057E9
0x1800057d5  mov     r8d, 400h
0x1800057db  lea     rdx, [rbp+1400h+var_1440]
0x1800057df  lea     rcx, [rsp+1500h+var_14E0]
0x1800057e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057e9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800057f0  test    rax, rax
0x1800057f3  jz      short loc_1800057FF
0x1800057f5  lea     rcx, [rsp+1500h+var_14E0]
0x1800057fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ff  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005806  test    rax, rax
0x180005809  jz      short loc_18000581C
0x18000580b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005810  jnz     short loc_18000581C
0x180005812  lea     rcx, [rsp+1500h+var_14E0]
0x180005817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000581c  cmp     [rsp+1500h+var_14D8], r12d
0x180005821  jge     loc_18000591E
0x180005827  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000582e  jnz     short loc_18000584F
0x180005830  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005837  test    rax, rax
0x18000583a  jz      short loc_180005845
0x18000583c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005841  test    al, al
0x180005843  jmp     short loc_18000584D
0x180005845  call    cs:__imp_IsDebuggerPresent
0x18000584b  test    eax, eax
0x18000584d  jz      short loc_180005856
0x18000584f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005854  jz      short loc_18000587C
0x180005856  mov     rax, cs:g_pfnResultLoggingCallback
0x18000585d  test    rax, rax
0x180005860  jz      short loc_1800058D5
0x180005862  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005869  jnz     short loc_1800058D5
0x18000586b  xor     r8d, r8d
0x18000586e  lea     rcx, [rsp+1500h+var_14E0]
0x180005873  xor     edx, edx
0x180005875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000587a  jmp     short loc_1800058D5
0x18000587c  mov     rax, cs:g_pfnResultLoggingCallback
0x180005883  mov     ebx, 800h
0x180005888  test    rax, rax
0x18000588b  jz      short loc_1800058AA
0x18000588d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005894  jnz     short loc_1800058AA
0x180005896  mov     r8d, ebx
0x180005899  lea     rdx, [rbp+1400h+OutputString]
0x1800058a0  lea     rcx, [rsp+1500h+var_14E0]
0x1800058a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058aa  cmp     [rbp+1400h+OutputString], r12w
0x1800058b2  jnz     short loc_1800058C8
0x1800058b4  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800058b9  mov     rdx, rbx; unsigned __int16 *
0x1800058bc  lea     rcx, [rbp+1400h+OutputString]; this
0x1800058c3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800058c8  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800058cf  call    cs:__imp_OutputDebugStringW
0x1800058d5  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800058da  jnz     short loc_1800058E5
0x1800058dc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800058e3  jz      short loc_1800058F6
0x1800058e5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800058ec  test    rax, rax
0x1800058ef  jz      short loc_1800058F6
0x1800058f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058f6  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800058fb  jnz     short loc_180005924
0x1800058fd  mov     rcx, [rbp+1400h+var_40]
0x180005904  xor     rcx, rsp; StackCookie
0x180005907  call    __security_check_cookie
0x18000590c  add     rsp, 14D0h
0x180005913  pop     r15
0x180005915  pop     r14
0x180005917  pop     r12
0x180005919  pop     rdi
0x18000591a  pop     rsi
0x18000591b  pop     rbx
0x18000591c  pop     rbp
0x18000591d  retn
0x18000591e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005924  lea     rcx, [rsp+1500h+var_14E0]; this
0x180005929  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
