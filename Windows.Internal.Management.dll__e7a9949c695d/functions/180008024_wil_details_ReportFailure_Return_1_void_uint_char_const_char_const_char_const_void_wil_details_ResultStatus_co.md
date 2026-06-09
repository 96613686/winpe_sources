# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180008024`
- end: `0x1800082ca`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180007ca8`

## callees

- `0x180004d50`
- `0x180005904`
- `0x180008024`
- `0x180008f84`
- `0x18000a090`
- `0x18000ad38`
- `0x18000aef4`
- `0x1800b32f0`
- `0x1800b7010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800080ea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800080ea`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008269`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008269`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800081df`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800081df`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
0x180008024  push    rbp
0x180008026  push    rbx
0x180008027  push    rsi
0x180008028  push    rdi
0x180008029  push    r12
0x18000802b  push    r14
0x18000802d  push    r15
0x18000802f  lea     rbp, [rsp-13D0h]
0x180008037  mov     eax, 14D0h
0x18000803c  call    _alloca_probe
0x180008041  sub     rsp, rax
0x180008044  mov     rax, cs:__security_cookie
0x18000804b  xor     rax, rsp
0x18000804e  mov     [rbp+1400h+var_40], rax
0x180008055  mov     rsi, r8
0x180008058  mov     edi, edx
0x18000805a  mov     rbx, rcx
0x18000805d  mov     r14, [rbp+1400h+arg_28]
0x180008064  xor     edx, edx; Val
0x180008066  mov     r8d, 98h; Size
0x18000806c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180008071  call    memset_0
0x180008076  nop
0x180008077  xor     r12d, r12d
0x18000807a  mov     [rbp+1400h+OutputString], r12w
0x180008082  mov     [rbp+1400h+var_1440], r12b
0x180008086  mov     rdx, [rbp+1400h+arg_30]; int
0x18000808d  mov     ecx, [rdx]; this
0x18000808f  mov     [rsp+1500h+var_14D8], ecx
0x180008093  mov     eax, [rdx+4]
0x180008096  mov     [rsp+1500h+var_14D4], eax
0x18000809a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000809f  mov     r15d, eax
0x1800080a2  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800080aa  mov     ecx, r12d
0x1800080ad  lea     eax, [r12+8]
0x1800080b2  cmp     dword ptr [rdx+8], 1
0x1800080b6  cmovz   ecx, eax
0x1800080b9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800080bd  lea     ecx, [rax-7]
0x1800080c0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800080c8  inc     ecx
0x1800080ca  mov     [rsp+1500h+var_14D0], ecx
0x1800080ce  mov     rcx, [rbp+1400h+arg_38]
0x1800080d5  test    rcx, rcx
0x1800080d8  jz      short loc_1800080E5
0x1800080da  cmp     [rcx], r12w
0x1800080de  mov     [rsp+1500h+var_14C8], rcx
0x1800080e3  jnz     short loc_1800080EA
0x1800080e5  mov     [rsp+1500h+var_14C8], r12
0x1800080ea  call    cs:__imp_GetCurrentThreadId
0x1800080f0  mov     [rsp+1500h+var_14C0], eax
0x1800080f4  mov     [rsp+1500h+var_14A8], rsi
0x1800080f9  mov     [rsp+1500h+var_14A0], edi
0x1800080fd  mov     [rsp+1500h+var_149C], r15d
0x180008102  mov     [rsp+1500h+var_14B8], r12
0x180008107  mov     [rsp+1500h+var_14B0], r12
0x18000810c  mov     [rbp+1400h+var_1458], r14
0x180008110  mov     [rbp+1400h+var_1450], rbx
0x180008114  mov     [rsp+1500h+var_1498], r12
0x180008119  xorps   xmm0, xmm0
0x18000811c  xor     eax, eax
0x18000811e  movups  [rbp+1400h+var_1478], xmm0
0x180008122  mov     [rbp+1400h+var_1468], rax
0x180008126  xorps   xmm1, xmm1
0x180008129  movups  [rsp+1500h+var_1490], xmm1
0x18000812e  mov     [rbp+1400h+var_1480], rax
0x180008132  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008139  test    rax, rax
0x18000813c  jz      short loc_180008149
0x18000813e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008143  mov     [rbp+1400h+var_1460], rax
0x180008147  jmp     short loc_18000814D
0x180008149  mov     [rbp+1400h+var_1460], r12
0x18000814d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008154  test    rax, rax
0x180008157  jz      short loc_180008163
0x180008159  lea     rcx, [rsp+1500h+var_14E0]
0x18000815e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008163  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000816a  test    rax, rax
0x18000816d  jz      short loc_180008183
0x18000816f  mov     r8d, 400h
0x180008175  lea     rdx, [rbp+1400h+var_1440]
0x180008179  lea     rcx, [rsp+1500h+var_14E0]
0x18000817e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008183  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000818a  test    rax, rax
0x18000818d  jz      short loc_180008199
0x18000818f  lea     rcx, [rsp+1500h+var_14E0]
0x180008194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008199  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800081a0  test    rax, rax
0x1800081a3  jz      short loc_1800081B6
0x1800081a5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800081aa  jnz     short loc_1800081B6
0x1800081ac  lea     rcx, [rsp+1500h+var_14E0]
0x1800081b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081b6  cmp     [rsp+1500h+var_14D8], r12d
0x1800081bb  jge     loc_1800082C4
0x1800081c1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800081c8  jnz     short loc_1800081E9
0x1800081ca  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800081d1  test    rax, rax
0x1800081d4  jz      short loc_1800081DF
0x1800081d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081db  test    al, al
0x1800081dd  jmp     short loc_1800081E7
0x1800081df  call    cs:__imp_IsDebuggerPresent
0x1800081e5  test    eax, eax
0x1800081e7  jz      short loc_1800081F0
0x1800081e9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800081ee  jz      short loc_180008216
0x1800081f0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800081f7  test    rax, rax
0x1800081fa  jz      short loc_18000826F
0x1800081fc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180008203  jnz     short loc_18000826F
0x180008205  xor     r8d, r8d
0x180008208  xor     edx, edx
0x18000820a  lea     rcx, [rsp+1500h+var_14E0]
0x18000820f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008214  jmp     short loc_18000826F
0x180008216  mov     ebx, 800h
0x18000821b  mov     rax, cs:g_pfnResultLoggingCallback
0x180008222  test    rax, rax
0x180008225  jz      short loc_180008244
0x180008227  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000822e  jnz     short loc_180008244
0x180008230  mov     r8d, ebx
0x180008233  lea     rdx, [rbp+1400h+OutputString]
0x18000823a  lea     rcx, [rsp+1500h+var_14E0]
0x18000823f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008244  cmp     [rbp+1400h+OutputString], r12w
0x18000824c  jnz     short loc_180008262
0x18000824e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180008253  mov     rdx, rbx; unsigned __int16 *
0x180008256  lea     rcx, [rbp+1400h+OutputString]; this
0x18000825d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008262  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180008269  call    cs:__imp_OutputDebugStringW
0x18000826f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180008274  jnz     short loc_18000827F
0x180008276  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000827d  jz      short loc_180008291
0x18000827f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008286  test    rax, rax
0x180008289  jz      short loc_180008291
0x18000828b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008290  nop
0x180008291  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180008296  jnz     short loc_1800082B9
0x180008298  mov     rcx, [rbp+1400h+var_40]
0x18000829f  xor     rcx, rsp; StackCookie
0x1800082a2  call    __security_check_cookie
0x1800082a7  add     rsp, 14D0h
0x1800082ae  pop     r15
0x1800082b0  pop     r14
0x1800082b2  pop     r12
0x1800082b4  pop     rdi
0x1800082b5  pop     rsi
0x1800082b6  pop     rbx
0x1800082b7  pop     rbp
0x1800082b8  retn
0x1800082b9  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800082be  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800082c4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
