# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002f5c`
- end: `0x1800031f2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002a3c`

## callees

- `0x180001d30`
- `0x1800027c8`
- `0x180002f5c`
- `0x1800051f4`
- `0x180006a18`
- `0x180008e00`
- `0x180008fcc`
- `0x180029820`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003007`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003007`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000318c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000318c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003102`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003102`

## pseudocode

```c
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
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
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
0x180002f5c  mov     [rsp-8+arg_10], rbx
0x180002f61  push    rbp
0x180002f62  push    rsi
0x180002f63  push    rdi
0x180002f64  push    r14
0x180002f66  push    r15
0x180002f68  lea     rbp, [rsp-13D0h]
0x180002f70  mov     eax, 14D0h
0x180002f75  call    _alloca_probe
0x180002f7a  sub     rsp, rax
0x180002f7d  mov     rax, cs:__security_cookie
0x180002f84  xor     rax, rsp
0x180002f87  mov     [rbp+13F0h+var_30], rax
0x180002f8e  mov     esi, edx
0x180002f90  mov     r14, rcx
0x180002f93  mov     rdi, [rbp+13F0h+arg_28]
0x180002f9a  xor     edx, edx; Val
0x180002f9c  mov     r8d, 98h; Size
0x180002fa2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002fa7  call    memset_0
0x180002fac  nop
0x180002fad  xor     r15d, r15d
0x180002fb0  mov     [rbp+13F0h+OutputString], r15w
0x180002fb8  mov     [rbp+13F0h+var_1430], r15b
0x180002fbc  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002fc3  mov     ecx, [rdx]; this
0x180002fc5  mov     [rsp+14F0h+var_14C8], ecx
0x180002fc9  mov     eax, [rdx+4]
0x180002fcc  mov     [rsp+14F0h+var_14C4], eax
0x180002fd0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002fd5  mov     ebx, eax
0x180002fd7  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002fdf  mov     ecx, r15d
0x180002fe2  lea     eax, [r15+8]
0x180002fe6  cmp     dword ptr [rdx+8], 1
0x180002fea  cmovz   ecx, eax
0x180002fed  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002ff1  lea     ecx, [rax-7]
0x180002ff4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002ffc  inc     ecx
0x180002ffe  mov     [rsp+14F0h+var_14C0], ecx
0x180003002  mov     [rsp+14F0h+var_14B8], r15
0x180003007  call    cs:__imp_GetCurrentThreadId
0x18000300d  mov     [rsp+14F0h+var_14B0], eax
0x180003011  lea     rax, aWil; "wil"
0x180003018  mov     [rsp+14F0h+var_1498], rax
0x18000301d  mov     [rsp+14F0h+var_1490], esi
0x180003021  mov     [rsp+14F0h+var_148C], ebx
0x180003025  mov     [rsp+14F0h+var_14A8], r15
0x18000302a  mov     [rsp+14F0h+var_14A0], r15
0x18000302f  mov     [rbp+13F0h+var_1448], rdi
0x180003033  mov     [rbp+13F0h+var_1440], r14
0x180003037  mov     [rsp+14F0h+var_1488], r15
0x18000303c  xorps   xmm0, xmm0
0x18000303f  xor     eax, eax
0x180003041  movups  [rbp+13F0h+var_1468], xmm0
0x180003045  mov     [rbp+13F0h+var_1458], rax
0x180003049  xorps   xmm1, xmm1
0x18000304c  movups  [rsp+14F0h+var_1480], xmm1
0x180003051  mov     [rbp+13F0h+var_1470], rax
0x180003055  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000305c  test    rax, rax
0x18000305f  jz      short loc_18000306C
0x180003061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003066  mov     [rbp+13F0h+var_1450], rax
0x18000306a  jmp     short loc_180003070
0x18000306c  mov     [rbp+13F0h+var_1450], r15
0x180003070  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003077  test    rax, rax
0x18000307a  jz      short loc_180003086
0x18000307c  lea     rcx, [rsp+14F0h+var_14D0]
0x180003081  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003086  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000308d  test    rax, rax
0x180003090  jz      short loc_1800030A6
0x180003092  mov     r8d, 400h
0x180003098  lea     rdx, [rbp+13F0h+var_1430]
0x18000309c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800030ad  test    rax, rax
0x1800030b0  jz      short loc_1800030BC
0x1800030b2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030bc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800030c3  test    rax, rax
0x1800030c6  jz      short loc_1800030D9
0x1800030c8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800030cd  jnz     short loc_1800030D9
0x1800030cf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d9  cmp     [rsp+14F0h+var_14C8], r15d
0x1800030de  jge     loc_1800031EC
0x1800030e4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800030eb  jnz     short loc_18000310C
0x1800030ed  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800030f4  test    rax, rax
0x1800030f7  jz      short loc_180003102
0x1800030f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030fe  test    al, al
0x180003100  jmp     short loc_18000310A
0x180003102  call    cs:__imp_IsDebuggerPresent
0x180003108  test    eax, eax
0x18000310a  jz      short loc_180003113
0x18000310c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003111  jz      short loc_180003139
0x180003113  mov     rax, cs:g_pfnResultLoggingCallback
0x18000311a  test    rax, rax
0x18000311d  jz      short loc_180003192
0x18000311f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003126  jnz     short loc_180003192
0x180003128  xor     r8d, r8d
0x18000312b  xor     edx, edx
0x18000312d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003137  jmp     short loc_180003192
0x180003139  mov     ebx, 800h
0x18000313e  mov     rax, cs:g_pfnResultLoggingCallback
0x180003145  test    rax, rax
0x180003148  jz      short loc_180003167
0x18000314a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003151  jnz     short loc_180003167
0x180003153  mov     r8d, ebx
0x180003156  lea     rdx, [rbp+13F0h+OutputString]
0x18000315d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003167  cmp     [rbp+13F0h+OutputString], r15w
0x18000316f  jnz     short loc_180003185
0x180003171  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003176  mov     rdx, rbx; unsigned __int16 *
0x180003179  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003180  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003185  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000318c  call    cs:__imp_OutputDebugStringW
0x180003192  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003197  jnz     short loc_1800031A2
0x180003199  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800031a0  jz      short loc_1800031B4
0x1800031a2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800031a9  test    rax, rax
0x1800031ac  jz      short loc_1800031B4
0x1800031ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031b3  nop
0x1800031b4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800031b9  jnz     short loc_1800031E1
0x1800031bb  mov     rcx, [rbp+13F0h+var_30]
0x1800031c2  xor     rcx, rsp; StackCookie
0x1800031c5  call    __security_check_cookie
0x1800031ca  mov     rbx, [rsp+14F0h+arg_10]
0x1800031d2  add     rsp, 14D0h
0x1800031d9  pop     r15
0x1800031db  pop     r14
0x1800031dd  pop     rdi
0x1800031de  pop     rsi
0x1800031df  pop     rbp
0x1800031e0  retn
0x1800031e1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800031e6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800031ec  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
