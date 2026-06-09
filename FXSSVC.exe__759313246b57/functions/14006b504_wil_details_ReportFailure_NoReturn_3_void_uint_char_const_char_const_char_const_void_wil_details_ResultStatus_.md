# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x14006b504`
- end: `0x14006b778`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `628`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14006b2a0`

## callees

- `0x140002c73`
- `0x14006b504`
- `0x14006d754`
- `0x14006df60`
- `0x14006eea0`
- `0x1400712cc`
- `0x140086f80`
- `0x14008b010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14006b6af`
- `KERNEL32!IsDebuggerPresent` at `0x14006b6af`
- `KERNEL32!OutputDebugStringW` at `0x14006b73f`
- `KERNEL32!OutputDebugStringW` at `0x14006b73f`
- `KERNEL32!GetCurrentThreadId` at `0x14006b5a6`
- `KERNEL32!GetCurrentThreadId` at `0x14006b5a6`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
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
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
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
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x14006b504  mov     [rsp-8+arg_18], rbx
0x14006b509  push    rbp
0x14006b50a  push    rsi
0x14006b50b  push    rdi
0x14006b50c  push    r12
0x14006b50e  push    r13
0x14006b510  push    r14
0x14006b512  push    r15
0x14006b514  lea     rbp, [rsp-13C0h]
0x14006b51c  mov     eax, 14C0h
0x14006b521  call    _alloca_probe
0x14006b526  sub     rsp, rax
0x14006b529  mov     r15, r8
0x14006b52c  mov     r14d, edx
0x14006b52f  mov     r12, rcx
0x14006b532  mov     rsi, [rbp+13F0h+arg_28]
0x14006b539  xor     edx, edx; Val
0x14006b53b  mov     r8d, 98h; Size
0x14006b541  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14006b546  call    memset_0
0x14006b54b  nop
0x14006b54c  xor     r13d, r13d
0x14006b54f  mov     [rbp+13F0h+OutputString], r13w
0x14006b557  mov     [rbp+13F0h+var_1430], r13b
0x14006b55b  mov     rbx, [rbp+13F0h+arg_30]
0x14006b562  mov     ecx, [rbx]; this
0x14006b564  mov     [rsp+14F0h+var_14C8], ecx
0x14006b568  mov     eax, [rbx+4]
0x14006b56b  mov     [rsp+14F0h+var_14C4], eax
0x14006b56f  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14006b574  mov     edi, eax
0x14006b576  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x14006b57e  mov     ecx, r13d
0x14006b581  lea     eax, [r13+8]
0x14006b585  cmp     dword ptr [rbx+8], 1
0x14006b589  cmovz   ecx, eax
0x14006b58c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14006b590  lea     ecx, [rax-7]
0x14006b593  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14006b59b  inc     ecx
0x14006b59d  mov     [rsp+14F0h+var_14C0], ecx
0x14006b5a1  mov     [rsp+14F0h+var_14B8], r13
0x14006b5a6  call    cs:__imp_GetCurrentThreadId
0x14006b5ad  nop     dword ptr [rax+rax+00h]
0x14006b5b2  mov     [rsp+14F0h+var_14B0], eax
0x14006b5b6  mov     [rsp+14F0h+var_1498], r15
0x14006b5bb  mov     [rsp+14F0h+var_1490], r14d
0x14006b5c0  mov     [rsp+14F0h+var_148C], edi
0x14006b5c4  mov     [rsp+14F0h+var_14A8], r13
0x14006b5c9  mov     [rsp+14F0h+var_14A0], r13
0x14006b5ce  mov     [rbp+13F0h+var_1448], rsi
0x14006b5d2  mov     [rbp+13F0h+var_1440], r12
0x14006b5d6  mov     [rsp+14F0h+var_1488], r13
0x14006b5db  xorps   xmm0, xmm0
0x14006b5de  xor     eax, eax
0x14006b5e0  movups  [rbp+13F0h+var_1468], xmm0
0x14006b5e4  mov     [rbp+13F0h+var_1458], rax
0x14006b5e8  xorps   xmm1, xmm1
0x14006b5eb  movups  [rsp+14F0h+var_1480], xmm1
0x14006b5f0  mov     [rbp+13F0h+var_1470], rax
0x14006b5f4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14006b5fb  test    rax, rax
0x14006b5fe  jz      short loc_14006B60B
0x14006b600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b605  mov     [rbp+13F0h+var_1450], rax
0x14006b609  jmp     short loc_14006B60F
0x14006b60b  mov     [rbp+13F0h+var_1450], r13
0x14006b60f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14006b616  test    rax, rax
0x14006b619  jz      short loc_14006B625
0x14006b61b  lea     rcx, [rsp+14F0h+var_14D0]
0x14006b620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b625  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14006b62c  test    rax, rax
0x14006b62f  jz      short loc_14006B645
0x14006b631  mov     r8d, 400h
0x14006b637  lea     rdx, [rbp+13F0h+var_1430]
0x14006b63b  lea     rcx, [rsp+14F0h+var_14D0]
0x14006b640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b645  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14006b64c  test    rax, rax
0x14006b64f  jz      short loc_14006B65B
0x14006b651  lea     rcx, [rsp+14F0h+var_14D0]
0x14006b656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b65b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14006b662  test    rax, rax
0x14006b665  jz      short loc_14006B678
0x14006b667  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14006b66c  jnz     short loc_14006B678
0x14006b66e  lea     rcx, [rsp+14F0h+var_14D0]
0x14006b673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b678  cmp     [rsp+14F0h+var_14C8], r13d
0x14006b67d  jl      short loc_14006B691
0x14006b67f  mov     ecx, 8000FFFFh; this
0x14006b684  mov     [rsp+14F0h+var_14C8], ecx
0x14006b688  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14006b68d  mov     [rsp+14F0h+var_14C4], eax
0x14006b691  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x14006b698  jnz     short loc_14006B6BF
0x14006b69a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14006b6a1  test    rax, rax
0x14006b6a4  jz      short loc_14006B6AF
0x14006b6a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b6ab  test    al, al
0x14006b6ad  jmp     short loc_14006B6BD
0x14006b6af  call    cs:__imp_IsDebuggerPresent
0x14006b6b6  nop     dword ptr [rax+rax+00h]
0x14006b6bb  test    eax, eax
0x14006b6bd  jz      short loc_14006B6C6
0x14006b6bf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14006b6c4  jz      short loc_14006B6EC
0x14006b6c6  mov     rax, cs:g_pfnResultLoggingCallback
0x14006b6cd  test    rax, rax
0x14006b6d0  jz      short loc_14006B74B
0x14006b6d2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14006b6d9  jnz     short loc_14006B74B
0x14006b6db  xor     r8d, r8d
0x14006b6de  xor     edx, edx
0x14006b6e0  lea     rcx, [rsp+14F0h+var_14D0]
0x14006b6e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b6ea  jmp     short loc_14006B74B
0x14006b6ec  mov     ebx, 800h
0x14006b6f1  mov     rax, cs:g_pfnResultLoggingCallback
0x14006b6f8  test    rax, rax
0x14006b6fb  jz      short loc_14006B71A
0x14006b6fd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14006b704  jnz     short loc_14006B71A
0x14006b706  mov     r8d, ebx
0x14006b709  lea     rdx, [rbp+13F0h+OutputString]
0x14006b710  lea     rcx, [rsp+14F0h+var_14D0]
0x14006b715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b71a  cmp     [rbp+13F0h+OutputString], r13w
0x14006b722  jnz     short loc_14006B738
0x14006b724  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14006b729  mov     rdx, rbx; unsigned __int16 *
0x14006b72c  lea     rcx, [rbp+13F0h+OutputString]; this
0x14006b733  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14006b738  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14006b73f  call    cs:__imp_OutputDebugStringW
0x14006b746  nop     dword ptr [rax+rax+00h]
0x14006b74b  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14006b750  jnz     short loc_14006B75B
0x14006b752  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14006b759  jz      short loc_14006B76D
0x14006b75b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14006b762  test    rax, rax
0x14006b765  jz      short loc_14006B76D
0x14006b767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006b76c  nop
0x14006b76d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14006b772  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
