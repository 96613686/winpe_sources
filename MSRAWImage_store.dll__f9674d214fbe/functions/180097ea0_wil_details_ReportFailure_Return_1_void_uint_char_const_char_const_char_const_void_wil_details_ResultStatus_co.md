# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180097ea0`
- end: `0x180098161`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180097958`

## callees

- `0x180002a00`
- `0x180095170`
- `0x180097ea0`
- `0x18009a62c`
- `0x18009d124`
- `0x18009e2d4`
- `0x18009e6c0`
- `0x1800b0b00`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097f6e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097f6e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180098069`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180098069`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800980f9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800980f9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        unsigned __int64 *a7,
        _WORD *a8)
{
  unsigned int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  unsigned __int64 v18[22]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v19[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v18[20] = -2;
  memset(v18, 0, 0x98u);
  OutputString[0] = 0;
  v19[0] = 0;
  v18[1] = *a7;
  v11 = wil::details::RecordReturn((wil::details *)LODWORD(v18[1]), (int)a7);
  LODWORD(v18[0]) = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  HIDWORD(v18[0]) = v12;
  LODWORD(v18[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v18[3] = (unsigned __int64)a8, v17) )
    v18[3] = 0;
  LODWORD(v18[4]) = GetCurrentThreadId();
  v18[7] = a3;
  v18[8] = __PAIR64__(v11, a2);
  v18[5] = 0;
  v18[6] = 0;
  v18[17] = a6;
  v18[18] = a1;
  memset(&v18[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v18[16] = wil::details::g_pfnGetModuleName(v15);
  else
    v18[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v18, v19, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v18);
  if ( wil::details::g_pfnOriginateCallback && (v18[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v18);
  if ( SLODWORD(v18[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v18[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v18, v14);
}

```

## disassembly

```asm
0x180097ea0  push    rbp
0x180097ea2  push    rbx
0x180097ea3  push    rsi
0x180097ea4  push    rdi
0x180097ea5  push    r12
0x180097ea7  push    r14
0x180097ea9  push    r15
0x180097eab  lea     rbp, [rsp-13E0h]
0x180097eb3  mov     eax, 14E0h
0x180097eb8  call    _alloca_probe
0x180097ebd  sub     rsp, rax
0x180097ec0  mov     [rbp+1410h+var_1450], 0FFFFFFFFFFFFFFFEh
0x180097ec8  mov     rax, cs:__security_cookie
0x180097ecf  xor     rax, rsp
0x180097ed2  mov     [rbp+1410h+var_40], rax
0x180097ed9  mov     rsi, r8
0x180097edc  mov     edi, edx
0x180097ede  mov     rbx, rcx
0x180097ee1  mov     r14, [rbp+1410h+arg_28]
0x180097ee8  xor     edx, edx; Val
0x180097eea  mov     r8d, 98h; Size
0x180097ef0  lea     rcx, [rsp+1510h+var_14F0]; void *
0x180097ef5  call    memset
0x180097efa  nop
0x180097efb  xor     r12d, r12d
0x180097efe  mov     [rbp+1410h+OutputString], r12w
0x180097f06  mov     [rbp+1410h+var_1440], r12b
0x180097f0a  mov     rdx, [rbp+1410h+arg_30]; int
0x180097f11  mov     ecx, [rdx]; this
0x180097f13  mov     [rsp+1510h+var_14E8], ecx
0x180097f17  mov     eax, [rdx+4]
0x180097f1a  mov     [rsp+1510h+var_14E4], eax
0x180097f1e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180097f23  mov     r15d, eax
0x180097f26  mov     dword ptr [rsp+1510h+var_14F0], 1
0x180097f2e  mov     ecx, r12d
0x180097f31  lea     eax, [r12+8]
0x180097f36  cmp     dword ptr [rdx+8], 1
0x180097f3a  cmovz   ecx, eax
0x180097f3d  mov     dword ptr [rsp+1510h+var_14F0+4], ecx
0x180097f41  lea     ecx, [rax-7]
0x180097f44  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180097f4c  inc     ecx
0x180097f4e  mov     [rsp+1510h+var_14E0], ecx
0x180097f52  mov     rcx, [rbp+1410h+arg_38]
0x180097f59  test    rcx, rcx
0x180097f5c  jz      short loc_180097F69
0x180097f5e  cmp     [rcx], r12w
0x180097f62  mov     [rsp+1510h+var_14D8], rcx
0x180097f67  jnz     short loc_180097F6E
0x180097f69  mov     [rsp+1510h+var_14D8], r12
0x180097f6e  call    cs:__imp_GetCurrentThreadId
0x180097f75  nop     dword ptr [rax+rax+00h]
0x180097f7a  mov     [rsp+1510h+var_14D0], eax
0x180097f7e  mov     [rsp+1510h+var_14B8], rsi
0x180097f83  mov     [rsp+1510h+var_14B0], edi
0x180097f87  mov     [rsp+1510h+var_14AC], r15d
0x180097f8c  mov     [rsp+1510h+var_14C8], r12
0x180097f91  mov     [rsp+1510h+var_14C0], r12
0x180097f96  mov     [rbp+1410h+var_1468], r14
0x180097f9a  mov     [rbp+1410h+var_1460], rbx
0x180097f9e  mov     [rsp+1510h+var_14A8], r12
0x180097fa3  xorps   xmm0, xmm0
0x180097fa6  xor     eax, eax
0x180097fa8  movups  [rbp+1410h+var_1488], xmm0
0x180097fac  mov     [rbp+1410h+var_1478], rax
0x180097fb0  xorps   xmm1, xmm1
0x180097fb3  movups  [rsp+1510h+var_14A0], xmm1
0x180097fb8  mov     [rbp+1410h+var_1490], rax
0x180097fbc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180097fc3  test    rax, rax
0x180097fc6  jz      short loc_180097FD3
0x180097fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097fcd  mov     [rbp+1410h+var_1470], rax
0x180097fd1  jmp     short loc_180097FD7
0x180097fd3  mov     [rbp+1410h+var_1470], r12
0x180097fd7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180097fde  test    rax, rax
0x180097fe1  jz      short loc_180097FED
0x180097fe3  lea     rcx, [rsp+1510h+var_14F0]
0x180097fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097fed  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180097ff4  test    rax, rax
0x180097ff7  jz      short loc_18009800D
0x180097ff9  mov     r8d, 400h
0x180097fff  lea     rdx, [rbp+1410h+var_1440]
0x180098003  lea     rcx, [rsp+1510h+var_14F0]
0x180098008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009800d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180098014  test    rax, rax
0x180098017  jz      short loc_180098023
0x180098019  lea     rcx, [rsp+1510h+var_14F0]
0x18009801e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098023  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18009802a  test    rax, rax
0x18009802d  jz      short loc_180098040
0x18009802f  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x180098034  jnz     short loc_180098040
0x180098036  lea     rcx, [rsp+1510h+var_14F0]
0x18009803b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098040  cmp     [rsp+1510h+var_14E8], r12d
0x180098045  jge     loc_18009815B
0x18009804b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180098052  jnz     short loc_180098079
0x180098054  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18009805b  test    rax, rax
0x18009805e  jz      short loc_180098069
0x180098060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098065  test    al, al
0x180098067  jmp     short loc_180098077
0x180098069  call    cs:__imp_IsDebuggerPresent
0x180098070  nop     dword ptr [rax+rax+00h]
0x180098075  test    eax, eax
0x180098077  jz      short loc_180098080
0x180098079  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x18009807e  jz      short loc_1800980A6
0x180098080  mov     rax, cs:g_pfnResultLoggingCallback
0x180098087  test    rax, rax
0x18009808a  jz      short loc_180098105
0x18009808c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180098093  jnz     short loc_180098105
0x180098095  xor     r8d, r8d
0x180098098  xor     edx, edx
0x18009809a  lea     rcx, [rsp+1510h+var_14F0]
0x18009809f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800980a4  jmp     short loc_180098105
0x1800980a6  mov     ebx, 800h
0x1800980ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1800980b2  test    rax, rax
0x1800980b5  jz      short loc_1800980D4
0x1800980b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800980be  jnz     short loc_1800980D4
0x1800980c0  mov     r8d, ebx
0x1800980c3  lea     rdx, [rbp+1410h+OutputString]
0x1800980ca  lea     rcx, [rsp+1510h+var_14F0]
0x1800980cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800980d4  cmp     [rbp+1410h+OutputString], r12w
0x1800980dc  jnz     short loc_1800980F2
0x1800980de  lea     r8, [rsp+1510h+var_14F0]; unsigned __int64
0x1800980e3  mov     rdx, rbx; unsigned __int16 *
0x1800980e6  lea     rcx, [rbp+1410h+OutputString]; this
0x1800980ed  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800980f2  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x1800980f9  call    cs:__imp_OutputDebugStringW
0x180098100  nop     dword ptr [rax+rax+00h]
0x180098105  test    byte ptr [rsp+1510h+var_14F0+4], 4
0x18009810a  jnz     short loc_180098115
0x18009810c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180098113  jz      short loc_180098127
0x180098115  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18009811c  test    rax, rax
0x18009811f  jz      short loc_180098127
0x180098121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098126  nop
0x180098127  test    byte ptr [rsp+1510h+var_14F0+4], 1
0x18009812c  jnz     short loc_180098150
0x18009812e  mov     rcx, [rbp+1410h+var_40]
0x180098135  xor     rcx, rsp; StackCookie
0x180098138  call    __security_check_cookie
0x18009813d  add     rsp, 14E0h
0x180098144  pop     r15
0x180098146  pop     r14
0x180098148  pop     r12
0x18009814a  pop     rdi
0x18009814b  pop     rsi
0x18009814c  pop     rbx
0x18009814d  pop     rbp
0x18009814e  retn
0x180098150  lea     rcx, [rsp+1510h+var_14F0]; this
0x180098155  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18009815b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
