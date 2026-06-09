# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003060`
- end: `0x1800032c9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002e0c`

## callees

- `0x180002ac8`
- `0x180003060`
- `0x180004444`
- `0x180004be4`
- `0x180005310`
- `0x1800062b0`
- `0x180010010`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003102`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003102`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000320c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000320c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003296`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003296`

## string_xrefs

- `0x18000310c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
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
0x180003060  mov     [rsp-8+arg_10], rbx
0x180003065  mov     [rsp-8+arg_18], rsi
0x18000306a  push    rbp
0x18000306b  push    rdi
0x18000306c  push    r12
0x18000306e  push    r14
0x180003070  push    r15
0x180003072  lea     rbp, [rsp-13C0h]
0x18000307a  mov     eax, 14C0h
0x18000307f  call    _alloca_probe
0x180003084  sub     rsp, rax
0x180003087  mov     r14d, edx
0x18000308a  mov     r15, rcx
0x18000308d  mov     rsi, [rbp+13E0h+arg_28]
0x180003094  xor     edx, edx; Val
0x180003096  mov     r8d, 98h; Size
0x18000309c  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x1800030a1  call    memset_0
0x1800030a6  nop
0x1800030a7  xor     r12d, r12d
0x1800030aa  mov     [rbp+13E0h+OutputString], r12w
0x1800030b2  mov     [rbp+13E0h+var_1420], r12b
0x1800030b6  mov     rbx, [rbp+13E0h+arg_30]
0x1800030bd  mov     ecx, [rbx]; this
0x1800030bf  mov     [rsp+14E0h+var_14B8], ecx
0x1800030c3  mov     eax, [rbx+4]
0x1800030c6  mov     [rsp+14E0h+var_14B4], eax
0x1800030ca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800030cf  mov     edi, eax
0x1800030d1  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1800030d9  mov     ecx, r12d
0x1800030dc  lea     eax, [r12+8]
0x1800030e1  cmp     dword ptr [rbx+8], 1
0x1800030e5  cmovz   ecx, eax
0x1800030e8  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1800030ec  lea     ecx, [rax-7]
0x1800030ef  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800030f7  inc     ecx
0x1800030f9  mov     [rsp+14E0h+var_14B0], ecx
0x1800030fd  mov     [rsp+14E0h+var_14A8], r12
0x180003102  call    cs:__imp_GetCurrentThreadId
0x180003108  mov     [rsp+14E0h+var_14A0], eax
0x18000310c  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003113  mov     [rsp+14E0h+var_1488], rax
0x180003118  mov     [rsp+14E0h+var_1480], r14d
0x18000311d  mov     [rsp+14E0h+var_147C], edi
0x180003121  mov     [rsp+14E0h+var_1498], r12
0x180003126  mov     [rsp+14E0h+var_1490], r12
0x18000312b  mov     [rbp+13E0h+var_1438], rsi
0x18000312f  mov     [rbp+13E0h+var_1430], r15
0x180003133  mov     [rsp+14E0h+var_1478], r12
0x180003138  xorps   xmm0, xmm0
0x18000313b  xor     eax, eax
0x18000313d  movups  [rbp+13E0h+var_1458], xmm0
0x180003141  mov     [rbp+13E0h+var_1448], rax
0x180003145  xorps   xmm1, xmm1
0x180003148  movups  [rsp+14E0h+var_1470], xmm1
0x18000314d  mov     [rbp+13E0h+var_1460], rax
0x180003151  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003158  test    rax, rax
0x18000315b  jz      short loc_180003168
0x18000315d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003162  mov     [rbp+13E0h+var_1440], rax
0x180003166  jmp     short loc_18000316C
0x180003168  mov     [rbp+13E0h+var_1440], r12
0x18000316c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003173  test    rax, rax
0x180003176  jz      short loc_180003182
0x180003178  lea     rcx, [rsp+14E0h+var_14C0]
0x18000317d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003182  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003189  test    rax, rax
0x18000318c  jz      short loc_1800031A2
0x18000318e  mov     r8d, 400h
0x180003194  lea     rdx, [rbp+13E0h+var_1420]
0x180003198  lea     rcx, [rsp+14E0h+var_14C0]
0x18000319d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031a2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800031a9  test    rax, rax
0x1800031ac  jz      short loc_1800031B8
0x1800031ae  lea     rcx, [rsp+14E0h+var_14C0]
0x1800031b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031b8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800031bf  test    rax, rax
0x1800031c2  jz      short loc_1800031D5
0x1800031c4  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800031c9  jnz     short loc_1800031D5
0x1800031cb  lea     rcx, [rsp+14E0h+var_14C0]
0x1800031d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031d5  cmp     [rsp+14E0h+var_14B8], r12d
0x1800031da  jl      short loc_1800031EE
0x1800031dc  mov     ecx, 8000FFFFh; this
0x1800031e1  mov     [rsp+14E0h+var_14B8], ecx
0x1800031e5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800031ea  mov     [rsp+14E0h+var_14B4], eax
0x1800031ee  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800031f5  jnz     short loc_180003216
0x1800031f7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800031fe  test    rax, rax
0x180003201  jz      short loc_18000320C
0x180003203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003208  test    al, al
0x18000320a  jmp     short loc_180003214
0x18000320c  call    cs:__imp_IsDebuggerPresent
0x180003212  test    eax, eax
0x180003214  jz      short loc_18000321D
0x180003216  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x18000321b  jz      short loc_180003243
0x18000321d  mov     rax, cs:g_pfnResultLoggingCallback
0x180003224  test    rax, rax
0x180003227  jz      short loc_18000329C
0x180003229  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003230  jnz     short loc_18000329C
0x180003232  xor     r8d, r8d
0x180003235  xor     edx, edx
0x180003237  lea     rcx, [rsp+14E0h+var_14C0]
0x18000323c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003241  jmp     short loc_18000329C
0x180003243  mov     ebx, 800h
0x180003248  mov     rax, cs:g_pfnResultLoggingCallback
0x18000324f  test    rax, rax
0x180003252  jz      short loc_180003271
0x180003254  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000325b  jnz     short loc_180003271
0x18000325d  mov     r8d, ebx
0x180003260  lea     rdx, [rbp+13E0h+OutputString]
0x180003267  lea     rcx, [rsp+14E0h+var_14C0]
0x18000326c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003271  cmp     [rbp+13E0h+OutputString], r12w
0x180003279  jnz     short loc_18000328F
0x18000327b  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180003280  mov     rdx, rbx; unsigned __int16 *
0x180003283  lea     rcx, [rbp+13E0h+OutputString]; this
0x18000328a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000328f  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180003296  call    cs:__imp_OutputDebugStringW
0x18000329c  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x1800032a1  jnz     short loc_1800032AC
0x1800032a3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800032aa  jz      short loc_1800032BE
0x1800032ac  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800032b3  test    rax, rax
0x1800032b6  jz      short loc_1800032BE
0x1800032b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032bd  nop
0x1800032be  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1800032c3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
