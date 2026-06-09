# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000bbe0`
- end: `0x18000be40`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000b97c`

## callees

- `0x18000a684`
- `0x18000aa6c`
- `0x18000add0`
- `0x18000bbe0`
- `0x18000f604`
- `0x18001972e`
- `0x180019820`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bc81`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bc81`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000be0e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000be0e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bd84`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bd84`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x18000bbe0  mov     [rsp-8+arg_18], rbx
0x18000bbe5  push    rbp
0x18000bbe6  push    rsi
0x18000bbe7  push    rdi
0x18000bbe8  push    r12
0x18000bbea  push    r13
0x18000bbec  push    r14
0x18000bbee  push    r15
0x18000bbf0  lea     rbp, [rsp-13C0h]
0x18000bbf8  mov     eax, 14C0h
0x18000bbfd  call    _alloca_probe
0x18000bc02  sub     rsp, rax
0x18000bc05  mov     rsi, [rbp+13F0h+arg_28]
0x18000bc0c  mov     r15, r8
0x18000bc0f  mov     r14d, edx
0x18000bc12  mov     r12, rcx
0x18000bc15  xor     edx, edx; Val
0x18000bc17  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000bc1c  mov     r8d, 98h; Size
0x18000bc22  call    memset_0
0x18000bc27  mov     rbx, [rbp+13F0h+arg_30]
0x18000bc2e  xor     r13d, r13d
0x18000bc31  mov     [rbp+13F0h+OutputString], r13w
0x18000bc39  mov     [rbp+13F0h+var_1430], r13b
0x18000bc3d  mov     ecx, [rbx]; this
0x18000bc3f  mov     eax, [rbx+4]
0x18000bc42  mov     [rsp+14F0h+var_14C8], ecx
0x18000bc46  mov     [rsp+14F0h+var_14C4], eax
0x18000bc4a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000bc4f  cmp     dword ptr [rbx+8], 1
0x18000bc53  mov     edi, eax
0x18000bc55  lea     eax, [r13+8]
0x18000bc59  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000bc61  mov     ecx, r13d
0x18000bc64  cmovz   ecx, eax
0x18000bc67  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000bc6b  lea     ecx, [rax-7]
0x18000bc6e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000bc76  inc     ecx
0x18000bc78  mov     [rsp+14F0h+var_14B8], r13
0x18000bc7d  mov     [rsp+14F0h+var_14C0], ecx
0x18000bc81  call    cs:__imp_GetCurrentThreadId
0x18000bc87  xorps   xmm0, xmm0
0x18000bc8a  mov     [rsp+14F0h+var_1498], r15
0x18000bc8f  mov     [rsp+14F0h+var_14B0], eax
0x18000bc93  xorps   xmm1, xmm1
0x18000bc96  xor     eax, eax
0x18000bc98  mov     [rsp+14F0h+var_1490], r14d
0x18000bc9d  mov     [rbp+13F0h+var_1458], rax
0x18000bca1  mov     [rbp+13F0h+var_1470], rax
0x18000bca5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000bcac  mov     [rsp+14F0h+var_148C], edi
0x18000bcb0  mov     [rsp+14F0h+var_14A8], r13
0x18000bcb5  mov     [rsp+14F0h+var_14A0], r13
0x18000bcba  mov     [rbp+13F0h+var_1448], rsi
0x18000bcbe  mov     [rbp+13F0h+var_1440], r12
0x18000bcc2  mov     [rsp+14F0h+var_1488], r13
0x18000bcc7  movups  [rbp+13F0h+var_1468], xmm0
0x18000bccb  movups  [rsp+14F0h+var_1480], xmm1
0x18000bcd0  test    rax, rax
0x18000bcd3  jz      short loc_18000BCE0
0x18000bcd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcda  mov     [rbp+13F0h+var_1450], rax
0x18000bcde  jmp     short loc_18000BCE4
0x18000bce0  mov     [rbp+13F0h+var_1450], r13
0x18000bce4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000bceb  test    rax, rax
0x18000bcee  jz      short loc_18000BCFA
0x18000bcf0  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bcf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcfa  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000bd01  test    rax, rax
0x18000bd04  jz      short loc_18000BD1A
0x18000bd06  mov     r8d, 400h
0x18000bd0c  lea     rdx, [rbp+13F0h+var_1430]
0x18000bd10  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bd15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd1a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bd21  test    rax, rax
0x18000bd24  jz      short loc_18000BD30
0x18000bd26  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bd2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd30  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bd37  test    rax, rax
0x18000bd3a  jz      short loc_18000BD4D
0x18000bd3c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000bd41  jnz     short loc_18000BD4D
0x18000bd43  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bd48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd4d  cmp     [rsp+14F0h+var_14C8], r13d
0x18000bd52  jl      short loc_18000BD66
0x18000bd54  mov     ecx, 8000FFFFh; this
0x18000bd59  mov     [rsp+14F0h+var_14C8], ecx
0x18000bd5d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000bd62  mov     [rsp+14F0h+var_14C4], eax
0x18000bd66  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000bd6d  jnz     short loc_18000BD8E
0x18000bd6f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000bd76  test    rax, rax
0x18000bd79  jz      short loc_18000BD84
0x18000bd7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd80  test    al, al
0x18000bd82  jmp     short loc_18000BD8C
0x18000bd84  call    cs:__imp_IsDebuggerPresent
0x18000bd8a  test    eax, eax
0x18000bd8c  jz      short loc_18000BD95
0x18000bd8e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000bd93  jz      short loc_18000BDBB
0x18000bd95  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bd9c  test    rax, rax
0x18000bd9f  jz      short loc_18000BE14
0x18000bda1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000bda8  jnz     short loc_18000BE14
0x18000bdaa  xor     r8d, r8d
0x18000bdad  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bdb2  xor     edx, edx
0x18000bdb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdb9  jmp     short loc_18000BE14
0x18000bdbb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bdc2  mov     ebx, 800h
0x18000bdc7  test    rax, rax
0x18000bdca  jz      short loc_18000BDE9
0x18000bdcc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000bdd3  jnz     short loc_18000BDE9
0x18000bdd5  mov     r8d, ebx
0x18000bdd8  lea     rdx, [rbp+13F0h+OutputString]
0x18000bddf  lea     rcx, [rsp+14F0h+var_14D0]
0x18000bde4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bde9  cmp     [rbp+13F0h+OutputString], r13w
0x18000bdf1  jnz     short loc_18000BE07
0x18000bdf3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000bdf8  mov     rdx, rbx; unsigned __int16 *
0x18000bdfb  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000be02  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000be07  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000be0e  call    cs:__imp_OutputDebugStringW
0x18000be14  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000be19  jnz     short loc_18000BE24
0x18000be1b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000be22  jz      short loc_18000BE35
0x18000be24  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000be2b  test    rax, rax
0x18000be2e  jz      short loc_18000BE35
0x18000be30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be35  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000be3a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
