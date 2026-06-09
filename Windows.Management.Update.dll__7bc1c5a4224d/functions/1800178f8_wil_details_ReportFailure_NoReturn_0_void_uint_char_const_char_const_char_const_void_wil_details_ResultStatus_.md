# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800178f8`
- end: `0x180017ba4`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180017870`

## callees

- `0x1800033e8`
- `0x18000b974`
- `0x18000d170`
- `0x18000f27c`
- `0x18000f9b0`
- `0x18000fb7c`
- `0x1800178f8`
- `0x180027600`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800179a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800179a1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180017b38`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180017b38`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180017a9c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180017a9c`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
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

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x1800178f8  mov     [rsp-8+arg_18], rbx
0x1800178fd  push    rbp
0x1800178fe  push    rsi
0x1800178ff  push    rdi
0x180017900  push    r12
0x180017902  push    r13
0x180017904  push    r14
0x180017906  push    r15
0x180017908  lea     rbp, [rsp-13C0h]
0x180017910  mov     eax, 14C0h
0x180017915  call    _alloca_probe
0x18001791a  sub     rsp, rax
0x18001791d  mov     r14, r8
0x180017920  mov     esi, edx
0x180017922  mov     r15, rcx
0x180017925  mov     rdi, [rbp+13F0h+arg_28]
0x18001792c  xor     r13d, r13d
0x18001792f  cmp     cs:g_pfnThrowPlatformException, r13
0x180017936  setnz   r12b
0x18001793a  xor     edx, edx; Val
0x18001793c  mov     r8d, 98h; Size
0x180017942  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180017947  call    memset_0
0x18001794c  nop
0x18001794d  mov     [rbp+13F0h+OutputString], r13w
0x180017955  mov     [rbp+13F0h+var_1430], r13b
0x180017959  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180017960  mov     ecx, [rdx]; this
0x180017962  mov     [rsp+14F0h+var_14C8], ecx
0x180017966  mov     eax, [rdx+4]
0x180017969  mov     [rsp+14F0h+var_14C4], eax
0x18001796d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180017972  mov     ebx, eax
0x180017974  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180017979  mov     ecx, r13d
0x18001797c  lea     eax, [r13+8]
0x180017980  cmp     dword ptr [rdx+8], 1
0x180017984  cmovz   ecx, eax
0x180017987  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001798b  lea     ecx, [rax-7]
0x18001798e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180017996  inc     ecx
0x180017998  mov     [rsp+14F0h+var_14C0], ecx
0x18001799c  mov     [rsp+14F0h+var_14B8], r13
0x1800179a1  call    cs:__imp_GetCurrentThreadId
0x1800179a7  mov     [rsp+14F0h+var_14B0], eax
0x1800179ab  mov     [rsp+14F0h+var_1498], r14
0x1800179b0  mov     [rsp+14F0h+var_1490], esi
0x1800179b4  mov     [rsp+14F0h+var_148C], ebx
0x1800179b8  mov     [rsp+14F0h+var_14A8], r13
0x1800179bd  mov     [rsp+14F0h+var_14A0], r13
0x1800179c2  mov     [rbp+13F0h+var_1448], rdi
0x1800179c6  mov     [rbp+13F0h+var_1440], r15
0x1800179ca  mov     [rsp+14F0h+var_1488], r13
0x1800179cf  xorps   xmm0, xmm0
0x1800179d2  xor     eax, eax
0x1800179d4  movups  [rbp+13F0h+var_1468], xmm0
0x1800179d8  mov     [rbp+13F0h+var_1458], rax
0x1800179dc  xorps   xmm1, xmm1
0x1800179df  movups  [rsp+14F0h+var_1480], xmm1
0x1800179e4  mov     [rbp+13F0h+var_1470], rax
0x1800179e8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800179ef  test    rax, rax
0x1800179f2  jz      short loc_1800179FF
0x1800179f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179f9  mov     [rbp+13F0h+var_1450], rax
0x1800179fd  jmp     short loc_180017A03
0x1800179ff  mov     [rbp+13F0h+var_1450], r13
0x180017a03  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180017a0a  test    rax, rax
0x180017a0d  jz      short loc_180017A19
0x180017a0f  lea     rcx, [rsp+14F0h+var_14D0]
0x180017a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a19  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180017a20  test    rax, rax
0x180017a23  jz      short loc_180017A39
0x180017a25  mov     r8d, 400h
0x180017a2b  lea     rdx, [rbp+13F0h+var_1430]
0x180017a2f  lea     rcx, [rsp+14F0h+var_14D0]
0x180017a34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a39  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180017a40  test    rax, rax
0x180017a43  jz      short loc_180017A4F
0x180017a45  lea     rcx, [rsp+14F0h+var_14D0]
0x180017a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a4f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180017a56  test    rax, rax
0x180017a59  jz      short loc_180017A71
0x180017a5b  test    r12b, r12b
0x180017a5e  jnz     short loc_180017A71
0x180017a60  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180017a65  jnz     short loc_180017A71
0x180017a67  lea     rcx, [rsp+14F0h+var_14D0]
0x180017a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a71  cmp     [rsp+14F0h+var_14C8], r13d
0x180017a76  jl      short loc_180017A7E
0x180017a78  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180017a7e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180017a85  jnz     short loc_180017AA6
0x180017a87  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180017a8e  test    rax, rax
0x180017a91  jz      short loc_180017A9C
0x180017a93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a98  test    al, al
0x180017a9a  jmp     short loc_180017AA4
0x180017a9c  call    cs:__imp_IsDebuggerPresent
0x180017aa2  test    eax, eax
0x180017aa4  jz      short loc_180017AAF
0x180017aa6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180017aab  mov     bl, 1
0x180017aad  jz      short loc_180017AB2
0x180017aaf  mov     bl, r13b
0x180017ab2  test    r12b, r12b
0x180017ab5  jnz     short loc_180017AE1
0x180017ab7  test    bl, bl
0x180017ab9  jnz     short loc_180017AE1
0x180017abb  mov     rax, cs:g_pfnResultLoggingCallback
0x180017ac2  test    rax, rax
0x180017ac5  jz      short loc_180017B3E
0x180017ac7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180017ace  jnz     short loc_180017B3E
0x180017ad0  xor     r8d, r8d
0x180017ad3  xor     edx, edx
0x180017ad5  lea     rcx, [rsp+14F0h+var_14D0]
0x180017ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017adf  jmp     short loc_180017B3E
0x180017ae1  mov     edi, 800h
0x180017ae6  mov     rax, cs:g_pfnResultLoggingCallback
0x180017aed  test    rax, rax
0x180017af0  jz      short loc_180017B0F
0x180017af2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180017af9  jnz     short loc_180017B0F
0x180017afb  mov     r8d, edi
0x180017afe  lea     rdx, [rbp+13F0h+OutputString]
0x180017b05  lea     rcx, [rsp+14F0h+var_14D0]
0x180017b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b0f  cmp     [rbp+13F0h+OutputString], r13w
0x180017b17  jnz     short loc_180017B2D
0x180017b19  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180017b1e  mov     rdx, rdi; unsigned __int16 *
0x180017b21  lea     rcx, [rbp+13F0h+OutputString]; this
0x180017b28  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180017b2d  test    bl, bl
0x180017b2f  jz      short loc_180017B3E
0x180017b31  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180017b38  call    cs:__imp_OutputDebugStringW
0x180017b3e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180017b43  jnz     short loc_180017B4E
0x180017b45  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180017b4c  jz      short loc_180017B60
0x180017b4e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180017b55  test    rax, rax
0x180017b58  jz      short loc_180017B60
0x180017b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b5f  nop
0x180017b60  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180017b65  jz      short loc_180017B72
0x180017b67  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180017b6c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180017b72  test    r12b, r12b
0x180017b75  jz      short loc_180017B8F
0x180017b77  lea     rdx, [rbp+13F0h+OutputString]
0x180017b7e  lea     rcx, [rsp+14F0h+var_14D0]
0x180017b83  mov     rax, cs:g_pfnThrowPlatformException
0x180017b8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017b8f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180017b94  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180017b99  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180017b9e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
