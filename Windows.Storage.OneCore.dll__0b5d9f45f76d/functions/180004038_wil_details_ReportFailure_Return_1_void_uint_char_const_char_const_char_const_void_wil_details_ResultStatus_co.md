# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004038`
- end: `0x1800042de`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003cbc`

## callees

- `0x180002be0`
- `0x1800037c8`
- `0x180004038`
- `0x180005a94`
- `0x18000776c`
- `0x180009278`
- `0x180009510`
- `0x180023130`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800040fe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000427d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000427d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800041f3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800041f3`

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
0x180004038  push    rbp
0x18000403a  push    rbx
0x18000403b  push    rsi
0x18000403c  push    rdi
0x18000403d  push    r12
0x18000403f  push    r14
0x180004041  push    r15
0x180004043  lea     rbp, [rsp-13D0h]
0x18000404b  mov     eax, 14D0h
0x180004050  call    _alloca_probe
0x180004055  sub     rsp, rax
0x180004058  mov     rax, cs:__security_cookie
0x18000405f  xor     rax, rsp
0x180004062  mov     [rbp+1400h+var_40], rax
0x180004069  mov     rsi, r8
0x18000406c  mov     edi, edx
0x18000406e  mov     rbx, rcx
0x180004071  mov     r14, [rbp+1400h+arg_28]
0x180004078  xor     edx, edx; Val
0x18000407a  mov     r8d, 98h; Size
0x180004080  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004085  call    memset_0
0x18000408a  nop
0x18000408b  xor     r12d, r12d
0x18000408e  mov     [rbp+1400h+OutputString], r12w
0x180004096  mov     [rbp+1400h+var_1440], r12b
0x18000409a  mov     rdx, [rbp+1400h+arg_30]; int
0x1800040a1  mov     ecx, [rdx]; this
0x1800040a3  mov     [rsp+1500h+var_14D8], ecx
0x1800040a7  mov     eax, [rdx+4]
0x1800040aa  mov     [rsp+1500h+var_14D4], eax
0x1800040ae  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800040b3  mov     r15d, eax
0x1800040b6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800040be  mov     ecx, r12d
0x1800040c1  lea     eax, [r12+8]
0x1800040c6  cmp     dword ptr [rdx+8], 1
0x1800040ca  cmovz   ecx, eax
0x1800040cd  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800040d1  lea     ecx, [rax-7]
0x1800040d4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800040dc  inc     ecx
0x1800040de  mov     [rsp+1500h+var_14D0], ecx
0x1800040e2  mov     rcx, [rbp+1400h+arg_38]
0x1800040e9  test    rcx, rcx
0x1800040ec  jz      short loc_1800040F9
0x1800040ee  cmp     [rcx], r12w
0x1800040f2  mov     [rsp+1500h+var_14C8], rcx
0x1800040f7  jnz     short loc_1800040FE
0x1800040f9  mov     [rsp+1500h+var_14C8], r12
0x1800040fe  call    cs:__imp_GetCurrentThreadId
0x180004104  mov     [rsp+1500h+var_14C0], eax
0x180004108  mov     [rsp+1500h+var_14A8], rsi
0x18000410d  mov     [rsp+1500h+var_14A0], edi
0x180004111  mov     [rsp+1500h+var_149C], r15d
0x180004116  mov     [rsp+1500h+var_14B8], r12
0x18000411b  mov     [rsp+1500h+var_14B0], r12
0x180004120  mov     [rbp+1400h+var_1458], r14
0x180004124  mov     [rbp+1400h+var_1450], rbx
0x180004128  mov     [rsp+1500h+var_1498], r12
0x18000412d  xorps   xmm0, xmm0
0x180004130  xor     eax, eax
0x180004132  movups  [rbp+1400h+var_1478], xmm0
0x180004136  mov     [rbp+1400h+var_1468], rax
0x18000413a  xorps   xmm1, xmm1
0x18000413d  movups  [rsp+1500h+var_1490], xmm1
0x180004142  mov     [rbp+1400h+var_1480], rax
0x180004146  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000414d  test    rax, rax
0x180004150  jz      short loc_18000415D
0x180004152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004157  mov     [rbp+1400h+var_1460], rax
0x18000415b  jmp     short loc_180004161
0x18000415d  mov     [rbp+1400h+var_1460], r12
0x180004161  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004168  test    rax, rax
0x18000416b  jz      short loc_180004177
0x18000416d  lea     rcx, [rsp+1500h+var_14E0]
0x180004172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004177  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000417e  test    rax, rax
0x180004181  jz      short loc_180004197
0x180004183  mov     r8d, 400h
0x180004189  lea     rdx, [rbp+1400h+var_1440]
0x18000418d  lea     rcx, [rsp+1500h+var_14E0]
0x180004192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004197  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000419e  test    rax, rax
0x1800041a1  jz      short loc_1800041AD
0x1800041a3  lea     rcx, [rsp+1500h+var_14E0]
0x1800041a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041ad  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800041b4  test    rax, rax
0x1800041b7  jz      short loc_1800041CA
0x1800041b9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800041be  jnz     short loc_1800041CA
0x1800041c0  lea     rcx, [rsp+1500h+var_14E0]
0x1800041c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041ca  cmp     [rsp+1500h+var_14D8], r12d
0x1800041cf  jge     loc_1800042D8
0x1800041d5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800041dc  jnz     short loc_1800041FD
0x1800041de  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800041e5  test    rax, rax
0x1800041e8  jz      short loc_1800041F3
0x1800041ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041ef  test    al, al
0x1800041f1  jmp     short loc_1800041FB
0x1800041f3  call    cs:__imp_IsDebuggerPresent
0x1800041f9  test    eax, eax
0x1800041fb  jz      short loc_180004204
0x1800041fd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004202  jz      short loc_18000422A
0x180004204  mov     rax, cs:g_pfnResultLoggingCallback
0x18000420b  test    rax, rax
0x18000420e  jz      short loc_180004283
0x180004210  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004217  jnz     short loc_180004283
0x180004219  xor     r8d, r8d
0x18000421c  xor     edx, edx
0x18000421e  lea     rcx, [rsp+1500h+var_14E0]
0x180004223  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004228  jmp     short loc_180004283
0x18000422a  mov     ebx, 800h
0x18000422f  mov     rax, cs:g_pfnResultLoggingCallback
0x180004236  test    rax, rax
0x180004239  jz      short loc_180004258
0x18000423b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004242  jnz     short loc_180004258
0x180004244  mov     r8d, ebx
0x180004247  lea     rdx, [rbp+1400h+OutputString]
0x18000424e  lea     rcx, [rsp+1500h+var_14E0]
0x180004253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004258  cmp     [rbp+1400h+OutputString], r12w
0x180004260  jnz     short loc_180004276
0x180004262  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004267  mov     rdx, rbx; unsigned __int16 *
0x18000426a  lea     rcx, [rbp+1400h+OutputString]; this
0x180004271  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004276  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000427d  call    cs:__imp_OutputDebugStringW
0x180004283  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004288  jnz     short loc_180004293
0x18000428a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004291  jz      short loc_1800042A5
0x180004293  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000429a  test    rax, rax
0x18000429d  jz      short loc_1800042A5
0x18000429f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042a4  nop
0x1800042a5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800042aa  jnz     short loc_1800042CD
0x1800042ac  mov     rcx, [rbp+1400h+var_40]
0x1800042b3  xor     rcx, rsp; StackCookie
0x1800042b6  call    __security_check_cookie
0x1800042bb  add     rsp, 14D0h
0x1800042c2  pop     r15
0x1800042c4  pop     r14
0x1800042c6  pop     r12
0x1800042c8  pop     rdi
0x1800042c9  pop     rsi
0x1800042ca  pop     rbx
0x1800042cb  pop     rbp
0x1800042cc  retn
0x1800042cd  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800042d2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800042d8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
