# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000a648`
- end: `0x14000a8d3`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140008008`

## callees

- `0x140007714`
- `0x140008c80`
- `0x140009640`
- `0x14000a648`
- `0x14000b4d4`
- `0x14000cc98`
- `0x14000cd74`
- `0x14000f260`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a6f5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a6f5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000a873`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000a873`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000a7e9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000a7e9`

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
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x14000a648  push    rbp
0x14000a64a  push    rbx
0x14000a64b  push    rsi
0x14000a64c  push    rdi
0x14000a64d  push    r12
0x14000a64f  push    r14
0x14000a651  push    r15
0x14000a653  lea     rbp, [rsp-13D0h]
0x14000a65b  mov     eax, 14D0h
0x14000a660  call    _alloca_probe
0x14000a665  sub     rsp, rax
0x14000a668  mov     rax, cs:__security_cookie
0x14000a66f  xor     rax, rsp
0x14000a672  mov     [rbp+1400h+var_40], rax
0x14000a679  mov     rdi, [rbp+1400h+arg_28]
0x14000a680  mov     r14, r8
0x14000a683  mov     esi, edx
0x14000a685  mov     r15, rcx
0x14000a688  xor     edx, edx; Val
0x14000a68a  lea     rcx, [rsp+1500h+var_14E0]; void *
0x14000a68f  mov     r8d, 98h; Size
0x14000a695  call    memset_0
0x14000a69a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x14000a6a1  xor     r12d, r12d
0x14000a6a4  mov     [rbp+1400h+OutputString], r12w
0x14000a6ac  mov     [rbp+1400h+var_1440], r12b
0x14000a6b0  mov     ecx, [rdx]; this
0x14000a6b2  mov     eax, [rdx+4]
0x14000a6b5  mov     [rsp+1500h+var_14D8], ecx
0x14000a6b9  mov     [rsp+1500h+var_14D4], eax
0x14000a6bd  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000a6c2  cmp     dword ptr [rdx+8], 1
0x14000a6c6  mov     ebx, eax
0x14000a6c8  lea     eax, [r12+8]
0x14000a6cd  mov     dword ptr [rsp+1500h+var_14E0], 1
0x14000a6d5  mov     ecx, r12d
0x14000a6d8  cmovz   ecx, eax
0x14000a6db  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x14000a6df  lea     ecx, [rax-7]
0x14000a6e2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000a6ea  inc     ecx
0x14000a6ec  mov     [rsp+1500h+var_14C8], r12
0x14000a6f1  mov     [rsp+1500h+var_14D0], ecx
0x14000a6f5  call    cs:__imp_GetCurrentThreadId
0x14000a6fb  xorps   xmm0, xmm0
0x14000a6fe  mov     [rsp+1500h+var_14A8], r14
0x14000a703  mov     [rsp+1500h+var_14C0], eax
0x14000a707  xorps   xmm1, xmm1
0x14000a70a  xor     eax, eax
0x14000a70c  mov     [rsp+1500h+var_14A0], esi
0x14000a710  mov     [rbp+1400h+var_1468], rax
0x14000a714  mov     [rbp+1400h+var_1480], rax
0x14000a718  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000a71f  mov     [rsp+1500h+var_149C], ebx
0x14000a723  mov     [rsp+1500h+var_14B8], r12
0x14000a728  mov     [rsp+1500h+var_14B0], r12
0x14000a72d  mov     [rbp+1400h+var_1458], rdi
0x14000a731  mov     [rbp+1400h+var_1450], r15
0x14000a735  mov     [rsp+1500h+var_1498], r12
0x14000a73a  movups  [rbp+1400h+var_1478], xmm0
0x14000a73e  movups  [rsp+1500h+var_1490], xmm1
0x14000a743  test    rax, rax
0x14000a746  jz      short loc_14000A753
0x14000a748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a74d  mov     [rbp+1400h+var_1460], rax
0x14000a751  jmp     short loc_14000A757
0x14000a753  mov     [rbp+1400h+var_1460], r12
0x14000a757  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000a75e  test    rax, rax
0x14000a761  jz      short loc_14000A76D
0x14000a763  lea     rcx, [rsp+1500h+var_14E0]
0x14000a768  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a76d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000a774  test    rax, rax
0x14000a777  jz      short loc_14000A78D
0x14000a779  mov     r8d, 400h
0x14000a77f  lea     rdx, [rbp+1400h+var_1440]
0x14000a783  lea     rcx, [rsp+1500h+var_14E0]
0x14000a788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a78d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a794  test    rax, rax
0x14000a797  jz      short loc_14000A7A3
0x14000a799  lea     rcx, [rsp+1500h+var_14E0]
0x14000a79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7a3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a7aa  test    rax, rax
0x14000a7ad  jz      short loc_14000A7C0
0x14000a7af  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000a7b4  jnz     short loc_14000A7C0
0x14000a7b6  lea     rcx, [rsp+1500h+var_14E0]
0x14000a7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7c0  cmp     [rsp+1500h+var_14D8], r12d
0x14000a7c5  jge     loc_14000A8C2
0x14000a7cb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000a7d2  jnz     short loc_14000A7F3
0x14000a7d4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000a7db  test    rax, rax
0x14000a7de  jz      short loc_14000A7E9
0x14000a7e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a7e5  test    al, al
0x14000a7e7  jmp     short loc_14000A7F1
0x14000a7e9  call    cs:__imp_IsDebuggerPresent
0x14000a7ef  test    eax, eax
0x14000a7f1  jz      short loc_14000A7FA
0x14000a7f3  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000a7f8  jz      short loc_14000A820
0x14000a7fa  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a801  test    rax, rax
0x14000a804  jz      short loc_14000A879
0x14000a806  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000a80d  jnz     short loc_14000A879
0x14000a80f  xor     r8d, r8d
0x14000a812  lea     rcx, [rsp+1500h+var_14E0]
0x14000a817  xor     edx, edx
0x14000a819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a81e  jmp     short loc_14000A879
0x14000a820  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a827  mov     ebx, 800h
0x14000a82c  test    rax, rax
0x14000a82f  jz      short loc_14000A84E
0x14000a831  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000a838  jnz     short loc_14000A84E
0x14000a83a  mov     r8d, ebx
0x14000a83d  lea     rdx, [rbp+1400h+OutputString]
0x14000a844  lea     rcx, [rsp+1500h+var_14E0]
0x14000a849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a84e  cmp     [rbp+1400h+OutputString], r12w
0x14000a856  jnz     short loc_14000A86C
0x14000a858  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x14000a85d  mov     rdx, rbx; unsigned __int16 *
0x14000a860  lea     rcx, [rbp+1400h+OutputString]; this
0x14000a867  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000a86c  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x14000a873  call    cs:__imp_OutputDebugStringW
0x14000a879  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x14000a87e  jnz     short loc_14000A889
0x14000a880  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000a887  jz      short loc_14000A89A
0x14000a889  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000a890  test    rax, rax
0x14000a893  jz      short loc_14000A89A
0x14000a895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a89a  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x14000a89f  jnz     short loc_14000A8C8
0x14000a8a1  mov     rcx, [rbp+1400h+var_40]
0x14000a8a8  xor     rcx, rsp; StackCookie
0x14000a8ab  call    __security_check_cookie
0x14000a8b0  add     rsp, 14D0h
0x14000a8b7  pop     r15
0x14000a8b9  pop     r14
0x14000a8bb  pop     r12
0x14000a8bd  pop     rdi
0x14000a8be  pop     rsi
0x14000a8bf  pop     rbx
0x14000a8c0  pop     rbp
0x14000a8c1  retn
0x14000a8c2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000a8c8  lea     rcx, [rsp+1500h+var_14E0]; this
0x14000a8cd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
