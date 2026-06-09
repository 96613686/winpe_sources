# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140005840`
- end: `0x140005aee`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `686`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400054c4`

## callees

- `0x1400030a0`
- `0x140003c74`
- `0x140005840`
- `0x140007874`
- `0x1400095fc`
- `0x14000b248`
- `0x14000b524`
- `0x140049bf0`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000590e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000590e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005a8d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005a8d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005a03`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005a03`

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
  __int64 v38; // [rsp+C0h] [rbp-40h]
  char v39[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v38 = -2;
  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
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
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v39, 1024);
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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
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
0x140005840  push    rbp
0x140005842  push    rbx
0x140005843  push    rsi
0x140005844  push    rdi
0x140005845  push    r12
0x140005847  push    r14
0x140005849  push    r15
0x14000584b  lea     rbp, [rsp-13E0h]
0x140005853  mov     eax, 14E0h
0x140005858  call    _alloca_probe
0x14000585d  sub     rsp, rax
0x140005860  mov     [rbp+1410h+var_1450], 0FFFFFFFFFFFFFFFEh
0x140005868  mov     rax, cs:__security_cookie
0x14000586f  xor     rax, rsp
0x140005872  mov     [rbp+1410h+var_40], rax
0x140005879  mov     rsi, r8
0x14000587c  mov     edi, edx
0x14000587e  mov     rbx, rcx
0x140005881  mov     r14, [rbp+1410h+arg_28]
0x140005888  xor     edx, edx; Val
0x14000588a  mov     r8d, 98h; Size
0x140005890  lea     rcx, [rsp+1510h+var_14F0]; void *
0x140005895  call    memset_0
0x14000589a  nop
0x14000589b  xor     r12d, r12d
0x14000589e  mov     [rbp+1410h+OutputString], r12w
0x1400058a6  mov     [rbp+1410h+var_1440], r12b
0x1400058aa  mov     rdx, [rbp+1410h+arg_30]; int
0x1400058b1  mov     ecx, [rdx]; this
0x1400058b3  mov     [rsp+1510h+var_14E8], ecx
0x1400058b7  mov     eax, [rdx+4]
0x1400058ba  mov     [rsp+1510h+var_14E4], eax
0x1400058be  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400058c3  mov     r15d, eax
0x1400058c6  mov     dword ptr [rsp+1510h+var_14F0], 1
0x1400058ce  mov     ecx, r12d
0x1400058d1  lea     eax, [r12+8]
0x1400058d6  cmp     dword ptr [rdx+8], 1
0x1400058da  cmovz   ecx, eax
0x1400058dd  mov     dword ptr [rsp+1510h+var_14F0+4], ecx
0x1400058e1  lea     ecx, [rax-7]
0x1400058e4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400058ec  inc     ecx
0x1400058ee  mov     [rsp+1510h+var_14E0], ecx
0x1400058f2  mov     rcx, [rbp+1410h+arg_38]
0x1400058f9  test    rcx, rcx
0x1400058fc  jz      short loc_140005909
0x1400058fe  cmp     [rcx], r12w
0x140005902  mov     [rsp+1510h+var_14D8], rcx
0x140005907  jnz     short loc_14000590E
0x140005909  mov     [rsp+1510h+var_14D8], r12
0x14000590e  call    cs:__imp_GetCurrentThreadId
0x140005914  mov     [rsp+1510h+var_14D0], eax
0x140005918  mov     [rsp+1510h+var_14B8], rsi
0x14000591d  mov     [rsp+1510h+var_14B0], edi
0x140005921  mov     [rsp+1510h+var_14AC], r15d
0x140005926  mov     [rsp+1510h+var_14C8], r12
0x14000592b  mov     [rsp+1510h+var_14C0], r12
0x140005930  mov     [rbp+1410h+var_1468], r14
0x140005934  mov     [rbp+1410h+var_1460], rbx
0x140005938  mov     [rsp+1510h+var_14A8], r12
0x14000593d  xorps   xmm0, xmm0
0x140005940  xor     eax, eax
0x140005942  movups  [rbp+1410h+var_1488], xmm0
0x140005946  mov     [rbp+1410h+var_1478], rax
0x14000594a  xorps   xmm1, xmm1
0x14000594d  movups  [rsp+1510h+var_14A0], xmm1
0x140005952  mov     [rbp+1410h+var_1490], rax
0x140005956  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000595d  test    rax, rax
0x140005960  jz      short loc_14000596D
0x140005962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005967  mov     [rbp+1410h+var_1470], rax
0x14000596b  jmp     short loc_140005971
0x14000596d  mov     [rbp+1410h+var_1470], r12
0x140005971  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140005978  test    rax, rax
0x14000597b  jz      short loc_140005987
0x14000597d  lea     rcx, [rsp+1510h+var_14F0]
0x140005982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005987  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000598e  test    rax, rax
0x140005991  jz      short loc_1400059A7
0x140005993  mov     r8d, 400h
0x140005999  lea     rdx, [rbp+1410h+var_1440]
0x14000599d  lea     rcx, [rsp+1510h+var_14F0]
0x1400059a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059a7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400059ae  test    rax, rax
0x1400059b1  jz      short loc_1400059BD
0x1400059b3  lea     rcx, [rsp+1510h+var_14F0]
0x1400059b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059bd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400059c4  test    rax, rax
0x1400059c7  jz      short loc_1400059DA
0x1400059c9  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x1400059ce  jnz     short loc_1400059DA
0x1400059d0  lea     rcx, [rsp+1510h+var_14F0]
0x1400059d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059da  cmp     [rsp+1510h+var_14E8], r12d
0x1400059df  jge     loc_140005AE8
0x1400059e5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400059ec  jnz     short loc_140005A0D
0x1400059ee  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400059f5  test    rax, rax
0x1400059f8  jz      short loc_140005A03
0x1400059fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059ff  test    al, al
0x140005a01  jmp     short loc_140005A0B
0x140005a03  call    cs:__imp_IsDebuggerPresent
0x140005a09  test    eax, eax
0x140005a0b  jz      short loc_140005A14
0x140005a0d  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x140005a12  jz      short loc_140005A3A
0x140005a14  mov     rax, cs:g_pfnResultLoggingCallback
0x140005a1b  test    rax, rax
0x140005a1e  jz      short loc_140005A93
0x140005a20  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140005a27  jnz     short loc_140005A93
0x140005a29  xor     r8d, r8d
0x140005a2c  xor     edx, edx
0x140005a2e  lea     rcx, [rsp+1510h+var_14F0]
0x140005a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a38  jmp     short loc_140005A93
0x140005a3a  mov     ebx, 800h
0x140005a3f  mov     rax, cs:g_pfnResultLoggingCallback
0x140005a46  test    rax, rax
0x140005a49  jz      short loc_140005A68
0x140005a4b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140005a52  jnz     short loc_140005A68
0x140005a54  mov     r8d, ebx
0x140005a57  lea     rdx, [rbp+1410h+OutputString]
0x140005a5e  lea     rcx, [rsp+1510h+var_14F0]
0x140005a63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a68  cmp     [rbp+1410h+OutputString], r12w
0x140005a70  jnz     short loc_140005A86
0x140005a72  lea     r8, [rsp+1510h+var_14F0]; unsigned __int64
0x140005a77  mov     rdx, rbx; wchar_t *
0x140005a7a  lea     rcx, [rbp+1410h+OutputString]; this
0x140005a81  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140005a86  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x140005a8d  call    cs:__imp_OutputDebugStringW
0x140005a93  test    byte ptr [rsp+1510h+var_14F0+4], 4
0x140005a98  jnz     short loc_140005AA3
0x140005a9a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140005aa1  jz      short loc_140005AB5
0x140005aa3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140005aaa  test    rax, rax
0x140005aad  jz      short loc_140005AB5
0x140005aaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ab4  nop
0x140005ab5  test    byte ptr [rsp+1510h+var_14F0+4], 1
0x140005aba  jnz     short loc_140005ADD
0x140005abc  mov     rcx, [rbp+1410h+var_40]
0x140005ac3  xor     rcx, rsp; StackCookie
0x140005ac6  call    __security_check_cookie
0x140005acb  add     rsp, 14E0h
0x140005ad2  pop     r15
0x140005ad4  pop     r14
0x140005ad6  pop     r12
0x140005ad8  pop     rdi
0x140005ad9  pop     rsi
0x140005ada  pop     rbx
0x140005adb  pop     rbp
0x140005adc  retn
0x140005add  lea     rcx, [rsp+1510h+var_14F0]; this
0x140005ae2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140005ae8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
