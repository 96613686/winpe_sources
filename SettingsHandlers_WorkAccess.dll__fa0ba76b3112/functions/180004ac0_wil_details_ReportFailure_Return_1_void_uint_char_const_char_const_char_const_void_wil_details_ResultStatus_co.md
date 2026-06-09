# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004ac0`
- end: `0x180004d79`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004750`

## callees

- `0x180002a60`
- `0x180003534`
- `0x180004ac0`
- `0x180006bb4`
- `0x180008a84`
- `0x18000aa10`
- `0x18000acb4`
- `0x18004e8b0`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b86`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004c81`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004c81`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004d11`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004d11`

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
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180004ac0  push    rbp
0x180004ac2  push    rbx
0x180004ac3  push    rsi
0x180004ac4  push    rdi
0x180004ac5  push    r12
0x180004ac7  push    r14
0x180004ac9  push    r15
0x180004acb  lea     rbp, [rsp-13D0h]
0x180004ad3  mov     eax, 14D0h
0x180004ad8  call    _alloca_probe
0x180004add  sub     rsp, rax
0x180004ae0  mov     rax, cs:__security_cookie
0x180004ae7  xor     rax, rsp
0x180004aea  mov     [rbp+1400h+var_40], rax
0x180004af1  mov     rsi, r8
0x180004af4  mov     edi, edx
0x180004af6  mov     rbx, rcx
0x180004af9  mov     r14, [rbp+1400h+arg_28]
0x180004b00  xor     edx, edx; Val
0x180004b02  mov     r8d, 98h; Size
0x180004b08  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004b0d  call    memset_0
0x180004b12  nop
0x180004b13  xor     r12d, r12d
0x180004b16  mov     [rbp+1400h+OutputString], r12w
0x180004b1e  mov     [rbp+1400h+var_1440], r12b
0x180004b22  mov     rdx, [rbp+1400h+arg_30]; int
0x180004b29  mov     ecx, [rdx]; this
0x180004b2b  mov     [rsp+1500h+var_14D8], ecx
0x180004b2f  mov     eax, [rdx+4]
0x180004b32  mov     [rsp+1500h+var_14D4], eax
0x180004b36  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004b3b  mov     r15d, eax
0x180004b3e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004b46  mov     ecx, r12d
0x180004b49  lea     eax, [r12+8]
0x180004b4e  cmp     dword ptr [rdx+8], 1
0x180004b52  cmovz   ecx, eax
0x180004b55  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004b59  lea     ecx, [rax-7]
0x180004b5c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004b64  inc     ecx
0x180004b66  mov     [rsp+1500h+var_14D0], ecx
0x180004b6a  mov     rcx, [rbp+1400h+arg_38]
0x180004b71  test    rcx, rcx
0x180004b74  jz      short loc_180004B81
0x180004b76  cmp     [rcx], r12w
0x180004b7a  mov     [rsp+1500h+var_14C8], rcx
0x180004b7f  jnz     short loc_180004B86
0x180004b81  mov     [rsp+1500h+var_14C8], r12
0x180004b86  call    cs:__imp_GetCurrentThreadId
0x180004b8d  nop     dword ptr [rax+rax+00h]
0x180004b92  mov     [rsp+1500h+var_14C0], eax
0x180004b96  mov     [rsp+1500h+var_14A8], rsi
0x180004b9b  mov     [rsp+1500h+var_14A0], edi
0x180004b9f  mov     [rsp+1500h+var_149C], r15d
0x180004ba4  mov     [rsp+1500h+var_14B8], r12
0x180004ba9  mov     [rsp+1500h+var_14B0], r12
0x180004bae  mov     [rbp+1400h+var_1458], r14
0x180004bb2  mov     [rbp+1400h+var_1450], rbx
0x180004bb6  mov     [rsp+1500h+var_1498], r12
0x180004bbb  xorps   xmm0, xmm0
0x180004bbe  xor     eax, eax
0x180004bc0  movups  [rbp+1400h+var_1478], xmm0
0x180004bc4  mov     [rbp+1400h+var_1468], rax
0x180004bc8  xorps   xmm1, xmm1
0x180004bcb  movups  [rsp+1500h+var_1490], xmm1
0x180004bd0  mov     [rbp+1400h+var_1480], rax
0x180004bd4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004bdb  test    rax, rax
0x180004bde  jz      short loc_180004BEB
0x180004be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004be5  mov     [rbp+1400h+var_1460], rax
0x180004be9  jmp     short loc_180004BEF
0x180004beb  mov     [rbp+1400h+var_1460], r12
0x180004bef  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004bf6  test    rax, rax
0x180004bf9  jz      short loc_180004C05
0x180004bfb  lea     rcx, [rsp+1500h+var_14E0]
0x180004c00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c05  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004c0c  test    rax, rax
0x180004c0f  jz      short loc_180004C25
0x180004c11  mov     r8d, 400h
0x180004c17  lea     rdx, [rbp+1400h+var_1440]
0x180004c1b  lea     rcx, [rsp+1500h+var_14E0]
0x180004c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c25  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004c2c  test    rax, rax
0x180004c2f  jz      short loc_180004C3B
0x180004c31  lea     rcx, [rsp+1500h+var_14E0]
0x180004c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c3b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004c42  test    rax, rax
0x180004c45  jz      short loc_180004C58
0x180004c47  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004c4c  jnz     short loc_180004C58
0x180004c4e  lea     rcx, [rsp+1500h+var_14E0]
0x180004c53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c58  cmp     [rsp+1500h+var_14D8], r12d
0x180004c5d  jge     loc_180004D73
0x180004c63  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004c6a  jnz     short loc_180004C91
0x180004c6c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004c73  test    rax, rax
0x180004c76  jz      short loc_180004C81
0x180004c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c7d  test    al, al
0x180004c7f  jmp     short loc_180004C8F
0x180004c81  call    cs:__imp_IsDebuggerPresent
0x180004c88  nop     dword ptr [rax+rax+00h]
0x180004c8d  test    eax, eax
0x180004c8f  jz      short loc_180004C98
0x180004c91  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004c96  jz      short loc_180004CBE
0x180004c98  mov     rax, cs:g_pfnResultLoggingCallback
0x180004c9f  test    rax, rax
0x180004ca2  jz      short loc_180004D1D
0x180004ca4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004cab  jnz     short loc_180004D1D
0x180004cad  xor     r8d, r8d
0x180004cb0  xor     edx, edx
0x180004cb2  lea     rcx, [rsp+1500h+var_14E0]
0x180004cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cbc  jmp     short loc_180004D1D
0x180004cbe  mov     ebx, 800h
0x180004cc3  mov     rax, cs:g_pfnResultLoggingCallback
0x180004cca  test    rax, rax
0x180004ccd  jz      short loc_180004CEC
0x180004ccf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004cd6  jnz     short loc_180004CEC
0x180004cd8  mov     r8d, ebx
0x180004cdb  lea     rdx, [rbp+1400h+OutputString]
0x180004ce2  lea     rcx, [rsp+1500h+var_14E0]
0x180004ce7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cec  cmp     [rbp+1400h+OutputString], r12w
0x180004cf4  jnz     short loc_180004D0A
0x180004cf6  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004cfb  mov     rdx, rbx; unsigned __int16 *
0x180004cfe  lea     rcx, [rbp+1400h+OutputString]; this
0x180004d05  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004d0a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004d11  call    cs:__imp_OutputDebugStringW
0x180004d18  nop     dword ptr [rax+rax+00h]
0x180004d1d  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004d22  jnz     short loc_180004D2D
0x180004d24  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004d2b  jz      short loc_180004D3F
0x180004d2d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004d34  test    rax, rax
0x180004d37  jz      short loc_180004D3F
0x180004d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d3e  nop
0x180004d3f  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004d44  jnz     short loc_180004D68
0x180004d46  mov     rcx, [rbp+1400h+var_40]
0x180004d4d  xor     rcx, rsp; StackCookie
0x180004d50  call    __security_check_cookie
0x180004d55  add     rsp, 14D0h
0x180004d5c  pop     r15
0x180004d5e  pop     r14
0x180004d60  pop     r12
0x180004d62  pop     rdi
0x180004d63  pop     rsi
0x180004d64  pop     rbx
0x180004d65  pop     rbp
0x180004d66  retn
0x180004d68  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004d6d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004d73  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
