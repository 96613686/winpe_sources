# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000290c`
- end: `0x180002ba2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800023ec`

## callees

- `0x18000290c`
- `0x1800055e4`
- `0x18000780c`
- `0x18000a130`
- `0x18000ab0c`
- `0x18000c5e2`
- `0x18000c610`
- `0x18000c6d0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800029b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800029b7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002ab2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002ab2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002b3c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002b3c`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
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
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x18000290c  mov     [rsp-8+arg_10], rbx
0x180002911  push    rbp
0x180002912  push    rsi
0x180002913  push    rdi
0x180002914  push    r14
0x180002916  push    r15
0x180002918  lea     rbp, [rsp-13D0h]
0x180002920  mov     eax, 14D0h
0x180002925  call    _alloca_probe
0x18000292a  sub     rsp, rax
0x18000292d  mov     rax, cs:__security_cookie
0x180002934  xor     rax, rsp
0x180002937  mov     [rbp+13F0h+var_30], rax
0x18000293e  mov     esi, edx
0x180002940  mov     r14, rcx
0x180002943  mov     rdi, [rbp+13F0h+arg_28]
0x18000294a  xor     edx, edx; Val
0x18000294c  mov     r8d, 98h; Size
0x180002952  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002957  call    memset_0
0x18000295c  nop
0x18000295d  xor     r15d, r15d
0x180002960  mov     [rbp+13F0h+OutputString], r15w
0x180002968  mov     [rbp+13F0h+var_1430], r15b
0x18000296c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002973  mov     ecx, [rdx]; this
0x180002975  mov     [rsp+14F0h+var_14C8], ecx
0x180002979  mov     eax, [rdx+4]
0x18000297c  mov     [rsp+14F0h+var_14C4], eax
0x180002980  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002985  mov     ebx, eax
0x180002987  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000298f  mov     ecx, r15d
0x180002992  lea     eax, [r15+8]
0x180002996  cmp     dword ptr [rdx+8], 1
0x18000299a  cmovz   ecx, eax
0x18000299d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800029a1  lea     ecx, [rax-7]
0x1800029a4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800029ac  inc     ecx
0x1800029ae  mov     [rsp+14F0h+var_14C0], ecx
0x1800029b2  mov     [rsp+14F0h+var_14B8], r15
0x1800029b7  call    cs:__imp_GetCurrentThreadId
0x1800029bd  mov     [rsp+14F0h+var_14B0], eax
0x1800029c1  lea     rax, aWil; "wil"
0x1800029c8  mov     [rsp+14F0h+var_1498], rax
0x1800029cd  mov     [rsp+14F0h+var_1490], esi
0x1800029d1  mov     [rsp+14F0h+var_148C], ebx
0x1800029d5  mov     [rsp+14F0h+var_14A8], r15
0x1800029da  mov     [rsp+14F0h+var_14A0], r15
0x1800029df  mov     [rbp+13F0h+var_1448], rdi
0x1800029e3  mov     [rbp+13F0h+var_1440], r14
0x1800029e7  mov     [rsp+14F0h+var_1488], r15
0x1800029ec  xorps   xmm0, xmm0
0x1800029ef  xor     eax, eax
0x1800029f1  movups  [rbp+13F0h+var_1468], xmm0
0x1800029f5  mov     [rbp+13F0h+var_1458], rax
0x1800029f9  xorps   xmm1, xmm1
0x1800029fc  movups  [rsp+14F0h+var_1480], xmm1
0x180002a01  mov     [rbp+13F0h+var_1470], rax
0x180002a05  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002a0c  test    rax, rax
0x180002a0f  jz      short loc_180002A1C
0x180002a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a16  mov     [rbp+13F0h+var_1450], rax
0x180002a1a  jmp     short loc_180002A20
0x180002a1c  mov     [rbp+13F0h+var_1450], r15
0x180002a20  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002a27  test    rax, rax
0x180002a2a  jz      short loc_180002A36
0x180002a2c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a36  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002a3d  test    rax, rax
0x180002a40  jz      short loc_180002A56
0x180002a42  mov     r8d, 400h
0x180002a48  lea     rdx, [rbp+13F0h+var_1430]
0x180002a4c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a56  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002a5d  test    rax, rax
0x180002a60  jz      short loc_180002A6C
0x180002a62  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a6c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002a73  test    rax, rax
0x180002a76  jz      short loc_180002A89
0x180002a78  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002a7d  jnz     short loc_180002A89
0x180002a7f  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a89  cmp     [rsp+14F0h+var_14C8], r15d
0x180002a8e  jge     loc_180002B9C
0x180002a94  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002a9b  jnz     short loc_180002ABC
0x180002a9d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002aa4  test    rax, rax
0x180002aa7  jz      short loc_180002AB2
0x180002aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aae  test    al, al
0x180002ab0  jmp     short loc_180002ABA
0x180002ab2  call    cs:__imp_IsDebuggerPresent
0x180002ab8  test    eax, eax
0x180002aba  jz      short loc_180002AC3
0x180002abc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002ac1  jz      short loc_180002AE9
0x180002ac3  mov     rax, cs:g_pfnResultLoggingCallback
0x180002aca  test    rax, rax
0x180002acd  jz      short loc_180002B42
0x180002acf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002ad6  jnz     short loc_180002B42
0x180002ad8  xor     r8d, r8d
0x180002adb  xor     edx, edx
0x180002add  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ae7  jmp     short loc_180002B42
0x180002ae9  mov     ebx, 800h
0x180002aee  mov     rax, cs:g_pfnResultLoggingCallback
0x180002af5  test    rax, rax
0x180002af8  jz      short loc_180002B17
0x180002afa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002b01  jnz     short loc_180002B17
0x180002b03  mov     r8d, ebx
0x180002b06  lea     rdx, [rbp+13F0h+OutputString]
0x180002b0d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b17  cmp     [rbp+13F0h+OutputString], r15w
0x180002b1f  jnz     short loc_180002B35
0x180002b21  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002b26  mov     rdx, rbx; unsigned __int16 *
0x180002b29  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002b30  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002b35  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002b3c  call    cs:__imp_OutputDebugStringW
0x180002b42  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002b47  jnz     short loc_180002B52
0x180002b49  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002b50  jz      short loc_180002B64
0x180002b52  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002b59  test    rax, rax
0x180002b5c  jz      short loc_180002B64
0x180002b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b63  nop
0x180002b64  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002b69  jnz     short loc_180002B91
0x180002b6b  mov     rcx, [rbp+13F0h+var_30]
0x180002b72  xor     rcx, rsp; StackCookie
0x180002b75  call    __security_check_cookie
0x180002b7a  mov     rbx, [rsp+14F0h+arg_10]
0x180002b82  add     rsp, 14D0h
0x180002b89  pop     r15
0x180002b8b  pop     r14
0x180002b8d  pop     rdi
0x180002b8e  pop     rsi
0x180002b8f  pop     rbp
0x180002b90  retn
0x180002b91  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002b96  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002b9c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
