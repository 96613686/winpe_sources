# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140009eec`
- end: `0x14000a1ec`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `768`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x14000959c`

## callees

- `0x140008660`
- `0x1400090ec`
- `0x1400098f8`
- `0x140009eec`
- `0x14000b4c4`
- `0x14000bc6c`
- `0x14000c0e4`
- `0x14000d200`
- `0x14000d2dc`
- `0x1400167a0`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a00d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a00d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000a189`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000a189`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000a100`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000a100`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int v14; // edx
  int v15; // ebx
  int v16; // edx
  int v17; // ebx
  const struct wil::FailureInfo *v18; // rdx
  wil::details::in1diag3 *v19; // rcx
  const struct wil::FailureInfo *v20; // r9
  bool v21; // zf
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

  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v15 = *a7;
  v25 = v15;
  v26 = a7[1];
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v22) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v22);
    v25 = -2147024228;
    v26 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v16);
  }
  v17 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  v23 = 2;
  v24 = a10;
  if ( a7[2] == 1 )
    v24 = a10 | 8;
  v27 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v21 = *a8 == 0, v28 = a8, v21) )
    v28 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v17;
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
    ModuleName = wil::details::g_pfnGetModuleName(v19);
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v21 = !IsDebuggerPresent())
      : (v21 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v19) == 0),
        v21)
    || (v24 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v23, v20);
    OutputDebugStringW(OutputString);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v19);
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v18);
}

```

## disassembly

```asm
0x140009eec  push    rbp
0x140009eee  push    rbx
0x140009eef  push    rsi
0x140009ef0  push    rdi
0x140009ef1  push    r12
0x140009ef3  push    r13
0x140009ef5  push    r14
0x140009ef7  push    r15
0x140009ef9  lea     rbp, [rsp-1408h]
0x140009f01  mov     eax, 1508h
0x140009f06  call    _alloca_probe
0x140009f0b  sub     rsp, rax
0x140009f0e  mov     rax, cs:__security_cookie
0x140009f15  xor     rax, rsp
0x140009f18  mov     [rbp+1440h+var_50], rax
0x140009f1f  mov     r12, r9
0x140009f22  mov     r15, r8
0x140009f25  mov     r14d, edx
0x140009f28  mov     rsi, rcx
0x140009f2b  mov     r13, [rbp+1440h+arg_20]
0x140009f32  mov     rax, [rbp+1440h+arg_28]
0x140009f39  mov     [rsp+1540h+var_1500], rax
0x140009f3e  xor     edx, edx; Val
0x140009f40  mov     r8d, 98h; Size
0x140009f46  lea     rcx, [rsp+1540h+var_14F0]; void *
0x140009f4b  call    memset_0
0x140009f50  nop
0x140009f51  xor     eax, eax
0x140009f53  mov     [rbp+1440h+OutputString], ax
0x140009f5a  mov     [rbp+1440h+var_1450], al
0x140009f5d  mov     rdi, [rbp+1440h+arg_30]
0x140009f64  mov     ebx, [rdi]
0x140009f66  mov     [rsp+1540h+var_14E8], ebx
0x140009f6a  mov     eax, [rdi+4]
0x140009f6d  mov     [rsp+1540h+var_14E4], eax
0x140009f71  test    ebx, ebx
0x140009f73  js      short loc_140009FB5
0x140009f75  mov     [rsp+1540h+var_1508], 0
0x140009f7d  mov     ebx, 8007029Ch
0x140009f82  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x140009f86  mov     rax, [rsp+1540h+var_1500]
0x140009f8b  mov     [rsp+1540h+var_1518], rax; __int64
0x140009f90  mov     [rsp+1540h+var_1520], r13; __int64
0x140009f95  mov     r9, r12; int
0x140009f98  mov     r8, r15; int
0x140009f9b  mov     edx, r14d; int
0x140009f9e  mov     rcx, rsi; int
0x140009fa1  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140009fa6  mov     [rsp+1540h+var_14E8], ebx
0x140009faa  mov     ecx, ebx; this
0x140009fac  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140009fb1  mov     [rsp+1540h+var_14E4], eax
0x140009fb5  mov     ecx, ebx; this
0x140009fb7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140009fbc  mov     ebx, eax
0x140009fbe  mov     dword ptr [rsp+1540h+var_14F0], 2
0x140009fc6  mov     ecx, [rbp+1440h+arg_48]
0x140009fcc  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x140009fd0  cmp     dword ptr [rdi+8], 1
0x140009fd4  jnz     short loc_140009FDD
0x140009fd6  or      ecx, 8
0x140009fd9  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x140009fdd  mov     ecx, 1
0x140009fe2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140009fea  inc     ecx
0x140009fec  mov     [rsp+1540h+var_14E0], ecx
0x140009ff0  mov     rax, [rbp+1440h+arg_38]
0x140009ff7  xor     edi, edi
0x140009ff9  test    rax, rax
0x140009ffc  jz      short loc_14000A008
0x140009ffe  cmp     [rax], di
0x14000a001  mov     [rsp+1540h+var_14D8], rax
0x14000a006  jnz     short loc_14000A00D
0x14000a008  mov     [rsp+1540h+var_14D8], rdi
0x14000a00d  call    cs:__imp_GetCurrentThreadId
0x14000a013  mov     [rsp+1540h+var_14D0], eax
0x14000a017  mov     [rbp+1440h+var_14B8], r15
0x14000a01b  mov     [rbp+1440h+var_14B0], r14d
0x14000a01f  mov     [rbp+1440h+var_14AC], ebx
0x14000a022  mov     [rsp+1540h+var_14C8], r13
0x14000a027  mov     [rbp+1440h+var_14C0], r12
0x14000a02b  mov     rax, [rsp+1540h+var_1500]
0x14000a030  mov     [rbp+1440h+var_1468], rax
0x14000a034  mov     [rbp+1440h+var_1460], rsi
0x14000a038  mov     [rbp+1440h+var_14A8], rdi
0x14000a03c  xorps   xmm0, xmm0
0x14000a03f  xor     eax, eax
0x14000a041  movups  [rbp+1440h+var_1488], xmm0
0x14000a045  mov     [rbp+1440h+var_1478], rax
0x14000a049  xorps   xmm1, xmm1
0x14000a04c  movups  [rbp+1440h+var_14A0], xmm1
0x14000a050  mov     [rbp+1440h+var_1490], rax
0x14000a054  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000a05b  test    rax, rax
0x14000a05e  jz      short loc_14000A06B
0x14000a060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a065  mov     [rbp+1440h+var_1470], rax
0x14000a069  jmp     short loc_14000A06F
0x14000a06b  mov     [rbp+1440h+var_1470], rdi
0x14000a06f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000a076  test    rax, rax
0x14000a079  jz      short loc_14000A085
0x14000a07b  lea     rcx, [rsp+1540h+var_14F0]
0x14000a080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a085  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000a08c  test    rax, rax
0x14000a08f  jz      short loc_14000A0A5
0x14000a091  mov     r8d, 400h
0x14000a097  lea     rdx, [rbp+1440h+var_1450]
0x14000a09b  lea     rcx, [rsp+1540h+var_14F0]
0x14000a0a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0a5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a0ac  test    rax, rax
0x14000a0af  jz      short loc_14000A0BB
0x14000a0b1  lea     rcx, [rsp+1540h+var_14F0]
0x14000a0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0bb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a0c2  test    rax, rax
0x14000a0c5  jz      short loc_14000A0D8
0x14000a0c7  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x14000a0cc  jnz     short loc_14000A0D8
0x14000a0ce  lea     rcx, [rsp+1540h+var_14F0]
0x14000a0d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0d8  cmp     [rsp+1540h+var_14E8], edi
0x14000a0dc  jge     loc_14000A1E6
0x14000a0e2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000a0e9  jnz     short loc_14000A10A
0x14000a0eb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000a0f2  test    rax, rax
0x14000a0f5  jz      short loc_14000A100
0x14000a0f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a0fc  test    al, al
0x14000a0fe  jmp     short loc_14000A108
0x14000a100  call    cs:__imp_IsDebuggerPresent
0x14000a106  test    eax, eax
0x14000a108  jz      short loc_14000A111
0x14000a10a  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x14000a10f  jz      short loc_14000A137
0x14000a111  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a118  test    rax, rax
0x14000a11b  jz      short loc_14000A18F
0x14000a11d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000a124  jnz     short loc_14000A18F
0x14000a126  xor     r8d, r8d
0x14000a129  xor     edx, edx
0x14000a12b  lea     rcx, [rsp+1540h+var_14F0]
0x14000a130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a135  jmp     short loc_14000A18F
0x14000a137  mov     ebx, 800h
0x14000a13c  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a143  test    rax, rax
0x14000a146  jz      short loc_14000A165
0x14000a148  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000a14f  jnz     short loc_14000A165
0x14000a151  mov     r8d, ebx
0x14000a154  lea     rdx, [rbp+1440h+OutputString]
0x14000a15b  lea     rcx, [rsp+1540h+var_14F0]
0x14000a160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a165  cmp     [rbp+1440h+OutputString], di
0x14000a16c  jnz     short loc_14000A182
0x14000a16e  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x14000a173  mov     rdx, rbx; unsigned __int16 *
0x14000a176  lea     rcx, [rbp+1440h+OutputString]; this
0x14000a17d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000a182  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x14000a189  call    cs:__imp_OutputDebugStringW
0x14000a18f  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x14000a194  jnz     short loc_14000A19F
0x14000a196  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000a19d  jz      short loc_14000A1B1
0x14000a19f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000a1a6  test    rax, rax
0x14000a1a9  jz      short loc_14000A1B1
0x14000a1ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a1b0  nop
0x14000a1b1  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x14000a1b6  jnz     short loc_14000A1DB
0x14000a1b8  mov     rcx, [rbp+1440h+var_50]
0x14000a1bf  xor     rcx, rsp; StackCookie
0x14000a1c2  call    __security_check_cookie
0x14000a1c7  add     rsp, 1508h
0x14000a1ce  pop     r15
0x14000a1d0  pop     r14
0x14000a1d2  pop     r13
0x14000a1d4  pop     r12
0x14000a1d6  pop     rdi
0x14000a1d7  pop     rsi
0x14000a1d8  pop     rbx
0x14000a1d9  pop     rbp
0x14000a1da  retn
0x14000a1db  lea     rcx, [rsp+1540h+var_14F0]; this
0x14000a1e0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000a1e6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
