# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180022ac8`
- end: `0x180022d28`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800226e4`

## callees

- `0x1800028d8`
- `0x180022ac8`
- `0x180024be8`
- `0x18002538c`
- `0x180025ff0`
- `0x180027be0`
- `0x18005c3b0`
- `0x18005d010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180022c6c`
- `KERNEL32!IsDebuggerPresent` at `0x180022c6c`
- `KERNEL32!OutputDebugStringW` at `0x180022cf6`
- `KERNEL32!OutputDebugStringW` at `0x180022cf6`
- `KERNEL32!GetCurrentThreadId` at `0x180022b69`
- `KERNEL32!GetCurrentThreadId` at `0x180022b69`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
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
0x180022ac8  mov     [rsp-8+arg_18], rbx
0x180022acd  push    rbp
0x180022ace  push    rsi
0x180022acf  push    rdi
0x180022ad0  push    r12
0x180022ad2  push    r13
0x180022ad4  push    r14
0x180022ad6  push    r15
0x180022ad8  lea     rbp, [rsp-13C0h]
0x180022ae0  mov     eax, 14C0h
0x180022ae5  call    _alloca_probe
0x180022aea  sub     rsp, rax
0x180022aed  mov     rsi, [rbp+13F0h+arg_28]
0x180022af4  mov     r15, r8
0x180022af7  mov     r14d, edx
0x180022afa  mov     r12, rcx
0x180022afd  xor     edx, edx; Val
0x180022aff  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180022b04  mov     r8d, 98h; Size
0x180022b0a  call    memset_0
0x180022b0f  mov     rbx, [rbp+13F0h+arg_30]
0x180022b16  xor     r13d, r13d
0x180022b19  mov     [rbp+13F0h+OutputString], r13w
0x180022b21  mov     [rbp+13F0h+var_1430], r13b
0x180022b25  mov     ecx, [rbx]; this
0x180022b27  mov     eax, [rbx+4]
0x180022b2a  mov     [rsp+14F0h+var_14C8], ecx
0x180022b2e  mov     [rsp+14F0h+var_14C4], eax
0x180022b32  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180022b37  cmp     dword ptr [rbx+8], 1
0x180022b3b  mov     edi, eax
0x180022b3d  lea     eax, [r13+8]
0x180022b41  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180022b49  mov     ecx, r13d
0x180022b4c  cmovz   ecx, eax
0x180022b4f  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180022b53  lea     ecx, [rax-7]
0x180022b56  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180022b5e  inc     ecx
0x180022b60  mov     [rsp+14F0h+var_14B8], r13
0x180022b65  mov     [rsp+14F0h+var_14C0], ecx
0x180022b69  call    cs:__imp_GetCurrentThreadId
0x180022b6f  xorps   xmm0, xmm0
0x180022b72  mov     [rsp+14F0h+var_1498], r15
0x180022b77  mov     [rsp+14F0h+var_14B0], eax
0x180022b7b  xorps   xmm1, xmm1
0x180022b7e  xor     eax, eax
0x180022b80  mov     [rsp+14F0h+var_1490], r14d
0x180022b85  mov     [rbp+13F0h+var_1458], rax
0x180022b89  mov     [rbp+13F0h+var_1470], rax
0x180022b8d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180022b94  mov     [rsp+14F0h+var_148C], edi
0x180022b98  mov     [rsp+14F0h+var_14A8], r13
0x180022b9d  mov     [rsp+14F0h+var_14A0], r13
0x180022ba2  mov     [rbp+13F0h+var_1448], rsi
0x180022ba6  mov     [rbp+13F0h+var_1440], r12
0x180022baa  mov     [rsp+14F0h+var_1488], r13
0x180022baf  movups  [rbp+13F0h+var_1468], xmm0
0x180022bb3  movups  [rsp+14F0h+var_1480], xmm1
0x180022bb8  test    rax, rax
0x180022bbb  jz      short loc_180022BC8
0x180022bbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022bc2  mov     [rbp+13F0h+var_1450], rax
0x180022bc6  jmp     short loc_180022BCC
0x180022bc8  mov     [rbp+13F0h+var_1450], r13
0x180022bcc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180022bd3  test    rax, rax
0x180022bd6  jz      short loc_180022BE2
0x180022bd8  lea     rcx, [rsp+14F0h+var_14D0]
0x180022bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022be2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180022be9  test    rax, rax
0x180022bec  jz      short loc_180022C02
0x180022bee  mov     r8d, 400h
0x180022bf4  lea     rdx, [rbp+13F0h+var_1430]
0x180022bf8  lea     rcx, [rsp+14F0h+var_14D0]
0x180022bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c02  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180022c09  test    rax, rax
0x180022c0c  jz      short loc_180022C18
0x180022c0e  lea     rcx, [rsp+14F0h+var_14D0]
0x180022c13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c18  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180022c1f  test    rax, rax
0x180022c22  jz      short loc_180022C35
0x180022c24  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180022c29  jnz     short loc_180022C35
0x180022c2b  lea     rcx, [rsp+14F0h+var_14D0]
0x180022c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c35  cmp     [rsp+14F0h+var_14C8], r13d
0x180022c3a  jl      short loc_180022C4E
0x180022c3c  mov     ecx, 8000FFFFh; this
0x180022c41  mov     [rsp+14F0h+var_14C8], ecx
0x180022c45  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180022c4a  mov     [rsp+14F0h+var_14C4], eax
0x180022c4e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180022c55  jnz     short loc_180022C76
0x180022c57  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180022c5e  test    rax, rax
0x180022c61  jz      short loc_180022C6C
0x180022c63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c68  test    al, al
0x180022c6a  jmp     short loc_180022C74
0x180022c6c  call    cs:__imp_IsDebuggerPresent
0x180022c72  test    eax, eax
0x180022c74  jz      short loc_180022C7D
0x180022c76  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180022c7b  jz      short loc_180022CA3
0x180022c7d  mov     rax, cs:g_pfnResultLoggingCallback
0x180022c84  test    rax, rax
0x180022c87  jz      short loc_180022CFC
0x180022c89  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180022c90  jnz     short loc_180022CFC
0x180022c92  xor     r8d, r8d
0x180022c95  lea     rcx, [rsp+14F0h+var_14D0]
0x180022c9a  xor     edx, edx
0x180022c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ca1  jmp     short loc_180022CFC
0x180022ca3  mov     rax, cs:g_pfnResultLoggingCallback
0x180022caa  mov     ebx, 800h
0x180022caf  test    rax, rax
0x180022cb2  jz      short loc_180022CD1
0x180022cb4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180022cbb  jnz     short loc_180022CD1
0x180022cbd  mov     r8d, ebx
0x180022cc0  lea     rdx, [rbp+13F0h+OutputString]
0x180022cc7  lea     rcx, [rsp+14F0h+var_14D0]
0x180022ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cd1  cmp     [rbp+13F0h+OutputString], r13w
0x180022cd9  jnz     short loc_180022CEF
0x180022cdb  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180022ce0  mov     rdx, rbx; unsigned __int16 *
0x180022ce3  lea     rcx, [rbp+13F0h+OutputString]; this
0x180022cea  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180022cef  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180022cf6  call    cs:__imp_OutputDebugStringW
0x180022cfc  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180022d01  jnz     short loc_180022D0C
0x180022d03  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180022d0a  jz      short loc_180022D1D
0x180022d0c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180022d13  test    rax, rax
0x180022d16  jz      short loc_180022D1D
0x180022d18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d1d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180022d22  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
