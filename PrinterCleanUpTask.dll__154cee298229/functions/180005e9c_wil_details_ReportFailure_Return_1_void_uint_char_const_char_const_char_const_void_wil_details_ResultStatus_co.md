# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005e9c`
- end: `0x180006142`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800059b0`

## callees

- `0x180002020`
- `0x180002b78`
- `0x180004214`
- `0x180005e9c`
- `0x1800065a8`
- `0x1800065e4`
- `0x1800066fc`
- `0x180015f10`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f62`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f62`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800060e1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800060e1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006057`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006057`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
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
0x180005e9c  push    rbp
0x180005e9e  push    rbx
0x180005e9f  push    rsi
0x180005ea0  push    rdi
0x180005ea1  push    r12
0x180005ea3  push    r14
0x180005ea5  push    r15
0x180005ea7  lea     rbp, [rsp-13D0h]
0x180005eaf  mov     eax, 14D0h
0x180005eb4  call    _alloca_probe
0x180005eb9  sub     rsp, rax
0x180005ebc  mov     rax, cs:__security_cookie
0x180005ec3  xor     rax, rsp
0x180005ec6  mov     [rbp+1400h+var_40], rax
0x180005ecd  mov     rsi, r8
0x180005ed0  mov     edi, edx
0x180005ed2  mov     rbx, rcx
0x180005ed5  mov     r14, [rbp+1400h+arg_28]
0x180005edc  xor     edx, edx; Val
0x180005ede  mov     r8d, 98h; Size
0x180005ee4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180005ee9  call    memset_0
0x180005eee  nop
0x180005eef  xor     r12d, r12d
0x180005ef2  mov     [rbp+1400h+OutputString], r12w
0x180005efa  mov     [rbp+1400h+var_1440], r12b
0x180005efe  mov     rdx, [rbp+1400h+arg_30]; int
0x180005f05  mov     ecx, [rdx]; this
0x180005f07  mov     [rsp+1500h+var_14D8], ecx
0x180005f0b  mov     eax, [rdx+4]
0x180005f0e  mov     [rsp+1500h+var_14D4], eax
0x180005f12  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005f17  mov     r15d, eax
0x180005f1a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005f22  mov     ecx, r12d
0x180005f25  lea     eax, [r12+8]
0x180005f2a  cmp     dword ptr [rdx+8], 1
0x180005f2e  cmovz   ecx, eax
0x180005f31  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005f35  lea     ecx, [rax-7]
0x180005f38  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005f40  inc     ecx
0x180005f42  mov     [rsp+1500h+var_14D0], ecx
0x180005f46  mov     rcx, [rbp+1400h+arg_38]
0x180005f4d  test    rcx, rcx
0x180005f50  jz      short loc_180005F5D
0x180005f52  cmp     [rcx], r12w
0x180005f56  mov     [rsp+1500h+var_14C8], rcx
0x180005f5b  jnz     short loc_180005F62
0x180005f5d  mov     [rsp+1500h+var_14C8], r12
0x180005f62  call    cs:__imp_GetCurrentThreadId
0x180005f68  mov     [rsp+1500h+var_14C0], eax
0x180005f6c  mov     [rsp+1500h+var_14A8], rsi
0x180005f71  mov     [rsp+1500h+var_14A0], edi
0x180005f75  mov     [rsp+1500h+var_149C], r15d
0x180005f7a  mov     [rsp+1500h+var_14B8], r12
0x180005f7f  mov     [rsp+1500h+var_14B0], r12
0x180005f84  mov     [rbp+1400h+var_1458], r14
0x180005f88  mov     [rbp+1400h+var_1450], rbx
0x180005f8c  mov     [rsp+1500h+var_1498], r12
0x180005f91  xorps   xmm0, xmm0
0x180005f94  xor     eax, eax
0x180005f96  movups  [rbp+1400h+var_1478], xmm0
0x180005f9a  mov     [rbp+1400h+var_1468], rax
0x180005f9e  xorps   xmm1, xmm1
0x180005fa1  movups  [rsp+1500h+var_1490], xmm1
0x180005fa6  mov     [rbp+1400h+var_1480], rax
0x180005faa  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005fb1  test    rax, rax
0x180005fb4  jz      short loc_180005FC1
0x180005fb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fbb  mov     [rbp+1400h+var_1460], rax
0x180005fbf  jmp     short loc_180005FC5
0x180005fc1  mov     [rbp+1400h+var_1460], r12
0x180005fc5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005fcc  test    rax, rax
0x180005fcf  jz      short loc_180005FDB
0x180005fd1  lea     rcx, [rsp+1500h+var_14E0]
0x180005fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fdb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005fe2  test    rax, rax
0x180005fe5  jz      short loc_180005FFB
0x180005fe7  mov     r8d, 400h
0x180005fed  lea     rdx, [rbp+1400h+var_1440]
0x180005ff1  lea     rcx, [rsp+1500h+var_14E0]
0x180005ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ffb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006002  test    rax, rax
0x180006005  jz      short loc_180006011
0x180006007  lea     rcx, [rsp+1500h+var_14E0]
0x18000600c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006011  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006018  test    rax, rax
0x18000601b  jz      short loc_18000602E
0x18000601d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006022  jnz     short loc_18000602E
0x180006024  lea     rcx, [rsp+1500h+var_14E0]
0x180006029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000602e  cmp     [rsp+1500h+var_14D8], r12d
0x180006033  jge     loc_18000613C
0x180006039  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180006040  jnz     short loc_180006061
0x180006042  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006049  test    rax, rax
0x18000604c  jz      short loc_180006057
0x18000604e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006053  test    al, al
0x180006055  jmp     short loc_18000605F
0x180006057  call    cs:__imp_IsDebuggerPresent
0x18000605d  test    eax, eax
0x18000605f  jz      short loc_180006068
0x180006061  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006066  jz      short loc_18000608E
0x180006068  mov     rax, cs:g_pfnResultLoggingCallback
0x18000606f  test    rax, rax
0x180006072  jz      short loc_1800060E7
0x180006074  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000607b  jnz     short loc_1800060E7
0x18000607d  xor     r8d, r8d
0x180006080  xor     edx, edx
0x180006082  lea     rcx, [rsp+1500h+var_14E0]
0x180006087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000608c  jmp     short loc_1800060E7
0x18000608e  mov     ebx, 800h
0x180006093  mov     rax, cs:g_pfnResultLoggingCallback
0x18000609a  test    rax, rax
0x18000609d  jz      short loc_1800060BC
0x18000609f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800060a6  jnz     short loc_1800060BC
0x1800060a8  mov     r8d, ebx
0x1800060ab  lea     rdx, [rbp+1400h+OutputString]
0x1800060b2  lea     rcx, [rsp+1500h+var_14E0]
0x1800060b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060bc  cmp     [rbp+1400h+OutputString], r12w
0x1800060c4  jnz     short loc_1800060DA
0x1800060c6  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800060cb  mov     rdx, rbx; unsigned __int16 *
0x1800060ce  lea     rcx, [rbp+1400h+OutputString]; this
0x1800060d5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800060da  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800060e1  call    cs:__imp_OutputDebugStringW
0x1800060e7  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800060ec  jnz     short loc_1800060F7
0x1800060ee  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800060f5  jz      short loc_180006109
0x1800060f7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800060fe  test    rax, rax
0x180006101  jz      short loc_180006109
0x180006103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006108  nop
0x180006109  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000610e  jnz     short loc_180006131
0x180006110  mov     rcx, [rbp+1400h+var_40]
0x180006117  xor     rcx, rsp; StackCookie
0x18000611a  call    __security_check_cookie
0x18000611f  add     rsp, 14D0h
0x180006126  pop     r15
0x180006128  pop     r14
0x18000612a  pop     r12
0x18000612c  pop     rdi
0x18000612d  pop     rsi
0x18000612e  pop     rbx
0x18000612f  pop     rbp
0x180006130  retn
0x180006131  lea     rcx, [rsp+1500h+var_14E0]; this
0x180006136  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000613c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
