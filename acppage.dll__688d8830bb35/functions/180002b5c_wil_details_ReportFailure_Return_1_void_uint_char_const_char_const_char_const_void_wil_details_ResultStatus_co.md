# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002b5c`
- end: `0x180002df0`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000263c`

## callees

- `0x180002b5c`
- `0x180004c84`
- `0x180006544`
- `0x1800080f0`
- `0x1800082c4`
- `0x18001623a`
- `0x180016280`
- `0x180016310`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180002c06`
- `KERNEL32!GetCurrentThreadId` at `0x180002c06`
- `KERNEL32!OutputDebugStringW` at `0x180002d8b`
- `KERNEL32!OutputDebugStringW` at `0x180002d8b`
- `KERNEL32!IsDebuggerPresent` at `0x180002d01`
- `KERNEL32!IsDebuggerPresent` at `0x180002d01`

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
0x180002b5c  mov     [rsp-8+arg_10], rbx
0x180002b61  push    rbp
0x180002b62  push    rsi
0x180002b63  push    rdi
0x180002b64  push    r14
0x180002b66  push    r15
0x180002b68  lea     rbp, [rsp-13D0h]
0x180002b70  mov     eax, 14D0h
0x180002b75  call    _alloca_probe
0x180002b7a  sub     rsp, rax
0x180002b7d  mov     rax, cs:__security_cookie
0x180002b84  xor     rax, rsp
0x180002b87  mov     [rbp+13F0h+var_30], rax
0x180002b8e  mov     rdi, [rbp+13F0h+arg_28]
0x180002b95  mov     esi, edx
0x180002b97  mov     r14, rcx
0x180002b9a  xor     edx, edx; Val
0x180002b9c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002ba1  mov     r8d, 98h; Size
0x180002ba7  call    memset_0
0x180002bac  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002bb3  xor     r15d, r15d
0x180002bb6  mov     [rbp+13F0h+OutputString], r15w
0x180002bbe  mov     [rbp+13F0h+var_1430], r15b
0x180002bc2  mov     ecx, [rdx]; this
0x180002bc4  mov     eax, [rdx+4]
0x180002bc7  mov     [rsp+14F0h+var_14C8], ecx
0x180002bcb  mov     [rsp+14F0h+var_14C4], eax
0x180002bcf  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002bd4  cmp     dword ptr [rdx+8], 1
0x180002bd8  mov     ebx, eax
0x180002bda  lea     eax, [r15+8]
0x180002bde  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002be6  mov     ecx, r15d
0x180002be9  cmovz   ecx, eax
0x180002bec  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002bf0  lea     ecx, [rax-7]
0x180002bf3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002bfb  inc     ecx
0x180002bfd  mov     [rsp+14F0h+var_14B8], r15
0x180002c02  mov     [rsp+14F0h+var_14C0], ecx
0x180002c06  call    cs:__imp_GetCurrentThreadId
0x180002c0c  xorps   xmm0, xmm0
0x180002c0f  mov     [rsp+14F0h+var_1490], esi
0x180002c13  mov     [rsp+14F0h+var_14B0], eax
0x180002c17  xorps   xmm1, xmm1
0x180002c1a  lea     rax, aWil; "wil"
0x180002c21  mov     [rsp+14F0h+var_148C], ebx
0x180002c25  mov     [rsp+14F0h+var_1498], rax
0x180002c2a  xor     eax, eax
0x180002c2c  mov     [rbp+13F0h+var_1458], rax
0x180002c30  mov     [rbp+13F0h+var_1470], rax
0x180002c34  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002c3b  mov     [rsp+14F0h+var_14A8], r15
0x180002c40  mov     [rsp+14F0h+var_14A0], r15
0x180002c45  mov     [rbp+13F0h+var_1448], rdi
0x180002c49  mov     [rbp+13F0h+var_1440], r14
0x180002c4d  mov     [rsp+14F0h+var_1488], r15
0x180002c52  movups  [rbp+13F0h+var_1468], xmm0
0x180002c56  movups  [rsp+14F0h+var_1480], xmm1
0x180002c5b  test    rax, rax
0x180002c5e  jz      short loc_180002C6B
0x180002c60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c65  mov     [rbp+13F0h+var_1450], rax
0x180002c69  jmp     short loc_180002C6F
0x180002c6b  mov     [rbp+13F0h+var_1450], r15
0x180002c6f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002c76  test    rax, rax
0x180002c79  jz      short loc_180002C85
0x180002c7b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c85  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002c8c  test    rax, rax
0x180002c8f  jz      short loc_180002CA5
0x180002c91  mov     r8d, 400h
0x180002c97  lea     rdx, [rbp+13F0h+var_1430]
0x180002c9b  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ca5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002cac  test    rax, rax
0x180002caf  jz      short loc_180002CBB
0x180002cb1  lea     rcx, [rsp+14F0h+var_14D0]
0x180002cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cbb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002cc2  test    rax, rax
0x180002cc5  jz      short loc_180002CD8
0x180002cc7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002ccc  jnz     short loc_180002CD8
0x180002cce  lea     rcx, [rsp+14F0h+var_14D0]
0x180002cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cd8  cmp     [rsp+14F0h+var_14C8], r15d
0x180002cdd  jge     loc_180002DDF
0x180002ce3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002cea  jnz     short loc_180002D0B
0x180002cec  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002cf3  test    rax, rax
0x180002cf6  jz      short loc_180002D01
0x180002cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cfd  test    al, al
0x180002cff  jmp     short loc_180002D09
0x180002d01  call    cs:__imp_IsDebuggerPresent
0x180002d07  test    eax, eax
0x180002d09  jz      short loc_180002D12
0x180002d0b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002d10  jz      short loc_180002D38
0x180002d12  mov     rax, cs:g_pfnResultLoggingCallback
0x180002d19  test    rax, rax
0x180002d1c  jz      short loc_180002D91
0x180002d1e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002d25  jnz     short loc_180002D91
0x180002d27  xor     r8d, r8d
0x180002d2a  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d2f  xor     edx, edx
0x180002d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d36  jmp     short loc_180002D91
0x180002d38  mov     rax, cs:g_pfnResultLoggingCallback
0x180002d3f  mov     ebx, 800h
0x180002d44  test    rax, rax
0x180002d47  jz      short loc_180002D66
0x180002d49  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002d50  jnz     short loc_180002D66
0x180002d52  mov     r8d, ebx
0x180002d55  lea     rdx, [rbp+13F0h+OutputString]
0x180002d5c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002d61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d66  cmp     [rbp+13F0h+OutputString], r15w
0x180002d6e  jnz     short loc_180002D84
0x180002d70  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002d75  mov     rdx, rbx; unsigned __int16 *
0x180002d78  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002d7f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002d84  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002d8b  call    cs:__imp_OutputDebugStringW
0x180002d91  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002d96  jnz     short loc_180002DA1
0x180002d98  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002d9f  jz      short loc_180002DB2
0x180002da1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002da8  test    rax, rax
0x180002dab  jz      short loc_180002DB2
0x180002dad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002db2  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002db7  jnz     short loc_180002DE5
0x180002db9  mov     rcx, [rbp+13F0h+var_30]
0x180002dc0  xor     rcx, rsp; StackCookie
0x180002dc3  call    __security_check_cookie
0x180002dc8  mov     rbx, [rsp+14F0h+arg_10]
0x180002dd0  add     rsp, 14D0h
0x180002dd7  pop     r15
0x180002dd9  pop     r14
0x180002ddb  pop     rdi
0x180002ddc  pop     rsi
0x180002ddd  pop     rbp
0x180002dde  retn
0x180002ddf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180002de5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002dea  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
