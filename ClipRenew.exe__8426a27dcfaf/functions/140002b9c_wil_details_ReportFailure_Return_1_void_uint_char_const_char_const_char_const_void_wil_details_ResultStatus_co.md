# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002b9c`
- end: `0x140002e30`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000267c`

## callees

- `0x140002b9c`
- `0x140003b24`
- `0x140004b90`
- `0x140005410`
- `0x1400054ec`
- `0x14001346e`
- `0x1400134a0`
- `0x140013530`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002c46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002c46`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002dcb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002dcb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002d41`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002d41`

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
0x140002b9c  mov     [rsp-8+arg_10], rbx
0x140002ba1  push    rbp
0x140002ba2  push    rsi
0x140002ba3  push    rdi
0x140002ba4  push    r14
0x140002ba6  push    r15
0x140002ba8  lea     rbp, [rsp-13D0h]
0x140002bb0  mov     eax, 14D0h
0x140002bb5  call    _alloca_probe
0x140002bba  sub     rsp, rax
0x140002bbd  mov     rax, cs:__security_cookie
0x140002bc4  xor     rax, rsp
0x140002bc7  mov     [rbp+13F0h+var_30], rax
0x140002bce  mov     rdi, [rbp+13F0h+arg_28]
0x140002bd5  mov     esi, edx
0x140002bd7  mov     r14, rcx
0x140002bda  xor     edx, edx; Val
0x140002bdc  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140002be1  mov     r8d, 98h; Size
0x140002be7  call    memset_0
0x140002bec  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140002bf3  xor     r15d, r15d
0x140002bf6  mov     [rbp+13F0h+OutputString], r15w
0x140002bfe  mov     [rbp+13F0h+var_1430], r15b
0x140002c02  mov     ecx, [rdx]; this
0x140002c04  mov     eax, [rdx+4]
0x140002c07  mov     [rsp+14F0h+var_14C8], ecx
0x140002c0b  mov     [rsp+14F0h+var_14C4], eax
0x140002c0f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002c14  cmp     dword ptr [rdx+8], 1
0x140002c18  mov     ebx, eax
0x140002c1a  lea     eax, [r15+8]
0x140002c1e  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x140002c26  mov     ecx, r15d
0x140002c29  cmovz   ecx, eax
0x140002c2c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002c30  lea     ecx, [rax-7]
0x140002c33  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002c3b  inc     ecx
0x140002c3d  mov     [rsp+14F0h+var_14B8], r15
0x140002c42  mov     [rsp+14F0h+var_14C0], ecx
0x140002c46  call    cs:__imp_GetCurrentThreadId
0x140002c4c  xorps   xmm0, xmm0
0x140002c4f  mov     [rsp+14F0h+var_1490], esi
0x140002c53  mov     [rsp+14F0h+var_14B0], eax
0x140002c57  xorps   xmm1, xmm1
0x140002c5a  lea     rax, aWil; "wil"
0x140002c61  mov     [rsp+14F0h+var_148C], ebx
0x140002c65  mov     [rsp+14F0h+var_1498], rax
0x140002c6a  xor     eax, eax
0x140002c6c  mov     [rbp+13F0h+var_1458], rax
0x140002c70  mov     [rbp+13F0h+var_1470], rax
0x140002c74  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002c7b  mov     [rsp+14F0h+var_14A8], r15
0x140002c80  mov     [rsp+14F0h+var_14A0], r15
0x140002c85  mov     [rbp+13F0h+var_1448], rdi
0x140002c89  mov     [rbp+13F0h+var_1440], r14
0x140002c8d  mov     [rsp+14F0h+var_1488], r15
0x140002c92  movups  [rbp+13F0h+var_1468], xmm0
0x140002c96  movups  [rsp+14F0h+var_1480], xmm1
0x140002c9b  test    rax, rax
0x140002c9e  jz      short loc_140002CAB
0x140002ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ca5  mov     [rbp+13F0h+var_1450], rax
0x140002ca9  jmp     short loc_140002CAF
0x140002cab  mov     [rbp+13F0h+var_1450], r15
0x140002caf  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002cb6  test    rax, rax
0x140002cb9  jz      short loc_140002CC5
0x140002cbb  lea     rcx, [rsp+14F0h+var_14D0]
0x140002cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cc5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002ccc  test    rax, rax
0x140002ccf  jz      short loc_140002CE5
0x140002cd1  mov     r8d, 400h
0x140002cd7  lea     rdx, [rbp+13F0h+var_1430]
0x140002cdb  lea     rcx, [rsp+14F0h+var_14D0]
0x140002ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ce5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002cec  test    rax, rax
0x140002cef  jz      short loc_140002CFB
0x140002cf1  lea     rcx, [rsp+14F0h+var_14D0]
0x140002cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002cfb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002d02  test    rax, rax
0x140002d05  jz      short loc_140002D18
0x140002d07  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002d0c  jnz     short loc_140002D18
0x140002d0e  lea     rcx, [rsp+14F0h+var_14D0]
0x140002d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d18  cmp     [rsp+14F0h+var_14C8], r15d
0x140002d1d  jge     loc_140002E1F
0x140002d23  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140002d2a  jnz     short loc_140002D4B
0x140002d2c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002d33  test    rax, rax
0x140002d36  jz      short loc_140002D41
0x140002d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d3d  test    al, al
0x140002d3f  jmp     short loc_140002D49
0x140002d41  call    cs:__imp_IsDebuggerPresent
0x140002d47  test    eax, eax
0x140002d49  jz      short loc_140002D52
0x140002d4b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002d50  jz      short loc_140002D78
0x140002d52  mov     rax, cs:g_pfnResultLoggingCallback
0x140002d59  test    rax, rax
0x140002d5c  jz      short loc_140002DD1
0x140002d5e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002d65  jnz     short loc_140002DD1
0x140002d67  xor     r8d, r8d
0x140002d6a  lea     rcx, [rsp+14F0h+var_14D0]
0x140002d6f  xor     edx, edx
0x140002d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d76  jmp     short loc_140002DD1
0x140002d78  mov     rax, cs:g_pfnResultLoggingCallback
0x140002d7f  mov     ebx, 800h
0x140002d84  test    rax, rax
0x140002d87  jz      short loc_140002DA6
0x140002d89  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002d90  jnz     short loc_140002DA6
0x140002d92  mov     r8d, ebx
0x140002d95  lea     rdx, [rbp+13F0h+OutputString]
0x140002d9c  lea     rcx, [rsp+14F0h+var_14D0]
0x140002da1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002da6  cmp     [rbp+13F0h+OutputString], r15w
0x140002dae  jnz     short loc_140002DC4
0x140002db0  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140002db5  mov     rdx, rbx; unsigned __int16 *
0x140002db8  lea     rcx, [rbp+13F0h+OutputString]; this
0x140002dbf  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002dc4  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140002dcb  call    cs:__imp_OutputDebugStringW
0x140002dd1  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140002dd6  jnz     short loc_140002DE1
0x140002dd8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140002ddf  jz      short loc_140002DF2
0x140002de1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002de8  test    rax, rax
0x140002deb  jz      short loc_140002DF2
0x140002ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002df2  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140002df7  jnz     short loc_140002E25
0x140002df9  mov     rcx, [rbp+13F0h+var_30]
0x140002e00  xor     rcx, rsp; StackCookie
0x140002e03  call    __security_check_cookie
0x140002e08  mov     rbx, [rsp+14F0h+arg_10]
0x140002e10  add     rsp, 14D0h
0x140002e17  pop     r15
0x140002e19  pop     r14
0x140002e1b  pop     rdi
0x140002e1c  pop     rsi
0x140002e1d  pop     rbp
0x140002e1e  retn
0x140002e1f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002e25  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002e2a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
