# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140001d70`
- end: `0x140001fd7`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140001b24`

## callees

- `0x14000187f`
- `0x140001d70`
- `0x140002de4`
- `0x14000357c`
- `0x140003ca0`
- `0x140004850`
- `0x140004c30`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140001e11`
- `KERNEL32!GetCurrentThreadId` at `0x140001e11`
- `KERNEL32!IsDebuggerPresent` at `0x140001f1b`
- `KERNEL32!IsDebuggerPresent` at `0x140001f1b`
- `KERNEL32!OutputDebugStringW` at `0x140001fa5`
- `KERNEL32!OutputDebugStringW` at `0x140001fa5`

## string_xrefs

- `0x140001e26`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edi
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  __int64 v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
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
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v21, v10);
  v18 = a7[2] == 1;
  v12 = v11;
  v19 = 3;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
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
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
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
0x140001d70  mov     [rsp-8+arg_10], rbx
0x140001d75  mov     [rsp-8+arg_18], rsi
0x140001d7a  push    rbp
0x140001d7b  push    rdi
0x140001d7c  push    r12
0x140001d7e  push    r14
0x140001d80  push    r15
0x140001d82  lea     rbp, [rsp-13C0h]
0x140001d8a  mov     eax, 14C0h
0x140001d8f  call    _alloca_probe
0x140001d94  sub     rsp, rax
0x140001d97  mov     rsi, [rbp+13E0h+arg_28]
0x140001d9e  mov     r14d, edx
0x140001da1  mov     r15, rcx
0x140001da4  xor     edx, edx; Val
0x140001da6  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x140001dab  mov     r8d, 98h; Size
0x140001db1  call    memset_0
0x140001db6  mov     rbx, [rbp+13E0h+arg_30]
0x140001dbd  xor     r12d, r12d
0x140001dc0  mov     [rbp+13E0h+OutputString], r12w
0x140001dc8  mov     [rbp+13E0h+var_1420], r12b
0x140001dcc  mov     ecx, [rbx]; this
0x140001dce  mov     eax, [rbx+4]
0x140001dd1  mov     [rsp+14E0h+var_14B8], ecx
0x140001dd5  mov     [rsp+14E0h+var_14B4], eax
0x140001dd9  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140001dde  cmp     dword ptr [rbx+8], 1
0x140001de2  mov     edi, eax
0x140001de4  lea     eax, [r12+8]
0x140001de9  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x140001df1  mov     ecx, r12d
0x140001df4  cmovz   ecx, eax
0x140001df7  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x140001dfb  lea     ecx, [rax-7]
0x140001dfe  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140001e06  inc     ecx
0x140001e08  mov     [rsp+14E0h+var_14A8], r12
0x140001e0d  mov     [rsp+14E0h+var_14B0], ecx
0x140001e11  call    cs:__imp_GetCurrentThreadId
0x140001e17  xorps   xmm0, xmm0
0x140001e1a  mov     [rsp+14E0h+var_1480], r14d
0x140001e1f  mov     [rsp+14E0h+var_14A0], eax
0x140001e23  xorps   xmm1, xmm1
0x140001e26  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140001e2d  mov     [rsp+14E0h+var_147C], edi
0x140001e31  mov     [rsp+14E0h+var_1488], rax
0x140001e36  xor     eax, eax
0x140001e38  mov     [rbp+13E0h+var_1448], rax
0x140001e3c  mov     [rbp+13E0h+var_1460], rax
0x140001e40  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140001e47  mov     [rsp+14E0h+var_1498], r12
0x140001e4c  mov     [rsp+14E0h+var_1490], r12
0x140001e51  mov     [rbp+13E0h+var_1438], rsi
0x140001e55  mov     [rbp+13E0h+var_1430], r15
0x140001e59  mov     [rsp+14E0h+var_1478], r12
0x140001e5e  movups  [rbp+13E0h+var_1458], xmm0
0x140001e62  movups  [rsp+14E0h+var_1470], xmm1
0x140001e67  test    rax, rax
0x140001e6a  jz      short loc_140001E77
0x140001e6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e71  mov     [rbp+13E0h+var_1440], rax
0x140001e75  jmp     short loc_140001E7B
0x140001e77  mov     [rbp+13E0h+var_1440], r12
0x140001e7b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140001e82  test    rax, rax
0x140001e85  jz      short loc_140001E91
0x140001e87  lea     rcx, [rsp+14E0h+var_14C0]
0x140001e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001e91  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140001e98  test    rax, rax
0x140001e9b  jz      short loc_140001EB1
0x140001e9d  mov     r8d, 400h
0x140001ea3  lea     rdx, [rbp+13E0h+var_1420]
0x140001ea7  lea     rcx, [rsp+14E0h+var_14C0]
0x140001eac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001eb1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140001eb8  test    rax, rax
0x140001ebb  jz      short loc_140001EC7
0x140001ebd  lea     rcx, [rsp+14E0h+var_14C0]
0x140001ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001ec7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140001ece  test    rax, rax
0x140001ed1  jz      short loc_140001EE4
0x140001ed3  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x140001ed8  jnz     short loc_140001EE4
0x140001eda  lea     rcx, [rsp+14E0h+var_14C0]
0x140001edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001ee4  cmp     [rsp+14E0h+var_14B8], r12d
0x140001ee9  jl      short loc_140001EFD
0x140001eeb  mov     ecx, 8000FFFFh; this
0x140001ef0  mov     [rsp+14E0h+var_14B8], ecx
0x140001ef4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140001ef9  mov     [rsp+14E0h+var_14B4], eax
0x140001efd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140001f04  jnz     short loc_140001F25
0x140001f06  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140001f0d  test    rax, rax
0x140001f10  jz      short loc_140001F1B
0x140001f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001f17  test    al, al
0x140001f19  jmp     short loc_140001F23
0x140001f1b  call    cs:__imp_IsDebuggerPresent
0x140001f21  test    eax, eax
0x140001f23  jz      short loc_140001F2C
0x140001f25  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x140001f2a  jz      short loc_140001F52
0x140001f2c  mov     rax, cs:g_pfnResultLoggingCallback
0x140001f33  test    rax, rax
0x140001f36  jz      short loc_140001FAB
0x140001f38  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140001f3f  jnz     short loc_140001FAB
0x140001f41  xor     r8d, r8d
0x140001f44  lea     rcx, [rsp+14E0h+var_14C0]
0x140001f49  xor     edx, edx
0x140001f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001f50  jmp     short loc_140001FAB
0x140001f52  mov     rax, cs:g_pfnResultLoggingCallback
0x140001f59  mov     ebx, 800h
0x140001f5e  test    rax, rax
0x140001f61  jz      short loc_140001F80
0x140001f63  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140001f6a  jnz     short loc_140001F80
0x140001f6c  mov     r8d, ebx
0x140001f6f  lea     rdx, [rbp+13E0h+OutputString]
0x140001f76  lea     rcx, [rsp+14E0h+var_14C0]
0x140001f7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001f80  cmp     [rbp+13E0h+OutputString], r12w
0x140001f88  jnz     short loc_140001F9E
0x140001f8a  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x140001f8f  mov     rdx, rbx; unsigned __int16 *
0x140001f92  lea     rcx, [rbp+13E0h+OutputString]; this
0x140001f99  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140001f9e  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x140001fa5  call    cs:__imp_OutputDebugStringW
0x140001fab  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x140001fb0  jnz     short loc_140001FBB
0x140001fb2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140001fb9  jz      short loc_140001FCC
0x140001fbb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140001fc2  test    rax, rax
0x140001fc5  jz      short loc_140001FCC
0x140001fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140001fcc  lea     rcx, [rsp+14E0h+var_14C0]; this
0x140001fd1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
