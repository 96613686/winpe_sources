# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180007830`
- end: `0x180007acf`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `671`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180006f2c`

## callees

- `0x180001514`
- `0x180001988`
- `0x180002c28`
- `0x180002e94`
- `0x180007830`
- `0x180008a80`
- `0x18000941c`
- `0x180009830`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800078db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800078db`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800079d7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800079d7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007a69`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007a69`

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
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v14; // r9
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh]
  int v17; // [rsp+28h] [rbp-D8h]
  int v18; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v19; // [rsp+30h] [rbp-D0h]
  __int64 v20; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v22; // [rsp+48h] [rbp-B8h]
  __int64 v23; // [rsp+50h] [rbp-B0h]
  const char *v24; // [rsp+58h] [rbp-A8h]
  int v25; // [rsp+60h] [rbp-A0h]
  int v26; // [rsp+64h] [rbp-9Ch]
  __int64 v27; // [rsp+68h] [rbp-98h]
  __int128 v28; // [rsp+70h] [rbp-90h]
  __int64 v29; // [rsp+80h] [rbp-80h]
  __int128 v30; // [rsp+88h] [rbp-78h]
  __int64 v31; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v33; // [rsp+A8h] [rbp-58h]
  __int64 v34; // [rsp+B0h] [rbp-50h]
  char v35[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v15, 0, 0x98u);
  OutputString[0] = 0;
  v35[0] = 0;
  v17 = *a7;
  v18 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v17, (int)a7);
  v15 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v16 = v10;
  v19 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v20 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v24 = "wil";
  v25 = a2;
  v26 = v9;
  v22 = 0;
  v23 = 0;
  v33 = a6;
  v34 = a1;
  v27 = 0;
  v30 = 0;
  v31 = 0;
  v28 = 0;
  v29 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v15, v35, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v15);
  if ( wil::details::g_pfnOriginateCallback && (v16 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v15);
  if ( v17 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (v16 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v15, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v15, v14);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v15, 0, 0);
  }
  if ( ((v16 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  if ( (v16 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v15, v12);
}

```

## disassembly

```asm
0x180007830  mov     [rsp-8+arg_10], rbx
0x180007835  push    rbp
0x180007836  push    rsi
0x180007837  push    rdi
0x180007838  push    r14
0x18000783a  push    r15
0x18000783c  lea     rbp, [rsp-13D0h]
0x180007844  mov     eax, 14D0h
0x180007849  call    _alloca_probe
0x18000784e  sub     rsp, rax
0x180007851  mov     rax, cs:__security_cookie
0x180007858  xor     rax, rsp
0x18000785b  mov     [rbp+13F0h+var_30], rax
0x180007862  mov     esi, edx
0x180007864  mov     r14, rcx
0x180007867  mov     rdi, [rbp+13F0h+arg_28]
0x18000786e  xor     edx, edx; Val
0x180007870  mov     r8d, 98h; Size
0x180007876  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000787b  call    memset_0
0x180007880  nop
0x180007881  xor     r15d, r15d
0x180007884  mov     [rbp+13F0h+OutputString], r15w
0x18000788c  mov     [rbp+13F0h+var_1430], r15b
0x180007890  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180007897  mov     ecx, [rdx]; this
0x180007899  mov     [rsp+14F0h+var_14C8], ecx
0x18000789d  mov     eax, [rdx+4]
0x1800078a0  mov     [rsp+14F0h+var_14C4], eax
0x1800078a4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800078a9  mov     ebx, eax
0x1800078ab  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800078b3  mov     ecx, r15d
0x1800078b6  lea     eax, [r15+8]
0x1800078ba  cmp     dword ptr [rdx+8], 1
0x1800078be  cmovz   ecx, eax
0x1800078c1  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800078c5  lea     ecx, [rax-7]
0x1800078c8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800078d0  inc     ecx
0x1800078d2  mov     [rsp+14F0h+var_14C0], ecx
0x1800078d6  mov     [rsp+14F0h+var_14B8], r15
0x1800078db  call    cs:__imp_GetCurrentThreadId
0x1800078e1  mov     [rsp+14F0h+var_14B0], eax
0x1800078e5  lea     rax, aWil; "wil"
0x1800078ec  mov     [rsp+14F0h+var_1498], rax
0x1800078f1  mov     [rsp+14F0h+var_1490], esi
0x1800078f5  mov     [rsp+14F0h+var_148C], ebx
0x1800078f9  mov     [rsp+14F0h+var_14A8], r15
0x1800078fe  mov     [rsp+14F0h+var_14A0], r15
0x180007903  mov     [rbp+13F0h+var_1448], rdi
0x180007907  mov     [rbp+13F0h+var_1440], r14
0x18000790b  mov     [rsp+14F0h+var_1488], r15
0x180007910  xorps   xmm0, xmm0
0x180007913  xor     eax, eax
0x180007915  movups  [rbp+13F0h+var_1468], xmm0
0x180007919  mov     [rbp+13F0h+var_1458], rax
0x18000791d  xorps   xmm1, xmm1
0x180007920  movups  [rsp+14F0h+var_1480], xmm1
0x180007925  mov     [rbp+13F0h+var_1470], rax
0x180007929  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007930  test    rax, rax
0x180007933  jz      short loc_180007940
0x180007935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000793a  mov     [rbp+13F0h+var_1450], rax
0x18000793e  jmp     short loc_180007944
0x180007940  mov     [rbp+13F0h+var_1450], r15
0x180007944  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000794b  test    rax, rax
0x18000794e  jz      short loc_18000795A
0x180007950  lea     rcx, [rsp+14F0h+var_14D0]
0x180007955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000795a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007961  test    rax, rax
0x180007964  jz      short loc_18000797A
0x180007966  mov     r8d, 400h
0x18000796c  lea     rdx, [rbp+13F0h+var_1430]
0x180007970  lea     rcx, [rsp+14F0h+var_14D0]
0x180007975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000797a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007981  test    rax, rax
0x180007984  jz      short loc_180007990
0x180007986  lea     rcx, [rsp+14F0h+var_14D0]
0x18000798b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007990  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007997  test    rax, rax
0x18000799a  jz      short loc_1800079AD
0x18000799c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800079a1  jnz     short loc_1800079AD
0x1800079a3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800079a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079ad  cmp     [rsp+14F0h+var_14C8], r15d
0x1800079b2  jge     loc_180007AC9
0x1800079b8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800079bf  jnz     short loc_1800079E9
0x1800079c1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800079c8  test    rax, rax
0x1800079cb  jz      short loc_1800079D7
0x1800079cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079d2  movzx   ecx, al
0x1800079d5  jmp     short loc_1800079E5
0x1800079d7  call    cs:__imp_IsDebuggerPresent
0x1800079dd  mov     ecx, r15d
0x1800079e0  test    eax, eax
0x1800079e2  setnz   cl
0x1800079e5  test    ecx, ecx
0x1800079e7  jz      short loc_1800079F0
0x1800079e9  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800079ee  jz      short loc_180007A16
0x1800079f0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800079f7  test    rax, rax
0x1800079fa  jz      short loc_180007A6F
0x1800079fc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007a03  jnz     short loc_180007A6F
0x180007a05  xor     r8d, r8d
0x180007a08  xor     edx, edx
0x180007a0a  lea     rcx, [rsp+14F0h+var_14D0]
0x180007a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a14  jmp     short loc_180007A6F
0x180007a16  mov     ebx, 800h
0x180007a1b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007a22  test    rax, rax
0x180007a25  jz      short loc_180007A44
0x180007a27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007a2e  jnz     short loc_180007A44
0x180007a30  mov     r8d, ebx
0x180007a33  lea     rdx, [rbp+13F0h+OutputString]
0x180007a3a  lea     rcx, [rsp+14F0h+var_14D0]
0x180007a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a44  cmp     [rbp+13F0h+OutputString], r15w
0x180007a4c  jnz     short loc_180007A62
0x180007a4e  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180007a53  mov     rdx, rbx; unsigned __int16 *
0x180007a56  lea     rcx, [rbp+13F0h+OutputString]; this
0x180007a5d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007a62  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180007a69  call    cs:__imp_OutputDebugStringW
0x180007a6f  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180007a74  jnz     short loc_180007A7F
0x180007a76  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180007a7d  jz      short loc_180007A91
0x180007a7f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007a86  test    rax, rax
0x180007a89  jz      short loc_180007A91
0x180007a8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a90  nop
0x180007a91  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180007a96  jnz     short loc_180007ABE
0x180007a98  mov     rcx, [rbp+13F0h+var_30]
0x180007a9f  xor     rcx, rsp; StackCookie
0x180007aa2  call    __security_check_cookie
0x180007aa7  mov     rbx, [rsp+14F0h+arg_10]
0x180007aaf  add     rsp, 14D0h
0x180007ab6  pop     r15
0x180007ab8  pop     r14
0x180007aba  pop     rdi
0x180007abb  pop     rsi
0x180007abc  pop     rbp
0x180007abd  retn
0x180007abe  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007ac3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007ac9  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
