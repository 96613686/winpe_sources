# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000672c`
- end: `0x1800069b9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800063e8`

## callees

- `0x180004170`
- `0x180005140`
- `0x18000672c`
- `0x1800079f4`
- `0x180008e10`
- `0x18000a248`
- `0x18000a378`
- `0x180041d40`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800067da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800067da`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800068ce`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800068ce`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006958`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006958`

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
0x18000672c  push    rbp
0x18000672e  push    rbx
0x18000672f  push    rsi
0x180006730  push    rdi
0x180006731  push    r12
0x180006733  push    r14
0x180006735  push    r15
0x180006737  lea     rbp, [rsp-13D0h]
0x18000673f  mov     eax, 14D0h
0x180006744  call    _alloca_probe
0x180006749  sub     rsp, rax
0x18000674c  mov     rax, cs:__security_cookie
0x180006753  xor     rax, rsp
0x180006756  mov     [rbp+1400h+var_40], rax
0x18000675d  mov     r14, r8
0x180006760  mov     esi, edx
0x180006762  mov     r15, rcx
0x180006765  mov     rdi, [rbp+1400h+arg_28]
0x18000676c  xor     edx, edx; Val
0x18000676e  mov     r8d, 98h; Size
0x180006774  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180006779  call    memset_0
0x18000677e  nop
0x18000677f  xor     r12d, r12d
0x180006782  mov     [rbp+1400h+OutputString], r12w
0x18000678a  mov     [rbp+1400h+var_1440], r12b
0x18000678e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180006795  mov     ecx, [rdx]; this
0x180006797  mov     [rsp+1500h+var_14D8], ecx
0x18000679b  mov     eax, [rdx+4]
0x18000679e  mov     [rsp+1500h+var_14D4], eax
0x1800067a2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800067a7  mov     ebx, eax
0x1800067a9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800067b1  mov     ecx, r12d
0x1800067b4  lea     eax, [r12+8]
0x1800067b9  cmp     dword ptr [rdx+8], 1
0x1800067bd  cmovz   ecx, eax
0x1800067c0  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800067c4  lea     ecx, [rax-7]
0x1800067c7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800067cf  inc     ecx
0x1800067d1  mov     [rsp+1500h+var_14D0], ecx
0x1800067d5  mov     [rsp+1500h+var_14C8], r12
0x1800067da  call    cs:__imp_GetCurrentThreadId
0x1800067e0  mov     [rsp+1500h+var_14C0], eax
0x1800067e4  mov     [rsp+1500h+var_14A8], r14
0x1800067e9  mov     [rsp+1500h+var_14A0], esi
0x1800067ed  mov     [rsp+1500h+var_149C], ebx
0x1800067f1  mov     [rsp+1500h+var_14B8], r12
0x1800067f6  mov     [rsp+1500h+var_14B0], r12
0x1800067fb  mov     [rbp+1400h+var_1458], rdi
0x1800067ff  mov     [rbp+1400h+var_1450], r15
0x180006803  mov     [rsp+1500h+var_1498], r12
0x180006808  xorps   xmm0, xmm0
0x18000680b  xor     eax, eax
0x18000680d  movups  [rbp+1400h+var_1478], xmm0
0x180006811  mov     [rbp+1400h+var_1468], rax
0x180006815  xorps   xmm1, xmm1
0x180006818  movups  [rsp+1500h+var_1490], xmm1
0x18000681d  mov     [rbp+1400h+var_1480], rax
0x180006821  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006828  test    rax, rax
0x18000682b  jz      short loc_180006838
0x18000682d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006832  mov     [rbp+1400h+var_1460], rax
0x180006836  jmp     short loc_18000683C
0x180006838  mov     [rbp+1400h+var_1460], r12
0x18000683c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006843  test    rax, rax
0x180006846  jz      short loc_180006852
0x180006848  lea     rcx, [rsp+1500h+var_14E0]
0x18000684d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006852  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006859  test    rax, rax
0x18000685c  jz      short loc_180006872
0x18000685e  mov     r8d, 400h
0x180006864  lea     rdx, [rbp+1400h+var_1440]
0x180006868  lea     rcx, [rsp+1500h+var_14E0]
0x18000686d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006872  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006879  test    rax, rax
0x18000687c  jz      short loc_180006888
0x18000687e  lea     rcx, [rsp+1500h+var_14E0]
0x180006883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006888  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000688f  test    rax, rax
0x180006892  jz      short loc_1800068A5
0x180006894  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006899  jnz     short loc_1800068A5
0x18000689b  lea     rcx, [rsp+1500h+var_14E0]
0x1800068a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068a5  cmp     [rsp+1500h+var_14D8], r12d
0x1800068aa  jge     loc_1800069B3
0x1800068b0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800068b7  jnz     short loc_1800068D8
0x1800068b9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800068c0  test    rax, rax
0x1800068c3  jz      short loc_1800068CE
0x1800068c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068ca  test    al, al
0x1800068cc  jmp     short loc_1800068D6
0x1800068ce  call    cs:__imp_IsDebuggerPresent
0x1800068d4  test    eax, eax
0x1800068d6  jz      short loc_1800068DF
0x1800068d8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800068dd  jz      short loc_180006905
0x1800068df  mov     rax, cs:g_pfnResultLoggingCallback
0x1800068e6  test    rax, rax
0x1800068e9  jz      short loc_18000695E
0x1800068eb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800068f2  jnz     short loc_18000695E
0x1800068f4  xor     r8d, r8d
0x1800068f7  xor     edx, edx
0x1800068f9  lea     rcx, [rsp+1500h+var_14E0]
0x1800068fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006903  jmp     short loc_18000695E
0x180006905  mov     ebx, 800h
0x18000690a  mov     rax, cs:g_pfnResultLoggingCallback
0x180006911  test    rax, rax
0x180006914  jz      short loc_180006933
0x180006916  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000691d  jnz     short loc_180006933
0x18000691f  mov     r8d, ebx
0x180006922  lea     rdx, [rbp+1400h+OutputString]
0x180006929  lea     rcx, [rsp+1500h+var_14E0]
0x18000692e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006933  cmp     [rbp+1400h+OutputString], r12w
0x18000693b  jnz     short loc_180006951
0x18000693d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180006942  mov     rdx, rbx; unsigned __int16 *
0x180006945  lea     rcx, [rbp+1400h+OutputString]; this
0x18000694c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006951  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180006958  call    cs:__imp_OutputDebugStringW
0x18000695e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180006963  jnz     short loc_18000696E
0x180006965  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000696c  jz      short loc_180006980
0x18000696e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006975  test    rax, rax
0x180006978  jz      short loc_180006980
0x18000697a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000697f  nop
0x180006980  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180006985  jnz     short loc_1800069A8
0x180006987  mov     rcx, [rbp+1400h+var_40]
0x18000698e  xor     rcx, rsp; StackCookie
0x180006991  call    __security_check_cookie
0x180006996  add     rsp, 14D0h
0x18000699d  pop     r15
0x18000699f  pop     r14
0x1800069a1  pop     r12
0x1800069a3  pop     rdi
0x1800069a4  pop     rsi
0x1800069a5  pop     rbx
0x1800069a6  pop     rbp
0x1800069a7  retn
0x1800069a8  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800069ad  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800069b3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
