# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002cec`
- end: `0x180002f80`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800027cc`

## callees

- `0x180002cec`
- `0x180004e44`
- `0x180006544`
- `0x180008aa0`
- `0x180009474`
- `0x18001380e`
- `0x180013840`
- `0x1800138d0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d96`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002f1b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002f1b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002e91`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002e91`

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
0x180002cec  mov     [rsp-8+arg_10], rbx
0x180002cf1  push    rbp
0x180002cf2  push    rsi
0x180002cf3  push    rdi
0x180002cf4  push    r14
0x180002cf6  push    r15
0x180002cf8  lea     rbp, [rsp-13D0h]
0x180002d00  mov     eax, 14D0h
0x180002d05  call    _alloca_probe
0x180002d0a  sub     rsp, rax
0x180002d0d  mov     rax, cs:__security_cookie
0x180002d14  xor     rax, rsp
0x180002d17  mov     [rbp+13F0h+var_30], rax
0x180002d1e  mov     rdi, [rbp+13F0h+arg_28]
0x180002d25  mov     esi, edx
0x180002d27  mov     r14, rcx
0x180002d2a  xor     edx, edx; Val
0x180002d2c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002d31  mov     r8d, 98h; Size
0x180002d37  call    memset_0
0x180002d3c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002d43  xor     r15d, r15d
0x180002d46  mov     [rbp+13F0h+OutputString], r15w
0x180002d4e  mov     [rbp+13F0h+var_1430], r15b
0x180002d52  mov     ecx, [rdx]; this
0x180002d54  mov     eax, [rdx+4]
0x180002d57  mov     [rsp+14F0h+var_14C8], ecx
0x180002d5b  mov     [rsp+14F0h+var_14C4], eax
0x180002d5f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002d64  cmp     dword ptr [rdx+8], 1
0x180002d68  mov     ebx, eax
0x180002d6a  lea     eax, [r15+8]
0x180002d6e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002d76  mov     ecx, r15d
0x180002d79  cmovz   ecx, eax
0x180002d7c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002d80  lea     ecx, [rax-7]
0x180002d83  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002d8b  inc     ecx
0x180002d8d  mov     [rsp+14F0h+var_14B8], r15
0x180002d92  mov     [rsp+14F0h+var_14C0], ecx
0x180002d96  call    cs:__imp_GetCurrentThreadId
0x180002d9c  xorps   xmm0, xmm0
0x180002d9f  mov     [rsp+14F0h+var_1490], esi
0x180002da3  mov     [rsp+14F0h+var_14B0], eax
0x180002da7  xorps   xmm1, xmm1
0x180002daa  lea     rax, aWil; "wil"
0x180002db1  mov     [rsp+14F0h+var_148C], ebx
0x180002db5  mov     [rsp+14F0h+var_1498], rax
0x180002dba  xor     eax, eax
0x180002dbc  mov     [rbp+13F0h+var_1458], rax
0x180002dc0  mov     [rbp+13F0h+var_1470], rax
0x180002dc4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002dcb  mov     [rsp+14F0h+var_14A8], r15
0x180002dd0  mov     [rsp+14F0h+var_14A0], r15
0x180002dd5  mov     [rbp+13F0h+var_1448], rdi
0x180002dd9  mov     [rbp+13F0h+var_1440], r14
0x180002ddd  mov     [rsp+14F0h+var_1488], r15
0x180002de2  movups  [rbp+13F0h+var_1468], xmm0
0x180002de6  movups  [rsp+14F0h+var_1480], xmm1
0x180002deb  test    rax, rax
0x180002dee  jz      short loc_180002DFB
0x180002df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df5  mov     [rbp+13F0h+var_1450], rax
0x180002df9  jmp     short loc_180002DFF
0x180002dfb  mov     [rbp+13F0h+var_1450], r15
0x180002dff  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002e06  test    rax, rax
0x180002e09  jz      short loc_180002E15
0x180002e0b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e15  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002e1c  test    rax, rax
0x180002e1f  jz      short loc_180002E35
0x180002e21  mov     r8d, 400h
0x180002e27  lea     rdx, [rbp+13F0h+var_1430]
0x180002e2b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e35  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002e3c  test    rax, rax
0x180002e3f  jz      short loc_180002E4B
0x180002e41  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e4b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002e52  test    rax, rax
0x180002e55  jz      short loc_180002E68
0x180002e57  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002e5c  jnz     short loc_180002E68
0x180002e5e  lea     rcx, [rsp+14F0h+var_14D0]
0x180002e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e68  cmp     [rsp+14F0h+var_14C8], r15d
0x180002e6d  jge     loc_180002F6F
0x180002e73  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002e7a  jnz     short loc_180002E9B
0x180002e7c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002e83  test    rax, rax
0x180002e86  jz      short loc_180002E91
0x180002e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e8d  test    al, al
0x180002e8f  jmp     short loc_180002E99
0x180002e91  call    cs:__imp_IsDebuggerPresent
0x180002e97  test    eax, eax
0x180002e99  jz      short loc_180002EA2
0x180002e9b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002ea0  jz      short loc_180002EC8
0x180002ea2  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ea9  test    rax, rax
0x180002eac  jz      short loc_180002F21
0x180002eae  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002eb5  jnz     short loc_180002F21
0x180002eb7  xor     r8d, r8d
0x180002eba  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ebf  xor     edx, edx
0x180002ec1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ec6  jmp     short loc_180002F21
0x180002ec8  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ecf  mov     ebx, 800h
0x180002ed4  test    rax, rax
0x180002ed7  jz      short loc_180002EF6
0x180002ed9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002ee0  jnz     short loc_180002EF6
0x180002ee2  mov     r8d, ebx
0x180002ee5  lea     rdx, [rbp+13F0h+OutputString]
0x180002eec  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef6  cmp     [rbp+13F0h+OutputString], r15w
0x180002efe  jnz     short loc_180002F14
0x180002f00  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002f05  mov     rdx, rbx; unsigned __int16 *
0x180002f08  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002f0f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002f14  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002f1b  call    cs:__imp_OutputDebugStringW
0x180002f21  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002f26  jnz     short loc_180002F31
0x180002f28  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002f2f  jz      short loc_180002F42
0x180002f31  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002f38  test    rax, rax
0x180002f3b  jz      short loc_180002F42
0x180002f3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f42  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002f47  jnz     short loc_180002F75
0x180002f49  mov     rcx, [rbp+13F0h+var_30]
0x180002f50  xor     rcx, rsp; StackCookie
0x180002f53  call    __security_check_cookie
0x180002f58  mov     rbx, [rsp+14F0h+arg_10]
0x180002f60  add     rsp, 14D0h
0x180002f67  pop     r15
0x180002f69  pop     r14
0x180002f6b  pop     rdi
0x180002f6c  pop     rsi
0x180002f6d  pop     rbp
0x180002f6e  retn
0x180002f6f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180002f75  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002f7a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
