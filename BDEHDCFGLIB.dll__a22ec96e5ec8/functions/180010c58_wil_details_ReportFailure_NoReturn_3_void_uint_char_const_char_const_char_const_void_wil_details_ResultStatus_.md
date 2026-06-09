# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180010c58`
- end: `0x180010ebf`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180010a0c`

## callees

- `0x180010c58`
- `0x180011ce4`
- `0x18001247c`
- `0x180012bf0`
- `0x180013370`
- `0x18001358e`
- `0x180013650`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180010cf9`
- `KERNEL32!GetCurrentThreadId` at `0x180010cf9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010e03`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010e03`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010e8d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010e8d`

## string_xrefs

- `0x180010d0e`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180010c58  mov     [rsp-8+arg_10], rbx
0x180010c5d  mov     [rsp-8+arg_18], rsi
0x180010c62  push    rbp
0x180010c63  push    rdi
0x180010c64  push    r12
0x180010c66  push    r14
0x180010c68  push    r15
0x180010c6a  lea     rbp, [rsp-13C0h]
0x180010c72  mov     eax, 14C0h
0x180010c77  call    _alloca_probe
0x180010c7c  sub     rsp, rax
0x180010c7f  mov     rsi, [rbp+13E0h+arg_28]
0x180010c86  mov     r14d, edx
0x180010c89  mov     r15, rcx
0x180010c8c  xor     edx, edx; Val
0x180010c8e  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180010c93  mov     r8d, 98h; Size
0x180010c99  call    memset_0
0x180010c9e  mov     rbx, [rbp+13E0h+arg_30]
0x180010ca5  xor     r12d, r12d
0x180010ca8  mov     [rbp+13E0h+OutputString], r12w
0x180010cb0  mov     [rbp+13E0h+var_1420], r12b
0x180010cb4  mov     ecx, [rbx]; this
0x180010cb6  mov     eax, [rbx+4]
0x180010cb9  mov     [rsp+14E0h+var_14B8], ecx
0x180010cbd  mov     [rsp+14E0h+var_14B4], eax
0x180010cc1  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180010cc6  cmp     dword ptr [rbx+8], 1
0x180010cca  mov     edi, eax
0x180010ccc  lea     eax, [r12+8]
0x180010cd1  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180010cd9  mov     ecx, r12d
0x180010cdc  cmovz   ecx, eax
0x180010cdf  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180010ce3  lea     ecx, [rax-7]
0x180010ce6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180010cee  inc     ecx
0x180010cf0  mov     [rsp+14E0h+var_14A8], r12
0x180010cf5  mov     [rsp+14E0h+var_14B0], ecx
0x180010cf9  call    cs:__imp_GetCurrentThreadId
0x180010cff  xorps   xmm0, xmm0
0x180010d02  mov     [rsp+14E0h+var_1480], r14d
0x180010d07  mov     [rsp+14E0h+var_14A0], eax
0x180010d0b  xorps   xmm1, xmm1
0x180010d0e  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180010d15  mov     [rsp+14E0h+var_147C], edi
0x180010d19  mov     [rsp+14E0h+var_1488], rax
0x180010d1e  xor     eax, eax
0x180010d20  mov     [rbp+13E0h+var_1448], rax
0x180010d24  mov     [rbp+13E0h+var_1460], rax
0x180010d28  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180010d2f  mov     [rsp+14E0h+var_1498], r12
0x180010d34  mov     [rsp+14E0h+var_1490], r12
0x180010d39  mov     [rbp+13E0h+var_1438], rsi
0x180010d3d  mov     [rbp+13E0h+var_1430], r15
0x180010d41  mov     [rsp+14E0h+var_1478], r12
0x180010d46  movups  [rbp+13E0h+var_1458], xmm0
0x180010d4a  movups  [rsp+14E0h+var_1470], xmm1
0x180010d4f  test    rax, rax
0x180010d52  jz      short loc_180010D5F
0x180010d54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d59  mov     [rbp+13E0h+var_1440], rax
0x180010d5d  jmp     short loc_180010D63
0x180010d5f  mov     [rbp+13E0h+var_1440], r12
0x180010d63  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180010d6a  test    rax, rax
0x180010d6d  jz      short loc_180010D79
0x180010d6f  lea     rcx, [rsp+14E0h+var_14C0]
0x180010d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d79  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180010d80  test    rax, rax
0x180010d83  jz      short loc_180010D99
0x180010d85  mov     r8d, 400h
0x180010d8b  lea     rdx, [rbp+13E0h+var_1420]
0x180010d8f  lea     rcx, [rsp+14E0h+var_14C0]
0x180010d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d99  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010da0  test    rax, rax
0x180010da3  jz      short loc_180010DAF
0x180010da5  lea     rcx, [rsp+14E0h+var_14C0]
0x180010daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010daf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010db6  test    rax, rax
0x180010db9  jz      short loc_180010DCC
0x180010dbb  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180010dc0  jnz     short loc_180010DCC
0x180010dc2  lea     rcx, [rsp+14E0h+var_14C0]
0x180010dc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dcc  cmp     [rsp+14E0h+var_14B8], r12d
0x180010dd1  jl      short loc_180010DE5
0x180010dd3  mov     ecx, 8000FFFFh; this
0x180010dd8  mov     [rsp+14E0h+var_14B8], ecx
0x180010ddc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180010de1  mov     [rsp+14E0h+var_14B4], eax
0x180010de5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180010dec  jnz     short loc_180010E0D
0x180010dee  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180010df5  test    rax, rax
0x180010df8  jz      short loc_180010E03
0x180010dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010dff  test    al, al
0x180010e01  jmp     short loc_180010E0B
0x180010e03  call    cs:__imp_IsDebuggerPresent
0x180010e09  test    eax, eax
0x180010e0b  jz      short loc_180010E14
0x180010e0d  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180010e12  jz      short loc_180010E3A
0x180010e14  mov     rax, cs:g_pfnResultLoggingCallback
0x180010e1b  test    rax, rax
0x180010e1e  jz      short loc_180010E93
0x180010e20  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180010e27  jnz     short loc_180010E93
0x180010e29  xor     r8d, r8d
0x180010e2c  lea     rcx, [rsp+14E0h+var_14C0]
0x180010e31  xor     edx, edx
0x180010e33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e38  jmp     short loc_180010E93
0x180010e3a  mov     rax, cs:g_pfnResultLoggingCallback
0x180010e41  mov     ebx, 800h
0x180010e46  test    rax, rax
0x180010e49  jz      short loc_180010E68
0x180010e4b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180010e52  jnz     short loc_180010E68
0x180010e54  mov     r8d, ebx
0x180010e57  lea     rdx, [rbp+13E0h+OutputString]
0x180010e5e  lea     rcx, [rsp+14E0h+var_14C0]
0x180010e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e68  cmp     [rbp+13E0h+OutputString], r12w
0x180010e70  jnz     short loc_180010E86
0x180010e72  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180010e77  mov     rdx, rbx; unsigned __int16 *
0x180010e7a  lea     rcx, [rbp+13E0h+OutputString]; this
0x180010e81  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180010e86  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180010e8d  call    cs:__imp_OutputDebugStringW
0x180010e93  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180010e98  jnz     short loc_180010EA3
0x180010e9a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180010ea1  jz      short loc_180010EB4
0x180010ea3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180010eaa  test    rax, rax
0x180010ead  jz      short loc_180010EB4
0x180010eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010eb4  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180010eb9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
