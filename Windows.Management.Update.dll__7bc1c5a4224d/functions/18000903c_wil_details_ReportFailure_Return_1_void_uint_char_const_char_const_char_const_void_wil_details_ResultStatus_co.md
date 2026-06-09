# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000903c`
- end: `0x1800092d2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008b1c`

## callees

- `0x1800028f0`
- `0x1800033e8`
- `0x18000903c`
- `0x18000b974`
- `0x18000d2d8`
- `0x18000f9b0`
- `0x18000fb7c`
- `0x180027600`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800090e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800090e7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000926c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000926c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800091e2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800091e2`

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
0x18000903c  mov     [rsp-8+arg_10], rbx
0x180009041  push    rbp
0x180009042  push    rsi
0x180009043  push    rdi
0x180009044  push    r14
0x180009046  push    r15
0x180009048  lea     rbp, [rsp-13D0h]
0x180009050  mov     eax, 14D0h
0x180009055  call    _alloca_probe
0x18000905a  sub     rsp, rax
0x18000905d  mov     rax, cs:__security_cookie
0x180009064  xor     rax, rsp
0x180009067  mov     [rbp+13F0h+var_30], rax
0x18000906e  mov     esi, edx
0x180009070  mov     r14, rcx
0x180009073  mov     rdi, [rbp+13F0h+arg_28]
0x18000907a  xor     edx, edx; Val
0x18000907c  mov     r8d, 98h; Size
0x180009082  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180009087  call    memset_0
0x18000908c  nop
0x18000908d  xor     r15d, r15d
0x180009090  mov     [rbp+13F0h+OutputString], r15w
0x180009098  mov     [rbp+13F0h+var_1430], r15b
0x18000909c  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800090a3  mov     ecx, [rdx]; this
0x1800090a5  mov     [rsp+14F0h+var_14C8], ecx
0x1800090a9  mov     eax, [rdx+4]
0x1800090ac  mov     [rsp+14F0h+var_14C4], eax
0x1800090b0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800090b5  mov     ebx, eax
0x1800090b7  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800090bf  mov     ecx, r15d
0x1800090c2  lea     eax, [r15+8]
0x1800090c6  cmp     dword ptr [rdx+8], 1
0x1800090ca  cmovz   ecx, eax
0x1800090cd  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800090d1  lea     ecx, [rax-7]
0x1800090d4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800090dc  inc     ecx
0x1800090de  mov     [rsp+14F0h+var_14C0], ecx
0x1800090e2  mov     [rsp+14F0h+var_14B8], r15
0x1800090e7  call    cs:__imp_GetCurrentThreadId
0x1800090ed  mov     [rsp+14F0h+var_14B0], eax
0x1800090f1  lea     rax, aWil; "wil"
0x1800090f8  mov     [rsp+14F0h+var_1498], rax
0x1800090fd  mov     [rsp+14F0h+var_1490], esi
0x180009101  mov     [rsp+14F0h+var_148C], ebx
0x180009105  mov     [rsp+14F0h+var_14A8], r15
0x18000910a  mov     [rsp+14F0h+var_14A0], r15
0x18000910f  mov     [rbp+13F0h+var_1448], rdi
0x180009113  mov     [rbp+13F0h+var_1440], r14
0x180009117  mov     [rsp+14F0h+var_1488], r15
0x18000911c  xorps   xmm0, xmm0
0x18000911f  xor     eax, eax
0x180009121  movups  [rbp+13F0h+var_1468], xmm0
0x180009125  mov     [rbp+13F0h+var_1458], rax
0x180009129  xorps   xmm1, xmm1
0x18000912c  movups  [rsp+14F0h+var_1480], xmm1
0x180009131  mov     [rbp+13F0h+var_1470], rax
0x180009135  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000913c  test    rax, rax
0x18000913f  jz      short loc_18000914C
0x180009141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009146  mov     [rbp+13F0h+var_1450], rax
0x18000914a  jmp     short loc_180009150
0x18000914c  mov     [rbp+13F0h+var_1450], r15
0x180009150  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009157  test    rax, rax
0x18000915a  jz      short loc_180009166
0x18000915c  lea     rcx, [rsp+14F0h+var_14D0]
0x180009161  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009166  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000916d  test    rax, rax
0x180009170  jz      short loc_180009186
0x180009172  mov     r8d, 400h
0x180009178  lea     rdx, [rbp+13F0h+var_1430]
0x18000917c  lea     rcx, [rsp+14F0h+var_14D0]
0x180009181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009186  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000918d  test    rax, rax
0x180009190  jz      short loc_18000919C
0x180009192  lea     rcx, [rsp+14F0h+var_14D0]
0x180009197  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000919c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800091a3  test    rax, rax
0x1800091a6  jz      short loc_1800091B9
0x1800091a8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800091ad  jnz     short loc_1800091B9
0x1800091af  lea     rcx, [rsp+14F0h+var_14D0]
0x1800091b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091b9  cmp     [rsp+14F0h+var_14C8], r15d
0x1800091be  jge     loc_1800092CC
0x1800091c4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800091cb  jnz     short loc_1800091EC
0x1800091cd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800091d4  test    rax, rax
0x1800091d7  jz      short loc_1800091E2
0x1800091d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091de  test    al, al
0x1800091e0  jmp     short loc_1800091EA
0x1800091e2  call    cs:__imp_IsDebuggerPresent
0x1800091e8  test    eax, eax
0x1800091ea  jz      short loc_1800091F3
0x1800091ec  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800091f1  jz      short loc_180009219
0x1800091f3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800091fa  test    rax, rax
0x1800091fd  jz      short loc_180009272
0x1800091ff  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009206  jnz     short loc_180009272
0x180009208  xor     r8d, r8d
0x18000920b  xor     edx, edx
0x18000920d  lea     rcx, [rsp+14F0h+var_14D0]
0x180009212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009217  jmp     short loc_180009272
0x180009219  mov     ebx, 800h
0x18000921e  mov     rax, cs:g_pfnResultLoggingCallback
0x180009225  test    rax, rax
0x180009228  jz      short loc_180009247
0x18000922a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009231  jnz     short loc_180009247
0x180009233  mov     r8d, ebx
0x180009236  lea     rdx, [rbp+13F0h+OutputString]
0x18000923d  lea     rcx, [rsp+14F0h+var_14D0]
0x180009242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009247  cmp     [rbp+13F0h+OutputString], r15w
0x18000924f  jnz     short loc_180009265
0x180009251  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180009256  mov     rdx, rbx; unsigned __int16 *
0x180009259  lea     rcx, [rbp+13F0h+OutputString]; this
0x180009260  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009265  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000926c  call    cs:__imp_OutputDebugStringW
0x180009272  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180009277  jnz     short loc_180009282
0x180009279  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180009280  jz      short loc_180009294
0x180009282  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009289  test    rax, rax
0x18000928c  jz      short loc_180009294
0x18000928e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009293  nop
0x180009294  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180009299  jnz     short loc_1800092C1
0x18000929b  mov     rcx, [rbp+13F0h+var_30]
0x1800092a2  xor     rcx, rsp; StackCookie
0x1800092a5  call    __security_check_cookie
0x1800092aa  mov     rbx, [rsp+14F0h+arg_10]
0x1800092b2  add     rsp, 14D0h
0x1800092b9  pop     r15
0x1800092bb  pop     r14
0x1800092bd  pop     rdi
0x1800092be  pop     rsi
0x1800092bf  pop     rbp
0x1800092c0  retn
0x1800092c1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800092c6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800092cc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
