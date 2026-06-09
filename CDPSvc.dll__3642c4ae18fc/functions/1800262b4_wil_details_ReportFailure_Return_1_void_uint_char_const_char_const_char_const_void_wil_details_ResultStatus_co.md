# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800262b4`
- end: `0x180026547`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `659`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001d308`

## callees

- `0x180016d98`
- `0x1800225a0`
- `0x1800262b4`
- `0x180026bfc`
- `0x180027090`
- `0x180027408`
- `0x180063b00`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026367`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026367`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002645c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002645c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800264e6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800264e6`

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
0x1800262b4  push    rbp
0x1800262b6  push    rbx
0x1800262b7  push    rsi
0x1800262b8  push    rdi
0x1800262b9  push    r12
0x1800262bb  push    r14
0x1800262bd  push    r15
0x1800262bf  lea     rbp, [rsp-13D0h]
0x1800262c7  mov     eax, 14D0h
0x1800262cc  call    _alloca_probe
0x1800262d1  sub     rsp, rax
0x1800262d4  mov     rax, cs:__security_cookie
0x1800262db  xor     rax, rsp
0x1800262de  mov     [rbp+1400h+var_40], rax
0x1800262e5  mov     rsi, r8
0x1800262e8  mov     edi, edx
0x1800262ea  mov     rbx, rcx
0x1800262ed  mov     r14, [rbp+1400h+arg_28]
0x1800262f4  xor     r12d, r12d
0x1800262f7  mov     [rbp+1400h+OutputString], r12w
0x1800262ff  mov     [rbp+1400h+var_1440], r12b
0x180026303  mov     rdx, [rbp+1400h+arg_30]; int
0x18002630a  mov     ecx, [rdx]; this
0x18002630c  mov     [rsp+1500h+var_14D8], ecx
0x180026310  mov     eax, [rdx+4]
0x180026313  mov     [rsp+1500h+var_14D4], eax
0x180026317  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002631c  mov     r15d, eax
0x18002631f  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180026327  mov     ecx, r12d
0x18002632a  lea     eax, [r12+8]
0x18002632f  cmp     dword ptr [rdx+8], 1
0x180026333  cmovz   ecx, eax
0x180026336  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18002633a  lea     ecx, [rax-7]
0x18002633d  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180026345  inc     ecx
0x180026347  mov     [rsp+1500h+var_14D0], ecx
0x18002634b  mov     rcx, [rbp+1400h+arg_38]
0x180026352  test    rcx, rcx
0x180026355  jz      short loc_180026362
0x180026357  cmp     [rcx], r12w
0x18002635b  mov     [rsp+1500h+var_14C8], rcx
0x180026360  jnz     short loc_180026367
0x180026362  mov     [rsp+1500h+var_14C8], r12
0x180026367  call    cs:__imp_GetCurrentThreadId
0x18002636d  mov     [rsp+1500h+var_14C0], eax
0x180026371  mov     [rsp+1500h+var_14A8], rsi
0x180026376  mov     [rsp+1500h+var_14A0], edi
0x18002637a  mov     [rsp+1500h+var_149C], r15d
0x18002637f  mov     [rsp+1500h+var_14B8], r12
0x180026384  mov     [rsp+1500h+var_14B0], r12
0x180026389  mov     [rbp+1400h+var_1458], r14
0x18002638d  mov     [rbp+1400h+var_1450], rbx
0x180026391  mov     [rsp+1500h+var_1498], r12
0x180026396  xorps   xmm0, xmm0
0x180026399  xor     eax, eax
0x18002639b  movups  [rbp+1400h+var_1478], xmm0
0x18002639f  mov     [rbp+1400h+var_1468], rax
0x1800263a3  xorps   xmm1, xmm1
0x1800263a6  movups  [rsp+1500h+var_1490], xmm1
0x1800263ab  mov     [rbp+1400h+var_1480], rax
0x1800263af  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800263b6  test    rax, rax
0x1800263b9  jz      short loc_1800263C6
0x1800263bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263c0  mov     [rbp+1400h+var_1460], rax
0x1800263c4  jmp     short loc_1800263CA
0x1800263c6  mov     [rbp+1400h+var_1460], r12
0x1800263ca  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800263d1  test    rax, rax
0x1800263d4  jz      short loc_1800263E0
0x1800263d6  lea     rcx, [rsp+1500h+var_14E0]
0x1800263db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800263e0  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800263e7  test    rax, rax
0x1800263ea  jz      short loc_180026400
0x1800263ec  mov     r8d, 400h
0x1800263f2  lea     rdx, [rbp+1400h+var_1440]
0x1800263f6  lea     rcx, [rsp+1500h+var_14E0]
0x1800263fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026400  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180026407  test    rax, rax
0x18002640a  jz      short loc_180026416
0x18002640c  lea     rcx, [rsp+1500h+var_14E0]
0x180026411  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026416  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002641d  test    rax, rax
0x180026420  jz      short loc_180026433
0x180026422  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180026427  jnz     short loc_180026433
0x180026429  lea     rcx, [rsp+1500h+var_14E0]
0x18002642e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026433  cmp     [rsp+1500h+var_14D8], r12d
0x180026438  jge     loc_180026541
0x18002643e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180026445  jnz     short loc_180026466
0x180026447  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002644e  test    rax, rax
0x180026451  jz      short loc_18002645C
0x180026453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026458  test    al, al
0x18002645a  jmp     short loc_180026464
0x18002645c  call    cs:__imp_IsDebuggerPresent
0x180026462  test    eax, eax
0x180026464  jz      short loc_18002646D
0x180026466  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18002646b  jz      short loc_180026493
0x18002646d  mov     rax, cs:g_pfnResultLoggingCallback
0x180026474  test    rax, rax
0x180026477  jz      short loc_1800264EC
0x180026479  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180026480  jnz     short loc_1800264EC
0x180026482  xor     r8d, r8d
0x180026485  xor     edx, edx
0x180026487  lea     rcx, [rsp+1500h+var_14E0]
0x18002648c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026491  jmp     short loc_1800264EC
0x180026493  mov     ebx, 800h
0x180026498  mov     rax, cs:g_pfnResultLoggingCallback
0x18002649f  test    rax, rax
0x1800264a2  jz      short loc_1800264C1
0x1800264a4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800264ab  jnz     short loc_1800264C1
0x1800264ad  mov     r8d, ebx
0x1800264b0  lea     rdx, [rbp+1400h+OutputString]
0x1800264b7  lea     rcx, [rsp+1500h+var_14E0]
0x1800264bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264c1  cmp     [rbp+1400h+OutputString], r12w
0x1800264c9  jnz     short loc_1800264DF
0x1800264cb  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800264d0  mov     rdx, rbx; unsigned __int16 *
0x1800264d3  lea     rcx, [rbp+1400h+OutputString]; this
0x1800264da  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800264df  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800264e6  call    cs:__imp_OutputDebugStringW
0x1800264ec  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800264f1  jnz     short loc_1800264FC
0x1800264f3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800264fa  jz      short loc_18002650E
0x1800264fc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180026503  test    rax, rax
0x180026506  jz      short loc_18002650E
0x180026508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002650d  nop
0x18002650e  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180026513  jnz     short loc_180026536
0x180026515  mov     rcx, [rbp+1400h+var_40]
0x18002651c  xor     rcx, rsp; StackCookie
0x18002651f  call    __security_check_cookie
0x180026524  add     rsp, 14D0h
0x18002652b  pop     r15
0x18002652d  pop     r14
0x18002652f  pop     r12
0x180026531  pop     rdi
0x180026532  pop     rsi
0x180026533  pop     rbx
0x180026534  pop     rbp
0x180026535  retn
0x180026536  lea     rcx, [rsp+1500h+var_14E0]; this
0x18002653b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180026541  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
