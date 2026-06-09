# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003640`
- end: `0x1800038a9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800033ec`

## callees

- `0x18000262c`
- `0x180003640`
- `0x180004a24`
- `0x1800051c4`
- `0x1800058f0`
- `0x1800068d0`
- `0x180035830`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036e2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003876`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003876`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800037ec`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800037ec`

## string_xrefs

- `0x1800036ec`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
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
  v25 = "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h";
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
0x180003640  mov     [rsp-8+arg_10], rbx
0x180003645  mov     [rsp-8+arg_18], rsi
0x18000364a  push    rbp
0x18000364b  push    rdi
0x18000364c  push    r12
0x18000364e  push    r14
0x180003650  push    r15
0x180003652  lea     rbp, [rsp-13C0h]
0x18000365a  mov     eax, 14C0h
0x18000365f  call    _alloca_probe
0x180003664  sub     rsp, rax
0x180003667  mov     r14d, edx
0x18000366a  mov     r15, rcx
0x18000366d  mov     rsi, [rbp+13E0h+arg_28]
0x180003674  xor     edx, edx; Val
0x180003676  mov     r8d, 98h; Size
0x18000367c  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180003681  call    memset_0
0x180003686  nop
0x180003687  xor     r12d, r12d
0x18000368a  mov     [rbp+13E0h+OutputString], r12w
0x180003692  mov     [rbp+13E0h+var_1420], r12b
0x180003696  mov     rbx, [rbp+13E0h+arg_30]
0x18000369d  mov     ecx, [rbx]; this
0x18000369f  mov     [rsp+14E0h+var_14B8], ecx
0x1800036a3  mov     eax, [rbx+4]
0x1800036a6  mov     [rsp+14E0h+var_14B4], eax
0x1800036aa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800036af  mov     edi, eax
0x1800036b1  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1800036b9  mov     ecx, r12d
0x1800036bc  lea     eax, [r12+8]
0x1800036c1  cmp     dword ptr [rbx+8], 1
0x1800036c5  cmovz   ecx, eax
0x1800036c8  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1800036cc  lea     ecx, [rax-7]
0x1800036cf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800036d7  inc     ecx
0x1800036d9  mov     [rsp+14E0h+var_14B0], ecx
0x1800036dd  mov     [rsp+14E0h+var_14A8], r12
0x1800036e2  call    cs:__imp_GetCurrentThreadId
0x1800036e8  mov     [rsp+14E0h+var_14A0], eax
0x1800036ec  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800036f3  mov     [rsp+14E0h+var_1488], rax
0x1800036f8  mov     [rsp+14E0h+var_1480], r14d
0x1800036fd  mov     [rsp+14E0h+var_147C], edi
0x180003701  mov     [rsp+14E0h+var_1498], r12
0x180003706  mov     [rsp+14E0h+var_1490], r12
0x18000370b  mov     [rbp+13E0h+var_1438], rsi
0x18000370f  mov     [rbp+13E0h+var_1430], r15
0x180003713  mov     [rsp+14E0h+var_1478], r12
0x180003718  xorps   xmm0, xmm0
0x18000371b  xor     eax, eax
0x18000371d  movups  [rbp+13E0h+var_1458], xmm0
0x180003721  mov     [rbp+13E0h+var_1448], rax
0x180003725  xorps   xmm1, xmm1
0x180003728  movups  [rsp+14E0h+var_1470], xmm1
0x18000372d  mov     [rbp+13E0h+var_1460], rax
0x180003731  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003738  test    rax, rax
0x18000373b  jz      short loc_180003748
0x18000373d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003742  mov     [rbp+13E0h+var_1440], rax
0x180003746  jmp     short loc_18000374C
0x180003748  mov     [rbp+13E0h+var_1440], r12
0x18000374c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003753  test    rax, rax
0x180003756  jz      short loc_180003762
0x180003758  lea     rcx, [rsp+14E0h+var_14C0]
0x18000375d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003762  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003769  test    rax, rax
0x18000376c  jz      short loc_180003782
0x18000376e  mov     r8d, 400h
0x180003774  lea     rdx, [rbp+13E0h+var_1420]
0x180003778  lea     rcx, [rsp+14E0h+var_14C0]
0x18000377d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003782  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003789  test    rax, rax
0x18000378c  jz      short loc_180003798
0x18000378e  lea     rcx, [rsp+14E0h+var_14C0]
0x180003793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003798  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000379f  test    rax, rax
0x1800037a2  jz      short loc_1800037B5
0x1800037a4  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800037a9  jnz     short loc_1800037B5
0x1800037ab  lea     rcx, [rsp+14E0h+var_14C0]
0x1800037b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b5  cmp     [rsp+14E0h+var_14B8], r12d
0x1800037ba  jl      short loc_1800037CE
0x1800037bc  mov     ecx, 8000FFFFh; this
0x1800037c1  mov     [rsp+14E0h+var_14B8], ecx
0x1800037c5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800037ca  mov     [rsp+14E0h+var_14B4], eax
0x1800037ce  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800037d5  jnz     short loc_1800037F6
0x1800037d7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800037de  test    rax, rax
0x1800037e1  jz      short loc_1800037EC
0x1800037e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037e8  test    al, al
0x1800037ea  jmp     short loc_1800037F4
0x1800037ec  call    cs:__imp_IsDebuggerPresent
0x1800037f2  test    eax, eax
0x1800037f4  jz      short loc_1800037FD
0x1800037f6  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800037fb  jz      short loc_180003823
0x1800037fd  mov     rax, cs:g_pfnResultLoggingCallback
0x180003804  test    rax, rax
0x180003807  jz      short loc_18000387C
0x180003809  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003810  jnz     short loc_18000387C
0x180003812  xor     r8d, r8d
0x180003815  xor     edx, edx
0x180003817  lea     rcx, [rsp+14E0h+var_14C0]
0x18000381c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003821  jmp     short loc_18000387C
0x180003823  mov     ebx, 800h
0x180003828  mov     rax, cs:g_pfnResultLoggingCallback
0x18000382f  test    rax, rax
0x180003832  jz      short loc_180003851
0x180003834  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000383b  jnz     short loc_180003851
0x18000383d  mov     r8d, ebx
0x180003840  lea     rdx, [rbp+13E0h+OutputString]
0x180003847  lea     rcx, [rsp+14E0h+var_14C0]
0x18000384c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003851  cmp     [rbp+13E0h+OutputString], r12w
0x180003859  jnz     short loc_18000386F
0x18000385b  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180003860  mov     rdx, rbx; unsigned __int16 *
0x180003863  lea     rcx, [rbp+13E0h+OutputString]; this
0x18000386a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000386f  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180003876  call    cs:__imp_OutputDebugStringW
0x18000387c  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180003881  jnz     short loc_18000388C
0x180003883  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000388a  jz      short loc_18000389E
0x18000388c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003893  test    rax, rax
0x180003896  jz      short loc_18000389E
0x180003898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000389d  nop
0x18000389e  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1800038a3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
