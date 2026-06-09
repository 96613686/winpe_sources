# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14004469c`
- end: `0x140044932`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140044364`

## callees

- `0x140003611`
- `0x14004469c`
- `0x140046a24`
- `0x140049324`
- `0x14004abd8`
- `0x14004ae94`
- `0x140113220`
- `0x1401132e0`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140044747`
- `KERNEL32!GetCurrentThreadId` at `0x140044747`
- `KERNEL32!IsDebuggerPresent` at `0x140044842`
- `KERNEL32!IsDebuggerPresent` at `0x140044842`
- `KERNEL32!OutputDebugStringW` at `0x1400448cc`
- `KERNEL32!OutputDebugStringW` at `0x1400448cc`

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
0x14004469c  mov     [rsp-8+arg_10], rbx
0x1400446a1  push    rbp
0x1400446a2  push    rsi
0x1400446a3  push    rdi
0x1400446a4  push    r14
0x1400446a6  push    r15
0x1400446a8  lea     rbp, [rsp-13D0h]
0x1400446b0  mov     eax, 14D0h
0x1400446b5  call    _alloca_probe
0x1400446ba  sub     rsp, rax
0x1400446bd  mov     rax, cs:__security_cookie
0x1400446c4  xor     rax, rsp
0x1400446c7  mov     [rbp+13F0h+var_30], rax
0x1400446ce  mov     esi, edx
0x1400446d0  mov     r14, rcx
0x1400446d3  mov     rdi, [rbp+13F0h+arg_28]
0x1400446da  xor     edx, edx; Val
0x1400446dc  mov     r8d, 98h; Size
0x1400446e2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400446e7  call    memset_0
0x1400446ec  nop
0x1400446ed  xor     r15d, r15d
0x1400446f0  mov     [rbp+13F0h+OutputString], r15w
0x1400446f8  mov     [rbp+13F0h+var_1430], r15b
0x1400446fc  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140044703  mov     ecx, [rdx]; this
0x140044705  mov     [rsp+14F0h+var_14C8], ecx
0x140044709  mov     eax, [rdx+4]
0x14004470c  mov     [rsp+14F0h+var_14C4], eax
0x140044710  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140044715  mov     ebx, eax
0x140044717  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x14004471f  mov     ecx, r15d
0x140044722  lea     eax, [r15+8]
0x140044726  cmp     dword ptr [rdx+8], 1
0x14004472a  cmovz   ecx, eax
0x14004472d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140044731  lea     ecx, [rax-7]
0x140044734  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14004473c  inc     ecx
0x14004473e  mov     [rsp+14F0h+var_14C0], ecx
0x140044742  mov     [rsp+14F0h+var_14B8], r15
0x140044747  call    cs:__imp_GetCurrentThreadId
0x14004474d  mov     [rsp+14F0h+var_14B0], eax
0x140044751  lea     rax, aWil; "wil"
0x140044758  mov     [rsp+14F0h+var_1498], rax
0x14004475d  mov     [rsp+14F0h+var_1490], esi
0x140044761  mov     [rsp+14F0h+var_148C], ebx
0x140044765  mov     [rsp+14F0h+var_14A8], r15
0x14004476a  mov     [rsp+14F0h+var_14A0], r15
0x14004476f  mov     [rbp+13F0h+var_1448], rdi
0x140044773  mov     [rbp+13F0h+var_1440], r14
0x140044777  mov     [rsp+14F0h+var_1488], r15
0x14004477c  xorps   xmm0, xmm0
0x14004477f  xor     eax, eax
0x140044781  movups  [rbp+13F0h+var_1468], xmm0
0x140044785  mov     [rbp+13F0h+var_1458], rax
0x140044789  xorps   xmm1, xmm1
0x14004478c  movups  [rsp+14F0h+var_1480], xmm1
0x140044791  mov     [rbp+13F0h+var_1470], rax
0x140044795  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14004479c  test    rax, rax
0x14004479f  jz      short loc_1400447AC
0x1400447a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400447a6  mov     [rbp+13F0h+var_1450], rax
0x1400447aa  jmp     short loc_1400447B0
0x1400447ac  mov     [rbp+13F0h+var_1450], r15
0x1400447b0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400447b7  test    rax, rax
0x1400447ba  jz      short loc_1400447C6
0x1400447bc  lea     rcx, [rsp+14F0h+var_14D0]
0x1400447c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400447c6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400447cd  test    rax, rax
0x1400447d0  jz      short loc_1400447E6
0x1400447d2  mov     r8d, 400h
0x1400447d8  lea     rdx, [rbp+13F0h+var_1430]
0x1400447dc  lea     rcx, [rsp+14F0h+var_14D0]
0x1400447e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400447e6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400447ed  test    rax, rax
0x1400447f0  jz      short loc_1400447FC
0x1400447f2  lea     rcx, [rsp+14F0h+var_14D0]
0x1400447f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400447fc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140044803  test    rax, rax
0x140044806  jz      short loc_140044819
0x140044808  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14004480d  jnz     short loc_140044819
0x14004480f  lea     rcx, [rsp+14F0h+var_14D0]
0x140044814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044819  cmp     [rsp+14F0h+var_14C8], r15d
0x14004481e  jge     loc_14004492C
0x140044824  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x14004482b  jnz     short loc_14004484C
0x14004482d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140044834  test    rax, rax
0x140044837  jz      short loc_140044842
0x140044839  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004483e  test    al, al
0x140044840  jmp     short loc_14004484A
0x140044842  call    cs:__imp_IsDebuggerPresent
0x140044848  test    eax, eax
0x14004484a  jz      short loc_140044853
0x14004484c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140044851  jz      short loc_140044879
0x140044853  mov     rax, cs:g_pfnResultLoggingCallback
0x14004485a  test    rax, rax
0x14004485d  jz      short loc_1400448D2
0x14004485f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140044866  jnz     short loc_1400448D2
0x140044868  xor     r8d, r8d
0x14004486b  xor     edx, edx
0x14004486d  lea     rcx, [rsp+14F0h+var_14D0]
0x140044872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140044877  jmp     short loc_1400448D2
0x140044879  mov     ebx, 800h
0x14004487e  mov     rax, cs:g_pfnResultLoggingCallback
0x140044885  test    rax, rax
0x140044888  jz      short loc_1400448A7
0x14004488a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140044891  jnz     short loc_1400448A7
0x140044893  mov     r8d, ebx
0x140044896  lea     rdx, [rbp+13F0h+OutputString]
0x14004489d  lea     rcx, [rsp+14F0h+var_14D0]
0x1400448a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400448a7  cmp     [rbp+13F0h+OutputString], r15w
0x1400448af  jnz     short loc_1400448C5
0x1400448b1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400448b6  mov     rdx, rbx; unsigned __int16 *
0x1400448b9  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400448c0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400448c5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400448cc  call    cs:__imp_OutputDebugStringW
0x1400448d2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400448d7  jnz     short loc_1400448E2
0x1400448d9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1400448e0  jz      short loc_1400448F4
0x1400448e2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400448e9  test    rax, rax
0x1400448ec  jz      short loc_1400448F4
0x1400448ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400448f3  nop
0x1400448f4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1400448f9  jnz     short loc_140044921
0x1400448fb  mov     rcx, [rbp+13F0h+var_30]
0x140044902  xor     rcx, rsp; StackCookie
0x140044905  call    __security_check_cookie
0x14004490a  mov     rbx, [rsp+14F0h+arg_10]
0x140044912  add     rsp, 14D0h
0x140044919  pop     r15
0x14004491b  pop     r14
0x14004491d  pop     rdi
0x14004491e  pop     rsi
0x14004491f  pop     rbp
0x140044920  retn
0x140044921  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140044926  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14004492c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
