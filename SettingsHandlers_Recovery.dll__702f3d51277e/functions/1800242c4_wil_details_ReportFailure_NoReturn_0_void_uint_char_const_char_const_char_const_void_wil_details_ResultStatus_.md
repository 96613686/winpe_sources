# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800242c4`
- end: `0x180024589`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180024204`

## callees

- `0x180002ed4`
- `0x180006304`
- `0x180007ad0`
- `0x180009b58`
- `0x18000a2c0`
- `0x18000a48c`
- `0x1800242c4`
- `0x1800291b0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024385`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024385`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180024481`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180024481`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002451d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002451d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  bool v11; // di
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v23 = *a7;
  v24 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v23, (int)a7);
  v21 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v22 = v13;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v26 = a8, v18) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v31 = a2;
  v32 = v12;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v19 = 1, (v22 & 2) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0, v17);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v15);
  if ( v11 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v21, OutputString);
  wil::ThrowResultException((wil *)&v21, v15);
  wil::details::WilFailFast((wil::details *)&v21, v20);
}

```

## disassembly

```asm
0x1800242c4  mov     [rsp-8+arg_18], rbx
0x1800242c9  push    rbp
0x1800242ca  push    rsi
0x1800242cb  push    rdi
0x1800242cc  push    r12
0x1800242ce  push    r13
0x1800242d0  push    r14
0x1800242d2  push    r15
0x1800242d4  lea     rbp, [rsp-13C0h]
0x1800242dc  mov     eax, 14C0h
0x1800242e1  call    _alloca_probe
0x1800242e6  sub     rsp, rax
0x1800242e9  mov     r14, r8
0x1800242ec  mov     esi, edx
0x1800242ee  mov     rbx, rcx
0x1800242f1  mov     r15, [rbp+13F0h+arg_28]
0x1800242f8  xor     r13d, r13d
0x1800242fb  cmp     cs:g_pfnThrowPlatformException, r13
0x180024302  setnz   dil
0x180024306  xor     edx, edx; Val
0x180024308  mov     r8d, 98h; Size
0x18002430e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180024313  call    memset_0
0x180024318  nop
0x180024319  mov     [rbp+13F0h+OutputString], r13w
0x180024321  mov     [rbp+13F0h+var_1430], r13b
0x180024325  mov     rdx, [rbp+13F0h+arg_30]; int
0x18002432c  mov     ecx, [rdx]; this
0x18002432e  mov     [rsp+14F0h+var_14C8], ecx
0x180024332  mov     eax, [rdx+4]
0x180024335  mov     [rsp+14F0h+var_14C4], eax
0x180024339  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002433e  mov     r12d, eax
0x180024341  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180024346  mov     ecx, r13d
0x180024349  lea     eax, [r13+8]
0x18002434d  cmp     dword ptr [rdx+8], 1
0x180024351  cmovz   ecx, eax
0x180024354  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180024358  lea     ecx, [rax-7]
0x18002435b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180024363  inc     ecx
0x180024365  mov     [rsp+14F0h+var_14C0], ecx
0x180024369  mov     rcx, [rbp+13F0h+arg_38]
0x180024370  test    rcx, rcx
0x180024373  jz      short loc_180024380
0x180024375  cmp     [rcx], r13w
0x180024379  mov     [rsp+14F0h+var_14B8], rcx
0x18002437e  jnz     short loc_180024385
0x180024380  mov     [rsp+14F0h+var_14B8], r13
0x180024385  call    cs:__imp_GetCurrentThreadId
0x18002438b  mov     [rsp+14F0h+var_14B0], eax
0x18002438f  mov     [rsp+14F0h+var_1498], r14
0x180024394  mov     [rsp+14F0h+var_1490], esi
0x180024398  mov     [rsp+14F0h+var_148C], r12d
0x18002439d  mov     [rsp+14F0h+var_14A8], r13
0x1800243a2  mov     [rsp+14F0h+var_14A0], r13
0x1800243a7  mov     [rbp+13F0h+var_1448], r15
0x1800243ab  mov     [rbp+13F0h+var_1440], rbx
0x1800243af  mov     [rsp+14F0h+var_1488], r13
0x1800243b4  xorps   xmm0, xmm0
0x1800243b7  xor     eax, eax
0x1800243b9  movups  [rbp+13F0h+var_1468], xmm0
0x1800243bd  mov     [rbp+13F0h+var_1458], rax
0x1800243c1  xorps   xmm1, xmm1
0x1800243c4  movups  [rsp+14F0h+var_1480], xmm1
0x1800243c9  mov     [rbp+13F0h+var_1470], rax
0x1800243cd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800243d4  test    rax, rax
0x1800243d7  jz      short loc_1800243E4
0x1800243d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243de  mov     [rbp+13F0h+var_1450], rax
0x1800243e2  jmp     short loc_1800243E8
0x1800243e4  mov     [rbp+13F0h+var_1450], r13
0x1800243e8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800243ef  test    rax, rax
0x1800243f2  jz      short loc_1800243FE
0x1800243f4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800243f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800243fe  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180024405  test    rax, rax
0x180024408  jz      short loc_18002441E
0x18002440a  mov     r8d, 400h
0x180024410  lea     rdx, [rbp+13F0h+var_1430]
0x180024414  lea     rcx, [rsp+14F0h+var_14D0]
0x180024419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002441e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180024425  test    rax, rax
0x180024428  jz      short loc_180024434
0x18002442a  lea     rcx, [rsp+14F0h+var_14D0]
0x18002442f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024434  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002443b  test    rax, rax
0x18002443e  jz      short loc_180024456
0x180024440  test    dil, dil
0x180024443  jnz     short loc_180024456
0x180024445  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18002444a  jnz     short loc_180024456
0x18002444c  lea     rcx, [rsp+14F0h+var_14D0]
0x180024451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024456  cmp     [rsp+14F0h+var_14C8], r13d
0x18002445b  jl      short loc_180024463
0x18002445d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180024463  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18002446a  jnz     short loc_18002448B
0x18002446c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180024473  test    rax, rax
0x180024476  jz      short loc_180024481
0x180024478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002447d  test    al, al
0x18002447f  jmp     short loc_180024489
0x180024481  call    cs:__imp_IsDebuggerPresent
0x180024487  test    eax, eax
0x180024489  jz      short loc_180024494
0x18002448b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180024490  mov     bl, 1
0x180024492  jz      short loc_180024497
0x180024494  mov     bl, r13b
0x180024497  test    dil, dil
0x18002449a  jnz     short loc_1800244C6
0x18002449c  test    bl, bl
0x18002449e  jnz     short loc_1800244C6
0x1800244a0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800244a7  test    rax, rax
0x1800244aa  jz      short loc_180024523
0x1800244ac  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800244b3  jnz     short loc_180024523
0x1800244b5  xor     r8d, r8d
0x1800244b8  xor     edx, edx
0x1800244ba  lea     rcx, [rsp+14F0h+var_14D0]
0x1800244bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244c4  jmp     short loc_180024523
0x1800244c6  mov     esi, 800h
0x1800244cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800244d2  test    rax, rax
0x1800244d5  jz      short loc_1800244F4
0x1800244d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800244de  jnz     short loc_1800244F4
0x1800244e0  mov     r8d, esi
0x1800244e3  lea     rdx, [rbp+13F0h+OutputString]
0x1800244ea  lea     rcx, [rsp+14F0h+var_14D0]
0x1800244ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800244f4  cmp     [rbp+13F0h+OutputString], r13w
0x1800244fc  jnz     short loc_180024512
0x1800244fe  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180024503  mov     rdx, rsi; unsigned __int16 *
0x180024506  lea     rcx, [rbp+13F0h+OutputString]; this
0x18002450d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180024512  test    bl, bl
0x180024514  jz      short loc_180024523
0x180024516  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18002451d  call    cs:__imp_OutputDebugStringW
0x180024523  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180024528  jnz     short loc_180024533
0x18002452a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180024531  jz      short loc_180024545
0x180024533  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002453a  test    rax, rax
0x18002453d  jz      short loc_180024545
0x18002453f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024544  nop
0x180024545  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18002454a  jz      short loc_180024557
0x18002454c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180024551  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180024557  test    dil, dil
0x18002455a  jz      short loc_180024574
0x18002455c  lea     rdx, [rbp+13F0h+OutputString]
0x180024563  lea     rcx, [rsp+14F0h+var_14D0]
0x180024568  mov     rax, cs:g_pfnThrowPlatformException
0x18002456f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024574  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180024579  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18002457e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180024583  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
