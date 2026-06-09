# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000289c`
- end: `0x140002b3c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400023d0`

## callees

- `0x14000289c`
- `0x1400044e4`
- `0x140005d14`
- `0x140007070`
- `0x14000738c`
- `0x140009cc6`
- `0x140009d00`
- `0x140009dc0`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000294a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000294a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002a44`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002a44`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002ad4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002ad4`

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
0x14000289c  push    rbp
0x14000289e  push    rbx
0x14000289f  push    rsi
0x1400028a0  push    rdi
0x1400028a1  push    r12
0x1400028a3  push    r14
0x1400028a5  push    r15
0x1400028a7  lea     rbp, [rsp-13D0h]
0x1400028af  mov     eax, 14D0h
0x1400028b4  call    _alloca_probe
0x1400028b9  sub     rsp, rax
0x1400028bc  mov     rax, cs:__security_cookie
0x1400028c3  xor     rax, rsp
0x1400028c6  mov     [rbp+1400h+var_40], rax
0x1400028cd  mov     r14, r8
0x1400028d0  mov     esi, edx
0x1400028d2  mov     r15, rcx
0x1400028d5  mov     rdi, [rbp+1400h+arg_28]
0x1400028dc  xor     edx, edx; Val
0x1400028de  mov     r8d, 98h; Size
0x1400028e4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400028e9  call    memset_0
0x1400028ee  nop
0x1400028ef  xor     r12d, r12d
0x1400028f2  mov     [rbp+1400h+OutputString], r12w
0x1400028fa  mov     [rbp+1400h+var_1440], r12b
0x1400028fe  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x140002905  mov     ecx, [rdx]; this
0x140002907  mov     [rsp+1500h+var_14D8], ecx
0x14000290b  mov     eax, [rdx+4]
0x14000290e  mov     [rsp+1500h+var_14D4], eax
0x140002912  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002917  mov     ebx, eax
0x140002919  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140002921  mov     ecx, r12d
0x140002924  lea     eax, [r12+8]
0x140002929  cmp     dword ptr [rdx+8], 1
0x14000292d  cmovz   ecx, eax
0x140002930  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140002934  lea     ecx, [rax-7]
0x140002937  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000293f  inc     ecx
0x140002941  mov     [rsp+1500h+var_14D0], ecx
0x140002945  mov     [rsp+1500h+var_14C8], r12
0x14000294a  call    cs:__imp_GetCurrentThreadId
0x140002951  nop     dword ptr [rax+rax+00h]
0x140002956  mov     [rsp+1500h+var_14C0], eax
0x14000295a  mov     [rsp+1500h+var_14A8], r14
0x14000295f  mov     [rsp+1500h+var_14A0], esi
0x140002963  mov     [rsp+1500h+var_149C], ebx
0x140002967  mov     [rsp+1500h+var_14B8], r12
0x14000296c  mov     [rsp+1500h+var_14B0], r12
0x140002971  mov     [rbp+1400h+var_1458], rdi
0x140002975  mov     [rbp+1400h+var_1450], r15
0x140002979  mov     [rsp+1500h+var_1498], r12
0x14000297e  xorps   xmm0, xmm0
0x140002981  xor     eax, eax
0x140002983  movups  [rbp+1400h+var_1478], xmm0
0x140002987  mov     [rbp+1400h+var_1468], rax
0x14000298b  xorps   xmm1, xmm1
0x14000298e  movups  [rsp+1500h+var_1490], xmm1
0x140002993  mov     [rbp+1400h+var_1480], rax
0x140002997  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000299e  test    rax, rax
0x1400029a1  jz      short loc_1400029AE
0x1400029a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029a8  mov     [rbp+1400h+var_1460], rax
0x1400029ac  jmp     short loc_1400029B2
0x1400029ae  mov     [rbp+1400h+var_1460], r12
0x1400029b2  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400029b9  test    rax, rax
0x1400029bc  jz      short loc_1400029C8
0x1400029be  lea     rcx, [rsp+1500h+var_14E0]
0x1400029c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029c8  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400029cf  test    rax, rax
0x1400029d2  jz      short loc_1400029E8
0x1400029d4  mov     r8d, 400h
0x1400029da  lea     rdx, [rbp+1400h+var_1440]
0x1400029de  lea     rcx, [rsp+1500h+var_14E0]
0x1400029e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029e8  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400029ef  test    rax, rax
0x1400029f2  jz      short loc_1400029FE
0x1400029f4  lea     rcx, [rsp+1500h+var_14E0]
0x1400029f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029fe  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002a05  test    rax, rax
0x140002a08  jz      short loc_140002A1B
0x140002a0a  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002a0f  jnz     short loc_140002A1B
0x140002a11  lea     rcx, [rsp+1500h+var_14E0]
0x140002a16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a1b  cmp     [rsp+1500h+var_14D8], r12d
0x140002a20  jge     loc_140002B36
0x140002a26  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140002a2d  jnz     short loc_140002A54
0x140002a2f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002a36  test    rax, rax
0x140002a39  jz      short loc_140002A44
0x140002a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a40  test    al, al
0x140002a42  jmp     short loc_140002A52
0x140002a44  call    cs:__imp_IsDebuggerPresent
0x140002a4b  nop     dword ptr [rax+rax+00h]
0x140002a50  test    eax, eax
0x140002a52  jz      short loc_140002A5B
0x140002a54  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002a59  jz      short loc_140002A81
0x140002a5b  mov     rax, cs:g_pfnResultLoggingCallback
0x140002a62  test    rax, rax
0x140002a65  jz      short loc_140002AE0
0x140002a67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002a6e  jnz     short loc_140002AE0
0x140002a70  xor     r8d, r8d
0x140002a73  xor     edx, edx
0x140002a75  lea     rcx, [rsp+1500h+var_14E0]
0x140002a7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a7f  jmp     short loc_140002AE0
0x140002a81  mov     ebx, 800h
0x140002a86  mov     rax, cs:g_pfnResultLoggingCallback
0x140002a8d  test    rax, rax
0x140002a90  jz      short loc_140002AAF
0x140002a92  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002a99  jnz     short loc_140002AAF
0x140002a9b  mov     r8d, ebx
0x140002a9e  lea     rdx, [rbp+1400h+OutputString]
0x140002aa5  lea     rcx, [rsp+1500h+var_14E0]
0x140002aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002aaf  cmp     [rbp+1400h+OutputString], r12w
0x140002ab7  jnz     short loc_140002ACD
0x140002ab9  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140002abe  mov     rdx, rbx; unsigned __int16 *
0x140002ac1  lea     rcx, [rbp+1400h+OutputString]; this
0x140002ac8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002acd  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140002ad4  call    cs:__imp_OutputDebugStringW
0x140002adb  nop     dword ptr [rax+rax+00h]
0x140002ae0  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140002ae5  jnz     short loc_140002AF0
0x140002ae7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140002aee  jz      short loc_140002B02
0x140002af0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002af7  test    rax, rax
0x140002afa  jz      short loc_140002B02
0x140002afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b01  nop
0x140002b02  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140002b07  jnz     short loc_140002B2B
0x140002b09  mov     rcx, [rbp+1400h+var_40]
0x140002b10  xor     rcx, rsp; StackCookie
0x140002b13  call    __security_check_cookie
0x140002b18  add     rsp, 14D0h
0x140002b1f  pop     r15
0x140002b21  pop     r14
0x140002b23  pop     r12
0x140002b25  pop     rdi
0x140002b26  pop     rsi
0x140002b27  pop     rbx
0x140002b28  pop     rbp
0x140002b29  retn
0x140002b2b  lea     rcx, [rsp+1500h+var_14E0]; this
0x140002b30  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002b36  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
