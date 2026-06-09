# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002aa0`
- end: `0x180002d36`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002580`

## callees

- `0x180001670`
- `0x180002034`
- `0x180002aa0`
- `0x180004f64`
- `0x180006938`
- `0x180008fa0`
- `0x18000916c`
- `0x1800136a0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b4b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002cd0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002cd0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002c46`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002c46`

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
0x180002aa0  mov     [rsp-8+arg_10], rbx
0x180002aa5  push    rbp
0x180002aa6  push    rsi
0x180002aa7  push    rdi
0x180002aa8  push    r14
0x180002aaa  push    r15
0x180002aac  lea     rbp, [rsp-13D0h]
0x180002ab4  mov     eax, 14D0h
0x180002ab9  call    _alloca_probe
0x180002abe  sub     rsp, rax
0x180002ac1  mov     rax, cs:__security_cookie
0x180002ac8  xor     rax, rsp
0x180002acb  mov     [rbp+13F0h+var_30], rax
0x180002ad2  mov     esi, edx
0x180002ad4  mov     r14, rcx
0x180002ad7  mov     rdi, [rbp+13F0h+arg_28]
0x180002ade  xor     edx, edx; Val
0x180002ae0  mov     r8d, 98h; Size
0x180002ae6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002aeb  call    memset_0
0x180002af0  nop
0x180002af1  xor     r15d, r15d
0x180002af4  mov     [rbp+13F0h+OutputString], r15w
0x180002afc  mov     [rbp+13F0h+var_1430], r15b
0x180002b00  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180002b07  mov     ecx, [rdx]; this
0x180002b09  mov     [rsp+14F0h+var_14C8], ecx
0x180002b0d  mov     eax, [rdx+4]
0x180002b10  mov     [rsp+14F0h+var_14C4], eax
0x180002b14  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002b19  mov     ebx, eax
0x180002b1b  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180002b23  mov     ecx, r15d
0x180002b26  lea     eax, [r15+8]
0x180002b2a  cmp     dword ptr [rdx+8], 1
0x180002b2e  cmovz   ecx, eax
0x180002b31  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002b35  lea     ecx, [rax-7]
0x180002b38  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002b40  inc     ecx
0x180002b42  mov     [rsp+14F0h+var_14C0], ecx
0x180002b46  mov     [rsp+14F0h+var_14B8], r15
0x180002b4b  call    cs:__imp_GetCurrentThreadId
0x180002b51  mov     [rsp+14F0h+var_14B0], eax
0x180002b55  lea     rax, aWil; "wil"
0x180002b5c  mov     [rsp+14F0h+var_1498], rax
0x180002b61  mov     [rsp+14F0h+var_1490], esi
0x180002b65  mov     [rsp+14F0h+var_148C], ebx
0x180002b69  mov     [rsp+14F0h+var_14A8], r15
0x180002b6e  mov     [rsp+14F0h+var_14A0], r15
0x180002b73  mov     [rbp+13F0h+var_1448], rdi
0x180002b77  mov     [rbp+13F0h+var_1440], r14
0x180002b7b  mov     [rsp+14F0h+var_1488], r15
0x180002b80  xorps   xmm0, xmm0
0x180002b83  xor     eax, eax
0x180002b85  movups  [rbp+13F0h+var_1468], xmm0
0x180002b89  mov     [rbp+13F0h+var_1458], rax
0x180002b8d  xorps   xmm1, xmm1
0x180002b90  movups  [rsp+14F0h+var_1480], xmm1
0x180002b95  mov     [rbp+13F0h+var_1470], rax
0x180002b99  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002ba0  test    rax, rax
0x180002ba3  jz      short loc_180002BB0
0x180002ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002baa  mov     [rbp+13F0h+var_1450], rax
0x180002bae  jmp     short loc_180002BB4
0x180002bb0  mov     [rbp+13F0h+var_1450], r15
0x180002bb4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002bbb  test    rax, rax
0x180002bbe  jz      short loc_180002BCA
0x180002bc0  lea     rcx, [rsp+14F0h+var_14D0]
0x180002bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bca  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002bd1  test    rax, rax
0x180002bd4  jz      short loc_180002BEA
0x180002bd6  mov     r8d, 400h
0x180002bdc  lea     rdx, [rbp+13F0h+var_1430]
0x180002be0  lea     rcx, [rsp+14F0h+var_14D0]
0x180002be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bea  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002bf1  test    rax, rax
0x180002bf4  jz      short loc_180002C00
0x180002bf6  lea     rcx, [rsp+14F0h+var_14D0]
0x180002bfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c00  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002c07  test    rax, rax
0x180002c0a  jz      short loc_180002C1D
0x180002c0c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002c11  jnz     short loc_180002C1D
0x180002c13  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c1d  cmp     [rsp+14F0h+var_14C8], r15d
0x180002c22  jge     loc_180002D30
0x180002c28  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002c2f  jnz     short loc_180002C50
0x180002c31  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002c38  test    rax, rax
0x180002c3b  jz      short loc_180002C46
0x180002c3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c42  test    al, al
0x180002c44  jmp     short loc_180002C4E
0x180002c46  call    cs:__imp_IsDebuggerPresent
0x180002c4c  test    eax, eax
0x180002c4e  jz      short loc_180002C57
0x180002c50  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002c55  jz      short loc_180002C7D
0x180002c57  mov     rax, cs:g_pfnResultLoggingCallback
0x180002c5e  test    rax, rax
0x180002c61  jz      short loc_180002CD6
0x180002c63  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002c6a  jnz     short loc_180002CD6
0x180002c6c  xor     r8d, r8d
0x180002c6f  xor     edx, edx
0x180002c71  lea     rcx, [rsp+14F0h+var_14D0]
0x180002c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c7b  jmp     short loc_180002CD6
0x180002c7d  mov     ebx, 800h
0x180002c82  mov     rax, cs:g_pfnResultLoggingCallback
0x180002c89  test    rax, rax
0x180002c8c  jz      short loc_180002CAB
0x180002c8e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002c95  jnz     short loc_180002CAB
0x180002c97  mov     r8d, ebx
0x180002c9a  lea     rdx, [rbp+13F0h+OutputString]
0x180002ca1  lea     rcx, [rsp+14F0h+var_14D0]
0x180002ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cab  cmp     [rbp+13F0h+OutputString], r15w
0x180002cb3  jnz     short loc_180002CC9
0x180002cb5  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002cba  mov     rdx, rbx; unsigned __int16 *
0x180002cbd  lea     rcx, [rbp+13F0h+OutputString]; this
0x180002cc4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002cc9  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180002cd0  call    cs:__imp_OutputDebugStringW
0x180002cd6  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002cdb  jnz     short loc_180002CE6
0x180002cdd  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002ce4  jz      short loc_180002CF8
0x180002ce6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002ced  test    rax, rax
0x180002cf0  jz      short loc_180002CF8
0x180002cf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cf7  nop
0x180002cf8  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180002cfd  jnz     short loc_180002D25
0x180002cff  mov     rcx, [rbp+13F0h+var_30]
0x180002d06  xor     rcx, rsp; StackCookie
0x180002d09  call    __security_check_cookie
0x180002d0e  mov     rbx, [rsp+14F0h+arg_10]
0x180002d16  add     rsp, 14D0h
0x180002d1d  pop     r15
0x180002d1f  pop     r14
0x180002d21  pop     rdi
0x180002d22  pop     rsi
0x180002d23  pop     rbp
0x180002d24  retn
0x180002d25  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002d2a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002d30  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
