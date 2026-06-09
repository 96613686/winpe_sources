# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800520e8`
- end: `0x18005238f`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `679`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18004963c`

## callees

- `0x180049d00`
- `0x18004a71c`
- `0x1800520e8`
- `0x180054054`
- `0x18005644c`
- `0x180057c70`
- `0x180057e74`
- `0x1800765d0`
- `0x180077010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180052293`
- `KERNEL32!IsDebuggerPresent` at `0x180052293`
- `KERNEL32!OutputDebugStringW` at `0x180052323`
- `KERNEL32!OutputDebugStringW` at `0x180052323`
- `KERNEL32!GetCurrentThreadId` at `0x180052192`
- `KERNEL32!GetCurrentThreadId` at `0x180052192`

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
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21);
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v19, v17);
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
0x1800520e8  mov     [rsp-8+arg_10], rbx
0x1800520ed  push    rbp
0x1800520ee  push    rsi
0x1800520ef  push    rdi
0x1800520f0  push    r14
0x1800520f2  push    r15
0x1800520f4  lea     rbp, [rsp-13D0h]
0x1800520fc  mov     eax, 14D0h
0x180052101  call    _alloca_probe
0x180052106  sub     rsp, rax
0x180052109  mov     rax, cs:__security_cookie
0x180052110  xor     rax, rsp
0x180052113  mov     [rbp+13F0h+var_30], rax
0x18005211a  mov     rdi, [rbp+13F0h+arg_28]
0x180052121  mov     esi, edx
0x180052123  mov     r14, rcx
0x180052126  xor     edx, edx; Val
0x180052128  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18005212d  mov     r8d, 98h; Size
0x180052133  call    memset_0
0x180052138  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18005213f  xor     r15d, r15d
0x180052142  mov     [rbp+13F0h+OutputString], r15w
0x18005214a  mov     [rbp+13F0h+var_1430], r15b
0x18005214e  mov     ecx, [rdx]; this
0x180052150  mov     eax, [rdx+4]
0x180052153  mov     [rsp+14F0h+var_14C8], ecx
0x180052157  mov     [rsp+14F0h+var_14C4], eax
0x18005215b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180052160  cmp     dword ptr [rdx+8], 1
0x180052164  mov     ebx, eax
0x180052166  lea     eax, [r15+8]
0x18005216a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180052172  mov     ecx, r15d
0x180052175  cmovz   ecx, eax
0x180052178  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18005217c  lea     ecx, [rax-7]
0x18005217f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180052187  inc     ecx
0x180052189  mov     [rsp+14F0h+var_14B8], r15
0x18005218e  mov     [rsp+14F0h+var_14C0], ecx
0x180052192  call    cs:__imp_GetCurrentThreadId
0x180052199  nop     dword ptr [rax+rax+00h]
0x18005219e  xorps   xmm0, xmm0
0x1800521a1  mov     [rsp+14F0h+var_1490], esi
0x1800521a5  mov     [rsp+14F0h+var_14B0], eax
0x1800521a9  xorps   xmm1, xmm1
0x1800521ac  lea     rax, aWil; "wil"
0x1800521b3  mov     [rsp+14F0h+var_148C], ebx
0x1800521b7  mov     [rsp+14F0h+var_1498], rax
0x1800521bc  xor     eax, eax
0x1800521be  mov     [rbp+13F0h+var_1458], rax
0x1800521c2  mov     [rbp+13F0h+var_1470], rax
0x1800521c6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800521cd  mov     [rsp+14F0h+var_14A8], r15
0x1800521d2  mov     [rsp+14F0h+var_14A0], r15
0x1800521d7  mov     [rbp+13F0h+var_1448], rdi
0x1800521db  mov     [rbp+13F0h+var_1440], r14
0x1800521df  mov     [rsp+14F0h+var_1488], r15
0x1800521e4  movups  [rbp+13F0h+var_1468], xmm0
0x1800521e8  movups  [rsp+14F0h+var_1480], xmm1
0x1800521ed  test    rax, rax
0x1800521f0  jz      short loc_1800521FD
0x1800521f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800521f7  mov     [rbp+13F0h+var_1450], rax
0x1800521fb  jmp     short loc_180052201
0x1800521fd  mov     [rbp+13F0h+var_1450], r15
0x180052201  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180052208  test    rax, rax
0x18005220b  jz      short loc_180052217
0x18005220d  lea     rcx, [rsp+14F0h+var_14D0]
0x180052212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052217  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18005221e  test    rax, rax
0x180052221  jz      short loc_180052237
0x180052223  mov     r8d, 400h
0x180052229  lea     rdx, [rbp+13F0h+var_1430]
0x18005222d  lea     rcx, [rsp+14F0h+var_14D0]
0x180052232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052237  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005223e  test    rax, rax
0x180052241  jz      short loc_18005224D
0x180052243  lea     rcx, [rsp+14F0h+var_14D0]
0x180052248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005224d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180052254  test    rax, rax
0x180052257  jz      short loc_18005226A
0x180052259  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18005225e  jnz     short loc_18005226A
0x180052260  lea     rcx, [rsp+14F0h+var_14D0]
0x180052265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005226a  cmp     [rsp+14F0h+var_14C8], r15d
0x18005226f  jge     loc_18005237E
0x180052275  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18005227c  jnz     short loc_1800522A3
0x18005227e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180052285  test    rax, rax
0x180052288  jz      short loc_180052293
0x18005228a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005228f  test    al, al
0x180052291  jmp     short loc_1800522A1
0x180052293  call    cs:__imp_IsDebuggerPresent
0x18005229a  nop     dword ptr [rax+rax+00h]
0x18005229f  test    eax, eax
0x1800522a1  jz      short loc_1800522AA
0x1800522a3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800522a8  jz      short loc_1800522D0
0x1800522aa  mov     rax, cs:g_pfnResultLoggingCallback
0x1800522b1  test    rax, rax
0x1800522b4  jz      short loc_18005232F
0x1800522b6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800522bd  jnz     short loc_18005232F
0x1800522bf  xor     r8d, r8d
0x1800522c2  lea     rcx, [rsp+14F0h+var_14D0]
0x1800522c7  xor     edx, edx
0x1800522c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522ce  jmp     short loc_18005232F
0x1800522d0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800522d7  mov     ebx, 800h
0x1800522dc  test    rax, rax
0x1800522df  jz      short loc_1800522FE
0x1800522e1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800522e8  jnz     short loc_1800522FE
0x1800522ea  mov     r8d, ebx
0x1800522ed  lea     rdx, [rbp+13F0h+OutputString]
0x1800522f4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800522f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800522fe  cmp     [rbp+13F0h+OutputString], r15w
0x180052306  jnz     short loc_18005231C
0x180052308  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18005230d  mov     rdx, rbx; unsigned __int16 *
0x180052310  lea     rcx, [rbp+13F0h+OutputString]; this
0x180052317  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18005231c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180052323  call    cs:__imp_OutputDebugStringW
0x18005232a  nop     dword ptr [rax+rax+00h]
0x18005232f  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180052334  jnz     short loc_18005233F
0x180052336  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18005233d  jz      short loc_180052350
0x18005233f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180052346  test    rax, rax
0x180052349  jz      short loc_180052350
0x18005234b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052350  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180052355  jnz     short loc_180052384
0x180052357  mov     rcx, [rbp+13F0h+var_30]
0x18005235e  xor     rcx, rsp; StackCookie
0x180052361  call    __security_check_cookie
0x180052366  mov     rbx, [rsp+14F0h+arg_10]
0x18005236e  add     rsp, 14D0h
0x180052375  pop     r15
0x180052377  pop     r14
0x180052379  pop     rdi
0x18005237a  pop     rsi
0x18005237b  pop     rbp
0x18005237c  retn
0x18005237e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180052384  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180052389  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
