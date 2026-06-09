# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000f924`
- end: `0x18000fbab`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `647`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000f41c`

## callees

- `0x18000c6e0`
- `0x18000d688`
- `0x18000f924`
- `0x180010984`
- `0x180011434`
- `0x180011bf0`
- `0x1800128f8`
- `0x180012ab4`
- `0x18011d1c0`
- `0x18012d010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18000fb24`
- `KERNEL32!OutputDebugStringW` at `0x18000fb24`
- `KERNEL32!GetCurrentThreadId` at `0x18000f9ea`
- `KERNEL32!GetCurrentThreadId` at `0x18000f9ea`

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
  bool v14; // zf
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  _WORD *v24; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v21 = *a7;
  v22 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v19 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v20 = v12;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v14 = *a8 == 0, v24 = a8, v14) )
    v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v28 = a3;
  v29 = a2;
  v30 = v11;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::FailFastImmediate_Unexpected(v15);
  if ( !wil::details::IsDebuggerPresent(v15) || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v16);
}

```

## disassembly

```asm
0x18000f924  push    rbp
0x18000f926  push    rbx
0x18000f927  push    rsi
0x18000f928  push    rdi
0x18000f929  push    r12
0x18000f92b  push    r14
0x18000f92d  push    r15
0x18000f92f  lea     rbp, [rsp-13D0h]
0x18000f937  mov     eax, 14D0h
0x18000f93c  call    _alloca_probe
0x18000f941  sub     rsp, rax
0x18000f944  mov     rax, cs:__security_cookie
0x18000f94b  xor     rax, rsp
0x18000f94e  mov     [rbp+1400h+var_40], rax
0x18000f955  mov     rsi, r8
0x18000f958  mov     edi, edx
0x18000f95a  mov     rbx, rcx
0x18000f95d  mov     r14, [rbp+1400h+arg_28]
0x18000f964  xor     edx, edx; Val
0x18000f966  mov     r8d, 98h; Size
0x18000f96c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000f971  call    memset_0
0x18000f976  nop
0x18000f977  xor     r12d, r12d
0x18000f97a  mov     [rbp+1400h+OutputString], r12w
0x18000f982  mov     [rbp+1400h+var_1440], r12b
0x18000f986  mov     rdx, [rbp+1400h+arg_30]; int
0x18000f98d  mov     ecx, [rdx]; this
0x18000f98f  mov     [rsp+1500h+var_14D8], ecx
0x18000f993  mov     eax, [rdx+4]
0x18000f996  mov     [rsp+1500h+var_14D4], eax
0x18000f99a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000f99f  mov     r15d, eax
0x18000f9a2  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000f9aa  mov     ecx, r12d
0x18000f9ad  lea     eax, [r12+8]
0x18000f9b2  cmp     dword ptr [rdx+8], 1
0x18000f9b6  cmovz   ecx, eax
0x18000f9b9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000f9bd  lea     ecx, [rax-7]
0x18000f9c0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000f9c8  inc     ecx
0x18000f9ca  mov     [rsp+1500h+var_14D0], ecx
0x18000f9ce  mov     rcx, [rbp+1400h+arg_38]
0x18000f9d5  test    rcx, rcx
0x18000f9d8  jz      short loc_18000F9E5
0x18000f9da  cmp     [rcx], r12w
0x18000f9de  mov     [rsp+1500h+var_14C8], rcx
0x18000f9e3  jnz     short loc_18000F9EA
0x18000f9e5  mov     [rsp+1500h+var_14C8], r12
0x18000f9ea  call    cs:__imp_GetCurrentThreadId
0x18000f9f0  mov     [rsp+1500h+var_14C0], eax
0x18000f9f4  mov     [rsp+1500h+var_14A8], rsi
0x18000f9f9  mov     [rsp+1500h+var_14A0], edi
0x18000f9fd  mov     [rsp+1500h+var_149C], r15d
0x18000fa02  mov     [rsp+1500h+var_14B8], r12
0x18000fa07  mov     [rsp+1500h+var_14B0], r12
0x18000fa0c  mov     [rbp+1400h+var_1458], r14
0x18000fa10  mov     [rbp+1400h+var_1450], rbx
0x18000fa14  mov     [rsp+1500h+var_1498], r12
0x18000fa19  xorps   xmm0, xmm0
0x18000fa1c  xor     eax, eax
0x18000fa1e  movups  [rbp+1400h+var_1478], xmm0
0x18000fa22  mov     [rbp+1400h+var_1468], rax
0x18000fa26  xorps   xmm1, xmm1
0x18000fa29  movups  [rsp+1500h+var_1490], xmm1
0x18000fa2e  mov     [rbp+1400h+var_1480], rax
0x18000fa32  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000fa39  test    rax, rax
0x18000fa3c  jz      short loc_18000FA49
0x18000fa3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa43  mov     [rbp+1400h+var_1460], rax
0x18000fa47  jmp     short loc_18000FA4D
0x18000fa49  mov     [rbp+1400h+var_1460], r12
0x18000fa4d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000fa54  test    rax, rax
0x18000fa57  jz      short loc_18000FA63
0x18000fa59  lea     rcx, [rsp+1500h+var_14E0]
0x18000fa5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa63  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000fa6a  test    rax, rax
0x18000fa6d  jz      short loc_18000FA83
0x18000fa6f  mov     r8d, 400h
0x18000fa75  lea     rdx, [rbp+1400h+var_1440]
0x18000fa79  lea     rcx, [rsp+1500h+var_14E0]
0x18000fa7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa83  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000fa8a  test    rax, rax
0x18000fa8d  jz      short loc_18000FA99
0x18000fa8f  lea     rcx, [rsp+1500h+var_14E0]
0x18000fa94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fa99  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000faa0  test    rax, rax
0x18000faa3  jz      short loc_18000FAB6
0x18000faa5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000faaa  jnz     short loc_18000FAB6
0x18000faac  lea     rcx, [rsp+1500h+var_14E0]
0x18000fab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fab6  cmp     [rsp+1500h+var_14D8], r12d
0x18000fabb  jge     loc_18000FBA5
0x18000fac1  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x18000fac6  test    al, al
0x18000fac8  jz      short loc_18000FB2C
0x18000faca  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000facf  jnz     short loc_18000FB2C
0x18000fad1  mov     ebx, 800h
0x18000fad6  mov     rax, cs:g_pfnResultLoggingCallback
0x18000fadd  test    rax, rax
0x18000fae0  jz      short loc_18000FAFF
0x18000fae2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000fae9  jnz     short loc_18000FAFF
0x18000faeb  mov     r8d, ebx
0x18000faee  lea     rdx, [rbp+1400h+OutputString]
0x18000faf5  lea     rcx, [rsp+1500h+var_14E0]
0x18000fafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000faff  cmp     [rbp+1400h+OutputString], r12w
0x18000fb07  jnz     short loc_18000FB1D
0x18000fb09  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000fb0e  mov     rdx, rbx; unsigned __int16 *
0x18000fb11  lea     rcx, [rbp+1400h+OutputString]; this
0x18000fb18  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000fb1d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000fb24  call    cs:__imp_OutputDebugStringW
0x18000fb2a  jmp     short loc_18000FB50
0x18000fb2c  mov     rax, cs:g_pfnResultLoggingCallback
0x18000fb33  test    rax, rax
0x18000fb36  jz      short loc_18000FB50
0x18000fb38  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000fb3f  jnz     short loc_18000FB50
0x18000fb41  xor     r8d, r8d
0x18000fb44  xor     edx, edx
0x18000fb46  lea     rcx, [rsp+1500h+var_14E0]
0x18000fb4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb50  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000fb55  jnz     short loc_18000FB60
0x18000fb57  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000fb5e  jz      short loc_18000FB72
0x18000fb60  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000fb67  test    rax, rax
0x18000fb6a  jz      short loc_18000FB72
0x18000fb6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fb71  nop
0x18000fb72  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000fb77  jnz     short loc_18000FB9A
0x18000fb79  mov     rcx, [rbp+1400h+var_40]
0x18000fb80  xor     rcx, rsp; StackCookie
0x18000fb83  call    __security_check_cookie
0x18000fb88  add     rsp, 14D0h
0x18000fb8f  pop     r15
0x18000fb91  pop     r14
0x18000fb93  pop     r12
0x18000fb95  pop     rdi
0x18000fb96  pop     rsi
0x18000fb97  pop     rbx
0x18000fb98  pop     rbp
0x18000fb99  retn
0x18000fb9a  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000fb9f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000fba5  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
