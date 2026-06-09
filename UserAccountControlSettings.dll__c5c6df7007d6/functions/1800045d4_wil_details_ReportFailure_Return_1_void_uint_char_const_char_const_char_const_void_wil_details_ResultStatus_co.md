# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800045d4`
- end: `0x180004868`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800042a8`

## callees

- `0x1800045d4`
- `0x1800053f4`
- `0x180006540`
- `0x180006ee8`
- `0x180007050`
- `0x18000b6de`
- `0x18000b710`
- `0x18000b7a0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000467e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000467e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004803`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004803`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004779`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004779`

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
      wil::GetFailureLogString(OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
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
0x1800045d4  mov     [rsp-8+arg_10], rbx
0x1800045d9  push    rbp
0x1800045da  push    rsi
0x1800045db  push    rdi
0x1800045dc  push    r14
0x1800045de  push    r15
0x1800045e0  lea     rbp, [rsp-13D0h]
0x1800045e8  mov     eax, 14D0h
0x1800045ed  call    _alloca_probe
0x1800045f2  sub     rsp, rax
0x1800045f5  mov     rax, cs:__security_cookie
0x1800045fc  xor     rax, rsp
0x1800045ff  mov     [rbp+13F0h+var_30], rax
0x180004606  mov     rdi, [rbp+13F0h+arg_28]
0x18000460d  mov     esi, edx
0x18000460f  mov     r14, rcx
0x180004612  xor     edx, edx; Val
0x180004614  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004619  mov     r8d, 98h; Size
0x18000461f  call    memset_0
0x180004624  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000462b  xor     r15d, r15d
0x18000462e  mov     [rbp+13F0h+OutputString], r15w
0x180004636  mov     [rbp+13F0h+var_1430], r15b
0x18000463a  mov     ecx, [rdx]; this
0x18000463c  mov     eax, [rdx+4]
0x18000463f  mov     [rsp+14F0h+var_14C8], ecx
0x180004643  mov     [rsp+14F0h+var_14C4], eax
0x180004647  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000464c  cmp     dword ptr [rdx+8], 1
0x180004650  mov     ebx, eax
0x180004652  lea     eax, [r15+8]
0x180004656  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000465e  mov     ecx, r15d
0x180004661  cmovz   ecx, eax
0x180004664  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004668  lea     ecx, [rax-7]
0x18000466b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004673  inc     ecx
0x180004675  mov     [rsp+14F0h+var_14B8], r15
0x18000467a  mov     [rsp+14F0h+var_14C0], ecx
0x18000467e  call    cs:__imp_GetCurrentThreadId
0x180004684  xorps   xmm0, xmm0
0x180004687  mov     [rsp+14F0h+var_1490], esi
0x18000468b  mov     [rsp+14F0h+var_14B0], eax
0x18000468f  xorps   xmm1, xmm1
0x180004692  lea     rax, aWil; "wil"
0x180004699  mov     [rsp+14F0h+var_148C], ebx
0x18000469d  mov     [rsp+14F0h+var_1498], rax
0x1800046a2  xor     eax, eax
0x1800046a4  mov     [rbp+13F0h+var_1458], rax
0x1800046a8  mov     [rbp+13F0h+var_1470], rax
0x1800046ac  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800046b3  mov     [rsp+14F0h+var_14A8], r15
0x1800046b8  mov     [rsp+14F0h+var_14A0], r15
0x1800046bd  mov     [rbp+13F0h+var_1448], rdi
0x1800046c1  mov     [rbp+13F0h+var_1440], r14
0x1800046c5  mov     [rsp+14F0h+var_1488], r15
0x1800046ca  movups  [rbp+13F0h+var_1468], xmm0
0x1800046ce  movups  [rsp+14F0h+var_1480], xmm1
0x1800046d3  test    rax, rax
0x1800046d6  jz      short loc_1800046E3
0x1800046d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046dd  mov     [rbp+13F0h+var_1450], rax
0x1800046e1  jmp     short loc_1800046E7
0x1800046e3  mov     [rbp+13F0h+var_1450], r15
0x1800046e7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800046ee  test    rax, rax
0x1800046f1  jz      short loc_1800046FD
0x1800046f3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800046f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046fd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004704  test    rax, rax
0x180004707  jz      short loc_18000471D
0x180004709  mov     r8d, 400h
0x18000470f  lea     rdx, [rbp+13F0h+var_1430]
0x180004713  lea     rcx, [rsp+14F0h+var_14D0]
0x180004718  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000471d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004724  test    rax, rax
0x180004727  jz      short loc_180004733
0x180004729  lea     rcx, [rsp+14F0h+var_14D0]
0x18000472e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004733  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000473a  test    rax, rax
0x18000473d  jz      short loc_180004750
0x18000473f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004744  jnz     short loc_180004750
0x180004746  lea     rcx, [rsp+14F0h+var_14D0]
0x18000474b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004750  cmp     [rsp+14F0h+var_14C8], r15d
0x180004755  jge     loc_180004857
0x18000475b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180004762  jnz     short loc_180004783
0x180004764  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000476b  test    rax, rax
0x18000476e  jz      short loc_180004779
0x180004770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004775  test    al, al
0x180004777  jmp     short loc_180004781
0x180004779  call    cs:__imp_IsDebuggerPresent
0x18000477f  test    eax, eax
0x180004781  jz      short loc_18000478A
0x180004783  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004788  jz      short loc_1800047B0
0x18000478a  mov     rax, cs:g_pfnResultLoggingCallback
0x180004791  test    rax, rax
0x180004794  jz      short loc_180004809
0x180004796  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000479d  jnz     short loc_180004809
0x18000479f  xor     r8d, r8d
0x1800047a2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800047a7  xor     edx, edx
0x1800047a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047ae  jmp     short loc_180004809
0x1800047b0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800047b7  mov     ebx, 800h
0x1800047bc  test    rax, rax
0x1800047bf  jz      short loc_1800047DE
0x1800047c1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800047c8  jnz     short loc_1800047DE
0x1800047ca  mov     r8d, ebx
0x1800047cd  lea     rdx, [rbp+13F0h+OutputString]
0x1800047d4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800047d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047de  cmp     [rbp+13F0h+OutputString], r15w
0x1800047e6  jnz     short loc_1800047FC
0x1800047e8  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800047ed  mov     rdx, rbx; unsigned __int16 *
0x1800047f0  lea     rcx, [rbp+13F0h+OutputString]; pszDest
0x1800047f7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800047fc  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180004803  call    cs:__imp_OutputDebugStringW
0x180004809  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000480e  jnz     short loc_180004819
0x180004810  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180004817  jz      short loc_18000482A
0x180004819  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004820  test    rax, rax
0x180004823  jz      short loc_18000482A
0x180004825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000482a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000482f  jnz     short loc_18000485D
0x180004831  mov     rcx, [rbp+13F0h+var_30]
0x180004838  xor     rcx, rsp; StackCookie
0x18000483b  call    __security_check_cookie
0x180004840  mov     rbx, [rsp+14F0h+arg_10]
0x180004848  add     rsp, 14D0h
0x18000484f  pop     r15
0x180004851  pop     r14
0x180004853  pop     rdi
0x180004854  pop     rsi
0x180004855  pop     rbp
0x180004856  retn
0x180004857  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000485d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004862  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
