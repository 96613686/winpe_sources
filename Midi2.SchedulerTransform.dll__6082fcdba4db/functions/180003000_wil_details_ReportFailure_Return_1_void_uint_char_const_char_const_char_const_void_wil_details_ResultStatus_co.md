# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003000`
- end: `0x18000328d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002ae0`

## callees

- `0x180002000`
- `0x180002a68`
- `0x180003000`
- `0x1800053a4`
- `0x180006840`
- `0x180008910`
- `0x180008a04`
- `0x18000cc00`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800030ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800030ae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000322c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000322c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800031a2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800031a2`

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
        int *a7)
{
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180003000  push    rbp
0x180003002  push    rbx
0x180003003  push    rsi
0x180003004  push    rdi
0x180003005  push    r12
0x180003007  push    r14
0x180003009  push    r15
0x18000300b  lea     rbp, [rsp-13D0h]
0x180003013  mov     eax, 14D0h
0x180003018  call    _alloca_probe
0x18000301d  sub     rsp, rax
0x180003020  mov     rax, cs:__security_cookie
0x180003027  xor     rax, rsp
0x18000302a  mov     [rbp+1400h+var_40], rax
0x180003031  mov     r14, r8
0x180003034  mov     esi, edx
0x180003036  mov     r15, rcx
0x180003039  mov     rdi, [rbp+1400h+arg_28]
0x180003040  xor     edx, edx; Val
0x180003042  mov     r8d, 98h; Size
0x180003048  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000304d  call    memset_0
0x180003052  nop
0x180003053  xor     r12d, r12d
0x180003056  mov     [rbp+1400h+OutputString], r12w
0x18000305e  mov     [rbp+1400h+var_1440], r12b
0x180003062  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180003069  mov     ecx, [rdx]; this
0x18000306b  mov     [rsp+1500h+var_14D8], ecx
0x18000306f  mov     eax, [rdx+4]
0x180003072  mov     [rsp+1500h+var_14D4], eax
0x180003076  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000307b  mov     ebx, eax
0x18000307d  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003085  mov     ecx, r12d
0x180003088  lea     eax, [r12+8]
0x18000308d  cmp     dword ptr [rdx+8], 1
0x180003091  cmovz   ecx, eax
0x180003094  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003098  lea     ecx, [rax-7]
0x18000309b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800030a3  inc     ecx
0x1800030a5  mov     [rsp+1500h+var_14D0], ecx
0x1800030a9  mov     [rsp+1500h+var_14C8], r12
0x1800030ae  call    cs:__imp_GetCurrentThreadId
0x1800030b4  mov     [rsp+1500h+var_14C0], eax
0x1800030b8  mov     [rsp+1500h+var_14A8], r14
0x1800030bd  mov     [rsp+1500h+var_14A0], esi
0x1800030c1  mov     [rsp+1500h+var_149C], ebx
0x1800030c5  mov     [rsp+1500h+var_14B8], r12
0x1800030ca  mov     [rsp+1500h+var_14B0], r12
0x1800030cf  mov     [rbp+1400h+var_1458], rdi
0x1800030d3  mov     [rbp+1400h+var_1450], r15
0x1800030d7  mov     [rsp+1500h+var_1498], r12
0x1800030dc  xorps   xmm0, xmm0
0x1800030df  xor     eax, eax
0x1800030e1  movups  [rbp+1400h+var_1478], xmm0
0x1800030e5  mov     [rbp+1400h+var_1468], rax
0x1800030e9  xorps   xmm1, xmm1
0x1800030ec  movups  [rsp+1500h+var_1490], xmm1
0x1800030f1  mov     [rbp+1400h+var_1480], rax
0x1800030f5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800030fc  test    rax, rax
0x1800030ff  jz      short loc_18000310C
0x180003101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003106  mov     [rbp+1400h+var_1460], rax
0x18000310a  jmp     short loc_180003110
0x18000310c  mov     [rbp+1400h+var_1460], r12
0x180003110  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003117  test    rax, rax
0x18000311a  jz      short loc_180003126
0x18000311c  lea     rcx, [rsp+1500h+var_14E0]
0x180003121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003126  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000312d  test    rax, rax
0x180003130  jz      short loc_180003146
0x180003132  mov     r8d, 400h
0x180003138  lea     rdx, [rbp+1400h+var_1440]
0x18000313c  lea     rcx, [rsp+1500h+var_14E0]
0x180003141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003146  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000314d  test    rax, rax
0x180003150  jz      short loc_18000315C
0x180003152  lea     rcx, [rsp+1500h+var_14E0]
0x180003157  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000315c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003163  test    rax, rax
0x180003166  jz      short loc_180003179
0x180003168  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000316d  jnz     short loc_180003179
0x18000316f  lea     rcx, [rsp+1500h+var_14E0]
0x180003174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003179  cmp     [rsp+1500h+var_14D8], r12d
0x18000317e  jge     loc_180003287
0x180003184  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000318b  jnz     short loc_1800031AC
0x18000318d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003194  test    rax, rax
0x180003197  jz      short loc_1800031A2
0x180003199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000319e  test    al, al
0x1800031a0  jmp     short loc_1800031AA
0x1800031a2  call    cs:__imp_IsDebuggerPresent
0x1800031a8  test    eax, eax
0x1800031aa  jz      short loc_1800031B3
0x1800031ac  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800031b1  jz      short loc_1800031D9
0x1800031b3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800031ba  test    rax, rax
0x1800031bd  jz      short loc_180003232
0x1800031bf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800031c6  jnz     short loc_180003232
0x1800031c8  xor     r8d, r8d
0x1800031cb  xor     edx, edx
0x1800031cd  lea     rcx, [rsp+1500h+var_14E0]
0x1800031d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031d7  jmp     short loc_180003232
0x1800031d9  mov     ebx, 800h
0x1800031de  mov     rax, cs:g_pfnResultLoggingCallback
0x1800031e5  test    rax, rax
0x1800031e8  jz      short loc_180003207
0x1800031ea  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800031f1  jnz     short loc_180003207
0x1800031f3  mov     r8d, ebx
0x1800031f6  lea     rdx, [rbp+1400h+OutputString]
0x1800031fd  lea     rcx, [rsp+1500h+var_14E0]
0x180003202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003207  cmp     [rbp+1400h+OutputString], r12w
0x18000320f  jnz     short loc_180003225
0x180003211  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003216  mov     rdx, rbx; unsigned __int16 *
0x180003219  lea     rcx, [rbp+1400h+OutputString]; this
0x180003220  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003225  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000322c  call    cs:__imp_OutputDebugStringW
0x180003232  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003237  jnz     short loc_180003242
0x180003239  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003240  jz      short loc_180003254
0x180003242  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003249  test    rax, rax
0x18000324c  jz      short loc_180003254
0x18000324e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003253  nop
0x180003254  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003259  jnz     short loc_18000327C
0x18000325b  mov     rcx, [rbp+1400h+var_40]
0x180003262  xor     rcx, rsp; StackCookie
0x180003265  call    __security_check_cookie
0x18000326a  add     rsp, 14D0h
0x180003271  pop     r15
0x180003273  pop     r14
0x180003275  pop     r12
0x180003277  pop     rdi
0x180003278  pop     rsi
0x180003279  pop     rbx
0x18000327a  pop     rbp
0x18000327b  retn
0x18000327c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003281  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003287  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
