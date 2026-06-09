# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180013f58`
- end: `0x1800141ee`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180013a38`

## callees

- `0x1800016d0`
- `0x180002024`
- `0x180013f58`
- `0x180015f74`
- `0x180017448`
- `0x1800194e0`
- `0x1800196ac`
- `0x18002ad30`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014003`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014003`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180014188`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180014188`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800140fe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800140fe`

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
0x180013f58  mov     [rsp-8+arg_10], rbx
0x180013f5d  push    rbp
0x180013f5e  push    rsi
0x180013f5f  push    rdi
0x180013f60  push    r14
0x180013f62  push    r15
0x180013f64  lea     rbp, [rsp-13D0h]
0x180013f6c  mov     eax, 14D0h
0x180013f71  call    _alloca_probe
0x180013f76  sub     rsp, rax
0x180013f79  mov     rax, cs:__security_cookie
0x180013f80  xor     rax, rsp
0x180013f83  mov     [rbp+13F0h+var_30], rax
0x180013f8a  mov     esi, edx
0x180013f8c  mov     r14, rcx
0x180013f8f  mov     rdi, [rbp+13F0h+arg_28]
0x180013f96  xor     edx, edx; Val
0x180013f98  mov     r8d, 98h; Size
0x180013f9e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180013fa3  call    memset_0
0x180013fa8  nop
0x180013fa9  xor     r15d, r15d
0x180013fac  mov     [rbp+13F0h+OutputString], r15w
0x180013fb4  mov     [rbp+13F0h+var_1430], r15b
0x180013fb8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180013fbf  mov     ecx, [rdx]; this
0x180013fc1  mov     [rsp+14F0h+var_14C8], ecx
0x180013fc5  mov     eax, [rdx+4]
0x180013fc8  mov     [rsp+14F0h+var_14C4], eax
0x180013fcc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180013fd1  mov     ebx, eax
0x180013fd3  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180013fdb  mov     ecx, r15d
0x180013fde  lea     eax, [r15+8]
0x180013fe2  cmp     dword ptr [rdx+8], 1
0x180013fe6  cmovz   ecx, eax
0x180013fe9  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180013fed  lea     ecx, [rax-7]
0x180013ff0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180013ff8  inc     ecx
0x180013ffa  mov     [rsp+14F0h+var_14C0], ecx
0x180013ffe  mov     [rsp+14F0h+var_14B8], r15
0x180014003  call    cs:__imp_GetCurrentThreadId
0x180014009  mov     [rsp+14F0h+var_14B0], eax
0x18001400d  lea     rax, aWil; "wil"
0x180014014  mov     [rsp+14F0h+var_1498], rax
0x180014019  mov     [rsp+14F0h+var_1490], esi
0x18001401d  mov     [rsp+14F0h+var_148C], ebx
0x180014021  mov     [rsp+14F0h+var_14A8], r15
0x180014026  mov     [rsp+14F0h+var_14A0], r15
0x18001402b  mov     [rbp+13F0h+var_1448], rdi
0x18001402f  mov     [rbp+13F0h+var_1440], r14
0x180014033  mov     [rsp+14F0h+var_1488], r15
0x180014038  xorps   xmm0, xmm0
0x18001403b  xor     eax, eax
0x18001403d  movups  [rbp+13F0h+var_1468], xmm0
0x180014041  mov     [rbp+13F0h+var_1458], rax
0x180014045  xorps   xmm1, xmm1
0x180014048  movups  [rsp+14F0h+var_1480], xmm1
0x18001404d  mov     [rbp+13F0h+var_1470], rax
0x180014051  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180014058  test    rax, rax
0x18001405b  jz      short loc_180014068
0x18001405d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014062  mov     [rbp+13F0h+var_1450], rax
0x180014066  jmp     short loc_18001406C
0x180014068  mov     [rbp+13F0h+var_1450], r15
0x18001406c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180014073  test    rax, rax
0x180014076  jz      short loc_180014082
0x180014078  lea     rcx, [rsp+14F0h+var_14D0]
0x18001407d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014082  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180014089  test    rax, rax
0x18001408c  jz      short loc_1800140A2
0x18001408e  mov     r8d, 400h
0x180014094  lea     rdx, [rbp+13F0h+var_1430]
0x180014098  lea     rcx, [rsp+14F0h+var_14D0]
0x18001409d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140a2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800140a9  test    rax, rax
0x1800140ac  jz      short loc_1800140B8
0x1800140ae  lea     rcx, [rsp+14F0h+var_14D0]
0x1800140b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140b8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800140bf  test    rax, rax
0x1800140c2  jz      short loc_1800140D5
0x1800140c4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800140c9  jnz     short loc_1800140D5
0x1800140cb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800140d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140d5  cmp     [rsp+14F0h+var_14C8], r15d
0x1800140da  jge     loc_1800141E8
0x1800140e0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800140e7  jnz     short loc_180014108
0x1800140e9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800140f0  test    rax, rax
0x1800140f3  jz      short loc_1800140FE
0x1800140f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140fa  test    al, al
0x1800140fc  jmp     short loc_180014106
0x1800140fe  call    cs:__imp_IsDebuggerPresent
0x180014104  test    eax, eax
0x180014106  jz      short loc_18001410F
0x180014108  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001410d  jz      short loc_180014135
0x18001410f  mov     rax, cs:g_pfnResultLoggingCallback
0x180014116  test    rax, rax
0x180014119  jz      short loc_18001418E
0x18001411b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180014122  jnz     short loc_18001418E
0x180014124  xor     r8d, r8d
0x180014127  xor     edx, edx
0x180014129  lea     rcx, [rsp+14F0h+var_14D0]
0x18001412e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014133  jmp     short loc_18001418E
0x180014135  mov     ebx, 800h
0x18001413a  mov     rax, cs:g_pfnResultLoggingCallback
0x180014141  test    rax, rax
0x180014144  jz      short loc_180014163
0x180014146  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001414d  jnz     short loc_180014163
0x18001414f  mov     r8d, ebx
0x180014152  lea     rdx, [rbp+13F0h+OutputString]
0x180014159  lea     rcx, [rsp+14F0h+var_14D0]
0x18001415e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014163  cmp     [rbp+13F0h+OutputString], r15w
0x18001416b  jnz     short loc_180014181
0x18001416d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180014172  mov     rdx, rbx; unsigned __int16 *
0x180014175  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001417c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180014181  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180014188  call    cs:__imp_OutputDebugStringW
0x18001418e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180014193  jnz     short loc_18001419E
0x180014195  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18001419c  jz      short loc_1800141B0
0x18001419e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800141a5  test    rax, rax
0x1800141a8  jz      short loc_1800141B0
0x1800141aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141af  nop
0x1800141b0  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800141b5  jnz     short loc_1800141DD
0x1800141b7  mov     rcx, [rbp+13F0h+var_30]
0x1800141be  xor     rcx, rsp; StackCookie
0x1800141c1  call    __security_check_cookie
0x1800141c6  mov     rbx, [rsp+14F0h+arg_10]
0x1800141ce  add     rsp, 14D0h
0x1800141d5  pop     r15
0x1800141d7  pop     r14
0x1800141d9  pop     rdi
0x1800141da  pop     rsi
0x1800141db  pop     rbp
0x1800141dc  retn
0x1800141dd  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800141e2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800141e8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
