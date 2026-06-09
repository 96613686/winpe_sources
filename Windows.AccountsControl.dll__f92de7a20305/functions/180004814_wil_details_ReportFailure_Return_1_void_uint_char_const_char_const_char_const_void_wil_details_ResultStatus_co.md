# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004814`
- end: `0x180004a9f`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800044b8`

## callees

- `0x180004814`
- `0x1800058d4`
- `0x180006ab0`
- `0x180007758`
- `0x180007914`
- `0x1800696f2`
- `0x180069730`
- `0x1800697f0`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048c1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004a3f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004a3f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800049b5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800049b5`

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
0x180004814  push    rbp
0x180004816  push    rbx
0x180004817  push    rsi
0x180004818  push    rdi
0x180004819  push    r12
0x18000481b  push    r14
0x18000481d  push    r15
0x18000481f  lea     rbp, [rsp-13D0h]
0x180004827  mov     eax, 14D0h
0x18000482c  call    _alloca_probe
0x180004831  sub     rsp, rax
0x180004834  mov     rax, cs:__security_cookie
0x18000483b  xor     rax, rsp
0x18000483e  mov     [rbp+1400h+var_40], rax
0x180004845  mov     rdi, [rbp+1400h+arg_28]
0x18000484c  mov     r14, r8
0x18000484f  mov     esi, edx
0x180004851  mov     r15, rcx
0x180004854  xor     edx, edx; Val
0x180004856  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000485b  mov     r8d, 98h; Size
0x180004861  call    memset_0
0x180004866  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000486d  xor     r12d, r12d
0x180004870  mov     [rbp+1400h+OutputString], r12w
0x180004878  mov     [rbp+1400h+var_1440], r12b
0x18000487c  mov     ecx, [rdx]; this
0x18000487e  mov     eax, [rdx+4]
0x180004881  mov     [rsp+1500h+var_14D8], ecx
0x180004885  mov     [rsp+1500h+var_14D4], eax
0x180004889  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000488e  cmp     dword ptr [rdx+8], 1
0x180004892  mov     ebx, eax
0x180004894  lea     eax, [r12+8]
0x180004899  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800048a1  mov     ecx, r12d
0x1800048a4  cmovz   ecx, eax
0x1800048a7  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800048ab  lea     ecx, [rax-7]
0x1800048ae  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800048b6  inc     ecx
0x1800048b8  mov     [rsp+1500h+var_14C8], r12
0x1800048bd  mov     [rsp+1500h+var_14D0], ecx
0x1800048c1  call    cs:__imp_GetCurrentThreadId
0x1800048c7  xorps   xmm0, xmm0
0x1800048ca  mov     [rsp+1500h+var_14A8], r14
0x1800048cf  mov     [rsp+1500h+var_14C0], eax
0x1800048d3  xorps   xmm1, xmm1
0x1800048d6  xor     eax, eax
0x1800048d8  mov     [rsp+1500h+var_14A0], esi
0x1800048dc  mov     [rbp+1400h+var_1468], rax
0x1800048e0  mov     [rbp+1400h+var_1480], rax
0x1800048e4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800048eb  mov     [rsp+1500h+var_149C], ebx
0x1800048ef  mov     [rsp+1500h+var_14B8], r12
0x1800048f4  mov     [rsp+1500h+var_14B0], r12
0x1800048f9  mov     [rbp+1400h+var_1458], rdi
0x1800048fd  mov     [rbp+1400h+var_1450], r15
0x180004901  mov     [rsp+1500h+var_1498], r12
0x180004906  movups  [rbp+1400h+var_1478], xmm0
0x18000490a  movups  [rsp+1500h+var_1490], xmm1
0x18000490f  test    rax, rax
0x180004912  jz      short loc_18000491F
0x180004914  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004919  mov     [rbp+1400h+var_1460], rax
0x18000491d  jmp     short loc_180004923
0x18000491f  mov     [rbp+1400h+var_1460], r12
0x180004923  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000492a  test    rax, rax
0x18000492d  jz      short loc_180004939
0x18000492f  lea     rcx, [rsp+1500h+var_14E0]
0x180004934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004939  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004940  test    rax, rax
0x180004943  jz      short loc_180004959
0x180004945  mov     r8d, 400h
0x18000494b  lea     rdx, [rbp+1400h+var_1440]
0x18000494f  lea     rcx, [rsp+1500h+var_14E0]
0x180004954  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004959  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004960  test    rax, rax
0x180004963  jz      short loc_18000496F
0x180004965  lea     rcx, [rsp+1500h+var_14E0]
0x18000496a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000496f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004976  test    rax, rax
0x180004979  jz      short loc_18000498C
0x18000497b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004980  jnz     short loc_18000498C
0x180004982  lea     rcx, [rsp+1500h+var_14E0]
0x180004987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000498c  cmp     [rsp+1500h+var_14D8], r12d
0x180004991  jge     loc_180004A8E
0x180004997  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000499e  jnz     short loc_1800049BF
0x1800049a0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800049a7  test    rax, rax
0x1800049aa  jz      short loc_1800049B5
0x1800049ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049b1  test    al, al
0x1800049b3  jmp     short loc_1800049BD
0x1800049b5  call    cs:__imp_IsDebuggerPresent
0x1800049bb  test    eax, eax
0x1800049bd  jz      short loc_1800049C6
0x1800049bf  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800049c4  jz      short loc_1800049EC
0x1800049c6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800049cd  test    rax, rax
0x1800049d0  jz      short loc_180004A45
0x1800049d2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800049d9  jnz     short loc_180004A45
0x1800049db  xor     r8d, r8d
0x1800049de  lea     rcx, [rsp+1500h+var_14E0]
0x1800049e3  xor     edx, edx
0x1800049e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ea  jmp     short loc_180004A45
0x1800049ec  mov     rax, cs:g_pfnResultLoggingCallback
0x1800049f3  mov     ebx, 800h
0x1800049f8  test    rax, rax
0x1800049fb  jz      short loc_180004A1A
0x1800049fd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004a04  jnz     short loc_180004A1A
0x180004a06  mov     r8d, ebx
0x180004a09  lea     rdx, [rbp+1400h+OutputString]
0x180004a10  lea     rcx, [rsp+1500h+var_14E0]
0x180004a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a1a  cmp     [rbp+1400h+OutputString], r12w
0x180004a22  jnz     short loc_180004A38
0x180004a24  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004a29  mov     rdx, rbx; unsigned __int16 *
0x180004a2c  lea     rcx, [rbp+1400h+OutputString]; this
0x180004a33  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004a38  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004a3f  call    cs:__imp_OutputDebugStringW
0x180004a45  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004a4a  jnz     short loc_180004A55
0x180004a4c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004a53  jz      short loc_180004A66
0x180004a55  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004a5c  test    rax, rax
0x180004a5f  jz      short loc_180004A66
0x180004a61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a66  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004a6b  jnz     short loc_180004A94
0x180004a6d  mov     rcx, [rbp+1400h+var_40]
0x180004a74  xor     rcx, rsp; StackCookie
0x180004a77  call    __security_check_cookie
0x180004a7c  add     rsp, 14D0h
0x180004a83  pop     r15
0x180004a85  pop     r14
0x180004a87  pop     r12
0x180004a89  pop     rdi
0x180004a8a  pop     rsi
0x180004a8b  pop     rbx
0x180004a8c  pop     rbp
0x180004a8d  retn
0x180004a8e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180004a94  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004a99  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
