# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002ef0`
- end: `0x18000317d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800029d0`

## callees

- `0x180001ef0`
- `0x180002958`
- `0x180002ef0`
- `0x180005294`
- `0x180006730`
- `0x1800087f0`
- `0x1800088e4`
- `0x18000e890`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f9e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f9e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003092`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003092`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000311c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000311c`

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
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180002ef0  push    rbp
0x180002ef2  push    rbx
0x180002ef3  push    rsi
0x180002ef4  push    rdi
0x180002ef5  push    r12
0x180002ef7  push    r14
0x180002ef9  push    r15
0x180002efb  lea     rbp, [rsp-13D0h]
0x180002f03  mov     eax, 14D0h
0x180002f08  call    _alloca_probe
0x180002f0d  sub     rsp, rax
0x180002f10  mov     rax, cs:__security_cookie
0x180002f17  xor     rax, rsp
0x180002f1a  mov     [rbp+1400h+var_40], rax
0x180002f21  mov     r14, r8
0x180002f24  mov     esi, edx
0x180002f26  mov     r15, rcx
0x180002f29  mov     rdi, [rbp+1400h+arg_28]
0x180002f30  xor     edx, edx; Val
0x180002f32  mov     r8d, 98h; Size
0x180002f38  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002f3d  call    memset_0
0x180002f42  nop
0x180002f43  xor     r12d, r12d
0x180002f46  mov     [rbp+1400h+OutputString], r12w
0x180002f4e  mov     [rbp+1400h+var_1440], r12b
0x180002f52  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180002f59  mov     ecx, [rdx]; this
0x180002f5b  mov     [rsp+1500h+var_14D8], ecx
0x180002f5f  mov     eax, [rdx+4]
0x180002f62  mov     [rsp+1500h+var_14D4], eax
0x180002f66  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002f6b  mov     ebx, eax
0x180002f6d  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180002f75  mov     ecx, r12d
0x180002f78  lea     eax, [r12+8]
0x180002f7d  cmp     dword ptr [rdx+8], 1
0x180002f81  cmovz   ecx, eax
0x180002f84  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180002f88  lea     ecx, [rax-7]
0x180002f8b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002f93  inc     ecx
0x180002f95  mov     [rsp+1500h+var_14D0], ecx
0x180002f99  mov     [rsp+1500h+var_14C8], r12
0x180002f9e  call    cs:__imp_GetCurrentThreadId
0x180002fa4  mov     [rsp+1500h+var_14C0], eax
0x180002fa8  mov     [rsp+1500h+var_14A8], r14
0x180002fad  mov     [rsp+1500h+var_14A0], esi
0x180002fb1  mov     [rsp+1500h+var_149C], ebx
0x180002fb5  mov     [rsp+1500h+var_14B8], r12
0x180002fba  mov     [rsp+1500h+var_14B0], r12
0x180002fbf  mov     [rbp+1400h+var_1458], rdi
0x180002fc3  mov     [rbp+1400h+var_1450], r15
0x180002fc7  mov     [rsp+1500h+var_1498], r12
0x180002fcc  xorps   xmm0, xmm0
0x180002fcf  xor     eax, eax
0x180002fd1  movups  [rbp+1400h+var_1478], xmm0
0x180002fd5  mov     [rbp+1400h+var_1468], rax
0x180002fd9  xorps   xmm1, xmm1
0x180002fdc  movups  [rsp+1500h+var_1490], xmm1
0x180002fe1  mov     [rbp+1400h+var_1480], rax
0x180002fe5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002fec  test    rax, rax
0x180002fef  jz      short loc_180002FFC
0x180002ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ff6  mov     [rbp+1400h+var_1460], rax
0x180002ffa  jmp     short loc_180003000
0x180002ffc  mov     [rbp+1400h+var_1460], r12
0x180003000  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003007  test    rax, rax
0x18000300a  jz      short loc_180003016
0x18000300c  lea     rcx, [rsp+1500h+var_14E0]
0x180003011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003016  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000301d  test    rax, rax
0x180003020  jz      short loc_180003036
0x180003022  mov     r8d, 400h
0x180003028  lea     rdx, [rbp+1400h+var_1440]
0x18000302c  lea     rcx, [rsp+1500h+var_14E0]
0x180003031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003036  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000303d  test    rax, rax
0x180003040  jz      short loc_18000304C
0x180003042  lea     rcx, [rsp+1500h+var_14E0]
0x180003047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000304c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003053  test    rax, rax
0x180003056  jz      short loc_180003069
0x180003058  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000305d  jnz     short loc_180003069
0x18000305f  lea     rcx, [rsp+1500h+var_14E0]
0x180003064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003069  cmp     [rsp+1500h+var_14D8], r12d
0x18000306e  jge     loc_180003177
0x180003074  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000307b  jnz     short loc_18000309C
0x18000307d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003084  test    rax, rax
0x180003087  jz      short loc_180003092
0x180003089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000308e  test    al, al
0x180003090  jmp     short loc_18000309A
0x180003092  call    cs:__imp_IsDebuggerPresent
0x180003098  test    eax, eax
0x18000309a  jz      short loc_1800030A3
0x18000309c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800030a1  jz      short loc_1800030C9
0x1800030a3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800030aa  test    rax, rax
0x1800030ad  jz      short loc_180003122
0x1800030af  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800030b6  jnz     short loc_180003122
0x1800030b8  xor     r8d, r8d
0x1800030bb  xor     edx, edx
0x1800030bd  lea     rcx, [rsp+1500h+var_14E0]
0x1800030c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030c7  jmp     short loc_180003122
0x1800030c9  mov     ebx, 800h
0x1800030ce  mov     rax, cs:g_pfnResultLoggingCallback
0x1800030d5  test    rax, rax
0x1800030d8  jz      short loc_1800030F7
0x1800030da  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800030e1  jnz     short loc_1800030F7
0x1800030e3  mov     r8d, ebx
0x1800030e6  lea     rdx, [rbp+1400h+OutputString]
0x1800030ed  lea     rcx, [rsp+1500h+var_14E0]
0x1800030f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030f7  cmp     [rbp+1400h+OutputString], r12w
0x1800030ff  jnz     short loc_180003115
0x180003101  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003106  mov     rdx, rbx; unsigned __int16 *
0x180003109  lea     rcx, [rbp+1400h+OutputString]; this
0x180003110  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003115  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000311c  call    cs:__imp_OutputDebugStringW
0x180003122  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003127  jnz     short loc_180003132
0x180003129  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003130  jz      short loc_180003144
0x180003132  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003139  test    rax, rax
0x18000313c  jz      short loc_180003144
0x18000313e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003143  nop
0x180003144  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003149  jnz     short loc_18000316C
0x18000314b  mov     rcx, [rbp+1400h+var_40]
0x180003152  xor     rcx, rsp; StackCookie
0x180003155  call    __security_check_cookie
0x18000315a  add     rsp, 14D0h
0x180003161  pop     r15
0x180003163  pop     r14
0x180003165  pop     r12
0x180003167  pop     rdi
0x180003168  pop     rsi
0x180003169  pop     rbx
0x18000316a  pop     rbp
0x18000316b  retn
0x18000316c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003171  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003177  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
