# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000a780`
- end: `0x18000aa22`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `674`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000a5e8`

## callees

- `0x1800089c4`
- `0x180009788`
- `0x180009aec`
- `0x18000a780`
- `0x18000b0c4`
- `0x18000d2ce`
- `0x18000d300`
- `0x18000d390`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a837`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a837`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a9bc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a9bc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a932`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a932`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  __int64 v36; // [rsp+C0h] [rbp-40h]
  char v37[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v36 = -2;
  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
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
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v37, 1024);
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
0x18000a780  push    rbp
0x18000a782  push    rsi
0x18000a783  push    rdi
0x18000a784  push    r14
0x18000a786  push    r15
0x18000a788  lea     rbp, [rsp-13E0h]
0x18000a790  mov     eax, 14E0h
0x18000a795  call    _alloca_probe
0x18000a79a  sub     rsp, rax
0x18000a79d  mov     [rbp+1400h+var_1440], 0FFFFFFFFFFFFFFFEh
0x18000a7a5  mov     [rsp+1500h+arg_10], rbx
0x18000a7ad  mov     rax, cs:__security_cookie
0x18000a7b4  xor     rax, rsp
0x18000a7b7  mov     [rbp+1400h+var_30], rax
0x18000a7be  mov     esi, edx
0x18000a7c0  mov     r14, rcx
0x18000a7c3  mov     rdi, [rbp+1400h+arg_28]
0x18000a7ca  xor     edx, edx; Val
0x18000a7cc  mov     r8d, 98h; Size
0x18000a7d2  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000a7d7  call    memset_0
0x18000a7dc  nop
0x18000a7dd  xor     r15d, r15d
0x18000a7e0  mov     [rbp+1400h+OutputString], r15w
0x18000a7e8  mov     [rbp+1400h+var_1430], r15b
0x18000a7ec  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000a7f3  mov     ecx, [rdx]; this
0x18000a7f5  mov     [rsp+1500h+var_14D8], ecx
0x18000a7f9  mov     eax, [rdx+4]
0x18000a7fc  mov     [rsp+1500h+var_14D4], eax
0x18000a800  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a805  mov     ebx, eax
0x18000a807  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000a80f  mov     ecx, r15d
0x18000a812  lea     eax, [r15+8]
0x18000a816  cmp     dword ptr [rdx+8], 1
0x18000a81a  cmovz   ecx, eax
0x18000a81d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000a821  lea     ecx, [rax-7]
0x18000a824  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a82c  inc     ecx
0x18000a82e  mov     [rsp+1500h+var_14D0], ecx
0x18000a832  mov     [rsp+1500h+var_14C8], r15
0x18000a837  call    cs:__imp_GetCurrentThreadId
0x18000a83d  mov     [rsp+1500h+var_14C0], eax
0x18000a841  lea     rax, aWil; "wil"
0x18000a848  mov     [rsp+1500h+var_14A8], rax
0x18000a84d  mov     [rsp+1500h+var_14A0], esi
0x18000a851  mov     [rsp+1500h+var_149C], ebx
0x18000a855  mov     [rsp+1500h+var_14B8], r15
0x18000a85a  mov     [rsp+1500h+var_14B0], r15
0x18000a85f  mov     [rbp+1400h+var_1458], rdi
0x18000a863  mov     [rbp+1400h+var_1450], r14
0x18000a867  mov     [rsp+1500h+var_1498], r15
0x18000a86c  xorps   xmm0, xmm0
0x18000a86f  xor     eax, eax
0x18000a871  movups  [rbp+1400h+var_1478], xmm0
0x18000a875  mov     [rbp+1400h+var_1468], rax
0x18000a879  xorps   xmm1, xmm1
0x18000a87c  movups  [rsp+1500h+var_1490], xmm1
0x18000a881  mov     [rbp+1400h+var_1480], rax
0x18000a885  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a88c  test    rax, rax
0x18000a88f  jz      short loc_18000A89C
0x18000a891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a896  mov     [rbp+1400h+var_1460], rax
0x18000a89a  jmp     short loc_18000A8A0
0x18000a89c  mov     [rbp+1400h+var_1460], r15
0x18000a8a0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a8a7  test    rax, rax
0x18000a8aa  jz      short loc_18000A8B6
0x18000a8ac  lea     rcx, [rsp+1500h+var_14E0]
0x18000a8b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8b6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a8bd  test    rax, rax
0x18000a8c0  jz      short loc_18000A8D6
0x18000a8c2  mov     r8d, 400h
0x18000a8c8  lea     rdx, [rbp+1400h+var_1430]
0x18000a8cc  lea     rcx, [rsp+1500h+var_14E0]
0x18000a8d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8d6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a8dd  test    rax, rax
0x18000a8e0  jz      short loc_18000A8EC
0x18000a8e2  lea     rcx, [rsp+1500h+var_14E0]
0x18000a8e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8ec  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a8f3  test    rax, rax
0x18000a8f6  jz      short loc_18000A909
0x18000a8f8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000a8fd  jnz     short loc_18000A909
0x18000a8ff  lea     rcx, [rsp+1500h+var_14E0]
0x18000a904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a909  cmp     [rsp+1500h+var_14D8], r15d
0x18000a90e  jge     loc_18000AA1C
0x18000a914  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000a91b  jnz     short loc_18000A93C
0x18000a91d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a924  test    rax, rax
0x18000a927  jz      short loc_18000A932
0x18000a929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a92e  test    al, al
0x18000a930  jmp     short loc_18000A93A
0x18000a932  call    cs:__imp_IsDebuggerPresent
0x18000a938  test    eax, eax
0x18000a93a  jz      short loc_18000A943
0x18000a93c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000a941  jz      short loc_18000A969
0x18000a943  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a94a  test    rax, rax
0x18000a94d  jz      short loc_18000A9C2
0x18000a94f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000a956  jnz     short loc_18000A9C2
0x18000a958  xor     r8d, r8d
0x18000a95b  xor     edx, edx
0x18000a95d  lea     rcx, [rsp+1500h+var_14E0]
0x18000a962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a967  jmp     short loc_18000A9C2
0x18000a969  mov     ebx, 800h
0x18000a96e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a975  test    rax, rax
0x18000a978  jz      short loc_18000A997
0x18000a97a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000a981  jnz     short loc_18000A997
0x18000a983  mov     r8d, ebx
0x18000a986  lea     rdx, [rbp+1400h+OutputString]
0x18000a98d  lea     rcx, [rsp+1500h+var_14E0]
0x18000a992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a997  cmp     [rbp+1400h+OutputString], r15w
0x18000a99f  jnz     short loc_18000A9B5
0x18000a9a1  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000a9a6  mov     rdx, rbx; unsigned __int16 *
0x18000a9a9  lea     rcx, [rbp+1400h+OutputString]; this
0x18000a9b0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a9b5  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000a9bc  call    cs:__imp_OutputDebugStringW
0x18000a9c2  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000a9c7  jnz     short loc_18000A9D2
0x18000a9c9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000a9d0  jz      short loc_18000A9E4
0x18000a9d2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a9d9  test    rax, rax
0x18000a9dc  jz      short loc_18000A9E4
0x18000a9de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9e3  nop
0x18000a9e4  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000a9e9  jnz     short loc_18000AA11
0x18000a9eb  mov     rcx, [rbp+1400h+var_30]
0x18000a9f2  xor     rcx, rsp; StackCookie
0x18000a9f5  call    __security_check_cookie
0x18000a9fa  mov     rbx, [rsp+1500h+arg_10]
0x18000aa02  add     rsp, 14E0h
0x18000aa09  pop     r15
0x18000aa0b  pop     r14
0x18000aa0d  pop     rdi
0x18000aa0e  pop     rsi
0x18000aa0f  pop     rbp
0x18000aa10  retn
0x18000aa11  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000aa16  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000aa1c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
