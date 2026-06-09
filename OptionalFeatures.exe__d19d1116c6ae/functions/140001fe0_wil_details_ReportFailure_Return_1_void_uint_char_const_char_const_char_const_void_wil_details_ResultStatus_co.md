# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140001fe0`
- end: `0x140002274`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140001ac8`

## callees

- `0x14000187f`
- `0x140001fe0`
- `0x140002de4`
- `0x140003cd0`
- `0x140004850`
- `0x14000492c`
- `0x140004ba0`
- `0x140004c30`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000208a`
- `KERNEL32!GetCurrentThreadId` at `0x14000208a`
- `KERNEL32!IsDebuggerPresent` at `0x140002185`
- `KERNEL32!IsDebuggerPresent` at `0x140002185`
- `KERNEL32!OutputDebugStringW` at `0x14000220f`
- `KERNEL32!OutputDebugStringW` at `0x14000220f`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x140001fe0  mov     [rsp-8+arg_10], rbx
0x140001fe5  push    rbp
0x140001fe6  push    rsi
0x140001fe7  push    rdi
0x140001fe8  push    r14
0x140001fea  push    r15
0x140001fec  lea     rbp, [rsp-13D0h]
0x140001ff4  mov     eax, 14D0h
0x140001ff9  call    _alloca_probe
0x140001ffe  sub     rsp, rax
0x140002001  mov     rax, cs:__security_cookie
0x140002008  xor     rax, rsp
0x14000200b  mov     [rbp+13F0h+var_30], rax
0x140002012  mov     rdi, [rbp+13F0h+arg_28]
0x140002019  mov     esi, edx
0x14000201b  mov     r14, rcx
0x14000201e  xor     edx, edx; Val
0x140002020  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140002025  mov     r8d, 98h; Size
0x14000202b  call    memset_0
0x140002030  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140002037  xor     r15d, r15d
0x14000203a  mov     [rbp+13F0h+OutputString], r15w
0x140002042  mov     [rbp+13F0h+var_1430], r15b
0x140002046  mov     ecx, [rdx]; this
0x140002048  mov     eax, [rdx+4]
0x14000204b  mov     [rsp+14F0h+var_14C8], ecx
0x14000204f  mov     [rsp+14F0h+var_14C4], eax
0x140002053  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002058  cmp     dword ptr [rdx+8], 1
0x14000205c  mov     ebx, eax
0x14000205e  lea     eax, [r15+8]
0x140002062  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x14000206a  mov     ecx, r15d
0x14000206d  cmovz   ecx, eax
0x140002070  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002074  lea     ecx, [rax-7]
0x140002077  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000207f  inc     ecx
0x140002081  mov     [rsp+14F0h+var_14B8], r15
0x140002086  mov     [rsp+14F0h+var_14C0], ecx
0x14000208a  call    cs:__imp_GetCurrentThreadId
0x140002090  xorps   xmm0, xmm0
0x140002093  mov     [rsp+14F0h+var_1490], esi
0x140002097  mov     [rsp+14F0h+var_14B0], eax
0x14000209b  xorps   xmm1, xmm1
0x14000209e  lea     rax, aWil; "wil"
0x1400020a5  mov     [rsp+14F0h+var_148C], ebx
0x1400020a9  mov     [rsp+14F0h+var_1498], rax
0x1400020ae  xor     eax, eax
0x1400020b0  mov     [rbp+13F0h+var_1458], rax
0x1400020b4  mov     [rbp+13F0h+var_1470], rax
0x1400020b8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400020bf  mov     [rsp+14F0h+var_14A8], r15
0x1400020c4  mov     [rsp+14F0h+var_14A0], r15
0x1400020c9  mov     [rbp+13F0h+var_1448], rdi
0x1400020cd  mov     [rbp+13F0h+var_1440], r14
0x1400020d1  mov     [rsp+14F0h+var_1488], r15
0x1400020d6  movups  [rbp+13F0h+var_1468], xmm0
0x1400020da  movups  [rsp+14F0h+var_1480], xmm1
0x1400020df  test    rax, rax
0x1400020e2  jz      short loc_1400020EF
0x1400020e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400020e9  mov     [rbp+13F0h+var_1450], rax
0x1400020ed  jmp     short loc_1400020F3
0x1400020ef  mov     [rbp+13F0h+var_1450], r15
0x1400020f3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400020fa  test    rax, rax
0x1400020fd  jz      short loc_140002109
0x1400020ff  lea     rcx, [rsp+14F0h+var_14D0]
0x140002104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002109  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002110  test    rax, rax
0x140002113  jz      short loc_140002129
0x140002115  mov     r8d, 400h
0x14000211b  lea     rdx, [rbp+13F0h+var_1430]
0x14000211f  lea     rcx, [rsp+14F0h+var_14D0]
0x140002124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002129  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002130  test    rax, rax
0x140002133  jz      short loc_14000213F
0x140002135  lea     rcx, [rsp+14F0h+var_14D0]
0x14000213a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000213f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002146  test    rax, rax
0x140002149  jz      short loc_14000215C
0x14000214b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002150  jnz     short loc_14000215C
0x140002152  lea     rcx, [rsp+14F0h+var_14D0]
0x140002157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000215c  cmp     [rsp+14F0h+var_14C8], r15d
0x140002161  jge     loc_140002263
0x140002167  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x14000216e  jnz     short loc_14000218F
0x140002170  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002177  test    rax, rax
0x14000217a  jz      short loc_140002185
0x14000217c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002181  test    al, al
0x140002183  jmp     short loc_14000218D
0x140002185  call    cs:__imp_IsDebuggerPresent
0x14000218b  test    eax, eax
0x14000218d  jz      short loc_140002196
0x14000218f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002194  jz      short loc_1400021BC
0x140002196  mov     rax, cs:g_pfnResultLoggingCallback
0x14000219d  test    rax, rax
0x1400021a0  jz      short loc_140002215
0x1400021a2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400021a9  jnz     short loc_140002215
0x1400021ab  xor     r8d, r8d
0x1400021ae  lea     rcx, [rsp+14F0h+var_14D0]
0x1400021b3  xor     edx, edx
0x1400021b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400021ba  jmp     short loc_140002215
0x1400021bc  mov     rax, cs:g_pfnResultLoggingCallback
0x1400021c3  mov     ebx, 800h
0x1400021c8  test    rax, rax
0x1400021cb  jz      short loc_1400021EA
0x1400021cd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400021d4  jnz     short loc_1400021EA
0x1400021d6  mov     r8d, ebx
0x1400021d9  lea     rdx, [rbp+13F0h+OutputString]
0x1400021e0  lea     rcx, [rsp+14F0h+var_14D0]
0x1400021e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400021ea  cmp     [rbp+13F0h+OutputString], r15w
0x1400021f2  jnz     short loc_140002208
0x1400021f4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400021f9  mov     rdx, rbx; unsigned __int16 *
0x1400021fc  lea     rcx, [rbp+13F0h+OutputString]; this
0x140002203  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002208  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000220f  call    cs:__imp_OutputDebugStringW
0x140002215  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000221a  jnz     short loc_140002225
0x14000221c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140002223  jz      short loc_140002236
0x140002225  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000222c  test    rax, rax
0x14000222f  jz      short loc_140002236
0x140002231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002236  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x14000223b  jnz     short loc_140002269
0x14000223d  mov     rcx, [rbp+13F0h+var_30]
0x140002244  xor     rcx, rsp; StackCookie
0x140002247  call    __security_check_cookie
0x14000224c  mov     rbx, [rsp+14F0h+arg_10]
0x140002254  add     rsp, 14D0h
0x14000225b  pop     r15
0x14000225d  pop     r14
0x14000225f  pop     rdi
0x140002260  pop     rsi
0x140002261  pop     rbp
0x140002262  retn
0x140002263  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002269  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000226e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
