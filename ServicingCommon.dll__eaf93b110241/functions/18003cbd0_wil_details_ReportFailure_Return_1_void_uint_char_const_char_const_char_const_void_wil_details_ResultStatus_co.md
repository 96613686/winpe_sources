# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18003cbd0`
- end: `0x18003ce6e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001e5bc`

## callees

- `0x1800293a0`
- `0x180029fd0`
- `0x18003cbd0`
- `0x18003d120`
- `0x18003d7b4`
- `0x18003d90c`
- `0x18003d9e8`
- `0x180099cb0`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18003ce07`
- `KERNEL32!OutputDebugStringW` at `0x18003ce07`
- `KERNEL32!GetCurrentThreadId` at `0x18003cc7d`
- `KERNEL32!GetCurrentThreadId` at `0x18003cc7d`
- `KERNEL32!IsDebuggerPresent` at `0x18003cd77`
- `KERNEL32!IsDebuggerPresent` at `0x18003cd77`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        _DWORD *a7)
{
  int v10; // eax
  unsigned int v11; // eax
  __int64 v12; // rdx
  unsigned int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  unsigned __int64 v20[20]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v21[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset(v20, 0, 0x98u);
  OutputString[0] = 0;
  v21[0] = 0;
  v10 = a7[1];
  LODWORD(v20[1]) = *a7;
  HIDWORD(v20[1]) = v10;
  v11 = wil::details::RecordReturn((wil::details *)LODWORD(v20[1]), (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  LODWORD(v20[0]) = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  HIDWORD(v20[0]) = v14;
  v20[3] = 0;
  LODWORD(v20[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v20[7] = a3;
  LODWORD(v20[4]) = CurrentThreadId;
  v20[8] = __PAIR64__(v13, a2);
  v20[5] = 0;
  v20[6] = 0;
  v20[17] = a6;
  v20[18] = a1;
  memset(&v20[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v20[16] = wil::details::g_pfnGetModuleName(v17);
  else
    v20[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v20, v21, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v20);
  if ( wil::details::g_pfnOriginateCallback && (v20[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v20);
  if ( SLODWORD(v20[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v20[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v20[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v20, v16);
}

```

## disassembly

```asm
0x18003cbd0  push    rbp
0x18003cbd2  push    rbx
0x18003cbd3  push    rsi
0x18003cbd4  push    rdi
0x18003cbd5  push    r12
0x18003cbd7  push    r14
0x18003cbd9  push    r15
0x18003cbdb  lea     rbp, [rsp-13D0h]
0x18003cbe3  mov     eax, 14D0h
0x18003cbe8  call    _alloca_probe
0x18003cbed  sub     rsp, rax
0x18003cbf0  mov     rax, cs:__security_cookie
0x18003cbf7  xor     rax, rsp
0x18003cbfa  mov     [rbp+1400h+var_40], rax
0x18003cc01  mov     rdi, [rbp+1400h+arg_28]
0x18003cc08  mov     r14, r8
0x18003cc0b  mov     esi, edx
0x18003cc0d  mov     r15, rcx
0x18003cc10  xor     edx, edx; Val
0x18003cc12  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18003cc17  mov     r8d, 98h; Size
0x18003cc1d  call    memset
0x18003cc22  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18003cc29  xor     r12d, r12d
0x18003cc2c  mov     [rbp+1400h+OutputString], r12w
0x18003cc34  mov     [rbp+1400h+var_1440], r12b
0x18003cc38  mov     ecx, [rdx]; this
0x18003cc3a  mov     eax, [rdx+4]
0x18003cc3d  mov     [rsp+1500h+var_14D8], ecx
0x18003cc41  mov     [rsp+1500h+var_14D4], eax
0x18003cc45  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003cc4a  cmp     dword ptr [rdx+8], 1
0x18003cc4e  mov     ebx, eax
0x18003cc50  lea     eax, [r12+8]
0x18003cc55  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18003cc5d  mov     ecx, r12d
0x18003cc60  cmovz   ecx, eax
0x18003cc63  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18003cc67  lea     ecx, [rax-7]
0x18003cc6a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003cc72  inc     ecx
0x18003cc74  mov     [rsp+1500h+var_14C8], r12
0x18003cc79  mov     [rsp+1500h+var_14D0], ecx
0x18003cc7d  call    cs:__imp_GetCurrentThreadId
0x18003cc84  nop     dword ptr [rax+rax+00h]
0x18003cc89  xorps   xmm0, xmm0
0x18003cc8c  mov     [rsp+1500h+var_14A8], r14
0x18003cc91  mov     [rsp+1500h+var_14C0], eax
0x18003cc95  xorps   xmm1, xmm1
0x18003cc98  xor     eax, eax
0x18003cc9a  mov     [rsp+1500h+var_14A0], esi
0x18003cc9e  mov     [rbp+1400h+var_1468], rax
0x18003cca2  mov     [rbp+1400h+var_1480], rax
0x18003cca6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003ccad  mov     [rsp+1500h+var_149C], ebx
0x18003ccb1  mov     [rsp+1500h+var_14B8], r12
0x18003ccb6  mov     [rsp+1500h+var_14B0], r12
0x18003ccbb  mov     [rbp+1400h+var_1458], rdi
0x18003ccbf  mov     [rbp+1400h+var_1450], r15
0x18003ccc3  mov     [rsp+1500h+var_1498], r12
0x18003ccc8  movups  [rbp+1400h+var_1478], xmm0
0x18003cccc  movups  [rsp+1500h+var_1490], xmm1
0x18003ccd1  test    rax, rax
0x18003ccd4  jz      short loc_18003CCE1
0x18003ccd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccdb  mov     [rbp+1400h+var_1460], rax
0x18003ccdf  jmp     short loc_18003CCE5
0x18003cce1  mov     [rbp+1400h+var_1460], r12
0x18003cce5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003ccec  test    rax, rax
0x18003ccef  jz      short loc_18003CCFB
0x18003ccf1  lea     rcx, [rsp+1500h+var_14E0]
0x18003ccf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccfb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003cd02  test    rax, rax
0x18003cd05  jz      short loc_18003CD1B
0x18003cd07  mov     r8d, 400h
0x18003cd0d  lea     rdx, [rbp+1400h+var_1440]
0x18003cd11  lea     rcx, [rsp+1500h+var_14E0]
0x18003cd16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd1b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003cd22  test    rax, rax
0x18003cd25  jz      short loc_18003CD31
0x18003cd27  lea     rcx, [rsp+1500h+var_14E0]
0x18003cd2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd31  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003cd38  test    rax, rax
0x18003cd3b  jz      short loc_18003CD4E
0x18003cd3d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18003cd42  jnz     short loc_18003CD4E
0x18003cd44  lea     rcx, [rsp+1500h+var_14E0]
0x18003cd49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd4e  cmp     [rsp+1500h+var_14D8], r12d
0x18003cd53  jge     loc_18003CE5D
0x18003cd59  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18003cd60  jnz     short loc_18003CD87
0x18003cd62  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003cd69  test    rax, rax
0x18003cd6c  jz      short loc_18003CD77
0x18003cd6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd73  test    al, al
0x18003cd75  jmp     short loc_18003CD85
0x18003cd77  call    cs:__imp_IsDebuggerPresent
0x18003cd7e  nop     dword ptr [rax+rax+00h]
0x18003cd83  test    eax, eax
0x18003cd85  jz      short loc_18003CD8E
0x18003cd87  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18003cd8c  jz      short loc_18003CDB4
0x18003cd8e  mov     rax, cs:g_pfnResultLoggingCallback
0x18003cd95  test    rax, rax
0x18003cd98  jz      short loc_18003CE13
0x18003cd9a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18003cda1  jnz     short loc_18003CE13
0x18003cda3  xor     r8d, r8d
0x18003cda6  lea     rcx, [rsp+1500h+var_14E0]
0x18003cdab  xor     edx, edx
0x18003cdad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cdb2  jmp     short loc_18003CE13
0x18003cdb4  mov     rax, cs:g_pfnResultLoggingCallback
0x18003cdbb  mov     ebx, 800h
0x18003cdc0  test    rax, rax
0x18003cdc3  jz      short loc_18003CDE2
0x18003cdc5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18003cdcc  jnz     short loc_18003CDE2
0x18003cdce  mov     r8d, ebx
0x18003cdd1  lea     rdx, [rbp+1400h+OutputString]
0x18003cdd8  lea     rcx, [rsp+1500h+var_14E0]
0x18003cddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cde2  cmp     [rbp+1400h+OutputString], r12w
0x18003cdea  jnz     short loc_18003CE00
0x18003cdec  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18003cdf1  mov     rdx, rbx; wchar_t *
0x18003cdf4  lea     rcx, [rbp+1400h+OutputString]; this
0x18003cdfb  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18003ce00  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18003ce07  call    cs:__imp_OutputDebugStringW
0x18003ce0e  nop     dword ptr [rax+rax+00h]
0x18003ce13  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18003ce18  jnz     short loc_18003CE23
0x18003ce1a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18003ce21  jz      short loc_18003CE34
0x18003ce23  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003ce2a  test    rax, rax
0x18003ce2d  jz      short loc_18003CE34
0x18003ce2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ce34  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18003ce39  jnz     short loc_18003CE63
0x18003ce3b  mov     rcx, [rbp+1400h+var_40]
0x18003ce42  xor     rcx, rsp; StackCookie
0x18003ce45  call    __security_check_cookie
0x18003ce4a  add     rsp, 14D0h
0x18003ce51  pop     r15
0x18003ce53  pop     r14
0x18003ce55  pop     r12
0x18003ce57  pop     rdi
0x18003ce58  pop     rsi
0x18003ce59  pop     rbx
0x18003ce5a  pop     rbp
0x18003ce5b  retn
0x18003ce5d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18003ce63  lea     rcx, [rsp+1500h+var_14E0]; this
0x18003ce68  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
