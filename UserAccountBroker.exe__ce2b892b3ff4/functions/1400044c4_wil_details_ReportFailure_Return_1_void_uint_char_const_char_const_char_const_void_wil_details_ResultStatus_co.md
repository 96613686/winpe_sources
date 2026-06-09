# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400044c4`
- end: `0x14000474f`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140003fa4`

## callees

- `0x14000195f`
- `0x1400044c4`
- `0x140005374`
- `0x140006150`
- `0x1400069e0`
- `0x140006abc`
- `0x140006b90`
- `0x140006c20`
- `0x140007010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004571`
- `KERNEL32!GetCurrentThreadId` at `0x140004571`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400046ef`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400046ef`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004665`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004665`

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
0x1400044c4  push    rbp
0x1400044c6  push    rbx
0x1400044c7  push    rsi
0x1400044c8  push    rdi
0x1400044c9  push    r12
0x1400044cb  push    r14
0x1400044cd  push    r15
0x1400044cf  lea     rbp, [rsp-13D0h]
0x1400044d7  mov     eax, 14D0h
0x1400044dc  call    _alloca_probe
0x1400044e1  sub     rsp, rax
0x1400044e4  mov     rax, cs:__security_cookie
0x1400044eb  xor     rax, rsp
0x1400044ee  mov     [rbp+1400h+var_40], rax
0x1400044f5  mov     rdi, [rbp+1400h+arg_28]
0x1400044fc  mov     r14, r8
0x1400044ff  mov     esi, edx
0x140004501  mov     r15, rcx
0x140004504  xor     edx, edx; Val
0x140004506  lea     rcx, [rsp+1500h+var_14E0]; void *
0x14000450b  mov     r8d, 98h; Size
0x140004511  call    memset_0
0x140004516  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x14000451d  xor     r12d, r12d
0x140004520  mov     [rbp+1400h+OutputString], r12w
0x140004528  mov     [rbp+1400h+var_1440], r12b
0x14000452c  mov     ecx, [rdx]; this
0x14000452e  mov     eax, [rdx+4]
0x140004531  mov     [rsp+1500h+var_14D8], ecx
0x140004535  mov     [rsp+1500h+var_14D4], eax
0x140004539  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000453e  cmp     dword ptr [rdx+8], 1
0x140004542  mov     ebx, eax
0x140004544  lea     eax, [r12+8]
0x140004549  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140004551  mov     ecx, r12d
0x140004554  cmovz   ecx, eax
0x140004557  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x14000455b  lea     ecx, [rax-7]
0x14000455e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004566  inc     ecx
0x140004568  mov     [rsp+1500h+var_14C8], r12
0x14000456d  mov     [rsp+1500h+var_14D0], ecx
0x140004571  call    cs:__imp_GetCurrentThreadId
0x140004577  xorps   xmm0, xmm0
0x14000457a  mov     [rsp+1500h+var_14A8], r14
0x14000457f  mov     [rsp+1500h+var_14C0], eax
0x140004583  xorps   xmm1, xmm1
0x140004586  xor     eax, eax
0x140004588  mov     [rsp+1500h+var_14A0], esi
0x14000458c  mov     [rbp+1400h+var_1468], rax
0x140004590  mov     [rbp+1400h+var_1480], rax
0x140004594  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000459b  mov     [rsp+1500h+var_149C], ebx
0x14000459f  mov     [rsp+1500h+var_14B8], r12
0x1400045a4  mov     [rsp+1500h+var_14B0], r12
0x1400045a9  mov     [rbp+1400h+var_1458], rdi
0x1400045ad  mov     [rbp+1400h+var_1450], r15
0x1400045b1  mov     [rsp+1500h+var_1498], r12
0x1400045b6  movups  [rbp+1400h+var_1478], xmm0
0x1400045ba  movups  [rsp+1500h+var_1490], xmm1
0x1400045bf  test    rax, rax
0x1400045c2  jz      short loc_1400045CF
0x1400045c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045c9  mov     [rbp+1400h+var_1460], rax
0x1400045cd  jmp     short loc_1400045D3
0x1400045cf  mov     [rbp+1400h+var_1460], r12
0x1400045d3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400045da  test    rax, rax
0x1400045dd  jz      short loc_1400045E9
0x1400045df  lea     rcx, [rsp+1500h+var_14E0]
0x1400045e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045e9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400045f0  test    rax, rax
0x1400045f3  jz      short loc_140004609
0x1400045f5  mov     r8d, 400h
0x1400045fb  lea     rdx, [rbp+1400h+var_1440]
0x1400045ff  lea     rcx, [rsp+1500h+var_14E0]
0x140004604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004609  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004610  test    rax, rax
0x140004613  jz      short loc_14000461F
0x140004615  lea     rcx, [rsp+1500h+var_14E0]
0x14000461a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000461f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004626  test    rax, rax
0x140004629  jz      short loc_14000463C
0x14000462b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140004630  jnz     short loc_14000463C
0x140004632  lea     rcx, [rsp+1500h+var_14E0]
0x140004637  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000463c  cmp     [rsp+1500h+var_14D8], r12d
0x140004641  jge     loc_14000473E
0x140004647  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000464e  jnz     short loc_14000466F
0x140004650  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004657  test    rax, rax
0x14000465a  jz      short loc_140004665
0x14000465c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004661  test    al, al
0x140004663  jmp     short loc_14000466D
0x140004665  call    cs:__imp_IsDebuggerPresent
0x14000466b  test    eax, eax
0x14000466d  jz      short loc_140004676
0x14000466f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140004674  jz      short loc_14000469C
0x140004676  mov     rax, cs:g_pfnResultLoggingCallback
0x14000467d  test    rax, rax
0x140004680  jz      short loc_1400046F5
0x140004682  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140004689  jnz     short loc_1400046F5
0x14000468b  xor     r8d, r8d
0x14000468e  lea     rcx, [rsp+1500h+var_14E0]
0x140004693  xor     edx, edx
0x140004695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000469a  jmp     short loc_1400046F5
0x14000469c  mov     rax, cs:g_pfnResultLoggingCallback
0x1400046a3  mov     ebx, 800h
0x1400046a8  test    rax, rax
0x1400046ab  jz      short loc_1400046CA
0x1400046ad  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400046b4  jnz     short loc_1400046CA
0x1400046b6  mov     r8d, ebx
0x1400046b9  lea     rdx, [rbp+1400h+OutputString]
0x1400046c0  lea     rcx, [rsp+1500h+var_14E0]
0x1400046c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046ca  cmp     [rbp+1400h+OutputString], r12w
0x1400046d2  jnz     short loc_1400046E8
0x1400046d4  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1400046d9  mov     rdx, rbx; unsigned __int16 *
0x1400046dc  lea     rcx, [rbp+1400h+OutputString]; this
0x1400046e3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400046e8  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1400046ef  call    cs:__imp_OutputDebugStringW
0x1400046f5  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1400046fa  jnz     short loc_140004705
0x1400046fc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140004703  jz      short loc_140004716
0x140004705  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000470c  test    rax, rax
0x14000470f  jz      short loc_140004716
0x140004711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004716  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x14000471b  jnz     short loc_140004744
0x14000471d  mov     rcx, [rbp+1400h+var_40]
0x140004724  xor     rcx, rsp; StackCookie
0x140004727  call    __security_check_cookie
0x14000472c  add     rsp, 14D0h
0x140004733  pop     r15
0x140004735  pop     r14
0x140004737  pop     r12
0x140004739  pop     rdi
0x14000473a  pop     rsi
0x14000473b  pop     rbx
0x14000473c  pop     rbp
0x14000473d  retn
0x14000473e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140004744  lea     rcx, [rsp+1500h+var_14E0]; this
0x140004749  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
