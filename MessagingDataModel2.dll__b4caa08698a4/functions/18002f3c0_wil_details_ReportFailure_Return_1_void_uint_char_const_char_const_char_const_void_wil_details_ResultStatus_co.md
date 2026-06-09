# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18002f3c0`
- end: `0x18002f64b`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18002f090`

## callees

- `0x18002f3c0`
- `0x18003033c`
- `0x1800312b0`
- `0x1800318c8`
- `0x1800319a4`
- `0x1800c6902`
- `0x1800c6940`
- `0x1800c6a00`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002f561`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002f561`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002f5eb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002f5eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f46d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f46d`

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
0x18002f3c0  push    rbp
0x18002f3c2  push    rbx
0x18002f3c3  push    rsi
0x18002f3c4  push    rdi
0x18002f3c5  push    r12
0x18002f3c7  push    r14
0x18002f3c9  push    r15
0x18002f3cb  lea     rbp, [rsp-13D0h]
0x18002f3d3  mov     eax, 14D0h
0x18002f3d8  call    _alloca_probe
0x18002f3dd  sub     rsp, rax
0x18002f3e0  mov     rax, cs:__security_cookie
0x18002f3e7  xor     rax, rsp
0x18002f3ea  mov     [rbp+1400h+var_40], rax
0x18002f3f1  mov     rdi, [rbp+1400h+arg_28]
0x18002f3f8  mov     r14, r8
0x18002f3fb  mov     esi, edx
0x18002f3fd  mov     r15, rcx
0x18002f400  xor     edx, edx; Val
0x18002f402  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18002f407  mov     r8d, 98h; Size
0x18002f40d  call    memset_0
0x18002f412  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18002f419  xor     r12d, r12d
0x18002f41c  mov     [rbp+1400h+OutputString], r12w
0x18002f424  mov     [rbp+1400h+var_1440], r12b
0x18002f428  mov     ecx, [rdx]; this
0x18002f42a  mov     eax, [rdx+4]
0x18002f42d  mov     [rsp+1500h+var_14D8], ecx
0x18002f431  mov     [rsp+1500h+var_14D4], eax
0x18002f435  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002f43a  cmp     dword ptr [rdx+8], 1
0x18002f43e  mov     ebx, eax
0x18002f440  lea     eax, [r12+8]
0x18002f445  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18002f44d  mov     ecx, r12d
0x18002f450  cmovz   ecx, eax
0x18002f453  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18002f457  lea     ecx, [rax-7]
0x18002f45a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002f462  inc     ecx
0x18002f464  mov     [rsp+1500h+var_14C8], r12
0x18002f469  mov     [rsp+1500h+var_14D0], ecx
0x18002f46d  call    cs:__imp_GetCurrentThreadId
0x18002f473  xorps   xmm0, xmm0
0x18002f476  mov     [rsp+1500h+var_14A8], r14
0x18002f47b  mov     [rsp+1500h+var_14C0], eax
0x18002f47f  xorps   xmm1, xmm1
0x18002f482  xor     eax, eax
0x18002f484  mov     [rsp+1500h+var_14A0], esi
0x18002f488  mov     [rbp+1400h+var_1468], rax
0x18002f48c  mov     [rbp+1400h+var_1480], rax
0x18002f490  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002f497  mov     [rsp+1500h+var_149C], ebx
0x18002f49b  mov     [rsp+1500h+var_14B8], r12
0x18002f4a0  mov     [rsp+1500h+var_14B0], r12
0x18002f4a5  mov     [rbp+1400h+var_1458], rdi
0x18002f4a9  mov     [rbp+1400h+var_1450], r15
0x18002f4ad  mov     [rsp+1500h+var_1498], r12
0x18002f4b2  movups  [rbp+1400h+var_1478], xmm0
0x18002f4b6  movups  [rsp+1500h+var_1490], xmm1
0x18002f4bb  test    rax, rax
0x18002f4be  jz      short loc_18002F4CB
0x18002f4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4c5  mov     [rbp+1400h+var_1460], rax
0x18002f4c9  jmp     short loc_18002F4CF
0x18002f4cb  mov     [rbp+1400h+var_1460], r12
0x18002f4cf  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002f4d6  test    rax, rax
0x18002f4d9  jz      short loc_18002F4E5
0x18002f4db  lea     rcx, [rsp+1500h+var_14E0]
0x18002f4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f4e5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002f4ec  test    rax, rax
0x18002f4ef  jz      short loc_18002F505
0x18002f4f1  mov     r8d, 400h
0x18002f4f7  lea     rdx, [rbp+1400h+var_1440]
0x18002f4fb  lea     rcx, [rsp+1500h+var_14E0]
0x18002f500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f505  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002f50c  test    rax, rax
0x18002f50f  jz      short loc_18002F51B
0x18002f511  lea     rcx, [rsp+1500h+var_14E0]
0x18002f516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f51b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002f522  test    rax, rax
0x18002f525  jz      short loc_18002F538
0x18002f527  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18002f52c  jnz     short loc_18002F538
0x18002f52e  lea     rcx, [rsp+1500h+var_14E0]
0x18002f533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f538  cmp     [rsp+1500h+var_14D8], r12d
0x18002f53d  jge     loc_18002F63A
0x18002f543  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18002f54a  jnz     short loc_18002F56B
0x18002f54c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002f553  test    rax, rax
0x18002f556  jz      short loc_18002F561
0x18002f558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f55d  test    al, al
0x18002f55f  jmp     short loc_18002F569
0x18002f561  call    cs:__imp_IsDebuggerPresent
0x18002f567  test    eax, eax
0x18002f569  jz      short loc_18002F572
0x18002f56b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18002f570  jz      short loc_18002F598
0x18002f572  mov     rax, cs:g_pfnResultLoggingCallback
0x18002f579  test    rax, rax
0x18002f57c  jz      short loc_18002F5F1
0x18002f57e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18002f585  jnz     short loc_18002F5F1
0x18002f587  xor     r8d, r8d
0x18002f58a  lea     rcx, [rsp+1500h+var_14E0]
0x18002f58f  xor     edx, edx
0x18002f591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f596  jmp     short loc_18002F5F1
0x18002f598  mov     rax, cs:g_pfnResultLoggingCallback
0x18002f59f  mov     ebx, 800h
0x18002f5a4  test    rax, rax
0x18002f5a7  jz      short loc_18002F5C6
0x18002f5a9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18002f5b0  jnz     short loc_18002F5C6
0x18002f5b2  mov     r8d, ebx
0x18002f5b5  lea     rdx, [rbp+1400h+OutputString]
0x18002f5bc  lea     rcx, [rsp+1500h+var_14E0]
0x18002f5c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5c6  cmp     [rbp+1400h+OutputString], r12w
0x18002f5ce  jnz     short loc_18002F5E4
0x18002f5d0  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18002f5d5  mov     rdx, rbx; unsigned __int16 *
0x18002f5d8  lea     rcx, [rbp+1400h+OutputString]; this
0x18002f5df  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002f5e4  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18002f5eb  call    cs:__imp_OutputDebugStringW
0x18002f5f1  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18002f5f6  jnz     short loc_18002F601
0x18002f5f8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18002f5ff  jz      short loc_18002F612
0x18002f601  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002f608  test    rax, rax
0x18002f60b  jz      short loc_18002F612
0x18002f60d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f612  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18002f617  jnz     short loc_18002F640
0x18002f619  mov     rcx, [rbp+1400h+var_40]
0x18002f620  xor     rcx, rsp; StackCookie
0x18002f623  call    __security_check_cookie
0x18002f628  add     rsp, 14D0h
0x18002f62f  pop     r15
0x18002f631  pop     r14
0x18002f633  pop     r12
0x18002f635  pop     rdi
0x18002f636  pop     rsi
0x18002f637  pop     rbx
0x18002f638  pop     rbp
0x18002f639  retn
0x18002f63a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002f640  lea     rcx, [rsp+1500h+var_14E0]; this
0x18002f645  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
