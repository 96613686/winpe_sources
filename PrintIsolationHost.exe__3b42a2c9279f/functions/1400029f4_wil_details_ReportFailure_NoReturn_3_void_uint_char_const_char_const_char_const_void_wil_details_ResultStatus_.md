# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1400029f4`
- end: `0x140002c5b`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400027a8`

## callees

- `0x140002690`
- `0x1400029f4`
- `0x140003b74`
- `0x14000430c`
- `0x140004b80`
- `0x1400057c0`
- `0x140007710`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002a95`
- `KERNEL32!GetCurrentThreadId` at `0x140002a95`
- `KERNEL32!OutputDebugStringW` at `0x140002c29`
- `KERNEL32!OutputDebugStringW` at `0x140002c29`
- `KERNEL32!IsDebuggerPresent` at `0x140002b9f`
- `KERNEL32!IsDebuggerPresent` at `0x140002b9f`

## string_xrefs

- `0x140002aaa`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  v28 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
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
0x1400029f4  mov     [rsp-8+arg_10], rbx
0x1400029f9  mov     [rsp-8+arg_18], rsi
0x1400029fe  push    rbp
0x1400029ff  push    rdi
0x140002a00  push    r12
0x140002a02  push    r14
0x140002a04  push    r15
0x140002a06  lea     rbp, [rsp-13C0h]
0x140002a0e  mov     eax, 14C0h
0x140002a13  call    _alloca_probe
0x140002a18  sub     rsp, rax
0x140002a1b  mov     rsi, [rbp+13E0h+arg_28]
0x140002a22  mov     r14d, edx
0x140002a25  mov     r15, rcx
0x140002a28  xor     edx, edx; Val
0x140002a2a  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x140002a2f  mov     r8d, 98h; Size
0x140002a35  call    memset_0
0x140002a3a  mov     rbx, [rbp+13E0h+arg_30]
0x140002a41  xor     r12d, r12d
0x140002a44  mov     [rbp+13E0h+OutputString], r12w
0x140002a4c  mov     [rbp+13E0h+var_1420], r12b
0x140002a50  mov     ecx, [rbx]; this
0x140002a52  mov     eax, [rbx+4]
0x140002a55  mov     [rsp+14E0h+var_14B8], ecx
0x140002a59  mov     [rsp+14E0h+var_14B4], eax
0x140002a5d  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140002a62  cmp     dword ptr [rbx+8], 1
0x140002a66  mov     edi, eax
0x140002a68  lea     eax, [r12+8]
0x140002a6d  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x140002a75  mov     ecx, r12d
0x140002a78  cmovz   ecx, eax
0x140002a7b  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x140002a7f  lea     ecx, [rax-7]
0x140002a82  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002a8a  inc     ecx
0x140002a8c  mov     [rsp+14E0h+var_14A8], r12
0x140002a91  mov     [rsp+14E0h+var_14B0], ecx
0x140002a95  call    cs:__imp_GetCurrentThreadId
0x140002a9b  xorps   xmm0, xmm0
0x140002a9e  mov     [rsp+14E0h+var_1480], r14d
0x140002aa3  mov     [rsp+14E0h+var_14A0], eax
0x140002aa7  xorps   xmm1, xmm1
0x140002aaa  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140002ab1  mov     [rsp+14E0h+var_147C], edi
0x140002ab5  mov     [rsp+14E0h+var_1488], rax
0x140002aba  xor     eax, eax
0x140002abc  mov     [rbp+13E0h+var_1448], rax
0x140002ac0  mov     [rbp+13E0h+var_1460], rax
0x140002ac4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002acb  mov     [rsp+14E0h+var_1498], r12
0x140002ad0  mov     [rsp+14E0h+var_1490], r12
0x140002ad5  mov     [rbp+13E0h+var_1438], rsi
0x140002ad9  mov     [rbp+13E0h+var_1430], r15
0x140002add  mov     [rsp+14E0h+var_1478], r12
0x140002ae2  movups  [rbp+13E0h+var_1458], xmm0
0x140002ae6  movups  [rsp+14E0h+var_1470], xmm1
0x140002aeb  test    rax, rax
0x140002aee  jz      short loc_140002AFB
0x140002af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002af5  mov     [rbp+13E0h+var_1440], rax
0x140002af9  jmp     short loc_140002AFF
0x140002afb  mov     [rbp+13E0h+var_1440], r12
0x140002aff  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002b06  test    rax, rax
0x140002b09  jz      short loc_140002B15
0x140002b0b  lea     rcx, [rsp+14E0h+var_14C0]
0x140002b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b15  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002b1c  test    rax, rax
0x140002b1f  jz      short loc_140002B35
0x140002b21  mov     r8d, 400h
0x140002b27  lea     rdx, [rbp+13E0h+var_1420]
0x140002b2b  lea     rcx, [rsp+14E0h+var_14C0]
0x140002b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b35  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002b3c  test    rax, rax
0x140002b3f  jz      short loc_140002B4B
0x140002b41  lea     rcx, [rsp+14E0h+var_14C0]
0x140002b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b4b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002b52  test    rax, rax
0x140002b55  jz      short loc_140002B68
0x140002b57  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x140002b5c  jnz     short loc_140002B68
0x140002b5e  lea     rcx, [rsp+14E0h+var_14C0]
0x140002b63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b68  cmp     [rsp+14E0h+var_14B8], r12d
0x140002b6d  jl      short loc_140002B81
0x140002b6f  mov     ecx, 8000FFFFh; this
0x140002b74  mov     [rsp+14E0h+var_14B8], ecx
0x140002b78  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002b7d  mov     [rsp+14E0h+var_14B4], eax
0x140002b81  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140002b88  jnz     short loc_140002BA9
0x140002b8a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002b91  test    rax, rax
0x140002b94  jz      short loc_140002B9F
0x140002b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b9b  test    al, al
0x140002b9d  jmp     short loc_140002BA7
0x140002b9f  call    cs:__imp_IsDebuggerPresent
0x140002ba5  test    eax, eax
0x140002ba7  jz      short loc_140002BB0
0x140002ba9  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x140002bae  jz      short loc_140002BD6
0x140002bb0  mov     rax, cs:g_pfnResultLoggingCallback
0x140002bb7  test    rax, rax
0x140002bba  jz      short loc_140002C2F
0x140002bbc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002bc3  jnz     short loc_140002C2F
0x140002bc5  xor     r8d, r8d
0x140002bc8  lea     rcx, [rsp+14E0h+var_14C0]
0x140002bcd  xor     edx, edx
0x140002bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bd4  jmp     short loc_140002C2F
0x140002bd6  mov     rax, cs:g_pfnResultLoggingCallback
0x140002bdd  mov     ebx, 800h
0x140002be2  test    rax, rax
0x140002be5  jz      short loc_140002C04
0x140002be7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002bee  jnz     short loc_140002C04
0x140002bf0  mov     r8d, ebx
0x140002bf3  lea     rdx, [rbp+13E0h+OutputString]
0x140002bfa  lea     rcx, [rsp+14E0h+var_14C0]
0x140002bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c04  cmp     [rbp+13E0h+OutputString], r12w
0x140002c0c  jnz     short loc_140002C22
0x140002c0e  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x140002c13  mov     rdx, rbx; unsigned __int16 *
0x140002c16  lea     rcx, [rbp+13E0h+OutputString]; this
0x140002c1d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002c22  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x140002c29  call    cs:__imp_OutputDebugStringW
0x140002c2f  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x140002c34  jnz     short loc_140002C3F
0x140002c36  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140002c3d  jz      short loc_140002C50
0x140002c3f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002c46  test    rax, rax
0x140002c49  jz      short loc_140002C50
0x140002c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c50  lea     rcx, [rsp+14E0h+var_14C0]; this
0x140002c55  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
