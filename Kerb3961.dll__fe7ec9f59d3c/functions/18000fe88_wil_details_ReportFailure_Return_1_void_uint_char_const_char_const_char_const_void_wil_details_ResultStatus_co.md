# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000fe88`
- end: `0x18001011c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000fd0c`

## callees

- `0x180001d40`
- `0x180002928`
- `0x180008018`
- `0x180009450`
- `0x180009e94`
- `0x18000a074`
- `0x18000fe88`
- `0x18001d300`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001002d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001002d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800100b7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800100b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ff32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ff32`

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
0x18000fe88  mov     [rsp-8+arg_10], rbx
0x18000fe8d  push    rbp
0x18000fe8e  push    rsi
0x18000fe8f  push    rdi
0x18000fe90  push    r14
0x18000fe92  push    r15
0x18000fe94  lea     rbp, [rsp-13D0h]
0x18000fe9c  mov     eax, 14D0h
0x18000fea1  call    _alloca_probe
0x18000fea6  sub     rsp, rax
0x18000fea9  mov     rax, cs:__security_cookie
0x18000feb0  xor     rax, rsp
0x18000feb3  mov     [rbp+13F0h+var_30], rax
0x18000feba  mov     rdi, [rbp+13F0h+arg_28]
0x18000fec1  mov     esi, edx
0x18000fec3  mov     r14, rcx
0x18000fec6  xor     edx, edx; Val
0x18000fec8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000fecd  mov     r8d, 98h; Size
0x18000fed3  call    memset_0
0x18000fed8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000fedf  xor     r15d, r15d
0x18000fee2  mov     [rbp+13F0h+OutputString], r15w
0x18000feea  mov     [rbp+13F0h+var_1430], r15b
0x18000feee  mov     ecx, [rdx]; this
0x18000fef0  mov     eax, [rdx+4]
0x18000fef3  mov     [rsp+14F0h+var_14C8], ecx
0x18000fef7  mov     [rsp+14F0h+var_14C4], eax
0x18000fefb  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000ff00  cmp     dword ptr [rdx+8], 1
0x18000ff04  mov     ebx, eax
0x18000ff06  lea     eax, [r15+8]
0x18000ff0a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000ff12  mov     ecx, r15d
0x18000ff15  cmovz   ecx, eax
0x18000ff18  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000ff1c  lea     ecx, [rax-7]
0x18000ff1f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ff27  inc     ecx
0x18000ff29  mov     [rsp+14F0h+var_14B8], r15
0x18000ff2e  mov     [rsp+14F0h+var_14C0], ecx
0x18000ff32  call    cs:__imp_GetCurrentThreadId
0x18000ff38  xorps   xmm0, xmm0
0x18000ff3b  mov     [rsp+14F0h+var_1490], esi
0x18000ff3f  mov     [rsp+14F0h+var_14B0], eax
0x18000ff43  xorps   xmm1, xmm1
0x18000ff46  lea     rax, aWil; "wil"
0x18000ff4d  mov     [rsp+14F0h+var_148C], ebx
0x18000ff51  mov     [rsp+14F0h+var_1498], rax
0x18000ff56  xor     eax, eax
0x18000ff58  mov     [rbp+13F0h+var_1458], rax
0x18000ff5c  mov     [rbp+13F0h+var_1470], rax
0x18000ff60  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000ff67  mov     [rsp+14F0h+var_14A8], r15
0x18000ff6c  mov     [rsp+14F0h+var_14A0], r15
0x18000ff71  mov     [rbp+13F0h+var_1448], rdi
0x18000ff75  mov     [rbp+13F0h+var_1440], r14
0x18000ff79  mov     [rsp+14F0h+var_1488], r15
0x18000ff7e  movups  [rbp+13F0h+var_1468], xmm0
0x18000ff82  movups  [rsp+14F0h+var_1480], xmm1
0x18000ff87  test    rax, rax
0x18000ff8a  jz      short loc_18000FF97
0x18000ff8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff91  mov     [rbp+13F0h+var_1450], rax
0x18000ff95  jmp     short loc_18000FF9B
0x18000ff97  mov     [rbp+13F0h+var_1450], r15
0x18000ff9b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000ffa2  test    rax, rax
0x18000ffa5  jz      short loc_18000FFB1
0x18000ffa7  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ffac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffb1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000ffb8  test    rax, rax
0x18000ffbb  jz      short loc_18000FFD1
0x18000ffbd  mov     r8d, 400h
0x18000ffc3  lea     rdx, [rbp+13F0h+var_1430]
0x18000ffc7  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ffcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffd1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ffd8  test    rax, rax
0x18000ffdb  jz      short loc_18000FFE7
0x18000ffdd  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ffe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffe7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ffee  test    rax, rax
0x18000fff1  jz      short loc_180010004
0x18000fff3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000fff8  jnz     short loc_180010004
0x18000fffa  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ffff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010004  cmp     [rsp+14F0h+var_14C8], r15d
0x180010009  jge     loc_18001010B
0x18001000f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180010016  jnz     short loc_180010037
0x180010018  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001001f  test    rax, rax
0x180010022  jz      short loc_18001002D
0x180010024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010029  test    al, al
0x18001002b  jmp     short loc_180010035
0x18001002d  call    cs:__imp_IsDebuggerPresent
0x180010033  test    eax, eax
0x180010035  jz      short loc_18001003E
0x180010037  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001003c  jz      short loc_180010064
0x18001003e  mov     rax, cs:g_pfnResultLoggingCallback
0x180010045  test    rax, rax
0x180010048  jz      short loc_1800100BD
0x18001004a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180010051  jnz     short loc_1800100BD
0x180010053  xor     r8d, r8d
0x180010056  lea     rcx, [rsp+14F0h+var_14D0]
0x18001005b  xor     edx, edx
0x18001005d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010062  jmp     short loc_1800100BD
0x180010064  mov     rax, cs:g_pfnResultLoggingCallback
0x18001006b  mov     ebx, 800h
0x180010070  test    rax, rax
0x180010073  jz      short loc_180010092
0x180010075  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001007c  jnz     short loc_180010092
0x18001007e  mov     r8d, ebx
0x180010081  lea     rdx, [rbp+13F0h+OutputString]
0x180010088  lea     rcx, [rsp+14F0h+var_14D0]
0x18001008d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010092  cmp     [rbp+13F0h+OutputString], r15w
0x18001009a  jnz     short loc_1800100B0
0x18001009c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800100a1  mov     rdx, rbx; unsigned __int16 *
0x1800100a4  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800100ab  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800100b0  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800100b7  call    cs:__imp_OutputDebugStringW
0x1800100bd  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800100c2  jnz     short loc_1800100CD
0x1800100c4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800100cb  jz      short loc_1800100DE
0x1800100cd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800100d4  test    rax, rax
0x1800100d7  jz      short loc_1800100DE
0x1800100d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100de  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800100e3  jnz     short loc_180010111
0x1800100e5  mov     rcx, [rbp+13F0h+var_30]
0x1800100ec  xor     rcx, rsp; StackCookie
0x1800100ef  call    __security_check_cookie
0x1800100f4  mov     rbx, [rsp+14F0h+arg_10]
0x1800100fc  add     rsp, 14D0h
0x180010103  pop     r15
0x180010105  pop     r14
0x180010107  pop     rdi
0x180010108  pop     rsi
0x180010109  pop     rbp
0x18001010a  retn
0x18001010b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180010111  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180010116  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
