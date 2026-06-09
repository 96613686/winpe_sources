# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180055e30`
- end: `0x1800560c6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180055af8`

## callees

- `0x180004fa0`
- `0x180005e6c`
- `0x180055e30`
- `0x180056c64`
- `0x180057e20`
- `0x180058a18`
- `0x180058b80`
- `0x1800591f0`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055edb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180055edb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180056060`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180056060`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180055fd6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180055fd6`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
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
0x180055e30  mov     [rsp-8+arg_10], rbx
0x180055e35  push    rbp
0x180055e36  push    rsi
0x180055e37  push    rdi
0x180055e38  push    r14
0x180055e3a  push    r15
0x180055e3c  lea     rbp, [rsp-13D0h]
0x180055e44  mov     eax, 14D0h
0x180055e49  call    _alloca_probe
0x180055e4e  sub     rsp, rax
0x180055e51  mov     rax, cs:__security_cookie
0x180055e58  xor     rax, rsp
0x180055e5b  mov     [rbp+13F0h+var_30], rax
0x180055e62  mov     esi, edx
0x180055e64  mov     r14, rcx
0x180055e67  mov     rdi, [rbp+13F0h+arg_28]
0x180055e6e  xor     edx, edx; Val
0x180055e70  mov     r8d, 98h; Size
0x180055e76  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180055e7b  call    memset_0
0x180055e80  nop
0x180055e81  xor     r15d, r15d
0x180055e84  mov     [rbp+13F0h+OutputString], r15w
0x180055e8c  mov     [rbp+13F0h+var_1430], r15b
0x180055e90  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180055e97  mov     ecx, [rdx]; this
0x180055e99  mov     [rsp+14F0h+var_14C8], ecx
0x180055e9d  mov     eax, [rdx+4]
0x180055ea0  mov     [rsp+14F0h+var_14C4], eax
0x180055ea4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180055ea9  mov     ebx, eax
0x180055eab  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180055eb3  mov     ecx, r15d
0x180055eb6  lea     eax, [r15+8]
0x180055eba  cmp     dword ptr [rdx+8], 1
0x180055ebe  cmovz   ecx, eax
0x180055ec1  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180055ec5  lea     ecx, [rax-7]
0x180055ec8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180055ed0  inc     ecx
0x180055ed2  mov     [rsp+14F0h+var_14C0], ecx
0x180055ed6  mov     [rsp+14F0h+var_14B8], r15
0x180055edb  call    cs:__imp_GetCurrentThreadId
0x180055ee1  mov     [rsp+14F0h+var_14B0], eax
0x180055ee5  lea     rax, aWil; "wil"
0x180055eec  mov     [rsp+14F0h+var_1498], rax
0x180055ef1  mov     [rsp+14F0h+var_1490], esi
0x180055ef5  mov     [rsp+14F0h+var_148C], ebx
0x180055ef9  mov     [rsp+14F0h+var_14A8], r15
0x180055efe  mov     [rsp+14F0h+var_14A0], r15
0x180055f03  mov     [rbp+13F0h+var_1448], rdi
0x180055f07  mov     [rbp+13F0h+var_1440], r14
0x180055f0b  mov     [rsp+14F0h+var_1488], r15
0x180055f10  xorps   xmm0, xmm0
0x180055f13  xor     eax, eax
0x180055f15  movups  [rbp+13F0h+var_1468], xmm0
0x180055f19  mov     [rbp+13F0h+var_1458], rax
0x180055f1d  xorps   xmm1, xmm1
0x180055f20  movups  [rsp+14F0h+var_1480], xmm1
0x180055f25  mov     [rbp+13F0h+var_1470], rax
0x180055f29  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180055f30  test    rax, rax
0x180055f33  jz      short loc_180055F40
0x180055f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f3a  mov     [rbp+13F0h+var_1450], rax
0x180055f3e  jmp     short loc_180055F44
0x180055f40  mov     [rbp+13F0h+var_1450], r15
0x180055f44  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180055f4b  test    rax, rax
0x180055f4e  jz      short loc_180055F5A
0x180055f50  lea     rcx, [rsp+14F0h+var_14D0]
0x180055f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f5a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180055f61  test    rax, rax
0x180055f64  jz      short loc_180055F7A
0x180055f66  mov     r8d, 400h
0x180055f6c  lea     rdx, [rbp+13F0h+var_1430]
0x180055f70  lea     rcx, [rsp+14F0h+var_14D0]
0x180055f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f7a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180055f81  test    rax, rax
0x180055f84  jz      short loc_180055F90
0x180055f86  lea     rcx, [rsp+14F0h+var_14D0]
0x180055f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055f90  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180055f97  test    rax, rax
0x180055f9a  jz      short loc_180055FAD
0x180055f9c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180055fa1  jnz     short loc_180055FAD
0x180055fa3  lea     rcx, [rsp+14F0h+var_14D0]
0x180055fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fad  cmp     [rsp+14F0h+var_14C8], r15d
0x180055fb2  jge     loc_1800560C0
0x180055fb8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180055fbf  jnz     short loc_180055FE0
0x180055fc1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180055fc8  test    rax, rax
0x180055fcb  jz      short loc_180055FD6
0x180055fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055fd2  test    al, al
0x180055fd4  jmp     short loc_180055FDE
0x180055fd6  call    cs:__imp_IsDebuggerPresent
0x180055fdc  test    eax, eax
0x180055fde  jz      short loc_180055FE7
0x180055fe0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180055fe5  jz      short loc_18005600D
0x180055fe7  mov     rax, cs:g_pfnResultLoggingCallback
0x180055fee  test    rax, rax
0x180055ff1  jz      short loc_180056066
0x180055ff3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180055ffa  jnz     short loc_180056066
0x180055ffc  xor     r8d, r8d
0x180055fff  xor     edx, edx
0x180056001  lea     rcx, [rsp+14F0h+var_14D0]
0x180056006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005600b  jmp     short loc_180056066
0x18005600d  mov     ebx, 800h
0x180056012  mov     rax, cs:g_pfnResultLoggingCallback
0x180056019  test    rax, rax
0x18005601c  jz      short loc_18005603B
0x18005601e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180056025  jnz     short loc_18005603B
0x180056027  mov     r8d, ebx
0x18005602a  lea     rdx, [rbp+13F0h+OutputString]
0x180056031  lea     rcx, [rsp+14F0h+var_14D0]
0x180056036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005603b  cmp     [rbp+13F0h+OutputString], r15w
0x180056043  jnz     short loc_180056059
0x180056045  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18005604a  mov     rdx, rbx; unsigned __int16 *
0x18005604d  lea     rcx, [rbp+13F0h+OutputString]; this
0x180056054  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180056059  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180056060  call    cs:__imp_OutputDebugStringW
0x180056066  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18005606b  jnz     short loc_180056076
0x18005606d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180056074  jz      short loc_180056088
0x180056076  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18005607d  test    rax, rax
0x180056080  jz      short loc_180056088
0x180056082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056087  nop
0x180056088  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18005608d  jnz     short loc_1800560B5
0x18005608f  mov     rcx, [rbp+13F0h+var_30]
0x180056096  xor     rcx, rsp; StackCookie
0x180056099  call    __security_check_cookie
0x18005609e  mov     rbx, [rsp+14F0h+arg_10]
0x1800560a6  add     rsp, 14D0h
0x1800560ad  pop     r15
0x1800560af  pop     r14
0x1800560b1  pop     rdi
0x1800560b2  pop     rsi
0x1800560b3  pop     rbp
0x1800560b4  retn
0x1800560b5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800560ba  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800560c0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
