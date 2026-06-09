# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002f64`
- end: `0x1800031ef`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002a3c`

## callees

- `0x180001ac0`
- `0x1800026b4`
- `0x180002f64`
- `0x180004ed4`
- `0x1800066b4`
- `0x180008520`
- `0x1800086ec`
- `0x1800228f0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003011`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003011`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000318f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000318f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003105`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003105`

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
0x180002f64  push    rbp
0x180002f66  push    rbx
0x180002f67  push    rsi
0x180002f68  push    rdi
0x180002f69  push    r12
0x180002f6b  push    r14
0x180002f6d  push    r15
0x180002f6f  lea     rbp, [rsp-13D0h]
0x180002f77  mov     eax, 14D0h
0x180002f7c  call    _alloca_probe
0x180002f81  sub     rsp, rax
0x180002f84  mov     rax, cs:__security_cookie
0x180002f8b  xor     rax, rsp
0x180002f8e  mov     [rbp+1400h+var_40], rax
0x180002f95  mov     rdi, [rbp+1400h+arg_28]
0x180002f9c  mov     r14, r8
0x180002f9f  mov     esi, edx
0x180002fa1  mov     r15, rcx
0x180002fa4  xor     edx, edx; Val
0x180002fa6  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002fab  mov     r8d, 98h; Size
0x180002fb1  call    memset_0
0x180002fb6  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180002fbd  xor     r12d, r12d
0x180002fc0  mov     [rbp+1400h+OutputString], r12w
0x180002fc8  mov     [rbp+1400h+var_1440], r12b
0x180002fcc  mov     ecx, [rdx]; this
0x180002fce  mov     eax, [rdx+4]
0x180002fd1  mov     [rsp+1500h+var_14D8], ecx
0x180002fd5  mov     [rsp+1500h+var_14D4], eax
0x180002fd9  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002fde  cmp     dword ptr [rdx+8], 1
0x180002fe2  mov     ebx, eax
0x180002fe4  lea     eax, [r12+8]
0x180002fe9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180002ff1  mov     ecx, r12d
0x180002ff4  cmovz   ecx, eax
0x180002ff7  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180002ffb  lea     ecx, [rax-7]
0x180002ffe  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003006  inc     ecx
0x180003008  mov     [rsp+1500h+var_14C8], r12
0x18000300d  mov     [rsp+1500h+var_14D0], ecx
0x180003011  call    cs:__imp_GetCurrentThreadId
0x180003017  xorps   xmm0, xmm0
0x18000301a  mov     [rsp+1500h+var_14A8], r14
0x18000301f  mov     [rsp+1500h+var_14C0], eax
0x180003023  xorps   xmm1, xmm1
0x180003026  xor     eax, eax
0x180003028  mov     [rsp+1500h+var_14A0], esi
0x18000302c  mov     [rbp+1400h+var_1468], rax
0x180003030  mov     [rbp+1400h+var_1480], rax
0x180003034  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000303b  mov     [rsp+1500h+var_149C], ebx
0x18000303f  mov     [rsp+1500h+var_14B8], r12
0x180003044  mov     [rsp+1500h+var_14B0], r12
0x180003049  mov     [rbp+1400h+var_1458], rdi
0x18000304d  mov     [rbp+1400h+var_1450], r15
0x180003051  mov     [rsp+1500h+var_1498], r12
0x180003056  movups  [rbp+1400h+var_1478], xmm0
0x18000305a  movups  [rsp+1500h+var_1490], xmm1
0x18000305f  test    rax, rax
0x180003062  jz      short loc_18000306F
0x180003064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003069  mov     [rbp+1400h+var_1460], rax
0x18000306d  jmp     short loc_180003073
0x18000306f  mov     [rbp+1400h+var_1460], r12
0x180003073  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000307a  test    rax, rax
0x18000307d  jz      short loc_180003089
0x18000307f  lea     rcx, [rsp+1500h+var_14E0]
0x180003084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003089  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003090  test    rax, rax
0x180003093  jz      short loc_1800030A9
0x180003095  mov     r8d, 400h
0x18000309b  lea     rdx, [rbp+1400h+var_1440]
0x18000309f  lea     rcx, [rsp+1500h+var_14E0]
0x1800030a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030a9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800030b0  test    rax, rax
0x1800030b3  jz      short loc_1800030BF
0x1800030b5  lea     rcx, [rsp+1500h+var_14E0]
0x1800030ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030bf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800030c6  test    rax, rax
0x1800030c9  jz      short loc_1800030DC
0x1800030cb  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800030d0  jnz     short loc_1800030DC
0x1800030d2  lea     rcx, [rsp+1500h+var_14E0]
0x1800030d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030dc  cmp     [rsp+1500h+var_14D8], r12d
0x1800030e1  jge     loc_1800031DE
0x1800030e7  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800030ee  jnz     short loc_18000310F
0x1800030f0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800030f7  test    rax, rax
0x1800030fa  jz      short loc_180003105
0x1800030fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003101  test    al, al
0x180003103  jmp     short loc_18000310D
0x180003105  call    cs:__imp_IsDebuggerPresent
0x18000310b  test    eax, eax
0x18000310d  jz      short loc_180003116
0x18000310f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003114  jz      short loc_18000313C
0x180003116  mov     rax, cs:g_pfnResultLoggingCallback
0x18000311d  test    rax, rax
0x180003120  jz      short loc_180003195
0x180003122  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003129  jnz     short loc_180003195
0x18000312b  xor     r8d, r8d
0x18000312e  lea     rcx, [rsp+1500h+var_14E0]
0x180003133  xor     edx, edx
0x180003135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000313a  jmp     short loc_180003195
0x18000313c  mov     rax, cs:g_pfnResultLoggingCallback
0x180003143  mov     ebx, 800h
0x180003148  test    rax, rax
0x18000314b  jz      short loc_18000316A
0x18000314d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003154  jnz     short loc_18000316A
0x180003156  mov     r8d, ebx
0x180003159  lea     rdx, [rbp+1400h+OutputString]
0x180003160  lea     rcx, [rsp+1500h+var_14E0]
0x180003165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000316a  cmp     [rbp+1400h+OutputString], r12w
0x180003172  jnz     short loc_180003188
0x180003174  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003179  mov     rdx, rbx; unsigned __int16 *
0x18000317c  lea     rcx, [rbp+1400h+OutputString]; this
0x180003183  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003188  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000318f  call    cs:__imp_OutputDebugStringW
0x180003195  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000319a  jnz     short loc_1800031A5
0x18000319c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800031a3  jz      short loc_1800031B6
0x1800031a5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800031ac  test    rax, rax
0x1800031af  jz      short loc_1800031B6
0x1800031b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031b6  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800031bb  jnz     short loc_1800031E4
0x1800031bd  mov     rcx, [rbp+1400h+var_40]
0x1800031c4  xor     rcx, rsp; StackCookie
0x1800031c7  call    __security_check_cookie
0x1800031cc  add     rsp, 14D0h
0x1800031d3  pop     r15
0x1800031d5  pop     r14
0x1800031d7  pop     r12
0x1800031d9  pop     rdi
0x1800031da  pop     rsi
0x1800031db  pop     rbx
0x1800031dc  pop     rbp
0x1800031dd  retn
0x1800031de  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800031e4  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800031e9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
