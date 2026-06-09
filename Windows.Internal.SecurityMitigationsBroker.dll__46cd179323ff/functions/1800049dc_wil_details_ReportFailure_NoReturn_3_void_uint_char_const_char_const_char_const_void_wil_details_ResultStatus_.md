# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800049dc`
- end: `0x180004c52`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `630`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004940`

## callees

- `0x180001fa3`
- `0x1800049dc`
- `0x180004d64`
- `0x18000514c`
- `0x180005e60`
- `0x180005ee0`
- `0x180006956`
- `0x180006a10`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c20`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c20`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004b96`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004b96`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // eax
  int v12; // edx
  int v13; // eax
  int v14; // r12d
  int v15; // ecx
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  _WORD *v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId_0; // [rsp+40h] [rbp-C0h]
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

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v11 = a7[1];
  v22 = *a7;
  v23 = v11;
  v13 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v12);
  v19 = a7[2] == 1;
  v14 = v13;
  v20 = 3;
  v15 = 0;
  if ( v19 )
    v15 = 8;
  v21 = v15;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v25 = a8, !*a8) )
    v25 = 0;
  CurrentThreadId_0 = GetCurrentThreadId_0();
  v29 = a3;
  v36 = 0;
  v34 = 0;
  v30 = a2;
  v31 = v14;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x1800049dc  mov     [rsp-8+arg_18], rbx
0x1800049e1  push    rbp
0x1800049e2  push    rsi
0x1800049e3  push    rdi
0x1800049e4  push    r12
0x1800049e6  push    r13
0x1800049e8  push    r14
0x1800049ea  push    r15
0x1800049ec  lea     rbp, [rsp-13C0h]
0x1800049f4  mov     eax, 14C0h
0x1800049f9  call    _alloca_probe
0x1800049fe  sub     rsp, rax
0x180004a01  mov     r15, [rbp+13F0h+arg_28]
0x180004a08  mov     r14, r8
0x180004a0b  mov     esi, edx
0x180004a0d  mov     rdi, rcx
0x180004a10  xor     edx, edx; Val
0x180004a12  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004a17  mov     r8d, 98h; Size
0x180004a1d  call    memset_0
0x180004a22  mov     rbx, [rbp+13F0h+arg_30]
0x180004a29  xor     r13d, r13d
0x180004a2c  mov     [rbp+13F0h+OutputString], r13w
0x180004a34  mov     [rbp+13F0h+var_1430], r13b
0x180004a38  mov     ecx, [rbx]; this
0x180004a3a  mov     eax, [rbx+4]
0x180004a3d  mov     [rsp+14F0h+var_14C8], ecx
0x180004a41  mov     [rsp+14F0h+var_14C4], eax
0x180004a45  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004a4a  cmp     dword ptr [rbx+8], 1
0x180004a4e  mov     r12d, eax
0x180004a51  lea     eax, [r13+8]
0x180004a55  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180004a5d  mov     ecx, r13d
0x180004a60  cmovz   ecx, eax
0x180004a63  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004a67  lea     ecx, [rax-7]
0x180004a6a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004a72  inc     ecx
0x180004a74  mov     [rsp+14F0h+var_14C0], ecx
0x180004a78  mov     rcx, [rbp+13F0h+arg_38]
0x180004a7f  test    rcx, rcx
0x180004a82  jz      short loc_180004A8F
0x180004a84  mov     [rsp+14F0h+var_14B8], rcx
0x180004a89  cmp     [rcx], r13w
0x180004a8d  jnz     short loc_180004A94
0x180004a8f  mov     [rsp+14F0h+var_14B8], r13
0x180004a94  call    GetCurrentThreadId_0
0x180004a99  mov     [rsp+14F0h+var_14B0], eax
0x180004a9d  xorps   xmm0, xmm0
0x180004aa0  xor     eax, eax
0x180004aa2  mov     [rsp+14F0h+var_1498], r14
0x180004aa7  mov     [rbp+13F0h+var_1458], rax
0x180004aab  xorps   xmm1, xmm1
0x180004aae  mov     [rbp+13F0h+var_1470], rax
0x180004ab2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004ab9  mov     [rsp+14F0h+var_1490], esi
0x180004abd  mov     [rsp+14F0h+var_148C], r12d
0x180004ac2  mov     [rsp+14F0h+var_14A8], r13
0x180004ac7  mov     [rsp+14F0h+var_14A0], r13
0x180004acc  mov     [rbp+13F0h+var_1448], r15
0x180004ad0  mov     [rbp+13F0h+var_1440], rdi
0x180004ad4  mov     [rsp+14F0h+var_1488], r13
0x180004ad9  movups  [rbp+13F0h+var_1468], xmm0
0x180004add  movups  [rsp+14F0h+var_1480], xmm1
0x180004ae2  test    rax, rax
0x180004ae5  jz      short loc_180004AF2
0x180004ae7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aec  mov     [rbp+13F0h+var_1450], rax
0x180004af0  jmp     short loc_180004AF6
0x180004af2  mov     [rbp+13F0h+var_1450], r13
0x180004af6  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004afd  test    rax, rax
0x180004b00  jz      short loc_180004B0C
0x180004b02  lea     rcx, [rsp+14F0h+var_14D0]
0x180004b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b0c  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004b13  test    rax, rax
0x180004b16  jz      short loc_180004B2C
0x180004b18  mov     r8d, 400h
0x180004b1e  lea     rdx, [rbp+13F0h+var_1430]
0x180004b22  lea     rcx, [rsp+14F0h+var_14D0]
0x180004b27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b2c  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004b33  test    rax, rax
0x180004b36  jz      short loc_180004B42
0x180004b38  lea     rcx, [rsp+14F0h+var_14D0]
0x180004b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b42  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004b49  test    rax, rax
0x180004b4c  jz      short loc_180004B5F
0x180004b4e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004b53  jnz     short loc_180004B5F
0x180004b55  lea     rcx, [rsp+14F0h+var_14D0]
0x180004b5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b5f  cmp     [rsp+14F0h+var_14C8], r13d
0x180004b64  jl      short loc_180004B78
0x180004b66  mov     ecx, 8000FFFFh; this
0x180004b6b  mov     [rsp+14F0h+var_14C8], ecx
0x180004b6f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004b74  mov     [rsp+14F0h+var_14C4], eax
0x180004b78  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180004b7f  jnz     short loc_180004BA0
0x180004b81  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004b88  test    rax, rax
0x180004b8b  jz      short loc_180004B96
0x180004b8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b92  test    al, al
0x180004b94  jmp     short loc_180004B9E
0x180004b96  call    cs:__imp_IsDebuggerPresent
0x180004b9c  test    eax, eax
0x180004b9e  jz      short loc_180004BA7
0x180004ba0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004ba5  jz      short loc_180004BCD
0x180004ba7  mov     rax, cs:g_pfnResultLoggingCallback
0x180004bae  test    rax, rax
0x180004bb1  jz      short loc_180004C26
0x180004bb3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004bba  jnz     short loc_180004C26
0x180004bbc  xor     r8d, r8d
0x180004bbf  lea     rcx, [rsp+14F0h+var_14D0]
0x180004bc4  xor     edx, edx
0x180004bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bcb  jmp     short loc_180004C26
0x180004bcd  mov     rax, cs:g_pfnResultLoggingCallback
0x180004bd4  mov     ebx, 800h
0x180004bd9  test    rax, rax
0x180004bdc  jz      short loc_180004BFB
0x180004bde  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004be5  jnz     short loc_180004BFB
0x180004be7  mov     r8d, ebx
0x180004bea  lea     rdx, [rbp+13F0h+OutputString]
0x180004bf1  lea     rcx, [rsp+14F0h+var_14D0]
0x180004bf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bfb  cmp     [rbp+13F0h+OutputString], r13w
0x180004c03  jnz     short loc_180004C19
0x180004c05  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180004c0a  mov     rdx, rbx; unsigned __int16 *
0x180004c0d  lea     rcx, [rbp+13F0h+OutputString]; this
0x180004c14  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004c19  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180004c20  call    cs:__imp_OutputDebugStringW
0x180004c26  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180004c2b  jnz     short loc_180004C36
0x180004c2d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180004c34  jz      short loc_180004C47
0x180004c36  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004c3d  test    rax, rax
0x180004c40  jz      short loc_180004C47
0x180004c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c47  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004c4c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
