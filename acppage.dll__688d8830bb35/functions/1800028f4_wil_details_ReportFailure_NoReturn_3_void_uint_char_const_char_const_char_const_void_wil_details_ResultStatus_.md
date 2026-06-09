# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800028f4`
- end: `0x180002b54`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002698`

## callees

- `0x1800028f4`
- `0x180004c84`
- `0x1800054ac`
- `0x180006400`
- `0x1800080f0`
- `0x18001623a`
- `0x180016310`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180002995`
- `KERNEL32!GetCurrentThreadId` at `0x180002995`
- `KERNEL32!OutputDebugStringW` at `0x180002b22`
- `KERNEL32!OutputDebugStringW` at `0x180002b22`
- `KERNEL32!IsDebuggerPresent` at `0x180002a98`
- `KERNEL32!IsDebuggerPresent` at `0x180002a98`

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
0x1800028f4  mov     [rsp-8+arg_18], rbx
0x1800028f9  push    rbp
0x1800028fa  push    rsi
0x1800028fb  push    rdi
0x1800028fc  push    r12
0x1800028fe  push    r13
0x180002900  push    r14
0x180002902  push    r15
0x180002904  lea     rbp, [rsp-13C0h]
0x18000290c  mov     eax, 14C0h
0x180002911  call    _alloca_probe
0x180002916  sub     rsp, rax
0x180002919  mov     rsi, [rbp+13F0h+arg_28]
0x180002920  mov     r15, r8
0x180002923  mov     r14d, edx
0x180002926  mov     r12, rcx
0x180002929  xor     edx, edx; Val
0x18000292b  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002930  mov     r8d, 98h; Size
0x180002936  call    memset_0
0x18000293b  mov     rbx, [rbp+13F0h+arg_30]
0x180002942  xor     r13d, r13d
0x180002945  mov     [rbp+13F0h+OutputString], r13w
0x18000294d  mov     [rbp+13F0h+var_1430], r13b
0x180002951  mov     ecx, [rbx]; this
0x180002953  mov     eax, [rbx+4]
0x180002956  mov     [rsp+14F0h+var_14C8], ecx
0x18000295a  mov     [rsp+14F0h+var_14C4], eax
0x18000295e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002963  cmp     dword ptr [rbx+8], 1
0x180002967  mov     edi, eax
0x180002969  lea     eax, [r13+8]
0x18000296d  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002975  mov     ecx, r13d
0x180002978  cmovz   ecx, eax
0x18000297b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000297f  lea     ecx, [rax-7]
0x180002982  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000298a  inc     ecx
0x18000298c  mov     [rsp+14F0h+var_14B8], r13
0x180002991  mov     [rsp+14F0h+var_14C0], ecx
0x180002995  call    cs:__imp_GetCurrentThreadId
0x18000299b  xorps   xmm0, xmm0
0x18000299e  mov     [rsp+14F0h+var_1498], r15
0x1800029a3  mov     [rsp+14F0h+var_14B0], eax
0x1800029a7  xorps   xmm1, xmm1
0x1800029aa  xor     eax, eax
0x1800029ac  mov     [rsp+14F0h+var_1490], r14d
0x1800029b1  mov     [rbp+13F0h+var_1458], rax
0x1800029b5  mov     [rbp+13F0h+var_1470], rax
0x1800029b9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800029c0  mov     [rsp+14F0h+var_148C], edi
0x1800029c4  mov     [rsp+14F0h+var_14A8], r13
0x1800029c9  mov     [rsp+14F0h+var_14A0], r13
0x1800029ce  mov     [rbp+13F0h+var_1448], rsi
0x1800029d2  mov     [rbp+13F0h+var_1440], r12
0x1800029d6  mov     [rsp+14F0h+var_1488], r13
0x1800029db  movups  [rbp+13F0h+var_1468], xmm0
0x1800029df  movups  [rsp+14F0h+var_1480], xmm1
0x1800029e4  test    rax, rax
0x1800029e7  jz      short loc_1800029F4
0x1800029e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029ee  mov     [rbp+13F0h+var_1450], rax
0x1800029f2  jmp     short loc_1800029F8
0x1800029f4  mov     [rbp+13F0h+var_1450], r13
0x1800029f8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800029ff  test    rax, rax
0x180002a02  jz      short loc_180002A0E
0x180002a04  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a0e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002a15  test    rax, rax
0x180002a18  jz      short loc_180002A2E
0x180002a1a  mov     r8d, 400h
0x180002a20  lea     rdx, [rbp+13F0h+var_1430]
0x180002a24  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a2e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002a35  test    rax, rax
0x180002a38  jz      short loc_180002A44
0x180002a3a  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a44  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002a4b  test    rax, rax
0x180002a4e  jz      short loc_180002A61
0x180002a50  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002a55  jnz     short loc_180002A61
0x180002a57  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a61  cmp     [rsp+14F0h+var_14C8], r13d
0x180002a66  jl      short loc_180002A7A
0x180002a68  mov     ecx, 8000FFFFh; this
0x180002a6d  mov     [rsp+14F0h+var_14C8], ecx
0x180002a71  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002a76  mov     [rsp+14F0h+var_14C4], eax
0x180002a7a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002a81  jnz     short loc_180002AA2
0x180002a83  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002a8a  test    rax, rax
0x180002a8d  jz      short loc_180002A98
0x180002a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a94  test    al, al
0x180002a96  jmp     short loc_180002AA0
0x180002a98  call    cs:__imp_IsDebuggerPresent
0x180002a9e  test    eax, eax
0x180002aa0  jz      short loc_180002AA9
0x180002aa2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002aa7  jz      short loc_180002ACF
0x180002aa9  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ab0  test    rax, rax
0x180002ab3  jz      short loc_180002B28
0x180002ab5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002abc  jnz     short loc_180002B28
0x180002abe  xor     r8d, r8d
0x180002ac1  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ac6  xor     edx, edx
0x180002ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002acd  jmp     short loc_180002B28
0x180002acf  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ad6  mov     ebx, 800h
0x180002adb  test    rax, rax
0x180002ade  jz      short loc_180002AFD
0x180002ae0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002ae7  jnz     short loc_180002AFD
0x180002ae9  mov     r8d, ebx
0x180002aec  lea     rdx, [rbp+13F0h+OutputString]
0x180002af3  lea     rcx, [rsp+14F0h+var_14D0]
0x180002af8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002afd  cmp     [rbp+13F0h+OutputString], r13w
0x180002b05  jnz     short loc_180002B1B
0x180002b07  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002b0c  mov     rdx, rbx; unsigned __int16 *
0x180002b0f  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002b16  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002b1b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002b22  call    cs:__imp_OutputDebugStringW
0x180002b28  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002b2d  jnz     short loc_180002B38
0x180002b2f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002b36  jz      short loc_180002B49
0x180002b38  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002b3f  test    rax, rax
0x180002b42  jz      short loc_180002B49
0x180002b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b49  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002b4e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
