# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14001be40`
- end: `0x14001c0d6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14001b928`

## callees

- `0x140003e50`
- `0x140004a78`
- `0x14001be40`
- `0x14001cf14`
- `0x14001de10`
- `0x14001ed80`
- `0x14001ee5c`
- `0x14008f070`
- `0x14009b010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x14001c070`
- `KERNEL32!OutputDebugStringW` at `0x14001c070`
- `KERNEL32!GetCurrentThreadId` at `0x14001beeb`
- `KERNEL32!GetCurrentThreadId` at `0x14001beeb`
- `KERNEL32!IsDebuggerPresent` at `0x14001bfe6`
- `KERNEL32!IsDebuggerPresent` at `0x14001bfe6`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
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
0x14001be40  mov     [rsp-8+arg_10], rbx
0x14001be45  push    rbp
0x14001be46  push    rsi
0x14001be47  push    rdi
0x14001be48  push    r14
0x14001be4a  push    r15
0x14001be4c  lea     rbp, [rsp-13D0h]
0x14001be54  mov     eax, 14D0h
0x14001be59  call    _alloca_probe
0x14001be5e  sub     rsp, rax
0x14001be61  mov     rax, cs:__security_cookie
0x14001be68  xor     rax, rsp
0x14001be6b  mov     [rbp+13F0h+var_30], rax
0x14001be72  mov     esi, edx
0x14001be74  mov     r14, rcx
0x14001be77  mov     rdi, [rbp+13F0h+arg_28]
0x14001be7e  xor     edx, edx; Val
0x14001be80  mov     r8d, 98h; Size
0x14001be86  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14001be8b  call    memset_0
0x14001be90  nop
0x14001be91  xor     r15d, r15d
0x14001be94  mov     [rbp+13F0h+OutputString], r15w
0x14001be9c  mov     [rbp+13F0h+var_1430], r15b
0x14001bea0  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x14001bea7  mov     ecx, [rdx]; this
0x14001bea9  mov     [rsp+14F0h+var_14C8], ecx
0x14001bead  mov     eax, [rdx+4]
0x14001beb0  mov     [rsp+14F0h+var_14C4], eax
0x14001beb4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14001beb9  mov     ebx, eax
0x14001bebb  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x14001bec3  mov     ecx, r15d
0x14001bec6  lea     eax, [r15+8]
0x14001beca  cmp     dword ptr [rdx+8], 1
0x14001bece  cmovz   ecx, eax
0x14001bed1  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14001bed5  lea     ecx, [rax-7]
0x14001bed8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14001bee0  inc     ecx
0x14001bee2  mov     [rsp+14F0h+var_14C0], ecx
0x14001bee6  mov     [rsp+14F0h+var_14B8], r15
0x14001beeb  call    cs:__imp_GetCurrentThreadId
0x14001bef1  mov     [rsp+14F0h+var_14B0], eax
0x14001bef5  lea     rax, aWil; "wil"
0x14001befc  mov     [rsp+14F0h+var_1498], rax
0x14001bf01  mov     [rsp+14F0h+var_1490], esi
0x14001bf05  mov     [rsp+14F0h+var_148C], ebx
0x14001bf09  mov     [rsp+14F0h+var_14A8], r15
0x14001bf0e  mov     [rsp+14F0h+var_14A0], r15
0x14001bf13  mov     [rbp+13F0h+var_1448], rdi
0x14001bf17  mov     [rbp+13F0h+var_1440], r14
0x14001bf1b  mov     [rsp+14F0h+var_1488], r15
0x14001bf20  xorps   xmm0, xmm0
0x14001bf23  xor     eax, eax
0x14001bf25  movups  [rbp+13F0h+var_1468], xmm0
0x14001bf29  mov     [rbp+13F0h+var_1458], rax
0x14001bf2d  xorps   xmm1, xmm1
0x14001bf30  movups  [rsp+14F0h+var_1480], xmm1
0x14001bf35  mov     [rbp+13F0h+var_1470], rax
0x14001bf39  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14001bf40  test    rax, rax
0x14001bf43  jz      short loc_14001BF50
0x14001bf45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bf4a  mov     [rbp+13F0h+var_1450], rax
0x14001bf4e  jmp     short loc_14001BF54
0x14001bf50  mov     [rbp+13F0h+var_1450], r15
0x14001bf54  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14001bf5b  test    rax, rax
0x14001bf5e  jz      short loc_14001BF6A
0x14001bf60  lea     rcx, [rsp+14F0h+var_14D0]
0x14001bf65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bf6a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14001bf71  test    rax, rax
0x14001bf74  jz      short loc_14001BF8A
0x14001bf76  mov     r8d, 400h
0x14001bf7c  lea     rdx, [rbp+13F0h+var_1430]
0x14001bf80  lea     rcx, [rsp+14F0h+var_14D0]
0x14001bf85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bf8a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14001bf91  test    rax, rax
0x14001bf94  jz      short loc_14001BFA0
0x14001bf96  lea     rcx, [rsp+14F0h+var_14D0]
0x14001bf9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bfa0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14001bfa7  test    rax, rax
0x14001bfaa  jz      short loc_14001BFBD
0x14001bfac  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14001bfb1  jnz     short loc_14001BFBD
0x14001bfb3  lea     rcx, [rsp+14F0h+var_14D0]
0x14001bfb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bfbd  cmp     [rsp+14F0h+var_14C8], r15d
0x14001bfc2  jge     loc_14001C0D0
0x14001bfc8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x14001bfcf  jnz     short loc_14001BFF0
0x14001bfd1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14001bfd8  test    rax, rax
0x14001bfdb  jz      short loc_14001BFE6
0x14001bfdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001bfe2  test    al, al
0x14001bfe4  jmp     short loc_14001BFEE
0x14001bfe6  call    cs:__imp_IsDebuggerPresent
0x14001bfec  test    eax, eax
0x14001bfee  jz      short loc_14001BFF7
0x14001bff0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14001bff5  jz      short loc_14001C01D
0x14001bff7  mov     rax, cs:g_pfnResultLoggingCallback
0x14001bffe  test    rax, rax
0x14001c001  jz      short loc_14001C076
0x14001c003  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14001c00a  jnz     short loc_14001C076
0x14001c00c  xor     r8d, r8d
0x14001c00f  xor     edx, edx
0x14001c011  lea     rcx, [rsp+14F0h+var_14D0]
0x14001c016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c01b  jmp     short loc_14001C076
0x14001c01d  mov     ebx, 800h
0x14001c022  mov     rax, cs:g_pfnResultLoggingCallback
0x14001c029  test    rax, rax
0x14001c02c  jz      short loc_14001C04B
0x14001c02e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14001c035  jnz     short loc_14001C04B
0x14001c037  mov     r8d, ebx
0x14001c03a  lea     rdx, [rbp+13F0h+OutputString]
0x14001c041  lea     rcx, [rsp+14F0h+var_14D0]
0x14001c046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c04b  cmp     [rbp+13F0h+OutputString], r15w
0x14001c053  jnz     short loc_14001C069
0x14001c055  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14001c05a  mov     rdx, rbx; wchar_t *
0x14001c05d  lea     rcx, [rbp+13F0h+OutputString]; this
0x14001c064  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x14001c069  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14001c070  call    cs:__imp_OutputDebugStringW
0x14001c076  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14001c07b  jnz     short loc_14001C086
0x14001c07d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x14001c084  jz      short loc_14001C098
0x14001c086  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14001c08d  test    rax, rax
0x14001c090  jz      short loc_14001C098
0x14001c092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c097  nop
0x14001c098  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x14001c09d  jnz     short loc_14001C0C5
0x14001c09f  mov     rcx, [rbp+13F0h+var_30]
0x14001c0a6  xor     rcx, rsp; StackCookie
0x14001c0a9  call    __security_check_cookie
0x14001c0ae  mov     rbx, [rsp+14F0h+arg_10]
0x14001c0b6  add     rsp, 14D0h
0x14001c0bd  pop     r15
0x14001c0bf  pop     r14
0x14001c0c1  pop     rdi
0x14001c0c2  pop     rsi
0x14001c0c3  pop     rbp
0x14001c0c4  retn
0x14001c0c5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14001c0ca  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14001c0d0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
