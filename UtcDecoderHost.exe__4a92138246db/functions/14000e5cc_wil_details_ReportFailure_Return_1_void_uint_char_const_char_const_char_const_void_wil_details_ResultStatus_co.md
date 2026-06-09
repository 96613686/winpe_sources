# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000e5cc`
- end: `0x14000e85d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `657`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x14000e1b0`

## callees

- `0x140008660`
- `0x1400090ec`
- `0x14000c100`
- `0x14000d200`
- `0x14000d2dc`
- `0x14000e5cc`
- `0x140010c3c`
- `0x1400167a0`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e677`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e677`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000e7f7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000e7f7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000e772`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000e772`

## string_xrefs

- `0x14000e681`: `onecore\base\telemetry\utc\service\utcdecoderhost\api\server\utcdecoderhostapiserver.cpp`

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
  wchar_t *v12; // rdx
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
  v25 = "onecore\\base\\telemetry\\utc\\service\\utcdecoderhost\\api\\server\\utcdecoderhostapiserver.cpp";
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
      wil::GetFailureLogString((wil *)OutputString, v12, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, (const struct wil::FailureInfo *)v12);
}

```

## disassembly

```asm
0x14000e5cc  mov     [rsp-8+arg_10], rbx
0x14000e5d1  push    rbp
0x14000e5d2  push    rsi
0x14000e5d3  push    rdi
0x14000e5d4  push    r14
0x14000e5d6  push    r15
0x14000e5d8  lea     rbp, [rsp-13D0h]
0x14000e5e0  mov     eax, 14D0h
0x14000e5e5  call    _alloca_probe
0x14000e5ea  sub     rsp, rax
0x14000e5ed  mov     rax, cs:__security_cookie
0x14000e5f4  xor     rax, rsp
0x14000e5f7  mov     [rbp+13F0h+var_30], rax
0x14000e5fe  mov     esi, edx
0x14000e600  mov     r14, rcx
0x14000e603  mov     rdi, [rbp+13F0h+arg_28]
0x14000e60a  xor     edx, edx; Val
0x14000e60c  mov     r8d, 98h; Size
0x14000e612  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14000e617  call    memset_0
0x14000e61c  nop
0x14000e61d  xor     r15d, r15d
0x14000e620  mov     [rbp+13F0h+OutputString], r15w
0x14000e628  mov     [rbp+13F0h+var_1430], r15b
0x14000e62c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x14000e633  mov     ecx, [rdx]; this
0x14000e635  mov     [rsp+14F0h+var_14C8], ecx
0x14000e639  mov     eax, [rdx+4]
0x14000e63c  mov     [rsp+14F0h+var_14C4], eax
0x14000e640  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000e645  mov     ebx, eax
0x14000e647  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x14000e64f  mov     ecx, r15d
0x14000e652  lea     eax, [r15+8]
0x14000e656  cmp     dword ptr [rdx+8], 1
0x14000e65a  cmovz   ecx, eax
0x14000e65d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14000e661  lea     ecx, [rax-7]
0x14000e664  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000e66c  inc     ecx
0x14000e66e  mov     [rsp+14F0h+var_14C0], ecx
0x14000e672  mov     [rsp+14F0h+var_14B8], r15
0x14000e677  call    cs:__imp_GetCurrentThreadId
0x14000e67d  mov     [rsp+14F0h+var_14B0], eax
0x14000e681  lea     rax, aOnecoreBaseTel_2; "onecore\\base\\telemetry\\utc\\service"...
0x14000e688  mov     [rsp+14F0h+var_1498], rax
0x14000e68d  mov     [rsp+14F0h+var_1490], esi
0x14000e691  mov     [rsp+14F0h+var_148C], ebx
0x14000e695  mov     [rsp+14F0h+var_14A8], r15
0x14000e69a  mov     [rsp+14F0h+var_14A0], r15
0x14000e69f  mov     [rbp+13F0h+var_1448], rdi
0x14000e6a3  mov     [rbp+13F0h+var_1440], r14
0x14000e6a7  mov     [rsp+14F0h+var_1488], r15
0x14000e6ac  xorps   xmm0, xmm0
0x14000e6af  xor     eax, eax
0x14000e6b1  movups  [rbp+13F0h+var_1468], xmm0
0x14000e6b5  mov     [rbp+13F0h+var_1458], rax
0x14000e6b9  xorps   xmm1, xmm1
0x14000e6bc  movups  [rsp+14F0h+var_1480], xmm1
0x14000e6c1  mov     [rbp+13F0h+var_1470], rax
0x14000e6c5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000e6cc  test    rax, rax
0x14000e6cf  jz      short loc_14000E6DC
0x14000e6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e6d6  mov     [rbp+13F0h+var_1450], rax
0x14000e6da  jmp     short loc_14000E6E0
0x14000e6dc  mov     [rbp+13F0h+var_1450], r15
0x14000e6e0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000e6e7  test    rax, rax
0x14000e6ea  jz      short loc_14000E6F6
0x14000e6ec  lea     rcx, [rsp+14F0h+var_14D0]
0x14000e6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e6f6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000e6fd  test    rax, rax
0x14000e700  jz      short loc_14000E716
0x14000e702  mov     r8d, 400h
0x14000e708  lea     rdx, [rbp+13F0h+var_1430]
0x14000e70c  lea     rcx, [rsp+14F0h+var_14D0]
0x14000e711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e716  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000e71d  test    rax, rax
0x14000e720  jz      short loc_14000E72C
0x14000e722  lea     rcx, [rsp+14F0h+var_14D0]
0x14000e727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e72c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000e733  test    rax, rax
0x14000e736  jz      short loc_14000E749
0x14000e738  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000e73d  jnz     short loc_14000E749
0x14000e73f  lea     rcx, [rsp+14F0h+var_14D0]
0x14000e744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e749  cmp     [rsp+14F0h+var_14C8], r15d
0x14000e74e  jge     loc_14000E857
0x14000e754  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x14000e75b  jnz     short loc_14000E77C
0x14000e75d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000e764  test    rax, rax
0x14000e767  jz      short loc_14000E772
0x14000e769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e76e  test    al, al
0x14000e770  jmp     short loc_14000E77A
0x14000e772  call    cs:__imp_IsDebuggerPresent
0x14000e778  test    eax, eax
0x14000e77a  jz      short loc_14000E783
0x14000e77c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000e781  jz      short loc_14000E7A9
0x14000e783  mov     rax, cs:g_pfnResultLoggingCallback
0x14000e78a  test    rax, rax
0x14000e78d  jz      short loc_14000E7FD
0x14000e78f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000e796  jnz     short loc_14000E7FD
0x14000e798  xor     r8d, r8d
0x14000e79b  xor     edx, edx
0x14000e79d  lea     rcx, [rsp+14F0h+var_14D0]
0x14000e7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e7a7  jmp     short loc_14000E7FD
0x14000e7a9  mov     rax, cs:g_pfnResultLoggingCallback
0x14000e7b0  test    rax, rax
0x14000e7b3  jz      short loc_14000E7D5
0x14000e7b5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000e7bc  jnz     short loc_14000E7D5
0x14000e7be  mov     r8d, 800h
0x14000e7c4  lea     rdx, [rbp+13F0h+OutputString]
0x14000e7cb  lea     rcx, [rsp+14F0h+var_14D0]
0x14000e7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e7d5  cmp     [rbp+13F0h+OutputString], r15w
0x14000e7dd  jnz     short loc_14000E7F0
0x14000e7df  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000e7e4  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000e7eb  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x14000e7f0  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000e7f7  call    cs:__imp_OutputDebugStringW
0x14000e7fd  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000e802  jnz     short loc_14000E80D
0x14000e804  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x14000e80b  jz      short loc_14000E81F
0x14000e80d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000e814  test    rax, rax
0x14000e817  jz      short loc_14000E81F
0x14000e819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e81e  nop
0x14000e81f  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x14000e824  jnz     short loc_14000E84C
0x14000e826  mov     rcx, [rbp+13F0h+var_30]
0x14000e82d  xor     rcx, rsp; StackCookie
0x14000e830  call    __security_check_cookie
0x14000e835  mov     rbx, [rsp+14F0h+arg_10]
0x14000e83d  add     rsp, 14D0h
0x14000e844  pop     r15
0x14000e846  pop     r14
0x14000e848  pop     rdi
0x14000e849  pop     rsi
0x14000e84a  pop     rbp
0x14000e84b  retn
0x14000e84c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000e851  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000e857  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
