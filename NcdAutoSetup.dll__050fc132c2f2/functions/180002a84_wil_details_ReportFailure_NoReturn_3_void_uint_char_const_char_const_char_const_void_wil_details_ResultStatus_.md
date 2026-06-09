# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002a84`
- end: `0x180002ce4`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002828`

## callees

- `0x180002a84`
- `0x180004e44`
- `0x1800055dc`
- `0x180006400`
- `0x180008aa0`
- `0x18001380e`
- `0x1800138d0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b25`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b25`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002cb2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002cb2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002c28`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002c28`

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
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
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
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
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
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x180002a84  mov     [rsp-8+arg_18], rbx
0x180002a89  push    rbp
0x180002a8a  push    rsi
0x180002a8b  push    rdi
0x180002a8c  push    r12
0x180002a8e  push    r13
0x180002a90  push    r14
0x180002a92  push    r15
0x180002a94  lea     rbp, [rsp-13C0h]
0x180002a9c  mov     eax, 14C0h
0x180002aa1  call    _alloca_probe
0x180002aa6  sub     rsp, rax
0x180002aa9  mov     rsi, [rbp+13F0h+arg_28]
0x180002ab0  mov     r15, r8
0x180002ab3  mov     r14d, edx
0x180002ab6  mov     r12, rcx
0x180002ab9  xor     edx, edx; Val
0x180002abb  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002ac0  mov     r8d, 98h; Size
0x180002ac6  call    memset_0
0x180002acb  mov     rbx, [rbp+13F0h+arg_30]
0x180002ad2  xor     r13d, r13d
0x180002ad5  mov     [rbp+13F0h+OutputString], r13w
0x180002add  mov     [rbp+13F0h+var_1430], r13b
0x180002ae1  mov     ecx, [rbx]; this
0x180002ae3  mov     eax, [rbx+4]
0x180002ae6  mov     [rsp+14F0h+var_14C8], ecx
0x180002aea  mov     [rsp+14F0h+var_14C4], eax
0x180002aee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002af3  cmp     dword ptr [rbx+8], 1
0x180002af7  mov     edi, eax
0x180002af9  lea     eax, [r13+8]
0x180002afd  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002b05  mov     ecx, r13d
0x180002b08  cmovz   ecx, eax
0x180002b0b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002b0f  lea     ecx, [rax-7]
0x180002b12  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002b1a  inc     ecx
0x180002b1c  mov     [rsp+14F0h+var_14B8], r13
0x180002b21  mov     [rsp+14F0h+var_14C0], ecx
0x180002b25  call    cs:__imp_GetCurrentThreadId
0x180002b2b  xorps   xmm0, xmm0
0x180002b2e  mov     [rsp+14F0h+var_1498], r15
0x180002b33  mov     [rsp+14F0h+var_14B0], eax
0x180002b37  xorps   xmm1, xmm1
0x180002b3a  xor     eax, eax
0x180002b3c  mov     [rsp+14F0h+var_1490], r14d
0x180002b41  mov     [rbp+13F0h+var_1458], rax
0x180002b45  mov     [rbp+13F0h+var_1470], rax
0x180002b49  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002b50  mov     [rsp+14F0h+var_148C], edi
0x180002b54  mov     [rsp+14F0h+var_14A8], r13
0x180002b59  mov     [rsp+14F0h+var_14A0], r13
0x180002b5e  mov     [rbp+13F0h+var_1448], rsi
0x180002b62  mov     [rbp+13F0h+var_1440], r12
0x180002b66  mov     [rsp+14F0h+var_1488], r13
0x180002b6b  movups  [rbp+13F0h+var_1468], xmm0
0x180002b6f  movups  [rsp+14F0h+var_1480], xmm1
0x180002b74  test    rax, rax
0x180002b77  jz      short loc_180002B84
0x180002b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b7e  mov     [rbp+13F0h+var_1450], rax
0x180002b82  jmp     short loc_180002B88
0x180002b84  mov     [rbp+13F0h+var_1450], r13
0x180002b88  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002b8f  test    rax, rax
0x180002b92  jz      short loc_180002B9E
0x180002b94  lea     rcx, [rsp+14F0h+var_14D0]
0x180002b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b9e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002ba5  test    rax, rax
0x180002ba8  jz      short loc_180002BBE
0x180002baa  mov     r8d, 400h
0x180002bb0  lea     rdx, [rbp+13F0h+var_1430]
0x180002bb4  lea     rcx, [rsp+14F0h+var_14D0]
0x180002bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bbe  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002bc5  test    rax, rax
0x180002bc8  jz      short loc_180002BD4
0x180002bca  lea     rcx, [rsp+14F0h+var_14D0]
0x180002bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bd4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002bdb  test    rax, rax
0x180002bde  jz      short loc_180002BF1
0x180002be0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002be5  jnz     short loc_180002BF1
0x180002be7  lea     rcx, [rsp+14F0h+var_14D0]
0x180002bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf1  cmp     [rsp+14F0h+var_14C8], r13d
0x180002bf6  jl      short loc_180002C0A
0x180002bf8  mov     ecx, 8000FFFFh; this
0x180002bfd  mov     [rsp+14F0h+var_14C8], ecx
0x180002c01  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002c06  mov     [rsp+14F0h+var_14C4], eax
0x180002c0a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002c11  jnz     short loc_180002C32
0x180002c13  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002c1a  test    rax, rax
0x180002c1d  jz      short loc_180002C28
0x180002c1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c24  test    al, al
0x180002c26  jmp     short loc_180002C30
0x180002c28  call    cs:__imp_IsDebuggerPresent
0x180002c2e  test    eax, eax
0x180002c30  jz      short loc_180002C39
0x180002c32  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002c37  jz      short loc_180002C5F
0x180002c39  mov     rax, cs:g_pfnResultLoggingCallback
0x180002c40  test    rax, rax
0x180002c43  jz      short loc_180002CB8
0x180002c45  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002c4c  jnz     short loc_180002CB8
0x180002c4e  xor     r8d, r8d
0x180002c51  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c56  xor     edx, edx
0x180002c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c5d  jmp     short loc_180002CB8
0x180002c5f  mov     rax, cs:g_pfnResultLoggingCallback
0x180002c66  mov     ebx, 800h
0x180002c6b  test    rax, rax
0x180002c6e  jz      short loc_180002C8D
0x180002c70  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002c77  jnz     short loc_180002C8D
0x180002c79  mov     r8d, ebx
0x180002c7c  lea     rdx, [rbp+13F0h+OutputString]
0x180002c83  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c8d  cmp     [rbp+13F0h+OutputString], r13w
0x180002c95  jnz     short loc_180002CAB
0x180002c97  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002c9c  mov     rdx, rbx; unsigned __int16 *
0x180002c9f  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002ca6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002cab  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002cb2  call    cs:__imp_OutputDebugStringW
0x180002cb8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002cbd  jnz     short loc_180002CC8
0x180002cbf  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002cc6  jz      short loc_180002CD9
0x180002cc8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002ccf  test    rax, rax
0x180002cd2  jz      short loc_180002CD9
0x180002cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cd9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002cde  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
