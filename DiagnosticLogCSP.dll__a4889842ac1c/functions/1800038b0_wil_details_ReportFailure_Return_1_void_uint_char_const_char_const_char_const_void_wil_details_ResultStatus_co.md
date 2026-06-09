# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800038b0`
- end: `0x180003b3d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003390`

## callees

- `0x180001b60`
- `0x18000262c`
- `0x1800038b0`
- `0x180004a24`
- `0x180005920`
- `0x1800068d0`
- `0x1800069ac`
- `0x180035830`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000395e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000395e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003adc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003adc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003a52`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003a52`

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
0x1800038b0  push    rbp
0x1800038b2  push    rbx
0x1800038b3  push    rsi
0x1800038b4  push    rdi
0x1800038b5  push    r12
0x1800038b7  push    r14
0x1800038b9  push    r15
0x1800038bb  lea     rbp, [rsp-13D0h]
0x1800038c3  mov     eax, 14D0h
0x1800038c8  call    _alloca_probe
0x1800038cd  sub     rsp, rax
0x1800038d0  mov     rax, cs:__security_cookie
0x1800038d7  xor     rax, rsp
0x1800038da  mov     [rbp+1400h+var_40], rax
0x1800038e1  mov     r14, r8
0x1800038e4  mov     esi, edx
0x1800038e6  mov     r15, rcx
0x1800038e9  mov     rdi, [rbp+1400h+arg_28]
0x1800038f0  xor     edx, edx; Val
0x1800038f2  mov     r8d, 98h; Size
0x1800038f8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800038fd  call    memset_0
0x180003902  nop
0x180003903  xor     r12d, r12d
0x180003906  mov     [rbp+1400h+OutputString], r12w
0x18000390e  mov     [rbp+1400h+var_1440], r12b
0x180003912  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180003919  mov     ecx, [rdx]; this
0x18000391b  mov     [rsp+1500h+var_14D8], ecx
0x18000391f  mov     eax, [rdx+4]
0x180003922  mov     [rsp+1500h+var_14D4], eax
0x180003926  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000392b  mov     ebx, eax
0x18000392d  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003935  mov     ecx, r12d
0x180003938  lea     eax, [r12+8]
0x18000393d  cmp     dword ptr [rdx+8], 1
0x180003941  cmovz   ecx, eax
0x180003944  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003948  lea     ecx, [rax-7]
0x18000394b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003953  inc     ecx
0x180003955  mov     [rsp+1500h+var_14D0], ecx
0x180003959  mov     [rsp+1500h+var_14C8], r12
0x18000395e  call    cs:__imp_GetCurrentThreadId
0x180003964  mov     [rsp+1500h+var_14C0], eax
0x180003968  mov     [rsp+1500h+var_14A8], r14
0x18000396d  mov     [rsp+1500h+var_14A0], esi
0x180003971  mov     [rsp+1500h+var_149C], ebx
0x180003975  mov     [rsp+1500h+var_14B8], r12
0x18000397a  mov     [rsp+1500h+var_14B0], r12
0x18000397f  mov     [rbp+1400h+var_1458], rdi
0x180003983  mov     [rbp+1400h+var_1450], r15
0x180003987  mov     [rsp+1500h+var_1498], r12
0x18000398c  xorps   xmm0, xmm0
0x18000398f  xor     eax, eax
0x180003991  movups  [rbp+1400h+var_1478], xmm0
0x180003995  mov     [rbp+1400h+var_1468], rax
0x180003999  xorps   xmm1, xmm1
0x18000399c  movups  [rsp+1500h+var_1490], xmm1
0x1800039a1  mov     [rbp+1400h+var_1480], rax
0x1800039a5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800039ac  test    rax, rax
0x1800039af  jz      short loc_1800039BC
0x1800039b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039b6  mov     [rbp+1400h+var_1460], rax
0x1800039ba  jmp     short loc_1800039C0
0x1800039bc  mov     [rbp+1400h+var_1460], r12
0x1800039c0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800039c7  test    rax, rax
0x1800039ca  jz      short loc_1800039D6
0x1800039cc  lea     rcx, [rsp+1500h+var_14E0]
0x1800039d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039d6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800039dd  test    rax, rax
0x1800039e0  jz      short loc_1800039F6
0x1800039e2  mov     r8d, 400h
0x1800039e8  lea     rdx, [rbp+1400h+var_1440]
0x1800039ec  lea     rcx, [rsp+1500h+var_14E0]
0x1800039f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039f6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800039fd  test    rax, rax
0x180003a00  jz      short loc_180003A0C
0x180003a02  lea     rcx, [rsp+1500h+var_14E0]
0x180003a07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a0c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003a13  test    rax, rax
0x180003a16  jz      short loc_180003A29
0x180003a18  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003a1d  jnz     short loc_180003A29
0x180003a1f  lea     rcx, [rsp+1500h+var_14E0]
0x180003a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a29  cmp     [rsp+1500h+var_14D8], r12d
0x180003a2e  jge     loc_180003B37
0x180003a34  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003a3b  jnz     short loc_180003A5C
0x180003a3d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003a44  test    rax, rax
0x180003a47  jz      short loc_180003A52
0x180003a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a4e  test    al, al
0x180003a50  jmp     short loc_180003A5A
0x180003a52  call    cs:__imp_IsDebuggerPresent
0x180003a58  test    eax, eax
0x180003a5a  jz      short loc_180003A63
0x180003a5c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003a61  jz      short loc_180003A89
0x180003a63  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a6a  test    rax, rax
0x180003a6d  jz      short loc_180003AE2
0x180003a6f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003a76  jnz     short loc_180003AE2
0x180003a78  xor     r8d, r8d
0x180003a7b  xor     edx, edx
0x180003a7d  lea     rcx, [rsp+1500h+var_14E0]
0x180003a82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a87  jmp     short loc_180003AE2
0x180003a89  mov     ebx, 800h
0x180003a8e  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a95  test    rax, rax
0x180003a98  jz      short loc_180003AB7
0x180003a9a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003aa1  jnz     short loc_180003AB7
0x180003aa3  mov     r8d, ebx
0x180003aa6  lea     rdx, [rbp+1400h+OutputString]
0x180003aad  lea     rcx, [rsp+1500h+var_14E0]
0x180003ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ab7  cmp     [rbp+1400h+OutputString], r12w
0x180003abf  jnz     short loc_180003AD5
0x180003ac1  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003ac6  mov     rdx, rbx; unsigned __int16 *
0x180003ac9  lea     rcx, [rbp+1400h+OutputString]; this
0x180003ad0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003ad5  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003adc  call    cs:__imp_OutputDebugStringW
0x180003ae2  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003ae7  jnz     short loc_180003AF2
0x180003ae9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003af0  jz      short loc_180003B04
0x180003af2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003af9  test    rax, rax
0x180003afc  jz      short loc_180003B04
0x180003afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b03  nop
0x180003b04  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003b09  jnz     short loc_180003B2C
0x180003b0b  mov     rcx, [rbp+1400h+var_40]
0x180003b12  xor     rcx, rsp; StackCookie
0x180003b15  call    __security_check_cookie
0x180003b1a  add     rsp, 14D0h
0x180003b21  pop     r15
0x180003b23  pop     r14
0x180003b25  pop     r12
0x180003b27  pop     rdi
0x180003b28  pop     rsi
0x180003b29  pop     rbx
0x180003b2a  pop     rbp
0x180003b2b  retn
0x180003b2c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003b31  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003b37  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
