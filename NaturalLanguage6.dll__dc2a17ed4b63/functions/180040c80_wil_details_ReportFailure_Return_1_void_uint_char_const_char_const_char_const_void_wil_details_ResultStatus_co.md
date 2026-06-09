# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180040c80`
- end: `0x180040f14`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18003839c`

## callees

- `0x18003f554`
- `0x180040c80`
- `0x18004ba38`
- `0x18004c60c`
- `0x18004c6e8`
- `0x18009e2c2`
- `0x18009e300`
- `0x18009e3c0`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040d2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180040d2a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180040e25`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180040e25`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180040eaf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180040eaf`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
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
  v28 = "wil";
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
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
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x180040c80  mov     [rsp-8+arg_10], rbx
0x180040c85  push    rbp
0x180040c86  push    rsi
0x180040c87  push    rdi
0x180040c88  push    r14
0x180040c8a  push    r15
0x180040c8c  lea     rbp, [rsp-13D0h]
0x180040c94  mov     eax, 14D0h
0x180040c99  call    _alloca_probe
0x180040c9e  sub     rsp, rax
0x180040ca1  mov     rax, cs:__security_cookie
0x180040ca8  xor     rax, rsp
0x180040cab  mov     [rbp+13F0h+var_30], rax
0x180040cb2  mov     rdi, [rbp+13F0h+arg_28]
0x180040cb9  mov     esi, edx
0x180040cbb  mov     r14, rcx
0x180040cbe  xor     edx, edx; Val
0x180040cc0  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180040cc5  mov     r8d, 98h; Size
0x180040ccb  call    memset_0
0x180040cd0  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180040cd7  xor     r15d, r15d
0x180040cda  mov     [rbp+13F0h+OutputString], r15w
0x180040ce2  mov     [rbp+13F0h+var_1430], r15b
0x180040ce6  mov     ecx, [rdx]; this
0x180040ce8  mov     eax, [rdx+4]
0x180040ceb  mov     [rsp+14F0h+var_14C8], ecx
0x180040cef  mov     [rsp+14F0h+var_14C4], eax
0x180040cf3  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180040cf8  cmp     dword ptr [rdx+8], 1
0x180040cfc  mov     ebx, eax
0x180040cfe  lea     eax, [r15+8]
0x180040d02  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180040d0a  mov     ecx, r15d
0x180040d0d  cmovz   ecx, eax
0x180040d10  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180040d14  lea     ecx, [rax-7]
0x180040d17  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180040d1f  inc     ecx
0x180040d21  mov     [rsp+14F0h+var_14B8], r15
0x180040d26  mov     [rsp+14F0h+var_14C0], ecx
0x180040d2a  call    cs:__imp_GetCurrentThreadId
0x180040d30  xorps   xmm0, xmm0
0x180040d33  mov     [rsp+14F0h+var_1490], esi
0x180040d37  mov     [rsp+14F0h+var_14B0], eax
0x180040d3b  xorps   xmm1, xmm1
0x180040d3e  lea     rax, aWil; "wil"
0x180040d45  mov     [rsp+14F0h+var_148C], ebx
0x180040d49  mov     [rsp+14F0h+var_1498], rax
0x180040d4e  xor     eax, eax
0x180040d50  mov     [rbp+13F0h+var_1458], rax
0x180040d54  mov     [rbp+13F0h+var_1470], rax
0x180040d58  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180040d5f  mov     [rsp+14F0h+var_14A8], r15
0x180040d64  mov     [rsp+14F0h+var_14A0], r15
0x180040d69  mov     [rbp+13F0h+var_1448], rdi
0x180040d6d  mov     [rbp+13F0h+var_1440], r14
0x180040d71  mov     [rsp+14F0h+var_1488], r15
0x180040d76  movups  [rbp+13F0h+var_1468], xmm0
0x180040d7a  movups  [rsp+14F0h+var_1480], xmm1
0x180040d7f  test    rax, rax
0x180040d82  jz      short loc_180040D8F
0x180040d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040d89  mov     [rbp+13F0h+var_1450], rax
0x180040d8d  jmp     short loc_180040D93
0x180040d8f  mov     [rbp+13F0h+var_1450], r15
0x180040d93  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180040d9a  test    rax, rax
0x180040d9d  jz      short loc_180040DA9
0x180040d9f  lea     rcx, [rsp+14F0h+var_14D0]
0x180040da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040da9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180040db0  test    rax, rax
0x180040db3  jz      short loc_180040DC9
0x180040db5  mov     r8d, 400h
0x180040dbb  lea     rdx, [rbp+13F0h+var_1430]
0x180040dbf  lea     rcx, [rsp+14F0h+var_14D0]
0x180040dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040dc9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180040dd0  test    rax, rax
0x180040dd3  jz      short loc_180040DDF
0x180040dd5  lea     rcx, [rsp+14F0h+var_14D0]
0x180040dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ddf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180040de6  test    rax, rax
0x180040de9  jz      short loc_180040DFC
0x180040deb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180040df0  jnz     short loc_180040DFC
0x180040df2  lea     rcx, [rsp+14F0h+var_14D0]
0x180040df7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040dfc  cmp     [rsp+14F0h+var_14C8], r15d
0x180040e01  jge     loc_180040F03
0x180040e07  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180040e0e  jnz     short loc_180040E2F
0x180040e10  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180040e17  test    rax, rax
0x180040e1a  jz      short loc_180040E25
0x180040e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e21  test    al, al
0x180040e23  jmp     short loc_180040E2D
0x180040e25  call    cs:__imp_IsDebuggerPresent
0x180040e2b  test    eax, eax
0x180040e2d  jz      short loc_180040E36
0x180040e2f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180040e34  jz      short loc_180040E5C
0x180040e36  mov     rax, cs:g_pfnResultLoggingCallback
0x180040e3d  test    rax, rax
0x180040e40  jz      short loc_180040EB5
0x180040e42  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180040e49  jnz     short loc_180040EB5
0x180040e4b  xor     r8d, r8d
0x180040e4e  lea     rcx, [rsp+14F0h+var_14D0]
0x180040e53  xor     edx, edx
0x180040e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e5a  jmp     short loc_180040EB5
0x180040e5c  mov     rax, cs:g_pfnResultLoggingCallback
0x180040e63  mov     ebx, 800h
0x180040e68  test    rax, rax
0x180040e6b  jz      short loc_180040E8A
0x180040e6d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180040e74  jnz     short loc_180040E8A
0x180040e76  mov     r8d, ebx
0x180040e79  lea     rdx, [rbp+13F0h+OutputString]
0x180040e80  lea     rcx, [rsp+14F0h+var_14D0]
0x180040e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040e8a  cmp     [rbp+13F0h+OutputString], r15w
0x180040e92  jnz     short loc_180040EA8
0x180040e94  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180040e99  mov     rdx, rbx; unsigned __int16 *
0x180040e9c  lea     rcx, [rbp+13F0h+OutputString]; this
0x180040ea3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180040ea8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180040eaf  call    cs:__imp_OutputDebugStringW
0x180040eb5  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180040eba  jnz     short loc_180040EC5
0x180040ebc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180040ec3  jz      short loc_180040ED6
0x180040ec5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180040ecc  test    rax, rax
0x180040ecf  jz      short loc_180040ED6
0x180040ed1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040ed6  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180040edb  jnz     short loc_180040F09
0x180040edd  mov     rcx, [rbp+13F0h+var_30]
0x180040ee4  xor     rcx, rsp; StackCookie
0x180040ee7  call    __security_check_cookie
0x180040eec  mov     rbx, [rsp+14F0h+arg_10]
0x180040ef4  add     rsp, 14D0h
0x180040efb  pop     r15
0x180040efd  pop     r14
0x180040eff  pop     rdi
0x180040f00  pop     rsi
0x180040f01  pop     rbp
0x180040f02  retn
0x180040f03  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180040f09  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180040f0e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
