# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003e3c`
- end: `0x1400040ea`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `686`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400038f0`

## callees

- `0x140002a30`
- `0x14000369c`
- `0x140003e3c`
- `0x140005304`
- `0x1400062e0`
- `0x140007220`
- `0x1400073b0`
- `0x140011fc0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003f0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003f0a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004089`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004089`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003fff`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003fff`

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
0x140003e3c  push    rbp
0x140003e3e  push    rbx
0x140003e3f  push    rsi
0x140003e40  push    rdi
0x140003e41  push    r12
0x140003e43  push    r14
0x140003e45  push    r15
0x140003e47  lea     rbp, [rsp-13E0h]
0x140003e4f  mov     eax, 14E0h
0x140003e54  call    _alloca_probe
0x140003e59  sub     rsp, rax
0x140003e5c  mov     [rbp+1410h+var_1450], 0FFFFFFFFFFFFFFFEh
0x140003e64  mov     rax, cs:__security_cookie
0x140003e6b  xor     rax, rsp
0x140003e6e  mov     [rbp+1410h+var_40], rax
0x140003e75  mov     rsi, r8
0x140003e78  mov     edi, edx
0x140003e7a  mov     rbx, rcx
0x140003e7d  mov     r14, [rbp+1410h+arg_28]
0x140003e84  xor     edx, edx; Val
0x140003e86  mov     r8d, 98h; Size
0x140003e8c  lea     rcx, [rsp+1510h+var_14F0]; void *
0x140003e91  call    memset_0
0x140003e96  nop
0x140003e97  xor     r12d, r12d
0x140003e9a  mov     [rbp+1410h+OutputString], r12w
0x140003ea2  mov     [rbp+1410h+var_1440], r12b
0x140003ea6  mov     rdx, [rbp+1410h+arg_30]; int
0x140003ead  mov     ecx, [rdx]; this
0x140003eaf  mov     [rsp+1510h+var_14E8], ecx
0x140003eb3  mov     eax, [rdx+4]
0x140003eb6  mov     [rsp+1510h+var_14E4], eax
0x140003eba  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003ebf  mov     r15d, eax
0x140003ec2  mov     dword ptr [rsp+1510h+var_14F0], 1
0x140003eca  mov     ecx, r12d
0x140003ecd  lea     eax, [r12+8]
0x140003ed2  cmp     dword ptr [rdx+8], 1
0x140003ed6  cmovz   ecx, eax
0x140003ed9  mov     dword ptr [rsp+1510h+var_14F0+4], ecx
0x140003edd  lea     ecx, [rax-7]
0x140003ee0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003ee8  inc     ecx
0x140003eea  mov     [rsp+1510h+var_14E0], ecx
0x140003eee  mov     rcx, [rbp+1410h+arg_38]
0x140003ef5  test    rcx, rcx
0x140003ef8  jz      short loc_140003F05
0x140003efa  cmp     [rcx], r12w
0x140003efe  mov     [rsp+1510h+var_14D8], rcx
0x140003f03  jnz     short loc_140003F0A
0x140003f05  mov     [rsp+1510h+var_14D8], r12
0x140003f0a  call    cs:__imp_GetCurrentThreadId
0x140003f10  mov     [rsp+1510h+var_14D0], eax
0x140003f14  mov     [rsp+1510h+var_14B8], rsi
0x140003f19  mov     [rsp+1510h+var_14B0], edi
0x140003f1d  mov     [rsp+1510h+var_14AC], r15d
0x140003f22  mov     [rsp+1510h+var_14C8], r12
0x140003f27  mov     [rsp+1510h+var_14C0], r12
0x140003f2c  mov     [rbp+1410h+var_1468], r14
0x140003f30  mov     [rbp+1410h+var_1460], rbx
0x140003f34  mov     [rsp+1510h+var_14A8], r12
0x140003f39  xorps   xmm0, xmm0
0x140003f3c  xor     eax, eax
0x140003f3e  movups  [rbp+1410h+var_1488], xmm0
0x140003f42  mov     [rbp+1410h+var_1478], rax
0x140003f46  xorps   xmm1, xmm1
0x140003f49  movups  [rsp+1510h+var_14A0], xmm1
0x140003f4e  mov     [rbp+1410h+var_1490], rax
0x140003f52  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003f59  test    rax, rax
0x140003f5c  jz      short loc_140003F69
0x140003f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f63  mov     [rbp+1410h+var_1470], rax
0x140003f67  jmp     short loc_140003F6D
0x140003f69  mov     [rbp+1410h+var_1470], r12
0x140003f6d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003f74  test    rax, rax
0x140003f77  jz      short loc_140003F83
0x140003f79  lea     rcx, [rsp+1510h+var_14F0]
0x140003f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f83  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003f8a  test    rax, rax
0x140003f8d  jz      short loc_140003FA3
0x140003f8f  mov     r8d, 400h
0x140003f95  lea     rdx, [rbp+1410h+var_1440]
0x140003f99  lea     rcx, [rsp+1510h+var_14F0]
0x140003f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fa3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003faa  test    rax, rax
0x140003fad  jz      short loc_140003FB9
0x140003faf  lea     rcx, [rsp+1510h+var_14F0]
0x140003fb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fb9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003fc0  test    rax, rax
0x140003fc3  jz      short loc_140003FD6
0x140003fc5  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x140003fca  jnz     short loc_140003FD6
0x140003fcc  lea     rcx, [rsp+1510h+var_14F0]
0x140003fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003fd6  cmp     [rsp+1510h+var_14E8], r12d
0x140003fdb  jge     loc_1400040E4
0x140003fe1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140003fe8  jnz     short loc_140004009
0x140003fea  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003ff1  test    rax, rax
0x140003ff4  jz      short loc_140003FFF
0x140003ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ffb  test    al, al
0x140003ffd  jmp     short loc_140004007
0x140003fff  call    cs:__imp_IsDebuggerPresent
0x140004005  test    eax, eax
0x140004007  jz      short loc_140004010
0x140004009  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x14000400e  jz      short loc_140004036
0x140004010  mov     rax, cs:g_pfnResultLoggingCallback
0x140004017  test    rax, rax
0x14000401a  jz      short loc_14000408F
0x14000401c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140004023  jnz     short loc_14000408F
0x140004025  xor     r8d, r8d
0x140004028  xor     edx, edx
0x14000402a  lea     rcx, [rsp+1510h+var_14F0]
0x14000402f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004034  jmp     short loc_14000408F
0x140004036  mov     ebx, 800h
0x14000403b  mov     rax, cs:g_pfnResultLoggingCallback
0x140004042  test    rax, rax
0x140004045  jz      short loc_140004064
0x140004047  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000404e  jnz     short loc_140004064
0x140004050  mov     r8d, ebx
0x140004053  lea     rdx, [rbp+1410h+OutputString]
0x14000405a  lea     rcx, [rsp+1510h+var_14F0]
0x14000405f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004064  cmp     [rbp+1410h+OutputString], r12w
0x14000406c  jnz     short loc_140004082
0x14000406e  lea     r8, [rsp+1510h+var_14F0]; unsigned __int64
0x140004073  mov     rdx, rbx; unsigned __int16 *
0x140004076  lea     rcx, [rbp+1410h+OutputString]; this
0x14000407d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004082  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x140004089  call    cs:__imp_OutputDebugStringW
0x14000408f  test    byte ptr [rsp+1510h+var_14F0+4], 4
0x140004094  jnz     short loc_14000409F
0x140004096  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000409d  jz      short loc_1400040B1
0x14000409f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400040a6  test    rax, rax
0x1400040a9  jz      short loc_1400040B1
0x1400040ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400040b0  nop
0x1400040b1  test    byte ptr [rsp+1510h+var_14F0+4], 1
0x1400040b6  jnz     short loc_1400040D9
0x1400040b8  mov     rcx, [rbp+1410h+var_40]
0x1400040bf  xor     rcx, rsp; StackCookie
0x1400040c2  call    __security_check_cookie
0x1400040c7  add     rsp, 14E0h
0x1400040ce  pop     r15
0x1400040d0  pop     r14
0x1400040d2  pop     r12
0x1400040d4  pop     rdi
0x1400040d5  pop     rsi
0x1400040d6  pop     rbx
0x1400040d7  pop     rbp
0x1400040d8  retn
0x1400040d9  lea     rcx, [rsp+1510h+var_14F0]; this
0x1400040de  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400040e4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
