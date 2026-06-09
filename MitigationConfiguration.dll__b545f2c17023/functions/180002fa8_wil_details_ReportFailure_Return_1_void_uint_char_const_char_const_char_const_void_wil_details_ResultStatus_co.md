# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002fa8`
- end: `0x180003235`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002a88`

## callees

- `0x180001c00`
- `0x180002648`
- `0x180002fa8`
- `0x180004b54`
- `0x180005b60`
- `0x180006c70`
- `0x180006e34`
- `0x180013a60`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003056`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003056`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000314a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000314a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800031d4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800031d4`

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
0x180002fa8  push    rbp
0x180002faa  push    rbx
0x180002fab  push    rsi
0x180002fac  push    rdi
0x180002fad  push    r12
0x180002faf  push    r14
0x180002fb1  push    r15
0x180002fb3  lea     rbp, [rsp-13D0h]
0x180002fbb  mov     eax, 14D0h
0x180002fc0  call    _alloca_probe
0x180002fc5  sub     rsp, rax
0x180002fc8  mov     rax, cs:__security_cookie
0x180002fcf  xor     rax, rsp
0x180002fd2  mov     [rbp+1400h+var_40], rax
0x180002fd9  mov     r14, r8
0x180002fdc  mov     esi, edx
0x180002fde  mov     r15, rcx
0x180002fe1  mov     rdi, [rbp+1400h+arg_28]
0x180002fe8  xor     edx, edx; Val
0x180002fea  mov     r8d, 98h; Size
0x180002ff0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002ff5  call    memset_0
0x180002ffa  nop
0x180002ffb  xor     r12d, r12d
0x180002ffe  mov     [rbp+1400h+OutputString], r12w
0x180003006  mov     [rbp+1400h+var_1440], r12b
0x18000300a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180003011  mov     ecx, [rdx]; this
0x180003013  mov     [rsp+1500h+var_14D8], ecx
0x180003017  mov     eax, [rdx+4]
0x18000301a  mov     [rsp+1500h+var_14D4], eax
0x18000301e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003023  mov     ebx, eax
0x180003025  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000302d  mov     ecx, r12d
0x180003030  lea     eax, [r12+8]
0x180003035  cmp     dword ptr [rdx+8], 1
0x180003039  cmovz   ecx, eax
0x18000303c  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003040  lea     ecx, [rax-7]
0x180003043  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000304b  inc     ecx
0x18000304d  mov     [rsp+1500h+var_14D0], ecx
0x180003051  mov     [rsp+1500h+var_14C8], r12
0x180003056  call    cs:__imp_GetCurrentThreadId
0x18000305c  mov     [rsp+1500h+var_14C0], eax
0x180003060  mov     [rsp+1500h+var_14A8], r14
0x180003065  mov     [rsp+1500h+var_14A0], esi
0x180003069  mov     [rsp+1500h+var_149C], ebx
0x18000306d  mov     [rsp+1500h+var_14B8], r12
0x180003072  mov     [rsp+1500h+var_14B0], r12
0x180003077  mov     [rbp+1400h+var_1458], rdi
0x18000307b  mov     [rbp+1400h+var_1450], r15
0x18000307f  mov     [rsp+1500h+var_1498], r12
0x180003084  xorps   xmm0, xmm0
0x180003087  xor     eax, eax
0x180003089  movups  [rbp+1400h+var_1478], xmm0
0x18000308d  mov     [rbp+1400h+var_1468], rax
0x180003091  xorps   xmm1, xmm1
0x180003094  movups  [rsp+1500h+var_1490], xmm1
0x180003099  mov     [rbp+1400h+var_1480], rax
0x18000309d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800030a4  test    rax, rax
0x1800030a7  jz      short loc_1800030B4
0x1800030a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ae  mov     [rbp+1400h+var_1460], rax
0x1800030b2  jmp     short loc_1800030B8
0x1800030b4  mov     [rbp+1400h+var_1460], r12
0x1800030b8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800030bf  test    rax, rax
0x1800030c2  jz      short loc_1800030CE
0x1800030c4  lea     rcx, [rsp+1500h+var_14E0]
0x1800030c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ce  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800030d5  test    rax, rax
0x1800030d8  jz      short loc_1800030EE
0x1800030da  mov     r8d, 400h
0x1800030e0  lea     rdx, [rbp+1400h+var_1440]
0x1800030e4  lea     rcx, [rsp+1500h+var_14E0]
0x1800030e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ee  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800030f5  test    rax, rax
0x1800030f8  jz      short loc_180003104
0x1800030fa  lea     rcx, [rsp+1500h+var_14E0]
0x1800030ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003104  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000310b  test    rax, rax
0x18000310e  jz      short loc_180003121
0x180003110  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003115  jnz     short loc_180003121
0x180003117  lea     rcx, [rsp+1500h+var_14E0]
0x18000311c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003121  cmp     [rsp+1500h+var_14D8], r12d
0x180003126  jge     loc_18000322F
0x18000312c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003133  jnz     short loc_180003154
0x180003135  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000313c  test    rax, rax
0x18000313f  jz      short loc_18000314A
0x180003141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003146  test    al, al
0x180003148  jmp     short loc_180003152
0x18000314a  call    cs:__imp_IsDebuggerPresent
0x180003150  test    eax, eax
0x180003152  jz      short loc_18000315B
0x180003154  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003159  jz      short loc_180003181
0x18000315b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003162  test    rax, rax
0x180003165  jz      short loc_1800031DA
0x180003167  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000316e  jnz     short loc_1800031DA
0x180003170  xor     r8d, r8d
0x180003173  xor     edx, edx
0x180003175  lea     rcx, [rsp+1500h+var_14E0]
0x18000317a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000317f  jmp     short loc_1800031DA
0x180003181  mov     ebx, 800h
0x180003186  mov     rax, cs:g_pfnResultLoggingCallback
0x18000318d  test    rax, rax
0x180003190  jz      short loc_1800031AF
0x180003192  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003199  jnz     short loc_1800031AF
0x18000319b  mov     r8d, ebx
0x18000319e  lea     rdx, [rbp+1400h+OutputString]
0x1800031a5  lea     rcx, [rsp+1500h+var_14E0]
0x1800031aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031af  cmp     [rbp+1400h+OutputString], r12w
0x1800031b7  jnz     short loc_1800031CD
0x1800031b9  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800031be  mov     rdx, rbx; unsigned __int16 *
0x1800031c1  lea     rcx, [rbp+1400h+OutputString]; this
0x1800031c8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800031cd  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800031d4  call    cs:__imp_OutputDebugStringW
0x1800031da  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800031df  jnz     short loc_1800031EA
0x1800031e1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800031e8  jz      short loc_1800031FC
0x1800031ea  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800031f1  test    rax, rax
0x1800031f4  jz      short loc_1800031FC
0x1800031f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031fb  nop
0x1800031fc  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003201  jnz     short loc_180003224
0x180003203  mov     rcx, [rbp+1400h+var_40]
0x18000320a  xor     rcx, rsp; StackCookie
0x18000320d  call    __security_check_cookie
0x180003212  add     rsp, 14D0h
0x180003219  pop     r15
0x18000321b  pop     r14
0x18000321d  pop     r12
0x18000321f  pop     rdi
0x180003220  pop     rsi
0x180003221  pop     rbx
0x180003222  pop     rbp
0x180003223  retn
0x180003224  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003229  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000322f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
