# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004968`
- end: `0x180004bd6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `622`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004620`

## callees

- `0x1800030b6`
- `0x180004968`
- `0x180006f94`
- `0x180007b94`
- `0x180009078`
- `0x18000b108`
- `0x18000b444`
- `0x180076c50`
- `0x180076d10`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a16`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a16`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004b4f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004b4f`

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
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
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
    ModuleName = wil::details::g_pfnGetModuleName(v13);
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::details::IsDebuggerPresent(v13) || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v17, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v14);
}

```

## disassembly

```asm
0x180004968  push    rbp
0x18000496a  push    rbx
0x18000496b  push    rsi
0x18000496c  push    rdi
0x18000496d  push    r12
0x18000496f  push    r14
0x180004971  push    r15
0x180004973  lea     rbp, [rsp-13D0h]
0x18000497b  mov     eax, 14D0h
0x180004980  call    _alloca_probe
0x180004985  sub     rsp, rax
0x180004988  mov     rax, cs:__security_cookie
0x18000498f  xor     rax, rsp
0x180004992  mov     [rbp+1400h+var_40], rax
0x180004999  mov     r14, r8
0x18000499c  mov     esi, edx
0x18000499e  mov     r15, rcx
0x1800049a1  mov     rdi, [rbp+1400h+arg_28]
0x1800049a8  xor     edx, edx; Val
0x1800049aa  mov     r8d, 98h; Size
0x1800049b0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800049b5  call    memset_0
0x1800049ba  nop
0x1800049bb  xor     r12d, r12d
0x1800049be  mov     [rbp+1400h+OutputString], r12w
0x1800049c6  mov     [rbp+1400h+var_1440], r12b
0x1800049ca  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800049d1  mov     ecx, [rdx]; this
0x1800049d3  mov     [rsp+1500h+var_14D8], ecx
0x1800049d7  mov     eax, [rdx+4]
0x1800049da  mov     [rsp+1500h+var_14D4], eax
0x1800049de  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800049e3  mov     ebx, eax
0x1800049e5  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800049ed  mov     ecx, r12d
0x1800049f0  lea     eax, [r12+8]
0x1800049f5  cmp     dword ptr [rdx+8], 1
0x1800049f9  cmovz   ecx, eax
0x1800049fc  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004a00  lea     ecx, [rax-7]
0x180004a03  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004a0b  inc     ecx
0x180004a0d  mov     [rsp+1500h+var_14D0], ecx
0x180004a11  mov     [rsp+1500h+var_14C8], r12
0x180004a16  call    cs:__imp_GetCurrentThreadId
0x180004a1c  mov     [rsp+1500h+var_14C0], eax
0x180004a20  mov     [rsp+1500h+var_14A8], r14
0x180004a25  mov     [rsp+1500h+var_14A0], esi
0x180004a29  mov     [rsp+1500h+var_149C], ebx
0x180004a2d  mov     [rsp+1500h+var_14B8], r12
0x180004a32  mov     [rsp+1500h+var_14B0], r12
0x180004a37  mov     [rbp+1400h+var_1458], rdi
0x180004a3b  mov     [rbp+1400h+var_1450], r15
0x180004a3f  mov     [rsp+1500h+var_1498], r12
0x180004a44  xorps   xmm0, xmm0
0x180004a47  xor     eax, eax
0x180004a49  movups  [rbp+1400h+var_1478], xmm0
0x180004a4d  mov     [rbp+1400h+var_1468], rax
0x180004a51  xorps   xmm1, xmm1
0x180004a54  movups  [rsp+1500h+var_1490], xmm1
0x180004a59  mov     [rbp+1400h+var_1480], rax
0x180004a5d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004a64  test    rax, rax
0x180004a67  jz      short loc_180004A74
0x180004a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a6e  mov     [rbp+1400h+var_1460], rax
0x180004a72  jmp     short loc_180004A78
0x180004a74  mov     [rbp+1400h+var_1460], r12
0x180004a78  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004a7f  test    rax, rax
0x180004a82  jz      short loc_180004A8E
0x180004a84  lea     rcx, [rsp+1500h+var_14E0]
0x180004a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a8e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004a95  test    rax, rax
0x180004a98  jz      short loc_180004AAE
0x180004a9a  mov     r8d, 400h
0x180004aa0  lea     rdx, [rbp+1400h+var_1440]
0x180004aa4  lea     rcx, [rsp+1500h+var_14E0]
0x180004aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aae  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004ab5  test    rax, rax
0x180004ab8  jz      short loc_180004AC4
0x180004aba  lea     rcx, [rsp+1500h+var_14E0]
0x180004abf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ac4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004acb  test    rax, rax
0x180004ace  jz      short loc_180004AE1
0x180004ad0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004ad5  jnz     short loc_180004AE1
0x180004ad7  lea     rcx, [rsp+1500h+var_14E0]
0x180004adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ae1  cmp     [rsp+1500h+var_14D8], r12d
0x180004ae6  jge     loc_180004BD0
0x180004aec  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x180004af1  test    al, al
0x180004af3  jz      short loc_180004B57
0x180004af5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004afa  jnz     short loc_180004B57
0x180004afc  mov     ebx, 800h
0x180004b01  mov     rax, cs:g_pfnResultLoggingCallback
0x180004b08  test    rax, rax
0x180004b0b  jz      short loc_180004B2A
0x180004b0d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004b14  jnz     short loc_180004B2A
0x180004b16  mov     r8d, ebx
0x180004b19  lea     rdx, [rbp+1400h+OutputString]
0x180004b20  lea     rcx, [rsp+1500h+var_14E0]
0x180004b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b2a  cmp     [rbp+1400h+OutputString], r12w
0x180004b32  jnz     short loc_180004B48
0x180004b34  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004b39  mov     rdx, rbx; wchar_t *
0x180004b3c  lea     rcx, [rbp+1400h+OutputString]; this
0x180004b43  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180004b48  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004b4f  call    cs:__imp_OutputDebugStringW
0x180004b55  jmp     short loc_180004B7B
0x180004b57  mov     rax, cs:g_pfnResultLoggingCallback
0x180004b5e  test    rax, rax
0x180004b61  jz      short loc_180004B7B
0x180004b63  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004b6a  jnz     short loc_180004B7B
0x180004b6c  xor     r8d, r8d
0x180004b6f  xor     edx, edx
0x180004b71  lea     rcx, [rsp+1500h+var_14E0]
0x180004b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b7b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004b80  jnz     short loc_180004B8B
0x180004b82  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004b89  jz      short loc_180004B9D
0x180004b8b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004b92  test    rax, rax
0x180004b95  jz      short loc_180004B9D
0x180004b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b9c  nop
0x180004b9d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004ba2  jnz     short loc_180004BC5
0x180004ba4  mov     rcx, [rbp+1400h+var_40]
0x180004bab  xor     rcx, rsp; StackCookie
0x180004bae  call    __security_check_cookie
0x180004bb3  add     rsp, 14D0h
0x180004bba  pop     r15
0x180004bbc  pop     r14
0x180004bbe  pop     r12
0x180004bc0  pop     rdi
0x180004bc1  pop     rsi
0x180004bc2  pop     rbx
0x180004bc3  pop     rbp
0x180004bc4  retn
0x180004bc5  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004bca  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004bd0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
