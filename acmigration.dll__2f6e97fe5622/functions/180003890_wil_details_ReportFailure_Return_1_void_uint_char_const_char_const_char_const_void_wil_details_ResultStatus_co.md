# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003890`
- end: `0x180003b3e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `686`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800031cc`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x180003890`
- `0x180005d64`
- `0x1800076d0`
- `0x180009b00`
- `0x180009ccc`
- `0x1800650c0`
- `0x18006a010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180003a53`
- `KERNEL32!IsDebuggerPresent` at `0x180003a53`
- `KERNEL32!OutputDebugStringW` at `0x180003add`
- `KERNEL32!OutputDebugStringW` at `0x180003add`
- `KERNEL32!GetCurrentThreadId` at `0x18000395e`
- `KERNEL32!GetCurrentThreadId` at `0x18000395e`

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
  __int64 v38; // [rsp+C0h] [rbp-40h]
  char v39[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v38 = -2;
  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
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
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v39, 1024);
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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x180003890  push    rbp
0x180003892  push    rbx
0x180003893  push    rsi
0x180003894  push    rdi
0x180003895  push    r12
0x180003897  push    r14
0x180003899  push    r15
0x18000389b  lea     rbp, [rsp-13E0h]
0x1800038a3  mov     eax, 14E0h
0x1800038a8  call    _alloca_probe
0x1800038ad  sub     rsp, rax
0x1800038b0  mov     [rbp+1410h+var_1450], 0FFFFFFFFFFFFFFFEh
0x1800038b8  mov     rax, cs:__security_cookie
0x1800038bf  xor     rax, rsp
0x1800038c2  mov     [rbp+1410h+var_40], rax
0x1800038c9  mov     rsi, r8
0x1800038cc  mov     edi, edx
0x1800038ce  mov     rbx, rcx
0x1800038d1  mov     r14, [rbp+1410h+arg_28]
0x1800038d8  xor     edx, edx; Val
0x1800038da  mov     r8d, 98h; Size
0x1800038e0  lea     rcx, [rsp+1510h+var_14F0]; void *
0x1800038e5  call    memset_0
0x1800038ea  nop
0x1800038eb  xor     r12d, r12d
0x1800038ee  mov     [rbp+1410h+OutputString], r12w
0x1800038f6  mov     [rbp+1410h+var_1440], r12b
0x1800038fa  mov     rdx, [rbp+1410h+arg_30]; int
0x180003901  mov     ecx, [rdx]; this
0x180003903  mov     [rsp+1510h+var_14E8], ecx
0x180003907  mov     eax, [rdx+4]
0x18000390a  mov     [rsp+1510h+var_14E4], eax
0x18000390e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003913  mov     r15d, eax
0x180003916  mov     dword ptr [rsp+1510h+var_14F0], 1
0x18000391e  mov     ecx, r12d
0x180003921  lea     eax, [r12+8]
0x180003926  cmp     dword ptr [rdx+8], 1
0x18000392a  cmovz   ecx, eax
0x18000392d  mov     dword ptr [rsp+1510h+var_14F0+4], ecx
0x180003931  lea     ecx, [rax-7]
0x180003934  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000393c  inc     ecx
0x18000393e  mov     [rsp+1510h+var_14E0], ecx
0x180003942  mov     rcx, [rbp+1410h+arg_38]
0x180003949  test    rcx, rcx
0x18000394c  jz      short loc_180003959
0x18000394e  cmp     [rcx], r12w
0x180003952  mov     [rsp+1510h+var_14D8], rcx
0x180003957  jnz     short loc_18000395E
0x180003959  mov     [rsp+1510h+var_14D8], r12
0x18000395e  call    cs:__imp_GetCurrentThreadId
0x180003964  mov     [rsp+1510h+var_14D0], eax
0x180003968  mov     [rsp+1510h+var_14B8], rsi
0x18000396d  mov     [rsp+1510h+var_14B0], edi
0x180003971  mov     [rsp+1510h+var_14AC], r15d
0x180003976  mov     [rsp+1510h+var_14C8], r12
0x18000397b  mov     [rsp+1510h+var_14C0], r12
0x180003980  mov     [rbp+1410h+var_1468], r14
0x180003984  mov     [rbp+1410h+var_1460], rbx
0x180003988  mov     [rsp+1510h+var_14A8], r12
0x18000398d  xorps   xmm0, xmm0
0x180003990  xor     eax, eax
0x180003992  movups  [rbp+1410h+var_1488], xmm0
0x180003996  mov     [rbp+1410h+var_1478], rax
0x18000399a  xorps   xmm1, xmm1
0x18000399d  movups  [rsp+1510h+var_14A0], xmm1
0x1800039a2  mov     [rbp+1410h+var_1490], rax
0x1800039a6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800039ad  test    rax, rax
0x1800039b0  jz      short loc_1800039BD
0x1800039b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039b7  mov     [rbp+1410h+var_1470], rax
0x1800039bb  jmp     short loc_1800039C1
0x1800039bd  mov     [rbp+1410h+var_1470], r12
0x1800039c1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800039c8  test    rax, rax
0x1800039cb  jz      short loc_1800039D7
0x1800039cd  lea     rcx, [rsp+1510h+var_14F0]
0x1800039d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039d7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800039de  test    rax, rax
0x1800039e1  jz      short loc_1800039F7
0x1800039e3  mov     r8d, 400h
0x1800039e9  lea     rdx, [rbp+1410h+var_1440]
0x1800039ed  lea     rcx, [rsp+1510h+var_14F0]
0x1800039f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039f7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800039fe  test    rax, rax
0x180003a01  jz      short loc_180003A0D
0x180003a03  lea     rcx, [rsp+1510h+var_14F0]
0x180003a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a0d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003a14  test    rax, rax
0x180003a17  jz      short loc_180003A2A
0x180003a19  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x180003a1e  jnz     short loc_180003A2A
0x180003a20  lea     rcx, [rsp+1510h+var_14F0]
0x180003a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a2a  cmp     [rsp+1510h+var_14E8], r12d
0x180003a2f  jge     loc_180003B38
0x180003a35  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003a3c  jnz     short loc_180003A5D
0x180003a3e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003a45  test    rax, rax
0x180003a48  jz      short loc_180003A53
0x180003a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a4f  test    al, al
0x180003a51  jmp     short loc_180003A5B
0x180003a53  call    cs:__imp_IsDebuggerPresent
0x180003a59  test    eax, eax
0x180003a5b  jz      short loc_180003A64
0x180003a5d  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x180003a62  jz      short loc_180003A8A
0x180003a64  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a6b  test    rax, rax
0x180003a6e  jz      short loc_180003AE3
0x180003a70  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003a77  jnz     short loc_180003AE3
0x180003a79  xor     r8d, r8d
0x180003a7c  xor     edx, edx
0x180003a7e  lea     rcx, [rsp+1510h+var_14F0]
0x180003a83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a88  jmp     short loc_180003AE3
0x180003a8a  mov     ebx, 800h
0x180003a8f  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a96  test    rax, rax
0x180003a99  jz      short loc_180003AB8
0x180003a9b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003aa2  jnz     short loc_180003AB8
0x180003aa4  mov     r8d, ebx
0x180003aa7  lea     rdx, [rbp+1410h+OutputString]
0x180003aae  lea     rcx, [rsp+1510h+var_14F0]
0x180003ab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ab8  cmp     [rbp+1410h+OutputString], r12w
0x180003ac0  jnz     short loc_180003AD6
0x180003ac2  lea     r8, [rsp+1510h+var_14F0]; unsigned __int64
0x180003ac7  mov     rdx, rbx; unsigned __int16 *
0x180003aca  lea     rcx, [rbp+1410h+OutputString]; this
0x180003ad1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003ad6  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x180003add  call    cs:__imp_OutputDebugStringW
0x180003ae3  test    byte ptr [rsp+1510h+var_14F0+4], 4
0x180003ae8  jnz     short loc_180003AF3
0x180003aea  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003af1  jz      short loc_180003B05
0x180003af3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003afa  test    rax, rax
0x180003afd  jz      short loc_180003B05
0x180003aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b04  nop
0x180003b05  test    byte ptr [rsp+1510h+var_14F0+4], 1
0x180003b0a  jnz     short loc_180003B2D
0x180003b0c  mov     rcx, [rbp+1410h+var_40]
0x180003b13  xor     rcx, rsp; StackCookie
0x180003b16  call    __security_check_cookie
0x180003b1b  add     rsp, 14E0h
0x180003b22  pop     r15
0x180003b24  pop     r14
0x180003b26  pop     r12
0x180003b28  pop     rdi
0x180003b29  pop     rsi
0x180003b2a  pop     rbx
0x180003b2b  pop     rbp
0x180003b2c  retn
0x180003b2d  lea     rcx, [rsp+1510h+var_14F0]; this
0x180003b32  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003b38  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
