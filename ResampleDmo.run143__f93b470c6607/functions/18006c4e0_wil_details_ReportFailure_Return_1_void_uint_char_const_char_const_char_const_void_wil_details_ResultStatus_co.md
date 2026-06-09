# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18006c4e0`
- end: `0x18006c78d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `685`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18006c470`

## callees

- `0x18000ab90`
- `0x18006c4e0`
- `0x18006cdd0`
- `0x18006d4f0`
- `0x18006d620`
- `0x18006d780`
- `0x180084630`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006c5ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006c5ae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18006c72c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18006c72c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006c6a2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006c6a2`

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
        unsigned __int64 *a7)
{
  unsigned int v10; // ebx
  int v11; // ecx
  __int64 v12; // r8
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  unsigned __int64 v17[2]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v18; // [rsp+30h] [rbp-D0h]
  __int128 v19; // [rsp+40h] [rbp-C0h]
  __int128 v20; // [rsp+50h] [rbp-B0h]
  __int128 v21; // [rsp+60h] [rbp-A0h]
  __int128 v22; // [rsp+70h] [rbp-90h]
  _OWORD v23[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v24; // [rsp+A0h] [rbp-60h]
  __int64 v25; // [rsp+B0h] [rbp-50h]
  _BYTE v26[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  *(_OWORD *)v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  memset(v23, 0, sizeof(v23));
  v24 = 0;
  v25 = 0;
  OutputString[0] = 0;
  v26[0] = 0;
  v17[1] = *a7;
  v10 = wil::details::RecordReturn((wil::details *)LODWORD(v17[1]), a2);
  LODWORD(v17[0]) = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  HIDWORD(v17[0]) = v11;
  LODWORD(v18) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  *((_QWORD *)&v18 + 1) = 0;
  LODWORD(v19) = GetCurrentThreadId();
  *((_QWORD *)&v20 + 1) = a3;
  v21 = __PAIR64__(v10, a2);
  *((_QWORD *)&v19 + 1) = 0;
  *(_QWORD *)&v20 = 0;
  *((_QWORD *)&v24 + 1) = a6;
  v25 = a1;
  v22 = 0;
  memset(v23, 0, sizeof(v23));
  if ( wil::details::g_pfnGetModuleName )
    *(_QWORD *)&v24 = wil::details::g_pfnGetModuleName(v14);
  else
    *(_QWORD *)&v24 = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v17, v26, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v17);
  if ( wil::details::g_pfnOriginateCallback && (v17[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v17);
  if ( SLODWORD(v17[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v17[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v17[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v17, v13);
}

```

## disassembly

```asm
0x18006c4e0  push    rbp
0x18006c4e2  push    rbx
0x18006c4e3  push    rsi
0x18006c4e4  push    rdi
0x18006c4e5  push    r12
0x18006c4e7  push    r14
0x18006c4e9  push    r15
0x18006c4eb  lea     rbp, [rsp-13D0h]
0x18006c4f3  mov     eax, 14D0h
0x18006c4f8  call    _alloca_probe
0x18006c4fd  sub     rsp, rax
0x18006c500  mov     rax, cs:__security_cookie
0x18006c507  xor     rax, rsp
0x18006c50a  mov     [rbp+1400h+var_40], rax
0x18006c511  mov     r14, r8
0x18006c514  mov     esi, edx
0x18006c516  mov     r15, rcx
0x18006c519  mov     rdi, [rbp+1400h+arg_28]
0x18006c520  xorps   xmm0, xmm0
0x18006c523  xor     eax, eax
0x18006c525  movups  xmmword ptr [rsp+1500h+var_14E0], xmm0
0x18006c52a  movups  [rsp+1500h+var_14D0], xmm0
0x18006c52f  movups  [rsp+1500h+var_14C0], xmm0
0x18006c534  movups  [rsp+1500h+var_14B0], xmm0
0x18006c539  movups  [rsp+1500h+var_14A0], xmm0
0x18006c53e  movups  [rsp+1500h+var_1490], xmm0
0x18006c543  movups  [rbp+1400h+var_1480], xmm0
0x18006c547  movups  [rbp+1400h+var_1470], xmm0
0x18006c54b  movups  [rbp+1400h+var_1460], xmm0
0x18006c54f  mov     [rbp+1400h+var_1450], rax
0x18006c553  xor     r12d, r12d
0x18006c556  mov     [rbp+1400h+OutputString], r12w
0x18006c55e  mov     [rbp+1400h+var_1440], r12b
0x18006c562  mov     r8, [rbp+1400h+arg_30]
0x18006c569  mov     ecx, [r8]; this
0x18006c56c  mov     dword ptr [rsp+1500h+var_14E0+8], ecx
0x18006c570  mov     eax, [r8+4]
0x18006c574  mov     dword ptr [rsp+1500h+var_14E0+0Ch], eax
0x18006c578  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18006c57d  mov     ebx, eax
0x18006c57f  mov     edx, 1
0x18006c584  mov     dword ptr [rsp+1500h+var_14E0], edx
0x18006c588  mov     ecx, r12d
0x18006c58b  mov     eax, 8
0x18006c590  cmp     [r8+8], edx
0x18006c594  cmovz   ecx, eax
0x18006c597  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18006c59b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, edx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18006c5a3  inc     edx
0x18006c5a5  mov     dword ptr [rsp+1500h+var_14D0], edx
0x18006c5a9  mov     qword ptr [rsp+1500h+var_14D0+8], r12
0x18006c5ae  call    cs:__imp_GetCurrentThreadId
0x18006c5b4  mov     dword ptr [rsp+1500h+var_14C0], eax
0x18006c5b8  mov     qword ptr [rsp+1500h+var_14B0+8], r14
0x18006c5bd  mov     dword ptr [rsp+1500h+var_14A0], esi
0x18006c5c1  mov     dword ptr [rsp+1500h+var_14A0+4], ebx
0x18006c5c5  mov     qword ptr [rsp+1500h+var_14C0+8], r12
0x18006c5ca  mov     qword ptr [rsp+1500h+var_14B0], r12
0x18006c5cf  mov     qword ptr [rbp+1400h+var_1460+8], rdi
0x18006c5d3  mov     [rbp+1400h+var_1450], r15
0x18006c5d7  mov     qword ptr [rsp+1500h+var_14A0+8], r12
0x18006c5dc  xorps   xmm0, xmm0
0x18006c5df  xor     eax, eax
0x18006c5e1  movups  [rbp+1400h+var_1480+8], xmm0
0x18006c5e5  mov     qword ptr [rbp+1400h+var_1470+8], rax
0x18006c5e9  xorps   xmm1, xmm1
0x18006c5ec  movups  [rsp+1500h+var_1490], xmm1
0x18006c5f1  mov     qword ptr [rbp+1400h+var_1480], rax
0x18006c5f5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18006c5fc  test    rax, rax
0x18006c5ff  jz      short loc_18006C60C
0x18006c601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c606  mov     qword ptr [rbp+1400h+var_1460], rax
0x18006c60a  jmp     short loc_18006C610
0x18006c60c  mov     qword ptr [rbp+1400h+var_1460], r12
0x18006c610  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18006c617  test    rax, rax
0x18006c61a  jz      short loc_18006C626
0x18006c61c  lea     rcx, [rsp+1500h+var_14E0]
0x18006c621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c626  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18006c62d  test    rax, rax
0x18006c630  jz      short loc_18006C646
0x18006c632  mov     r8d, 400h
0x18006c638  lea     rdx, [rbp+1400h+var_1440]
0x18006c63c  lea     rcx, [rsp+1500h+var_14E0]
0x18006c641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c646  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18006c64d  test    rax, rax
0x18006c650  jz      short loc_18006C65C
0x18006c652  lea     rcx, [rsp+1500h+var_14E0]
0x18006c657  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c65c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18006c663  test    rax, rax
0x18006c666  jz      short loc_18006C679
0x18006c668  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18006c66d  jnz     short loc_18006C679
0x18006c66f  lea     rcx, [rsp+1500h+var_14E0]
0x18006c674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c679  cmp     dword ptr [rsp+1500h+var_14E0+8], r12d
0x18006c67e  jge     loc_18006C787
0x18006c684  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18006c68b  jnz     short loc_18006C6AC
0x18006c68d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18006c694  test    rax, rax
0x18006c697  jz      short loc_18006C6A2
0x18006c699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c69e  test    al, al
0x18006c6a0  jmp     short loc_18006C6AA
0x18006c6a2  call    cs:__imp_IsDebuggerPresent
0x18006c6a8  test    eax, eax
0x18006c6aa  jz      short loc_18006C6B3
0x18006c6ac  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18006c6b1  jz      short loc_18006C6D9
0x18006c6b3  mov     rax, cs:g_pfnResultLoggingCallback
0x18006c6ba  test    rax, rax
0x18006c6bd  jz      short loc_18006C732
0x18006c6bf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18006c6c6  jnz     short loc_18006C732
0x18006c6c8  xor     r8d, r8d
0x18006c6cb  xor     edx, edx
0x18006c6cd  lea     rcx, [rsp+1500h+var_14E0]
0x18006c6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c6d7  jmp     short loc_18006C732
0x18006c6d9  mov     rax, cs:g_pfnResultLoggingCallback
0x18006c6e0  test    rax, rax
0x18006c6e3  jz      short loc_18006C705
0x18006c6e5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18006c6ec  jnz     short loc_18006C705
0x18006c6ee  mov     r8d, 800h
0x18006c6f4  lea     rdx, [rbp+1400h+OutputString]
0x18006c6fb  lea     rcx, [rsp+1500h+var_14E0]
0x18006c700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c705  cmp     [rbp+1400h+OutputString], r12w
0x18006c70d  jnz     short loc_18006C725
0x18006c70f  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18006c714  mov     edx, 800h; unsigned __int16 *
0x18006c719  lea     rcx, [rbp+1400h+OutputString]; this
0x18006c720  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18006c725  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18006c72c  call    cs:__imp_OutputDebugStringW
0x18006c732  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18006c737  jnz     short loc_18006C742
0x18006c739  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18006c740  jz      short loc_18006C754
0x18006c742  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18006c749  test    rax, rax
0x18006c74c  jz      short loc_18006C754
0x18006c74e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006c753  nop
0x18006c754  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18006c759  jnz     short loc_18006C77C
0x18006c75b  mov     rcx, [rbp+1400h+var_40]
0x18006c762  xor     rcx, rsp; StackCookie
0x18006c765  call    __security_check_cookie
0x18006c76a  add     rsp, 14D0h
0x18006c771  pop     r15
0x18006c773  pop     r14
0x18006c775  pop     r12
0x18006c777  pop     rdi
0x18006c778  pop     rsi
0x18006c779  pop     rbx
0x18006c77a  pop     rbp
0x18006c77b  retn
0x18006c77c  lea     rcx, [rsp+1500h+var_14E0]; this
0x18006c781  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18006c787  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
