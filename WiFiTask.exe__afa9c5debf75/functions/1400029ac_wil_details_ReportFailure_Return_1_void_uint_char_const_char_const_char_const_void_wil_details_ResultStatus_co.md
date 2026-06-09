# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400029ac`
- end: `0x140002c42`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000248c`

## callees

- `0x1400016a0`
- `0x140002168`
- `0x1400029ac`
- `0x14000623c`
- `0x140008768`
- `0x14000b350`
- `0x14000b51c`
- `0x140010d80`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002a57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002a57`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002bdc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002bdc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002b52`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002b52`

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
0x1400029ac  mov     [rsp-8+arg_10], rbx
0x1400029b1  push    rbp
0x1400029b2  push    rsi
0x1400029b3  push    rdi
0x1400029b4  push    r14
0x1400029b6  push    r15
0x1400029b8  lea     rbp, [rsp-13D0h]
0x1400029c0  mov     eax, 14D0h
0x1400029c5  call    _alloca_probe
0x1400029ca  sub     rsp, rax
0x1400029cd  mov     rax, cs:__security_cookie
0x1400029d4  xor     rax, rsp
0x1400029d7  mov     [rbp+13F0h+var_30], rax
0x1400029de  mov     esi, edx
0x1400029e0  mov     r14, rcx
0x1400029e3  mov     rdi, [rbp+13F0h+arg_28]
0x1400029ea  xor     edx, edx; Val
0x1400029ec  mov     r8d, 98h; Size
0x1400029f2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400029f7  call    memset_0
0x1400029fc  nop
0x1400029fd  xor     r15d, r15d
0x140002a00  mov     [rbp+13F0h+OutputString], r15w
0x140002a08  mov     [rbp+13F0h+var_1430], r15b
0x140002a0c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140002a13  mov     ecx, [rdx]; this
0x140002a15  mov     [rsp+14F0h+var_14C8], ecx
0x140002a19  mov     eax, [rdx+4]
0x140002a1c  mov     [rsp+14F0h+var_14C4], eax
0x140002a20  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002a25  mov     ebx, eax
0x140002a27  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x140002a2f  mov     ecx, r15d
0x140002a32  lea     eax, [r15+8]
0x140002a36  cmp     dword ptr [rdx+8], 1
0x140002a3a  cmovz   ecx, eax
0x140002a3d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002a41  lea     ecx, [rax-7]
0x140002a44  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002a4c  inc     ecx
0x140002a4e  mov     [rsp+14F0h+var_14C0], ecx
0x140002a52  mov     [rsp+14F0h+var_14B8], r15
0x140002a57  call    cs:__imp_GetCurrentThreadId
0x140002a5d  mov     [rsp+14F0h+var_14B0], eax
0x140002a61  lea     rax, aWil; "wil"
0x140002a68  mov     [rsp+14F0h+var_1498], rax
0x140002a6d  mov     [rsp+14F0h+var_1490], esi
0x140002a71  mov     [rsp+14F0h+var_148C], ebx
0x140002a75  mov     [rsp+14F0h+var_14A8], r15
0x140002a7a  mov     [rsp+14F0h+var_14A0], r15
0x140002a7f  mov     [rbp+13F0h+var_1448], rdi
0x140002a83  mov     [rbp+13F0h+var_1440], r14
0x140002a87  mov     [rsp+14F0h+var_1488], r15
0x140002a8c  xorps   xmm0, xmm0
0x140002a8f  xor     eax, eax
0x140002a91  movups  [rbp+13F0h+var_1468], xmm0
0x140002a95  mov     [rbp+13F0h+var_1458], rax
0x140002a99  xorps   xmm1, xmm1
0x140002a9c  movups  [rsp+14F0h+var_1480], xmm1
0x140002aa1  mov     [rbp+13F0h+var_1470], rax
0x140002aa5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002aac  test    rax, rax
0x140002aaf  jz      short loc_140002ABC
0x140002ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ab6  mov     [rbp+13F0h+var_1450], rax
0x140002aba  jmp     short loc_140002AC0
0x140002abc  mov     [rbp+13F0h+var_1450], r15
0x140002ac0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002ac7  test    rax, rax
0x140002aca  jz      short loc_140002AD6
0x140002acc  lea     rcx, [rsp+14F0h+var_14D0]
0x140002ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ad6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002add  test    rax, rax
0x140002ae0  jz      short loc_140002AF6
0x140002ae2  mov     r8d, 400h
0x140002ae8  lea     rdx, [rbp+13F0h+var_1430]
0x140002aec  lea     rcx, [rsp+14F0h+var_14D0]
0x140002af1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002af6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002afd  test    rax, rax
0x140002b00  jz      short loc_140002B0C
0x140002b02  lea     rcx, [rsp+14F0h+var_14D0]
0x140002b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b0c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002b13  test    rax, rax
0x140002b16  jz      short loc_140002B29
0x140002b18  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002b1d  jnz     short loc_140002B29
0x140002b1f  lea     rcx, [rsp+14F0h+var_14D0]
0x140002b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b29  cmp     [rsp+14F0h+var_14C8], r15d
0x140002b2e  jge     loc_140002C3C
0x140002b34  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140002b3b  jnz     short loc_140002B5C
0x140002b3d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002b44  test    rax, rax
0x140002b47  jz      short loc_140002B52
0x140002b49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b4e  test    al, al
0x140002b50  jmp     short loc_140002B5A
0x140002b52  call    cs:__imp_IsDebuggerPresent
0x140002b58  test    eax, eax
0x140002b5a  jz      short loc_140002B63
0x140002b5c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002b61  jz      short loc_140002B89
0x140002b63  mov     rax, cs:g_pfnResultLoggingCallback
0x140002b6a  test    rax, rax
0x140002b6d  jz      short loc_140002BE2
0x140002b6f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002b76  jnz     short loc_140002BE2
0x140002b78  xor     r8d, r8d
0x140002b7b  xor     edx, edx
0x140002b7d  lea     rcx, [rsp+14F0h+var_14D0]
0x140002b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b87  jmp     short loc_140002BE2
0x140002b89  mov     ebx, 800h
0x140002b8e  mov     rax, cs:g_pfnResultLoggingCallback
0x140002b95  test    rax, rax
0x140002b98  jz      short loc_140002BB7
0x140002b9a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002ba1  jnz     short loc_140002BB7
0x140002ba3  mov     r8d, ebx
0x140002ba6  lea     rdx, [rbp+13F0h+OutputString]
0x140002bad  lea     rcx, [rsp+14F0h+var_14D0]
0x140002bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bb7  cmp     [rbp+13F0h+OutputString], r15w
0x140002bbf  jnz     short loc_140002BD5
0x140002bc1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140002bc6  mov     rdx, rbx; unsigned __int16 *
0x140002bc9  lea     rcx, [rbp+13F0h+OutputString]; this
0x140002bd0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002bd5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140002bdc  call    cs:__imp_OutputDebugStringW
0x140002be2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140002be7  jnz     short loc_140002BF2
0x140002be9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140002bf0  jz      short loc_140002C04
0x140002bf2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002bf9  test    rax, rax
0x140002bfc  jz      short loc_140002C04
0x140002bfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c03  nop
0x140002c04  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140002c09  jnz     short loc_140002C31
0x140002c0b  mov     rcx, [rbp+13F0h+var_30]
0x140002c12  xor     rcx, rsp; StackCookie
0x140002c15  call    __security_check_cookie
0x140002c1a  mov     rbx, [rsp+14F0h+arg_10]
0x140002c22  add     rsp, 14D0h
0x140002c29  pop     r15
0x140002c2b  pop     r14
0x140002c2d  pop     rdi
0x140002c2e  pop     rsi
0x140002c2f  pop     rbp
0x140002c30  retn
0x140002c31  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002c36  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002c3c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
