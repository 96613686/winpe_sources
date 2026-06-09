# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400032a4`
- end: `0x14000352f`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002d7c`

## callees

- `0x1400032a4`
- `0x140005c44`
- `0x140008044`
- `0x14000a590`
- `0x14000a764`
- `0x140015ac2`
- `0x140015b00`
- `0x140015b90`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003351`
- `KERNEL32!GetCurrentThreadId` at `0x140003351`
- `KERNEL32!OutputDebugStringW` at `0x1400034cf`
- `KERNEL32!OutputDebugStringW` at `0x1400034cf`
- `KERNEL32!IsDebuggerPresent` at `0x140003445`
- `KERNEL32!IsDebuggerPresent` at `0x140003445`

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
0x1400032a4  push    rbp
0x1400032a6  push    rbx
0x1400032a7  push    rsi
0x1400032a8  push    rdi
0x1400032a9  push    r12
0x1400032ab  push    r14
0x1400032ad  push    r15
0x1400032af  lea     rbp, [rsp-13D0h]
0x1400032b7  mov     eax, 14D0h
0x1400032bc  call    _alloca_probe
0x1400032c1  sub     rsp, rax
0x1400032c4  mov     rax, cs:__security_cookie
0x1400032cb  xor     rax, rsp
0x1400032ce  mov     [rbp+1400h+var_40], rax
0x1400032d5  mov     rdi, [rbp+1400h+arg_28]
0x1400032dc  mov     r14, r8
0x1400032df  mov     esi, edx
0x1400032e1  mov     r15, rcx
0x1400032e4  xor     edx, edx; Val
0x1400032e6  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400032eb  mov     r8d, 98h; Size
0x1400032f1  call    memset_0
0x1400032f6  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1400032fd  xor     r12d, r12d
0x140003300  mov     [rbp+1400h+OutputString], r12w
0x140003308  mov     [rbp+1400h+var_1440], r12b
0x14000330c  mov     ecx, [rdx]; this
0x14000330e  mov     eax, [rdx+4]
0x140003311  mov     [rsp+1500h+var_14D8], ecx
0x140003315  mov     [rsp+1500h+var_14D4], eax
0x140003319  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000331e  cmp     dword ptr [rdx+8], 1
0x140003322  mov     ebx, eax
0x140003324  lea     eax, [r12+8]
0x140003329  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140003331  mov     ecx, r12d
0x140003334  cmovz   ecx, eax
0x140003337  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x14000333b  lea     ecx, [rax-7]
0x14000333e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003346  inc     ecx
0x140003348  mov     [rsp+1500h+var_14C8], r12
0x14000334d  mov     [rsp+1500h+var_14D0], ecx
0x140003351  call    cs:__imp_GetCurrentThreadId
0x140003357  xorps   xmm0, xmm0
0x14000335a  mov     [rsp+1500h+var_14A8], r14
0x14000335f  mov     [rsp+1500h+var_14C0], eax
0x140003363  xorps   xmm1, xmm1
0x140003366  xor     eax, eax
0x140003368  mov     [rsp+1500h+var_14A0], esi
0x14000336c  mov     [rbp+1400h+var_1468], rax
0x140003370  mov     [rbp+1400h+var_1480], rax
0x140003374  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000337b  mov     [rsp+1500h+var_149C], ebx
0x14000337f  mov     [rsp+1500h+var_14B8], r12
0x140003384  mov     [rsp+1500h+var_14B0], r12
0x140003389  mov     [rbp+1400h+var_1458], rdi
0x14000338d  mov     [rbp+1400h+var_1450], r15
0x140003391  mov     [rsp+1500h+var_1498], r12
0x140003396  movups  [rbp+1400h+var_1478], xmm0
0x14000339a  movups  [rsp+1500h+var_1490], xmm1
0x14000339f  test    rax, rax
0x1400033a2  jz      short loc_1400033AF
0x1400033a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033a9  mov     [rbp+1400h+var_1460], rax
0x1400033ad  jmp     short loc_1400033B3
0x1400033af  mov     [rbp+1400h+var_1460], r12
0x1400033b3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400033ba  test    rax, rax
0x1400033bd  jz      short loc_1400033C9
0x1400033bf  lea     rcx, [rsp+1500h+var_14E0]
0x1400033c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033c9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400033d0  test    rax, rax
0x1400033d3  jz      short loc_1400033E9
0x1400033d5  mov     r8d, 400h
0x1400033db  lea     rdx, [rbp+1400h+var_1440]
0x1400033df  lea     rcx, [rsp+1500h+var_14E0]
0x1400033e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033e9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400033f0  test    rax, rax
0x1400033f3  jz      short loc_1400033FF
0x1400033f5  lea     rcx, [rsp+1500h+var_14E0]
0x1400033fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400033ff  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003406  test    rax, rax
0x140003409  jz      short loc_14000341C
0x14000340b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003410  jnz     short loc_14000341C
0x140003412  lea     rcx, [rsp+1500h+var_14E0]
0x140003417  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000341c  cmp     [rsp+1500h+var_14D8], r12d
0x140003421  jge     loc_14000351E
0x140003427  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000342e  jnz     short loc_14000344F
0x140003430  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003437  test    rax, rax
0x14000343a  jz      short loc_140003445
0x14000343c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003441  test    al, al
0x140003443  jmp     short loc_14000344D
0x140003445  call    cs:__imp_IsDebuggerPresent
0x14000344b  test    eax, eax
0x14000344d  jz      short loc_140003456
0x14000344f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003454  jz      short loc_14000347C
0x140003456  mov     rax, cs:g_pfnResultLoggingCallback
0x14000345d  test    rax, rax
0x140003460  jz      short loc_1400034D5
0x140003462  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003469  jnz     short loc_1400034D5
0x14000346b  xor     r8d, r8d
0x14000346e  lea     rcx, [rsp+1500h+var_14E0]
0x140003473  xor     edx, edx
0x140003475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000347a  jmp     short loc_1400034D5
0x14000347c  mov     rax, cs:g_pfnResultLoggingCallback
0x140003483  mov     ebx, 800h
0x140003488  test    rax, rax
0x14000348b  jz      short loc_1400034AA
0x14000348d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003494  jnz     short loc_1400034AA
0x140003496  mov     r8d, ebx
0x140003499  lea     rdx, [rbp+1400h+OutputString]
0x1400034a0  lea     rcx, [rsp+1500h+var_14E0]
0x1400034a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034aa  cmp     [rbp+1400h+OutputString], r12w
0x1400034b2  jnz     short loc_1400034C8
0x1400034b4  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1400034b9  mov     rdx, rbx; unsigned __int16 *
0x1400034bc  lea     rcx, [rbp+1400h+OutputString]; this
0x1400034c3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400034c8  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1400034cf  call    cs:__imp_OutputDebugStringW
0x1400034d5  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1400034da  jnz     short loc_1400034E5
0x1400034dc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400034e3  jz      short loc_1400034F6
0x1400034e5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400034ec  test    rax, rax
0x1400034ef  jz      short loc_1400034F6
0x1400034f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400034f6  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1400034fb  jnz     short loc_140003524
0x1400034fd  mov     rcx, [rbp+1400h+var_40]
0x140003504  xor     rcx, rsp; StackCookie
0x140003507  call    __security_check_cookie
0x14000350c  add     rsp, 14D0h
0x140003513  pop     r15
0x140003515  pop     r14
0x140003517  pop     r12
0x140003519  pop     rdi
0x14000351a  pop     rsi
0x14000351b  pop     rbx
0x14000351c  pop     rbp
0x14000351d  retn
0x14000351e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140003524  lea     rcx, [rsp+1500h+var_14E0]; this
0x140003529  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
