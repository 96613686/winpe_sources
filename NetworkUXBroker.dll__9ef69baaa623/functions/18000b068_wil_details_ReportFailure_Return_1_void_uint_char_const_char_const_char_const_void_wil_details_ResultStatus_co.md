# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000b068`
- end: `0x18000b30e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000acc8`

## callees

- `0x180002520`
- `0x1800030a0`
- `0x180005b94`
- `0x18000a35c`
- `0x18000b068`
- `0x18000e72c`
- `0x18000f034`
- `0x180044a10`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b12e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b12e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b2ad`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000b2ad`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b223`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000b223`

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
0x18000b068  push    rbp
0x18000b06a  push    rbx
0x18000b06b  push    rsi
0x18000b06c  push    rdi
0x18000b06d  push    r12
0x18000b06f  push    r14
0x18000b071  push    r15
0x18000b073  lea     rbp, [rsp-13D0h]
0x18000b07b  mov     eax, 14D0h
0x18000b080  call    _alloca_probe
0x18000b085  sub     rsp, rax
0x18000b088  mov     rax, cs:__security_cookie
0x18000b08f  xor     rax, rsp
0x18000b092  mov     [rbp+1400h+var_40], rax
0x18000b099  mov     rsi, r8
0x18000b09c  mov     edi, edx
0x18000b09e  mov     rbx, rcx
0x18000b0a1  mov     r14, [rbp+1400h+arg_28]
0x18000b0a8  xor     edx, edx; Val
0x18000b0aa  mov     r8d, 98h; Size
0x18000b0b0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000b0b5  call    memset_0
0x18000b0ba  nop
0x18000b0bb  xor     r12d, r12d
0x18000b0be  mov     [rbp+1400h+OutputString], r12w
0x18000b0c6  mov     [rbp+1400h+var_1440], r12b
0x18000b0ca  mov     rdx, [rbp+1400h+arg_30]; int
0x18000b0d1  mov     ecx, [rdx]; this
0x18000b0d3  mov     [rsp+1500h+var_14D8], ecx
0x18000b0d7  mov     eax, [rdx+4]
0x18000b0da  mov     [rsp+1500h+var_14D4], eax
0x18000b0de  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000b0e3  mov     r15d, eax
0x18000b0e6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000b0ee  mov     ecx, r12d
0x18000b0f1  lea     eax, [r12+8]
0x18000b0f6  cmp     dword ptr [rdx+8], 1
0x18000b0fa  cmovz   ecx, eax
0x18000b0fd  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000b101  lea     ecx, [rax-7]
0x18000b104  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000b10c  inc     ecx
0x18000b10e  mov     [rsp+1500h+var_14D0], ecx
0x18000b112  mov     rcx, [rbp+1400h+arg_38]
0x18000b119  test    rcx, rcx
0x18000b11c  jz      short loc_18000B129
0x18000b11e  cmp     [rcx], r12w
0x18000b122  mov     [rsp+1500h+var_14C8], rcx
0x18000b127  jnz     short loc_18000B12E
0x18000b129  mov     [rsp+1500h+var_14C8], r12
0x18000b12e  call    cs:__imp_GetCurrentThreadId
0x18000b134  mov     [rsp+1500h+var_14C0], eax
0x18000b138  mov     [rsp+1500h+var_14A8], rsi
0x18000b13d  mov     [rsp+1500h+var_14A0], edi
0x18000b141  mov     [rsp+1500h+var_149C], r15d
0x18000b146  mov     [rsp+1500h+var_14B8], r12
0x18000b14b  mov     [rsp+1500h+var_14B0], r12
0x18000b150  mov     [rbp+1400h+var_1458], r14
0x18000b154  mov     [rbp+1400h+var_1450], rbx
0x18000b158  mov     [rsp+1500h+var_1498], r12
0x18000b15d  xorps   xmm0, xmm0
0x18000b160  xor     eax, eax
0x18000b162  movups  [rbp+1400h+var_1478], xmm0
0x18000b166  mov     [rbp+1400h+var_1468], rax
0x18000b16a  xorps   xmm1, xmm1
0x18000b16d  movups  [rsp+1500h+var_1490], xmm1
0x18000b172  mov     [rbp+1400h+var_1480], rax
0x18000b176  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000b17d  test    rax, rax
0x18000b180  jz      short loc_18000B18D
0x18000b182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b187  mov     [rbp+1400h+var_1460], rax
0x18000b18b  jmp     short loc_18000B191
0x18000b18d  mov     [rbp+1400h+var_1460], r12
0x18000b191  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000b198  test    rax, rax
0x18000b19b  jz      short loc_18000B1A7
0x18000b19d  lea     rcx, [rsp+1500h+var_14E0]
0x18000b1a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1a7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000b1ae  test    rax, rax
0x18000b1b1  jz      short loc_18000B1C7
0x18000b1b3  mov     r8d, 400h
0x18000b1b9  lea     rdx, [rbp+1400h+var_1440]
0x18000b1bd  lea     rcx, [rsp+1500h+var_14E0]
0x18000b1c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1c7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b1ce  test    rax, rax
0x18000b1d1  jz      short loc_18000B1DD
0x18000b1d3  lea     rcx, [rsp+1500h+var_14E0]
0x18000b1d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1dd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000b1e4  test    rax, rax
0x18000b1e7  jz      short loc_18000B1FA
0x18000b1e9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000b1ee  jnz     short loc_18000B1FA
0x18000b1f0  lea     rcx, [rsp+1500h+var_14E0]
0x18000b1f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1fa  cmp     [rsp+1500h+var_14D8], r12d
0x18000b1ff  jge     loc_18000B308
0x18000b205  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000b20c  jnz     short loc_18000B22D
0x18000b20e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000b215  test    rax, rax
0x18000b218  jz      short loc_18000B223
0x18000b21a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b21f  test    al, al
0x18000b221  jmp     short loc_18000B22B
0x18000b223  call    cs:__imp_IsDebuggerPresent
0x18000b229  test    eax, eax
0x18000b22b  jz      short loc_18000B234
0x18000b22d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000b232  jz      short loc_18000B25A
0x18000b234  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b23b  test    rax, rax
0x18000b23e  jz      short loc_18000B2B3
0x18000b240  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000b247  jnz     short loc_18000B2B3
0x18000b249  xor     r8d, r8d
0x18000b24c  xor     edx, edx
0x18000b24e  lea     rcx, [rsp+1500h+var_14E0]
0x18000b253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b258  jmp     short loc_18000B2B3
0x18000b25a  mov     ebx, 800h
0x18000b25f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b266  test    rax, rax
0x18000b269  jz      short loc_18000B288
0x18000b26b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000b272  jnz     short loc_18000B288
0x18000b274  mov     r8d, ebx
0x18000b277  lea     rdx, [rbp+1400h+OutputString]
0x18000b27e  lea     rcx, [rsp+1500h+var_14E0]
0x18000b283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b288  cmp     [rbp+1400h+OutputString], r12w
0x18000b290  jnz     short loc_18000B2A6
0x18000b292  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000b297  mov     rdx, rbx; unsigned __int16 *
0x18000b29a  lea     rcx, [rbp+1400h+OutputString]; this
0x18000b2a1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000b2a6  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000b2ad  call    cs:__imp_OutputDebugStringW
0x18000b2b3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000b2b8  jnz     short loc_18000B2C3
0x18000b2ba  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000b2c1  jz      short loc_18000B2D5
0x18000b2c3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000b2ca  test    rax, rax
0x18000b2cd  jz      short loc_18000B2D5
0x18000b2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2d4  nop
0x18000b2d5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000b2da  jnz     short loc_18000B2FD
0x18000b2dc  mov     rcx, [rbp+1400h+var_40]
0x18000b2e3  xor     rcx, rsp; StackCookie
0x18000b2e6  call    __security_check_cookie
0x18000b2eb  add     rsp, 14D0h
0x18000b2f2  pop     r15
0x18000b2f4  pop     r14
0x18000b2f6  pop     r12
0x18000b2f8  pop     rdi
0x18000b2f9  pop     rsi
0x18000b2fa  pop     rbx
0x18000b2fb  pop     rbp
0x18000b2fc  retn
0x18000b2fd  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000b302  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000b308  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
