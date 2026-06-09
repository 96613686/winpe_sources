# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002e60`
- end: `0x1800030ed`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002940`

## callees

- `0x180001e60`
- `0x1800028c8`
- `0x180002e60`
- `0x180005204`
- `0x1800066a0`
- `0x180008760`
- `0x180008854`
- `0x18000b390`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f0e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f0e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000308c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000308c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003002`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003002`

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
0x180002e60  push    rbp
0x180002e62  push    rbx
0x180002e63  push    rsi
0x180002e64  push    rdi
0x180002e65  push    r12
0x180002e67  push    r14
0x180002e69  push    r15
0x180002e6b  lea     rbp, [rsp-13D0h]
0x180002e73  mov     eax, 14D0h
0x180002e78  call    _alloca_probe
0x180002e7d  sub     rsp, rax
0x180002e80  mov     rax, cs:__security_cookie
0x180002e87  xor     rax, rsp
0x180002e8a  mov     [rbp+1400h+var_40], rax
0x180002e91  mov     r14, r8
0x180002e94  mov     esi, edx
0x180002e96  mov     r15, rcx
0x180002e99  mov     rdi, [rbp+1400h+arg_28]
0x180002ea0  xor     edx, edx; Val
0x180002ea2  mov     r8d, 98h; Size
0x180002ea8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002ead  call    memset_0
0x180002eb2  nop
0x180002eb3  xor     r12d, r12d
0x180002eb6  mov     [rbp+1400h+OutputString], r12w
0x180002ebe  mov     [rbp+1400h+var_1440], r12b
0x180002ec2  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180002ec9  mov     ecx, [rdx]; this
0x180002ecb  mov     [rsp+1500h+var_14D8], ecx
0x180002ecf  mov     eax, [rdx+4]
0x180002ed2  mov     [rsp+1500h+var_14D4], eax
0x180002ed6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002edb  mov     ebx, eax
0x180002edd  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180002ee5  mov     ecx, r12d
0x180002ee8  lea     eax, [r12+8]
0x180002eed  cmp     dword ptr [rdx+8], 1
0x180002ef1  cmovz   ecx, eax
0x180002ef4  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180002ef8  lea     ecx, [rax-7]
0x180002efb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002f03  inc     ecx
0x180002f05  mov     [rsp+1500h+var_14D0], ecx
0x180002f09  mov     [rsp+1500h+var_14C8], r12
0x180002f0e  call    cs:__imp_GetCurrentThreadId
0x180002f14  mov     [rsp+1500h+var_14C0], eax
0x180002f18  mov     [rsp+1500h+var_14A8], r14
0x180002f1d  mov     [rsp+1500h+var_14A0], esi
0x180002f21  mov     [rsp+1500h+var_149C], ebx
0x180002f25  mov     [rsp+1500h+var_14B8], r12
0x180002f2a  mov     [rsp+1500h+var_14B0], r12
0x180002f2f  mov     [rbp+1400h+var_1458], rdi
0x180002f33  mov     [rbp+1400h+var_1450], r15
0x180002f37  mov     [rsp+1500h+var_1498], r12
0x180002f3c  xorps   xmm0, xmm0
0x180002f3f  xor     eax, eax
0x180002f41  movups  [rbp+1400h+var_1478], xmm0
0x180002f45  mov     [rbp+1400h+var_1468], rax
0x180002f49  xorps   xmm1, xmm1
0x180002f4c  movups  [rsp+1500h+var_1490], xmm1
0x180002f51  mov     [rbp+1400h+var_1480], rax
0x180002f55  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002f5c  test    rax, rax
0x180002f5f  jz      short loc_180002F6C
0x180002f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f66  mov     [rbp+1400h+var_1460], rax
0x180002f6a  jmp     short loc_180002F70
0x180002f6c  mov     [rbp+1400h+var_1460], r12
0x180002f70  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002f77  test    rax, rax
0x180002f7a  jz      short loc_180002F86
0x180002f7c  lea     rcx, [rsp+1500h+var_14E0]
0x180002f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f86  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002f8d  test    rax, rax
0x180002f90  jz      short loc_180002FA6
0x180002f92  mov     r8d, 400h
0x180002f98  lea     rdx, [rbp+1400h+var_1440]
0x180002f9c  lea     rcx, [rsp+1500h+var_14E0]
0x180002fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fa6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002fad  test    rax, rax
0x180002fb0  jz      short loc_180002FBC
0x180002fb2  lea     rcx, [rsp+1500h+var_14E0]
0x180002fb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fbc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002fc3  test    rax, rax
0x180002fc6  jz      short loc_180002FD9
0x180002fc8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002fcd  jnz     short loc_180002FD9
0x180002fcf  lea     rcx, [rsp+1500h+var_14E0]
0x180002fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fd9  cmp     [rsp+1500h+var_14D8], r12d
0x180002fde  jge     loc_1800030E7
0x180002fe4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002feb  jnz     short loc_18000300C
0x180002fed  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002ff4  test    rax, rax
0x180002ff7  jz      short loc_180003002
0x180002ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ffe  test    al, al
0x180003000  jmp     short loc_18000300A
0x180003002  call    cs:__imp_IsDebuggerPresent
0x180003008  test    eax, eax
0x18000300a  jz      short loc_180003013
0x18000300c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003011  jz      short loc_180003039
0x180003013  mov     rax, cs:g_pfnResultLoggingCallback
0x18000301a  test    rax, rax
0x18000301d  jz      short loc_180003092
0x18000301f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003026  jnz     short loc_180003092
0x180003028  xor     r8d, r8d
0x18000302b  xor     edx, edx
0x18000302d  lea     rcx, [rsp+1500h+var_14E0]
0x180003032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003037  jmp     short loc_180003092
0x180003039  mov     ebx, 800h
0x18000303e  mov     rax, cs:g_pfnResultLoggingCallback
0x180003045  test    rax, rax
0x180003048  jz      short loc_180003067
0x18000304a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003051  jnz     short loc_180003067
0x180003053  mov     r8d, ebx
0x180003056  lea     rdx, [rbp+1400h+OutputString]
0x18000305d  lea     rcx, [rsp+1500h+var_14E0]
0x180003062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003067  cmp     [rbp+1400h+OutputString], r12w
0x18000306f  jnz     short loc_180003085
0x180003071  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003076  mov     rdx, rbx; unsigned __int16 *
0x180003079  lea     rcx, [rbp+1400h+OutputString]; this
0x180003080  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003085  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000308c  call    cs:__imp_OutputDebugStringW
0x180003092  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003097  jnz     short loc_1800030A2
0x180003099  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800030a0  jz      short loc_1800030B4
0x1800030a2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800030a9  test    rax, rax
0x1800030ac  jz      short loc_1800030B4
0x1800030ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b3  nop
0x1800030b4  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800030b9  jnz     short loc_1800030DC
0x1800030bb  mov     rcx, [rbp+1400h+var_40]
0x1800030c2  xor     rcx, rsp; StackCookie
0x1800030c5  call    __security_check_cookie
0x1800030ca  add     rsp, 14D0h
0x1800030d1  pop     r15
0x1800030d3  pop     r14
0x1800030d5  pop     r12
0x1800030d7  pop     rdi
0x1800030d8  pop     rsi
0x1800030d9  pop     rbx
0x1800030da  pop     rbp
0x1800030db  retn
0x1800030dc  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800030e1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800030e7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
