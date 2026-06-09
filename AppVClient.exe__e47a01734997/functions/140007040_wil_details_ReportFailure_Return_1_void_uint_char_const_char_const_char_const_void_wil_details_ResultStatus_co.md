# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140007040`
- end: `0x1400072d6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140006b20`

## callees

- `0x140004280`
- `0x1400050e0`
- `0x140007040`
- `0x14000c664`
- `0x140011160`
- `0x140013a20`
- `0x140013c48`
- `0x140065be0`
- `0x14006a010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1400071e6`
- `KERNEL32!IsDebuggerPresent` at `0x1400071e6`
- `KERNEL32!OutputDebugStringW` at `0x140007270`
- `KERNEL32!OutputDebugStringW` at `0x140007270`
- `KERNEL32!GetCurrentThreadId` at `0x1400070eb`
- `KERNEL32!GetCurrentThreadId` at `0x1400070eb`

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
      wil::GetFailureLogString(OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v14);
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
0x140007040  mov     [rsp-8+arg_10], rbx
0x140007045  push    rbp
0x140007046  push    rsi
0x140007047  push    rdi
0x140007048  push    r14
0x14000704a  push    r15
0x14000704c  lea     rbp, [rsp-13D0h]
0x140007054  mov     eax, 14D0h
0x140007059  call    _alloca_probe
0x14000705e  sub     rsp, rax
0x140007061  mov     rax, cs:__security_cookie
0x140007068  xor     rax, rsp
0x14000706b  mov     [rbp+13F0h+var_30], rax
0x140007072  mov     esi, edx
0x140007074  mov     r14, rcx
0x140007077  mov     rdi, [rbp+13F0h+arg_28]
0x14000707e  xor     edx, edx; Val
0x140007080  mov     r8d, 98h; Size
0x140007086  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14000708b  call    memset_0
0x140007090  nop
0x140007091  xor     r15d, r15d
0x140007094  mov     [rbp+13F0h+OutputString], r15w
0x14000709c  mov     [rbp+13F0h+var_1430], r15b
0x1400070a0  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1400070a7  mov     ecx, [rdx]; this
0x1400070a9  mov     [rsp+14F0h+var_14C8], ecx
0x1400070ad  mov     eax, [rdx+4]
0x1400070b0  mov     [rsp+14F0h+var_14C4], eax
0x1400070b4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400070b9  mov     ebx, eax
0x1400070bb  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1400070c3  mov     ecx, r15d
0x1400070c6  lea     eax, [r15+8]
0x1400070ca  cmp     dword ptr [rdx+8], 1
0x1400070ce  cmovz   ecx, eax
0x1400070d1  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400070d5  lea     ecx, [rax-7]
0x1400070d8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400070e0  inc     ecx
0x1400070e2  mov     [rsp+14F0h+var_14C0], ecx
0x1400070e6  mov     [rsp+14F0h+var_14B8], r15
0x1400070eb  call    cs:__imp_GetCurrentThreadId
0x1400070f1  mov     [rsp+14F0h+var_14B0], eax
0x1400070f5  lea     rax, aWil; "wil"
0x1400070fc  mov     [rsp+14F0h+var_1498], rax
0x140007101  mov     [rsp+14F0h+var_1490], esi
0x140007105  mov     [rsp+14F0h+var_148C], ebx
0x140007109  mov     [rsp+14F0h+var_14A8], r15
0x14000710e  mov     [rsp+14F0h+var_14A0], r15
0x140007113  mov     [rbp+13F0h+var_1448], rdi
0x140007117  mov     [rbp+13F0h+var_1440], r14
0x14000711b  mov     [rsp+14F0h+var_1488], r15
0x140007120  xorps   xmm0, xmm0
0x140007123  xor     eax, eax
0x140007125  movups  [rbp+13F0h+var_1468], xmm0
0x140007129  mov     [rbp+13F0h+var_1458], rax
0x14000712d  xorps   xmm1, xmm1
0x140007130  movups  [rsp+14F0h+var_1480], xmm1
0x140007135  mov     [rbp+13F0h+var_1470], rax
0x140007139  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140007140  test    rax, rax
0x140007143  jz      short loc_140007150
0x140007145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000714a  mov     [rbp+13F0h+var_1450], rax
0x14000714e  jmp     short loc_140007154
0x140007150  mov     [rbp+13F0h+var_1450], r15
0x140007154  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000715b  test    rax, rax
0x14000715e  jz      short loc_14000716A
0x140007160  lea     rcx, [rsp+14F0h+var_14D0]
0x140007165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000716a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140007171  test    rax, rax
0x140007174  jz      short loc_14000718A
0x140007176  mov     r8d, 400h
0x14000717c  lea     rdx, [rbp+13F0h+var_1430]
0x140007180  lea     rcx, [rsp+14F0h+var_14D0]
0x140007185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000718a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007191  test    rax, rax
0x140007194  jz      short loc_1400071A0
0x140007196  lea     rcx, [rsp+14F0h+var_14D0]
0x14000719b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071a0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400071a7  test    rax, rax
0x1400071aa  jz      short loc_1400071BD
0x1400071ac  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400071b1  jnz     short loc_1400071BD
0x1400071b3  lea     rcx, [rsp+14F0h+var_14D0]
0x1400071b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071bd  cmp     [rsp+14F0h+var_14C8], r15d
0x1400071c2  jge     loc_1400072D0
0x1400071c8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1400071cf  jnz     short loc_1400071F0
0x1400071d1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400071d8  test    rax, rax
0x1400071db  jz      short loc_1400071E6
0x1400071dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071e2  test    al, al
0x1400071e4  jmp     short loc_1400071EE
0x1400071e6  call    cs:__imp_IsDebuggerPresent
0x1400071ec  test    eax, eax
0x1400071ee  jz      short loc_1400071F7
0x1400071f0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400071f5  jz      short loc_14000721D
0x1400071f7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400071fe  test    rax, rax
0x140007201  jz      short loc_140007276
0x140007203  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000720a  jnz     short loc_140007276
0x14000720c  xor     r8d, r8d
0x14000720f  xor     edx, edx
0x140007211  lea     rcx, [rsp+14F0h+var_14D0]
0x140007216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000721b  jmp     short loc_140007276
0x14000721d  mov     ebx, 800h
0x140007222  mov     rax, cs:g_pfnResultLoggingCallback
0x140007229  test    rax, rax
0x14000722c  jz      short loc_14000724B
0x14000722e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140007235  jnz     short loc_14000724B
0x140007237  mov     r8d, ebx
0x14000723a  lea     rdx, [rbp+13F0h+OutputString]
0x140007241  lea     rcx, [rsp+14F0h+var_14D0]
0x140007246  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000724b  cmp     [rbp+13F0h+OutputString], r15w
0x140007253  jnz     short loc_140007269
0x140007255  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000725a  mov     rdx, rbx; wchar_t *
0x14000725d  lea     rcx, [rbp+13F0h+OutputString]; Buffer
0x140007264  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140007269  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140007270  call    cs:__imp_OutputDebugStringW
0x140007276  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000727b  jnz     short loc_140007286
0x14000727d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x140007284  jz      short loc_140007298
0x140007286  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000728d  test    rax, rax
0x140007290  jz      short loc_140007298
0x140007292  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007297  nop
0x140007298  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x14000729d  jnz     short loc_1400072C5
0x14000729f  mov     rcx, [rbp+13F0h+var_30]
0x1400072a6  xor     rcx, rsp; StackCookie
0x1400072a9  call    __security_check_cookie
0x1400072ae  mov     rbx, [rsp+14F0h+arg_10]
0x1400072b6  add     rsp, 14D0h
0x1400072bd  pop     r15
0x1400072bf  pop     r14
0x1400072c1  pop     rdi
0x1400072c2  pop     rsi
0x1400072c3  pop     rbp
0x1400072c4  retn
0x1400072c5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400072ca  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400072d0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
