# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180004b10`
- end: `0x180004d89`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004880`

## callees

- `0x1800046a0`
- `0x180004b10`
- `0x180007144`
- `0x1800078e4`
- `0x1800085f0`
- `0x18000a830`
- `0x18001f830`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004bc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004bc9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004ccc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004ccc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004d56`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004d56`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
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
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180004b10  mov     [rsp-8+arg_18], rbx
0x180004b15  push    rbp
0x180004b16  push    rsi
0x180004b17  push    rdi
0x180004b18  push    r12
0x180004b1a  push    r13
0x180004b1c  push    r14
0x180004b1e  push    r15
0x180004b20  lea     rbp, [rsp-13C0h]
0x180004b28  mov     eax, 14C0h
0x180004b2d  call    _alloca_probe
0x180004b32  sub     rsp, rax
0x180004b35  mov     r14, r8
0x180004b38  mov     esi, edx
0x180004b3a  mov     rdi, rcx
0x180004b3d  mov     r15, [rbp+13F0h+arg_28]
0x180004b44  xor     edx, edx; Val
0x180004b46  mov     r8d, 98h; Size
0x180004b4c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004b51  call    memset_0
0x180004b56  nop
0x180004b57  xor     r13d, r13d
0x180004b5a  mov     [rbp+13F0h+OutputString], r13w
0x180004b62  mov     [rbp+13F0h+var_1430], r13b
0x180004b66  mov     rbx, [rbp+13F0h+arg_30]
0x180004b6d  mov     ecx, [rbx]; this
0x180004b6f  mov     [rsp+14F0h+var_14C8], ecx
0x180004b73  mov     eax, [rbx+4]
0x180004b76  mov     [rsp+14F0h+var_14C4], eax
0x180004b7a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004b7f  mov     r12d, eax
0x180004b82  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180004b8a  mov     ecx, r13d
0x180004b8d  lea     eax, [r13+8]
0x180004b91  cmp     dword ptr [rbx+8], 1
0x180004b95  cmovz   ecx, eax
0x180004b98  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004b9c  lea     ecx, [rax-7]
0x180004b9f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004ba7  inc     ecx
0x180004ba9  mov     [rsp+14F0h+var_14C0], ecx
0x180004bad  mov     rcx, [rbp+13F0h+arg_38]
0x180004bb4  test    rcx, rcx
0x180004bb7  jz      short loc_180004BC4
0x180004bb9  cmp     [rcx], r13w
0x180004bbd  mov     [rsp+14F0h+var_14B8], rcx
0x180004bc2  jnz     short loc_180004BC9
0x180004bc4  mov     [rsp+14F0h+var_14B8], r13
0x180004bc9  call    cs:__imp_GetCurrentThreadId
0x180004bcf  mov     [rsp+14F0h+var_14B0], eax
0x180004bd3  mov     [rsp+14F0h+var_1498], r14
0x180004bd8  mov     [rsp+14F0h+var_1490], esi
0x180004bdc  mov     [rsp+14F0h+var_148C], r12d
0x180004be1  mov     [rsp+14F0h+var_14A8], r13
0x180004be6  mov     [rsp+14F0h+var_14A0], r13
0x180004beb  mov     [rbp+13F0h+var_1448], r15
0x180004bef  mov     [rbp+13F0h+var_1440], rdi
0x180004bf3  mov     [rsp+14F0h+var_1488], r13
0x180004bf8  xorps   xmm0, xmm0
0x180004bfb  xor     eax, eax
0x180004bfd  movups  [rbp+13F0h+var_1468], xmm0
0x180004c01  mov     [rbp+13F0h+var_1458], rax
0x180004c05  xorps   xmm1, xmm1
0x180004c08  movups  [rsp+14F0h+var_1480], xmm1
0x180004c0d  mov     [rbp+13F0h+var_1470], rax
0x180004c11  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004c18  test    rax, rax
0x180004c1b  jz      short loc_180004C28
0x180004c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c22  mov     [rbp+13F0h+var_1450], rax
0x180004c26  jmp     short loc_180004C2C
0x180004c28  mov     [rbp+13F0h+var_1450], r13
0x180004c2c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004c33  test    rax, rax
0x180004c36  jz      short loc_180004C42
0x180004c38  lea     rcx, [rsp+14F0h+var_14D0]
0x180004c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c42  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004c49  test    rax, rax
0x180004c4c  jz      short loc_180004C62
0x180004c4e  mov     r8d, 400h
0x180004c54  lea     rdx, [rbp+13F0h+var_1430]
0x180004c58  lea     rcx, [rsp+14F0h+var_14D0]
0x180004c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c62  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004c69  test    rax, rax
0x180004c6c  jz      short loc_180004C78
0x180004c6e  lea     rcx, [rsp+14F0h+var_14D0]
0x180004c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c78  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004c7f  test    rax, rax
0x180004c82  jz      short loc_180004C95
0x180004c84  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004c89  jnz     short loc_180004C95
0x180004c8b  lea     rcx, [rsp+14F0h+var_14D0]
0x180004c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c95  cmp     [rsp+14F0h+var_14C8], r13d
0x180004c9a  jl      short loc_180004CAE
0x180004c9c  mov     ecx, 8000FFFFh; this
0x180004ca1  mov     [rsp+14F0h+var_14C8], ecx
0x180004ca5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004caa  mov     [rsp+14F0h+var_14C4], eax
0x180004cae  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180004cb5  jnz     short loc_180004CD6
0x180004cb7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004cbe  test    rax, rax
0x180004cc1  jz      short loc_180004CCC
0x180004cc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc8  test    al, al
0x180004cca  jmp     short loc_180004CD4
0x180004ccc  call    cs:__imp_IsDebuggerPresent
0x180004cd2  test    eax, eax
0x180004cd4  jz      short loc_180004CDD
0x180004cd6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004cdb  jz      short loc_180004D03
0x180004cdd  mov     rax, cs:g_pfnResultLoggingCallback
0x180004ce4  test    rax, rax
0x180004ce7  jz      short loc_180004D5C
0x180004ce9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004cf0  jnz     short loc_180004D5C
0x180004cf2  xor     r8d, r8d
0x180004cf5  xor     edx, edx
0x180004cf7  lea     rcx, [rsp+14F0h+var_14D0]
0x180004cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d01  jmp     short loc_180004D5C
0x180004d03  mov     ebx, 800h
0x180004d08  mov     rax, cs:g_pfnResultLoggingCallback
0x180004d0f  test    rax, rax
0x180004d12  jz      short loc_180004D31
0x180004d14  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004d1b  jnz     short loc_180004D31
0x180004d1d  mov     r8d, ebx
0x180004d20  lea     rdx, [rbp+13F0h+OutputString]
0x180004d27  lea     rcx, [rsp+14F0h+var_14D0]
0x180004d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d31  cmp     [rbp+13F0h+OutputString], r13w
0x180004d39  jnz     short loc_180004D4F
0x180004d3b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180004d40  mov     rdx, rbx; unsigned __int16 *
0x180004d43  lea     rcx, [rbp+13F0h+OutputString]; this
0x180004d4a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004d4f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180004d56  call    cs:__imp_OutputDebugStringW
0x180004d5c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180004d61  jnz     short loc_180004D6C
0x180004d63  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180004d6a  jz      short loc_180004D7E
0x180004d6c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004d73  test    rax, rax
0x180004d76  jz      short loc_180004D7E
0x180004d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d7d  nop
0x180004d7e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004d83  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
