# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x140004778`
- end: `0x1400049ea`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `626`
- prototype: `void __fastcall __noreturn(unsigned __int64, unsigned int, __int64, __int64, int, unsigned __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140002aac`

## callees

- `0x14000142c`
- `0x1400018f0`
- `0x140001b30`
- `0x1400029fc`
- `0x140004778`
- `0x14000f460`
- `0x14000f4d0`
- `0x14000f550`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000481a`
- `KERNEL32!GetCurrentThreadId` at `0x14000481a`
- `KERNEL32!OutputDebugStringW` at `0x1400049b7`
- `KERNEL32!OutputDebugStringW` at `0x1400049b7`
- `KERNEL32!IsDebuggerPresent` at `0x140004925`
- `KERNEL32!IsDebuggerPresent` at `0x140004925`

## string_xrefs

- `0x140004824`: `C:\__w\1\s\UCPDMgr\wil\Microsoft.Windows.Wil.Internal.0.2.159\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        unsigned __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        __int64 a7)
{
  int v9; // edx
  unsigned int v10; // edi
  int v11; // ecx
  const struct wil::FailureInfo *v12; // rdx
  __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v14; // r9
  unsigned __int64 v15[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v16[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v15, 0, 0x98u);
  OutputString[0] = 0;
  v16[0] = 0;
  v15[1] = *(_QWORD *)a7;
  v10 = wil::details::RecordFailFast((wil::details *)LODWORD(v15[1]), v9);
  LODWORD(v15[0]) = 3;
  v11 = 0;
  if ( *(_DWORD *)(a7 + 8) == 1 )
    v11 = 8;
  HIDWORD(v15[0]) = v11;
  LODWORD(v15[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v15[3] = 0;
  LODWORD(v15[4]) = GetCurrentThreadId();
  v15[7] = (unsigned __int64)"C:\\__w\\1\\s\\UCPDMgr\\wil\\Microsoft.Windows.Wil.Internal.0.2.159\\inc\\wil\\opensource\\wil\\resource.h";
  v15[8] = __PAIR64__(v10, a2);
  v15[5] = 0;
  v15[6] = 0;
  v15[17] = a6;
  v15[18] = a1;
  memset(&v15[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v15[16] = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
  else
    v15[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v15, v16, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v15);
  if ( wil::details::g_pfnOriginateCallback && (v15[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v15);
  if ( SLODWORD(v15[1]) >= 0 )
  {
    LODWORD(v15[1]) = -2147418113;
    HIDWORD(v15[1]) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v12);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (v15[0] & 0x200000000LL) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v15, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)v15, v14);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(v15, 0, 0);
  }
  if ( (v15[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  }
  wil::details::WilFailFast((wil::details *)v15, v12);
}

```

## disassembly

```asm
0x140004778  mov     [rsp-8+arg_10], rbx
0x14000477d  mov     [rsp-8+arg_18], rsi
0x140004782  push    rbp
0x140004783  push    rdi
0x140004784  push    r12
0x140004786  push    r14
0x140004788  push    r15
0x14000478a  lea     rbp, [rsp-13C0h]
0x140004792  mov     eax, 14C0h
0x140004797  call    _alloca_probe
0x14000479c  sub     rsp, rax
0x14000479f  mov     r14d, edx
0x1400047a2  mov     r15, rcx
0x1400047a5  mov     rsi, [rbp+13E0h+arg_28]
0x1400047ac  xor     edx, edx; Val
0x1400047ae  mov     r8d, 98h; Size
0x1400047b4  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x1400047b9  call    memset
0x1400047be  nop
0x1400047bf  xor     r12d, r12d
0x1400047c2  mov     [rbp+13E0h+OutputString], r12w
0x1400047ca  mov     [rbp+13E0h+var_1420], r12b
0x1400047ce  mov     rbx, [rbp+13E0h+arg_30]
0x1400047d5  mov     ecx, [rbx]; this
0x1400047d7  mov     [rsp+14E0h+var_14B8], ecx
0x1400047db  mov     eax, [rbx+4]
0x1400047de  mov     [rsp+14E0h+var_14B4], eax
0x1400047e2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400047e7  mov     edi, eax
0x1400047e9  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1400047f1  mov     ecx, r12d
0x1400047f4  lea     eax, [r12+8]
0x1400047f9  cmp     dword ptr [rbx+8], 1
0x1400047fd  cmovz   ecx, eax
0x140004800  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x140004804  lea     ecx, [rax-7]
0x140004807  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000480f  inc     ecx
0x140004811  mov     [rsp+14E0h+var_14B0], ecx
0x140004815  mov     [rsp+14E0h+var_14A8], r12
0x14000481a  call    cs:__imp_GetCurrentThreadId
0x140004820  mov     [rsp+14E0h+var_14A0], eax
0x140004824  lea     rax, aCW1SUcpdmgrWil; "C:\\__w\\1\\s\\UCPDMgr\\wil\\Microsoft."...
0x14000482b  mov     [rsp+14E0h+var_1488], rax
0x140004830  mov     [rsp+14E0h+var_1480], r14d
0x140004835  mov     [rsp+14E0h+var_147C], edi
0x140004839  mov     [rsp+14E0h+var_1498], r12
0x14000483e  mov     [rsp+14E0h+var_1490], r12
0x140004843  mov     [rbp+13E0h+var_1438], rsi
0x140004847  mov     [rbp+13E0h+var_1430], r15
0x14000484b  mov     [rsp+14E0h+var_1478], r12
0x140004850  xorps   xmm0, xmm0
0x140004853  xor     eax, eax
0x140004855  movups  [rbp+13E0h+var_1458], xmm0
0x140004859  mov     [rbp+13E0h+var_1448], rax
0x14000485d  xorps   xmm1, xmm1
0x140004860  movups  [rsp+14E0h+var_1470], xmm1
0x140004865  mov     [rbp+13E0h+var_1460], rax
0x140004869  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004870  test    rax, rax
0x140004873  jz      short loc_140004880
0x140004875  call    _guard_dispatch_icall
0x14000487a  mov     [rbp+13E0h+var_1440], rax
0x14000487e  jmp     short loc_140004884
0x140004880  mov     [rbp+13E0h+var_1440], r12
0x140004884  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000488b  test    rax, rax
0x14000488e  jz      short loc_14000489A
0x140004890  lea     rcx, [rsp+14E0h+var_14C0]
0x140004895  call    _guard_dispatch_icall
0x14000489a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400048a1  test    rax, rax
0x1400048a4  jz      short loc_1400048BA
0x1400048a6  mov     r8d, 400h
0x1400048ac  lea     rdx, [rbp+13E0h+var_1420]
0x1400048b0  lea     rcx, [rsp+14E0h+var_14C0]
0x1400048b5  call    _guard_dispatch_icall
0x1400048ba  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400048c1  test    rax, rax
0x1400048c4  jz      short loc_1400048D0
0x1400048c6  lea     rcx, [rsp+14E0h+var_14C0]
0x1400048cb  call    _guard_dispatch_icall
0x1400048d0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400048d7  test    rax, rax
0x1400048da  jz      short loc_1400048ED
0x1400048dc  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1400048e1  jnz     short loc_1400048ED
0x1400048e3  lea     rcx, [rsp+14E0h+var_14C0]
0x1400048e8  call    _guard_dispatch_icall
0x1400048ed  cmp     [rsp+14E0h+var_14B8], r12d
0x1400048f2  jl      short loc_140004906
0x1400048f4  mov     ecx, 8000FFFFh; this
0x1400048f9  mov     [rsp+14E0h+var_14B8], ecx
0x1400048fd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004902  mov     [rsp+14E0h+var_14B4], eax
0x140004906  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000490d  jnz     short loc_140004937
0x14000490f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004916  test    rax, rax
0x140004919  jz      short loc_140004925
0x14000491b  call    _guard_dispatch_icall
0x140004920  movzx   ecx, al
0x140004923  jmp     short loc_140004933
0x140004925  call    cs:__imp_IsDebuggerPresent
0x14000492b  mov     ecx, r12d
0x14000492e  test    eax, eax
0x140004930  setnz   cl
0x140004933  test    ecx, ecx
0x140004935  jz      short loc_14000493E
0x140004937  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x14000493c  jz      short loc_140004964
0x14000493e  mov     rax, cs:g_pfnResultLoggingCallback
0x140004945  test    rax, rax
0x140004948  jz      short loc_1400049BD
0x14000494a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140004951  jnz     short loc_1400049BD
0x140004953  xor     r8d, r8d
0x140004956  xor     edx, edx
0x140004958  lea     rcx, [rsp+14E0h+var_14C0]
0x14000495d  call    _guard_dispatch_icall
0x140004962  jmp     short loc_1400049BD
0x140004964  mov     ebx, 800h
0x140004969  mov     rax, cs:g_pfnResultLoggingCallback
0x140004970  test    rax, rax
0x140004973  jz      short loc_140004992
0x140004975  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000497c  jnz     short loc_140004992
0x14000497e  mov     r8d, ebx
0x140004981  lea     rdx, [rbp+13E0h+OutputString]
0x140004988  lea     rcx, [rsp+14E0h+var_14C0]
0x14000498d  call    _guard_dispatch_icall
0x140004992  cmp     [rbp+13E0h+OutputString], r12w
0x14000499a  jnz     short loc_1400049B0
0x14000499c  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x1400049a1  mov     rdx, rbx; wchar_t *
0x1400049a4  lea     rcx, [rbp+13E0h+OutputString]; this
0x1400049ab  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1400049b0  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x1400049b7  call    cs:__imp_OutputDebugStringW
0x1400049bd  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x1400049c2  jnz     short loc_1400049CD
0x1400049c4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400049cb  jz      short loc_1400049DF
0x1400049cd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400049d4  test    rax, rax
0x1400049d7  jz      short loc_1400049DF
0x1400049d9  call    _guard_dispatch_icall
0x1400049de  nop
0x1400049df  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1400049e4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
