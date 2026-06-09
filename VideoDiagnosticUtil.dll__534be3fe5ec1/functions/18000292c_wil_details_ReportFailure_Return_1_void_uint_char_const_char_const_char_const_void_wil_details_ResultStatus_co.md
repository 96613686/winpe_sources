# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000292c`
- end: `0x180002bd3`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `679`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800023f4`

## callees

- `0x18000292c`
- `0x1800043bc`
- `0x180005ab0`
- `0x180007698`
- `0x18000786c`
- `0x18000967e`
- `0x1800096b0`
- `0x180009740`
- `0x18000a010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180002b67`
- `KERNEL32!OutputDebugStringW` at `0x180002b67`
- `KERNEL32!GetCurrentThreadId` at `0x1800029d6`
- `KERNEL32!GetCurrentThreadId` at `0x1800029d6`
- `KERNEL32!IsDebuggerPresent` at `0x180002ad7`
- `KERNEL32!IsDebuggerPresent` at `0x180002ad7`

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
0x18000292c  mov     [rsp-8+arg_10], rbx
0x180002931  push    rbp
0x180002932  push    rsi
0x180002933  push    rdi
0x180002934  push    r14
0x180002936  push    r15
0x180002938  lea     rbp, [rsp-13D0h]
0x180002940  mov     eax, 14D0h
0x180002945  call    _alloca_probe
0x18000294a  sub     rsp, rax
0x18000294d  mov     rax, cs:__security_cookie
0x180002954  xor     rax, rsp
0x180002957  mov     [rbp+13F0h+var_30], rax
0x18000295e  mov     rdi, [rbp+13F0h+arg_28]
0x180002965  mov     esi, edx
0x180002967  mov     r14, rcx
0x18000296a  xor     edx, edx; Val
0x18000296c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002971  mov     r8d, 98h; Size
0x180002977  call    memset_0
0x18000297c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002983  xor     r15d, r15d
0x180002986  mov     [rbp+13F0h+OutputString], r15w
0x18000298e  mov     [rbp+13F0h+var_1430], r15b
0x180002992  mov     ecx, [rdx]; this
0x180002994  mov     eax, [rdx+4]
0x180002997  mov     [rsp+14F0h+var_14C8], ecx
0x18000299b  mov     [rsp+14F0h+var_14C4], eax
0x18000299f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800029a4  cmp     dword ptr [rdx+8], 1
0x1800029a8  mov     ebx, eax
0x1800029aa  lea     eax, [r15+8]
0x1800029ae  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800029b6  mov     ecx, r15d
0x1800029b9  cmovz   ecx, eax
0x1800029bc  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800029c0  lea     ecx, [rax-7]
0x1800029c3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800029cb  inc     ecx
0x1800029cd  mov     [rsp+14F0h+var_14B8], r15
0x1800029d2  mov     [rsp+14F0h+var_14C0], ecx
0x1800029d6  call    cs:__imp_GetCurrentThreadId
0x1800029dd  nop     dword ptr [rax+rax+00h]
0x1800029e2  xorps   xmm0, xmm0
0x1800029e5  mov     [rsp+14F0h+var_1490], esi
0x1800029e9  mov     [rsp+14F0h+var_14B0], eax
0x1800029ed  xorps   xmm1, xmm1
0x1800029f0  lea     rax, aWil; "wil"
0x1800029f7  mov     [rsp+14F0h+var_148C], ebx
0x1800029fb  mov     [rsp+14F0h+var_1498], rax
0x180002a00  xor     eax, eax
0x180002a02  mov     [rbp+13F0h+var_1458], rax
0x180002a06  mov     [rbp+13F0h+var_1470], rax
0x180002a0a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002a11  mov     [rsp+14F0h+var_14A8], r15
0x180002a16  mov     [rsp+14F0h+var_14A0], r15
0x180002a1b  mov     [rbp+13F0h+var_1448], rdi
0x180002a1f  mov     [rbp+13F0h+var_1440], r14
0x180002a23  mov     [rsp+14F0h+var_1488], r15
0x180002a28  movups  [rbp+13F0h+var_1468], xmm0
0x180002a2c  movups  [rsp+14F0h+var_1480], xmm1
0x180002a31  test    rax, rax
0x180002a34  jz      short loc_180002A41
0x180002a36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a3b  mov     [rbp+13F0h+var_1450], rax
0x180002a3f  jmp     short loc_180002A45
0x180002a41  mov     [rbp+13F0h+var_1450], r15
0x180002a45  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002a4c  test    rax, rax
0x180002a4f  jz      short loc_180002A5B
0x180002a51  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a5b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002a62  test    rax, rax
0x180002a65  jz      short loc_180002A7B
0x180002a67  mov     r8d, 400h
0x180002a6d  lea     rdx, [rbp+13F0h+var_1430]
0x180002a71  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a7b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002a82  test    rax, rax
0x180002a85  jz      short loc_180002A91
0x180002a87  lea     rcx, [rsp+14F0h+var_14D0]
0x180002a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a91  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002a98  test    rax, rax
0x180002a9b  jz      short loc_180002AAE
0x180002a9d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002aa2  jnz     short loc_180002AAE
0x180002aa4  lea     rcx, [rsp+14F0h+var_14D0]
0x180002aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002aae  cmp     [rsp+14F0h+var_14C8], r15d
0x180002ab3  jge     loc_180002BC2
0x180002ab9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002ac0  jnz     short loc_180002AE7
0x180002ac2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002ac9  test    rax, rax
0x180002acc  jz      short loc_180002AD7
0x180002ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ad3  test    al, al
0x180002ad5  jmp     short loc_180002AE5
0x180002ad7  call    cs:__imp_IsDebuggerPresent
0x180002ade  nop     dword ptr [rax+rax+00h]
0x180002ae3  test    eax, eax
0x180002ae5  jz      short loc_180002AEE
0x180002ae7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002aec  jz      short loc_180002B14
0x180002aee  mov     rax, cs:g_pfnResultLoggingCallback
0x180002af5  test    rax, rax
0x180002af8  jz      short loc_180002B73
0x180002afa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002b01  jnz     short loc_180002B73
0x180002b03  xor     r8d, r8d
0x180002b06  lea     rcx, [rsp+14F0h+var_14D0]
0x180002b0b  xor     edx, edx
0x180002b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b12  jmp     short loc_180002B73
0x180002b14  mov     rax, cs:g_pfnResultLoggingCallback
0x180002b1b  mov     ebx, 800h
0x180002b20  test    rax, rax
0x180002b23  jz      short loc_180002B42
0x180002b25  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002b2c  jnz     short loc_180002B42
0x180002b2e  mov     r8d, ebx
0x180002b31  lea     rdx, [rbp+13F0h+OutputString]
0x180002b38  lea     rcx, [rsp+14F0h+var_14D0]
0x180002b3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b42  cmp     [rbp+13F0h+OutputString], r15w
0x180002b4a  jnz     short loc_180002B60
0x180002b4c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002b51  mov     rdx, rbx; unsigned __int16 *
0x180002b54  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002b5b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002b60  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002b67  call    cs:__imp_OutputDebugStringW
0x180002b6e  nop     dword ptr [rax+rax+00h]
0x180002b73  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002b78  jnz     short loc_180002B83
0x180002b7a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002b81  jz      short loc_180002B94
0x180002b83  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002b8a  test    rax, rax
0x180002b8d  jz      short loc_180002B94
0x180002b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b94  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002b99  jnz     short loc_180002BC8
0x180002b9b  mov     rcx, [rbp+13F0h+var_30]
0x180002ba2  xor     rcx, rsp; StackCookie
0x180002ba5  call    __security_check_cookie
0x180002baa  mov     rbx, [rsp+14F0h+arg_10]
0x180002bb2  add     rsp, 14D0h
0x180002bb9  pop     r15
0x180002bbb  pop     r14
0x180002bbd  pop     rdi
0x180002bbe  pop     rsi
0x180002bbf  pop     rbp
0x180002bc0  retn
0x180002bc2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180002bc8  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002bcd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
