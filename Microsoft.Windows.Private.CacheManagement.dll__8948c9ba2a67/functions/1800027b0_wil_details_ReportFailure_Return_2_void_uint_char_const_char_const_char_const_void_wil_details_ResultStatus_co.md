# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800027b0`
- end: `0x180002a9c`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `748`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002aa0`

## callees

- `0x1800027b0`
- `0x180002ab0`
- `0x180002b20`
- `0x180002b50`
- `0x180002c80`
- `0x180002f90`
- `0x180003350`
- `0x1800181b0`
- `0x180018ce0`
- `0x18001cdf0`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180002a38`
- `KERNEL32!OutputDebugStringW` at `0x180002a38`
- `KERNEL32!GetCurrentThreadId` at `0x1800028a9`
- `KERNEL32!GetCurrentThreadId` at `0x1800028a9`
- `KERNEL32!IsDebuggerPresent` at `0x1800029a7`
- `KERNEL32!IsDebuggerPresent` at `0x1800029a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v12; // edx
  int IsDebuggerPresent; // ebx
  int v14; // edi
  int v15; // edx
  int v16; // edi
  int v17; // ecx
  bool v18; // zf
  const struct wil::FailureInfo *v19; // rdx
  wil::details::in1diag3 *v20; // rcx
  const struct wil::FailureInfo *v21; // r9
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

  v12 = a6;
  IsDebuggerPresent = 0;
  OutputString[0] = 0;
  v43[0] = 0;
  v14 = *a7;
  v25 = v14;
  v26 = a7[1];
  if ( v14 >= 0 )
  {
    v14 = -2147024228;
    LODWORD(v22) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v22);
    v25 = -2147024228;
    v26 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v15);
  }
  v16 = wil::details::RecordLog((wil::details *)(unsigned int)v14, v12);
  v23 = 2;
  v17 = 0;
  if ( a7[2] == 1 )
    v17 = 8;
  v24 = v17;
  v27 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v28 = a8, v18) )
    v28 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v16;
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
    ModuleName = wil::details::g_pfnGetModuleName(v20);
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v20);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v20)),
         IsDebuggerPresent))
    && (v24 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v23, v21);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v23, 0, 0);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v20);
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v19);
}

```

## disassembly

```asm
0x1800027b0  push    rbp
0x1800027b2  push    rbx
0x1800027b3  push    rsi
0x1800027b4  push    rdi
0x1800027b5  push    r12
0x1800027b7  push    r13
0x1800027b9  push    r14
0x1800027bb  push    r15
0x1800027bd  lea     rbp, [rsp-1408h]
0x1800027c5  mov     eax, 1508h
0x1800027ca  call    _alloca_probe
0x1800027cf  sub     rsp, rax
0x1800027d2  mov     rax, cs:__security_cookie
0x1800027d9  xor     rax, rsp
0x1800027dc  mov     [rbp+1440h+var_50], rax
0x1800027e3  mov     r13, r9
0x1800027e6  mov     r12, r8
0x1800027e9  mov     r15d, edx
0x1800027ec  mov     r14, rcx
0x1800027ef  mov     rcx, [rbp+1440h+arg_20]
0x1800027f6  mov     [rsp+1540h+var_1500], rcx
0x1800027fb  mov     rdx, [rbp+1440h+arg_28]
0x180002802  mov     [rsp+1540h+var_14F8], rdx
0x180002807  xor     ebx, ebx
0x180002809  mov     [rbp+1440h+OutputString], bx
0x180002810  mov     [rbp+1440h+var_1450], bl
0x180002813  mov     rsi, [rbp+1440h+arg_30]
0x18000281a  mov     edi, [rsi]
0x18000281c  mov     [rsp+1540h+var_14E8], edi
0x180002820  mov     eax, [rsi+4]
0x180002823  mov     [rsp+1540h+var_14E4], eax
0x180002827  test    edi, edi
0x180002829  js      short loc_180002858
0x18000282b  mov     edi, 8007029Ch
0x180002830  mov     dword ptr [rsp+1540h+var_1510], edi; wil::details *
0x180002834  mov     [rsp+1540h+var_1518], rdx; __int64
0x180002839  mov     [rsp+1540h+var_1520], rcx; __int64
0x18000283e  mov     edx, r15d; int
0x180002841  mov     rcx, r14; int
0x180002844  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x180002849  mov     [rsp+1540h+var_14E8], edi
0x18000284d  mov     ecx, edi; this
0x18000284f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002854  mov     [rsp+1540h+var_14E4], eax
0x180002858  mov     ecx, edi; this
0x18000285a  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000285f  mov     edi, eax
0x180002861  mov     dword ptr [rsp+1540h+var_14F0], 2
0x180002869  mov     ecx, ebx
0x18000286b  mov     eax, 8
0x180002870  cmp     dword ptr [rsi+8], 1
0x180002874  cmovz   ecx, eax
0x180002877  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x18000287b  mov     ecx, 1
0x180002880  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180002888  inc     ecx
0x18000288a  mov     [rsp+1540h+var_14E0], ecx
0x18000288e  mov     rcx, [rbp+1440h+arg_38]
0x180002895  test    rcx, rcx
0x180002898  jz      short loc_1800028A4
0x18000289a  cmp     [rcx], bx
0x18000289d  mov     [rsp+1540h+var_14D8], rcx
0x1800028a2  jnz     short loc_1800028A9
0x1800028a4  mov     [rsp+1540h+var_14D8], rbx
0x1800028a9  call    cs:__imp_GetCurrentThreadId
0x1800028af  mov     [rsp+1540h+var_14D0], eax
0x1800028b3  mov     [rbp+1440h+var_14B8], r12
0x1800028b7  mov     [rbp+1440h+var_14B0], r15d
0x1800028bb  mov     [rbp+1440h+var_14AC], edi
0x1800028be  mov     rax, [rsp+1540h+var_1500]
0x1800028c3  mov     [rsp+1540h+var_14C8], rax
0x1800028c8  mov     [rbp+1440h+var_14C0], r13
0x1800028cc  mov     rax, [rsp+1540h+var_14F8]
0x1800028d1  mov     [rbp+1440h+var_1468], rax
0x1800028d5  mov     [rbp+1440h+var_1460], r14
0x1800028d9  mov     [rbp+1440h+var_14A8], rbx
0x1800028dd  xorps   xmm0, xmm0
0x1800028e0  xor     eax, eax
0x1800028e2  movups  [rbp+1440h+var_1488], xmm0
0x1800028e6  mov     [rbp+1440h+var_1478], rax
0x1800028ea  xorps   xmm1, xmm1
0x1800028ed  movups  [rbp+1440h+var_14A0], xmm1
0x1800028f1  mov     [rbp+1440h+var_1490], rax
0x1800028f5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800028fc  test    rax, rax
0x1800028ff  jz      short loc_18000290D
0x180002901  call    cs:__guard_dispatch_icall_fptr
0x180002907  mov     [rbp+1440h+var_1470], rax
0x18000290b  jmp     short loc_180002911
0x18000290d  mov     [rbp+1440h+var_1470], rbx
0x180002911  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002918  test    rax, rax
0x18000291b  jz      short loc_180002928
0x18000291d  lea     rcx, [rsp+1540h+var_14F0]
0x180002922  call    cs:__guard_dispatch_icall_fptr
0x180002928  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000292f  test    rax, rax
0x180002932  jz      short loc_180002949
0x180002934  mov     r8d, 400h
0x18000293a  lea     rdx, [rbp+1440h+var_1450]
0x18000293e  lea     rcx, [rsp+1540h+var_14F0]
0x180002943  call    cs:__guard_dispatch_icall_fptr
0x180002949  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002950  test    rax, rax
0x180002953  jz      short loc_180002960
0x180002955  lea     rcx, [rsp+1540h+var_14F0]
0x18000295a  call    cs:__guard_dispatch_icall_fptr
0x180002960  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002967  test    rax, rax
0x18000296a  jz      short loc_18000297E
0x18000296c  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180002971  jnz     short loc_18000297E
0x180002973  lea     rcx, [rsp+1540h+var_14F0]
0x180002978  call    cs:__guard_dispatch_icall_fptr
0x18000297e  cmp     [rsp+1540h+var_14E8], ebx
0x180002982  jge     loc_180002A96
0x180002988  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, bl; bool wil::g_fIsDebuggerPresent
0x18000298e  jnz     short loc_1800029B6
0x180002990  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002997  test    rax, rax
0x18000299a  jz      short loc_1800029A7
0x18000299c  call    cs:__guard_dispatch_icall_fptr
0x1800029a2  movzx   ebx, al
0x1800029a5  jmp     short loc_1800029B2
0x1800029a7  call    cs:__imp_IsDebuggerPresent
0x1800029ad  test    eax, eax
0x1800029af  setnz   bl
0x1800029b2  test    ebx, ebx
0x1800029b4  jz      short loc_1800029BD
0x1800029b6  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x1800029bb  jz      short loc_1800029E4
0x1800029bd  mov     rax, cs:g_pfnResultLoggingCallback
0x1800029c4  test    rax, rax
0x1800029c7  jz      short loc_180002A3E
0x1800029c9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1800029d0  jnz     short loc_180002A3E
0x1800029d2  xor     r8d, r8d
0x1800029d5  xor     edx, edx
0x1800029d7  lea     rcx, [rsp+1540h+var_14F0]
0x1800029dc  call    cs:__guard_dispatch_icall_fptr
0x1800029e2  jmp     short loc_180002A3E
0x1800029e4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800029eb  test    rax, rax
0x1800029ee  jz      short loc_180002A11
0x1800029f0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1800029f7  jnz     short loc_180002A11
0x1800029f9  mov     r8d, 800h
0x1800029ff  lea     rdx, [rbp+1440h+OutputString]
0x180002a06  lea     rcx, [rsp+1540h+var_14F0]
0x180002a0b  call    cs:__guard_dispatch_icall_fptr
0x180002a11  cmp     [rbp+1440h+OutputString], 0
0x180002a19  jnz     short loc_180002A31
0x180002a1b  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x180002a20  mov     edx, 800h; wchar_t *
0x180002a25  lea     rcx, [rbp+1440h+OutputString]; this
0x180002a2c  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180002a31  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x180002a38  call    cs:__imp_OutputDebugStringW
0x180002a3e  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x180002a43  jnz     short loc_180002A4E
0x180002a45  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x180002a4c  jz      short loc_180002A61
0x180002a4e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002a55  test    rax, rax
0x180002a58  jz      short loc_180002A61
0x180002a5a  call    cs:__guard_dispatch_icall_fptr
0x180002a60  nop
0x180002a61  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x180002a66  jnz     short loc_180002A8B
0x180002a68  mov     rcx, [rbp+1440h+var_50]
0x180002a6f  xor     rcx, rsp; StackCookie
0x180002a72  call    __security_check_cookie
0x180002a77  add     rsp, 1508h
0x180002a7e  pop     r15
0x180002a80  pop     r14
0x180002a82  pop     r13
0x180002a84  pop     r12
0x180002a86  pop     rdi
0x180002a87  pop     rsi
0x180002a88  pop     rbx
0x180002a89  pop     rbp
0x180002a8a  retn
0x180002a8b  lea     rcx, [rsp+1540h+var_14F0]; this
0x180002a90  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002a96  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
