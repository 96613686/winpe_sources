# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000891c`
- end: `0x180008ba9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800083bc`

## callees

- `0x1800060a0`
- `0x180006ed4`
- `0x18000891c`
- `0x18000bea4`
- `0x18000cfe0`
- `0x18000e2f0`
- `0x18000e58c`
- `0x1800a28a0`
- `0x1800ae010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800089ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800089ca`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008b48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008b48`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008abe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008abe`

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
0x18000891c  push    rbp
0x18000891e  push    rbx
0x18000891f  push    rsi
0x180008920  push    rdi
0x180008921  push    r12
0x180008923  push    r14
0x180008925  push    r15
0x180008927  lea     rbp, [rsp-13D0h]
0x18000892f  mov     eax, 14D0h
0x180008934  call    _alloca_probe
0x180008939  sub     rsp, rax
0x18000893c  mov     rax, cs:__security_cookie
0x180008943  xor     rax, rsp
0x180008946  mov     [rbp+1400h+var_40], rax
0x18000894d  mov     r14, r8
0x180008950  mov     esi, edx
0x180008952  mov     r15, rcx
0x180008955  mov     rdi, [rbp+1400h+arg_28]
0x18000895c  xor     edx, edx; Val
0x18000895e  mov     r8d, 98h; Size
0x180008964  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180008969  call    memset_0
0x18000896e  nop
0x18000896f  xor     r12d, r12d
0x180008972  mov     [rbp+1400h+OutputString], r12w
0x18000897a  mov     [rbp+1400h+var_1440], r12b
0x18000897e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180008985  mov     ecx, [rdx]; this
0x180008987  mov     [rsp+1500h+var_14D8], ecx
0x18000898b  mov     eax, [rdx+4]
0x18000898e  mov     [rsp+1500h+var_14D4], eax
0x180008992  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008997  mov     ebx, eax
0x180008999  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800089a1  mov     ecx, r12d
0x1800089a4  lea     eax, [r12+8]
0x1800089a9  cmp     dword ptr [rdx+8], 1
0x1800089ad  cmovz   ecx, eax
0x1800089b0  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800089b4  lea     ecx, [rax-7]
0x1800089b7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800089bf  inc     ecx
0x1800089c1  mov     [rsp+1500h+var_14D0], ecx
0x1800089c5  mov     [rsp+1500h+var_14C8], r12
0x1800089ca  call    cs:__imp_GetCurrentThreadId
0x1800089d0  mov     [rsp+1500h+var_14C0], eax
0x1800089d4  mov     [rsp+1500h+var_14A8], r14
0x1800089d9  mov     [rsp+1500h+var_14A0], esi
0x1800089dd  mov     [rsp+1500h+var_149C], ebx
0x1800089e1  mov     [rsp+1500h+var_14B8], r12
0x1800089e6  mov     [rsp+1500h+var_14B0], r12
0x1800089eb  mov     [rbp+1400h+var_1458], rdi
0x1800089ef  mov     [rbp+1400h+var_1450], r15
0x1800089f3  mov     [rsp+1500h+var_1498], r12
0x1800089f8  xorps   xmm0, xmm0
0x1800089fb  xor     eax, eax
0x1800089fd  movups  [rbp+1400h+var_1478], xmm0
0x180008a01  mov     [rbp+1400h+var_1468], rax
0x180008a05  xorps   xmm1, xmm1
0x180008a08  movups  [rsp+1500h+var_1490], xmm1
0x180008a0d  mov     [rbp+1400h+var_1480], rax
0x180008a11  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008a18  test    rax, rax
0x180008a1b  jz      short loc_180008A28
0x180008a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a22  mov     [rbp+1400h+var_1460], rax
0x180008a26  jmp     short loc_180008A2C
0x180008a28  mov     [rbp+1400h+var_1460], r12
0x180008a2c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008a33  test    rax, rax
0x180008a36  jz      short loc_180008A42
0x180008a38  lea     rcx, [rsp+1500h+var_14E0]
0x180008a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a42  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008a49  test    rax, rax
0x180008a4c  jz      short loc_180008A62
0x180008a4e  mov     r8d, 400h
0x180008a54  lea     rdx, [rbp+1400h+var_1440]
0x180008a58  lea     rcx, [rsp+1500h+var_14E0]
0x180008a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a62  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008a69  test    rax, rax
0x180008a6c  jz      short loc_180008A78
0x180008a6e  lea     rcx, [rsp+1500h+var_14E0]
0x180008a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a78  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008a7f  test    rax, rax
0x180008a82  jz      short loc_180008A95
0x180008a84  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180008a89  jnz     short loc_180008A95
0x180008a8b  lea     rcx, [rsp+1500h+var_14E0]
0x180008a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a95  cmp     [rsp+1500h+var_14D8], r12d
0x180008a9a  jge     loc_180008BA3
0x180008aa0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180008aa7  jnz     short loc_180008AC8
0x180008aa9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008ab0  test    rax, rax
0x180008ab3  jz      short loc_180008ABE
0x180008ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aba  test    al, al
0x180008abc  jmp     short loc_180008AC6
0x180008abe  call    cs:__imp_IsDebuggerPresent
0x180008ac4  test    eax, eax
0x180008ac6  jz      short loc_180008ACF
0x180008ac8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180008acd  jz      short loc_180008AF5
0x180008acf  mov     rax, cs:g_pfnResultLoggingCallback
0x180008ad6  test    rax, rax
0x180008ad9  jz      short loc_180008B4E
0x180008adb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180008ae2  jnz     short loc_180008B4E
0x180008ae4  xor     r8d, r8d
0x180008ae7  xor     edx, edx
0x180008ae9  lea     rcx, [rsp+1500h+var_14E0]
0x180008aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008af3  jmp     short loc_180008B4E
0x180008af5  mov     ebx, 800h
0x180008afa  mov     rax, cs:g_pfnResultLoggingCallback
0x180008b01  test    rax, rax
0x180008b04  jz      short loc_180008B23
0x180008b06  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180008b0d  jnz     short loc_180008B23
0x180008b0f  mov     r8d, ebx
0x180008b12  lea     rdx, [rbp+1400h+OutputString]
0x180008b19  lea     rcx, [rsp+1500h+var_14E0]
0x180008b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b23  cmp     [rbp+1400h+OutputString], r12w
0x180008b2b  jnz     short loc_180008B41
0x180008b2d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180008b32  mov     rdx, rbx; unsigned __int16 *
0x180008b35  lea     rcx, [rbp+1400h+OutputString]; this
0x180008b3c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008b41  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180008b48  call    cs:__imp_OutputDebugStringW
0x180008b4e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180008b53  jnz     short loc_180008B5E
0x180008b55  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180008b5c  jz      short loc_180008B70
0x180008b5e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008b65  test    rax, rax
0x180008b68  jz      short loc_180008B70
0x180008b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b6f  nop
0x180008b70  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180008b75  jnz     short loc_180008B98
0x180008b77  mov     rcx, [rbp+1400h+var_40]
0x180008b7e  xor     rcx, rsp; StackCookie
0x180008b81  call    __security_check_cookie
0x180008b86  add     rsp, 14D0h
0x180008b8d  pop     r15
0x180008b8f  pop     r14
0x180008b91  pop     r12
0x180008b93  pop     rdi
0x180008b94  pop     rsi
0x180008b95  pop     rbx
0x180008b96  pop     rbp
0x180008b97  retn
0x180008b98  lea     rcx, [rsp+1500h+var_14E0]; this
0x180008b9d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180008ba3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
