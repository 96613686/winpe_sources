# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180011768`
- end: `0x1800119fc`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180011248`

## callees

- `0x180001630`
- `0x180001f7c`
- `0x180011768`
- `0x180013414`
- `0x180014904`
- `0x180016400`
- `0x1800165b8`
- `0x18001a640`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011812`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011812`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001190d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001190d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011997`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011997`

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
0x180011768  mov     [rsp-8+arg_10], rbx
0x18001176d  push    rbp
0x18001176e  push    rsi
0x18001176f  push    rdi
0x180011770  push    r14
0x180011772  push    r15
0x180011774  lea     rbp, [rsp-13D0h]
0x18001177c  mov     eax, 14D0h
0x180011781  call    _alloca_probe
0x180011786  sub     rsp, rax
0x180011789  mov     rax, cs:__security_cookie
0x180011790  xor     rax, rsp
0x180011793  mov     [rbp+13F0h+var_30], rax
0x18001179a  mov     rdi, [rbp+13F0h+arg_28]
0x1800117a1  mov     esi, edx
0x1800117a3  mov     r14, rcx
0x1800117a6  xor     edx, edx; Val
0x1800117a8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800117ad  mov     r8d, 98h; Size
0x1800117b3  call    memset_0
0x1800117b8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800117bf  xor     r15d, r15d
0x1800117c2  mov     [rbp+13F0h+OutputString], r15w
0x1800117ca  mov     [rbp+13F0h+var_1430], r15b
0x1800117ce  mov     ecx, [rdx]; this
0x1800117d0  mov     eax, [rdx+4]
0x1800117d3  mov     [rsp+14F0h+var_14C8], ecx
0x1800117d7  mov     [rsp+14F0h+var_14C4], eax
0x1800117db  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800117e0  cmp     dword ptr [rdx+8], 1
0x1800117e4  mov     ebx, eax
0x1800117e6  lea     eax, [r15+8]
0x1800117ea  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800117f2  mov     ecx, r15d
0x1800117f5  cmovz   ecx, eax
0x1800117f8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800117fc  lea     ecx, [rax-7]
0x1800117ff  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180011807  inc     ecx
0x180011809  mov     [rsp+14F0h+var_14B8], r15
0x18001180e  mov     [rsp+14F0h+var_14C0], ecx
0x180011812  call    cs:__imp_GetCurrentThreadId
0x180011818  xorps   xmm0, xmm0
0x18001181b  mov     [rsp+14F0h+var_1490], esi
0x18001181f  mov     [rsp+14F0h+var_14B0], eax
0x180011823  xorps   xmm1, xmm1
0x180011826  lea     rax, aWil; "wil"
0x18001182d  mov     [rsp+14F0h+var_148C], ebx
0x180011831  mov     [rsp+14F0h+var_1498], rax
0x180011836  xor     eax, eax
0x180011838  mov     [rbp+13F0h+var_1458], rax
0x18001183c  mov     [rbp+13F0h+var_1470], rax
0x180011840  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180011847  mov     [rsp+14F0h+var_14A8], r15
0x18001184c  mov     [rsp+14F0h+var_14A0], r15
0x180011851  mov     [rbp+13F0h+var_1448], rdi
0x180011855  mov     [rbp+13F0h+var_1440], r14
0x180011859  mov     [rsp+14F0h+var_1488], r15
0x18001185e  movups  [rbp+13F0h+var_1468], xmm0
0x180011862  movups  [rsp+14F0h+var_1480], xmm1
0x180011867  test    rax, rax
0x18001186a  jz      short loc_180011877
0x18001186c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011871  mov     [rbp+13F0h+var_1450], rax
0x180011875  jmp     short loc_18001187B
0x180011877  mov     [rbp+13F0h+var_1450], r15
0x18001187b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180011882  test    rax, rax
0x180011885  jz      short loc_180011891
0x180011887  lea     rcx, [rsp+14F0h+var_14D0]
0x18001188c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011891  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180011898  test    rax, rax
0x18001189b  jz      short loc_1800118B1
0x18001189d  mov     r8d, 400h
0x1800118a3  lea     rdx, [rbp+13F0h+var_1430]
0x1800118a7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800118ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118b1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800118b8  test    rax, rax
0x1800118bb  jz      short loc_1800118C7
0x1800118bd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800118c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118c7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800118ce  test    rax, rax
0x1800118d1  jz      short loc_1800118E4
0x1800118d3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800118d8  jnz     short loc_1800118E4
0x1800118da  lea     rcx, [rsp+14F0h+var_14D0]
0x1800118df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800118e4  cmp     [rsp+14F0h+var_14C8], r15d
0x1800118e9  jge     loc_1800119EB
0x1800118ef  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800118f6  jnz     short loc_180011917
0x1800118f8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800118ff  test    rax, rax
0x180011902  jz      short loc_18001190D
0x180011904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011909  test    al, al
0x18001190b  jmp     short loc_180011915
0x18001190d  call    cs:__imp_IsDebuggerPresent
0x180011913  test    eax, eax
0x180011915  jz      short loc_18001191E
0x180011917  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001191c  jz      short loc_180011944
0x18001191e  mov     rax, cs:g_pfnResultLoggingCallback
0x180011925  test    rax, rax
0x180011928  jz      short loc_18001199D
0x18001192a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180011931  jnz     short loc_18001199D
0x180011933  xor     r8d, r8d
0x180011936  lea     rcx, [rsp+14F0h+var_14D0]
0x18001193b  xor     edx, edx
0x18001193d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011942  jmp     short loc_18001199D
0x180011944  mov     rax, cs:g_pfnResultLoggingCallback
0x18001194b  mov     ebx, 800h
0x180011950  test    rax, rax
0x180011953  jz      short loc_180011972
0x180011955  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001195c  jnz     short loc_180011972
0x18001195e  mov     r8d, ebx
0x180011961  lea     rdx, [rbp+13F0h+OutputString]
0x180011968  lea     rcx, [rsp+14F0h+var_14D0]
0x18001196d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011972  cmp     [rbp+13F0h+OutputString], r15w
0x18001197a  jnz     short loc_180011990
0x18001197c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180011981  mov     rdx, rbx; unsigned __int16 *
0x180011984  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001198b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180011990  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180011997  call    cs:__imp_OutputDebugStringW
0x18001199d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800119a2  jnz     short loc_1800119AD
0x1800119a4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800119ab  jz      short loc_1800119BE
0x1800119ad  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800119b4  test    rax, rax
0x1800119b7  jz      short loc_1800119BE
0x1800119b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800119be  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800119c3  jnz     short loc_1800119F1
0x1800119c5  mov     rcx, [rbp+13F0h+var_30]
0x1800119cc  xor     rcx, rsp; StackCookie
0x1800119cf  call    __security_check_cookie
0x1800119d4  mov     rbx, [rsp+14F0h+arg_10]
0x1800119dc  add     rsp, 14D0h
0x1800119e3  pop     r15
0x1800119e5  pop     r14
0x1800119e7  pop     rdi
0x1800119e8  pop     rsi
0x1800119e9  pop     rbp
0x1800119ea  retn
0x1800119eb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800119f1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800119f6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
