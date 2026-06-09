# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000f5d0`
- end: `0x18000f864`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180009228`

## callees

- `0x180009850`
- `0x18000a19a`
- `0x18000f5d0`
- `0x1800100fc`
- `0x180010d64`
- `0x1800114d8`
- `0x1800115b4`
- `0x1800118a0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f67a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f67a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f775`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f775`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f7ff`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f7ff`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x18000f5d0  mov     [rsp-8+arg_10], rbx
0x18000f5d5  push    rbp
0x18000f5d6  push    rsi
0x18000f5d7  push    rdi
0x18000f5d8  push    r14
0x18000f5da  push    r15
0x18000f5dc  lea     rbp, [rsp-13D0h]
0x18000f5e4  mov     eax, 14D0h
0x18000f5e9  call    _alloca_probe
0x18000f5ee  sub     rsp, rax
0x18000f5f1  mov     rax, cs:__security_cookie
0x18000f5f8  xor     rax, rsp
0x18000f5fb  mov     [rbp+13F0h+var_30], rax
0x18000f602  mov     rdi, [rbp+13F0h+arg_28]
0x18000f609  mov     esi, edx
0x18000f60b  mov     r14, rcx
0x18000f60e  xor     edx, edx; Val
0x18000f610  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000f615  mov     r8d, 98h; Size
0x18000f61b  call    memset_0
0x18000f620  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000f627  xor     r15d, r15d
0x18000f62a  mov     [rbp+13F0h+OutputString], r15w
0x18000f632  mov     [rbp+13F0h+var_1430], r15b
0x18000f636  mov     ecx, [rdx]; this
0x18000f638  mov     eax, [rdx+4]
0x18000f63b  mov     [rsp+14F0h+var_14C8], ecx
0x18000f63f  mov     [rsp+14F0h+var_14C4], eax
0x18000f643  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000f648  cmp     dword ptr [rdx+8], 1
0x18000f64c  mov     ebx, eax
0x18000f64e  lea     eax, [r15+8]
0x18000f652  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000f65a  mov     ecx, r15d
0x18000f65d  cmovz   ecx, eax
0x18000f660  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000f664  lea     ecx, [rax-7]
0x18000f667  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000f66f  inc     ecx
0x18000f671  mov     [rsp+14F0h+var_14B8], r15
0x18000f676  mov     [rsp+14F0h+var_14C0], ecx
0x18000f67a  call    cs:__imp_GetCurrentThreadId
0x18000f680  xorps   xmm0, xmm0
0x18000f683  mov     [rsp+14F0h+var_1490], esi
0x18000f687  mov     [rsp+14F0h+var_14B0], eax
0x18000f68b  xorps   xmm1, xmm1
0x18000f68e  lea     rax, aWil; "wil"
0x18000f695  mov     [rsp+14F0h+var_148C], ebx
0x18000f699  mov     [rsp+14F0h+var_1498], rax
0x18000f69e  xor     eax, eax
0x18000f6a0  mov     [rbp+13F0h+var_1458], rax
0x18000f6a4  mov     [rbp+13F0h+var_1470], rax
0x18000f6a8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000f6af  mov     [rsp+14F0h+var_14A8], r15
0x18000f6b4  mov     [rsp+14F0h+var_14A0], r15
0x18000f6b9  mov     [rbp+13F0h+var_1448], rdi
0x18000f6bd  mov     [rbp+13F0h+var_1440], r14
0x18000f6c1  mov     [rsp+14F0h+var_1488], r15
0x18000f6c6  movups  [rbp+13F0h+var_1468], xmm0
0x18000f6ca  movups  [rsp+14F0h+var_1480], xmm1
0x18000f6cf  test    rax, rax
0x18000f6d2  jz      short loc_18000F6DF
0x18000f6d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6d9  mov     [rbp+13F0h+var_1450], rax
0x18000f6dd  jmp     short loc_18000F6E3
0x18000f6df  mov     [rbp+13F0h+var_1450], r15
0x18000f6e3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000f6ea  test    rax, rax
0x18000f6ed  jz      short loc_18000F6F9
0x18000f6ef  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f6f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f6f9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000f700  test    rax, rax
0x18000f703  jz      short loc_18000F719
0x18000f705  mov     r8d, 400h
0x18000f70b  lea     rdx, [rbp+13F0h+var_1430]
0x18000f70f  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f719  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f720  test    rax, rax
0x18000f723  jz      short loc_18000F72F
0x18000f725  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f72f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f736  test    rax, rax
0x18000f739  jz      short loc_18000F74C
0x18000f73b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000f740  jnz     short loc_18000F74C
0x18000f742  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f74c  cmp     [rsp+14F0h+var_14C8], r15d
0x18000f751  jge     loc_18000F85E
0x18000f757  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000f75e  jnz     short loc_18000F77F
0x18000f760  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000f767  test    rax, rax
0x18000f76a  jz      short loc_18000F775
0x18000f76c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f771  test    al, al
0x18000f773  jmp     short loc_18000F77D
0x18000f775  call    cs:__imp_IsDebuggerPresent
0x18000f77b  test    eax, eax
0x18000f77d  jz      short loc_18000F786
0x18000f77f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000f784  jz      short loc_18000F7AC
0x18000f786  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f78d  test    rax, rax
0x18000f790  jz      short loc_18000F805
0x18000f792  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000f799  jnz     short loc_18000F805
0x18000f79b  xor     r8d, r8d
0x18000f79e  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f7a3  xor     edx, edx
0x18000f7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7aa  jmp     short loc_18000F805
0x18000f7ac  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f7b3  mov     ebx, 800h
0x18000f7b8  test    rax, rax
0x18000f7bb  jz      short loc_18000F7DA
0x18000f7bd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000f7c4  jnz     short loc_18000F7DA
0x18000f7c6  mov     r8d, ebx
0x18000f7c9  lea     rdx, [rbp+13F0h+OutputString]
0x18000f7d0  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f7d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f7da  cmp     [rbp+13F0h+OutputString], r15w
0x18000f7e2  jnz     short loc_18000F7F8
0x18000f7e4  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000f7e9  mov     rdx, rbx; unsigned __int16 *
0x18000f7ec  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000f7f3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000f7f8  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000f7ff  call    cs:__imp_OutputDebugStringW
0x18000f805  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000f80a  jnz     short loc_18000F815
0x18000f80c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000f813  jz      short loc_18000F826
0x18000f815  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000f81c  test    rax, rax
0x18000f81f  jz      short loc_18000F826
0x18000f821  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f826  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000f82b  jnz     short loc_18000F853
0x18000f82d  mov     rcx, [rbp+13F0h+var_30]
0x18000f834  xor     rcx, rsp; StackCookie
0x18000f837  call    __security_check_cookie
0x18000f83c  mov     rbx, [rsp+14F0h+arg_10]
0x18000f844  add     rsp, 14D0h
0x18000f84b  pop     r15
0x18000f84d  pop     r14
0x18000f84f  pop     rdi
0x18000f850  pop     rsi
0x18000f851  pop     rbp
0x18000f852  retn
0x18000f853  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000f858  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000f85e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
