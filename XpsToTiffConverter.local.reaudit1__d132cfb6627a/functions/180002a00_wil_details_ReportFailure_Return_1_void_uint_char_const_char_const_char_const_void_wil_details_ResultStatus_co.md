# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002a00`
- end: `0x180002ca6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002348`

## callees

- `0x1800016a0`
- `0x1800020e4`
- `0x180002a00`
- `0x180004c84`
- `0x180006198`
- `0x180008540`
- `0x18000870c`
- `0x18000caf0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002ac6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002ac6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002c45`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002c45`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002bbb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002bbb`

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
0x180002a00  push    rbp
0x180002a02  push    rbx
0x180002a03  push    rsi
0x180002a04  push    rdi
0x180002a05  push    r12
0x180002a07  push    r14
0x180002a09  push    r15
0x180002a0b  lea     rbp, [rsp-13D0h]
0x180002a13  mov     eax, 14D0h
0x180002a18  call    _alloca_probe
0x180002a1d  sub     rsp, rax
0x180002a20  mov     rax, cs:__security_cookie
0x180002a27  xor     rax, rsp
0x180002a2a  mov     [rbp+1400h+var_40], rax
0x180002a31  mov     rsi, r8
0x180002a34  mov     edi, edx
0x180002a36  mov     rbx, rcx
0x180002a39  mov     r14, [rbp+1400h+arg_28]
0x180002a40  xor     edx, edx; Val
0x180002a42  mov     r8d, 98h; Size
0x180002a48  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002a4d  call    memset_0
0x180002a52  nop
0x180002a53  xor     r12d, r12d
0x180002a56  mov     [rbp+1400h+OutputString], r12w
0x180002a5e  mov     [rbp+1400h+var_1440], r12b
0x180002a62  mov     rdx, [rbp+1400h+arg_30]; int
0x180002a69  mov     ecx, [rdx]; this
0x180002a6b  mov     [rsp+1500h+var_14D8], ecx
0x180002a6f  mov     eax, [rdx+4]
0x180002a72  mov     [rsp+1500h+var_14D4], eax
0x180002a76  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002a7b  mov     r15d, eax
0x180002a7e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180002a86  mov     ecx, r12d
0x180002a89  lea     eax, [r12+8]
0x180002a8e  cmp     dword ptr [rdx+8], 1
0x180002a92  cmovz   ecx, eax
0x180002a95  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180002a99  lea     ecx, [rax-7]
0x180002a9c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002aa4  inc     ecx
0x180002aa6  mov     [rsp+1500h+var_14D0], ecx
0x180002aaa  mov     rcx, [rbp+1400h+arg_38]
0x180002ab1  test    rcx, rcx
0x180002ab4  jz      short loc_180002AC1
0x180002ab6  cmp     [rcx], r12w
0x180002aba  mov     [rsp+1500h+var_14C8], rcx
0x180002abf  jnz     short loc_180002AC6
0x180002ac1  mov     [rsp+1500h+var_14C8], r12
0x180002ac6  call    cs:__imp_GetCurrentThreadId
0x180002acc  mov     [rsp+1500h+var_14C0], eax
0x180002ad0  mov     [rsp+1500h+var_14A8], rsi
0x180002ad5  mov     [rsp+1500h+var_14A0], edi
0x180002ad9  mov     [rsp+1500h+var_149C], r15d
0x180002ade  mov     [rsp+1500h+var_14B8], r12
0x180002ae3  mov     [rsp+1500h+var_14B0], r12
0x180002ae8  mov     [rbp+1400h+var_1458], r14
0x180002aec  mov     [rbp+1400h+var_1450], rbx
0x180002af0  mov     [rsp+1500h+var_1498], r12
0x180002af5  xorps   xmm0, xmm0
0x180002af8  xor     eax, eax
0x180002afa  movups  [rbp+1400h+var_1478], xmm0
0x180002afe  mov     [rbp+1400h+var_1468], rax
0x180002b02  xorps   xmm1, xmm1
0x180002b05  movups  [rsp+1500h+var_1490], xmm1
0x180002b0a  mov     [rbp+1400h+var_1480], rax
0x180002b0e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002b15  test    rax, rax
0x180002b18  jz      short loc_180002B25
0x180002b1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b1f  mov     [rbp+1400h+var_1460], rax
0x180002b23  jmp     short loc_180002B29
0x180002b25  mov     [rbp+1400h+var_1460], r12
0x180002b29  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002b30  test    rax, rax
0x180002b33  jz      short loc_180002B3F
0x180002b35  lea     rcx, [rsp+1500h+var_14E0]
0x180002b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b3f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002b46  test    rax, rax
0x180002b49  jz      short loc_180002B5F
0x180002b4b  mov     r8d, 400h
0x180002b51  lea     rdx, [rbp+1400h+var_1440]
0x180002b55  lea     rcx, [rsp+1500h+var_14E0]
0x180002b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b5f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002b66  test    rax, rax
0x180002b69  jz      short loc_180002B75
0x180002b6b  lea     rcx, [rsp+1500h+var_14E0]
0x180002b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b75  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002b7c  test    rax, rax
0x180002b7f  jz      short loc_180002B92
0x180002b81  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002b86  jnz     short loc_180002B92
0x180002b88  lea     rcx, [rsp+1500h+var_14E0]
0x180002b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b92  cmp     [rsp+1500h+var_14D8], r12d
0x180002b97  jge     loc_180002CA0
0x180002b9d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002ba4  jnz     short loc_180002BC5
0x180002ba6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002bad  test    rax, rax
0x180002bb0  jz      short loc_180002BBB
0x180002bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bb7  test    al, al
0x180002bb9  jmp     short loc_180002BC3
0x180002bbb  call    cs:__imp_IsDebuggerPresent
0x180002bc1  test    eax, eax
0x180002bc3  jz      short loc_180002BCC
0x180002bc5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002bca  jz      short loc_180002BF2
0x180002bcc  mov     rax, cs:g_pfnResultLoggingCallback
0x180002bd3  test    rax, rax
0x180002bd6  jz      short loc_180002C4B
0x180002bd8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002bdf  jnz     short loc_180002C4B
0x180002be1  xor     r8d, r8d
0x180002be4  xor     edx, edx
0x180002be6  lea     rcx, [rsp+1500h+var_14E0]
0x180002beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf0  jmp     short loc_180002C4B
0x180002bf2  mov     ebx, 800h
0x180002bf7  mov     rax, cs:g_pfnResultLoggingCallback
0x180002bfe  test    rax, rax
0x180002c01  jz      short loc_180002C20
0x180002c03  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002c0a  jnz     short loc_180002C20
0x180002c0c  mov     r8d, ebx
0x180002c0f  lea     rdx, [rbp+1400h+OutputString]
0x180002c16  lea     rcx, [rsp+1500h+var_14E0]
0x180002c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c20  cmp     [rbp+1400h+OutputString], r12w
0x180002c28  jnz     short loc_180002C3E
0x180002c2a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180002c2f  mov     rdx, rbx; unsigned __int16 *
0x180002c32  lea     rcx, [rbp+1400h+OutputString]; this
0x180002c39  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002c3e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180002c45  call    cs:__imp_OutputDebugStringW
0x180002c4b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180002c50  jnz     short loc_180002C5B
0x180002c52  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002c59  jz      short loc_180002C6D
0x180002c5b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002c62  test    rax, rax
0x180002c65  jz      short loc_180002C6D
0x180002c67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c6c  nop
0x180002c6d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180002c72  jnz     short loc_180002C95
0x180002c74  mov     rcx, [rbp+1400h+var_40]
0x180002c7b  xor     rcx, rsp; StackCookie
0x180002c7e  call    __security_check_cookie
0x180002c83  add     rsp, 14D0h
0x180002c8a  pop     r15
0x180002c8c  pop     r14
0x180002c8e  pop     r12
0x180002c90  pop     rdi
0x180002c91  pop     rsi
0x180002c92  pop     rbx
0x180002c93  pop     rbp
0x180002c94  retn
0x180002c95  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002c9a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002ca0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
