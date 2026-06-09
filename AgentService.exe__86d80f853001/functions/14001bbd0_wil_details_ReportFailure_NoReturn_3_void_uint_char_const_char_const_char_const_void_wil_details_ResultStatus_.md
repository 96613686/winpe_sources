# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x14001bbd0`
- end: `0x14001be39`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14001b984`

## callees

- `0x140004a78`
- `0x14001bbd0`
- `0x14001cf14`
- `0x14001d6bc`
- `0x14001dde0`
- `0x14001ed80`
- `0x14008f070`
- `0x14009b010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x14001be06`
- `KERNEL32!OutputDebugStringW` at `0x14001be06`
- `KERNEL32!GetCurrentThreadId` at `0x14001bc72`
- `KERNEL32!GetCurrentThreadId` at `0x14001bc72`
- `KERNEL32!IsDebuggerPresent` at `0x14001bd7c`
- `KERNEL32!IsDebuggerPresent` at `0x14001bd7c`

## string_xrefs

- `0x14001bc7c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // edx
  int v10; // edi
  int v11; // ecx
  const struct wil::FailureInfo *v12; // rdx
  __int64 v13; // rcx
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
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v10 = wil::details::RecordFailFast((wil::details *)(unsigned int)v18, v9);
  v16 = 3;
  v11 = 0;
  if ( a7[2] == 1 )
    v11 = 8;
  v17 = v11;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v26 = a2;
  v27 = v10;
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
  {
    v18 = -2147418113;
    v19 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v12);
  }
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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( (v17 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v13);
  }
  wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x14001bbd0  mov     [rsp-8+arg_10], rbx
0x14001bbd5  mov     [rsp-8+arg_18], rsi
0x14001bbda  push    rbp
0x14001bbdb  push    rdi
0x14001bbdc  push    r12
0x14001bbde  push    r14
0x14001bbe0  push    r15
0x14001bbe2  lea     rbp, [rsp-13C0h]
0x14001bbea  mov     eax, 14C0h
0x14001bbef  call    _alloca_probe
0x14001bbf4  sub     rsp, rax
0x14001bbf7  mov     r14d, edx
0x14001bbfa  mov     r15, rcx
0x14001bbfd  mov     rsi, [rbp+13E0h+arg_28]
0x14001bc04  xor     edx, edx; Val
0x14001bc06  mov     r8d, 98h; Size
0x14001bc0c  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x14001bc11  call    memset_0
0x14001bc16  nop
0x14001bc17  xor     r12d, r12d
0x14001bc1a  mov     [rbp+13E0h+OutputString], r12w
0x14001bc22  mov     [rbp+13E0h+var_1420], r12b
0x14001bc26  mov     rbx, [rbp+13E0h+arg_30]
0x14001bc2d  mov     ecx, [rbx]; this
0x14001bc2f  mov     [rsp+14E0h+var_14B8], ecx
0x14001bc33  mov     eax, [rbx+4]
0x14001bc36  mov     [rsp+14E0h+var_14B4], eax
0x14001bc3a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14001bc3f  mov     edi, eax
0x14001bc41  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x14001bc49  mov     ecx, r12d
0x14001bc4c  lea     eax, [r12+8]
0x14001bc51  cmp     dword ptr [rbx+8], 1
0x14001bc55  cmovz   ecx, eax
0x14001bc58  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x14001bc5c  lea     ecx, [rax-7]
0x14001bc5f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14001bc67  inc     ecx
0x14001bc69  mov     [rsp+14E0h+var_14B0], ecx
0x14001bc6d  mov     [rsp+14E0h+var_14A8], r12
0x14001bc72  call    cs:__imp_GetCurrentThreadId
0x14001bc78  mov     [rsp+14E0h+var_14A0], eax
0x14001bc7c  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14001bc83  mov     [rsp+14E0h+var_1488], rax
0x14001bc88  mov     [rsp+14E0h+var_1480], r14d
0x14001bc8d  mov     [rsp+14E0h+var_147C], edi
0x14001bc91  mov     [rsp+14E0h+var_1498], r12
0x14001bc96  mov     [rsp+14E0h+var_1490], r12
0x14001bc9b  mov     [rbp+13E0h+var_1438], rsi
0x14001bc9f  mov     [rbp+13E0h+var_1430], r15
0x14001bca3  mov     [rsp+14E0h+var_1478], r12
0x14001bca8  xorps   xmm0, xmm0
0x14001bcab  xor     eax, eax
0x14001bcad  movups  [rbp+13E0h+var_1458], xmm0
0x14001bcb1  mov     [rbp+13E0h+var_1448], rax
0x14001bcb5  xorps   xmm1, xmm1
0x14001bcb8  movups  [rsp+14E0h+var_1470], xmm1
0x14001bcbd  mov     [rbp+13E0h+var_1460], rax
0x14001bcc1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14001bcc8  test    rax, rax
0x14001bccb  jz      short loc_14001BCD8
0x14001bccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bcd2  mov     [rbp+13E0h+var_1440], rax
0x14001bcd6  jmp     short loc_14001BCDC
0x14001bcd8  mov     [rbp+13E0h+var_1440], r12
0x14001bcdc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14001bce3  test    rax, rax
0x14001bce6  jz      short loc_14001BCF2
0x14001bce8  lea     rcx, [rsp+14E0h+var_14C0]
0x14001bced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bcf2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14001bcf9  test    rax, rax
0x14001bcfc  jz      short loc_14001BD12
0x14001bcfe  mov     r8d, 400h
0x14001bd04  lea     rdx, [rbp+13E0h+var_1420]
0x14001bd08  lea     rcx, [rsp+14E0h+var_14C0]
0x14001bd0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bd12  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14001bd19  test    rax, rax
0x14001bd1c  jz      short loc_14001BD28
0x14001bd1e  lea     rcx, [rsp+14E0h+var_14C0]
0x14001bd23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bd28  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14001bd2f  test    rax, rax
0x14001bd32  jz      short loc_14001BD45
0x14001bd34  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x14001bd39  jnz     short loc_14001BD45
0x14001bd3b  lea     rcx, [rsp+14E0h+var_14C0]
0x14001bd40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bd45  cmp     [rsp+14E0h+var_14B8], r12d
0x14001bd4a  jl      short loc_14001BD5E
0x14001bd4c  mov     ecx, 8000FFFFh; this
0x14001bd51  mov     [rsp+14E0h+var_14B8], ecx
0x14001bd55  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14001bd5a  mov     [rsp+14E0h+var_14B4], eax
0x14001bd5e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14001bd65  jnz     short loc_14001BD86
0x14001bd67  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14001bd6e  test    rax, rax
0x14001bd71  jz      short loc_14001BD7C
0x14001bd73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bd78  test    al, al
0x14001bd7a  jmp     short loc_14001BD84
0x14001bd7c  call    cs:__imp_IsDebuggerPresent
0x14001bd82  test    eax, eax
0x14001bd84  jz      short loc_14001BD8D
0x14001bd86  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x14001bd8b  jz      short loc_14001BDB3
0x14001bd8d  mov     rax, cs:g_pfnResultLoggingCallback
0x14001bd94  test    rax, rax
0x14001bd97  jz      short loc_14001BE0C
0x14001bd99  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14001bda0  jnz     short loc_14001BE0C
0x14001bda2  xor     r8d, r8d
0x14001bda5  xor     edx, edx
0x14001bda7  lea     rcx, [rsp+14E0h+var_14C0]
0x14001bdac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bdb1  jmp     short loc_14001BE0C
0x14001bdb3  mov     ebx, 800h
0x14001bdb8  mov     rax, cs:g_pfnResultLoggingCallback
0x14001bdbf  test    rax, rax
0x14001bdc2  jz      short loc_14001BDE1
0x14001bdc4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14001bdcb  jnz     short loc_14001BDE1
0x14001bdcd  mov     r8d, ebx
0x14001bdd0  lea     rdx, [rbp+13E0h+OutputString]
0x14001bdd7  lea     rcx, [rsp+14E0h+var_14C0]
0x14001bddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bde1  cmp     [rbp+13E0h+OutputString], r12w
0x14001bde9  jnz     short loc_14001BDFF
0x14001bdeb  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x14001bdf0  mov     rdx, rbx; wchar_t *
0x14001bdf3  lea     rcx, [rbp+13E0h+OutputString]; this
0x14001bdfa  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x14001bdff  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x14001be06  call    cs:__imp_OutputDebugStringW
0x14001be0c  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x14001be11  jnz     short loc_14001BE1C
0x14001be13  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14001be1a  jz      short loc_14001BE2E
0x14001be1c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14001be23  test    rax, rax
0x14001be26  jz      short loc_14001BE2E
0x14001be28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001be2d  nop
0x14001be2e  lea     rcx, [rsp+14E0h+var_14C0]; this
0x14001be33  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
