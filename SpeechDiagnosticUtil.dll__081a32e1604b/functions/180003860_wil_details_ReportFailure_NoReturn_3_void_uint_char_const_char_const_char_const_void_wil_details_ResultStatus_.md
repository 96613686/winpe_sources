# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003860`
- end: `0x180003ad9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800035f4`

## callees

- `0x180003290`
- `0x180003860`
- `0x180004624`
- `0x180004edc`
- `0x1800058a0`
- `0x1800062cc`
- `0x180010510`
- `0x180011010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180003a11`
- `KERNEL32!IsDebuggerPresent` at `0x180003a11`
- `KERNEL32!OutputDebugStringW` at `0x180003aa1`
- `KERNEL32!OutputDebugStringW` at `0x180003aa1`
- `KERNEL32!GetCurrentThreadId` at `0x180003901`
- `KERNEL32!GetCurrentThreadId` at `0x180003901`

## string_xrefs

- `0x18000391c`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edi
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  __int64 v16; // rcx
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
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v21, v10);
  v18 = a7[2] == 1;
  v12 = v11;
  v19 = 3;
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
  v28 = "onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h";
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
  {
    v21 = -2147418113;
    v22 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
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
  if ( (v20 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v16);
  }
  wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x180003860  mov     [rsp-8+arg_10], rbx
0x180003865  mov     [rsp-8+arg_18], rsi
0x18000386a  push    rbp
0x18000386b  push    rdi
0x18000386c  push    r12
0x18000386e  push    r14
0x180003870  push    r15
0x180003872  lea     rbp, [rsp-13C0h]
0x18000387a  mov     eax, 14C0h
0x18000387f  call    _alloca_probe
0x180003884  sub     rsp, rax
0x180003887  mov     rsi, [rbp+13E0h+arg_28]
0x18000388e  mov     r14d, edx
0x180003891  mov     r15, rcx
0x180003894  xor     edx, edx; Val
0x180003896  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x18000389b  mov     r8d, 98h; Size
0x1800038a1  call    memset_0
0x1800038a6  mov     rbx, [rbp+13E0h+arg_30]
0x1800038ad  xor     r12d, r12d
0x1800038b0  mov     [rbp+13E0h+OutputString], r12w
0x1800038b8  mov     [rbp+13E0h+var_1420], r12b
0x1800038bc  mov     ecx, [rbx]; this
0x1800038be  mov     eax, [rbx+4]
0x1800038c1  mov     [rsp+14E0h+var_14B8], ecx
0x1800038c5  mov     [rsp+14E0h+var_14B4], eax
0x1800038c9  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800038ce  cmp     dword ptr [rbx+8], 1
0x1800038d2  mov     edi, eax
0x1800038d4  lea     eax, [r12+8]
0x1800038d9  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1800038e1  mov     ecx, r12d
0x1800038e4  cmovz   ecx, eax
0x1800038e7  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1800038eb  lea     ecx, [rax-7]
0x1800038ee  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800038f6  inc     ecx
0x1800038f8  mov     [rsp+14E0h+var_14A8], r12
0x1800038fd  mov     [rsp+14E0h+var_14B0], ecx
0x180003901  call    cs:__imp_GetCurrentThreadId
0x180003908  nop     dword ptr [rax+rax+00h]
0x18000390d  xorps   xmm0, xmm0
0x180003910  mov     [rsp+14E0h+var_1480], r14d
0x180003915  mov     [rsp+14E0h+var_14A0], eax
0x180003919  xorps   xmm1, xmm1
0x18000391c  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180003923  mov     [rsp+14E0h+var_147C], edi
0x180003927  mov     [rsp+14E0h+var_1488], rax
0x18000392c  xor     eax, eax
0x18000392e  mov     [rbp+13E0h+var_1448], rax
0x180003932  mov     [rbp+13E0h+var_1460], rax
0x180003936  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000393d  mov     [rsp+14E0h+var_1498], r12
0x180003942  mov     [rsp+14E0h+var_1490], r12
0x180003947  mov     [rbp+13E0h+var_1438], rsi
0x18000394b  mov     [rbp+13E0h+var_1430], r15
0x18000394f  mov     [rsp+14E0h+var_1478], r12
0x180003954  movups  [rbp+13E0h+var_1458], xmm0
0x180003958  movups  [rsp+14E0h+var_1470], xmm1
0x18000395d  test    rax, rax
0x180003960  jz      short loc_18000396D
0x180003962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003967  mov     [rbp+13E0h+var_1440], rax
0x18000396b  jmp     short loc_180003971
0x18000396d  mov     [rbp+13E0h+var_1440], r12
0x180003971  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003978  test    rax, rax
0x18000397b  jz      short loc_180003987
0x18000397d  lea     rcx, [rsp+14E0h+var_14C0]
0x180003982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003987  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000398e  test    rax, rax
0x180003991  jz      short loc_1800039A7
0x180003993  mov     r8d, 400h
0x180003999  lea     rdx, [rbp+13E0h+var_1420]
0x18000399d  lea     rcx, [rsp+14E0h+var_14C0]
0x1800039a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039a7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800039ae  test    rax, rax
0x1800039b1  jz      short loc_1800039BD
0x1800039b3  lea     rcx, [rsp+14E0h+var_14C0]
0x1800039b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039bd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800039c4  test    rax, rax
0x1800039c7  jz      short loc_1800039DA
0x1800039c9  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800039ce  jnz     short loc_1800039DA
0x1800039d0  lea     rcx, [rsp+14E0h+var_14C0]
0x1800039d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039da  cmp     [rsp+14E0h+var_14B8], r12d
0x1800039df  jl      short loc_1800039F3
0x1800039e1  mov     ecx, 8000FFFFh; this
0x1800039e6  mov     [rsp+14E0h+var_14B8], ecx
0x1800039ea  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800039ef  mov     [rsp+14E0h+var_14B4], eax
0x1800039f3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800039fa  jnz     short loc_180003A21
0x1800039fc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003a03  test    rax, rax
0x180003a06  jz      short loc_180003A11
0x180003a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a0d  test    al, al
0x180003a0f  jmp     short loc_180003A1F
0x180003a11  call    cs:__imp_IsDebuggerPresent
0x180003a18  nop     dword ptr [rax+rax+00h]
0x180003a1d  test    eax, eax
0x180003a1f  jz      short loc_180003A28
0x180003a21  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180003a26  jz      short loc_180003A4E
0x180003a28  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a2f  test    rax, rax
0x180003a32  jz      short loc_180003AAD
0x180003a34  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003a3b  jnz     short loc_180003AAD
0x180003a3d  xor     r8d, r8d
0x180003a40  lea     rcx, [rsp+14E0h+var_14C0]
0x180003a45  xor     edx, edx
0x180003a47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a4c  jmp     short loc_180003AAD
0x180003a4e  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a55  mov     ebx, 800h
0x180003a5a  test    rax, rax
0x180003a5d  jz      short loc_180003A7C
0x180003a5f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003a66  jnz     short loc_180003A7C
0x180003a68  mov     r8d, ebx
0x180003a6b  lea     rdx, [rbp+13E0h+OutputString]
0x180003a72  lea     rcx, [rsp+14E0h+var_14C0]
0x180003a77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a7c  cmp     [rbp+13E0h+OutputString], r12w
0x180003a84  jnz     short loc_180003A9A
0x180003a86  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180003a8b  mov     rdx, rbx; unsigned __int16 *
0x180003a8e  lea     rcx, [rbp+13E0h+OutputString]; this
0x180003a95  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003a9a  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180003aa1  call    cs:__imp_OutputDebugStringW
0x180003aa8  nop     dword ptr [rax+rax+00h]
0x180003aad  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180003ab2  jnz     short loc_180003ABD
0x180003ab4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003abb  jz      short loc_180003ACE
0x180003abd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003ac4  test    rax, rax
0x180003ac7  jz      short loc_180003ACE
0x180003ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ace  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180003ad3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
