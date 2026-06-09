# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800849d8`
- end: `0x180084c6c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800846ac`

## callees

- `0x1800044bf`
- `0x180077c68`
- `0x1800849d8`
- `0x1800867fc`
- `0x18008771c`
- `0x1800877f8`
- `0x18009a520`
- `0x18009a5e0`
- `0x1800a3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180084a82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180084a82`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180084c07`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180084c07`
- `KERNEL32!IsDebuggerPresent` at `0x180084b7d`
- `KERNEL32!IsDebuggerPresent` at `0x180084b7d`

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
0x1800849d8  mov     [rsp-8+arg_10], rbx
0x1800849dd  push    rbp
0x1800849de  push    rsi
0x1800849df  push    rdi
0x1800849e0  push    r14
0x1800849e2  push    r15
0x1800849e4  lea     rbp, [rsp-13D0h]
0x1800849ec  mov     eax, 14D0h
0x1800849f1  call    _alloca_probe
0x1800849f6  sub     rsp, rax
0x1800849f9  mov     rax, cs:__security_cookie
0x180084a00  xor     rax, rsp
0x180084a03  mov     [rbp+13F0h+var_30], rax
0x180084a0a  mov     rdi, [rbp+13F0h+arg_28]
0x180084a11  mov     esi, edx
0x180084a13  mov     r14, rcx
0x180084a16  xor     edx, edx; Val
0x180084a18  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180084a1d  mov     r8d, 98h; Size
0x180084a23  call    memset_0
0x180084a28  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180084a2f  xor     r15d, r15d
0x180084a32  mov     [rbp+13F0h+OutputString], r15w
0x180084a3a  mov     [rbp+13F0h+var_1430], r15b
0x180084a3e  mov     ecx, [rdx]; this
0x180084a40  mov     eax, [rdx+4]
0x180084a43  mov     [rsp+14F0h+var_14C8], ecx
0x180084a47  mov     [rsp+14F0h+var_14C4], eax
0x180084a4b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180084a50  cmp     dword ptr [rdx+8], 1
0x180084a54  mov     ebx, eax
0x180084a56  lea     eax, [r15+8]
0x180084a5a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180084a62  mov     ecx, r15d
0x180084a65  cmovz   ecx, eax
0x180084a68  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180084a6c  lea     ecx, [rax-7]
0x180084a6f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180084a77  inc     ecx
0x180084a79  mov     [rsp+14F0h+var_14B8], r15
0x180084a7e  mov     [rsp+14F0h+var_14C0], ecx
0x180084a82  call    cs:__imp_GetCurrentThreadId
0x180084a88  xorps   xmm0, xmm0
0x180084a8b  mov     [rsp+14F0h+var_1490], esi
0x180084a8f  mov     [rsp+14F0h+var_14B0], eax
0x180084a93  xorps   xmm1, xmm1
0x180084a96  lea     rax, aWil; "wil"
0x180084a9d  mov     [rsp+14F0h+var_148C], ebx
0x180084aa1  mov     [rsp+14F0h+var_1498], rax
0x180084aa6  xor     eax, eax
0x180084aa8  mov     [rbp+13F0h+var_1458], rax
0x180084aac  mov     [rbp+13F0h+var_1470], rax
0x180084ab0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180084ab7  mov     [rsp+14F0h+var_14A8], r15
0x180084abc  mov     [rsp+14F0h+var_14A0], r15
0x180084ac1  mov     [rbp+13F0h+var_1448], rdi
0x180084ac5  mov     [rbp+13F0h+var_1440], r14
0x180084ac9  mov     [rsp+14F0h+var_1488], r15
0x180084ace  movups  [rbp+13F0h+var_1468], xmm0
0x180084ad2  movups  [rsp+14F0h+var_1480], xmm1
0x180084ad7  test    rax, rax
0x180084ada  jz      short loc_180084AE7
0x180084adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084ae1  mov     [rbp+13F0h+var_1450], rax
0x180084ae5  jmp     short loc_180084AEB
0x180084ae7  mov     [rbp+13F0h+var_1450], r15
0x180084aeb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180084af2  test    rax, rax
0x180084af5  jz      short loc_180084B01
0x180084af7  lea     rcx, [rsp+14F0h+var_14D0]
0x180084afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084b01  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180084b08  test    rax, rax
0x180084b0b  jz      short loc_180084B21
0x180084b0d  mov     r8d, 400h
0x180084b13  lea     rdx, [rbp+13F0h+var_1430]
0x180084b17  lea     rcx, [rsp+14F0h+var_14D0]
0x180084b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084b21  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180084b28  test    rax, rax
0x180084b2b  jz      short loc_180084B37
0x180084b2d  lea     rcx, [rsp+14F0h+var_14D0]
0x180084b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084b37  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180084b3e  test    rax, rax
0x180084b41  jz      short loc_180084B54
0x180084b43  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180084b48  jnz     short loc_180084B54
0x180084b4a  lea     rcx, [rsp+14F0h+var_14D0]
0x180084b4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084b54  cmp     [rsp+14F0h+var_14C8], r15d
0x180084b59  jge     loc_180084C5B
0x180084b5f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180084b66  jnz     short loc_180084B87
0x180084b68  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180084b6f  test    rax, rax
0x180084b72  jz      short loc_180084B7D
0x180084b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084b79  test    al, al
0x180084b7b  jmp     short loc_180084B85
0x180084b7d  call    cs:__imp_IsDebuggerPresent
0x180084b83  test    eax, eax
0x180084b85  jz      short loc_180084B8E
0x180084b87  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180084b8c  jz      short loc_180084BB4
0x180084b8e  mov     rax, cs:g_pfnResultLoggingCallback
0x180084b95  test    rax, rax
0x180084b98  jz      short loc_180084C0D
0x180084b9a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180084ba1  jnz     short loc_180084C0D
0x180084ba3  xor     r8d, r8d
0x180084ba6  lea     rcx, [rsp+14F0h+var_14D0]
0x180084bab  xor     edx, edx
0x180084bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084bb2  jmp     short loc_180084C0D
0x180084bb4  mov     rax, cs:g_pfnResultLoggingCallback
0x180084bbb  mov     ebx, 800h
0x180084bc0  test    rax, rax
0x180084bc3  jz      short loc_180084BE2
0x180084bc5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180084bcc  jnz     short loc_180084BE2
0x180084bce  mov     r8d, ebx
0x180084bd1  lea     rdx, [rbp+13F0h+OutputString]
0x180084bd8  lea     rcx, [rsp+14F0h+var_14D0]
0x180084bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084be2  cmp     [rbp+13F0h+OutputString], r15w
0x180084bea  jnz     short loc_180084C00
0x180084bec  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180084bf1  mov     rdx, rbx; unsigned __int16 *
0x180084bf4  lea     rcx, [rbp+13F0h+OutputString]; this
0x180084bfb  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180084c00  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180084c07  call    cs:__imp_OutputDebugStringW
0x180084c0d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180084c12  jnz     short loc_180084C1D
0x180084c14  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180084c1b  jz      short loc_180084C2E
0x180084c1d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180084c24  test    rax, rax
0x180084c27  jz      short loc_180084C2E
0x180084c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084c2e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180084c33  jnz     short loc_180084C61
0x180084c35  mov     rcx, [rbp+13F0h+var_30]
0x180084c3c  xor     rcx, rsp; StackCookie
0x180084c3f  call    __security_check_cookie
0x180084c44  mov     rbx, [rsp+14F0h+arg_10]
0x180084c4c  add     rsp, 14D0h
0x180084c53  pop     r15
0x180084c55  pop     r14
0x180084c57  pop     rdi
0x180084c58  pop     rsi
0x180084c59  pop     rbp
0x180084c5a  retn
0x180084c5b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180084c61  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180084c66  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
