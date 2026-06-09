# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002b1c`
- end: `0x140002dc2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400027a0`

## callees

- `0x14000252f`
- `0x140002b1c`
- `0x1400039a4`
- `0x140004a90`
- `0x140005648`
- `0x140005890`
- `0x1400094d0`
- `0x140009590`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002be2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002be2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002cd7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002cd7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002d61`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002d61`

## pseudocode

```c
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
0x140002b1c  push    rbp
0x140002b1e  push    rbx
0x140002b1f  push    rsi
0x140002b20  push    rdi
0x140002b21  push    r12
0x140002b23  push    r14
0x140002b25  push    r15
0x140002b27  lea     rbp, [rsp-13D0h]
0x140002b2f  mov     eax, 14D0h
0x140002b34  call    _alloca_probe
0x140002b39  sub     rsp, rax
0x140002b3c  mov     rax, cs:__security_cookie
0x140002b43  xor     rax, rsp
0x140002b46  mov     [rbp+1400h+var_40], rax
0x140002b4d  mov     rsi, r8
0x140002b50  mov     edi, edx
0x140002b52  mov     rbx, rcx
0x140002b55  mov     r14, [rbp+1400h+arg_28]
0x140002b5c  xor     edx, edx; Val
0x140002b5e  mov     r8d, 98h; Size
0x140002b64  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140002b69  call    memset_0
0x140002b6e  nop
0x140002b6f  xor     r12d, r12d
0x140002b72  mov     [rbp+1400h+OutputString], r12w
0x140002b7a  mov     [rbp+1400h+var_1440], r12b
0x140002b7e  mov     rdx, [rbp+1400h+arg_30]; int
0x140002b85  mov     ecx, [rdx]; this
0x140002b87  mov     [rsp+1500h+var_14D8], ecx
0x140002b8b  mov     eax, [rdx+4]
0x140002b8e  mov     [rsp+1500h+var_14D4], eax
0x140002b92  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002b97  mov     r15d, eax
0x140002b9a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140002ba2  mov     ecx, r12d
0x140002ba5  lea     eax, [r12+8]
0x140002baa  cmp     dword ptr [rdx+8], 1
0x140002bae  cmovz   ecx, eax
0x140002bb1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140002bb5  lea     ecx, [rax-7]
0x140002bb8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002bc0  inc     ecx
0x140002bc2  mov     [rsp+1500h+var_14D0], ecx
0x140002bc6  mov     rcx, [rbp+1400h+arg_38]
0x140002bcd  test    rcx, rcx
0x140002bd0  jz      short loc_140002BDD
0x140002bd2  cmp     [rcx], r12w
0x140002bd6  mov     [rsp+1500h+var_14C8], rcx
0x140002bdb  jnz     short loc_140002BE2
0x140002bdd  mov     [rsp+1500h+var_14C8], r12
0x140002be2  call    cs:__imp_GetCurrentThreadId
0x140002be8  mov     [rsp+1500h+var_14C0], eax
0x140002bec  mov     [rsp+1500h+var_14A8], rsi
0x140002bf1  mov     [rsp+1500h+var_14A0], edi
0x140002bf5  mov     [rsp+1500h+var_149C], r15d
0x140002bfa  mov     [rsp+1500h+var_14B8], r12
0x140002bff  mov     [rsp+1500h+var_14B0], r12
0x140002c04  mov     [rbp+1400h+var_1458], r14
0x140002c08  mov     [rbp+1400h+var_1450], rbx
0x140002c0c  mov     [rsp+1500h+var_1498], r12
0x140002c11  xorps   xmm0, xmm0
0x140002c14  xor     eax, eax
0x140002c16  movups  [rbp+1400h+var_1478], xmm0
0x140002c1a  mov     [rbp+1400h+var_1468], rax
0x140002c1e  xorps   xmm1, xmm1
0x140002c21  movups  [rsp+1500h+var_1490], xmm1
0x140002c26  mov     [rbp+1400h+var_1480], rax
0x140002c2a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002c31  test    rax, rax
0x140002c34  jz      short loc_140002C41
0x140002c36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c3b  mov     [rbp+1400h+var_1460], rax
0x140002c3f  jmp     short loc_140002C45
0x140002c41  mov     [rbp+1400h+var_1460], r12
0x140002c45  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002c4c  test    rax, rax
0x140002c4f  jz      short loc_140002C5B
0x140002c51  lea     rcx, [rsp+1500h+var_14E0]
0x140002c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c5b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002c62  test    rax, rax
0x140002c65  jz      short loc_140002C7B
0x140002c67  mov     r8d, 400h
0x140002c6d  lea     rdx, [rbp+1400h+var_1440]
0x140002c71  lea     rcx, [rsp+1500h+var_14E0]
0x140002c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c7b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002c82  test    rax, rax
0x140002c85  jz      short loc_140002C91
0x140002c87  lea     rcx, [rsp+1500h+var_14E0]
0x140002c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c91  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002c98  test    rax, rax
0x140002c9b  jz      short loc_140002CAE
0x140002c9d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002ca2  jnz     short loc_140002CAE
0x140002ca4  lea     rcx, [rsp+1500h+var_14E0]
0x140002ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cae  cmp     [rsp+1500h+var_14D8], r12d
0x140002cb3  jge     loc_140002DBC
0x140002cb9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140002cc0  jnz     short loc_140002CE1
0x140002cc2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002cc9  test    rax, rax
0x140002ccc  jz      short loc_140002CD7
0x140002cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cd3  test    al, al
0x140002cd5  jmp     short loc_140002CDF
0x140002cd7  call    cs:__imp_IsDebuggerPresent
0x140002cdd  test    eax, eax
0x140002cdf  jz      short loc_140002CE8
0x140002ce1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002ce6  jz      short loc_140002D0E
0x140002ce8  mov     rax, cs:g_pfnResultLoggingCallback
0x140002cef  test    rax, rax
0x140002cf2  jz      short loc_140002D67
0x140002cf4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002cfb  jnz     short loc_140002D67
0x140002cfd  xor     r8d, r8d
0x140002d00  xor     edx, edx
0x140002d02  lea     rcx, [rsp+1500h+var_14E0]
0x140002d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d0c  jmp     short loc_140002D67
0x140002d0e  mov     ebx, 800h
0x140002d13  mov     rax, cs:g_pfnResultLoggingCallback
0x140002d1a  test    rax, rax
0x140002d1d  jz      short loc_140002D3C
0x140002d1f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002d26  jnz     short loc_140002D3C
0x140002d28  mov     r8d, ebx
0x140002d2b  lea     rdx, [rbp+1400h+OutputString]
0x140002d32  lea     rcx, [rsp+1500h+var_14E0]
0x140002d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d3c  cmp     [rbp+1400h+OutputString], r12w
0x140002d44  jnz     short loc_140002D5A
0x140002d46  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140002d4b  mov     rdx, rbx; unsigned __int16 *
0x140002d4e  lea     rcx, [rbp+1400h+OutputString]; this
0x140002d55  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002d5a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140002d61  call    cs:__imp_OutputDebugStringW
0x140002d67  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140002d6c  jnz     short loc_140002D77
0x140002d6e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140002d75  jz      short loc_140002D89
0x140002d77  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002d7e  test    rax, rax
0x140002d81  jz      short loc_140002D89
0x140002d83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d88  nop
0x140002d89  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140002d8e  jnz     short loc_140002DB1
0x140002d90  mov     rcx, [rbp+1400h+var_40]
0x140002d97  xor     rcx, rsp; StackCookie
0x140002d9a  call    __security_check_cookie
0x140002d9f  add     rsp, 14D0h
0x140002da6  pop     r15
0x140002da8  pop     r14
0x140002daa  pop     r12
0x140002dac  pop     rdi
0x140002dad  pop     rsi
0x140002dae  pop     rbx
0x140002daf  pop     rbp
0x140002db0  retn
0x140002db1  lea     rcx, [rsp+1500h+var_14E0]; this
0x140002db6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002dbc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
