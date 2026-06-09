# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x18000dce0`
- end: `0x18000df77`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18000df80`

## callees

- `0x18000d4a0`
- `0x18000d590`
- `0x18000dbf0`
- `0x18000dce0`
- `0x18000dfd0`
- `0x1801f7d30`
- `0x180242120`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18000df1c`
- `KERNEL32!OutputDebugStringW` at `0x18000df1c`
- `KERNEL32!GetCurrentThreadId` at `0x18000dd93`
- `KERNEL32!GetCurrentThreadId` at `0x18000dd93`
- `KERNEL32!IsDebuggerPresent` at `0x18000dea8`
- `KERNEL32!IsDebuggerPresent` at `0x18000dea8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int IsDebuggerPresent; // edi
  int v13; // ecx
  bool v14; // zf
  const struct wil::FailureInfo *v15; // rdx
  __int64 v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh]
  int v21; // [rsp+38h] [rbp-C8h]
  int v22; // [rsp+3Ch] [rbp-C4h]
  signed __int32 v23; // [rsp+40h] [rbp-C0h]
  _WORD *v24; // [rsp+48h] [rbp-B8h]
  DWORD CurrentThreadId; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  __int64 v27; // [rsp+60h] [rbp-A0h]
  __int64 v28; // [rsp+68h] [rbp-98h]
  int v29; // [rsp+70h] [rbp-90h]
  int v30; // [rsp+74h] [rbp-8Ch]
  __int64 v31; // [rsp+78h] [rbp-88h]
  __int128 v32; // [rsp+80h] [rbp-80h]
  __int64 v33; // [rsp+90h] [rbp-70h]
  __int128 v34; // [rsp+98h] [rbp-68h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 ModuleName; // [rsp+B0h] [rbp-50h]
  __int64 v37; // [rsp+B8h] [rbp-48h]
  __int64 v38; // [rsp+C0h] [rbp-40h]
  char v39[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2080]; // [rsp+4D0h] [rbp+3D0h] BYREF

  IsDebuggerPresent = 0;
  OutputString[0] = 0;
  v39[0] = 0;
  v21 = *a7;
  v22 = a7[1];
  v18 = wil::details::RecordFailFast((wil::details *)(unsigned int)v21, a2);
  v19 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v20 = v13;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v14 = *a8 == 0, v24 = a8, v14) )
    v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v28 = a3;
  v29 = a2;
  v30 = v18;
  v26 = a5;
  v27 = a4;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
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
  {
    v21 = -2147418113;
    v22 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16)),
         IsDebuggerPresent))
    && wil::g_fResultOutputDebugString
    && (v20 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (wchar_t *)0x800, (__int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v19, 0, 0, v17);
  }
  if ( (v20 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v16);
  }
  wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x18000dce0  push    rbp
0x18000dce2  push    rbx
0x18000dce3  push    rsi
0x18000dce4  push    rdi
0x18000dce5  push    r12
0x18000dce7  push    r13
0x18000dce9  push    r14
0x18000dceb  push    r15
0x18000dced  lea     rbp, [rsp-13D8h]
0x18000dcf5  mov     eax, 14D8h
0x18000dcfa  call    _alloca_probe
0x18000dcff  sub     rsp, rax
0x18000dd02  mov     r12, r9
0x18000dd05  mov     r15, r8
0x18000dd08  mov     r14d, edx
0x18000dd0b  mov     rsi, rcx
0x18000dd0e  mov     r13, [rbp+1410h+arg_20]
0x18000dd15  mov     rax, [rbp+1410h+arg_28]
0x18000dd1c  mov     [rsp+1510h+var_14E8], rax
0x18000dd21  xor     edi, edi
0x18000dd23  mov     [rbp+1410h+OutputString], di
0x18000dd2a  mov     [rbp+1410h+var_1440], dil
0x18000dd2e  mov     rbx, [rbp+1410h+arg_30]
0x18000dd35  mov     ecx, [rbx]; this
0x18000dd37  mov     [rsp+1510h+var_14D8], ecx
0x18000dd3b  mov     eax, [rbx+4]
0x18000dd3e  mov     [rsp+1510h+var_14D4], eax
0x18000dd42  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000dd47  mov     [rsp+1510h+var_14F0], eax
0x18000dd4b  mov     dword ptr [rsp+1510h+var_14E0], 3
0x18000dd53  mov     ecx, edi
0x18000dd55  mov     eax, 8
0x18000dd5a  cmp     dword ptr [rbx+8], 1
0x18000dd5e  cmovz   ecx, eax
0x18000dd61  mov     dword ptr [rsp+1510h+var_14E0+4], ecx
0x18000dd65  mov     ecx, 1
0x18000dd6a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000dd72  inc     ecx
0x18000dd74  mov     [rsp+1510h+var_14D0], ecx
0x18000dd78  mov     rcx, [rbp+1410h+arg_38]
0x18000dd7f  test    rcx, rcx
0x18000dd82  jz      short loc_18000DD8E
0x18000dd84  cmp     [rcx], di
0x18000dd87  mov     [rsp+1510h+var_14C8], rcx
0x18000dd8c  jnz     short loc_18000DD93
0x18000dd8e  mov     [rsp+1510h+var_14C8], rdi
0x18000dd93  call    cs:__imp_GetCurrentThreadId
0x18000dd99  mov     [rsp+1510h+var_14C0], eax
0x18000dd9d  mov     [rsp+1510h+var_14A8], r15
0x18000dda2  mov     [rsp+1510h+var_14A0], r14d
0x18000dda7  mov     eax, [rsp+1510h+var_14F0]
0x18000ddab  mov     [rsp+1510h+var_149C], eax
0x18000ddaf  mov     [rsp+1510h+var_14B8], r13
0x18000ddb4  mov     [rsp+1510h+var_14B0], r12
0x18000ddb9  mov     rax, [rsp+1510h+var_14E8]
0x18000ddbe  mov     [rbp+1410h+var_1458], rax
0x18000ddc2  mov     [rbp+1410h+var_1450], rsi
0x18000ddc6  mov     [rsp+1510h+var_1498], rdi
0x18000ddcb  xorps   xmm0, xmm0
0x18000ddce  xor     eax, eax
0x18000ddd0  movups  [rbp+1410h+var_1478], xmm0
0x18000ddd4  mov     [rbp+1410h+var_1468], rax
0x18000ddd8  xorps   xmm1, xmm1
0x18000dddb  movups  [rbp+1410h+var_1490], xmm1
0x18000dddf  mov     [rbp+1410h+var_1480], rax
0x18000dde3  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000ddea  test    rax, rax
0x18000dded  jz      short loc_18000DDFB
0x18000ddef  call    cs:__guard_dispatch_icall_fptr
0x18000ddf5  mov     [rbp+1410h+var_1460], rax
0x18000ddf9  jmp     short loc_18000DDFF
0x18000ddfb  mov     [rbp+1410h+var_1460], rdi
0x18000ddff  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000de06  test    rax, rax
0x18000de09  jz      short loc_18000DE16
0x18000de0b  lea     rcx, [rsp+1510h+var_14E0]
0x18000de10  call    cs:__guard_dispatch_icall_fptr
0x18000de16  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000de1d  test    rax, rax
0x18000de20  jz      short loc_18000DE37
0x18000de22  mov     r8d, 400h
0x18000de28  lea     rdx, [rbp+1410h+var_1440]
0x18000de2c  lea     rcx, [rsp+1510h+var_14E0]
0x18000de31  call    cs:__guard_dispatch_icall_fptr
0x18000de37  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000de3e  test    rax, rax
0x18000de41  jz      short loc_18000DE4E
0x18000de43  lea     rcx, [rsp+1510h+var_14E0]
0x18000de48  call    cs:__guard_dispatch_icall_fptr
0x18000de4e  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000de55  test    rax, rax
0x18000de58  jz      short loc_18000DE6C
0x18000de5a  test    byte ptr [rsp+1510h+var_14E0+4], 2
0x18000de5f  jnz     short loc_18000DE6C
0x18000de61  lea     rcx, [rsp+1510h+var_14E0]
0x18000de66  call    cs:__guard_dispatch_icall_fptr
0x18000de6c  cmp     [rsp+1510h+var_14D8], edi
0x18000de70  jl      short loc_18000DE88
0x18000de72  mov     [rsp+1510h+var_14D8], 8000FFFFh
0x18000de7a  mov     ecx, 8000FFFFh; this
0x18000de7f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000de84  mov     [rsp+1510h+var_14D4], eax
0x18000de88  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000de8f  jnz     short loc_18000DEB8
0x18000de91  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000de98  test    rax, rax
0x18000de9b  jz      short loc_18000DEA8
0x18000de9d  call    cs:__guard_dispatch_icall_fptr
0x18000dea3  movzx   edi, al
0x18000dea6  jmp     short loc_18000DEB4
0x18000dea8  call    cs:__imp_IsDebuggerPresent
0x18000deae  test    eax, eax
0x18000deb0  setnz   dil
0x18000deb4  test    edi, edi
0x18000deb6  jz      short loc_18000DF24
0x18000deb8  cmp     cs:?g_fResultOutputDebugString@wil@@3_NA, 0; bool wil::g_fResultOutputDebugString
0x18000debf  jz      short loc_18000DF24
0x18000dec1  test    byte ptr [rsp+1510h+var_14E0+4], 2
0x18000dec6  jnz     short loc_18000DF24
0x18000dec8  mov     rax, cs:g_pfnResultLoggingCallback
0x18000decf  test    rax, rax
0x18000ded2  jz      short loc_18000DEF5
0x18000ded4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18000dedb  jnz     short loc_18000DEF5
0x18000dedd  mov     r8d, 800h
0x18000dee3  lea     rdx, [rbp+1410h+OutputString]
0x18000deea  lea     rcx, [rsp+1510h+var_14E0]
0x18000deef  call    cs:__guard_dispatch_icall_fptr
0x18000def5  cmp     [rbp+1410h+OutputString], 0
0x18000defd  jnz     short loc_18000DF15
0x18000deff  lea     r8, [rsp+1510h+var_14E0]; unsigned __int64
0x18000df04  mov     edx, 800h; wchar_t *
0x18000df09  lea     rcx, [rbp+1410h+OutputString]; Buffer
0x18000df10  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000df15  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x18000df1c  call    cs:__imp_OutputDebugStringW
0x18000df22  jmp     short loc_18000DF49
0x18000df24  mov     rax, cs:g_pfnResultLoggingCallback
0x18000df2b  test    rax, rax
0x18000df2e  jz      short loc_18000DF49
0x18000df30  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18000df37  jnz     short loc_18000DF49
0x18000df39  xor     r8d, r8d
0x18000df3c  xor     edx, edx
0x18000df3e  lea     rcx, [rsp+1510h+var_14E0]
0x18000df43  call    cs:__guard_dispatch_icall_fptr
0x18000df49  test    byte ptr [rsp+1510h+var_14E0+4], 4
0x18000df4e  jnz     short loc_18000DF59
0x18000df50  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x18000df57  jz      short loc_18000DF6C
0x18000df59  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000df60  test    rax, rax
0x18000df63  jz      short loc_18000DF6C
0x18000df65  call    cs:__guard_dispatch_icall_fptr
0x18000df6b  nop
0x18000df6c  lea     rcx, [rsp+1510h+var_14E0]; this
0x18000df71  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
