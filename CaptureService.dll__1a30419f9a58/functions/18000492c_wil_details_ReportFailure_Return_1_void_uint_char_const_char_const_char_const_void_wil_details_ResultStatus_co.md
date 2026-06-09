# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000492c`
- end: `0x180004bb9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800045c4`

## callees

- `0x180002e60`
- `0x180003bc8`
- `0x18000492c`
- `0x180006af4`
- `0x180008830`
- `0x18000a668`
- `0x18000a900`
- `0x180020780`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800049da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800049da`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004ace`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004ace`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004b58`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004b58`

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
0x18000492c  push    rbp
0x18000492e  push    rbx
0x18000492f  push    rsi
0x180004930  push    rdi
0x180004931  push    r12
0x180004933  push    r14
0x180004935  push    r15
0x180004937  lea     rbp, [rsp-13D0h]
0x18000493f  mov     eax, 14D0h
0x180004944  call    _alloca_probe
0x180004949  sub     rsp, rax
0x18000494c  mov     rax, cs:__security_cookie
0x180004953  xor     rax, rsp
0x180004956  mov     [rbp+1400h+var_40], rax
0x18000495d  mov     r14, r8
0x180004960  mov     esi, edx
0x180004962  mov     r15, rcx
0x180004965  mov     rdi, [rbp+1400h+arg_28]
0x18000496c  xor     edx, edx; Val
0x18000496e  mov     r8d, 98h; Size
0x180004974  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004979  call    memset_0
0x18000497e  nop
0x18000497f  xor     r12d, r12d
0x180004982  mov     [rbp+1400h+OutputString], r12w
0x18000498a  mov     [rbp+1400h+var_1440], r12b
0x18000498e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180004995  mov     ecx, [rdx]; this
0x180004997  mov     [rsp+1500h+var_14D8], ecx
0x18000499b  mov     eax, [rdx+4]
0x18000499e  mov     [rsp+1500h+var_14D4], eax
0x1800049a2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800049a7  mov     ebx, eax
0x1800049a9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800049b1  mov     ecx, r12d
0x1800049b4  lea     eax, [r12+8]
0x1800049b9  cmp     dword ptr [rdx+8], 1
0x1800049bd  cmovz   ecx, eax
0x1800049c0  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800049c4  lea     ecx, [rax-7]
0x1800049c7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800049cf  inc     ecx
0x1800049d1  mov     [rsp+1500h+var_14D0], ecx
0x1800049d5  mov     [rsp+1500h+var_14C8], r12
0x1800049da  call    cs:__imp_GetCurrentThreadId
0x1800049e0  mov     [rsp+1500h+var_14C0], eax
0x1800049e4  mov     [rsp+1500h+var_14A8], r14
0x1800049e9  mov     [rsp+1500h+var_14A0], esi
0x1800049ed  mov     [rsp+1500h+var_149C], ebx
0x1800049f1  mov     [rsp+1500h+var_14B8], r12
0x1800049f6  mov     [rsp+1500h+var_14B0], r12
0x1800049fb  mov     [rbp+1400h+var_1458], rdi
0x1800049ff  mov     [rbp+1400h+var_1450], r15
0x180004a03  mov     [rsp+1500h+var_1498], r12
0x180004a08  xorps   xmm0, xmm0
0x180004a0b  xor     eax, eax
0x180004a0d  movups  [rbp+1400h+var_1478], xmm0
0x180004a11  mov     [rbp+1400h+var_1468], rax
0x180004a15  xorps   xmm1, xmm1
0x180004a18  movups  [rsp+1500h+var_1490], xmm1
0x180004a1d  mov     [rbp+1400h+var_1480], rax
0x180004a21  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004a28  test    rax, rax
0x180004a2b  jz      short loc_180004A38
0x180004a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a32  mov     [rbp+1400h+var_1460], rax
0x180004a36  jmp     short loc_180004A3C
0x180004a38  mov     [rbp+1400h+var_1460], r12
0x180004a3c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004a43  test    rax, rax
0x180004a46  jz      short loc_180004A52
0x180004a48  lea     rcx, [rsp+1500h+var_14E0]
0x180004a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a52  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004a59  test    rax, rax
0x180004a5c  jz      short loc_180004A72
0x180004a5e  mov     r8d, 400h
0x180004a64  lea     rdx, [rbp+1400h+var_1440]
0x180004a68  lea     rcx, [rsp+1500h+var_14E0]
0x180004a6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a72  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004a79  test    rax, rax
0x180004a7c  jz      short loc_180004A88
0x180004a7e  lea     rcx, [rsp+1500h+var_14E0]
0x180004a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a88  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004a8f  test    rax, rax
0x180004a92  jz      short loc_180004AA5
0x180004a94  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004a99  jnz     short loc_180004AA5
0x180004a9b  lea     rcx, [rsp+1500h+var_14E0]
0x180004aa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aa5  cmp     [rsp+1500h+var_14D8], r12d
0x180004aaa  jge     loc_180004BB3
0x180004ab0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004ab7  jnz     short loc_180004AD8
0x180004ab9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004ac0  test    rax, rax
0x180004ac3  jz      short loc_180004ACE
0x180004ac5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aca  test    al, al
0x180004acc  jmp     short loc_180004AD6
0x180004ace  call    cs:__imp_IsDebuggerPresent
0x180004ad4  test    eax, eax
0x180004ad6  jz      short loc_180004ADF
0x180004ad8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004add  jz      short loc_180004B05
0x180004adf  mov     rax, cs:g_pfnResultLoggingCallback
0x180004ae6  test    rax, rax
0x180004ae9  jz      short loc_180004B5E
0x180004aeb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004af2  jnz     short loc_180004B5E
0x180004af4  xor     r8d, r8d
0x180004af7  xor     edx, edx
0x180004af9  lea     rcx, [rsp+1500h+var_14E0]
0x180004afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b03  jmp     short loc_180004B5E
0x180004b05  mov     ebx, 800h
0x180004b0a  mov     rax, cs:g_pfnResultLoggingCallback
0x180004b11  test    rax, rax
0x180004b14  jz      short loc_180004B33
0x180004b16  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004b1d  jnz     short loc_180004B33
0x180004b1f  mov     r8d, ebx
0x180004b22  lea     rdx, [rbp+1400h+OutputString]
0x180004b29  lea     rcx, [rsp+1500h+var_14E0]
0x180004b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b33  cmp     [rbp+1400h+OutputString], r12w
0x180004b3b  jnz     short loc_180004B51
0x180004b3d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004b42  mov     rdx, rbx; unsigned __int16 *
0x180004b45  lea     rcx, [rbp+1400h+OutputString]; this
0x180004b4c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004b51  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004b58  call    cs:__imp_OutputDebugStringW
0x180004b5e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004b63  jnz     short loc_180004B6E
0x180004b65  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004b6c  jz      short loc_180004B80
0x180004b6e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004b75  test    rax, rax
0x180004b78  jz      short loc_180004B80
0x180004b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b7f  nop
0x180004b80  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004b85  jnz     short loc_180004BA8
0x180004b87  mov     rcx, [rbp+1400h+var_40]
0x180004b8e  xor     rcx, rsp; StackCookie
0x180004b91  call    __security_check_cookie
0x180004b96  add     rsp, 14D0h
0x180004b9d  pop     r15
0x180004b9f  pop     r14
0x180004ba1  pop     r12
0x180004ba3  pop     rdi
0x180004ba4  pop     rsi
0x180004ba5  pop     rbx
0x180004ba6  pop     rbp
0x180004ba7  retn
0x180004ba8  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004bad  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004bb3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
