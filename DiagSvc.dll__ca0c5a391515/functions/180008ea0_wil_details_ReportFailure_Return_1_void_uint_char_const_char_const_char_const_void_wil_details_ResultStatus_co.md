# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180008ea0`
- end: `0x180009136`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008b68`

## callees

- `0x180003fc0`
- `0x180004b78`
- `0x180008ea0`
- `0x18000cccc`
- `0x18000f080`
- `0x1800124d8`
- `0x180012744`
- `0x1800260e0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800090d0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800090d0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009046`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009046`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008f4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008f4b`

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
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180008ea0  mov     [rsp-8+arg_10], rbx
0x180008ea5  push    rbp
0x180008ea6  push    rsi
0x180008ea7  push    rdi
0x180008ea8  push    r14
0x180008eaa  push    r15
0x180008eac  lea     rbp, [rsp-13D0h]
0x180008eb4  mov     eax, 14D0h
0x180008eb9  call    _alloca_probe
0x180008ebe  sub     rsp, rax
0x180008ec1  mov     rax, cs:__security_cookie
0x180008ec8  xor     rax, rsp
0x180008ecb  mov     [rbp+13F0h+var_30], rax
0x180008ed2  mov     esi, edx
0x180008ed4  mov     r14, rcx
0x180008ed7  mov     rdi, [rbp+13F0h+arg_28]
0x180008ede  xor     edx, edx; Val
0x180008ee0  mov     r8d, 98h; Size
0x180008ee6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180008eeb  call    memset_0
0x180008ef0  nop
0x180008ef1  xor     r15d, r15d
0x180008ef4  mov     [rbp+13F0h+OutputString], r15w
0x180008efc  mov     [rbp+13F0h+var_1430], r15b
0x180008f00  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180008f07  mov     ecx, [rdx]; this
0x180008f09  mov     [rsp+14F0h+var_14C8], ecx
0x180008f0d  mov     eax, [rdx+4]
0x180008f10  mov     [rsp+14F0h+var_14C4], eax
0x180008f14  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008f19  mov     ebx, eax
0x180008f1b  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180008f23  mov     ecx, r15d
0x180008f26  lea     eax, [r15+8]
0x180008f2a  cmp     dword ptr [rdx+8], 1
0x180008f2e  cmovz   ecx, eax
0x180008f31  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180008f35  lea     ecx, [rax-7]
0x180008f38  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008f40  inc     ecx
0x180008f42  mov     [rsp+14F0h+var_14C0], ecx
0x180008f46  mov     [rsp+14F0h+var_14B8], r15
0x180008f4b  call    cs:__imp_GetCurrentThreadId
0x180008f51  mov     [rsp+14F0h+var_14B0], eax
0x180008f55  lea     rax, aWil; "wil"
0x180008f5c  mov     [rsp+14F0h+var_1498], rax
0x180008f61  mov     [rsp+14F0h+var_1490], esi
0x180008f65  mov     [rsp+14F0h+var_148C], ebx
0x180008f69  mov     [rsp+14F0h+var_14A8], r15
0x180008f6e  mov     [rsp+14F0h+var_14A0], r15
0x180008f73  mov     [rbp+13F0h+var_1448], rdi
0x180008f77  mov     [rbp+13F0h+var_1440], r14
0x180008f7b  mov     [rsp+14F0h+var_1488], r15
0x180008f80  xorps   xmm0, xmm0
0x180008f83  xor     eax, eax
0x180008f85  movups  [rbp+13F0h+var_1468], xmm0
0x180008f89  mov     [rbp+13F0h+var_1458], rax
0x180008f8d  xorps   xmm1, xmm1
0x180008f90  movups  [rsp+14F0h+var_1480], xmm1
0x180008f95  mov     [rbp+13F0h+var_1470], rax
0x180008f99  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008fa0  test    rax, rax
0x180008fa3  jz      short loc_180008FB0
0x180008fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008faa  mov     [rbp+13F0h+var_1450], rax
0x180008fae  jmp     short loc_180008FB4
0x180008fb0  mov     [rbp+13F0h+var_1450], r15
0x180008fb4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008fbb  test    rax, rax
0x180008fbe  jz      short loc_180008FCA
0x180008fc0  lea     rcx, [rsp+14F0h+var_14D0]
0x180008fc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fca  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008fd1  test    rax, rax
0x180008fd4  jz      short loc_180008FEA
0x180008fd6  mov     r8d, 400h
0x180008fdc  lea     rdx, [rbp+13F0h+var_1430]
0x180008fe0  lea     rcx, [rsp+14F0h+var_14D0]
0x180008fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fea  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008ff1  test    rax, rax
0x180008ff4  jz      short loc_180009000
0x180008ff6  lea     rcx, [rsp+14F0h+var_14D0]
0x180008ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009000  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009007  test    rax, rax
0x18000900a  jz      short loc_18000901D
0x18000900c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180009011  jnz     short loc_18000901D
0x180009013  lea     rcx, [rsp+14F0h+var_14D0]
0x180009018  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000901d  cmp     [rsp+14F0h+var_14C8], r15d
0x180009022  jge     loc_180009130
0x180009028  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000902f  jnz     short loc_180009050
0x180009031  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009038  test    rax, rax
0x18000903b  jz      short loc_180009046
0x18000903d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009042  test    al, al
0x180009044  jmp     short loc_18000904E
0x180009046  call    cs:__imp_IsDebuggerPresent
0x18000904c  test    eax, eax
0x18000904e  jz      short loc_180009057
0x180009050  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180009055  jz      short loc_18000907D
0x180009057  mov     rax, cs:g_pfnResultLoggingCallback
0x18000905e  test    rax, rax
0x180009061  jz      short loc_1800090D6
0x180009063  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000906a  jnz     short loc_1800090D6
0x18000906c  xor     r8d, r8d
0x18000906f  xor     edx, edx
0x180009071  lea     rcx, [rsp+14F0h+var_14D0]
0x180009076  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000907b  jmp     short loc_1800090D6
0x18000907d  mov     ebx, 800h
0x180009082  mov     rax, cs:g_pfnResultLoggingCallback
0x180009089  test    rax, rax
0x18000908c  jz      short loc_1800090AB
0x18000908e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009095  jnz     short loc_1800090AB
0x180009097  mov     r8d, ebx
0x18000909a  lea     rdx, [rbp+13F0h+OutputString]
0x1800090a1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800090a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090ab  cmp     [rbp+13F0h+OutputString], r15w
0x1800090b3  jnz     short loc_1800090C9
0x1800090b5  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800090ba  mov     rdx, rbx; unsigned __int16 *
0x1800090bd  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800090c4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800090c9  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800090d0  call    cs:__imp_OutputDebugStringW
0x1800090d6  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800090db  jnz     short loc_1800090E6
0x1800090dd  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800090e4  jz      short loc_1800090F8
0x1800090e6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800090ed  test    rax, rax
0x1800090f0  jz      short loc_1800090F8
0x1800090f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090f7  nop
0x1800090f8  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800090fd  jnz     short loc_180009125
0x1800090ff  mov     rcx, [rbp+13F0h+var_30]
0x180009106  xor     rcx, rsp; StackCookie
0x180009109  call    __security_check_cookie
0x18000910e  mov     rbx, [rsp+14F0h+arg_10]
0x180009116  add     rsp, 14D0h
0x18000911d  pop     r15
0x18000911f  pop     r14
0x180009121  pop     rdi
0x180009122  pop     rsi
0x180009123  pop     rbp
0x180009124  retn
0x180009125  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000912a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180009130  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
