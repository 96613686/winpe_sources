# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004ed8`
- end: `0x180005186`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `686`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004814`

## callees

- `0x180003870`
- `0x1800042f4`
- `0x180004ed8`
- `0x1800075f4`
- `0x180009188`
- `0x18000bcd0`
- `0x18000bf6c`
- `0x180031b80`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004fa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004fa7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005125`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005125`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000509b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000509b`

## pseudocode

```c
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
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+34h] [rbp-CCh]
  int v20; // [rsp+38h] [rbp-C8h]
  int v21; // [rsp+3Ch] [rbp-C4h]
  signed __int32 v22; // [rsp+40h] [rbp-C0h]
  _WORD *v23; // [rsp+48h] [rbp-B8h]
  DWORD CurrentThreadId; // [rsp+50h] [rbp-B0h]
  __int64 v25; // [rsp+58h] [rbp-A8h]
  __int64 v26; // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+68h] [rbp-98h]
  int v28; // [rsp+70h] [rbp-90h]
  int v29; // [rsp+74h] [rbp-8Ch]
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int128 v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+90h] [rbp-70h]
  __int128 v33; // [rsp+98h] [rbp-68h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 ModuleName; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  __int64 v37; // [rsp+C0h] [rbp-40h]
  char v38[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
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
0x180004ed8  push    rbp
0x180004eda  push    rbx
0x180004edb  push    rsi
0x180004edc  push    rdi
0x180004edd  push    r12
0x180004edf  push    r14
0x180004ee1  push    r15
0x180004ee3  lea     rbp, [rsp-13E0h]
0x180004eeb  mov     eax, 14E0h
0x180004ef0  call    _alloca_probe
0x180004ef5  sub     rsp, rax
0x180004ef8  mov     [rsp+1510h+var_14F0], 0FFFFFFFFFFFFFFFEh
0x180004f01  mov     rax, cs:__security_cookie
0x180004f08  xor     rax, rsp
0x180004f0b  mov     [rbp+1410h+var_40], rax
0x180004f12  mov     rsi, r8
0x180004f15  mov     edi, edx
0x180004f17  mov     rbx, rcx
0x180004f1a  mov     r14, [rbp+1410h+arg_28]
0x180004f21  xor     edx, edx; Val
0x180004f23  mov     r8d, 98h; Size
0x180004f29  lea     rcx, [rsp+1510h+var_14E0]; void *
0x180004f2e  call    memset_0
0x180004f33  nop
0x180004f34  xor     r12d, r12d
0x180004f37  mov     [rbp+1410h+OutputString], r12w
0x180004f3f  mov     [rbp+1410h+var_1440], r12b
0x180004f43  mov     rdx, [rbp+1410h+arg_30]; int
0x180004f4a  mov     ecx, [rdx]; this
0x180004f4c  mov     [rsp+1510h+var_14D8], ecx
0x180004f50  mov     eax, [rdx+4]
0x180004f53  mov     [rsp+1510h+var_14D4], eax
0x180004f57  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004f5c  mov     r15d, eax
0x180004f5f  mov     dword ptr [rsp+1510h+var_14E0], 1
0x180004f67  mov     ecx, r12d
0x180004f6a  lea     eax, [r12+8]
0x180004f6f  cmp     dword ptr [rdx+8], 1
0x180004f73  cmovz   ecx, eax
0x180004f76  mov     dword ptr [rsp+1510h+var_14E0+4], ecx
0x180004f7a  lea     ecx, [rax-7]
0x180004f7d  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004f85  inc     ecx
0x180004f87  mov     [rsp+1510h+var_14D0], ecx
0x180004f8b  mov     rcx, [rbp+1410h+arg_38]
0x180004f92  test    rcx, rcx
0x180004f95  jz      short loc_180004FA2
0x180004f97  cmp     [rcx], r12w
0x180004f9b  mov     [rsp+1510h+var_14C8], rcx
0x180004fa0  jnz     short loc_180004FA7
0x180004fa2  mov     [rsp+1510h+var_14C8], r12
0x180004fa7  call    cs:__imp_GetCurrentThreadId
0x180004fad  mov     [rsp+1510h+var_14C0], eax
0x180004fb1  mov     [rsp+1510h+var_14A8], rsi
0x180004fb6  mov     [rsp+1510h+var_14A0], edi
0x180004fba  mov     [rsp+1510h+var_149C], r15d
0x180004fbf  mov     [rsp+1510h+var_14B8], r12
0x180004fc4  mov     [rsp+1510h+var_14B0], r12
0x180004fc9  mov     [rbp+1410h+var_1458], r14
0x180004fcd  mov     [rbp+1410h+var_1450], rbx
0x180004fd1  mov     [rsp+1510h+var_1498], r12
0x180004fd6  xorps   xmm0, xmm0
0x180004fd9  xor     eax, eax
0x180004fdb  movups  [rbp+1410h+var_1478], xmm0
0x180004fdf  mov     [rbp+1410h+var_1468], rax
0x180004fe3  xorps   xmm1, xmm1
0x180004fe6  movups  [rbp+1410h+var_1490], xmm1
0x180004fea  mov     [rbp+1410h+var_1480], rax
0x180004fee  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004ff5  test    rax, rax
0x180004ff8  jz      short loc_180005005
0x180004ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fff  mov     [rbp+1410h+var_1460], rax
0x180005003  jmp     short loc_180005009
0x180005005  mov     [rbp+1410h+var_1460], r12
0x180005009  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005010  test    rax, rax
0x180005013  jz      short loc_18000501F
0x180005015  lea     rcx, [rsp+1510h+var_14E0]
0x18000501a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000501f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005026  test    rax, rax
0x180005029  jz      short loc_18000503F
0x18000502b  mov     r8d, 400h
0x180005031  lea     rdx, [rbp+1410h+var_1440]
0x180005035  lea     rcx, [rsp+1510h+var_14E0]
0x18000503a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000503f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005046  test    rax, rax
0x180005049  jz      short loc_180005055
0x18000504b  lea     rcx, [rsp+1510h+var_14E0]
0x180005050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005055  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000505c  test    rax, rax
0x18000505f  jz      short loc_180005072
0x180005061  test    byte ptr [rsp+1510h+var_14E0+4], 2
0x180005066  jnz     short loc_180005072
0x180005068  lea     rcx, [rsp+1510h+var_14E0]
0x18000506d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005072  cmp     [rsp+1510h+var_14D8], r12d
0x180005077  jge     loc_180005180
0x18000507d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005084  jnz     short loc_1800050A5
0x180005086  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000508d  test    rax, rax
0x180005090  jz      short loc_18000509B
0x180005092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005097  test    al, al
0x180005099  jmp     short loc_1800050A3
0x18000509b  call    cs:__imp_IsDebuggerPresent
0x1800050a1  test    eax, eax
0x1800050a3  jz      short loc_1800050AC
0x1800050a5  test    byte ptr [rsp+1510h+var_14E0+4], 2
0x1800050aa  jz      short loc_1800050D2
0x1800050ac  mov     rax, cs:g_pfnResultLoggingCallback
0x1800050b3  test    rax, rax
0x1800050b6  jz      short loc_18000512B
0x1800050b8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800050bf  jnz     short loc_18000512B
0x1800050c1  xor     r8d, r8d
0x1800050c4  xor     edx, edx
0x1800050c6  lea     rcx, [rsp+1510h+var_14E0]
0x1800050cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050d0  jmp     short loc_18000512B
0x1800050d2  mov     ebx, 800h
0x1800050d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800050de  test    rax, rax
0x1800050e1  jz      short loc_180005100
0x1800050e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800050ea  jnz     short loc_180005100
0x1800050ec  mov     r8d, ebx
0x1800050ef  lea     rdx, [rbp+1410h+OutputString]
0x1800050f6  lea     rcx, [rsp+1510h+var_14E0]
0x1800050fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005100  cmp     [rbp+1410h+OutputString], r12w
0x180005108  jnz     short loc_18000511E
0x18000510a  lea     r8, [rsp+1510h+var_14E0]; unsigned __int64
0x18000510f  mov     rdx, rbx; wchar_t *
0x180005112  lea     rcx, [rbp+1410h+OutputString]; this
0x180005119  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000511e  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x180005125  call    cs:__imp_OutputDebugStringW
0x18000512b  test    byte ptr [rsp+1510h+var_14E0+4], 4
0x180005130  jnz     short loc_18000513B
0x180005132  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180005139  jz      short loc_18000514D
0x18000513b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005142  test    rax, rax
0x180005145  jz      short loc_18000514D
0x180005147  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000514c  nop
0x18000514d  test    byte ptr [rsp+1510h+var_14E0+4], 1
0x180005152  jnz     short loc_180005175
0x180005154  mov     rcx, [rbp+1410h+var_40]
0x18000515b  xor     rcx, rsp; StackCookie
0x18000515e  call    __security_check_cookie
0x180005163  add     rsp, 14E0h
0x18000516a  pop     r15
0x18000516c  pop     r14
0x18000516e  pop     r12
0x180005170  pop     rdi
0x180005171  pop     rsi
0x180005172  pop     rbx
0x180005173  pop     rbp
0x180005174  retn
0x180005175  lea     rcx, [rsp+1510h+var_14E0]; this
0x18000517a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005180  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
