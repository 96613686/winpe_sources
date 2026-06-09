# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002cfc`
- end: `0x180002f5c`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002a98`

## callees

- `0x1800026b4`
- `0x180002cfc`
- `0x180004ed4`
- `0x180005670`
- `0x180006570`
- `0x180008520`
- `0x1800228f0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d9d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002f2a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002f2a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002ea0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002ea0`

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
0x180002cfc  mov     [rsp-8+arg_18], rbx
0x180002d01  push    rbp
0x180002d02  push    rsi
0x180002d03  push    rdi
0x180002d04  push    r12
0x180002d06  push    r13
0x180002d08  push    r14
0x180002d0a  push    r15
0x180002d0c  lea     rbp, [rsp-13C0h]
0x180002d14  mov     eax, 14C0h
0x180002d19  call    _alloca_probe
0x180002d1e  sub     rsp, rax
0x180002d21  mov     rsi, [rbp+13F0h+arg_28]
0x180002d28  mov     r15, r8
0x180002d2b  mov     r14d, edx
0x180002d2e  mov     r12, rcx
0x180002d31  xor     edx, edx; Val
0x180002d33  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002d38  mov     r8d, 98h; Size
0x180002d3e  call    memset_0
0x180002d43  mov     rbx, [rbp+13F0h+arg_30]
0x180002d4a  xor     r13d, r13d
0x180002d4d  mov     [rbp+13F0h+OutputString], r13w
0x180002d55  mov     [rbp+13F0h+var_1430], r13b
0x180002d59  mov     ecx, [rbx]; this
0x180002d5b  mov     eax, [rbx+4]
0x180002d5e  mov     [rsp+14F0h+var_14C8], ecx
0x180002d62  mov     [rsp+14F0h+var_14C4], eax
0x180002d66  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002d6b  cmp     dword ptr [rbx+8], 1
0x180002d6f  mov     edi, eax
0x180002d71  lea     eax, [r13+8]
0x180002d75  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002d7d  mov     ecx, r13d
0x180002d80  cmovz   ecx, eax
0x180002d83  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002d87  lea     ecx, [rax-7]
0x180002d8a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002d92  inc     ecx
0x180002d94  mov     [rsp+14F0h+var_14B8], r13
0x180002d99  mov     [rsp+14F0h+var_14C0], ecx
0x180002d9d  call    cs:__imp_GetCurrentThreadId
0x180002da3  xorps   xmm0, xmm0
0x180002da6  mov     [rsp+14F0h+var_1498], r15
0x180002dab  mov     [rsp+14F0h+var_14B0], eax
0x180002daf  xorps   xmm1, xmm1
0x180002db2  xor     eax, eax
0x180002db4  mov     [rsp+14F0h+var_1490], r14d
0x180002db9  mov     [rbp+13F0h+var_1458], rax
0x180002dbd  mov     [rbp+13F0h+var_1470], rax
0x180002dc1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002dc8  mov     [rsp+14F0h+var_148C], edi
0x180002dcc  mov     [rsp+14F0h+var_14A8], r13
0x180002dd1  mov     [rsp+14F0h+var_14A0], r13
0x180002dd6  mov     [rbp+13F0h+var_1448], rsi
0x180002dda  mov     [rbp+13F0h+var_1440], r12
0x180002dde  mov     [rsp+14F0h+var_1488], r13
0x180002de3  movups  [rbp+13F0h+var_1468], xmm0
0x180002de7  movups  [rsp+14F0h+var_1480], xmm1
0x180002dec  test    rax, rax
0x180002def  jz      short loc_180002DFC
0x180002df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df6  mov     [rbp+13F0h+var_1450], rax
0x180002dfa  jmp     short loc_180002E00
0x180002dfc  mov     [rbp+13F0h+var_1450], r13
0x180002e00  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002e07  test    rax, rax
0x180002e0a  jz      short loc_180002E16
0x180002e0c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e16  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002e1d  test    rax, rax
0x180002e20  jz      short loc_180002E36
0x180002e22  mov     r8d, 400h
0x180002e28  lea     rdx, [rbp+13F0h+var_1430]
0x180002e2c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e36  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002e3d  test    rax, rax
0x180002e40  jz      short loc_180002E4C
0x180002e42  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e4c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002e53  test    rax, rax
0x180002e56  jz      short loc_180002E69
0x180002e58  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002e5d  jnz     short loc_180002E69
0x180002e5f  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e69  cmp     [rsp+14F0h+var_14C8], r13d
0x180002e6e  jl      short loc_180002E82
0x180002e70  mov     ecx, 8000FFFFh; this
0x180002e75  mov     [rsp+14F0h+var_14C8], ecx
0x180002e79  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002e7e  mov     [rsp+14F0h+var_14C4], eax
0x180002e82  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002e89  jnz     short loc_180002EAA
0x180002e8b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002e92  test    rax, rax
0x180002e95  jz      short loc_180002EA0
0x180002e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e9c  test    al, al
0x180002e9e  jmp     short loc_180002EA8
0x180002ea0  call    cs:__imp_IsDebuggerPresent
0x180002ea6  test    eax, eax
0x180002ea8  jz      short loc_180002EB1
0x180002eaa  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002eaf  jz      short loc_180002ED7
0x180002eb1  mov     rax, cs:g_pfnResultLoggingCallback
0x180002eb8  test    rax, rax
0x180002ebb  jz      short loc_180002F30
0x180002ebd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002ec4  jnz     short loc_180002F30
0x180002ec6  xor     r8d, r8d
0x180002ec9  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ece  xor     edx, edx
0x180002ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ed5  jmp     short loc_180002F30
0x180002ed7  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ede  mov     ebx, 800h
0x180002ee3  test    rax, rax
0x180002ee6  jz      short loc_180002F05
0x180002ee8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002eef  jnz     short loc_180002F05
0x180002ef1  mov     r8d, ebx
0x180002ef4  lea     rdx, [rbp+13F0h+OutputString]
0x180002efb  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f05  cmp     [rbp+13F0h+OutputString], r13w
0x180002f0d  jnz     short loc_180002F23
0x180002f0f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002f14  mov     rdx, rbx; unsigned __int16 *
0x180002f17  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002f1e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002f23  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002f2a  call    cs:__imp_OutputDebugStringW
0x180002f30  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002f35  jnz     short loc_180002F40
0x180002f37  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002f3e  jz      short loc_180002F51
0x180002f40  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002f47  test    rax, rax
0x180002f4a  jz      short loc_180002F51
0x180002f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f51  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002f56  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
