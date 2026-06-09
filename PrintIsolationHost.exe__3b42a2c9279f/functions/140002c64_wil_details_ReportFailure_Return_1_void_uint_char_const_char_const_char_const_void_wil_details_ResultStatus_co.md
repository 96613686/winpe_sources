# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002c64`
- end: `0x140002ef8`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000274c`

## callees

- `0x140001cd0`
- `0x140002690`
- `0x140002c64`
- `0x140003b74`
- `0x140004bb0`
- `0x1400057c0`
- `0x14000589c`
- `0x140007710`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002d0e`
- `KERNEL32!GetCurrentThreadId` at `0x140002d0e`
- `KERNEL32!OutputDebugStringW` at `0x140002e93`
- `KERNEL32!OutputDebugStringW` at `0x140002e93`
- `KERNEL32!IsDebuggerPresent` at `0x140002e09`
- `KERNEL32!IsDebuggerPresent` at `0x140002e09`

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
0x140002c64  mov     [rsp-8+arg_10], rbx
0x140002c69  push    rbp
0x140002c6a  push    rsi
0x140002c6b  push    rdi
0x140002c6c  push    r14
0x140002c6e  push    r15
0x140002c70  lea     rbp, [rsp-13D0h]
0x140002c78  mov     eax, 14D0h
0x140002c7d  call    _alloca_probe
0x140002c82  sub     rsp, rax
0x140002c85  mov     rax, cs:__security_cookie
0x140002c8c  xor     rax, rsp
0x140002c8f  mov     [rbp+13F0h+var_30], rax
0x140002c96  mov     rdi, [rbp+13F0h+arg_28]
0x140002c9d  mov     esi, edx
0x140002c9f  mov     r14, rcx
0x140002ca2  xor     edx, edx; Val
0x140002ca4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140002ca9  mov     r8d, 98h; Size
0x140002caf  call    memset_0
0x140002cb4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140002cbb  xor     r15d, r15d
0x140002cbe  mov     [rbp+13F0h+OutputString], r15w
0x140002cc6  mov     [rbp+13F0h+var_1430], r15b
0x140002cca  mov     ecx, [rdx]; this
0x140002ccc  mov     eax, [rdx+4]
0x140002ccf  mov     [rsp+14F0h+var_14C8], ecx
0x140002cd3  mov     [rsp+14F0h+var_14C4], eax
0x140002cd7  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002cdc  cmp     dword ptr [rdx+8], 1
0x140002ce0  mov     ebx, eax
0x140002ce2  lea     eax, [r15+8]
0x140002ce6  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x140002cee  mov     ecx, r15d
0x140002cf1  cmovz   ecx, eax
0x140002cf4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002cf8  lea     ecx, [rax-7]
0x140002cfb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002d03  inc     ecx
0x140002d05  mov     [rsp+14F0h+var_14B8], r15
0x140002d0a  mov     [rsp+14F0h+var_14C0], ecx
0x140002d0e  call    cs:__imp_GetCurrentThreadId
0x140002d14  xorps   xmm0, xmm0
0x140002d17  mov     [rsp+14F0h+var_1490], esi
0x140002d1b  mov     [rsp+14F0h+var_14B0], eax
0x140002d1f  xorps   xmm1, xmm1
0x140002d22  lea     rax, aWil; "wil"
0x140002d29  mov     [rsp+14F0h+var_148C], ebx
0x140002d2d  mov     [rsp+14F0h+var_1498], rax
0x140002d32  xor     eax, eax
0x140002d34  mov     [rbp+13F0h+var_1458], rax
0x140002d38  mov     [rbp+13F0h+var_1470], rax
0x140002d3c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002d43  mov     [rsp+14F0h+var_14A8], r15
0x140002d48  mov     [rsp+14F0h+var_14A0], r15
0x140002d4d  mov     [rbp+13F0h+var_1448], rdi
0x140002d51  mov     [rbp+13F0h+var_1440], r14
0x140002d55  mov     [rsp+14F0h+var_1488], r15
0x140002d5a  movups  [rbp+13F0h+var_1468], xmm0
0x140002d5e  movups  [rsp+14F0h+var_1480], xmm1
0x140002d63  test    rax, rax
0x140002d66  jz      short loc_140002D73
0x140002d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d6d  mov     [rbp+13F0h+var_1450], rax
0x140002d71  jmp     short loc_140002D77
0x140002d73  mov     [rbp+13F0h+var_1450], r15
0x140002d77  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002d7e  test    rax, rax
0x140002d81  jz      short loc_140002D8D
0x140002d83  lea     rcx, [rsp+14F0h+var_14D0]
0x140002d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d8d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002d94  test    rax, rax
0x140002d97  jz      short loc_140002DAD
0x140002d99  mov     r8d, 400h
0x140002d9f  lea     rdx, [rbp+13F0h+var_1430]
0x140002da3  lea     rcx, [rsp+14F0h+var_14D0]
0x140002da8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002dad  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002db4  test    rax, rax
0x140002db7  jz      short loc_140002DC3
0x140002db9  lea     rcx, [rsp+14F0h+var_14D0]
0x140002dbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002dc3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002dca  test    rax, rax
0x140002dcd  jz      short loc_140002DE0
0x140002dcf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002dd4  jnz     short loc_140002DE0
0x140002dd6  lea     rcx, [rsp+14F0h+var_14D0]
0x140002ddb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002de0  cmp     [rsp+14F0h+var_14C8], r15d
0x140002de5  jge     loc_140002EE7
0x140002deb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140002df2  jnz     short loc_140002E13
0x140002df4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002dfb  test    rax, rax
0x140002dfe  jz      short loc_140002E09
0x140002e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e05  test    al, al
0x140002e07  jmp     short loc_140002E11
0x140002e09  call    cs:__imp_IsDebuggerPresent
0x140002e0f  test    eax, eax
0x140002e11  jz      short loc_140002E1A
0x140002e13  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002e18  jz      short loc_140002E40
0x140002e1a  mov     rax, cs:g_pfnResultLoggingCallback
0x140002e21  test    rax, rax
0x140002e24  jz      short loc_140002E99
0x140002e26  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002e2d  jnz     short loc_140002E99
0x140002e2f  xor     r8d, r8d
0x140002e32  lea     rcx, [rsp+14F0h+var_14D0]
0x140002e37  xor     edx, edx
0x140002e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e3e  jmp     short loc_140002E99
0x140002e40  mov     rax, cs:g_pfnResultLoggingCallback
0x140002e47  mov     ebx, 800h
0x140002e4c  test    rax, rax
0x140002e4f  jz      short loc_140002E6E
0x140002e51  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002e58  jnz     short loc_140002E6E
0x140002e5a  mov     r8d, ebx
0x140002e5d  lea     rdx, [rbp+13F0h+OutputString]
0x140002e64  lea     rcx, [rsp+14F0h+var_14D0]
0x140002e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e6e  cmp     [rbp+13F0h+OutputString], r15w
0x140002e76  jnz     short loc_140002E8C
0x140002e78  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140002e7d  mov     rdx, rbx; unsigned __int16 *
0x140002e80  lea     rcx, [rbp+13F0h+OutputString]; this
0x140002e87  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002e8c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140002e93  call    cs:__imp_OutputDebugStringW
0x140002e99  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140002e9e  jnz     short loc_140002EA9
0x140002ea0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140002ea7  jz      short loc_140002EBA
0x140002ea9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002eb0  test    rax, rax
0x140002eb3  jz      short loc_140002EBA
0x140002eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002eba  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140002ebf  jnz     short loc_140002EED
0x140002ec1  mov     rcx, [rbp+13F0h+var_30]
0x140002ec8  xor     rcx, rsp; StackCookie
0x140002ecb  call    __security_check_cookie
0x140002ed0  mov     rbx, [rsp+14F0h+arg_10]
0x140002ed8  add     rsp, 14D0h
0x140002edf  pop     r15
0x140002ee1  pop     r14
0x140002ee3  pop     rdi
0x140002ee4  pop     rsi
0x140002ee5  pop     rbp
0x140002ee6  retn
0x140002ee7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140002eed  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002ef2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
