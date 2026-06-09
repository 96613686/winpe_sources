# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000e77c`
- end: `0x18000ea28`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000e5a0`

## callees

- `0x180003d14`
- `0x1800076e4`
- `0x180008ecc`
- `0x180009fc8`
- `0x18000a4f0`
- `0x18000a8dc`
- `0x18000e77c`
- `0x180028fe0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e825`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e825`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e920`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e920`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e9bc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e9bc`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
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

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x18000e77c  mov     [rsp-8+arg_18], rbx
0x18000e781  push    rbp
0x18000e782  push    rsi
0x18000e783  push    rdi
0x18000e784  push    r12
0x18000e786  push    r13
0x18000e788  push    r14
0x18000e78a  push    r15
0x18000e78c  lea     rbp, [rsp-13C0h]
0x18000e794  mov     eax, 14C0h
0x18000e799  call    _alloca_probe
0x18000e79e  sub     rsp, rax
0x18000e7a1  mov     r14, r8
0x18000e7a4  mov     esi, edx
0x18000e7a6  mov     r15, rcx
0x18000e7a9  mov     rdi, [rbp+13F0h+arg_28]
0x18000e7b0  xor     r13d, r13d
0x18000e7b3  cmp     cs:g_pfnThrowPlatformException, r13
0x18000e7ba  setnz   r12b
0x18000e7be  xor     edx, edx; Val
0x18000e7c0  mov     r8d, 98h; Size
0x18000e7c6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000e7cb  call    memset_0
0x18000e7d0  nop
0x18000e7d1  mov     [rbp+13F0h+OutputString], r13w
0x18000e7d9  mov     [rbp+13F0h+var_1430], r13b
0x18000e7dd  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000e7e4  mov     ecx, [rdx]; this
0x18000e7e6  mov     [rsp+14F0h+var_14C8], ecx
0x18000e7ea  mov     eax, [rdx+4]
0x18000e7ed  mov     [rsp+14F0h+var_14C4], eax
0x18000e7f1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000e7f6  mov     ebx, eax
0x18000e7f8  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000e7fd  mov     ecx, r13d
0x18000e800  lea     eax, [r13+8]
0x18000e804  cmp     dword ptr [rdx+8], 1
0x18000e808  cmovz   ecx, eax
0x18000e80b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000e80f  lea     ecx, [rax-7]
0x18000e812  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000e81a  inc     ecx
0x18000e81c  mov     [rsp+14F0h+var_14C0], ecx
0x18000e820  mov     [rsp+14F0h+var_14B8], r13
0x18000e825  call    cs:__imp_GetCurrentThreadId
0x18000e82b  mov     [rsp+14F0h+var_14B0], eax
0x18000e82f  mov     [rsp+14F0h+var_1498], r14
0x18000e834  mov     [rsp+14F0h+var_1490], esi
0x18000e838  mov     [rsp+14F0h+var_148C], ebx
0x18000e83c  mov     [rsp+14F0h+var_14A8], r13
0x18000e841  mov     [rsp+14F0h+var_14A0], r13
0x18000e846  mov     [rbp+13F0h+var_1448], rdi
0x18000e84a  mov     [rbp+13F0h+var_1440], r15
0x18000e84e  mov     [rsp+14F0h+var_1488], r13
0x18000e853  xorps   xmm0, xmm0
0x18000e856  xor     eax, eax
0x18000e858  movups  [rbp+13F0h+var_1468], xmm0
0x18000e85c  mov     [rbp+13F0h+var_1458], rax
0x18000e860  xorps   xmm1, xmm1
0x18000e863  movups  [rsp+14F0h+var_1480], xmm1
0x18000e868  mov     [rbp+13F0h+var_1470], rax
0x18000e86c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000e873  test    rax, rax
0x18000e876  jz      short loc_18000E883
0x18000e878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e87d  mov     [rbp+13F0h+var_1450], rax
0x18000e881  jmp     short loc_18000E887
0x18000e883  mov     [rbp+13F0h+var_1450], r13
0x18000e887  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e88e  test    rax, rax
0x18000e891  jz      short loc_18000E89D
0x18000e893  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e89d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e8a4  test    rax, rax
0x18000e8a7  jz      short loc_18000E8BD
0x18000e8a9  mov     r8d, 400h
0x18000e8af  lea     rdx, [rbp+13F0h+var_1430]
0x18000e8b3  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e8b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8bd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e8c4  test    rax, rax
0x18000e8c7  jz      short loc_18000E8D3
0x18000e8c9  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8d3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e8da  test    rax, rax
0x18000e8dd  jz      short loc_18000E8F5
0x18000e8df  test    r12b, r12b
0x18000e8e2  jnz     short loc_18000E8F5
0x18000e8e4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000e8e9  jnz     short loc_18000E8F5
0x18000e8eb  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e8f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8f5  cmp     [rsp+14F0h+var_14C8], r13d
0x18000e8fa  jl      short loc_18000E902
0x18000e8fc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000e902  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000e909  jnz     short loc_18000E92A
0x18000e90b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e912  test    rax, rax
0x18000e915  jz      short loc_18000E920
0x18000e917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e91c  test    al, al
0x18000e91e  jmp     short loc_18000E928
0x18000e920  call    cs:__imp_IsDebuggerPresent
0x18000e926  test    eax, eax
0x18000e928  jz      short loc_18000E933
0x18000e92a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000e92f  mov     bl, 1
0x18000e931  jz      short loc_18000E936
0x18000e933  mov     bl, r13b
0x18000e936  test    r12b, r12b
0x18000e939  jnz     short loc_18000E965
0x18000e93b  test    bl, bl
0x18000e93d  jnz     short loc_18000E965
0x18000e93f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e946  test    rax, rax
0x18000e949  jz      short loc_18000E9C2
0x18000e94b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000e952  jnz     short loc_18000E9C2
0x18000e954  xor     r8d, r8d
0x18000e957  xor     edx, edx
0x18000e959  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e95e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e963  jmp     short loc_18000E9C2
0x18000e965  mov     edi, 800h
0x18000e96a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e971  test    rax, rax
0x18000e974  jz      short loc_18000E993
0x18000e976  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000e97d  jnz     short loc_18000E993
0x18000e97f  mov     r8d, edi
0x18000e982  lea     rdx, [rbp+13F0h+OutputString]
0x18000e989  lea     rcx, [rsp+14F0h+var_14D0]
0x18000e98e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e993  cmp     [rbp+13F0h+OutputString], r13w
0x18000e99b  jnz     short loc_18000E9B1
0x18000e99d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000e9a2  mov     rdx, rdi; unsigned __int16 *
0x18000e9a5  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000e9ac  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000e9b1  test    bl, bl
0x18000e9b3  jz      short loc_18000E9C2
0x18000e9b5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000e9bc  call    cs:__imp_OutputDebugStringW
0x18000e9c2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000e9c7  jnz     short loc_18000E9D2
0x18000e9c9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000e9d0  jz      short loc_18000E9E4
0x18000e9d2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e9d9  test    rax, rax
0x18000e9dc  jz      short loc_18000E9E4
0x18000e9de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e9e3  nop
0x18000e9e4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000e9e9  jz      short loc_18000E9F6
0x18000e9eb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000e9f0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000e9f6  test    r12b, r12b
0x18000e9f9  jz      short loc_18000EA13
0x18000e9fb  lea     rdx, [rbp+13F0h+OutputString]
0x18000ea02  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ea07  mov     rax, cs:g_pfnThrowPlatformException
0x18000ea0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ea13  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000ea18  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000ea1d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000ea22  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
