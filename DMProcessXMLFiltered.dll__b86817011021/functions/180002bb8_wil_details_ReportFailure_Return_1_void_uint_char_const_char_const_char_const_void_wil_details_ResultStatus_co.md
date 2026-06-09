# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002bb8`
- end: `0x180002e5e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800024f8`

## callees

- `0x180001520`
- `0x180001e5a`
- `0x180002bb8`
- `0x180003f94`
- `0x180004ed0`
- `0x180005f50`
- `0x18000602c`
- `0x180006b70`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c7e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002c7e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002d73`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002d73`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002dfd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002dfd`

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
0x180002bb8  push    rbp
0x180002bba  push    rbx
0x180002bbb  push    rsi
0x180002bbc  push    rdi
0x180002bbd  push    r12
0x180002bbf  push    r14
0x180002bc1  push    r15
0x180002bc3  lea     rbp, [rsp-13D0h]
0x180002bcb  mov     eax, 14D0h
0x180002bd0  call    _alloca_probe
0x180002bd5  sub     rsp, rax
0x180002bd8  mov     rax, cs:__security_cookie
0x180002bdf  xor     rax, rsp
0x180002be2  mov     [rbp+1400h+var_40], rax
0x180002be9  mov     rsi, r8
0x180002bec  mov     edi, edx
0x180002bee  mov     rbx, rcx
0x180002bf1  mov     r14, [rbp+1400h+arg_28]
0x180002bf8  xor     edx, edx; Val
0x180002bfa  mov     r8d, 98h; Size
0x180002c00  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002c05  call    memset_0
0x180002c0a  nop
0x180002c0b  xor     r12d, r12d
0x180002c0e  mov     [rbp+1400h+OutputString], r12w
0x180002c16  mov     [rbp+1400h+var_1440], r12b
0x180002c1a  mov     rdx, [rbp+1400h+arg_30]; int
0x180002c21  mov     ecx, [rdx]; this
0x180002c23  mov     [rsp+1500h+var_14D8], ecx
0x180002c27  mov     eax, [rdx+4]
0x180002c2a  mov     [rsp+1500h+var_14D4], eax
0x180002c2e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002c33  mov     r15d, eax
0x180002c36  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180002c3e  mov     ecx, r12d
0x180002c41  lea     eax, [r12+8]
0x180002c46  cmp     dword ptr [rdx+8], 1
0x180002c4a  cmovz   ecx, eax
0x180002c4d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180002c51  lea     ecx, [rax-7]
0x180002c54  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002c5c  inc     ecx
0x180002c5e  mov     [rsp+1500h+var_14D0], ecx
0x180002c62  mov     rcx, [rbp+1400h+arg_38]
0x180002c69  test    rcx, rcx
0x180002c6c  jz      short loc_180002C79
0x180002c6e  cmp     [rcx], r12w
0x180002c72  mov     [rsp+1500h+var_14C8], rcx
0x180002c77  jnz     short loc_180002C7E
0x180002c79  mov     [rsp+1500h+var_14C8], r12
0x180002c7e  call    cs:__imp_GetCurrentThreadId
0x180002c84  mov     [rsp+1500h+var_14C0], eax
0x180002c88  mov     [rsp+1500h+var_14A8], rsi
0x180002c8d  mov     [rsp+1500h+var_14A0], edi
0x180002c91  mov     [rsp+1500h+var_149C], r15d
0x180002c96  mov     [rsp+1500h+var_14B8], r12
0x180002c9b  mov     [rsp+1500h+var_14B0], r12
0x180002ca0  mov     [rbp+1400h+var_1458], r14
0x180002ca4  mov     [rbp+1400h+var_1450], rbx
0x180002ca8  mov     [rsp+1500h+var_1498], r12
0x180002cad  xorps   xmm0, xmm0
0x180002cb0  xor     eax, eax
0x180002cb2  movups  [rbp+1400h+var_1478], xmm0
0x180002cb6  mov     [rbp+1400h+var_1468], rax
0x180002cba  xorps   xmm1, xmm1
0x180002cbd  movups  [rsp+1500h+var_1490], xmm1
0x180002cc2  mov     [rbp+1400h+var_1480], rax
0x180002cc6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002ccd  test    rax, rax
0x180002cd0  jz      short loc_180002CDD
0x180002cd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cd7  mov     [rbp+1400h+var_1460], rax
0x180002cdb  jmp     short loc_180002CE1
0x180002cdd  mov     [rbp+1400h+var_1460], r12
0x180002ce1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002ce8  test    rax, rax
0x180002ceb  jz      short loc_180002CF7
0x180002ced  lea     rcx, [rsp+1500h+var_14E0]
0x180002cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cf7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002cfe  test    rax, rax
0x180002d01  jz      short loc_180002D17
0x180002d03  mov     r8d, 400h
0x180002d09  lea     rdx, [rbp+1400h+var_1440]
0x180002d0d  lea     rcx, [rsp+1500h+var_14E0]
0x180002d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d17  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002d1e  test    rax, rax
0x180002d21  jz      short loc_180002D2D
0x180002d23  lea     rcx, [rsp+1500h+var_14E0]
0x180002d28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d2d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002d34  test    rax, rax
0x180002d37  jz      short loc_180002D4A
0x180002d39  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002d3e  jnz     short loc_180002D4A
0x180002d40  lea     rcx, [rsp+1500h+var_14E0]
0x180002d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d4a  cmp     [rsp+1500h+var_14D8], r12d
0x180002d4f  jge     loc_180002E58
0x180002d55  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002d5c  jnz     short loc_180002D7D
0x180002d5e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002d65  test    rax, rax
0x180002d68  jz      short loc_180002D73
0x180002d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d6f  test    al, al
0x180002d71  jmp     short loc_180002D7B
0x180002d73  call    cs:__imp_IsDebuggerPresent
0x180002d79  test    eax, eax
0x180002d7b  jz      short loc_180002D84
0x180002d7d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002d82  jz      short loc_180002DAA
0x180002d84  mov     rax, cs:g_pfnResultLoggingCallback
0x180002d8b  test    rax, rax
0x180002d8e  jz      short loc_180002E03
0x180002d90  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002d97  jnz     short loc_180002E03
0x180002d99  xor     r8d, r8d
0x180002d9c  xor     edx, edx
0x180002d9e  lea     rcx, [rsp+1500h+var_14E0]
0x180002da3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002da8  jmp     short loc_180002E03
0x180002daa  mov     ebx, 800h
0x180002daf  mov     rax, cs:g_pfnResultLoggingCallback
0x180002db6  test    rax, rax
0x180002db9  jz      short loc_180002DD8
0x180002dbb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002dc2  jnz     short loc_180002DD8
0x180002dc4  mov     r8d, ebx
0x180002dc7  lea     rdx, [rbp+1400h+OutputString]
0x180002dce  lea     rcx, [rsp+1500h+var_14E0]
0x180002dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002dd8  cmp     [rbp+1400h+OutputString], r12w
0x180002de0  jnz     short loc_180002DF6
0x180002de2  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180002de7  mov     rdx, rbx; unsigned __int16 *
0x180002dea  lea     rcx, [rbp+1400h+OutputString]; this
0x180002df1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002df6  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180002dfd  call    cs:__imp_OutputDebugStringW
0x180002e03  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180002e08  jnz     short loc_180002E13
0x180002e0a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002e11  jz      short loc_180002E25
0x180002e13  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002e1a  test    rax, rax
0x180002e1d  jz      short loc_180002E25
0x180002e1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e24  nop
0x180002e25  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180002e2a  jnz     short loc_180002E4D
0x180002e2c  mov     rcx, [rbp+1400h+var_40]
0x180002e33  xor     rcx, rsp; StackCookie
0x180002e36  call    __security_check_cookie
0x180002e3b  add     rsp, 14D0h
0x180002e42  pop     r15
0x180002e44  pop     r14
0x180002e46  pop     r12
0x180002e48  pop     rdi
0x180002e49  pop     rsi
0x180002e4a  pop     rbx
0x180002e4b  pop     rbp
0x180002e4c  retn
0x180002e4d  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002e52  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002e58  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
