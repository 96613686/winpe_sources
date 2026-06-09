# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000d6cc`
- end: `0x18000d972`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000d350`

## callees

- `0x18000a6e0`
- `0x18000b2b4`
- `0x18000d6cc`
- `0x18000fae4`
- `0x18001180c`
- `0x1800132c8`
- `0x1800137fc`
- `0x1800572e0`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d792`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d792`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d887`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000d887`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d911`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000d911`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x18000d6cc  push    rbp
0x18000d6ce  push    rbx
0x18000d6cf  push    rsi
0x18000d6d0  push    rdi
0x18000d6d1  push    r12
0x18000d6d3  push    r14
0x18000d6d5  push    r15
0x18000d6d7  lea     rbp, [rsp-13D0h]
0x18000d6df  mov     eax, 14D0h
0x18000d6e4  call    _alloca_probe
0x18000d6e9  sub     rsp, rax
0x18000d6ec  mov     rax, cs:__security_cookie
0x18000d6f3  xor     rax, rsp
0x18000d6f6  mov     [rbp+1400h+var_40], rax
0x18000d6fd  mov     rsi, r8
0x18000d700  mov     edi, edx
0x18000d702  mov     rbx, rcx
0x18000d705  mov     r14, [rbp+1400h+arg_28]
0x18000d70c  xor     edx, edx; Val
0x18000d70e  mov     r8d, 98h; Size
0x18000d714  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000d719  call    memset_0
0x18000d71e  nop
0x18000d71f  xor     r12d, r12d
0x18000d722  mov     [rbp+1400h+OutputString], r12w
0x18000d72a  mov     [rbp+1400h+var_1440], r12b
0x18000d72e  mov     rdx, [rbp+1400h+arg_30]; int
0x18000d735  mov     ecx, [rdx]; this
0x18000d737  mov     [rsp+1500h+var_14D8], ecx
0x18000d73b  mov     eax, [rdx+4]
0x18000d73e  mov     [rsp+1500h+var_14D4], eax
0x18000d742  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000d747  mov     r15d, eax
0x18000d74a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000d752  mov     ecx, r12d
0x18000d755  lea     eax, [r12+8]
0x18000d75a  cmp     dword ptr [rdx+8], 1
0x18000d75e  cmovz   ecx, eax
0x18000d761  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000d765  lea     ecx, [rax-7]
0x18000d768  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000d770  inc     ecx
0x18000d772  mov     [rsp+1500h+var_14D0], ecx
0x18000d776  mov     rcx, [rbp+1400h+arg_38]
0x18000d77d  test    rcx, rcx
0x18000d780  jz      short loc_18000D78D
0x18000d782  cmp     [rcx], r12w
0x18000d786  mov     [rsp+1500h+var_14C8], rcx
0x18000d78b  jnz     short loc_18000D792
0x18000d78d  mov     [rsp+1500h+var_14C8], r12
0x18000d792  call    cs:__imp_GetCurrentThreadId
0x18000d798  mov     [rsp+1500h+var_14C0], eax
0x18000d79c  mov     [rsp+1500h+var_14A8], rsi
0x18000d7a1  mov     [rsp+1500h+var_14A0], edi
0x18000d7a5  mov     [rsp+1500h+var_149C], r15d
0x18000d7aa  mov     [rsp+1500h+var_14B8], r12
0x18000d7af  mov     [rsp+1500h+var_14B0], r12
0x18000d7b4  mov     [rbp+1400h+var_1458], r14
0x18000d7b8  mov     [rbp+1400h+var_1450], rbx
0x18000d7bc  mov     [rsp+1500h+var_1498], r12
0x18000d7c1  xorps   xmm0, xmm0
0x18000d7c4  xor     eax, eax
0x18000d7c6  movups  [rbp+1400h+var_1478], xmm0
0x18000d7ca  mov     [rbp+1400h+var_1468], rax
0x18000d7ce  xorps   xmm1, xmm1
0x18000d7d1  movups  [rsp+1500h+var_1490], xmm1
0x18000d7d6  mov     [rbp+1400h+var_1480], rax
0x18000d7da  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000d7e1  test    rax, rax
0x18000d7e4  jz      short loc_18000D7F1
0x18000d7e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7eb  mov     [rbp+1400h+var_1460], rax
0x18000d7ef  jmp     short loc_18000D7F5
0x18000d7f1  mov     [rbp+1400h+var_1460], r12
0x18000d7f5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000d7fc  test    rax, rax
0x18000d7ff  jz      short loc_18000D80B
0x18000d801  lea     rcx, [rsp+1500h+var_14E0]
0x18000d806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d80b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000d812  test    rax, rax
0x18000d815  jz      short loc_18000D82B
0x18000d817  mov     r8d, 400h
0x18000d81d  lea     rdx, [rbp+1400h+var_1440]
0x18000d821  lea     rcx, [rsp+1500h+var_14E0]
0x18000d826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d82b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d832  test    rax, rax
0x18000d835  jz      short loc_18000D841
0x18000d837  lea     rcx, [rsp+1500h+var_14E0]
0x18000d83c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d841  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d848  test    rax, rax
0x18000d84b  jz      short loc_18000D85E
0x18000d84d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000d852  jnz     short loc_18000D85E
0x18000d854  lea     rcx, [rsp+1500h+var_14E0]
0x18000d859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d85e  cmp     [rsp+1500h+var_14D8], r12d
0x18000d863  jge     loc_18000D96C
0x18000d869  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000d870  jnz     short loc_18000D891
0x18000d872  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000d879  test    rax, rax
0x18000d87c  jz      short loc_18000D887
0x18000d87e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d883  test    al, al
0x18000d885  jmp     short loc_18000D88F
0x18000d887  call    cs:__imp_IsDebuggerPresent
0x18000d88d  test    eax, eax
0x18000d88f  jz      short loc_18000D898
0x18000d891  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000d896  jz      short loc_18000D8BE
0x18000d898  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d89f  test    rax, rax
0x18000d8a2  jz      short loc_18000D917
0x18000d8a4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000d8ab  jnz     short loc_18000D917
0x18000d8ad  xor     r8d, r8d
0x18000d8b0  xor     edx, edx
0x18000d8b2  lea     rcx, [rsp+1500h+var_14E0]
0x18000d8b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8bc  jmp     short loc_18000D917
0x18000d8be  mov     ebx, 800h
0x18000d8c3  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d8ca  test    rax, rax
0x18000d8cd  jz      short loc_18000D8EC
0x18000d8cf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000d8d6  jnz     short loc_18000D8EC
0x18000d8d8  mov     r8d, ebx
0x18000d8db  lea     rdx, [rbp+1400h+OutputString]
0x18000d8e2  lea     rcx, [rsp+1500h+var_14E0]
0x18000d8e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8ec  cmp     [rbp+1400h+OutputString], r12w
0x18000d8f4  jnz     short loc_18000D90A
0x18000d8f6  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000d8fb  mov     rdx, rbx; unsigned __int16 *
0x18000d8fe  lea     rcx, [rbp+1400h+OutputString]; this
0x18000d905  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000d90a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000d911  call    cs:__imp_OutputDebugStringW
0x18000d917  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000d91c  jnz     short loc_18000D927
0x18000d91e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000d925  jz      short loc_18000D939
0x18000d927  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000d92e  test    rax, rax
0x18000d931  jz      short loc_18000D939
0x18000d933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d938  nop
0x18000d939  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000d93e  jnz     short loc_18000D961
0x18000d940  mov     rcx, [rbp+1400h+var_40]
0x18000d947  xor     rcx, rsp; StackCookie
0x18000d94a  call    __security_check_cookie
0x18000d94f  add     rsp, 14D0h
0x18000d956  pop     r15
0x18000d958  pop     r14
0x18000d95a  pop     r12
0x18000d95c  pop     rdi
0x18000d95d  pop     rsi
0x18000d95e  pop     rbx
0x18000d95f  pop     rbp
0x18000d960  retn
0x18000d961  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000d966  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000d96c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
