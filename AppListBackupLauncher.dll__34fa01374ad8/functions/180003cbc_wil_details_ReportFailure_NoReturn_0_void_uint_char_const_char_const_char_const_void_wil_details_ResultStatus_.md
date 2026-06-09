# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003cbc`
- end: `0x180003f6f`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `691`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x18000366c`

## callees

- `0x180002de0`
- `0x180003cbc`
- `0x18000860c`
- `0x18000a790`
- `0x18000d6c4`
- `0x18000de50`
- `0x18000e804`
- `0x180010290`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d65`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003e67`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003e67`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003f03`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003f03`

## string_xrefs

- `0x180003d6f`: `pcshell\shell\applistbackuplauncher\dll\applistbackuplauncher.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v9; // r15
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  char v17; // bl
  const struct wil::FailureInfo *v18; // rdx
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
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

  v9 = g_pfnThrowPlatformException != 0;
  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v21 = *a7;
  v22 = a7[1];
  v10 = wil::details::RecordException((wil::details *)(unsigned int)v21, (int)a7);
  v19 = 0;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v20 = v11;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v28 = "pcshell\\shell\\applistbackuplauncher\\dll\\applistbackuplauncher.cpp";
  v29 = a2;
  v30 = v10;
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
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && !v9 && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v17 = 1, (v20 & 2) != 0) )
  {
    v17 = 0;
  }
  if ( v9 || v17 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v15);
    if ( v17 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v13);
  if ( v9 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v19, OutputString);
  wil::ThrowResultException((wil *)&v19, v13);
  wil::details::WilFailFast((wil::details *)&v19, v18);
}

```

## disassembly

```asm
0x180003cbc  mov     [rsp-8+arg_10], rbx
0x180003cc1  mov     [rsp-8+arg_18], rsi
0x180003cc6  push    rbp
0x180003cc7  push    rdi
0x180003cc8  push    r12
0x180003cca  push    r14
0x180003ccc  push    r15
0x180003cce  lea     rbp, [rsp-13C0h]
0x180003cd6  mov     eax, 14C0h
0x180003cdb  call    _alloca_probe
0x180003ce0  sub     rsp, rax
0x180003ce3  mov     esi, edx
0x180003ce5  mov     r14, rcx
0x180003ce8  mov     rdi, [rbp+13E0h+arg_28]
0x180003cef  xor     r12d, r12d
0x180003cf2  cmp     cs:g_pfnThrowPlatformException, r12
0x180003cf9  setnz   r15b
0x180003cfd  xor     edx, edx; Val
0x180003cff  mov     r8d, 98h; Size
0x180003d05  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180003d0a  call    memset_0
0x180003d0f  nop
0x180003d10  mov     [rbp+13E0h+OutputString], r12w
0x180003d18  mov     [rbp+13E0h+var_1420], r12b
0x180003d1c  mov     rdx, qword ptr [rbp+13E0h+arg_30]; int
0x180003d23  mov     ecx, [rdx]; this
0x180003d25  mov     [rsp+14E0h+var_14B8], ecx
0x180003d29  mov     eax, [rdx+4]
0x180003d2c  mov     [rsp+14E0h+var_14B4], eax
0x180003d30  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180003d35  mov     ebx, eax
0x180003d37  mov     dword ptr [rsp+14E0h+var_14C0], r12d
0x180003d3c  mov     ecx, r12d
0x180003d3f  lea     eax, [r12+8]
0x180003d44  cmp     dword ptr [rdx+8], 1
0x180003d48  cmovz   ecx, eax
0x180003d4b  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180003d4f  lea     ecx, [rax-7]
0x180003d52  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003d5a  inc     ecx
0x180003d5c  mov     [rsp+14E0h+var_14B0], ecx
0x180003d60  mov     [rsp+14E0h+var_14A8], r12
0x180003d65  call    cs:__imp_GetCurrentThreadId
0x180003d6b  mov     [rsp+14E0h+var_14A0], eax
0x180003d6f  lea     rax, aPcshellShellAp; "pcshell\\shell\\applistbackuplauncher\\"...
0x180003d76  mov     [rsp+14E0h+var_1488], rax
0x180003d7b  mov     [rsp+14E0h+var_1480], esi
0x180003d7f  mov     [rsp+14E0h+var_147C], ebx
0x180003d83  mov     [rsp+14E0h+var_1498], r12
0x180003d88  mov     [rsp+14E0h+var_1490], r12
0x180003d8d  mov     [rbp+13E0h+var_1438], rdi
0x180003d91  mov     [rbp+13E0h+var_1430], r14
0x180003d95  mov     [rsp+14E0h+var_1478], r12
0x180003d9a  xorps   xmm0, xmm0
0x180003d9d  xor     eax, eax
0x180003d9f  movups  [rbp+13E0h+var_1458], xmm0
0x180003da3  mov     [rbp+13E0h+var_1448], rax
0x180003da7  xorps   xmm1, xmm1
0x180003daa  movups  [rsp+14E0h+var_1470], xmm1
0x180003daf  mov     [rbp+13E0h+var_1460], rax
0x180003db3  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003dba  test    rax, rax
0x180003dbd  jz      short loc_180003DCA
0x180003dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dc4  mov     [rbp+13E0h+var_1440], rax
0x180003dc8  jmp     short loc_180003DCE
0x180003dca  mov     [rbp+13E0h+var_1440], r12
0x180003dce  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003dd5  test    rax, rax
0x180003dd8  jz      short loc_180003DE4
0x180003dda  lea     rcx, [rsp+14E0h+var_14C0]
0x180003ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003de4  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003deb  test    rax, rax
0x180003dee  jz      short loc_180003E04
0x180003df0  mov     r8d, 400h
0x180003df6  lea     rdx, [rbp+13E0h+var_1420]
0x180003dfa  lea     rcx, [rsp+14E0h+var_14C0]
0x180003dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e04  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003e0b  test    rax, rax
0x180003e0e  jz      short loc_180003E1A
0x180003e10  lea     rcx, [rsp+14E0h+var_14C0]
0x180003e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e1a  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003e21  test    rax, rax
0x180003e24  jz      short loc_180003E3C
0x180003e26  test    r15b, r15b
0x180003e29  jnz     short loc_180003E3C
0x180003e2b  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180003e30  jnz     short loc_180003E3C
0x180003e32  lea     rcx, [rsp+14E0h+var_14C0]
0x180003e37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e3c  cmp     [rsp+14E0h+var_14B8], r12d
0x180003e41  jl      short loc_180003E49
0x180003e43  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003e49  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003e50  jnz     short loc_180003E71
0x180003e52  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003e59  test    rax, rax
0x180003e5c  jz      short loc_180003E67
0x180003e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e63  test    al, al
0x180003e65  jmp     short loc_180003E6F
0x180003e67  call    cs:__imp_IsDebuggerPresent
0x180003e6d  test    eax, eax
0x180003e6f  jz      short loc_180003E7A
0x180003e71  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180003e76  mov     bl, 1
0x180003e78  jz      short loc_180003E7D
0x180003e7a  mov     bl, r12b
0x180003e7d  test    r15b, r15b
0x180003e80  jnz     short loc_180003EAC
0x180003e82  test    bl, bl
0x180003e84  jnz     short loc_180003EAC
0x180003e86  mov     rax, cs:g_pfnResultLoggingCallback
0x180003e8d  test    rax, rax
0x180003e90  jz      short loc_180003F09
0x180003e92  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003e99  jnz     short loc_180003F09
0x180003e9b  xor     r8d, r8d
0x180003e9e  xor     edx, edx
0x180003ea0  lea     rcx, [rsp+14E0h+var_14C0]
0x180003ea5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eaa  jmp     short loc_180003F09
0x180003eac  mov     edi, 800h
0x180003eb1  mov     rax, cs:g_pfnResultLoggingCallback
0x180003eb8  test    rax, rax
0x180003ebb  jz      short loc_180003EDA
0x180003ebd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003ec4  jnz     short loc_180003EDA
0x180003ec6  mov     r8d, edi
0x180003ec9  lea     rdx, [rbp+13E0h+OutputString]
0x180003ed0  lea     rcx, [rsp+14E0h+var_14C0]
0x180003ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eda  cmp     [rbp+13E0h+OutputString], r12w
0x180003ee2  jnz     short loc_180003EF8
0x180003ee4  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180003ee9  mov     rdx, rdi; unsigned __int16 *
0x180003eec  lea     rcx, [rbp+13E0h+OutputString]; this
0x180003ef3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003ef8  test    bl, bl
0x180003efa  jz      short loc_180003F09
0x180003efc  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180003f03  call    cs:__imp_OutputDebugStringW
0x180003f09  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180003f0e  jnz     short loc_180003F19
0x180003f10  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003f17  jz      short loc_180003F2B
0x180003f19  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003f20  test    rax, rax
0x180003f23  jz      short loc_180003F2B
0x180003f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f2a  nop
0x180003f2b  test    byte ptr [rsp+14E0h+var_14C0+4], 1
0x180003f30  jz      short loc_180003F3D
0x180003f32  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180003f37  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003f3d  test    r15b, r15b
0x180003f40  jz      short loc_180003F5A
0x180003f42  lea     rdx, [rbp+13E0h+OutputString]
0x180003f49  lea     rcx, [rsp+14E0h+var_14C0]
0x180003f4e  mov     rax, cs:g_pfnThrowPlatformException
0x180003f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f5a  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180003f5f  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180003f64  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180003f69  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
