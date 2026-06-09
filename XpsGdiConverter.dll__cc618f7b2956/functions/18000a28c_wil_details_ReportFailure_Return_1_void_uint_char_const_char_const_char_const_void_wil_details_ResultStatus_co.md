# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000a28c`
- end: `0x18000a522`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180009f54`

## callees

- `0x180008830`
- `0x1800093c4`
- `0x18000a28c`
- `0x18000b174`
- `0x18000c1a0`
- `0x18000cc28`
- `0x18000cd58`
- `0x180047170`
- `0x18004a010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18000a432`
- `KERNEL32!IsDebuggerPresent` at `0x18000a432`
- `KERNEL32!OutputDebugStringW` at `0x18000a4bc`
- `KERNEL32!OutputDebugStringW` at `0x18000a4bc`
- `KERNEL32!GetCurrentThreadId` at `0x18000a337`
- `KERNEL32!GetCurrentThreadId` at `0x18000a337`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000a28c  mov     [rsp-8+arg_10], rbx
0x18000a291  push    rbp
0x18000a292  push    rsi
0x18000a293  push    rdi
0x18000a294  push    r14
0x18000a296  push    r15
0x18000a298  lea     rbp, [rsp-13D0h]
0x18000a2a0  mov     eax, 14D0h
0x18000a2a5  call    _alloca_probe
0x18000a2aa  sub     rsp, rax
0x18000a2ad  mov     rax, cs:__security_cookie
0x18000a2b4  xor     rax, rsp
0x18000a2b7  mov     [rbp+13F0h+var_30], rax
0x18000a2be  mov     esi, edx
0x18000a2c0  mov     r14, rcx
0x18000a2c3  mov     rdi, [rbp+13F0h+arg_28]
0x18000a2ca  xor     edx, edx; Val
0x18000a2cc  mov     r8d, 98h; Size
0x18000a2d2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000a2d7  call    memset_0
0x18000a2dc  nop
0x18000a2dd  xor     r15d, r15d
0x18000a2e0  mov     [rbp+13F0h+OutputString], r15w
0x18000a2e8  mov     [rbp+13F0h+var_1430], r15b
0x18000a2ec  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000a2f3  mov     ecx, [rdx]; this
0x18000a2f5  mov     [rsp+14F0h+var_14C8], ecx
0x18000a2f9  mov     eax, [rdx+4]
0x18000a2fc  mov     [rsp+14F0h+var_14C4], eax
0x18000a300  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a305  mov     ebx, eax
0x18000a307  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000a30f  mov     ecx, r15d
0x18000a312  lea     eax, [r15+8]
0x18000a316  cmp     dword ptr [rdx+8], 1
0x18000a31a  cmovz   ecx, eax
0x18000a31d  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000a321  lea     ecx, [rax-7]
0x18000a324  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a32c  inc     ecx
0x18000a32e  mov     [rsp+14F0h+var_14C0], ecx
0x18000a332  mov     [rsp+14F0h+var_14B8], r15
0x18000a337  call    cs:__imp_GetCurrentThreadId
0x18000a33d  mov     [rsp+14F0h+var_14B0], eax
0x18000a341  lea     rax, aWil; "wil"
0x18000a348  mov     [rsp+14F0h+var_1498], rax
0x18000a34d  mov     [rsp+14F0h+var_1490], esi
0x18000a351  mov     [rsp+14F0h+var_148C], ebx
0x18000a355  mov     [rsp+14F0h+var_14A8], r15
0x18000a35a  mov     [rsp+14F0h+var_14A0], r15
0x18000a35f  mov     [rbp+13F0h+var_1448], rdi
0x18000a363  mov     [rbp+13F0h+var_1440], r14
0x18000a367  mov     [rsp+14F0h+var_1488], r15
0x18000a36c  xorps   xmm0, xmm0
0x18000a36f  xor     eax, eax
0x18000a371  movups  [rbp+13F0h+var_1468], xmm0
0x18000a375  mov     [rbp+13F0h+var_1458], rax
0x18000a379  xorps   xmm1, xmm1
0x18000a37c  movups  [rsp+14F0h+var_1480], xmm1
0x18000a381  mov     [rbp+13F0h+var_1470], rax
0x18000a385  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a38c  test    rax, rax
0x18000a38f  jz      short loc_18000A39C
0x18000a391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a396  mov     [rbp+13F0h+var_1450], rax
0x18000a39a  jmp     short loc_18000A3A0
0x18000a39c  mov     [rbp+13F0h+var_1450], r15
0x18000a3a0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a3a7  test    rax, rax
0x18000a3aa  jz      short loc_18000A3B6
0x18000a3ac  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a3b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3b6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a3bd  test    rax, rax
0x18000a3c0  jz      short loc_18000A3D6
0x18000a3c2  mov     r8d, 400h
0x18000a3c8  lea     rdx, [rbp+13F0h+var_1430]
0x18000a3cc  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a3d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a3dd  test    rax, rax
0x18000a3e0  jz      short loc_18000A3EC
0x18000a3e2  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a3e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3ec  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a3f3  test    rax, rax
0x18000a3f6  jz      short loc_18000A409
0x18000a3f8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000a3fd  jnz     short loc_18000A409
0x18000a3ff  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a404  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a409  cmp     [rsp+14F0h+var_14C8], r15d
0x18000a40e  jge     loc_18000A51C
0x18000a414  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18000a41b  jnz     short loc_18000A43C
0x18000a41d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a424  test    rax, rax
0x18000a427  jz      short loc_18000A432
0x18000a429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a42e  test    al, al
0x18000a430  jmp     short loc_18000A43A
0x18000a432  call    cs:__imp_IsDebuggerPresent
0x18000a438  test    eax, eax
0x18000a43a  jz      short loc_18000A443
0x18000a43c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000a441  jz      short loc_18000A469
0x18000a443  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a44a  test    rax, rax
0x18000a44d  jz      short loc_18000A4C2
0x18000a44f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000a456  jnz     short loc_18000A4C2
0x18000a458  xor     r8d, r8d
0x18000a45b  xor     edx, edx
0x18000a45d  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a467  jmp     short loc_18000A4C2
0x18000a469  mov     ebx, 800h
0x18000a46e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a475  test    rax, rax
0x18000a478  jz      short loc_18000A497
0x18000a47a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000a481  jnz     short loc_18000A497
0x18000a483  mov     r8d, ebx
0x18000a486  lea     rdx, [rbp+13F0h+OutputString]
0x18000a48d  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a497  cmp     [rbp+13F0h+OutputString], r15w
0x18000a49f  jnz     short loc_18000A4B5
0x18000a4a1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000a4a6  mov     rdx, rbx; wchar_t *
0x18000a4a9  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000a4b0  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000a4b5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000a4bc  call    cs:__imp_OutputDebugStringW
0x18000a4c2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000a4c7  jnz     short loc_18000A4D2
0x18000a4c9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000a4d0  jz      short loc_18000A4E4
0x18000a4d2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a4d9  test    rax, rax
0x18000a4dc  jz      short loc_18000A4E4
0x18000a4de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4e3  nop
0x18000a4e4  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000a4e9  jnz     short loc_18000A511
0x18000a4eb  mov     rcx, [rbp+13F0h+var_30]
0x18000a4f2  xor     rcx, rsp; StackCookie
0x18000a4f5  call    __security_check_cookie
0x18000a4fa  mov     rbx, [rsp+14F0h+arg_10]
0x18000a502  add     rsp, 14D0h
0x18000a509  pop     r15
0x18000a50b  pop     r14
0x18000a50d  pop     rdi
0x18000a50e  pop     rsi
0x18000a50f  pop     rbp
0x18000a510  retn
0x18000a511  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000a516  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000a51c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
