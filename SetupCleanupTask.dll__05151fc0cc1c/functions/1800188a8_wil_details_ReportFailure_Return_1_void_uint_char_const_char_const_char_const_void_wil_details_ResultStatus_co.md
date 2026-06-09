# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800188a8`
- end: `0x180018b3c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180018388`

## callees

- `0x1800188a8`
- `0x18001bb28`
- `0x180020f74`
- `0x180024360`
- `0x1800247e4`
- `0x1800322d2`
- `0x180032310`
- `0x1800323d0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018952`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018952`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180018a4d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180018a4d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180018ad7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180018ad7`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x1800188a8  mov     [rsp-8+arg_10], rbx
0x1800188ad  push    rbp
0x1800188ae  push    rsi
0x1800188af  push    rdi
0x1800188b0  push    r14
0x1800188b2  push    r15
0x1800188b4  lea     rbp, [rsp-13D0h]
0x1800188bc  mov     eax, 14D0h
0x1800188c1  call    _alloca_probe
0x1800188c6  sub     rsp, rax
0x1800188c9  mov     rax, cs:__security_cookie
0x1800188d0  xor     rax, rsp
0x1800188d3  mov     [rbp+13F0h+var_30], rax
0x1800188da  mov     rdi, [rbp+13F0h+arg_28]
0x1800188e1  mov     esi, edx
0x1800188e3  mov     r14, rcx
0x1800188e6  xor     edx, edx; Val
0x1800188e8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800188ed  mov     r8d, 98h; Size
0x1800188f3  call    memset_0
0x1800188f8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800188ff  xor     r15d, r15d
0x180018902  mov     [rbp+13F0h+OutputString], r15w
0x18001890a  mov     [rbp+13F0h+var_1430], r15b
0x18001890e  mov     ecx, [rdx]; this
0x180018910  mov     eax, [rdx+4]
0x180018913  mov     [rsp+14F0h+var_14C8], ecx
0x180018917  mov     [rsp+14F0h+var_14C4], eax
0x18001891b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180018920  cmp     dword ptr [rdx+8], 1
0x180018924  mov     ebx, eax
0x180018926  lea     eax, [r15+8]
0x18001892a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180018932  mov     ecx, r15d
0x180018935  cmovz   ecx, eax
0x180018938  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001893c  lea     ecx, [rax-7]
0x18001893f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180018947  inc     ecx
0x180018949  mov     [rsp+14F0h+var_14B8], r15
0x18001894e  mov     [rsp+14F0h+var_14C0], ecx
0x180018952  call    cs:__imp_GetCurrentThreadId
0x180018958  xorps   xmm0, xmm0
0x18001895b  mov     [rsp+14F0h+var_1490], esi
0x18001895f  mov     [rsp+14F0h+var_14B0], eax
0x180018963  xorps   xmm1, xmm1
0x180018966  lea     rax, aWil; "wil"
0x18001896d  mov     [rsp+14F0h+var_148C], ebx
0x180018971  mov     [rsp+14F0h+var_1498], rax
0x180018976  xor     eax, eax
0x180018978  mov     [rbp+13F0h+var_1458], rax
0x18001897c  mov     [rbp+13F0h+var_1470], rax
0x180018980  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180018987  mov     [rsp+14F0h+var_14A8], r15
0x18001898c  mov     [rsp+14F0h+var_14A0], r15
0x180018991  mov     [rbp+13F0h+var_1448], rdi
0x180018995  mov     [rbp+13F0h+var_1440], r14
0x180018999  mov     [rsp+14F0h+var_1488], r15
0x18001899e  movups  [rbp+13F0h+var_1468], xmm0
0x1800189a2  movups  [rsp+14F0h+var_1480], xmm1
0x1800189a7  test    rax, rax
0x1800189aa  jz      short loc_1800189B7
0x1800189ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189b1  mov     [rbp+13F0h+var_1450], rax
0x1800189b5  jmp     short loc_1800189BB
0x1800189b7  mov     [rbp+13F0h+var_1450], r15
0x1800189bb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800189c2  test    rax, rax
0x1800189c5  jz      short loc_1800189D1
0x1800189c7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800189cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189d1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800189d8  test    rax, rax
0x1800189db  jz      short loc_1800189F1
0x1800189dd  mov     r8d, 400h
0x1800189e3  lea     rdx, [rbp+13F0h+var_1430]
0x1800189e7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800189ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800189f1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800189f8  test    rax, rax
0x1800189fb  jz      short loc_180018A07
0x1800189fd  lea     rcx, [rsp+14F0h+var_14D0]
0x180018a02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a07  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180018a0e  test    rax, rax
0x180018a11  jz      short loc_180018A24
0x180018a13  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180018a18  jnz     short loc_180018A24
0x180018a1a  lea     rcx, [rsp+14F0h+var_14D0]
0x180018a1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a24  cmp     [rsp+14F0h+var_14C8], r15d
0x180018a29  jge     loc_180018B2B
0x180018a2f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180018a36  jnz     short loc_180018A57
0x180018a38  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180018a3f  test    rax, rax
0x180018a42  jz      short loc_180018A4D
0x180018a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a49  test    al, al
0x180018a4b  jmp     short loc_180018A55
0x180018a4d  call    cs:__imp_IsDebuggerPresent
0x180018a53  test    eax, eax
0x180018a55  jz      short loc_180018A5E
0x180018a57  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180018a5c  jz      short loc_180018A84
0x180018a5e  mov     rax, cs:g_pfnResultLoggingCallback
0x180018a65  test    rax, rax
0x180018a68  jz      short loc_180018ADD
0x180018a6a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180018a71  jnz     short loc_180018ADD
0x180018a73  xor     r8d, r8d
0x180018a76  lea     rcx, [rsp+14F0h+var_14D0]
0x180018a7b  xor     edx, edx
0x180018a7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018a82  jmp     short loc_180018ADD
0x180018a84  mov     rax, cs:g_pfnResultLoggingCallback
0x180018a8b  mov     ebx, 800h
0x180018a90  test    rax, rax
0x180018a93  jz      short loc_180018AB2
0x180018a95  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180018a9c  jnz     short loc_180018AB2
0x180018a9e  mov     r8d, ebx
0x180018aa1  lea     rdx, [rbp+13F0h+OutputString]
0x180018aa8  lea     rcx, [rsp+14F0h+var_14D0]
0x180018aad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018ab2  cmp     [rbp+13F0h+OutputString], r15w
0x180018aba  jnz     short loc_180018AD0
0x180018abc  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180018ac1  mov     rdx, rbx; unsigned __int16 *
0x180018ac4  lea     rcx, [rbp+13F0h+OutputString]; this
0x180018acb  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180018ad0  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180018ad7  call    cs:__imp_OutputDebugStringW
0x180018add  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180018ae2  jnz     short loc_180018AED
0x180018ae4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180018aeb  jz      short loc_180018AFE
0x180018aed  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180018af4  test    rax, rax
0x180018af7  jz      short loc_180018AFE
0x180018af9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018afe  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180018b03  jnz     short loc_180018B31
0x180018b05  mov     rcx, [rbp+13F0h+var_30]
0x180018b0c  xor     rcx, rsp; StackCookie
0x180018b0f  call    __security_check_cookie
0x180018b14  mov     rbx, [rsp+14F0h+arg_10]
0x180018b1c  add     rsp, 14D0h
0x180018b23  pop     r15
0x180018b25  pop     r14
0x180018b27  pop     rdi
0x180018b28  pop     rsi
0x180018b29  pop     rbp
0x180018b2a  retn
0x180018b2b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180018b31  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180018b36  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
