# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18001c5ac`
- end: `0x18001c840`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180015c44`

## callees

- `0x1800174c0`
- `0x180017e20`
- `0x18001c5ac`
- `0x18001e154`
- `0x180021050`
- `0x1800223b8`
- `0x180027c34`
- `0x180059450`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c656`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c656`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001c7db`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001c7db`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001c751`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001c751`

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
0x18001c5ac  mov     [rsp-8+arg_10], rbx
0x18001c5b1  push    rbp
0x18001c5b2  push    rsi
0x18001c5b3  push    rdi
0x18001c5b4  push    r14
0x18001c5b6  push    r15
0x18001c5b8  lea     rbp, [rsp-13D0h]
0x18001c5c0  mov     eax, 14D0h
0x18001c5c5  call    _alloca_probe
0x18001c5ca  sub     rsp, rax
0x18001c5cd  mov     rax, cs:__security_cookie
0x18001c5d4  xor     rax, rsp
0x18001c5d7  mov     [rbp+13F0h+var_30], rax
0x18001c5de  mov     rdi, [rbp+13F0h+arg_28]
0x18001c5e5  mov     esi, edx
0x18001c5e7  mov     r14, rcx
0x18001c5ea  xor     edx, edx; Val
0x18001c5ec  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001c5f1  mov     r8d, 98h; Size
0x18001c5f7  call    memset_0
0x18001c5fc  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18001c603  xor     r15d, r15d
0x18001c606  mov     [rbp+13F0h+OutputString], r15w
0x18001c60e  mov     [rbp+13F0h+var_1430], r15b
0x18001c612  mov     ecx, [rdx]; this
0x18001c614  mov     eax, [rdx+4]
0x18001c617  mov     [rsp+14F0h+var_14C8], ecx
0x18001c61b  mov     [rsp+14F0h+var_14C4], eax
0x18001c61f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001c624  cmp     dword ptr [rdx+8], 1
0x18001c628  mov     ebx, eax
0x18001c62a  lea     eax, [r15+8]
0x18001c62e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18001c636  mov     ecx, r15d
0x18001c639  cmovz   ecx, eax
0x18001c63c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001c640  lea     ecx, [rax-7]
0x18001c643  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001c64b  inc     ecx
0x18001c64d  mov     [rsp+14F0h+var_14B8], r15
0x18001c652  mov     [rsp+14F0h+var_14C0], ecx
0x18001c656  call    cs:__imp_GetCurrentThreadId
0x18001c65c  xorps   xmm0, xmm0
0x18001c65f  mov     [rsp+14F0h+var_1490], esi
0x18001c663  mov     [rsp+14F0h+var_14B0], eax
0x18001c667  xorps   xmm1, xmm1
0x18001c66a  lea     rax, aWil; "wil"
0x18001c671  mov     [rsp+14F0h+var_148C], ebx
0x18001c675  mov     [rsp+14F0h+var_1498], rax
0x18001c67a  xor     eax, eax
0x18001c67c  mov     [rbp+13F0h+var_1458], rax
0x18001c680  mov     [rbp+13F0h+var_1470], rax
0x18001c684  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001c68b  mov     [rsp+14F0h+var_14A8], r15
0x18001c690  mov     [rsp+14F0h+var_14A0], r15
0x18001c695  mov     [rbp+13F0h+var_1448], rdi
0x18001c699  mov     [rbp+13F0h+var_1440], r14
0x18001c69d  mov     [rsp+14F0h+var_1488], r15
0x18001c6a2  movups  [rbp+13F0h+var_1468], xmm0
0x18001c6a6  movups  [rsp+14F0h+var_1480], xmm1
0x18001c6ab  test    rax, rax
0x18001c6ae  jz      short loc_18001C6BB
0x18001c6b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6b5  mov     [rbp+13F0h+var_1450], rax
0x18001c6b9  jmp     short loc_18001C6BF
0x18001c6bb  mov     [rbp+13F0h+var_1450], r15
0x18001c6bf  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001c6c6  test    rax, rax
0x18001c6c9  jz      short loc_18001C6D5
0x18001c6cb  lea     rcx, [rsp+14F0h+var_14D0]
0x18001c6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6d5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001c6dc  test    rax, rax
0x18001c6df  jz      short loc_18001C6F5
0x18001c6e1  mov     r8d, 400h
0x18001c6e7  lea     rdx, [rbp+13F0h+var_1430]
0x18001c6eb  lea     rcx, [rsp+14F0h+var_14D0]
0x18001c6f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6f5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001c6fc  test    rax, rax
0x18001c6ff  jz      short loc_18001C70B
0x18001c701  lea     rcx, [rsp+14F0h+var_14D0]
0x18001c706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c70b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001c712  test    rax, rax
0x18001c715  jz      short loc_18001C728
0x18001c717  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001c71c  jnz     short loc_18001C728
0x18001c71e  lea     rcx, [rsp+14F0h+var_14D0]
0x18001c723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c728  cmp     [rsp+14F0h+var_14C8], r15d
0x18001c72d  jge     loc_18001C82F
0x18001c733  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18001c73a  jnz     short loc_18001C75B
0x18001c73c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001c743  test    rax, rax
0x18001c746  jz      short loc_18001C751
0x18001c748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c74d  test    al, al
0x18001c74f  jmp     short loc_18001C759
0x18001c751  call    cs:__imp_IsDebuggerPresent
0x18001c757  test    eax, eax
0x18001c759  jz      short loc_18001C762
0x18001c75b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001c760  jz      short loc_18001C788
0x18001c762  mov     rax, cs:g_pfnResultLoggingCallback
0x18001c769  test    rax, rax
0x18001c76c  jz      short loc_18001C7E1
0x18001c76e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001c775  jnz     short loc_18001C7E1
0x18001c777  xor     r8d, r8d
0x18001c77a  lea     rcx, [rsp+14F0h+var_14D0]
0x18001c77f  xor     edx, edx
0x18001c781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c786  jmp     short loc_18001C7E1
0x18001c788  mov     rax, cs:g_pfnResultLoggingCallback
0x18001c78f  mov     ebx, 800h
0x18001c794  test    rax, rax
0x18001c797  jz      short loc_18001C7B6
0x18001c799  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001c7a0  jnz     short loc_18001C7B6
0x18001c7a2  mov     r8d, ebx
0x18001c7a5  lea     rdx, [rbp+13F0h+OutputString]
0x18001c7ac  lea     rcx, [rsp+14F0h+var_14D0]
0x18001c7b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7b6  cmp     [rbp+13F0h+OutputString], r15w
0x18001c7be  jnz     short loc_18001C7D4
0x18001c7c0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001c7c5  mov     rdx, rbx; unsigned __int16 *
0x18001c7c8  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001c7cf  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001c7d4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001c7db  call    cs:__imp_OutputDebugStringW
0x18001c7e1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001c7e6  jnz     short loc_18001C7F1
0x18001c7e8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18001c7ef  jz      short loc_18001C802
0x18001c7f1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001c7f8  test    rax, rax
0x18001c7fb  jz      short loc_18001C802
0x18001c7fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c802  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18001c807  jnz     short loc_18001C835
0x18001c809  mov     rcx, [rbp+13F0h+var_30]
0x18001c810  xor     rcx, rsp; StackCookie
0x18001c813  call    __security_check_cookie
0x18001c818  mov     rbx, [rsp+14F0h+arg_10]
0x18001c820  add     rsp, 14D0h
0x18001c827  pop     r15
0x18001c829  pop     r14
0x18001c82b  pop     rdi
0x18001c82c  pop     rsi
0x18001c82d  pop     rbp
0x18001c82e  retn
0x18001c82f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001c835  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001c83a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
