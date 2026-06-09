# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002928`
- end: `0x180002bbe`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800023d4`

## callees

- `0x180001610`
- `0x180002084`
- `0x180002928`
- `0x180003b04`
- `0x180004a30`
- `0x180005a70`
- `0x180005b4c`
- `0x180009f50`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800029d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800029d3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002ace`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002ace`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002b58`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002b58`

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
      g_pfnResultLoggingCallback(&v16, 0, 0, v14);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048, v14);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v16, v14);
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
0x180002928  mov     [rsp-8+arg_10], rbx
0x18000292d  push    rbp
0x18000292e  push    rsi
0x18000292f  push    rdi
0x180002930  push    r14
0x180002932  push    r15
0x180002934  lea     rbp, [rsp-13D0h]
0x18000293c  mov     eax, 14D0h
0x180002941  call    _alloca_probe
0x180002946  sub     rsp, rax
0x180002949  mov     rax, cs:__security_cookie
0x180002950  xor     rax, rsp
0x180002953  mov     [rbp+13F0h+var_30], rax
0x18000295a  mov     esi, edx
0x18000295c  mov     r14, rcx
0x18000295f  mov     rdi, [rbp+13F0h+arg_28]
0x180002966  xor     edx, edx; Val
0x180002968  mov     r8d, 98h; Size
0x18000296e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002973  call    memset_0
0x180002978  nop
0x180002979  xor     r15d, r15d
0x18000297c  mov     [rbp+13F0h+OutputString], r15w
0x180002984  mov     [rbp+13F0h+var_1430], r15b
0x180002988  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000298f  mov     ecx, [rdx]; this
0x180002991  mov     [rsp+14F0h+var_14C8], ecx
0x180002995  mov     eax, [rdx+4]
0x180002998  mov     [rsp+14F0h+var_14C4], eax
0x18000299c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800029a1  mov     ebx, eax
0x1800029a3  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800029ab  mov     ecx, r15d
0x1800029ae  lea     eax, [r15+8]
0x1800029b2  cmp     dword ptr [rdx+8], 1
0x1800029b6  cmovz   ecx, eax
0x1800029b9  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800029bd  lea     ecx, [rax-7]
0x1800029c0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800029c8  inc     ecx
0x1800029ca  mov     [rsp+14F0h+var_14C0], ecx
0x1800029ce  mov     [rsp+14F0h+var_14B8], r15
0x1800029d3  call    cs:__imp_GetCurrentThreadId
0x1800029d9  mov     [rsp+14F0h+var_14B0], eax
0x1800029dd  lea     rax, aWil; "wil"
0x1800029e4  mov     [rsp+14F0h+var_1498], rax
0x1800029e9  mov     [rsp+14F0h+var_1490], esi
0x1800029ed  mov     [rsp+14F0h+var_148C], ebx
0x1800029f1  mov     [rsp+14F0h+var_14A8], r15
0x1800029f6  mov     [rsp+14F0h+var_14A0], r15
0x1800029fb  mov     [rbp+13F0h+var_1448], rdi
0x1800029ff  mov     [rbp+13F0h+var_1440], r14
0x180002a03  mov     [rsp+14F0h+var_1488], r15
0x180002a08  xorps   xmm0, xmm0
0x180002a0b  xor     eax, eax
0x180002a0d  movups  [rbp+13F0h+var_1468], xmm0
0x180002a11  mov     [rbp+13F0h+var_1458], rax
0x180002a15  xorps   xmm1, xmm1
0x180002a18  movups  [rsp+14F0h+var_1480], xmm1
0x180002a1d  mov     [rbp+13F0h+var_1470], rax
0x180002a21  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002a28  test    rax, rax
0x180002a2b  jz      short loc_180002A38
0x180002a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a32  mov     [rbp+13F0h+var_1450], rax
0x180002a36  jmp     short loc_180002A3C
0x180002a38  mov     [rbp+13F0h+var_1450], r15
0x180002a3c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002a43  test    rax, rax
0x180002a46  jz      short loc_180002A52
0x180002a48  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a52  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002a59  test    rax, rax
0x180002a5c  jz      short loc_180002A72
0x180002a5e  mov     r8d, 400h
0x180002a64  lea     rdx, [rbp+13F0h+var_1430]
0x180002a68  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a72  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002a79  test    rax, rax
0x180002a7c  jz      short loc_180002A88
0x180002a7e  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a88  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002a8f  test    rax, rax
0x180002a92  jz      short loc_180002AA5
0x180002a94  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002a99  jnz     short loc_180002AA5
0x180002a9b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aa5  cmp     [rsp+14F0h+var_14C8], r15d
0x180002aaa  jge     loc_180002BB8
0x180002ab0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002ab7  jnz     short loc_180002AD8
0x180002ab9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002ac0  test    rax, rax
0x180002ac3  jz      short loc_180002ACE
0x180002ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aca  test    al, al
0x180002acc  jmp     short loc_180002AD6
0x180002ace  call    cs:__imp_IsDebuggerPresent
0x180002ad4  test    eax, eax
0x180002ad6  jz      short loc_180002ADF
0x180002ad8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002add  jz      short loc_180002B05
0x180002adf  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ae6  test    rax, rax
0x180002ae9  jz      short loc_180002B5E
0x180002aeb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002af2  jnz     short loc_180002B5E
0x180002af4  xor     r8d, r8d
0x180002af7  xor     edx, edx
0x180002af9  lea     rcx, [rsp+14F0h+var_14D0]
0x180002afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b03  jmp     short loc_180002B5E
0x180002b05  mov     ebx, 800h
0x180002b0a  mov     rax, cs:g_pfnResultLoggingCallback
0x180002b11  test    rax, rax
0x180002b14  jz      short loc_180002B33
0x180002b16  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002b1d  jnz     short loc_180002B33
0x180002b1f  mov     r8d, ebx
0x180002b22  lea     rdx, [rbp+13F0h+OutputString]
0x180002b29  lea     rcx, [rsp+14F0h+var_14D0]
0x180002b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b33  cmp     [rbp+13F0h+OutputString], r15w
0x180002b3b  jnz     short loc_180002B51
0x180002b3d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002b42  mov     rdx, rbx; unsigned __int16 *
0x180002b45  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002b4c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002b51  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002b58  call    cs:__imp_OutputDebugStringW
0x180002b5e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002b63  jnz     short loc_180002B6E
0x180002b65  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002b6c  jz      short loc_180002B80
0x180002b6e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002b75  test    rax, rax
0x180002b78  jz      short loc_180002B80
0x180002b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b7f  nop
0x180002b80  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002b85  jnz     short loc_180002BAD
0x180002b87  mov     rcx, [rbp+13F0h+var_30]
0x180002b8e  xor     rcx, rsp; StackCookie
0x180002b91  call    __security_check_cookie
0x180002b96  mov     rbx, [rsp+14F0h+arg_10]
0x180002b9e  add     rsp, 14D0h
0x180002ba5  pop     r15
0x180002ba7  pop     r14
0x180002ba9  pop     rdi
0x180002baa  pop     rsi
0x180002bab  pop     rbp
0x180002bac  retn
0x180002bad  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002bb2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002bb8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
