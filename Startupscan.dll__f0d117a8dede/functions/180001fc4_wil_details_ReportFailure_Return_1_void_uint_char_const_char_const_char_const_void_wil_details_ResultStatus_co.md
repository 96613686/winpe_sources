# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180001fc4`
- end: `0x180002258`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x180001c88`

## callees

- `0x180001fc4`
- `0x1800024c4`
- `0x180002c24`
- `0x1800038f0`
- `0x1800039cc`
- `0x1800040f6`
- `0x180004130`
- `0x1800041c0`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000206e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000206e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800021f3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800021f3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002169`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002169`

## string_xrefs

- `0x180002082`: `shell\cpls\healthcenter\startupscan\dll\scantask.cpp`

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
  v28 = "shell\\cpls\\healthcenter\\startupscan\\dll\\scantask.cpp";
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
0x180001fc4  mov     [rsp-8+arg_10], rbx
0x180001fc9  push    rbp
0x180001fca  push    rsi
0x180001fcb  push    rdi
0x180001fcc  push    r14
0x180001fce  push    r15
0x180001fd0  lea     rbp, [rsp-13D0h]
0x180001fd8  mov     eax, 14D0h
0x180001fdd  call    _alloca_probe
0x180001fe2  sub     rsp, rax
0x180001fe5  mov     rax, cs:__security_cookie
0x180001fec  xor     rax, rsp
0x180001fef  mov     [rbp+13F0h+var_30], rax
0x180001ff6  mov     rdi, [rbp+13F0h+arg_28]
0x180001ffd  mov     esi, edx
0x180001fff  mov     r14, rcx
0x180002002  xor     edx, edx; Val
0x180002004  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002009  mov     r8d, 98h; Size
0x18000200f  call    memset_0
0x180002014  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000201b  xor     r15d, r15d
0x18000201e  mov     [rbp+13F0h+OutputString], r15w
0x180002026  mov     [rbp+13F0h+var_1430], r15b
0x18000202a  mov     ecx, [rdx]; this
0x18000202c  mov     eax, [rdx+4]
0x18000202f  mov     [rsp+14F0h+var_14C8], ecx
0x180002033  mov     [rsp+14F0h+var_14C4], eax
0x180002037  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000203c  cmp     dword ptr [rdx+8], 1
0x180002040  mov     ebx, eax
0x180002042  lea     eax, [r15+8]
0x180002046  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18000204e  mov     ecx, r15d
0x180002051  cmovz   ecx, eax
0x180002054  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002058  lea     ecx, [rax-7]
0x18000205b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002063  inc     ecx
0x180002065  mov     [rsp+14F0h+var_14B8], r15
0x18000206a  mov     [rsp+14F0h+var_14C0], ecx
0x18000206e  call    cs:__imp_GetCurrentThreadId
0x180002074  xorps   xmm0, xmm0
0x180002077  mov     [rsp+14F0h+var_1490], esi
0x18000207b  mov     [rsp+14F0h+var_14B0], eax
0x18000207f  xorps   xmm1, xmm1
0x180002082  lea     rax, aShellCplsHealt; "shell\\cpls\\healthcenter\\startupscan"...
0x180002089  mov     [rsp+14F0h+var_148C], ebx
0x18000208d  mov     [rsp+14F0h+var_1498], rax
0x180002092  xor     eax, eax
0x180002094  mov     [rbp+13F0h+var_1458], rax
0x180002098  mov     [rbp+13F0h+var_1470], rax
0x18000209c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800020a3  mov     [rsp+14F0h+var_14A8], r15
0x1800020a8  mov     [rsp+14F0h+var_14A0], r15
0x1800020ad  mov     [rbp+13F0h+var_1448], rdi
0x1800020b1  mov     [rbp+13F0h+var_1440], r14
0x1800020b5  mov     [rsp+14F0h+var_1488], r15
0x1800020ba  movups  [rbp+13F0h+var_1468], xmm0
0x1800020be  movups  [rsp+14F0h+var_1480], xmm1
0x1800020c3  test    rax, rax
0x1800020c6  jz      short loc_1800020D3
0x1800020c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020cd  mov     [rbp+13F0h+var_1450], rax
0x1800020d1  jmp     short loc_1800020D7
0x1800020d3  mov     [rbp+13F0h+var_1450], r15
0x1800020d7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800020de  test    rax, rax
0x1800020e1  jz      short loc_1800020ED
0x1800020e3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800020e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800020ed  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800020f4  test    rax, rax
0x1800020f7  jz      short loc_18000210D
0x1800020f9  mov     r8d, 400h
0x1800020ff  lea     rdx, [rbp+13F0h+var_1430]
0x180002103  lea     rcx, [rsp+14F0h+var_14D0]
0x180002108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000210d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002114  test    rax, rax
0x180002117  jz      short loc_180002123
0x180002119  lea     rcx, [rsp+14F0h+var_14D0]
0x18000211e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002123  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000212a  test    rax, rax
0x18000212d  jz      short loc_180002140
0x18000212f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002134  jnz     short loc_180002140
0x180002136  lea     rcx, [rsp+14F0h+var_14D0]
0x18000213b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002140  cmp     [rsp+14F0h+var_14C8], r15d
0x180002145  jge     loc_180002247
0x18000214b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180002152  jnz     short loc_180002173
0x180002154  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000215b  test    rax, rax
0x18000215e  jz      short loc_180002169
0x180002160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002165  test    al, al
0x180002167  jmp     short loc_180002171
0x180002169  call    cs:__imp_IsDebuggerPresent
0x18000216f  test    eax, eax
0x180002171  jz      short loc_18000217A
0x180002173  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002178  jz      short loc_1800021A0
0x18000217a  mov     rax, cs:g_pfnResultLoggingCallback
0x180002181  test    rax, rax
0x180002184  jz      short loc_1800021F9
0x180002186  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000218d  jnz     short loc_1800021F9
0x18000218f  xor     r8d, r8d
0x180002192  lea     rcx, [rsp+14F0h+var_14D0]
0x180002197  xor     edx, edx
0x180002199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000219e  jmp     short loc_1800021F9
0x1800021a0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800021a7  mov     ebx, 800h
0x1800021ac  test    rax, rax
0x1800021af  jz      short loc_1800021CE
0x1800021b1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800021b8  jnz     short loc_1800021CE
0x1800021ba  mov     r8d, ebx
0x1800021bd  lea     rdx, [rbp+13F0h+OutputString]
0x1800021c4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800021c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800021ce  cmp     [rbp+13F0h+OutputString], r15w
0x1800021d6  jnz     short loc_1800021EC
0x1800021d8  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800021dd  mov     rdx, rbx; unsigned __int16 *
0x1800021e0  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800021e7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800021ec  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800021f3  call    cs:__imp_OutputDebugStringW
0x1800021f9  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800021fe  jnz     short loc_180002209
0x180002200  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180002207  jz      short loc_18000221A
0x180002209  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002210  test    rax, rax
0x180002213  jz      short loc_18000221A
0x180002215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000221a  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000221f  jnz     short loc_18000224D
0x180002221  mov     rcx, [rbp+13F0h+var_30]
0x180002228  xor     rcx, rsp; StackCookie
0x18000222b  call    __security_check_cookie
0x180002230  mov     rbx, [rsp+14F0h+arg_10]
0x180002238  add     rsp, 14D0h
0x18000223f  pop     r15
0x180002241  pop     r14
0x180002243  pop     rdi
0x180002244  pop     rsi
0x180002245  pop     rbp
0x180002246  retn
0x180002247  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000224d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002252  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
