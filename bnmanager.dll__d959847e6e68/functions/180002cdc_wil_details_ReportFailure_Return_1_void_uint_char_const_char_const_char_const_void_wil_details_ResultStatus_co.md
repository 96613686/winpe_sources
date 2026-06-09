# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002cdc`
- end: `0x180002f72`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800027bc`

## callees

- `0x1800017c0`
- `0x180002290`
- `0x180002cdc`
- `0x180007e54`
- `0x180009558`
- `0x18000b9b0`
- `0x18000bb7c`
- `0x18000ca80`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d87`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002e82`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002e82`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002f0c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002f0c`

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
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180002cdc  mov     [rsp-8+arg_10], rbx
0x180002ce1  push    rbp
0x180002ce2  push    rsi
0x180002ce3  push    rdi
0x180002ce4  push    r14
0x180002ce6  push    r15
0x180002ce8  lea     rbp, [rsp-13D0h]
0x180002cf0  mov     eax, 14D0h
0x180002cf5  call    _alloca_probe
0x180002cfa  sub     rsp, rax
0x180002cfd  mov     rax, cs:__security_cookie
0x180002d04  xor     rax, rsp
0x180002d07  mov     [rbp+13F0h+var_30], rax
0x180002d0e  mov     esi, edx
0x180002d10  mov     r14, rcx
0x180002d13  mov     rdi, [rbp+13F0h+arg_28]
0x180002d1a  xor     edx, edx; Val
0x180002d1c  mov     r8d, 98h; Size
0x180002d22  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002d27  call    memset_0
0x180002d2c  nop
0x180002d2d  xor     r15d, r15d
0x180002d30  mov     [rbp+13F0h+OutputString], r15w
0x180002d38  mov     [rbp+13F0h+var_1430], r15b
0x180002d3c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002d43  mov     ecx, [rdx]; this
0x180002d45  mov     [rsp+14F0h+var_14C8], ecx
0x180002d49  mov     eax, [rdx+4]
0x180002d4c  mov     [rsp+14F0h+var_14C4], eax
0x180002d50  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002d55  mov     ebx, eax
0x180002d57  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002d5f  mov     ecx, r15d
0x180002d62  lea     eax, [r15+8]
0x180002d66  cmp     dword ptr [rdx+8], 1
0x180002d6a  cmovz   ecx, eax
0x180002d6d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002d71  lea     ecx, [rax-7]
0x180002d74  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002d7c  inc     ecx
0x180002d7e  mov     [rsp+14F0h+var_14C0], ecx
0x180002d82  mov     [rsp+14F0h+var_14B8], r15
0x180002d87  call    cs:__imp_GetCurrentThreadId
0x180002d8d  mov     [rsp+14F0h+var_14B0], eax
0x180002d91  lea     rax, aWil; "wil"
0x180002d98  mov     [rsp+14F0h+var_1498], rax
0x180002d9d  mov     [rsp+14F0h+var_1490], esi
0x180002da1  mov     [rsp+14F0h+var_148C], ebx
0x180002da5  mov     [rsp+14F0h+var_14A8], r15
0x180002daa  mov     [rsp+14F0h+var_14A0], r15
0x180002daf  mov     [rbp+13F0h+var_1448], rdi
0x180002db3  mov     [rbp+13F0h+var_1440], r14
0x180002db7  mov     [rsp+14F0h+var_1488], r15
0x180002dbc  xorps   xmm0, xmm0
0x180002dbf  xor     eax, eax
0x180002dc1  movups  [rbp+13F0h+var_1468], xmm0
0x180002dc5  mov     [rbp+13F0h+var_1458], rax
0x180002dc9  xorps   xmm1, xmm1
0x180002dcc  movups  [rsp+14F0h+var_1480], xmm1
0x180002dd1  mov     [rbp+13F0h+var_1470], rax
0x180002dd5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002ddc  test    rax, rax
0x180002ddf  jz      short loc_180002DEC
0x180002de1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de6  mov     [rbp+13F0h+var_1450], rax
0x180002dea  jmp     short loc_180002DF0
0x180002dec  mov     [rbp+13F0h+var_1450], r15
0x180002df0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002df7  test    rax, rax
0x180002dfa  jz      short loc_180002E06
0x180002dfc  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e06  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002e0d  test    rax, rax
0x180002e10  jz      short loc_180002E26
0x180002e12  mov     r8d, 400h
0x180002e18  lea     rdx, [rbp+13F0h+var_1430]
0x180002e1c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e26  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002e2d  test    rax, rax
0x180002e30  jz      short loc_180002E3C
0x180002e32  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e3c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002e43  test    rax, rax
0x180002e46  jz      short loc_180002E59
0x180002e48  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002e4d  jnz     short loc_180002E59
0x180002e4f  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e59  cmp     [rsp+14F0h+var_14C8], r15d
0x180002e5e  jge     loc_180002F6C
0x180002e64  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002e6b  jnz     short loc_180002E8C
0x180002e6d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002e74  test    rax, rax
0x180002e77  jz      short loc_180002E82
0x180002e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e7e  test    al, al
0x180002e80  jmp     short loc_180002E8A
0x180002e82  call    cs:__imp_IsDebuggerPresent
0x180002e88  test    eax, eax
0x180002e8a  jz      short loc_180002E93
0x180002e8c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002e91  jz      short loc_180002EB9
0x180002e93  mov     rax, cs:g_pfnResultLoggingCallback
0x180002e9a  test    rax, rax
0x180002e9d  jz      short loc_180002F12
0x180002e9f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002ea6  jnz     short loc_180002F12
0x180002ea8  xor     r8d, r8d
0x180002eab  xor     edx, edx
0x180002ead  lea     rcx, [rsp+14F0h+var_14D0]
0x180002eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002eb7  jmp     short loc_180002F12
0x180002eb9  mov     ebx, 800h
0x180002ebe  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ec5  test    rax, rax
0x180002ec8  jz      short loc_180002EE7
0x180002eca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002ed1  jnz     short loc_180002EE7
0x180002ed3  mov     r8d, ebx
0x180002ed6  lea     rdx, [rbp+13F0h+OutputString]
0x180002edd  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ee2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ee7  cmp     [rbp+13F0h+OutputString], r15w
0x180002eef  jnz     short loc_180002F05
0x180002ef1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002ef6  mov     rdx, rbx; unsigned __int16 *
0x180002ef9  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002f00  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002f05  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002f0c  call    cs:__imp_OutputDebugStringW
0x180002f12  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002f17  jnz     short loc_180002F22
0x180002f19  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002f20  jz      short loc_180002F34
0x180002f22  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002f29  test    rax, rax
0x180002f2c  jz      short loc_180002F34
0x180002f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f33  nop
0x180002f34  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002f39  jnz     short loc_180002F61
0x180002f3b  mov     rcx, [rbp+13F0h+var_30]
0x180002f42  xor     rcx, rsp; StackCookie
0x180002f45  call    __security_check_cookie
0x180002f4a  mov     rbx, [rsp+14F0h+arg_10]
0x180002f52  add     rsp, 14D0h
0x180002f59  pop     r15
0x180002f5b  pop     r14
0x180002f5d  pop     rdi
0x180002f5e  pop     rsi
0x180002f5f  pop     rbp
0x180002f60  retn
0x180002f61  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002f66  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002f6c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
