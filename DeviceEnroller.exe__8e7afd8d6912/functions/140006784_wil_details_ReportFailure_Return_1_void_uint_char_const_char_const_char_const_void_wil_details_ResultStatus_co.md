# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140006784`
- end: `0x140006a2a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140005edc`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x140006784`
- `0x140007f74`
- `0x1400091f0`
- `0x14000a510`
- `0x14000a698`
- `0x140059180`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000684a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000684a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000693f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000693f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400069c9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400069c9`

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
0x140006784  push    rbp
0x140006786  push    rbx
0x140006787  push    rsi
0x140006788  push    rdi
0x140006789  push    r12
0x14000678b  push    r14
0x14000678d  push    r15
0x14000678f  lea     rbp, [rsp-13D0h]
0x140006797  mov     eax, 14D0h
0x14000679c  call    _alloca_probe
0x1400067a1  sub     rsp, rax
0x1400067a4  mov     rax, cs:__security_cookie
0x1400067ab  xor     rax, rsp
0x1400067ae  mov     [rbp+1400h+var_40], rax
0x1400067b5  mov     rsi, r8
0x1400067b8  mov     edi, edx
0x1400067ba  mov     rbx, rcx
0x1400067bd  mov     r14, [rbp+1400h+arg_28]
0x1400067c4  xor     edx, edx; Val
0x1400067c6  mov     r8d, 98h; Size
0x1400067cc  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400067d1  call    memset_0
0x1400067d6  nop
0x1400067d7  xor     r12d, r12d
0x1400067da  mov     [rbp+1400h+OutputString], r12w
0x1400067e2  mov     [rbp+1400h+var_1440], r12b
0x1400067e6  mov     rdx, [rbp+1400h+arg_30]; int
0x1400067ed  mov     ecx, [rdx]; this
0x1400067ef  mov     [rsp+1500h+var_14D8], ecx
0x1400067f3  mov     eax, [rdx+4]
0x1400067f6  mov     [rsp+1500h+var_14D4], eax
0x1400067fa  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400067ff  mov     r15d, eax
0x140006802  mov     dword ptr [rsp+1500h+var_14E0], 1
0x14000680a  mov     ecx, r12d
0x14000680d  lea     eax, [r12+8]
0x140006812  cmp     dword ptr [rdx+8], 1
0x140006816  cmovz   ecx, eax
0x140006819  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x14000681d  lea     ecx, [rax-7]
0x140006820  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006828  inc     ecx
0x14000682a  mov     [rsp+1500h+var_14D0], ecx
0x14000682e  mov     rcx, [rbp+1400h+arg_38]
0x140006835  test    rcx, rcx
0x140006838  jz      short loc_140006845
0x14000683a  cmp     [rcx], r12w
0x14000683e  mov     [rsp+1500h+var_14C8], rcx
0x140006843  jnz     short loc_14000684A
0x140006845  mov     [rsp+1500h+var_14C8], r12
0x14000684a  call    cs:__imp_GetCurrentThreadId
0x140006850  mov     [rsp+1500h+var_14C0], eax
0x140006854  mov     [rsp+1500h+var_14A8], rsi
0x140006859  mov     [rsp+1500h+var_14A0], edi
0x14000685d  mov     [rsp+1500h+var_149C], r15d
0x140006862  mov     [rsp+1500h+var_14B8], r12
0x140006867  mov     [rsp+1500h+var_14B0], r12
0x14000686c  mov     [rbp+1400h+var_1458], r14
0x140006870  mov     [rbp+1400h+var_1450], rbx
0x140006874  mov     [rsp+1500h+var_1498], r12
0x140006879  xorps   xmm0, xmm0
0x14000687c  xor     eax, eax
0x14000687e  movups  [rbp+1400h+var_1478], xmm0
0x140006882  mov     [rbp+1400h+var_1468], rax
0x140006886  xorps   xmm1, xmm1
0x140006889  movups  [rsp+1500h+var_1490], xmm1
0x14000688e  mov     [rbp+1400h+var_1480], rax
0x140006892  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006899  test    rax, rax
0x14000689c  jz      short loc_1400068A9
0x14000689e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068a3  mov     [rbp+1400h+var_1460], rax
0x1400068a7  jmp     short loc_1400068AD
0x1400068a9  mov     [rbp+1400h+var_1460], r12
0x1400068ad  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400068b4  test    rax, rax
0x1400068b7  jz      short loc_1400068C3
0x1400068b9  lea     rcx, [rsp+1500h+var_14E0]
0x1400068be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068c3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400068ca  test    rax, rax
0x1400068cd  jz      short loc_1400068E3
0x1400068cf  mov     r8d, 400h
0x1400068d5  lea     rdx, [rbp+1400h+var_1440]
0x1400068d9  lea     rcx, [rsp+1500h+var_14E0]
0x1400068de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068e3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400068ea  test    rax, rax
0x1400068ed  jz      short loc_1400068F9
0x1400068ef  lea     rcx, [rsp+1500h+var_14E0]
0x1400068f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400068f9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006900  test    rax, rax
0x140006903  jz      short loc_140006916
0x140006905  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000690a  jnz     short loc_140006916
0x14000690c  lea     rcx, [rsp+1500h+var_14E0]
0x140006911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006916  cmp     [rsp+1500h+var_14D8], r12d
0x14000691b  jge     loc_140006A24
0x140006921  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140006928  jnz     short loc_140006949
0x14000692a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006931  test    rax, rax
0x140006934  jz      short loc_14000693F
0x140006936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000693b  test    al, al
0x14000693d  jmp     short loc_140006947
0x14000693f  call    cs:__imp_IsDebuggerPresent
0x140006945  test    eax, eax
0x140006947  jz      short loc_140006950
0x140006949  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000694e  jz      short loc_140006976
0x140006950  mov     rax, cs:g_pfnResultLoggingCallback
0x140006957  test    rax, rax
0x14000695a  jz      short loc_1400069CF
0x14000695c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140006963  jnz     short loc_1400069CF
0x140006965  xor     r8d, r8d
0x140006968  xor     edx, edx
0x14000696a  lea     rcx, [rsp+1500h+var_14E0]
0x14000696f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006974  jmp     short loc_1400069CF
0x140006976  mov     ebx, 800h
0x14000697b  mov     rax, cs:g_pfnResultLoggingCallback
0x140006982  test    rax, rax
0x140006985  jz      short loc_1400069A4
0x140006987  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000698e  jnz     short loc_1400069A4
0x140006990  mov     r8d, ebx
0x140006993  lea     rdx, [rbp+1400h+OutputString]
0x14000699a  lea     rcx, [rsp+1500h+var_14E0]
0x14000699f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400069a4  cmp     [rbp+1400h+OutputString], r12w
0x1400069ac  jnz     short loc_1400069C2
0x1400069ae  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1400069b3  mov     rdx, rbx; unsigned __int16 *
0x1400069b6  lea     rcx, [rbp+1400h+OutputString]; this
0x1400069bd  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400069c2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1400069c9  call    cs:__imp_OutputDebugStringW
0x1400069cf  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1400069d4  jnz     short loc_1400069DF
0x1400069d6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400069dd  jz      short loc_1400069F1
0x1400069df  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400069e6  test    rax, rax
0x1400069e9  jz      short loc_1400069F1
0x1400069eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400069f0  nop
0x1400069f1  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1400069f6  jnz     short loc_140006A19
0x1400069f8  mov     rcx, [rbp+1400h+var_40]
0x1400069ff  xor     rcx, rsp; StackCookie
0x140006a02  call    __security_check_cookie
0x140006a07  add     rsp, 14D0h
0x140006a0e  pop     r15
0x140006a10  pop     r14
0x140006a12  pop     r12
0x140006a14  pop     rdi
0x140006a15  pop     rsi
0x140006a16  pop     rbx
0x140006a17  pop     rbp
0x140006a18  retn
0x140006a19  lea     rcx, [rsp+1500h+var_14E0]; this
0x140006a1e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140006a24  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
