# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000be48`
- end: `0x18000c0d3`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000b920`

## callees

- `0x18000a684`
- `0x18000be48`
- `0x18000ee9c`
- `0x18000f604`
- `0x18000f6e0`
- `0x18001972e`
- `0x180019760`
- `0x180019820`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bef5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bef5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c073`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c073`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bfe9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bfe9`

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
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x18000be48  push    rbp
0x18000be4a  push    rbx
0x18000be4b  push    rsi
0x18000be4c  push    rdi
0x18000be4d  push    r12
0x18000be4f  push    r14
0x18000be51  push    r15
0x18000be53  lea     rbp, [rsp-13D0h]
0x18000be5b  mov     eax, 14D0h
0x18000be60  call    _alloca_probe
0x18000be65  sub     rsp, rax
0x18000be68  mov     rax, cs:__security_cookie
0x18000be6f  xor     rax, rsp
0x18000be72  mov     [rbp+1400h+var_40], rax
0x18000be79  mov     rdi, [rbp+1400h+arg_28]
0x18000be80  mov     r14, r8
0x18000be83  mov     esi, edx
0x18000be85  mov     r15, rcx
0x18000be88  xor     edx, edx; Val
0x18000be8a  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000be8f  mov     r8d, 98h; Size
0x18000be95  call    memset_0
0x18000be9a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000bea1  xor     r12d, r12d
0x18000bea4  mov     [rbp+1400h+OutputString], r12w
0x18000beac  mov     [rbp+1400h+var_1440], r12b
0x18000beb0  mov     ecx, [rdx]; this
0x18000beb2  mov     eax, [rdx+4]
0x18000beb5  mov     [rsp+1500h+var_14D8], ecx
0x18000beb9  mov     [rsp+1500h+var_14D4], eax
0x18000bebd  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000bec2  cmp     dword ptr [rdx+8], 1
0x18000bec6  mov     ebx, eax
0x18000bec8  lea     eax, [r12+8]
0x18000becd  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000bed5  mov     ecx, r12d
0x18000bed8  cmovz   ecx, eax
0x18000bedb  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000bedf  lea     ecx, [rax-7]
0x18000bee2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000beea  inc     ecx
0x18000beec  mov     [rsp+1500h+var_14C8], r12
0x18000bef1  mov     [rsp+1500h+var_14D0], ecx
0x18000bef5  call    cs:__imp_GetCurrentThreadId
0x18000befb  xorps   xmm0, xmm0
0x18000befe  mov     [rsp+1500h+var_14A8], r14
0x18000bf03  mov     [rsp+1500h+var_14C0], eax
0x18000bf07  xorps   xmm1, xmm1
0x18000bf0a  xor     eax, eax
0x18000bf0c  mov     [rsp+1500h+var_14A0], esi
0x18000bf10  mov     [rbp+1400h+var_1468], rax
0x18000bf14  mov     [rbp+1400h+var_1480], rax
0x18000bf18  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000bf1f  mov     [rsp+1500h+var_149C], ebx
0x18000bf23  mov     [rsp+1500h+var_14B8], r12
0x18000bf28  mov     [rsp+1500h+var_14B0], r12
0x18000bf2d  mov     [rbp+1400h+var_1458], rdi
0x18000bf31  mov     [rbp+1400h+var_1450], r15
0x18000bf35  mov     [rsp+1500h+var_1498], r12
0x18000bf3a  movups  [rbp+1400h+var_1478], xmm0
0x18000bf3e  movups  [rsp+1500h+var_1490], xmm1
0x18000bf43  test    rax, rax
0x18000bf46  jz      short loc_18000BF53
0x18000bf48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf4d  mov     [rbp+1400h+var_1460], rax
0x18000bf51  jmp     short loc_18000BF57
0x18000bf53  mov     [rbp+1400h+var_1460], r12
0x18000bf57  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000bf5e  test    rax, rax
0x18000bf61  jz      short loc_18000BF6D
0x18000bf63  lea     rcx, [rsp+1500h+var_14E0]
0x18000bf68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf6d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000bf74  test    rax, rax
0x18000bf77  jz      short loc_18000BF8D
0x18000bf79  mov     r8d, 400h
0x18000bf7f  lea     rdx, [rbp+1400h+var_1440]
0x18000bf83  lea     rcx, [rsp+1500h+var_14E0]
0x18000bf88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bf8d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bf94  test    rax, rax
0x18000bf97  jz      short loc_18000BFA3
0x18000bf99  lea     rcx, [rsp+1500h+var_14E0]
0x18000bf9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfa3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000bfaa  test    rax, rax
0x18000bfad  jz      short loc_18000BFC0
0x18000bfaf  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000bfb4  jnz     short loc_18000BFC0
0x18000bfb6  lea     rcx, [rsp+1500h+var_14E0]
0x18000bfbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfc0  cmp     [rsp+1500h+var_14D8], r12d
0x18000bfc5  jge     loc_18000C0CD
0x18000bfcb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000bfd2  jnz     short loc_18000BFF3
0x18000bfd4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000bfdb  test    rax, rax
0x18000bfde  jz      short loc_18000BFE9
0x18000bfe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfe5  test    al, al
0x18000bfe7  jmp     short loc_18000BFF1
0x18000bfe9  call    cs:__imp_IsDebuggerPresent
0x18000bfef  test    eax, eax
0x18000bff1  jz      short loc_18000BFFA
0x18000bff3  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000bff8  jz      short loc_18000C020
0x18000bffa  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c001  test    rax, rax
0x18000c004  jz      short loc_18000C079
0x18000c006  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000c00d  jnz     short loc_18000C079
0x18000c00f  xor     r8d, r8d
0x18000c012  lea     rcx, [rsp+1500h+var_14E0]
0x18000c017  xor     edx, edx
0x18000c019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c01e  jmp     short loc_18000C079
0x18000c020  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c027  mov     ebx, 800h
0x18000c02c  test    rax, rax
0x18000c02f  jz      short loc_18000C04E
0x18000c031  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000c038  jnz     short loc_18000C04E
0x18000c03a  mov     r8d, ebx
0x18000c03d  lea     rdx, [rbp+1400h+OutputString]
0x18000c044  lea     rcx, [rsp+1500h+var_14E0]
0x18000c049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c04e  cmp     [rbp+1400h+OutputString], r12w
0x18000c056  jnz     short loc_18000C06C
0x18000c058  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000c05d  mov     rdx, rbx; unsigned __int16 *
0x18000c060  lea     rcx, [rbp+1400h+OutputString]; this
0x18000c067  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000c06c  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000c073  call    cs:__imp_OutputDebugStringW
0x18000c079  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000c07e  jnz     short loc_18000C089
0x18000c080  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000c087  jz      short loc_18000C09A
0x18000c089  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000c090  test    rax, rax
0x18000c093  jz      short loc_18000C09A
0x18000c095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c09a  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000c09f  jnz     short loc_18000C0C2
0x18000c0a1  mov     rcx, [rbp+1400h+var_40]
0x18000c0a8  xor     rcx, rsp; StackCookie
0x18000c0ab  call    __security_check_cookie
0x18000c0b0  add     rsp, 14D0h
0x18000c0b7  pop     r15
0x18000c0b9  pop     r14
0x18000c0bb  pop     r12
0x18000c0bd  pop     rdi
0x18000c0be  pop     rsi
0x18000c0bf  pop     rbx
0x18000c0c0  pop     rbp
0x18000c0c1  retn
0x18000c0c2  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000c0c7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000c0cd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
