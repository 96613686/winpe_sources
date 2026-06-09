# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800268cc`
- end: `0x180026b62`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180026788`

## callees

- `0x1800094a0`
- `0x18000a074`
- `0x180025be0`
- `0x1800265f0`
- `0x180026664`
- `0x180026740`
- `0x1800268cc`
- `0x18003be70`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026977`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026977`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026afc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180026afc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180026a72`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180026a72`

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
0x1800268cc  mov     [rsp-8+arg_10], rbx
0x1800268d1  push    rbp
0x1800268d2  push    rsi
0x1800268d3  push    rdi
0x1800268d4  push    r14
0x1800268d6  push    r15
0x1800268d8  lea     rbp, [rsp-13D0h]
0x1800268e0  mov     eax, 14D0h
0x1800268e5  call    _alloca_probe
0x1800268ea  sub     rsp, rax
0x1800268ed  mov     rax, cs:__security_cookie
0x1800268f4  xor     rax, rsp
0x1800268f7  mov     [rbp+13F0h+var_30], rax
0x1800268fe  mov     esi, edx
0x180026900  mov     r14, rcx
0x180026903  mov     rdi, [rbp+13F0h+arg_28]
0x18002690a  xor     edx, edx; Val
0x18002690c  mov     r8d, 98h; Size
0x180026912  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180026917  call    memset_0
0x18002691c  nop
0x18002691d  xor     r15d, r15d
0x180026920  mov     [rbp+13F0h+OutputString], r15w
0x180026928  mov     [rbp+13F0h+var_1430], r15b
0x18002692c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180026933  mov     ecx, [rdx]; this
0x180026935  mov     [rsp+14F0h+var_14C8], ecx
0x180026939  mov     eax, [rdx+4]
0x18002693c  mov     [rsp+14F0h+var_14C4], eax
0x180026940  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180026945  mov     ebx, eax
0x180026947  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18002694f  mov     ecx, r15d
0x180026952  lea     eax, [r15+8]
0x180026956  cmp     dword ptr [rdx+8], 1
0x18002695a  cmovz   ecx, eax
0x18002695d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180026961  lea     ecx, [rax-7]
0x180026964  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002696c  inc     ecx
0x18002696e  mov     [rsp+14F0h+var_14C0], ecx
0x180026972  mov     [rsp+14F0h+var_14B8], r15
0x180026977  call    cs:__imp_GetCurrentThreadId
0x18002697d  mov     [rsp+14F0h+var_14B0], eax
0x180026981  lea     rax, aWil; "wil"
0x180026988  mov     [rsp+14F0h+var_1498], rax
0x18002698d  mov     [rsp+14F0h+var_1490], esi
0x180026991  mov     [rsp+14F0h+var_148C], ebx
0x180026995  mov     [rsp+14F0h+var_14A8], r15
0x18002699a  mov     [rsp+14F0h+var_14A0], r15
0x18002699f  mov     [rbp+13F0h+var_1448], rdi
0x1800269a3  mov     [rbp+13F0h+var_1440], r14
0x1800269a7  mov     [rsp+14F0h+var_1488], r15
0x1800269ac  xorps   xmm0, xmm0
0x1800269af  xor     eax, eax
0x1800269b1  movups  [rbp+13F0h+var_1468], xmm0
0x1800269b5  mov     [rbp+13F0h+var_1458], rax
0x1800269b9  xorps   xmm1, xmm1
0x1800269bc  movups  [rsp+14F0h+var_1480], xmm1
0x1800269c1  mov     [rbp+13F0h+var_1470], rax
0x1800269c5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800269cc  test    rax, rax
0x1800269cf  jz      short loc_1800269DC
0x1800269d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269d6  mov     [rbp+13F0h+var_1450], rax
0x1800269da  jmp     short loc_1800269E0
0x1800269dc  mov     [rbp+13F0h+var_1450], r15
0x1800269e0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800269e7  test    rax, rax
0x1800269ea  jz      short loc_1800269F6
0x1800269ec  lea     rcx, [rsp+14F0h+var_14D0]
0x1800269f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800269f6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800269fd  test    rax, rax
0x180026a00  jz      short loc_180026A16
0x180026a02  mov     r8d, 400h
0x180026a08  lea     rdx, [rbp+13F0h+var_1430]
0x180026a0c  lea     rcx, [rsp+14F0h+var_14D0]
0x180026a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a16  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180026a1d  test    rax, rax
0x180026a20  jz      short loc_180026A2C
0x180026a22  lea     rcx, [rsp+14F0h+var_14D0]
0x180026a27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a2c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180026a33  test    rax, rax
0x180026a36  jz      short loc_180026A49
0x180026a38  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180026a3d  jnz     short loc_180026A49
0x180026a3f  lea     rcx, [rsp+14F0h+var_14D0]
0x180026a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a49  cmp     [rsp+14F0h+var_14C8], r15d
0x180026a4e  jge     loc_180026B5C
0x180026a54  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180026a5b  jnz     short loc_180026A7C
0x180026a5d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180026a64  test    rax, rax
0x180026a67  jz      short loc_180026A72
0x180026a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a6e  test    al, al
0x180026a70  jmp     short loc_180026A7A
0x180026a72  call    cs:__imp_IsDebuggerPresent
0x180026a78  test    eax, eax
0x180026a7a  jz      short loc_180026A83
0x180026a7c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180026a81  jz      short loc_180026AA9
0x180026a83  mov     rax, cs:g_pfnResultLoggingCallback
0x180026a8a  test    rax, rax
0x180026a8d  jz      short loc_180026B02
0x180026a8f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180026a96  jnz     short loc_180026B02
0x180026a98  xor     r8d, r8d
0x180026a9b  xor     edx, edx
0x180026a9d  lea     rcx, [rsp+14F0h+var_14D0]
0x180026aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026aa7  jmp     short loc_180026B02
0x180026aa9  mov     ebx, 800h
0x180026aae  mov     rax, cs:g_pfnResultLoggingCallback
0x180026ab5  test    rax, rax
0x180026ab8  jz      short loc_180026AD7
0x180026aba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180026ac1  jnz     short loc_180026AD7
0x180026ac3  mov     r8d, ebx
0x180026ac6  lea     rdx, [rbp+13F0h+OutputString]
0x180026acd  lea     rcx, [rsp+14F0h+var_14D0]
0x180026ad2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ad7  cmp     [rbp+13F0h+OutputString], r15w
0x180026adf  jnz     short loc_180026AF5
0x180026ae1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180026ae6  mov     rdx, rbx; unsigned __int16 *
0x180026ae9  lea     rcx, [rbp+13F0h+OutputString]; this
0x180026af0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180026af5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180026afc  call    cs:__imp_OutputDebugStringW
0x180026b02  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180026b07  jnz     short loc_180026B12
0x180026b09  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180026b10  jz      short loc_180026B24
0x180026b12  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180026b19  test    rax, rax
0x180026b1c  jz      short loc_180026B24
0x180026b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026b23  nop
0x180026b24  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180026b29  jnz     short loc_180026B51
0x180026b2b  mov     rcx, [rbp+13F0h+var_30]
0x180026b32  xor     rcx, rsp; StackCookie
0x180026b35  call    __security_check_cookie
0x180026b3a  mov     rbx, [rsp+14F0h+arg_10]
0x180026b42  add     rsp, 14D0h
0x180026b49  pop     r15
0x180026b4b  pop     r14
0x180026b4d  pop     rdi
0x180026b4e  pop     rsi
0x180026b4f  pop     rbp
0x180026b50  retn
0x180026b51  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180026b56  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180026b5c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
