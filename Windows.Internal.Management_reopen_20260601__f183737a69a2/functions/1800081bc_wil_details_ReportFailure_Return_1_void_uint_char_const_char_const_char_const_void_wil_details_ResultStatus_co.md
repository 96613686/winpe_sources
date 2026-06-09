# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800081bc`
- end: `0x180008475`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180007e40`

## callees

- `0x180004eb0`
- `0x180005a74`
- `0x1800081bc`
- `0x1800091d4`
- `0x18000a394`
- `0x18000b0d0`
- `0x18000b294`
- `0x1800b6760`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008282`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008282`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000840d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000840d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000837d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000837d`

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
0x1800081bc  push    rbp
0x1800081be  push    rbx
0x1800081bf  push    rsi
0x1800081c0  push    rdi
0x1800081c1  push    r12
0x1800081c3  push    r14
0x1800081c5  push    r15
0x1800081c7  lea     rbp, [rsp-13D0h]
0x1800081cf  mov     eax, 14D0h
0x1800081d4  call    _alloca_probe
0x1800081d9  sub     rsp, rax
0x1800081dc  mov     rax, cs:__security_cookie
0x1800081e3  xor     rax, rsp
0x1800081e6  mov     [rbp+1400h+var_40], rax
0x1800081ed  mov     rsi, r8
0x1800081f0  mov     edi, edx
0x1800081f2  mov     rbx, rcx
0x1800081f5  mov     r14, [rbp+1400h+arg_28]
0x1800081fc  xor     edx, edx; Val
0x1800081fe  mov     r8d, 98h; Size
0x180008204  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180008209  call    memset_0
0x18000820e  nop
0x18000820f  xor     r12d, r12d
0x180008212  mov     [rbp+1400h+OutputString], r12w
0x18000821a  mov     [rbp+1400h+var_1440], r12b
0x18000821e  mov     rdx, [rbp+1400h+arg_30]; int
0x180008225  mov     ecx, [rdx]; this
0x180008227  mov     [rsp+1500h+var_14D8], ecx
0x18000822b  mov     eax, [rdx+4]
0x18000822e  mov     [rsp+1500h+var_14D4], eax
0x180008232  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008237  mov     r15d, eax
0x18000823a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180008242  mov     ecx, r12d
0x180008245  lea     eax, [r12+8]
0x18000824a  cmp     dword ptr [rdx+8], 1
0x18000824e  cmovz   ecx, eax
0x180008251  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180008255  lea     ecx, [rax-7]
0x180008258  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008260  inc     ecx
0x180008262  mov     [rsp+1500h+var_14D0], ecx
0x180008266  mov     rcx, [rbp+1400h+arg_38]
0x18000826d  test    rcx, rcx
0x180008270  jz      short loc_18000827D
0x180008272  cmp     [rcx], r12w
0x180008276  mov     [rsp+1500h+var_14C8], rcx
0x18000827b  jnz     short loc_180008282
0x18000827d  mov     [rsp+1500h+var_14C8], r12
0x180008282  call    cs:__imp_GetCurrentThreadId
0x180008289  nop     dword ptr [rax+rax+00h]
0x18000828e  mov     [rsp+1500h+var_14C0], eax
0x180008292  mov     [rsp+1500h+var_14A8], rsi
0x180008297  mov     [rsp+1500h+var_14A0], edi
0x18000829b  mov     [rsp+1500h+var_149C], r15d
0x1800082a0  mov     [rsp+1500h+var_14B8], r12
0x1800082a5  mov     [rsp+1500h+var_14B0], r12
0x1800082aa  mov     [rbp+1400h+var_1458], r14
0x1800082ae  mov     [rbp+1400h+var_1450], rbx
0x1800082b2  mov     [rsp+1500h+var_1498], r12
0x1800082b7  xorps   xmm0, xmm0
0x1800082ba  xor     eax, eax
0x1800082bc  movups  [rbp+1400h+var_1478], xmm0
0x1800082c0  mov     [rbp+1400h+var_1468], rax
0x1800082c4  xorps   xmm1, xmm1
0x1800082c7  movups  [rsp+1500h+var_1490], xmm1
0x1800082cc  mov     [rbp+1400h+var_1480], rax
0x1800082d0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800082d7  test    rax, rax
0x1800082da  jz      short loc_1800082E7
0x1800082dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082e1  mov     [rbp+1400h+var_1460], rax
0x1800082e5  jmp     short loc_1800082EB
0x1800082e7  mov     [rbp+1400h+var_1460], r12
0x1800082eb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800082f2  test    rax, rax
0x1800082f5  jz      short loc_180008301
0x1800082f7  lea     rcx, [rsp+1500h+var_14E0]
0x1800082fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008301  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008308  test    rax, rax
0x18000830b  jz      short loc_180008321
0x18000830d  mov     r8d, 400h
0x180008313  lea     rdx, [rbp+1400h+var_1440]
0x180008317  lea     rcx, [rsp+1500h+var_14E0]
0x18000831c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008321  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008328  test    rax, rax
0x18000832b  jz      short loc_180008337
0x18000832d  lea     rcx, [rsp+1500h+var_14E0]
0x180008332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008337  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000833e  test    rax, rax
0x180008341  jz      short loc_180008354
0x180008343  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180008348  jnz     short loc_180008354
0x18000834a  lea     rcx, [rsp+1500h+var_14E0]
0x18000834f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008354  cmp     [rsp+1500h+var_14D8], r12d
0x180008359  jge     loc_18000846F
0x18000835f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180008366  jnz     short loc_18000838D
0x180008368  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000836f  test    rax, rax
0x180008372  jz      short loc_18000837D
0x180008374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008379  test    al, al
0x18000837b  jmp     short loc_18000838B
0x18000837d  call    cs:__imp_IsDebuggerPresent
0x180008384  nop     dword ptr [rax+rax+00h]
0x180008389  test    eax, eax
0x18000838b  jz      short loc_180008394
0x18000838d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180008392  jz      short loc_1800083BA
0x180008394  mov     rax, cs:g_pfnResultLoggingCallback
0x18000839b  test    rax, rax
0x18000839e  jz      short loc_180008419
0x1800083a0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800083a7  jnz     short loc_180008419
0x1800083a9  xor     r8d, r8d
0x1800083ac  xor     edx, edx
0x1800083ae  lea     rcx, [rsp+1500h+var_14E0]
0x1800083b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083b8  jmp     short loc_180008419
0x1800083ba  mov     ebx, 800h
0x1800083bf  mov     rax, cs:g_pfnResultLoggingCallback
0x1800083c6  test    rax, rax
0x1800083c9  jz      short loc_1800083E8
0x1800083cb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800083d2  jnz     short loc_1800083E8
0x1800083d4  mov     r8d, ebx
0x1800083d7  lea     rdx, [rbp+1400h+OutputString]
0x1800083de  lea     rcx, [rsp+1500h+var_14E0]
0x1800083e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083e8  cmp     [rbp+1400h+OutputString], r12w
0x1800083f0  jnz     short loc_180008406
0x1800083f2  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800083f7  mov     rdx, rbx; unsigned __int16 *
0x1800083fa  lea     rcx, [rbp+1400h+OutputString]; this
0x180008401  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008406  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000840d  call    cs:__imp_OutputDebugStringW
0x180008414  nop     dword ptr [rax+rax+00h]
0x180008419  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000841e  jnz     short loc_180008429
0x180008420  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180008427  jz      short loc_18000843B
0x180008429  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008430  test    rax, rax
0x180008433  jz      short loc_18000843B
0x180008435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000843a  nop
0x18000843b  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180008440  jnz     short loc_180008464
0x180008442  mov     rcx, [rbp+1400h+var_40]
0x180008449  xor     rcx, rsp; StackCookie
0x18000844c  call    __security_check_cookie
0x180008451  add     rsp, 14D0h
0x180008458  pop     r15
0x18000845a  pop     r14
0x18000845c  pop     r12
0x18000845e  pop     rdi
0x18000845f  pop     rsi
0x180008460  pop     rbx
0x180008461  pop     rbp
0x180008462  retn
0x180008464  lea     rcx, [rsp+1500h+var_14E0]; this
0x180008469  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000846f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
