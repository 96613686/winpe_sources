# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000e864`
- end: `0x14000eb35`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `721`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14000e1bc`

## callees

- `0x140008660`
- `0x1400090ec`
- `0x1400098f8`
- `0x14000bc6c`
- `0x14000c0e4`
- `0x14000d200`
- `0x14000d2dc`
- `0x14000e864`
- `0x140010c3c`
- `0x1400167a0`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e955`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e955`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000eacb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000eacb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000ea46`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000ea46`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // edx
  int v10; // ebx
  int v11; // edx
  int v12; // ebx
  int v13; // ecx
  wchar_t *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  wil::details *v18; // [rsp+30h] [rbp-D0h]
  int v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+44h] [rbp-BCh]
  int v21; // [rsp+48h] [rbp-B8h]
  int v22; // [rsp+4Ch] [rbp-B4h]
  signed __int32 v23; // [rsp+50h] [rbp-B0h]
  __int64 v24; // [rsp+58h] [rbp-A8h]
  DWORD CurrentThreadId; // [rsp+60h] [rbp-A0h]
  __int64 v26; // [rsp+68h] [rbp-98h]
  __int64 v27; // [rsp+70h] [rbp-90h]
  const char *v28; // [rsp+78h] [rbp-88h]
  int v29; // [rsp+80h] [rbp-80h]
  int v30; // [rsp+84h] [rbp-7Ch]
  __int64 v31; // [rsp+88h] [rbp-78h]
  __int128 v32; // [rsp+90h] [rbp-70h]
  __int64 v33; // [rsp+A0h] [rbp-60h]
  __int128 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B8h] [rbp-48h]
  __int64 ModuleName; // [rsp+C0h] [rbp-40h]
  __int64 v37; // [rsp+C8h] [rbp-38h]
  __int64 v38; // [rsp+D0h] [rbp-30h]
  char v39[1024]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR OutputString[2048]; // [rsp+4E0h] [rbp+3E0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v10 = *a7;
  v21 = v10;
  v22 = a7[1];
  if ( v10 >= 0 )
  {
    v10 = -2147024228;
    LODWORD(v18) = -2147024228;
    wil::details::ReportFailure_Hr<2>(
      a1,
      a2,
      (__int64)"onecore\\base\\telemetry\\utc\\include\\StringUtils.h",
      0,
      0,
      a6,
      v18);
    v21 = -2147024228;
    v22 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v11);
  }
  v12 = wil::details::RecordLog((wil::details *)(unsigned int)v10, v9);
  v19 = 2;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v20 = v13;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v28 = "onecore\\base\\telemetry\\utc\\include\\StringUtils.h";
  v29 = a2;
  v30 = v12;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
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
      wil::GetFailureLogString((wil *)OutputString, v14, (unsigned __int64)&v19, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, (const struct wil::FailureInfo *)v14);
}

```

## disassembly

```asm
0x14000e864  mov     [rsp-8+arg_10], rbx
0x14000e869  push    rbp
0x14000e86a  push    rsi
0x14000e86b  push    rdi
0x14000e86c  push    r12
0x14000e86e  push    r13
0x14000e870  push    r14
0x14000e872  push    r15
0x14000e874  lea     rbp, [rsp-13F0h]
0x14000e87c  mov     eax, 14F0h
0x14000e881  call    _alloca_probe
0x14000e886  sub     rsp, rax
0x14000e889  mov     rax, cs:__security_cookie
0x14000e890  xor     rax, rsp
0x14000e893  mov     [rbp+1420h+var_40], rax
0x14000e89a  mov     r14d, edx
0x14000e89d  mov     rsi, rcx
0x14000e8a0  mov     r15, [rbp+1420h+arg_28]
0x14000e8a7  xor     edx, edx; Val
0x14000e8a9  mov     r8d, 98h; Size
0x14000e8af  lea     rcx, [rsp+1520h+var_14E0]; void *
0x14000e8b4  call    memset_0
0x14000e8b9  nop
0x14000e8ba  xor     r12d, r12d
0x14000e8bd  mov     [rbp+1420h+OutputString], r12w
0x14000e8c5  mov     [rbp+1420h+var_1440], r12b
0x14000e8c9  mov     rdi, [rbp+1420h+arg_30]
0x14000e8d0  mov     ebx, [rdi]
0x14000e8d2  mov     [rsp+1520h+var_14D8], ebx
0x14000e8d6  mov     eax, [rdi+4]
0x14000e8d9  mov     [rsp+1520h+var_14D4], eax
0x14000e8dd  lea     r13, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x14000e8e4  test    ebx, ebx
0x14000e8e6  js      short loc_14000E91B
0x14000e8e8  mov     ebx, 8007029Ch
0x14000e8ed  mov     dword ptr [rsp+1520h+var_14F0], ebx; wil::details *
0x14000e8f1  mov     [rsp+1520h+var_14F8], r15; __int64
0x14000e8f6  mov     [rsp+1520h+var_1500], r12; __int64
0x14000e8fb  xor     r9d, r9d; int
0x14000e8fe  mov     r8, r13; int
0x14000e901  mov     edx, r14d; int
0x14000e904  mov     rcx, rsi; int
0x14000e907  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000e90c  mov     [rsp+1520h+var_14D8], ebx
0x14000e910  mov     ecx, ebx; this
0x14000e912  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000e917  mov     [rsp+1520h+var_14D4], eax
0x14000e91b  mov     ecx, ebx; this
0x14000e91d  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000e922  mov     ebx, eax
0x14000e924  mov     dword ptr [rsp+1520h+var_14E0], 2
0x14000e92c  mov     ecx, r12d
0x14000e92f  mov     eax, 8
0x14000e934  cmp     dword ptr [rdi+8], 1
0x14000e938  cmovz   ecx, eax
0x14000e93b  mov     dword ptr [rsp+1520h+var_14E0+4], ecx
0x14000e93f  lea     ecx, [rax-7]
0x14000e942  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000e94a  inc     ecx
0x14000e94c  mov     [rsp+1520h+var_14D0], ecx
0x14000e950  mov     [rsp+1520h+var_14C8], r12
0x14000e955  call    cs:__imp_GetCurrentThreadId
0x14000e95b  mov     [rsp+1520h+var_14C0], eax
0x14000e95f  mov     [rsp+1520h+var_14A8], r13
0x14000e964  mov     [rbp+1420h+var_14A0], r14d
0x14000e968  mov     [rbp+1420h+var_149C], ebx
0x14000e96b  mov     [rsp+1520h+var_14B8], r12
0x14000e970  mov     [rsp+1520h+var_14B0], r12
0x14000e975  mov     [rbp+1420h+var_1458], r15
0x14000e979  mov     [rbp+1420h+var_1450], rsi
0x14000e97d  mov     [rbp+1420h+var_1498], r12
0x14000e981  xorps   xmm0, xmm0
0x14000e984  xor     eax, eax
0x14000e986  movups  [rbp+1420h+var_1478], xmm0
0x14000e98a  mov     [rbp+1420h+var_1468], rax
0x14000e98e  xorps   xmm1, xmm1
0x14000e991  movups  [rbp+1420h+var_1490], xmm1
0x14000e995  mov     [rbp+1420h+var_1480], rax
0x14000e999  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000e9a0  test    rax, rax
0x14000e9a3  jz      short loc_14000E9B0
0x14000e9a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e9aa  mov     [rbp+1420h+var_1460], rax
0x14000e9ae  jmp     short loc_14000E9B4
0x14000e9b0  mov     [rbp+1420h+var_1460], r12
0x14000e9b4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000e9bb  test    rax, rax
0x14000e9be  jz      short loc_14000E9CA
0x14000e9c0  lea     rcx, [rsp+1520h+var_14E0]
0x14000e9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e9ca  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000e9d1  test    rax, rax
0x14000e9d4  jz      short loc_14000E9EA
0x14000e9d6  mov     r8d, 400h
0x14000e9dc  lea     rdx, [rbp+1420h+var_1440]
0x14000e9e0  lea     rcx, [rsp+1520h+var_14E0]
0x14000e9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e9ea  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000e9f1  test    rax, rax
0x14000e9f4  jz      short loc_14000EA00
0x14000e9f6  lea     rcx, [rsp+1520h+var_14E0]
0x14000e9fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ea00  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000ea07  test    rax, rax
0x14000ea0a  jz      short loc_14000EA1D
0x14000ea0c  test    byte ptr [rsp+1520h+var_14E0+4], 2
0x14000ea11  jnz     short loc_14000EA1D
0x14000ea13  lea     rcx, [rsp+1520h+var_14E0]
0x14000ea18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ea1d  cmp     [rsp+1520h+var_14D8], r12d
0x14000ea22  jge     loc_14000EB2F
0x14000ea28  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000ea2f  jnz     short loc_14000EA50
0x14000ea31  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000ea38  test    rax, rax
0x14000ea3b  jz      short loc_14000EA46
0x14000ea3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ea42  test    al, al
0x14000ea44  jmp     short loc_14000EA4E
0x14000ea46  call    cs:__imp_IsDebuggerPresent
0x14000ea4c  test    eax, eax
0x14000ea4e  jz      short loc_14000EA57
0x14000ea50  test    byte ptr [rsp+1520h+var_14E0+4], 2
0x14000ea55  jz      short loc_14000EA7D
0x14000ea57  mov     rax, cs:g_pfnResultLoggingCallback
0x14000ea5e  test    rax, rax
0x14000ea61  jz      short loc_14000EAD1
0x14000ea63  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000ea6a  jnz     short loc_14000EAD1
0x14000ea6c  xor     r8d, r8d
0x14000ea6f  xor     edx, edx
0x14000ea71  lea     rcx, [rsp+1520h+var_14E0]
0x14000ea76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ea7b  jmp     short loc_14000EAD1
0x14000ea7d  mov     rax, cs:g_pfnResultLoggingCallback
0x14000ea84  test    rax, rax
0x14000ea87  jz      short loc_14000EAA9
0x14000ea89  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000ea90  jnz     short loc_14000EAA9
0x14000ea92  mov     r8d, 800h
0x14000ea98  lea     rdx, [rbp+1420h+OutputString]
0x14000ea9f  lea     rcx, [rsp+1520h+var_14E0]
0x14000eaa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eaa9  cmp     [rbp+1420h+OutputString], r12w
0x14000eab1  jnz     short loc_14000EAC4
0x14000eab3  lea     r8, [rsp+1520h+var_14E0]; unsigned __int64
0x14000eab8  lea     rcx, [rbp+1420h+OutputString]; this
0x14000eabf  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x14000eac4  lea     rcx, [rbp+1420h+OutputString]; lpOutputString
0x14000eacb  call    cs:__imp_OutputDebugStringW
0x14000ead1  test    byte ptr [rsp+1520h+var_14E0+4], 4
0x14000ead6  jnz     short loc_14000EAE1
0x14000ead8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000eadf  jz      short loc_14000EAF3
0x14000eae1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000eae8  test    rax, rax
0x14000eaeb  jz      short loc_14000EAF3
0x14000eaed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000eaf2  nop
0x14000eaf3  test    byte ptr [rsp+1520h+var_14E0+4], 1
0x14000eaf8  jnz     short loc_14000EB24
0x14000eafa  mov     rcx, [rbp+1420h+var_40]
0x14000eb01  xor     rcx, rsp; StackCookie
0x14000eb04  call    __security_check_cookie
0x14000eb09  mov     rbx, [rsp+1520h+arg_10]
0x14000eb11  add     rsp, 14F0h
0x14000eb18  pop     r15
0x14000eb1a  pop     r14
0x14000eb1c  pop     r13
0x14000eb1e  pop     r12
0x14000eb20  pop     rdi
0x14000eb21  pop     rsi
0x14000eb22  pop     rbp
0x14000eb23  retn
0x14000eb24  lea     rcx, [rsp+1520h+var_14E0]; this
0x14000eb29  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000eb2f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
