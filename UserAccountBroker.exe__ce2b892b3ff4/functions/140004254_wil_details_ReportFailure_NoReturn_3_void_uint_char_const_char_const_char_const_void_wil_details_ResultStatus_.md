# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140004254`
- end: `0x1400044bb`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140004000`

## callees

- `0x14000195f`
- `0x140004254`
- `0x140005374`
- `0x140005b10`
- `0x140006120`
- `0x1400069e0`
- `0x140006c20`
- `0x140007010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400042f5`
- `KERNEL32!GetCurrentThreadId` at `0x1400042f5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004489`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004489`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400043ff`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400043ff`

## string_xrefs

- `0x14000430a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
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
0x140004254  mov     [rsp-8+arg_10], rbx
0x140004259  mov     [rsp-8+arg_18], rsi
0x14000425e  push    rbp
0x14000425f  push    rdi
0x140004260  push    r12
0x140004262  push    r14
0x140004264  push    r15
0x140004266  lea     rbp, [rsp-13C0h]
0x14000426e  mov     eax, 14C0h
0x140004273  call    _alloca_probe
0x140004278  sub     rsp, rax
0x14000427b  mov     rsi, [rbp+13E0h+arg_28]
0x140004282  mov     r14d, edx
0x140004285  mov     r15, rcx
0x140004288  xor     edx, edx; Val
0x14000428a  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x14000428f  mov     r8d, 98h; Size
0x140004295  call    memset_0
0x14000429a  mov     rbx, [rbp+13E0h+arg_30]
0x1400042a1  xor     r12d, r12d
0x1400042a4  mov     [rbp+13E0h+OutputString], r12w
0x1400042ac  mov     [rbp+13E0h+var_1420], r12b
0x1400042b0  mov     ecx, [rbx]; this
0x1400042b2  mov     eax, [rbx+4]
0x1400042b5  mov     [rsp+14E0h+var_14B8], ecx
0x1400042b9  mov     [rsp+14E0h+var_14B4], eax
0x1400042bd  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400042c2  cmp     dword ptr [rbx+8], 1
0x1400042c6  mov     edi, eax
0x1400042c8  lea     eax, [r12+8]
0x1400042cd  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1400042d5  mov     ecx, r12d
0x1400042d8  cmovz   ecx, eax
0x1400042db  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1400042df  lea     ecx, [rax-7]
0x1400042e2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400042ea  inc     ecx
0x1400042ec  mov     [rsp+14E0h+var_14A8], r12
0x1400042f1  mov     [rsp+14E0h+var_14B0], ecx
0x1400042f5  call    cs:__imp_GetCurrentThreadId
0x1400042fb  xorps   xmm0, xmm0
0x1400042fe  mov     [rsp+14E0h+var_1480], r14d
0x140004303  mov     [rsp+14E0h+var_14A0], eax
0x140004307  xorps   xmm1, xmm1
0x14000430a  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140004311  mov     [rsp+14E0h+var_147C], edi
0x140004315  mov     [rsp+14E0h+var_1488], rax
0x14000431a  xor     eax, eax
0x14000431c  mov     [rbp+13E0h+var_1448], rax
0x140004320  mov     [rbp+13E0h+var_1460], rax
0x140004324  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000432b  mov     [rsp+14E0h+var_1498], r12
0x140004330  mov     [rsp+14E0h+var_1490], r12
0x140004335  mov     [rbp+13E0h+var_1438], rsi
0x140004339  mov     [rbp+13E0h+var_1430], r15
0x14000433d  mov     [rsp+14E0h+var_1478], r12
0x140004342  movups  [rbp+13E0h+var_1458], xmm0
0x140004346  movups  [rsp+14E0h+var_1470], xmm1
0x14000434b  test    rax, rax
0x14000434e  jz      short loc_14000435B
0x140004350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004355  mov     [rbp+13E0h+var_1440], rax
0x140004359  jmp     short loc_14000435F
0x14000435b  mov     [rbp+13E0h+var_1440], r12
0x14000435f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004366  test    rax, rax
0x140004369  jz      short loc_140004375
0x14000436b  lea     rcx, [rsp+14E0h+var_14C0]
0x140004370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004375  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000437c  test    rax, rax
0x14000437f  jz      short loc_140004395
0x140004381  mov     r8d, 400h
0x140004387  lea     rdx, [rbp+13E0h+var_1420]
0x14000438b  lea     rcx, [rsp+14E0h+var_14C0]
0x140004390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004395  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000439c  test    rax, rax
0x14000439f  jz      short loc_1400043AB
0x1400043a1  lea     rcx, [rsp+14E0h+var_14C0]
0x1400043a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043ab  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400043b2  test    rax, rax
0x1400043b5  jz      short loc_1400043C8
0x1400043b7  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1400043bc  jnz     short loc_1400043C8
0x1400043be  lea     rcx, [rsp+14E0h+var_14C0]
0x1400043c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043c8  cmp     [rsp+14E0h+var_14B8], r12d
0x1400043cd  jl      short loc_1400043E1
0x1400043cf  mov     ecx, 8000FFFFh; this
0x1400043d4  mov     [rsp+14E0h+var_14B8], ecx
0x1400043d8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400043dd  mov     [rsp+14E0h+var_14B4], eax
0x1400043e1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400043e8  jnz     short loc_140004409
0x1400043ea  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400043f1  test    rax, rax
0x1400043f4  jz      short loc_1400043FF
0x1400043f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043fb  test    al, al
0x1400043fd  jmp     short loc_140004407
0x1400043ff  call    cs:__imp_IsDebuggerPresent
0x140004405  test    eax, eax
0x140004407  jz      short loc_140004410
0x140004409  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x14000440e  jz      short loc_140004436
0x140004410  mov     rax, cs:g_pfnResultLoggingCallback
0x140004417  test    rax, rax
0x14000441a  jz      short loc_14000448F
0x14000441c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140004423  jnz     short loc_14000448F
0x140004425  xor     r8d, r8d
0x140004428  lea     rcx, [rsp+14E0h+var_14C0]
0x14000442d  xor     edx, edx
0x14000442f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004434  jmp     short loc_14000448F
0x140004436  mov     rax, cs:g_pfnResultLoggingCallback
0x14000443d  mov     ebx, 800h
0x140004442  test    rax, rax
0x140004445  jz      short loc_140004464
0x140004447  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000444e  jnz     short loc_140004464
0x140004450  mov     r8d, ebx
0x140004453  lea     rdx, [rbp+13E0h+OutputString]
0x14000445a  lea     rcx, [rsp+14E0h+var_14C0]
0x14000445f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004464  cmp     [rbp+13E0h+OutputString], r12w
0x14000446c  jnz     short loc_140004482
0x14000446e  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x140004473  mov     rdx, rbx; unsigned __int16 *
0x140004476  lea     rcx, [rbp+13E0h+OutputString]; this
0x14000447d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004482  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x140004489  call    cs:__imp_OutputDebugStringW
0x14000448f  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x140004494  jnz     short loc_14000449F
0x140004496  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000449d  jz      short loc_1400044B0
0x14000449f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400044a6  test    rax, rax
0x1400044a9  jz      short loc_1400044B0
0x1400044ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044b0  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1400044b5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
