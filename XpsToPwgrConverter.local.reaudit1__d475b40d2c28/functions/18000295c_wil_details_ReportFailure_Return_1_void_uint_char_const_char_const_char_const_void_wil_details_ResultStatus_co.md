# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000295c`
- end: `0x180002c02`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800023e8`

## callees

- `0x180001760`
- `0x180002194`
- `0x18000295c`
- `0x1800049e4`
- `0x180005ef8`
- `0x180008230`
- `0x1800083fc`
- `0x18000f4f0`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a22`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002a22`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002b17`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002b17`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002ba1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002ba1`

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
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x18000295c  push    rbp
0x18000295e  push    rbx
0x18000295f  push    rsi
0x180002960  push    rdi
0x180002961  push    r12
0x180002963  push    r14
0x180002965  push    r15
0x180002967  lea     rbp, [rsp-13D0h]
0x18000296f  mov     eax, 14D0h
0x180002974  call    _alloca_probe
0x180002979  sub     rsp, rax
0x18000297c  mov     rax, cs:__security_cookie
0x180002983  xor     rax, rsp
0x180002986  mov     [rbp+1400h+var_40], rax
0x18000298d  mov     rsi, r8
0x180002990  mov     edi, edx
0x180002992  mov     rbx, rcx
0x180002995  mov     r14, [rbp+1400h+arg_28]
0x18000299c  xor     edx, edx; Val
0x18000299e  mov     r8d, 98h; Size
0x1800029a4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800029a9  call    memset_0
0x1800029ae  nop
0x1800029af  xor     r12d, r12d
0x1800029b2  mov     [rbp+1400h+OutputString], r12w
0x1800029ba  mov     [rbp+1400h+var_1440], r12b
0x1800029be  mov     rdx, [rbp+1400h+arg_30]; int
0x1800029c5  mov     ecx, [rdx]; this
0x1800029c7  mov     [rsp+1500h+var_14D8], ecx
0x1800029cb  mov     eax, [rdx+4]
0x1800029ce  mov     [rsp+1500h+var_14D4], eax
0x1800029d2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800029d7  mov     r15d, eax
0x1800029da  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800029e2  mov     ecx, r12d
0x1800029e5  lea     eax, [r12+8]
0x1800029ea  cmp     dword ptr [rdx+8], 1
0x1800029ee  cmovz   ecx, eax
0x1800029f1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800029f5  lea     ecx, [rax-7]
0x1800029f8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002a00  inc     ecx
0x180002a02  mov     [rsp+1500h+var_14D0], ecx
0x180002a06  mov     rcx, [rbp+1400h+arg_38]
0x180002a0d  test    rcx, rcx
0x180002a10  jz      short loc_180002A1D
0x180002a12  cmp     [rcx], r12w
0x180002a16  mov     [rsp+1500h+var_14C8], rcx
0x180002a1b  jnz     short loc_180002A22
0x180002a1d  mov     [rsp+1500h+var_14C8], r12
0x180002a22  call    cs:__imp_GetCurrentThreadId
0x180002a28  mov     [rsp+1500h+var_14C0], eax
0x180002a2c  mov     [rsp+1500h+var_14A8], rsi
0x180002a31  mov     [rsp+1500h+var_14A0], edi
0x180002a35  mov     [rsp+1500h+var_149C], r15d
0x180002a3a  mov     [rsp+1500h+var_14B8], r12
0x180002a3f  mov     [rsp+1500h+var_14B0], r12
0x180002a44  mov     [rbp+1400h+var_1458], r14
0x180002a48  mov     [rbp+1400h+var_1450], rbx
0x180002a4c  mov     [rsp+1500h+var_1498], r12
0x180002a51  xorps   xmm0, xmm0
0x180002a54  xor     eax, eax
0x180002a56  movups  [rbp+1400h+var_1478], xmm0
0x180002a5a  mov     [rbp+1400h+var_1468], rax
0x180002a5e  xorps   xmm1, xmm1
0x180002a61  movups  [rsp+1500h+var_1490], xmm1
0x180002a66  mov     [rbp+1400h+var_1480], rax
0x180002a6a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002a71  test    rax, rax
0x180002a74  jz      short loc_180002A81
0x180002a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a7b  mov     [rbp+1400h+var_1460], rax
0x180002a7f  jmp     short loc_180002A85
0x180002a81  mov     [rbp+1400h+var_1460], r12
0x180002a85  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002a8c  test    rax, rax
0x180002a8f  jz      short loc_180002A9B
0x180002a91  lea     rcx, [rsp+1500h+var_14E0]
0x180002a96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a9b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002aa2  test    rax, rax
0x180002aa5  jz      short loc_180002ABB
0x180002aa7  mov     r8d, 400h
0x180002aad  lea     rdx, [rbp+1400h+var_1440]
0x180002ab1  lea     rcx, [rsp+1500h+var_14E0]
0x180002ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002abb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002ac2  test    rax, rax
0x180002ac5  jz      short loc_180002AD1
0x180002ac7  lea     rcx, [rsp+1500h+var_14E0]
0x180002acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ad1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002ad8  test    rax, rax
0x180002adb  jz      short loc_180002AEE
0x180002add  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002ae2  jnz     short loc_180002AEE
0x180002ae4  lea     rcx, [rsp+1500h+var_14E0]
0x180002ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aee  cmp     [rsp+1500h+var_14D8], r12d
0x180002af3  jge     loc_180002BFC
0x180002af9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002b00  jnz     short loc_180002B21
0x180002b02  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002b09  test    rax, rax
0x180002b0c  jz      short loc_180002B17
0x180002b0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b13  test    al, al
0x180002b15  jmp     short loc_180002B1F
0x180002b17  call    cs:__imp_IsDebuggerPresent
0x180002b1d  test    eax, eax
0x180002b1f  jz      short loc_180002B28
0x180002b21  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002b26  jz      short loc_180002B4E
0x180002b28  mov     rax, cs:g_pfnResultLoggingCallback
0x180002b2f  test    rax, rax
0x180002b32  jz      short loc_180002BA7
0x180002b34  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002b3b  jnz     short loc_180002BA7
0x180002b3d  xor     r8d, r8d
0x180002b40  xor     edx, edx
0x180002b42  lea     rcx, [rsp+1500h+var_14E0]
0x180002b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b4c  jmp     short loc_180002BA7
0x180002b4e  mov     ebx, 800h
0x180002b53  mov     rax, cs:g_pfnResultLoggingCallback
0x180002b5a  test    rax, rax
0x180002b5d  jz      short loc_180002B7C
0x180002b5f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002b66  jnz     short loc_180002B7C
0x180002b68  mov     r8d, ebx
0x180002b6b  lea     rdx, [rbp+1400h+OutputString]
0x180002b72  lea     rcx, [rsp+1500h+var_14E0]
0x180002b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b7c  cmp     [rbp+1400h+OutputString], r12w
0x180002b84  jnz     short loc_180002B9A
0x180002b86  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180002b8b  mov     rdx, rbx; unsigned __int16 *
0x180002b8e  lea     rcx, [rbp+1400h+OutputString]; this
0x180002b95  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002b9a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180002ba1  call    cs:__imp_OutputDebugStringW
0x180002ba7  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180002bac  jnz     short loc_180002BB7
0x180002bae  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002bb5  jz      short loc_180002BC9
0x180002bb7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002bbe  test    rax, rax
0x180002bc1  jz      short loc_180002BC9
0x180002bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bc8  nop
0x180002bc9  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180002bce  jnz     short loc_180002BF1
0x180002bd0  mov     rcx, [rbp+1400h+var_40]
0x180002bd7  xor     rcx, rsp; StackCookie
0x180002bda  call    __security_check_cookie
0x180002bdf  add     rsp, 14D0h
0x180002be6  pop     r15
0x180002be8  pop     r14
0x180002bea  pop     r12
0x180002bec  pop     rdi
0x180002bed  pop     rsi
0x180002bee  pop     rbx
0x180002bef  pop     rbp
0x180002bf0  retn
0x180002bf1  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002bf6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002bfc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
