# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000516c`
- end: `0x180005412`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004df8`

## callees

- `0x180003ab0`
- `0x1800047f0`
- `0x18000516c`
- `0x180006c14`
- `0x18000893c`
- `0x18000a488`
- `0x18000a720`
- `0x18002f0d0`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005232`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005232`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005327`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005327`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800053b1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800053b1`

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
0x18000516c  push    rbp
0x18000516e  push    rbx
0x18000516f  push    rsi
0x180005170  push    rdi
0x180005171  push    r12
0x180005173  push    r14
0x180005175  push    r15
0x180005177  lea     rbp, [rsp-13D0h]
0x18000517f  mov     eax, 14D0h
0x180005184  call    _alloca_probe
0x180005189  sub     rsp, rax
0x18000518c  mov     rax, cs:__security_cookie
0x180005193  xor     rax, rsp
0x180005196  mov     [rbp+1400h+var_40], rax
0x18000519d  mov     rsi, r8
0x1800051a0  mov     edi, edx
0x1800051a2  mov     rbx, rcx
0x1800051a5  mov     r14, [rbp+1400h+arg_28]
0x1800051ac  xor     edx, edx; Val
0x1800051ae  mov     r8d, 98h; Size
0x1800051b4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800051b9  call    memset_0
0x1800051be  nop
0x1800051bf  xor     r12d, r12d
0x1800051c2  mov     [rbp+1400h+OutputString], r12w
0x1800051ca  mov     [rbp+1400h+var_1440], r12b
0x1800051ce  mov     rdx, [rbp+1400h+arg_30]; int
0x1800051d5  mov     ecx, [rdx]; this
0x1800051d7  mov     [rsp+1500h+var_14D8], ecx
0x1800051db  mov     eax, [rdx+4]
0x1800051de  mov     [rsp+1500h+var_14D4], eax
0x1800051e2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800051e7  mov     r15d, eax
0x1800051ea  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800051f2  mov     ecx, r12d
0x1800051f5  lea     eax, [r12+8]
0x1800051fa  cmp     dword ptr [rdx+8], 1
0x1800051fe  cmovz   ecx, eax
0x180005201  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005205  lea     ecx, [rax-7]
0x180005208  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005210  inc     ecx
0x180005212  mov     [rsp+1500h+var_14D0], ecx
0x180005216  mov     rcx, [rbp+1400h+arg_38]
0x18000521d  test    rcx, rcx
0x180005220  jz      short loc_18000522D
0x180005222  cmp     [rcx], r12w
0x180005226  mov     [rsp+1500h+var_14C8], rcx
0x18000522b  jnz     short loc_180005232
0x18000522d  mov     [rsp+1500h+var_14C8], r12
0x180005232  call    cs:__imp_GetCurrentThreadId
0x180005238  mov     [rsp+1500h+var_14C0], eax
0x18000523c  mov     [rsp+1500h+var_14A8], rsi
0x180005241  mov     [rsp+1500h+var_14A0], edi
0x180005245  mov     [rsp+1500h+var_149C], r15d
0x18000524a  mov     [rsp+1500h+var_14B8], r12
0x18000524f  mov     [rsp+1500h+var_14B0], r12
0x180005254  mov     [rbp+1400h+var_1458], r14
0x180005258  mov     [rbp+1400h+var_1450], rbx
0x18000525c  mov     [rsp+1500h+var_1498], r12
0x180005261  xorps   xmm0, xmm0
0x180005264  xor     eax, eax
0x180005266  movups  [rbp+1400h+var_1478], xmm0
0x18000526a  mov     [rbp+1400h+var_1468], rax
0x18000526e  xorps   xmm1, xmm1
0x180005271  movups  [rsp+1500h+var_1490], xmm1
0x180005276  mov     [rbp+1400h+var_1480], rax
0x18000527a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005281  test    rax, rax
0x180005284  jz      short loc_180005291
0x180005286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000528b  mov     [rbp+1400h+var_1460], rax
0x18000528f  jmp     short loc_180005295
0x180005291  mov     [rbp+1400h+var_1460], r12
0x180005295  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000529c  test    rax, rax
0x18000529f  jz      short loc_1800052AB
0x1800052a1  lea     rcx, [rsp+1500h+var_14E0]
0x1800052a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052ab  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800052b2  test    rax, rax
0x1800052b5  jz      short loc_1800052CB
0x1800052b7  mov     r8d, 400h
0x1800052bd  lea     rdx, [rbp+1400h+var_1440]
0x1800052c1  lea     rcx, [rsp+1500h+var_14E0]
0x1800052c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052cb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800052d2  test    rax, rax
0x1800052d5  jz      short loc_1800052E1
0x1800052d7  lea     rcx, [rsp+1500h+var_14E0]
0x1800052dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052e1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800052e8  test    rax, rax
0x1800052eb  jz      short loc_1800052FE
0x1800052ed  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800052f2  jnz     short loc_1800052FE
0x1800052f4  lea     rcx, [rsp+1500h+var_14E0]
0x1800052f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052fe  cmp     [rsp+1500h+var_14D8], r12d
0x180005303  jge     loc_18000540C
0x180005309  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005310  jnz     short loc_180005331
0x180005312  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005319  test    rax, rax
0x18000531c  jz      short loc_180005327
0x18000531e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005323  test    al, al
0x180005325  jmp     short loc_18000532F
0x180005327  call    cs:__imp_IsDebuggerPresent
0x18000532d  test    eax, eax
0x18000532f  jz      short loc_180005338
0x180005331  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005336  jz      short loc_18000535E
0x180005338  mov     rax, cs:g_pfnResultLoggingCallback
0x18000533f  test    rax, rax
0x180005342  jz      short loc_1800053B7
0x180005344  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000534b  jnz     short loc_1800053B7
0x18000534d  xor     r8d, r8d
0x180005350  xor     edx, edx
0x180005352  lea     rcx, [rsp+1500h+var_14E0]
0x180005357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000535c  jmp     short loc_1800053B7
0x18000535e  mov     ebx, 800h
0x180005363  mov     rax, cs:g_pfnResultLoggingCallback
0x18000536a  test    rax, rax
0x18000536d  jz      short loc_18000538C
0x18000536f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005376  jnz     short loc_18000538C
0x180005378  mov     r8d, ebx
0x18000537b  lea     rdx, [rbp+1400h+OutputString]
0x180005382  lea     rcx, [rsp+1500h+var_14E0]
0x180005387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000538c  cmp     [rbp+1400h+OutputString], r12w
0x180005394  jnz     short loc_1800053AA
0x180005396  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000539b  mov     rdx, rbx; unsigned __int16 *
0x18000539e  lea     rcx, [rbp+1400h+OutputString]; this
0x1800053a5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800053aa  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800053b1  call    cs:__imp_OutputDebugStringW
0x1800053b7  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800053bc  jnz     short loc_1800053C7
0x1800053be  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800053c5  jz      short loc_1800053D9
0x1800053c7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800053ce  test    rax, rax
0x1800053d1  jz      short loc_1800053D9
0x1800053d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053d8  nop
0x1800053d9  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800053de  jnz     short loc_180005401
0x1800053e0  mov     rcx, [rbp+1400h+var_40]
0x1800053e7  xor     rcx, rsp; StackCookie
0x1800053ea  call    __security_check_cookie
0x1800053ef  add     rsp, 14D0h
0x1800053f6  pop     r15
0x1800053f8  pop     r14
0x1800053fa  pop     r12
0x1800053fc  pop     rdi
0x1800053fd  pop     rsi
0x1800053fe  pop     rbx
0x1800053ff  pop     rbp
0x180005400  retn
0x180005401  lea     rcx, [rsp+1500h+var_14E0]; this
0x180005406  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000540c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
