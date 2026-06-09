# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000451c`
- end: `0x1800047c2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003fbc`

## callees

- `0x180002590`
- `0x180002f98`
- `0x18000451c`
- `0x180007914`
- `0x1800093e8`
- `0x18000c380`
- `0x18000c5c4`
- `0x1800300f0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045e2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800045e2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800046d7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800046d7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004761`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004761`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
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
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
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
0x18000451c  push    rbp
0x18000451e  push    rbx
0x18000451f  push    rsi
0x180004520  push    rdi
0x180004521  push    r12
0x180004523  push    r14
0x180004525  push    r15
0x180004527  lea     rbp, [rsp-13D0h]
0x18000452f  mov     eax, 14D0h
0x180004534  call    _alloca_probe
0x180004539  sub     rsp, rax
0x18000453c  mov     rax, cs:__security_cookie
0x180004543  xor     rax, rsp
0x180004546  mov     [rbp+1400h+var_40], rax
0x18000454d  mov     rsi, r8
0x180004550  mov     edi, edx
0x180004552  mov     rbx, rcx
0x180004555  mov     r14, [rbp+1400h+arg_28]
0x18000455c  xor     edx, edx; Val
0x18000455e  mov     r8d, 98h; Size
0x180004564  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004569  call    memset_0
0x18000456e  nop
0x18000456f  xor     r12d, r12d
0x180004572  mov     [rbp+1400h+OutputString], r12w
0x18000457a  mov     [rbp+1400h+var_1440], r12b
0x18000457e  mov     rdx, [rbp+1400h+arg_30]; int
0x180004585  mov     ecx, [rdx]; this
0x180004587  mov     [rsp+1500h+var_14D8], ecx
0x18000458b  mov     eax, [rdx+4]
0x18000458e  mov     [rsp+1500h+var_14D4], eax
0x180004592  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004597  mov     r15d, eax
0x18000459a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800045a2  mov     ecx, r12d
0x1800045a5  lea     eax, [r12+8]
0x1800045aa  cmp     dword ptr [rdx+8], 1
0x1800045ae  cmovz   ecx, eax
0x1800045b1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800045b5  lea     ecx, [rax-7]
0x1800045b8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800045c0  inc     ecx
0x1800045c2  mov     [rsp+1500h+var_14D0], ecx
0x1800045c6  mov     rcx, [rbp+1400h+arg_38]
0x1800045cd  test    rcx, rcx
0x1800045d0  jz      short loc_1800045DD
0x1800045d2  cmp     [rcx], r12w
0x1800045d6  mov     [rsp+1500h+var_14C8], rcx
0x1800045db  jnz     short loc_1800045E2
0x1800045dd  mov     [rsp+1500h+var_14C8], r12
0x1800045e2  call    cs:__imp_GetCurrentThreadId
0x1800045e8  mov     [rsp+1500h+var_14C0], eax
0x1800045ec  mov     [rsp+1500h+var_14A8], rsi
0x1800045f1  mov     [rsp+1500h+var_14A0], edi
0x1800045f5  mov     [rsp+1500h+var_149C], r15d
0x1800045fa  mov     [rsp+1500h+var_14B8], r12
0x1800045ff  mov     [rsp+1500h+var_14B0], r12
0x180004604  mov     [rbp+1400h+var_1458], r14
0x180004608  mov     [rbp+1400h+var_1450], rbx
0x18000460c  mov     [rsp+1500h+var_1498], r12
0x180004611  xorps   xmm0, xmm0
0x180004614  xor     eax, eax
0x180004616  movups  [rbp+1400h+var_1478], xmm0
0x18000461a  mov     [rbp+1400h+var_1468], rax
0x18000461e  xorps   xmm1, xmm1
0x180004621  movups  [rsp+1500h+var_1490], xmm1
0x180004626  mov     [rbp+1400h+var_1480], rax
0x18000462a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004631  test    rax, rax
0x180004634  jz      short loc_180004641
0x180004636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000463b  mov     [rbp+1400h+var_1460], rax
0x18000463f  jmp     short loc_180004645
0x180004641  mov     [rbp+1400h+var_1460], r12
0x180004645  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000464c  test    rax, rax
0x18000464f  jz      short loc_18000465B
0x180004651  lea     rcx, [rsp+1500h+var_14E0]
0x180004656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000465b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004662  test    rax, rax
0x180004665  jz      short loc_18000467B
0x180004667  mov     r8d, 400h
0x18000466d  lea     rdx, [rbp+1400h+var_1440]
0x180004671  lea     rcx, [rsp+1500h+var_14E0]
0x180004676  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000467b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004682  test    rax, rax
0x180004685  jz      short loc_180004691
0x180004687  lea     rcx, [rsp+1500h+var_14E0]
0x18000468c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004691  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004698  test    rax, rax
0x18000469b  jz      short loc_1800046AE
0x18000469d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800046a2  jnz     short loc_1800046AE
0x1800046a4  lea     rcx, [rsp+1500h+var_14E0]
0x1800046a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ae  cmp     [rsp+1500h+var_14D8], r12d
0x1800046b3  jge     loc_1800047BC
0x1800046b9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800046c0  jnz     short loc_1800046E1
0x1800046c2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800046c9  test    rax, rax
0x1800046cc  jz      short loc_1800046D7
0x1800046ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046d3  test    al, al
0x1800046d5  jmp     short loc_1800046DF
0x1800046d7  call    cs:__imp_IsDebuggerPresent
0x1800046dd  test    eax, eax
0x1800046df  jz      short loc_1800046E8
0x1800046e1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800046e6  jz      short loc_18000470E
0x1800046e8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800046ef  test    rax, rax
0x1800046f2  jz      short loc_180004767
0x1800046f4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800046fb  jnz     short loc_180004767
0x1800046fd  xor     r8d, r8d
0x180004700  xor     edx, edx
0x180004702  lea     rcx, [rsp+1500h+var_14E0]
0x180004707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000470c  jmp     short loc_180004767
0x18000470e  mov     ebx, 800h
0x180004713  mov     rax, cs:g_pfnResultLoggingCallback
0x18000471a  test    rax, rax
0x18000471d  jz      short loc_18000473C
0x18000471f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004726  jnz     short loc_18000473C
0x180004728  mov     r8d, ebx
0x18000472b  lea     rdx, [rbp+1400h+OutputString]
0x180004732  lea     rcx, [rsp+1500h+var_14E0]
0x180004737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000473c  cmp     [rbp+1400h+OutputString], r12w
0x180004744  jnz     short loc_18000475A
0x180004746  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000474b  mov     rdx, rbx; unsigned __int16 *
0x18000474e  lea     rcx, [rbp+1400h+OutputString]; this
0x180004755  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000475a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004761  call    cs:__imp_OutputDebugStringW
0x180004767  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000476c  jnz     short loc_180004777
0x18000476e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004775  jz      short loc_180004789
0x180004777  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000477e  test    rax, rax
0x180004781  jz      short loc_180004789
0x180004783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004788  nop
0x180004789  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000478e  jnz     short loc_1800047B1
0x180004790  mov     rcx, [rbp+1400h+var_40]
0x180004797  xor     rcx, rsp; StackCookie
0x18000479a  call    __security_check_cookie
0x18000479f  add     rsp, 14D0h
0x1800047a6  pop     r15
0x1800047a8  pop     r14
0x1800047aa  pop     r12
0x1800047ac  pop     rdi
0x1800047ad  pop     rsi
0x1800047ae  pop     rbx
0x1800047af  pop     rbp
0x1800047b0  retn
0x1800047b1  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800047b6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800047bc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
