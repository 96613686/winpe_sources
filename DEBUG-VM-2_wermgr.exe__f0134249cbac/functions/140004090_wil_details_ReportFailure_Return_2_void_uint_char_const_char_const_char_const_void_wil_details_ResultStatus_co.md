# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140004090`
- end: `0x140004390`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140003a98`

## callees

- `0x140002fbc`
- `0x140003200`
- `0x140003c10`
- `0x140004090`
- `0x140007298`
- `0x140007a8c`
- `0x140009334`
- `0x14000d6ec`
- `0x14000d7c8`
- `0x14001c930`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400041b1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400041b1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400042a4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400042a4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000432d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000432d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int v14; // edx
  int v15; // ebx
  int v16; // edx
  int v17; // ebx
  const struct wil::FailureInfo *v18; // rdx
  wil::details::in1diag4 *v19; // rcx
  const struct wil::FailureInfo *v20; // r9
  bool v21; // zf
  wil::details *v22; // [rsp+30h] [rbp-D0h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh]
  int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  signed __int32 v27; // [rsp+60h] [rbp-A0h]
  _WORD *v28; // [rsp+68h] [rbp-98h]
  DWORD CurrentThreadId; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+94h] [rbp-6Ch]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  __int128 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  __int64 ModuleName; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  char v43[1024]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR OutputString[2048]; // [rsp+4F0h] [rbp+3F0h] BYREF

  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v15 = *a7;
  v25 = v15;
  v26 = a7[1];
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v22) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v22);
    v25 = -2147024228;
    v26 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v16);
  }
  v17 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  v23 = 2;
  v24 = a10;
  if ( a7[2] == 1 )
    v24 = a10 | 8;
  v27 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v21 = *a8 == 0, v28 = a8, v21) )
    v28 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v17;
  v30 = a5;
  v31 = a4;
  v41 = a6;
  v42 = a1;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v23, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v23);
  if ( wil::details::g_pfnOriginateCallback && (v24 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v23);
  if ( v25 >= 0 )
    wil::details::in1diag4::_FailFastImmediate_Unexpected(v19);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v21 = !IsDebuggerPresent())
      : (v21 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v21)
    || (v24 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v23, v20);
    OutputDebugStringW(OutputString);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v18);
}

```

## disassembly

```asm
0x140004090  push    rbp
0x140004092  push    rbx
0x140004093  push    rsi
0x140004094  push    rdi
0x140004095  push    r12
0x140004097  push    r13
0x140004099  push    r14
0x14000409b  push    r15
0x14000409d  lea     rbp, [rsp-1408h]
0x1400040a5  mov     eax, 1508h
0x1400040aa  call    _alloca_probe
0x1400040af  sub     rsp, rax
0x1400040b2  mov     rax, cs:__security_cookie
0x1400040b9  xor     rax, rsp
0x1400040bc  mov     [rbp+1440h+var_50], rax
0x1400040c3  mov     r12, r9
0x1400040c6  mov     r15, r8
0x1400040c9  mov     r14d, edx
0x1400040cc  mov     rsi, rcx
0x1400040cf  mov     r13, [rbp+1440h+arg_20]
0x1400040d6  mov     rax, [rbp+1440h+arg_28]
0x1400040dd  mov     [rsp+1540h+var_1500], rax
0x1400040e2  xor     edx, edx; Val
0x1400040e4  mov     r8d, 98h; Size
0x1400040ea  lea     rcx, [rsp+1540h+var_14F0]; void *
0x1400040ef  call    memset_0
0x1400040f4  nop
0x1400040f5  xor     eax, eax
0x1400040f7  mov     [rbp+1440h+OutputString], ax
0x1400040fe  mov     [rbp+1440h+var_1450], al
0x140004101  mov     rdi, [rbp+1440h+arg_30]
0x140004108  mov     ebx, [rdi]
0x14000410a  mov     [rsp+1540h+var_14E8], ebx
0x14000410e  mov     eax, [rdi+4]
0x140004111  mov     [rsp+1540h+var_14E4], eax
0x140004115  test    ebx, ebx
0x140004117  js      short loc_140004159
0x140004119  mov     [rsp+1540h+var_1508], 0
0x140004121  mov     ebx, 8007029Ch
0x140004126  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x14000412a  mov     rax, [rsp+1540h+var_1500]
0x14000412f  mov     [rsp+1540h+var_1518], rax; __int64
0x140004134  mov     [rsp+1540h+var_1520], r13; __int64
0x140004139  mov     r9, r12; int
0x14000413c  mov     r8, r15; int
0x14000413f  mov     edx, r14d; int
0x140004142  mov     rcx, rsi; int
0x140004145  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000414a  mov     [rsp+1540h+var_14E8], ebx
0x14000414e  mov     ecx, ebx; this
0x140004150  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004155  mov     [rsp+1540h+var_14E4], eax
0x140004159  mov     ecx, ebx; this
0x14000415b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004160  mov     ebx, eax
0x140004162  mov     dword ptr [rsp+1540h+var_14F0], 2
0x14000416a  mov     ecx, [rbp+1440h+arg_48]
0x140004170  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x140004174  cmp     dword ptr [rdi+8], 1
0x140004178  jnz     short loc_140004181
0x14000417a  or      ecx, 8
0x14000417d  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x140004181  mov     ecx, 1
0x140004186  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000418e  inc     ecx
0x140004190  mov     [rsp+1540h+var_14E0], ecx
0x140004194  mov     rax, [rbp+1440h+arg_38]
0x14000419b  xor     edi, edi
0x14000419d  test    rax, rax
0x1400041a0  jz      short loc_1400041AC
0x1400041a2  cmp     [rax], di
0x1400041a5  mov     [rsp+1540h+var_14D8], rax
0x1400041aa  jnz     short loc_1400041B1
0x1400041ac  mov     [rsp+1540h+var_14D8], rdi
0x1400041b1  call    cs:__imp_GetCurrentThreadId
0x1400041b7  mov     [rsp+1540h+var_14D0], eax
0x1400041bb  mov     [rbp+1440h+var_14B8], r15
0x1400041bf  mov     [rbp+1440h+var_14B0], r14d
0x1400041c3  mov     [rbp+1440h+var_14AC], ebx
0x1400041c6  mov     [rsp+1540h+var_14C8], r13
0x1400041cb  mov     [rbp+1440h+var_14C0], r12
0x1400041cf  mov     rax, [rsp+1540h+var_1500]
0x1400041d4  mov     [rbp+1440h+var_1468], rax
0x1400041d8  mov     [rbp+1440h+var_1460], rsi
0x1400041dc  mov     [rbp+1440h+var_14A8], rdi
0x1400041e0  xorps   xmm0, xmm0
0x1400041e3  xor     eax, eax
0x1400041e5  movups  [rbp+1440h+var_1488], xmm0
0x1400041e9  mov     [rbp+1440h+var_1478], rax
0x1400041ed  xorps   xmm1, xmm1
0x1400041f0  movups  [rbp+1440h+var_14A0], xmm1
0x1400041f4  mov     [rbp+1440h+var_1490], rax
0x1400041f8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400041ff  test    rax, rax
0x140004202  jz      short loc_14000420F
0x140004204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004209  mov     [rbp+1440h+var_1470], rax
0x14000420d  jmp     short loc_140004213
0x14000420f  mov     [rbp+1440h+var_1470], rdi
0x140004213  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000421a  test    rax, rax
0x14000421d  jz      short loc_140004229
0x14000421f  lea     rcx, [rsp+1540h+var_14F0]
0x140004224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004229  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004230  test    rax, rax
0x140004233  jz      short loc_140004249
0x140004235  mov     r8d, 400h
0x14000423b  lea     rdx, [rbp+1440h+var_1450]
0x14000423f  lea     rcx, [rsp+1540h+var_14F0]
0x140004244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004249  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004250  test    rax, rax
0x140004253  jz      short loc_14000425F
0x140004255  lea     rcx, [rsp+1540h+var_14F0]
0x14000425a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000425f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004266  test    rax, rax
0x140004269  jz      short loc_14000427C
0x14000426b  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x140004270  jnz     short loc_14000427C
0x140004272  lea     rcx, [rsp+1540h+var_14F0]
0x140004277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000427c  cmp     [rsp+1540h+var_14E8], edi
0x140004280  jge     loc_14000438A
0x140004286  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000428d  jnz     short loc_1400042AE
0x14000428f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004296  test    rax, rax
0x140004299  jz      short loc_1400042A4
0x14000429b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042a0  test    al, al
0x1400042a2  jmp     short loc_1400042AC
0x1400042a4  call    cs:__imp_IsDebuggerPresent
0x1400042aa  test    eax, eax
0x1400042ac  jz      short loc_1400042B5
0x1400042ae  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x1400042b3  jz      short loc_1400042DB
0x1400042b5  mov     rax, cs:g_pfnResultLoggingCallback
0x1400042bc  test    rax, rax
0x1400042bf  jz      short loc_140004333
0x1400042c1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400042c8  jnz     short loc_140004333
0x1400042ca  xor     r8d, r8d
0x1400042cd  xor     edx, edx
0x1400042cf  lea     rcx, [rsp+1540h+var_14F0]
0x1400042d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042d9  jmp     short loc_140004333
0x1400042db  mov     ebx, 800h
0x1400042e0  mov     rax, cs:g_pfnResultLoggingCallback
0x1400042e7  test    rax, rax
0x1400042ea  jz      short loc_140004309
0x1400042ec  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400042f3  jnz     short loc_140004309
0x1400042f5  mov     r8d, ebx
0x1400042f8  lea     rdx, [rbp+1440h+OutputString]
0x1400042ff  lea     rcx, [rsp+1540h+var_14F0]
0x140004304  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004309  cmp     [rbp+1440h+OutputString], di
0x140004310  jnz     short loc_140004326
0x140004312  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x140004317  mov     rdx, rbx; wchar_t *
0x14000431a  lea     rcx, [rbp+1440h+OutputString]; this
0x140004321  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140004326  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x14000432d  call    cs:__imp_OutputDebugStringW
0x140004333  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x140004338  jnz     short loc_140004343
0x14000433a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140004341  jz      short loc_140004355
0x140004343  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000434a  test    rax, rax
0x14000434d  jz      short loc_140004355
0x14000434f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004354  nop
0x140004355  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x14000435a  jnz     short loc_14000437F
0x14000435c  mov     rcx, [rbp+1440h+var_50]
0x140004363  xor     rcx, rsp; StackCookie
0x140004366  call    __security_check_cookie
0x14000436b  add     rsp, 1508h
0x140004372  pop     r15
0x140004374  pop     r14
0x140004376  pop     r13
0x140004378  pop     r12
0x14000437a  pop     rdi
0x14000437b  pop     rsi
0x14000437c  pop     rbx
0x14000437d  pop     rbp
0x14000437e  retn
0x14000437f  lea     rcx, [rsp+1540h+var_14F0]; this
0x140004384  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000438a  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
```
