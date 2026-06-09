# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002938`
- end: `0x180002bb1`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002554`

## callees

- `0x180001e5a`
- `0x180002938`
- `0x180003f94`
- `0x180004734`
- `0x180004ea0`
- `0x180005f50`
- `0x180006b70`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800029f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800029f1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002af4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002af4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002b7e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002b7e`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180002938  mov     [rsp-8+arg_18], rbx
0x18000293d  push    rbp
0x18000293e  push    rsi
0x18000293f  push    rdi
0x180002940  push    r12
0x180002942  push    r13
0x180002944  push    r14
0x180002946  push    r15
0x180002948  lea     rbp, [rsp-13C0h]
0x180002950  mov     eax, 14C0h
0x180002955  call    _alloca_probe
0x18000295a  sub     rsp, rax
0x18000295d  mov     r14, r8
0x180002960  mov     esi, edx
0x180002962  mov     rdi, rcx
0x180002965  mov     r15, [rbp+13F0h+arg_28]
0x18000296c  xor     edx, edx; Val
0x18000296e  mov     r8d, 98h; Size
0x180002974  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002979  call    memset_0
0x18000297e  nop
0x18000297f  xor     r13d, r13d
0x180002982  mov     [rbp+13F0h+OutputString], r13w
0x18000298a  mov     [rbp+13F0h+var_1430], r13b
0x18000298e  mov     rbx, [rbp+13F0h+arg_30]
0x180002995  mov     ecx, [rbx]; this
0x180002997  mov     [rsp+14F0h+var_14C8], ecx
0x18000299b  mov     eax, [rbx+4]
0x18000299e  mov     [rsp+14F0h+var_14C4], eax
0x1800029a2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800029a7  mov     r12d, eax
0x1800029aa  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800029b2  mov     ecx, r13d
0x1800029b5  lea     eax, [r13+8]
0x1800029b9  cmp     dword ptr [rbx+8], 1
0x1800029bd  cmovz   ecx, eax
0x1800029c0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800029c4  lea     ecx, [rax-7]
0x1800029c7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800029cf  inc     ecx
0x1800029d1  mov     [rsp+14F0h+var_14C0], ecx
0x1800029d5  mov     rcx, [rbp+13F0h+arg_38]
0x1800029dc  test    rcx, rcx
0x1800029df  jz      short loc_1800029EC
0x1800029e1  cmp     [rcx], r13w
0x1800029e5  mov     [rsp+14F0h+var_14B8], rcx
0x1800029ea  jnz     short loc_1800029F1
0x1800029ec  mov     [rsp+14F0h+var_14B8], r13
0x1800029f1  call    cs:__imp_GetCurrentThreadId
0x1800029f7  mov     [rsp+14F0h+var_14B0], eax
0x1800029fb  mov     [rsp+14F0h+var_1498], r14
0x180002a00  mov     [rsp+14F0h+var_1490], esi
0x180002a04  mov     [rsp+14F0h+var_148C], r12d
0x180002a09  mov     [rsp+14F0h+var_14A8], r13
0x180002a0e  mov     [rsp+14F0h+var_14A0], r13
0x180002a13  mov     [rbp+13F0h+var_1448], r15
0x180002a17  mov     [rbp+13F0h+var_1440], rdi
0x180002a1b  mov     [rsp+14F0h+var_1488], r13
0x180002a20  xorps   xmm0, xmm0
0x180002a23  xor     eax, eax
0x180002a25  movups  [rbp+13F0h+var_1468], xmm0
0x180002a29  mov     [rbp+13F0h+var_1458], rax
0x180002a2d  xorps   xmm1, xmm1
0x180002a30  movups  [rsp+14F0h+var_1480], xmm1
0x180002a35  mov     [rbp+13F0h+var_1470], rax
0x180002a39  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002a40  test    rax, rax
0x180002a43  jz      short loc_180002A50
0x180002a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a4a  mov     [rbp+13F0h+var_1450], rax
0x180002a4e  jmp     short loc_180002A54
0x180002a50  mov     [rbp+13F0h+var_1450], r13
0x180002a54  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002a5b  test    rax, rax
0x180002a5e  jz      short loc_180002A6A
0x180002a60  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a6a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002a71  test    rax, rax
0x180002a74  jz      short loc_180002A8A
0x180002a76  mov     r8d, 400h
0x180002a7c  lea     rdx, [rbp+13F0h+var_1430]
0x180002a80  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a8a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002a91  test    rax, rax
0x180002a94  jz      short loc_180002AA0
0x180002a96  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aa0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002aa7  test    rax, rax
0x180002aaa  jz      short loc_180002ABD
0x180002aac  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002ab1  jnz     short loc_180002ABD
0x180002ab3  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002abd  cmp     [rsp+14F0h+var_14C8], r13d
0x180002ac2  jl      short loc_180002AD6
0x180002ac4  mov     ecx, 8000FFFFh; this
0x180002ac9  mov     [rsp+14F0h+var_14C8], ecx
0x180002acd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002ad2  mov     [rsp+14F0h+var_14C4], eax
0x180002ad6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002add  jnz     short loc_180002AFE
0x180002adf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002ae6  test    rax, rax
0x180002ae9  jz      short loc_180002AF4
0x180002aeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002af0  test    al, al
0x180002af2  jmp     short loc_180002AFC
0x180002af4  call    cs:__imp_IsDebuggerPresent
0x180002afa  test    eax, eax
0x180002afc  jz      short loc_180002B05
0x180002afe  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002b03  jz      short loc_180002B2B
0x180002b05  mov     rax, cs:g_pfnResultLoggingCallback
0x180002b0c  test    rax, rax
0x180002b0f  jz      short loc_180002B84
0x180002b11  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002b18  jnz     short loc_180002B84
0x180002b1a  xor     r8d, r8d
0x180002b1d  xor     edx, edx
0x180002b1f  lea     rcx, [rsp+14F0h+var_14D0]
0x180002b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b29  jmp     short loc_180002B84
0x180002b2b  mov     ebx, 800h
0x180002b30  mov     rax, cs:g_pfnResultLoggingCallback
0x180002b37  test    rax, rax
0x180002b3a  jz      short loc_180002B59
0x180002b3c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002b43  jnz     short loc_180002B59
0x180002b45  mov     r8d, ebx
0x180002b48  lea     rdx, [rbp+13F0h+OutputString]
0x180002b4f  lea     rcx, [rsp+14F0h+var_14D0]
0x180002b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b59  cmp     [rbp+13F0h+OutputString], r13w
0x180002b61  jnz     short loc_180002B77
0x180002b63  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002b68  mov     rdx, rbx; unsigned __int16 *
0x180002b6b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002b72  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002b77  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002b7e  call    cs:__imp_OutputDebugStringW
0x180002b84  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002b89  jnz     short loc_180002B94
0x180002b8b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002b92  jz      short loc_180002BA6
0x180002b94  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002b9b  test    rax, rax
0x180002b9e  jz      short loc_180002BA6
0x180002ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ba5  nop
0x180002ba6  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002bab  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
