# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004e98`
- end: `0x18000512c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004978`

## callees

- `0x180004e98`
- `0x180006b44`
- `0x180007ff4`
- `0x180009ae0`
- `0x180009c9c`
- `0x18000a19e`
- `0x18000a1d0`
- `0x18000a260`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f42`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000503d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000503d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800050c7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800050c7`

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
0x180004e98  mov     [rsp-8+arg_10], rbx
0x180004e9d  push    rbp
0x180004e9e  push    rsi
0x180004e9f  push    rdi
0x180004ea0  push    r14
0x180004ea2  push    r15
0x180004ea4  lea     rbp, [rsp-13D0h]
0x180004eac  mov     eax, 14D0h
0x180004eb1  call    _alloca_probe
0x180004eb6  sub     rsp, rax
0x180004eb9  mov     rax, cs:__security_cookie
0x180004ec0  xor     rax, rsp
0x180004ec3  mov     [rbp+13F0h+var_30], rax
0x180004eca  mov     rdi, [rbp+13F0h+arg_28]
0x180004ed1  mov     esi, edx
0x180004ed3  mov     r14, rcx
0x180004ed6  xor     edx, edx; Val
0x180004ed8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004edd  mov     r8d, 98h; Size
0x180004ee3  call    memset_0
0x180004ee8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180004eef  xor     r15d, r15d
0x180004ef2  mov     [rbp+13F0h+OutputString], r15w
0x180004efa  mov     [rbp+13F0h+var_1430], r15b
0x180004efe  mov     ecx, [rdx]; this
0x180004f00  mov     eax, [rdx+4]
0x180004f03  mov     [rsp+14F0h+var_14C8], ecx
0x180004f07  mov     [rsp+14F0h+var_14C4], eax
0x180004f0b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004f10  cmp     dword ptr [rdx+8], 1
0x180004f14  mov     ebx, eax
0x180004f16  lea     eax, [r15+8]
0x180004f1a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180004f22  mov     ecx, r15d
0x180004f25  cmovz   ecx, eax
0x180004f28  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004f2c  lea     ecx, [rax-7]
0x180004f2f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004f37  inc     ecx
0x180004f39  mov     [rsp+14F0h+var_14B8], r15
0x180004f3e  mov     [rsp+14F0h+var_14C0], ecx
0x180004f42  call    cs:__imp_GetCurrentThreadId
0x180004f48  xorps   xmm0, xmm0
0x180004f4b  mov     [rsp+14F0h+var_1490], esi
0x180004f4f  mov     [rsp+14F0h+var_14B0], eax
0x180004f53  xorps   xmm1, xmm1
0x180004f56  lea     rax, aWil; "wil"
0x180004f5d  mov     [rsp+14F0h+var_148C], ebx
0x180004f61  mov     [rsp+14F0h+var_1498], rax
0x180004f66  xor     eax, eax
0x180004f68  mov     [rbp+13F0h+var_1458], rax
0x180004f6c  mov     [rbp+13F0h+var_1470], rax
0x180004f70  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004f77  mov     [rsp+14F0h+var_14A8], r15
0x180004f7c  mov     [rsp+14F0h+var_14A0], r15
0x180004f81  mov     [rbp+13F0h+var_1448], rdi
0x180004f85  mov     [rbp+13F0h+var_1440], r14
0x180004f89  mov     [rsp+14F0h+var_1488], r15
0x180004f8e  movups  [rbp+13F0h+var_1468], xmm0
0x180004f92  movups  [rsp+14F0h+var_1480], xmm1
0x180004f97  test    rax, rax
0x180004f9a  jz      short loc_180004FA7
0x180004f9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fa1  mov     [rbp+13F0h+var_1450], rax
0x180004fa5  jmp     short loc_180004FAB
0x180004fa7  mov     [rbp+13F0h+var_1450], r15
0x180004fab  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004fb2  test    rax, rax
0x180004fb5  jz      short loc_180004FC1
0x180004fb7  lea     rcx, [rsp+14F0h+var_14D0]
0x180004fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fc1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004fc8  test    rax, rax
0x180004fcb  jz      short loc_180004FE1
0x180004fcd  mov     r8d, 400h
0x180004fd3  lea     rdx, [rbp+13F0h+var_1430]
0x180004fd7  lea     rcx, [rsp+14F0h+var_14D0]
0x180004fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fe1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004fe8  test    rax, rax
0x180004feb  jz      short loc_180004FF7
0x180004fed  lea     rcx, [rsp+14F0h+var_14D0]
0x180004ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ff7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004ffe  test    rax, rax
0x180005001  jz      short loc_180005014
0x180005003  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005008  jnz     short loc_180005014
0x18000500a  lea     rcx, [rsp+14F0h+var_14D0]
0x18000500f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005014  cmp     [rsp+14F0h+var_14C8], r15d
0x180005019  jge     loc_18000511B
0x18000501f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180005026  jnz     short loc_180005047
0x180005028  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000502f  test    rax, rax
0x180005032  jz      short loc_18000503D
0x180005034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005039  test    al, al
0x18000503b  jmp     short loc_180005045
0x18000503d  call    cs:__imp_IsDebuggerPresent
0x180005043  test    eax, eax
0x180005045  jz      short loc_18000504E
0x180005047  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000504c  jz      short loc_180005074
0x18000504e  mov     rax, cs:g_pfnResultLoggingCallback
0x180005055  test    rax, rax
0x180005058  jz      short loc_1800050CD
0x18000505a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005061  jnz     short loc_1800050CD
0x180005063  xor     r8d, r8d
0x180005066  lea     rcx, [rsp+14F0h+var_14D0]
0x18000506b  xor     edx, edx
0x18000506d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005072  jmp     short loc_1800050CD
0x180005074  mov     rax, cs:g_pfnResultLoggingCallback
0x18000507b  mov     ebx, 800h
0x180005080  test    rax, rax
0x180005083  jz      short loc_1800050A2
0x180005085  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000508c  jnz     short loc_1800050A2
0x18000508e  mov     r8d, ebx
0x180005091  lea     rdx, [rbp+13F0h+OutputString]
0x180005098  lea     rcx, [rsp+14F0h+var_14D0]
0x18000509d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050a2  cmp     [rbp+13F0h+OutputString], r15w
0x1800050aa  jnz     short loc_1800050C0
0x1800050ac  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800050b1  mov     rdx, rbx; unsigned __int16 *
0x1800050b4  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800050bb  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800050c0  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800050c7  call    cs:__imp_OutputDebugStringW
0x1800050cd  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800050d2  jnz     short loc_1800050DD
0x1800050d4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800050db  jz      short loc_1800050EE
0x1800050dd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800050e4  test    rax, rax
0x1800050e7  jz      short loc_1800050EE
0x1800050e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050ee  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800050f3  jnz     short loc_180005121
0x1800050f5  mov     rcx, [rbp+13F0h+var_30]
0x1800050fc  xor     rcx, rsp; StackCookie
0x1800050ff  call    __security_check_cookie
0x180005104  mov     rbx, [rsp+14F0h+arg_10]
0x18000510c  add     rsp, 14D0h
0x180005113  pop     r15
0x180005115  pop     r14
0x180005117  pop     rdi
0x180005118  pop     rsi
0x180005119  pop     rbp
0x18000511a  retn
0x18000511b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005121  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005126  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
