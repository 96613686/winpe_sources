# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002ce4`
- end: `0x180002f5d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002a64`

## callees

- `0x1800022ea`
- `0x180002ce4`
- `0x180004074`
- `0x180004800`
- `0x180004f60`
- `0x180005fe0`
- `0x180011d10`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d9d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002ea0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002ea0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002f2a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002f2a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v10; // edx
  int v11; // r15d
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  _WORD *v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v16 = *a8 == 0, v22 = a8, v16) )
    v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = 0;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0, v15);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048, v15);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180002ce4  mov     [rsp-8+arg_0], rbx
0x180002ce9  mov     [rsp-8+arg_18], rsi
0x180002cee  push    rbp
0x180002cef  push    rdi
0x180002cf0  push    r12
0x180002cf2  push    r14
0x180002cf4  push    r15
0x180002cf6  lea     rbp, [rsp-13C0h]
0x180002cfe  mov     eax, 14C0h
0x180002d03  call    _alloca_probe
0x180002d08  sub     rsp, rax
0x180002d0b  mov     rsi, r8
0x180002d0e  mov     edi, edx
0x180002d10  mov     r14, [rbp+13E0h+arg_28]
0x180002d17  xor     edx, edx; Val
0x180002d19  mov     r8d, 98h; Size
0x180002d1f  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180002d24  call    memset_0
0x180002d29  nop
0x180002d2a  xor     r12d, r12d
0x180002d2d  mov     [rbp+13E0h+OutputString], r12w
0x180002d35  mov     [rbp+13E0h+var_1420], r12b
0x180002d39  mov     rbx, [rbp+13E0h+arg_30]
0x180002d40  mov     ecx, [rbx]; this
0x180002d42  mov     [rsp+14E0h+var_14B8], ecx
0x180002d46  mov     eax, [rbx+4]
0x180002d49  mov     [rsp+14E0h+var_14B4], eax
0x180002d4d  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002d52  mov     r15d, eax
0x180002d55  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x180002d5d  mov     ecx, r12d
0x180002d60  lea     eax, [r12+8]
0x180002d65  cmp     dword ptr [rbx+8], 1
0x180002d69  cmovz   ecx, eax
0x180002d6c  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180002d70  lea     ecx, [rax-7]
0x180002d73  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002d7b  inc     ecx
0x180002d7d  mov     [rsp+14E0h+var_14B0], ecx
0x180002d81  mov     rcx, [rbp+13E0h+arg_38]
0x180002d88  test    rcx, rcx
0x180002d8b  jz      short loc_180002D98
0x180002d8d  cmp     [rcx], r12w
0x180002d91  mov     [rsp+14E0h+var_14A8], rcx
0x180002d96  jnz     short loc_180002D9D
0x180002d98  mov     [rsp+14E0h+var_14A8], r12
0x180002d9d  call    cs:__imp_GetCurrentThreadId
0x180002da3  mov     [rsp+14E0h+var_14A0], eax
0x180002da7  mov     [rsp+14E0h+var_1488], rsi
0x180002dac  mov     [rsp+14E0h+var_1480], edi
0x180002db0  mov     [rsp+14E0h+var_147C], r15d
0x180002db5  mov     [rsp+14E0h+var_1498], r12
0x180002dba  mov     [rsp+14E0h+var_1490], r12
0x180002dbf  mov     [rbp+13E0h+var_1438], r14
0x180002dc3  mov     [rbp+13E0h+var_1430], r12
0x180002dc7  mov     [rsp+14E0h+var_1478], r12
0x180002dcc  xorps   xmm0, xmm0
0x180002dcf  xor     eax, eax
0x180002dd1  movups  [rbp+13E0h+var_1458], xmm0
0x180002dd5  mov     [rbp+13E0h+var_1448], rax
0x180002dd9  xorps   xmm1, xmm1
0x180002ddc  movups  [rsp+14E0h+var_1470], xmm1
0x180002de1  mov     [rbp+13E0h+var_1460], rax
0x180002de5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002dec  test    rax, rax
0x180002def  jz      short loc_180002DFC
0x180002df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002df6  mov     [rbp+13E0h+var_1440], rax
0x180002dfa  jmp     short loc_180002E00
0x180002dfc  mov     [rbp+13E0h+var_1440], r12
0x180002e00  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002e07  test    rax, rax
0x180002e0a  jz      short loc_180002E16
0x180002e0c  lea     rcx, [rsp+14E0h+var_14C0]
0x180002e11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e16  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002e1d  test    rax, rax
0x180002e20  jz      short loc_180002E36
0x180002e22  mov     r8d, 400h
0x180002e28  lea     rdx, [rbp+13E0h+var_1420]
0x180002e2c  lea     rcx, [rsp+14E0h+var_14C0]
0x180002e31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e36  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002e3d  test    rax, rax
0x180002e40  jz      short loc_180002E4C
0x180002e42  lea     rcx, [rsp+14E0h+var_14C0]
0x180002e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e4c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002e53  test    rax, rax
0x180002e56  jz      short loc_180002E69
0x180002e58  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002e5d  jnz     short loc_180002E69
0x180002e5f  lea     rcx, [rsp+14E0h+var_14C0]
0x180002e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e69  cmp     [rsp+14E0h+var_14B8], r12d
0x180002e6e  jl      short loc_180002E82
0x180002e70  mov     ecx, 8000FFFFh; this
0x180002e75  mov     [rsp+14E0h+var_14B8], ecx
0x180002e79  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002e7e  mov     [rsp+14E0h+var_14B4], eax
0x180002e82  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002e89  jnz     short loc_180002EAA
0x180002e8b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002e92  test    rax, rax
0x180002e95  jz      short loc_180002EA0
0x180002e97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e9c  test    al, al
0x180002e9e  jmp     short loc_180002EA8
0x180002ea0  call    cs:__imp_IsDebuggerPresent
0x180002ea6  test    eax, eax
0x180002ea8  jz      short loc_180002EB1
0x180002eaa  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180002eaf  jz      short loc_180002ED7
0x180002eb1  mov     rax, cs:g_pfnResultLoggingCallback
0x180002eb8  test    rax, rax
0x180002ebb  jz      short loc_180002F30
0x180002ebd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002ec4  jnz     short loc_180002F30
0x180002ec6  xor     r8d, r8d
0x180002ec9  xor     edx, edx
0x180002ecb  lea     rcx, [rsp+14E0h+var_14C0]
0x180002ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ed5  jmp     short loc_180002F30
0x180002ed7  mov     ebx, 800h
0x180002edc  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ee3  test    rax, rax
0x180002ee6  jz      short loc_180002F05
0x180002ee8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002eef  jnz     short loc_180002F05
0x180002ef1  mov     r8d, ebx
0x180002ef4  lea     rdx, [rbp+13E0h+OutputString]
0x180002efb  lea     rcx, [rsp+14E0h+var_14C0]
0x180002f00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f05  cmp     [rbp+13E0h+OutputString], r12w
0x180002f0d  jnz     short loc_180002F23
0x180002f0f  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180002f14  mov     rdx, rbx; unsigned __int16 *
0x180002f17  lea     rcx, [rbp+13E0h+OutputString]; this
0x180002f1e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002f23  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180002f2a  call    cs:__imp_OutputDebugStringW
0x180002f30  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180002f35  jnz     short loc_180002F40
0x180002f37  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002f3e  jz      short loc_180002F52
0x180002f40  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002f47  test    rax, rax
0x180002f4a  jz      short loc_180002F52
0x180002f4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f51  nop
0x180002f52  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180002f57  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
