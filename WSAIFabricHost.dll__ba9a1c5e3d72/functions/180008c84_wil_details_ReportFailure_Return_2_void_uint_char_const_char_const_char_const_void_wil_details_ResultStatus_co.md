# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180008c84`
- end: `0x180008f7c`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18000833c`

## callees

- `0x180004ca0`
- `0x180005758`
- `0x18000868c`
- `0x180008c84`
- `0x18000a024`
- `0x18000a870`
- `0x18000ace4`
- `0x18000be80`
- `0x18000c008`
- `0x18007f280`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008d9d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008f19`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008f19`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008e90`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008e90`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int v14; // edx
  int v15; // ebx
  int v16; // edx
  int v17; // ebx
  const struct wil::FailureInfo *v18; // rdx
  wil::details::in1diag3 *v19; // rcx
  const struct wil::FailureInfo *v20; // r9
  bool v21; // zf
  wil::details *v22; // [rsp+30h] [rbp-D0h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh]
  int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  signed __int32 v27; // [rsp+60h] [rbp-A0h]
  _WORD *v28; // [rsp+68h] [rbp-98h]
  DWORD CurrentThreadId; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+94h] [rbp-6Ch]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  __int128 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  __int64 ModuleName; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  char v43[1024]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR OutputString[2048]; // [rsp+4F0h] [rbp+3F0h] BYREF

  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v15 = *a7;
  v25 = v15;
  v26 = a7[1];
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v22) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v22);
    v25 = -2147024228;
    v26 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v16);
  }
  v17 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  v23 = 2;
  v24 = a10;
  if ( a7[2] == 1 )
    v24 = a10 | 8;
  v27 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v21 = *a8 == 0, v28 = a8, v21) )
    v28 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v17;
  v30 = a5;
  v31 = a4;
  v41 = a6;
  v42 = a1;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v19);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v23, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v23);
  if ( wil::details::g_pfnOriginateCallback && (v24 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v23);
  if ( v25 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v21 = !IsDebuggerPresent())
      : (v21 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v19) == 0),
        v21)
    || (v24 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v23, v20);
    OutputDebugStringW(OutputString);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v19);
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v18);
}

```

## disassembly

```asm
0x180008c84  push    rbp
0x180008c86  push    rbx
0x180008c87  push    rsi
0x180008c88  push    rdi
0x180008c89  push    r12
0x180008c8b  push    r13
0x180008c8d  push    r14
0x180008c8f  push    r15
0x180008c91  lea     rbp, [rsp-1408h]
0x180008c99  mov     eax, 1508h
0x180008c9e  call    _alloca_probe
0x180008ca3  sub     rsp, rax
0x180008ca6  mov     rax, cs:__security_cookie
0x180008cad  xor     rax, rsp
0x180008cb0  mov     [rbp+1440h+var_50], rax
0x180008cb7  mov     r12, r9
0x180008cba  mov     r15, r8
0x180008cbd  mov     r14d, edx
0x180008cc0  mov     rsi, rcx
0x180008cc3  mov     r13, [rbp+1440h+arg_20]
0x180008cca  mov     rax, [rbp+1440h+arg_28]
0x180008cd1  mov     [rsp+1540h+var_1500], rax
0x180008cd6  xor     edx, edx; Val
0x180008cd8  mov     r8d, 98h; Size
0x180008cde  lea     rcx, [rsp+1540h+var_14F0]; void *
0x180008ce3  call    memset_0
0x180008ce8  nop
0x180008ce9  xor     eax, eax
0x180008ceb  mov     [rbp+1440h+OutputString], ax
0x180008cf2  mov     [rbp+1440h+var_1450], al
0x180008cf5  mov     rdi, [rbp+1440h+arg_30]
0x180008cfc  mov     ebx, [rdi]
0x180008cfe  mov     [rsp+1540h+var_14E8], ebx
0x180008d02  mov     eax, [rdi+4]
0x180008d05  mov     [rsp+1540h+var_14E4], eax
0x180008d09  test    ebx, ebx
0x180008d0b  js      short loc_180008D45
0x180008d0d  mov     ebx, 8007029Ch
0x180008d12  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x180008d16  mov     rax, [rsp+1540h+var_1500]
0x180008d1b  mov     [rsp+1540h+var_1518], rax; __int64
0x180008d20  mov     [rsp+1540h+var_1520], r13; __int64
0x180008d25  mov     r9, r12; int
0x180008d28  mov     r8, r15; int
0x180008d2b  mov     edx, r14d; int
0x180008d2e  mov     rcx, rsi; int
0x180008d31  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008d36  mov     [rsp+1540h+var_14E8], ebx
0x180008d3a  mov     ecx, ebx; this
0x180008d3c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008d41  mov     [rsp+1540h+var_14E4], eax
0x180008d45  mov     ecx, ebx; this
0x180008d47  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008d4c  mov     ebx, eax
0x180008d4e  mov     dword ptr [rsp+1540h+var_14F0], 2
0x180008d56  mov     ecx, [rbp+1440h+arg_48]
0x180008d5c  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180008d60  cmp     dword ptr [rdi+8], 1
0x180008d64  jnz     short loc_180008D6D
0x180008d66  or      ecx, 8
0x180008d69  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180008d6d  mov     ecx, 1
0x180008d72  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008d7a  inc     ecx
0x180008d7c  mov     [rsp+1540h+var_14E0], ecx
0x180008d80  mov     rax, [rbp+1440h+arg_38]
0x180008d87  xor     edi, edi
0x180008d89  test    rax, rax
0x180008d8c  jz      short loc_180008D98
0x180008d8e  cmp     [rax], di
0x180008d91  mov     [rsp+1540h+var_14D8], rax
0x180008d96  jnz     short loc_180008D9D
0x180008d98  mov     [rsp+1540h+var_14D8], rdi
0x180008d9d  call    cs:__imp_GetCurrentThreadId
0x180008da3  mov     [rsp+1540h+var_14D0], eax
0x180008da7  mov     [rbp+1440h+var_14B8], r15
0x180008dab  mov     [rbp+1440h+var_14B0], r14d
0x180008daf  mov     [rbp+1440h+var_14AC], ebx
0x180008db2  mov     [rsp+1540h+var_14C8], r13
0x180008db7  mov     [rbp+1440h+var_14C0], r12
0x180008dbb  mov     rax, [rsp+1540h+var_1500]
0x180008dc0  mov     [rbp+1440h+var_1468], rax
0x180008dc4  mov     [rbp+1440h+var_1460], rsi
0x180008dc8  mov     [rbp+1440h+var_14A8], rdi
0x180008dcc  xorps   xmm0, xmm0
0x180008dcf  xor     eax, eax
0x180008dd1  movups  [rbp+1440h+var_1488], xmm0
0x180008dd5  mov     [rbp+1440h+var_1478], rax
0x180008dd9  xorps   xmm1, xmm1
0x180008ddc  movups  [rbp+1440h+var_14A0], xmm1
0x180008de0  mov     [rbp+1440h+var_1490], rax
0x180008de4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008deb  test    rax, rax
0x180008dee  jz      short loc_180008DFB
0x180008df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008df5  mov     [rbp+1440h+var_1470], rax
0x180008df9  jmp     short loc_180008DFF
0x180008dfb  mov     [rbp+1440h+var_1470], rdi
0x180008dff  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008e06  test    rax, rax
0x180008e09  jz      short loc_180008E15
0x180008e0b  lea     rcx, [rsp+1540h+var_14F0]
0x180008e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e15  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008e1c  test    rax, rax
0x180008e1f  jz      short loc_180008E35
0x180008e21  mov     r8d, 400h
0x180008e27  lea     rdx, [rbp+1440h+var_1450]
0x180008e2b  lea     rcx, [rsp+1540h+var_14F0]
0x180008e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e35  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008e3c  test    rax, rax
0x180008e3f  jz      short loc_180008E4B
0x180008e41  lea     rcx, [rsp+1540h+var_14F0]
0x180008e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e4b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008e52  test    rax, rax
0x180008e55  jz      short loc_180008E68
0x180008e57  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180008e5c  jnz     short loc_180008E68
0x180008e5e  lea     rcx, [rsp+1540h+var_14F0]
0x180008e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e68  cmp     [rsp+1540h+var_14E8], edi
0x180008e6c  jge     loc_180008F76
0x180008e72  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008e79  jnz     short loc_180008E9A
0x180008e7b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008e82  test    rax, rax
0x180008e85  jz      short loc_180008E90
0x180008e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e8c  test    al, al
0x180008e8e  jmp     short loc_180008E98
0x180008e90  call    cs:__imp_IsDebuggerPresent
0x180008e96  test    eax, eax
0x180008e98  jz      short loc_180008EA1
0x180008e9a  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180008e9f  jz      short loc_180008EC7
0x180008ea1  mov     rax, cs:g_pfnResultLoggingCallback
0x180008ea8  test    rax, rax
0x180008eab  jz      short loc_180008F1F
0x180008ead  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008eb4  jnz     short loc_180008F1F
0x180008eb6  xor     r8d, r8d
0x180008eb9  xor     edx, edx
0x180008ebb  lea     rcx, [rsp+1540h+var_14F0]
0x180008ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ec5  jmp     short loc_180008F1F
0x180008ec7  mov     ebx, 800h
0x180008ecc  mov     rax, cs:g_pfnResultLoggingCallback
0x180008ed3  test    rax, rax
0x180008ed6  jz      short loc_180008EF5
0x180008ed8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008edf  jnz     short loc_180008EF5
0x180008ee1  mov     r8d, ebx
0x180008ee4  lea     rdx, [rbp+1440h+OutputString]
0x180008eeb  lea     rcx, [rsp+1540h+var_14F0]
0x180008ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ef5  cmp     [rbp+1440h+OutputString], di
0x180008efc  jnz     short loc_180008F12
0x180008efe  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x180008f03  mov     rdx, rbx; wchar_t *
0x180008f06  lea     rcx, [rbp+1440h+OutputString]; this
0x180008f0d  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180008f12  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x180008f19  call    cs:__imp_OutputDebugStringW
0x180008f1f  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x180008f24  jnz     short loc_180008F2F
0x180008f26  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008f2d  jz      short loc_180008F41
0x180008f2f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008f36  test    rax, rax
0x180008f39  jz      short loc_180008F41
0x180008f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f40  nop
0x180008f41  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x180008f46  jnz     short loc_180008F6B
0x180008f48  mov     rcx, [rbp+1440h+var_50]
0x180008f4f  xor     rcx, rsp; StackCookie
0x180008f52  call    __security_check_cookie
0x180008f57  add     rsp, 1508h
0x180008f5e  pop     r15
0x180008f60  pop     r14
0x180008f62  pop     r13
0x180008f64  pop     r12
0x180008f66  pop     rdi
0x180008f67  pop     rsi
0x180008f68  pop     rbx
0x180008f69  pop     rbp
0x180008f6a  retn
0x180008f6b  lea     rcx, [rsp+1540h+var_14F0]; this
0x180008f70  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180008f76  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
