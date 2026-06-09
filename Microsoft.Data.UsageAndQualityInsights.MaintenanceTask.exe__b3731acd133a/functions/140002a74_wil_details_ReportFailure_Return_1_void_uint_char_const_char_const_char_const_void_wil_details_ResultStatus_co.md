# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002a74`
- end: `0x140002d0a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002554`

## callees

- `0x1400016f0`
- `0x14000221c`
- `0x140002a74`
- `0x140004d14`
- `0x140006538`
- `0x140008920`
- `0x140008aec`
- `0x14000b840`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002b1f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002b1f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002c1a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002c1a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002ca4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002ca4`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
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
0x140002a74  mov     [rsp-8+arg_10], rbx
0x140002a79  push    rbp
0x140002a7a  push    rsi
0x140002a7b  push    rdi
0x140002a7c  push    r14
0x140002a7e  push    r15
0x140002a80  lea     rbp, [rsp-13D0h]
0x140002a88  mov     eax, 14D0h
0x140002a8d  call    _alloca_probe
0x140002a92  sub     rsp, rax
0x140002a95  mov     rax, cs:__security_cookie
0x140002a9c  xor     rax, rsp
0x140002a9f  mov     [rbp+13F0h+var_30], rax
0x140002aa6  mov     esi, edx
0x140002aa8  mov     r14, rcx
0x140002aab  mov     rdi, [rbp+13F0h+arg_28]
0x140002ab2  xor     edx, edx; Val
0x140002ab4  mov     r8d, 98h; Size
0x140002aba  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140002abf  call    memset_0
0x140002ac4  nop
0x140002ac5  xor     r15d, r15d
0x140002ac8  mov     [rbp+13F0h+OutputString], r15w
0x140002ad0  mov     [rbp+13F0h+var_1430], r15b
0x140002ad4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140002adb  mov     ecx, [rdx]; this
0x140002add  mov     [rsp+14F0h+var_14C8], ecx
0x140002ae1  mov     eax, [rdx+4]
0x140002ae4  mov     [rsp+14F0h+var_14C4], eax
0x140002ae8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002aed  mov     ebx, eax
0x140002aef  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x140002af7  mov     ecx, r15d
0x140002afa  lea     eax, [r15+8]
0x140002afe  cmp     dword ptr [rdx+8], 1
0x140002b02  cmovz   ecx, eax
0x140002b05  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002b09  lea     ecx, [rax-7]
0x140002b0c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002b14  inc     ecx
0x140002b16  mov     [rsp+14F0h+var_14C0], ecx
0x140002b1a  mov     [rsp+14F0h+var_14B8], r15
0x140002b1f  call    cs:__imp_GetCurrentThreadId
0x140002b25  mov     [rsp+14F0h+var_14B0], eax
0x140002b29  lea     rax, aWil; "wil"
0x140002b30  mov     [rsp+14F0h+var_1498], rax
0x140002b35  mov     [rsp+14F0h+var_1490], esi
0x140002b39  mov     [rsp+14F0h+var_148C], ebx
0x140002b3d  mov     [rsp+14F0h+var_14A8], r15
0x140002b42  mov     [rsp+14F0h+var_14A0], r15
0x140002b47  mov     [rbp+13F0h+var_1448], rdi
0x140002b4b  mov     [rbp+13F0h+var_1440], r14
0x140002b4f  mov     [rsp+14F0h+var_1488], r15
0x140002b54  xorps   xmm0, xmm0
0x140002b57  xor     eax, eax
0x140002b59  movups  [rbp+13F0h+var_1468], xmm0
0x140002b5d  mov     [rbp+13F0h+var_1458], rax
0x140002b61  xorps   xmm1, xmm1
0x140002b64  movups  [rsp+14F0h+var_1480], xmm1
0x140002b69  mov     [rbp+13F0h+var_1470], rax
0x140002b6d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002b74  test    rax, rax
0x140002b77  jz      short loc_140002B84
0x140002b79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b7e  mov     [rbp+13F0h+var_1450], rax
0x140002b82  jmp     short loc_140002B88
0x140002b84  mov     [rbp+13F0h+var_1450], r15
0x140002b88  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002b8f  test    rax, rax
0x140002b92  jz      short loc_140002B9E
0x140002b94  lea     rcx, [rsp+14F0h+var_14D0]
0x140002b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002b9e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002ba5  test    rax, rax
0x140002ba8  jz      short loc_140002BBE
0x140002baa  mov     r8d, 400h
0x140002bb0  lea     rdx, [rbp+13F0h+var_1430]
0x140002bb4  lea     rcx, [rsp+14F0h+var_14D0]
0x140002bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bbe  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002bc5  test    rax, rax
0x140002bc8  jz      short loc_140002BD4
0x140002bca  lea     rcx, [rsp+14F0h+var_14D0]
0x140002bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bd4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002bdb  test    rax, rax
0x140002bde  jz      short loc_140002BF1
0x140002be0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002be5  jnz     short loc_140002BF1
0x140002be7  lea     rcx, [rsp+14F0h+var_14D0]
0x140002bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002bf1  cmp     [rsp+14F0h+var_14C8], r15d
0x140002bf6  jge     loc_140002D04
0x140002bfc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x140002c03  jnz     short loc_140002C24
0x140002c05  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002c0c  test    rax, rax
0x140002c0f  jz      short loc_140002C1A
0x140002c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c16  test    al, al
0x140002c18  jmp     short loc_140002C22
0x140002c1a  call    cs:__imp_IsDebuggerPresent
0x140002c20  test    eax, eax
0x140002c22  jz      short loc_140002C2B
0x140002c24  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002c29  jz      short loc_140002C51
0x140002c2b  mov     rax, cs:g_pfnResultLoggingCallback
0x140002c32  test    rax, rax
0x140002c35  jz      short loc_140002CAA
0x140002c37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002c3e  jnz     short loc_140002CAA
0x140002c40  xor     r8d, r8d
0x140002c43  xor     edx, edx
0x140002c45  lea     rcx, [rsp+14F0h+var_14D0]
0x140002c4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c4f  jmp     short loc_140002CAA
0x140002c51  mov     ebx, 800h
0x140002c56  mov     rax, cs:g_pfnResultLoggingCallback
0x140002c5d  test    rax, rax
0x140002c60  jz      short loc_140002C7F
0x140002c62  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140002c69  jnz     short loc_140002C7F
0x140002c6b  mov     r8d, ebx
0x140002c6e  lea     rdx, [rbp+13F0h+OutputString]
0x140002c75  lea     rcx, [rsp+14F0h+var_14D0]
0x140002c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002c7f  cmp     [rbp+13F0h+OutputString], r15w
0x140002c87  jnz     short loc_140002C9D
0x140002c89  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140002c8e  mov     rdx, rbx; wchar_t *
0x140002c91  lea     rcx, [rbp+13F0h+OutputString]; this
0x140002c98  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140002c9d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140002ca4  call    cs:__imp_OutputDebugStringW
0x140002caa  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140002caf  jnz     short loc_140002CBA
0x140002cb1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140002cb8  jz      short loc_140002CCC
0x140002cba  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002cc1  test    rax, rax
0x140002cc4  jz      short loc_140002CCC
0x140002cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ccb  nop
0x140002ccc  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x140002cd1  jnz     short loc_140002CF9
0x140002cd3  mov     rcx, [rbp+13F0h+var_30]
0x140002cda  xor     rcx, rsp; StackCookie
0x140002cdd  call    __security_check_cookie
0x140002ce2  mov     rbx, [rsp+14F0h+arg_10]
0x140002cea  add     rsp, 14D0h
0x140002cf1  pop     r15
0x140002cf3  pop     r14
0x140002cf5  pop     rdi
0x140002cf6  pop     rsi
0x140002cf7  pop     rbp
0x140002cf8  retn
0x140002cf9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002cfe  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002d04  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
