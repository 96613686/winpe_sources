# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003f78`
- end: `0x18000421e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800035d8`

## callees

- `0x180002300`
- `0x180002de0`
- `0x180003f78`
- `0x18000860c`
- `0x18000a8f8`
- `0x18000de50`
- `0x18000e804`
- `0x180010290`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000403e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000403e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004133`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004133`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800041bd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800041bd`

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
0x180003f78  push    rbp
0x180003f7a  push    rbx
0x180003f7b  push    rsi
0x180003f7c  push    rdi
0x180003f7d  push    r12
0x180003f7f  push    r14
0x180003f81  push    r15
0x180003f83  lea     rbp, [rsp-13D0h]
0x180003f8b  mov     eax, 14D0h
0x180003f90  call    _alloca_probe
0x180003f95  sub     rsp, rax
0x180003f98  mov     rax, cs:__security_cookie
0x180003f9f  xor     rax, rsp
0x180003fa2  mov     [rbp+1400h+var_40], rax
0x180003fa9  mov     rsi, r8
0x180003fac  mov     edi, edx
0x180003fae  mov     rbx, rcx
0x180003fb1  mov     r14, [rbp+1400h+arg_28]
0x180003fb8  xor     edx, edx; Val
0x180003fba  mov     r8d, 98h; Size
0x180003fc0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003fc5  call    memset_0
0x180003fca  nop
0x180003fcb  xor     r12d, r12d
0x180003fce  mov     [rbp+1400h+OutputString], r12w
0x180003fd6  mov     [rbp+1400h+var_1440], r12b
0x180003fda  mov     rdx, [rbp+1400h+arg_30]; int
0x180003fe1  mov     ecx, [rdx]; this
0x180003fe3  mov     [rsp+1500h+var_14D8], ecx
0x180003fe7  mov     eax, [rdx+4]
0x180003fea  mov     [rsp+1500h+var_14D4], eax
0x180003fee  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003ff3  mov     r15d, eax
0x180003ff6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003ffe  mov     ecx, r12d
0x180004001  lea     eax, [r12+8]
0x180004006  cmp     dword ptr [rdx+8], 1
0x18000400a  cmovz   ecx, eax
0x18000400d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004011  lea     ecx, [rax-7]
0x180004014  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000401c  inc     ecx
0x18000401e  mov     [rsp+1500h+var_14D0], ecx
0x180004022  mov     rcx, [rbp+1400h+arg_38]
0x180004029  test    rcx, rcx
0x18000402c  jz      short loc_180004039
0x18000402e  cmp     [rcx], r12w
0x180004032  mov     [rsp+1500h+var_14C8], rcx
0x180004037  jnz     short loc_18000403E
0x180004039  mov     [rsp+1500h+var_14C8], r12
0x18000403e  call    cs:__imp_GetCurrentThreadId
0x180004044  mov     [rsp+1500h+var_14C0], eax
0x180004048  mov     [rsp+1500h+var_14A8], rsi
0x18000404d  mov     [rsp+1500h+var_14A0], edi
0x180004051  mov     [rsp+1500h+var_149C], r15d
0x180004056  mov     [rsp+1500h+var_14B8], r12
0x18000405b  mov     [rsp+1500h+var_14B0], r12
0x180004060  mov     [rbp+1400h+var_1458], r14
0x180004064  mov     [rbp+1400h+var_1450], rbx
0x180004068  mov     [rsp+1500h+var_1498], r12
0x18000406d  xorps   xmm0, xmm0
0x180004070  xor     eax, eax
0x180004072  movups  [rbp+1400h+var_1478], xmm0
0x180004076  mov     [rbp+1400h+var_1468], rax
0x18000407a  xorps   xmm1, xmm1
0x18000407d  movups  [rsp+1500h+var_1490], xmm1
0x180004082  mov     [rbp+1400h+var_1480], rax
0x180004086  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000408d  test    rax, rax
0x180004090  jz      short loc_18000409D
0x180004092  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004097  mov     [rbp+1400h+var_1460], rax
0x18000409b  jmp     short loc_1800040A1
0x18000409d  mov     [rbp+1400h+var_1460], r12
0x1800040a1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800040a8  test    rax, rax
0x1800040ab  jz      short loc_1800040B7
0x1800040ad  lea     rcx, [rsp+1500h+var_14E0]
0x1800040b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040b7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800040be  test    rax, rax
0x1800040c1  jz      short loc_1800040D7
0x1800040c3  mov     r8d, 400h
0x1800040c9  lea     rdx, [rbp+1400h+var_1440]
0x1800040cd  lea     rcx, [rsp+1500h+var_14E0]
0x1800040d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040d7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800040de  test    rax, rax
0x1800040e1  jz      short loc_1800040ED
0x1800040e3  lea     rcx, [rsp+1500h+var_14E0]
0x1800040e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ed  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800040f4  test    rax, rax
0x1800040f7  jz      short loc_18000410A
0x1800040f9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800040fe  jnz     short loc_18000410A
0x180004100  lea     rcx, [rsp+1500h+var_14E0]
0x180004105  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000410a  cmp     [rsp+1500h+var_14D8], r12d
0x18000410f  jge     loc_180004218
0x180004115  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000411c  jnz     short loc_18000413D
0x18000411e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004125  test    rax, rax
0x180004128  jz      short loc_180004133
0x18000412a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000412f  test    al, al
0x180004131  jmp     short loc_18000413B
0x180004133  call    cs:__imp_IsDebuggerPresent
0x180004139  test    eax, eax
0x18000413b  jz      short loc_180004144
0x18000413d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004142  jz      short loc_18000416A
0x180004144  mov     rax, cs:g_pfnResultLoggingCallback
0x18000414b  test    rax, rax
0x18000414e  jz      short loc_1800041C3
0x180004150  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004157  jnz     short loc_1800041C3
0x180004159  xor     r8d, r8d
0x18000415c  xor     edx, edx
0x18000415e  lea     rcx, [rsp+1500h+var_14E0]
0x180004163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004168  jmp     short loc_1800041C3
0x18000416a  mov     ebx, 800h
0x18000416f  mov     rax, cs:g_pfnResultLoggingCallback
0x180004176  test    rax, rax
0x180004179  jz      short loc_180004198
0x18000417b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004182  jnz     short loc_180004198
0x180004184  mov     r8d, ebx
0x180004187  lea     rdx, [rbp+1400h+OutputString]
0x18000418e  lea     rcx, [rsp+1500h+var_14E0]
0x180004193  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004198  cmp     [rbp+1400h+OutputString], r12w
0x1800041a0  jnz     short loc_1800041B6
0x1800041a2  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800041a7  mov     rdx, rbx; unsigned __int16 *
0x1800041aa  lea     rcx, [rbp+1400h+OutputString]; this
0x1800041b1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800041b6  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800041bd  call    cs:__imp_OutputDebugStringW
0x1800041c3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800041c8  jnz     short loc_1800041D3
0x1800041ca  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800041d1  jz      short loc_1800041E5
0x1800041d3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800041da  test    rax, rax
0x1800041dd  jz      short loc_1800041E5
0x1800041df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041e4  nop
0x1800041e5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800041ea  jnz     short loc_18000420D
0x1800041ec  mov     rcx, [rbp+1400h+var_40]
0x1800041f3  xor     rcx, rsp; StackCookie
0x1800041f6  call    __security_check_cookie
0x1800041fb  add     rsp, 14D0h
0x180004202  pop     r15
0x180004204  pop     r14
0x180004206  pop     r12
0x180004208  pop     rdi
0x180004209  pop     rsi
0x18000420a  pop     rbx
0x18000420b  pop     rbp
0x18000420c  retn
0x18000420d  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004212  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004218  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
