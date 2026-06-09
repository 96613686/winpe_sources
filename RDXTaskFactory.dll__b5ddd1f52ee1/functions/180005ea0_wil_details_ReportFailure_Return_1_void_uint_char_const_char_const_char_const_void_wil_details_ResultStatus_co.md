# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005ea0`
- end: `0x180006146`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005b20`

## callees

- `0x180003390`
- `0x180003e00`
- `0x180005ea0`
- `0x1800080c4`
- `0x180009eb8`
- `0x18000bdd8`
- `0x18000c0cc`
- `0x18004cf00`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f66`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000605b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000605b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800060e5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800060e5`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180005ea0  push    rbp
0x180005ea2  push    rbx
0x180005ea3  push    rsi
0x180005ea4  push    rdi
0x180005ea5  push    r12
0x180005ea7  push    r14
0x180005ea9  push    r15
0x180005eab  lea     rbp, [rsp-13D0h]
0x180005eb3  mov     eax, 14D0h
0x180005eb8  call    _alloca_probe
0x180005ebd  sub     rsp, rax
0x180005ec0  mov     rax, cs:__security_cookie
0x180005ec7  xor     rax, rsp
0x180005eca  mov     [rbp+1400h+var_40], rax
0x180005ed1  mov     rsi, r8
0x180005ed4  mov     edi, edx
0x180005ed6  mov     rbx, rcx
0x180005ed9  mov     r14, [rbp+1400h+arg_28]
0x180005ee0  xor     edx, edx; Val
0x180005ee2  mov     r8d, 98h; Size
0x180005ee8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180005eed  call    memset_0
0x180005ef2  nop
0x180005ef3  xor     r12d, r12d
0x180005ef6  mov     [rbp+1400h+OutputString], r12w
0x180005efe  mov     [rbp+1400h+var_1440], r12b
0x180005f02  mov     rdx, [rbp+1400h+arg_30]; int
0x180005f09  mov     ecx, [rdx]; this
0x180005f0b  mov     [rsp+1500h+var_14D8], ecx
0x180005f0f  mov     eax, [rdx+4]
0x180005f12  mov     [rsp+1500h+var_14D4], eax
0x180005f16  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005f1b  mov     r15d, eax
0x180005f1e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005f26  mov     ecx, r12d
0x180005f29  lea     eax, [r12+8]
0x180005f2e  cmp     dword ptr [rdx+8], 1
0x180005f32  cmovz   ecx, eax
0x180005f35  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005f39  lea     ecx, [rax-7]
0x180005f3c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005f44  inc     ecx
0x180005f46  mov     [rsp+1500h+var_14D0], ecx
0x180005f4a  mov     rcx, [rbp+1400h+arg_38]
0x180005f51  test    rcx, rcx
0x180005f54  jz      short loc_180005F61
0x180005f56  cmp     [rcx], r12w
0x180005f5a  mov     [rsp+1500h+var_14C8], rcx
0x180005f5f  jnz     short loc_180005F66
0x180005f61  mov     [rsp+1500h+var_14C8], r12
0x180005f66  call    cs:__imp_GetCurrentThreadId
0x180005f6c  mov     [rsp+1500h+var_14C0], eax
0x180005f70  mov     [rsp+1500h+var_14A8], rsi
0x180005f75  mov     [rsp+1500h+var_14A0], edi
0x180005f79  mov     [rsp+1500h+var_149C], r15d
0x180005f7e  mov     [rsp+1500h+var_14B8], r12
0x180005f83  mov     [rsp+1500h+var_14B0], r12
0x180005f88  mov     [rbp+1400h+var_1458], r14
0x180005f8c  mov     [rbp+1400h+var_1450], rbx
0x180005f90  mov     [rsp+1500h+var_1498], r12
0x180005f95  xorps   xmm0, xmm0
0x180005f98  xor     eax, eax
0x180005f9a  movups  [rbp+1400h+var_1478], xmm0
0x180005f9e  mov     [rbp+1400h+var_1468], rax
0x180005fa2  xorps   xmm1, xmm1
0x180005fa5  movups  [rsp+1500h+var_1490], xmm1
0x180005faa  mov     [rbp+1400h+var_1480], rax
0x180005fae  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005fb5  test    rax, rax
0x180005fb8  jz      short loc_180005FC5
0x180005fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fbf  mov     [rbp+1400h+var_1460], rax
0x180005fc3  jmp     short loc_180005FC9
0x180005fc5  mov     [rbp+1400h+var_1460], r12
0x180005fc9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005fd0  test    rax, rax
0x180005fd3  jz      short loc_180005FDF
0x180005fd5  lea     rcx, [rsp+1500h+var_14E0]
0x180005fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fdf  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005fe6  test    rax, rax
0x180005fe9  jz      short loc_180005FFF
0x180005feb  mov     r8d, 400h
0x180005ff1  lea     rdx, [rbp+1400h+var_1440]
0x180005ff5  lea     rcx, [rsp+1500h+var_14E0]
0x180005ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fff  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006006  test    rax, rax
0x180006009  jz      short loc_180006015
0x18000600b  lea     rcx, [rsp+1500h+var_14E0]
0x180006010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006015  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000601c  test    rax, rax
0x18000601f  jz      short loc_180006032
0x180006021  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006026  jnz     short loc_180006032
0x180006028  lea     rcx, [rsp+1500h+var_14E0]
0x18000602d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006032  cmp     [rsp+1500h+var_14D8], r12d
0x180006037  jge     loc_180006140
0x18000603d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180006044  jnz     short loc_180006065
0x180006046  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000604d  test    rax, rax
0x180006050  jz      short loc_18000605B
0x180006052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006057  test    al, al
0x180006059  jmp     short loc_180006063
0x18000605b  call    cs:__imp_IsDebuggerPresent
0x180006061  test    eax, eax
0x180006063  jz      short loc_18000606C
0x180006065  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000606a  jz      short loc_180006092
0x18000606c  mov     rax, cs:g_pfnResultLoggingCallback
0x180006073  test    rax, rax
0x180006076  jz      short loc_1800060EB
0x180006078  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000607f  jnz     short loc_1800060EB
0x180006081  xor     r8d, r8d
0x180006084  xor     edx, edx
0x180006086  lea     rcx, [rsp+1500h+var_14E0]
0x18000608b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006090  jmp     short loc_1800060EB
0x180006092  mov     ebx, 800h
0x180006097  mov     rax, cs:g_pfnResultLoggingCallback
0x18000609e  test    rax, rax
0x1800060a1  jz      short loc_1800060C0
0x1800060a3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800060aa  jnz     short loc_1800060C0
0x1800060ac  mov     r8d, ebx
0x1800060af  lea     rdx, [rbp+1400h+OutputString]
0x1800060b6  lea     rcx, [rsp+1500h+var_14E0]
0x1800060bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c0  cmp     [rbp+1400h+OutputString], r12w
0x1800060c8  jnz     short loc_1800060DE
0x1800060ca  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800060cf  mov     rdx, rbx; unsigned __int16 *
0x1800060d2  lea     rcx, [rbp+1400h+OutputString]; this
0x1800060d9  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800060de  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800060e5  call    cs:__imp_OutputDebugStringW
0x1800060eb  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800060f0  jnz     short loc_1800060FB
0x1800060f2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800060f9  jz      short loc_18000610D
0x1800060fb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006102  test    rax, rax
0x180006105  jz      short loc_18000610D
0x180006107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000610c  nop
0x18000610d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180006112  jnz     short loc_180006135
0x180006114  mov     rcx, [rbp+1400h+var_40]
0x18000611b  xor     rcx, rsp; StackCookie
0x18000611e  call    __security_check_cookie
0x180006123  add     rsp, 14D0h
0x18000612a  pop     r15
0x18000612c  pop     r14
0x18000612e  pop     r12
0x180006130  pop     rdi
0x180006131  pop     rsi
0x180006132  pop     rbx
0x180006133  pop     rbp
0x180006134  retn
0x180006135  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000613a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180006140  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
