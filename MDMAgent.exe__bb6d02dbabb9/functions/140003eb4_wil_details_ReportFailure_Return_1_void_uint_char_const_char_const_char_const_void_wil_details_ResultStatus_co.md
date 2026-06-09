# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003eb4`
- end: `0x14000416d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400039b0`

## callees

- `0x1400029c0`
- `0x14000353c`
- `0x140003eb4`
- `0x140005534`
- `0x140006934`
- `0x140007a80`
- `0x140007c78`
- `0x140019340`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003f7a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003f7a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004075`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004075`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004105`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004105`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x140003eb4  push    rbp
0x140003eb6  push    rbx
0x140003eb7  push    rsi
0x140003eb8  push    rdi
0x140003eb9  push    r12
0x140003ebb  push    r14
0x140003ebd  push    r15
0x140003ebf  lea     rbp, [rsp-13D0h]
0x140003ec7  mov     eax, 14D0h
0x140003ecc  call    _alloca_probe
0x140003ed1  sub     rsp, rax
0x140003ed4  mov     rax, cs:__security_cookie
0x140003edb  xor     rax, rsp
0x140003ede  mov     [rbp+1400h+var_40], rax
0x140003ee5  mov     rsi, r8
0x140003ee8  mov     edi, edx
0x140003eea  mov     rbx, rcx
0x140003eed  mov     r14, [rbp+1400h+arg_28]
0x140003ef4  xor     edx, edx; Val
0x140003ef6  mov     r8d, 98h; Size
0x140003efc  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140003f01  call    memset_0
0x140003f06  nop
0x140003f07  xor     r12d, r12d
0x140003f0a  mov     [rbp+1400h+OutputString], r12w
0x140003f12  mov     [rbp+1400h+var_1440], r12b
0x140003f16  mov     rdx, [rbp+1400h+arg_30]; int
0x140003f1d  mov     ecx, [rdx]; this
0x140003f1f  mov     [rsp+1500h+var_14D8], ecx
0x140003f23  mov     eax, [rdx+4]
0x140003f26  mov     [rsp+1500h+var_14D4], eax
0x140003f2a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003f2f  mov     r15d, eax
0x140003f32  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140003f3a  mov     ecx, r12d
0x140003f3d  lea     eax, [r12+8]
0x140003f42  cmp     dword ptr [rdx+8], 1
0x140003f46  cmovz   ecx, eax
0x140003f49  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140003f4d  lea     ecx, [rax-7]
0x140003f50  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003f58  inc     ecx
0x140003f5a  mov     [rsp+1500h+var_14D0], ecx
0x140003f5e  mov     rcx, [rbp+1400h+arg_38]
0x140003f65  test    rcx, rcx
0x140003f68  jz      short loc_140003F75
0x140003f6a  cmp     [rcx], r12w
0x140003f6e  mov     [rsp+1500h+var_14C8], rcx
0x140003f73  jnz     short loc_140003F7A
0x140003f75  mov     [rsp+1500h+var_14C8], r12
0x140003f7a  call    cs:__imp_GetCurrentThreadId
0x140003f81  nop     dword ptr [rax+rax+00h]
0x140003f86  mov     [rsp+1500h+var_14C0], eax
0x140003f8a  mov     [rsp+1500h+var_14A8], rsi
0x140003f8f  mov     [rsp+1500h+var_14A0], edi
0x140003f93  mov     [rsp+1500h+var_149C], r15d
0x140003f98  mov     [rsp+1500h+var_14B8], r12
0x140003f9d  mov     [rsp+1500h+var_14B0], r12
0x140003fa2  mov     [rbp+1400h+var_1458], r14
0x140003fa6  mov     [rbp+1400h+var_1450], rbx
0x140003faa  mov     [rsp+1500h+var_1498], r12
0x140003faf  xorps   xmm0, xmm0
0x140003fb2  xor     eax, eax
0x140003fb4  movups  [rbp+1400h+var_1478], xmm0
0x140003fb8  mov     [rbp+1400h+var_1468], rax
0x140003fbc  xorps   xmm1, xmm1
0x140003fbf  movups  [rsp+1500h+var_1490], xmm1
0x140003fc4  mov     [rbp+1400h+var_1480], rax
0x140003fc8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003fcf  test    rax, rax
0x140003fd2  jz      short loc_140003FDF
0x140003fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fd9  mov     [rbp+1400h+var_1460], rax
0x140003fdd  jmp     short loc_140003FE3
0x140003fdf  mov     [rbp+1400h+var_1460], r12
0x140003fe3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003fea  test    rax, rax
0x140003fed  jz      short loc_140003FF9
0x140003fef  lea     rcx, [rsp+1500h+var_14E0]
0x140003ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ff9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004000  test    rax, rax
0x140004003  jz      short loc_140004019
0x140004005  mov     r8d, 400h
0x14000400b  lea     rdx, [rbp+1400h+var_1440]
0x14000400f  lea     rcx, [rsp+1500h+var_14E0]
0x140004014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004019  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004020  test    rax, rax
0x140004023  jz      short loc_14000402F
0x140004025  lea     rcx, [rsp+1500h+var_14E0]
0x14000402a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000402f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004036  test    rax, rax
0x140004039  jz      short loc_14000404C
0x14000403b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140004040  jnz     short loc_14000404C
0x140004042  lea     rcx, [rsp+1500h+var_14E0]
0x140004047  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000404c  cmp     [rsp+1500h+var_14D8], r12d
0x140004051  jge     loc_140004167
0x140004057  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000405e  jnz     short loc_140004085
0x140004060  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004067  test    rax, rax
0x14000406a  jz      short loc_140004075
0x14000406c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004071  test    al, al
0x140004073  jmp     short loc_140004083
0x140004075  call    cs:__imp_IsDebuggerPresent
0x14000407c  nop     dword ptr [rax+rax+00h]
0x140004081  test    eax, eax
0x140004083  jz      short loc_14000408C
0x140004085  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000408a  jz      short loc_1400040B2
0x14000408c  mov     rax, cs:g_pfnResultLoggingCallback
0x140004093  test    rax, rax
0x140004096  jz      short loc_140004111
0x140004098  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000409f  jnz     short loc_140004111
0x1400040a1  xor     r8d, r8d
0x1400040a4  xor     edx, edx
0x1400040a6  lea     rcx, [rsp+1500h+var_14E0]
0x1400040ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040b0  jmp     short loc_140004111
0x1400040b2  mov     ebx, 800h
0x1400040b7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400040be  test    rax, rax
0x1400040c1  jz      short loc_1400040E0
0x1400040c3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400040ca  jnz     short loc_1400040E0
0x1400040cc  mov     r8d, ebx
0x1400040cf  lea     rdx, [rbp+1400h+OutputString]
0x1400040d6  lea     rcx, [rsp+1500h+var_14E0]
0x1400040db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040e0  cmp     [rbp+1400h+OutputString], r12w
0x1400040e8  jnz     short loc_1400040FE
0x1400040ea  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1400040ef  mov     rdx, rbx; unsigned __int16 *
0x1400040f2  lea     rcx, [rbp+1400h+OutputString]; this
0x1400040f9  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400040fe  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140004105  call    cs:__imp_OutputDebugStringW
0x14000410c  nop     dword ptr [rax+rax+00h]
0x140004111  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140004116  jnz     short loc_140004121
0x140004118  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000411f  jz      short loc_140004133
0x140004121  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004128  test    rax, rax
0x14000412b  jz      short loc_140004133
0x14000412d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004132  nop
0x140004133  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140004138  jnz     short loc_14000415C
0x14000413a  mov     rcx, [rbp+1400h+var_40]
0x140004141  xor     rcx, rsp; StackCookie
0x140004144  call    __security_check_cookie
0x140004149  add     rsp, 14D0h
0x140004150  pop     r15
0x140004152  pop     r14
0x140004154  pop     r12
0x140004156  pop     rdi
0x140004157  pop     rsi
0x140004158  pop     rbx
0x140004159  pop     rbp
0x14000415a  retn
0x14000415c  lea     rcx, [rsp+1500h+var_14E0]; this
0x140004161  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140004167  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
