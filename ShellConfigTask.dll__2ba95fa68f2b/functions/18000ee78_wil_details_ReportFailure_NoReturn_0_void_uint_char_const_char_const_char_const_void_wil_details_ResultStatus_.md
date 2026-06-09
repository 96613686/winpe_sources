# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000ee78`
- end: `0x18000f124`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000eb5c`

## callees

- `0x180002f98`
- `0x180007914`
- `0x180009284`
- `0x18000bb64`
- `0x18000c380`
- `0x18000c5c4`
- `0x18000ee78`
- `0x1800300f0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ef21`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ef21`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f01c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f01c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f0b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f0b8`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0, v16);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x18000ee78  mov     [rsp-8+arg_18], rbx
0x18000ee7d  push    rbp
0x18000ee7e  push    rsi
0x18000ee7f  push    rdi
0x18000ee80  push    r12
0x18000ee82  push    r13
0x18000ee84  push    r14
0x18000ee86  push    r15
0x18000ee88  lea     rbp, [rsp-13C0h]
0x18000ee90  mov     eax, 14C0h
0x18000ee95  call    _alloca_probe
0x18000ee9a  sub     rsp, rax
0x18000ee9d  mov     r14, r8
0x18000eea0  mov     esi, edx
0x18000eea2  mov     r15, rcx
0x18000eea5  mov     rdi, [rbp+13F0h+arg_28]
0x18000eeac  xor     r13d, r13d
0x18000eeaf  cmp     cs:g_pfnThrowPlatformException, r13
0x18000eeb6  setnz   r12b
0x18000eeba  xor     edx, edx; Val
0x18000eebc  mov     r8d, 98h; Size
0x18000eec2  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000eec7  call    memset_0
0x18000eecc  nop
0x18000eecd  mov     [rbp+13F0h+OutputString], r13w
0x18000eed5  mov     [rbp+13F0h+var_1430], r13b
0x18000eed9  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000eee0  mov     ecx, [rdx]; this
0x18000eee2  mov     [rsp+14F0h+var_14C8], ecx
0x18000eee6  mov     eax, [rdx+4]
0x18000eee9  mov     [rsp+14F0h+var_14C4], eax
0x18000eeed  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000eef2  mov     ebx, eax
0x18000eef4  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000eef9  mov     ecx, r13d
0x18000eefc  lea     eax, [r13+8]
0x18000ef00  cmp     dword ptr [rdx+8], 1
0x18000ef04  cmovz   ecx, eax
0x18000ef07  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000ef0b  lea     ecx, [rax-7]
0x18000ef0e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ef16  inc     ecx
0x18000ef18  mov     [rsp+14F0h+var_14C0], ecx
0x18000ef1c  mov     [rsp+14F0h+var_14B8], r13
0x18000ef21  call    cs:__imp_GetCurrentThreadId
0x18000ef27  mov     [rsp+14F0h+var_14B0], eax
0x18000ef2b  mov     [rsp+14F0h+var_1498], r14
0x18000ef30  mov     [rsp+14F0h+var_1490], esi
0x18000ef34  mov     [rsp+14F0h+var_148C], ebx
0x18000ef38  mov     [rsp+14F0h+var_14A8], r13
0x18000ef3d  mov     [rsp+14F0h+var_14A0], r13
0x18000ef42  mov     [rbp+13F0h+var_1448], rdi
0x18000ef46  mov     [rbp+13F0h+var_1440], r15
0x18000ef4a  mov     [rsp+14F0h+var_1488], r13
0x18000ef4f  xorps   xmm0, xmm0
0x18000ef52  xor     eax, eax
0x18000ef54  movups  [rbp+13F0h+var_1468], xmm0
0x18000ef58  mov     [rbp+13F0h+var_1458], rax
0x18000ef5c  xorps   xmm1, xmm1
0x18000ef5f  movups  [rsp+14F0h+var_1480], xmm1
0x18000ef64  mov     [rbp+13F0h+var_1470], rax
0x18000ef68  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000ef6f  test    rax, rax
0x18000ef72  jz      short loc_18000EF7F
0x18000ef74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef79  mov     [rbp+13F0h+var_1450], rax
0x18000ef7d  jmp     short loc_18000EF83
0x18000ef7f  mov     [rbp+13F0h+var_1450], r13
0x18000ef83  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000ef8a  test    rax, rax
0x18000ef8d  jz      short loc_18000EF99
0x18000ef8f  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ef94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef99  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000efa0  test    rax, rax
0x18000efa3  jz      short loc_18000EFB9
0x18000efa5  mov     r8d, 400h
0x18000efab  lea     rdx, [rbp+13F0h+var_1430]
0x18000efaf  lea     rcx, [rsp+14F0h+var_14D0]
0x18000efb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efb9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000efc0  test    rax, rax
0x18000efc3  jz      short loc_18000EFCF
0x18000efc5  lea     rcx, [rsp+14F0h+var_14D0]
0x18000efca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efcf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000efd6  test    rax, rax
0x18000efd9  jz      short loc_18000EFF1
0x18000efdb  test    r12b, r12b
0x18000efde  jnz     short loc_18000EFF1
0x18000efe0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000efe5  jnz     short loc_18000EFF1
0x18000efe7  lea     rcx, [rsp+14F0h+var_14D0]
0x18000efec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eff1  cmp     [rsp+14F0h+var_14C8], r13d
0x18000eff6  jl      short loc_18000EFFE
0x18000eff8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000effe  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000f005  jnz     short loc_18000F026
0x18000f007  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000f00e  test    rax, rax
0x18000f011  jz      short loc_18000F01C
0x18000f013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f018  test    al, al
0x18000f01a  jmp     short loc_18000F024
0x18000f01c  call    cs:__imp_IsDebuggerPresent
0x18000f022  test    eax, eax
0x18000f024  jz      short loc_18000F02F
0x18000f026  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000f02b  mov     bl, 1
0x18000f02d  jz      short loc_18000F032
0x18000f02f  mov     bl, r13b
0x18000f032  test    r12b, r12b
0x18000f035  jnz     short loc_18000F061
0x18000f037  test    bl, bl
0x18000f039  jnz     short loc_18000F061
0x18000f03b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f042  test    rax, rax
0x18000f045  jz      short loc_18000F0BE
0x18000f047  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000f04e  jnz     short loc_18000F0BE
0x18000f050  xor     r8d, r8d
0x18000f053  xor     edx, edx
0x18000f055  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f05f  jmp     short loc_18000F0BE
0x18000f061  mov     edi, 800h
0x18000f066  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f06d  test    rax, rax
0x18000f070  jz      short loc_18000F08F
0x18000f072  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000f079  jnz     short loc_18000F08F
0x18000f07b  mov     r8d, edi
0x18000f07e  lea     rdx, [rbp+13F0h+OutputString]
0x18000f085  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f08a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f08f  cmp     [rbp+13F0h+OutputString], r13w
0x18000f097  jnz     short loc_18000F0AD
0x18000f099  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000f09e  mov     rdx, rdi; unsigned __int16 *
0x18000f0a1  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000f0a8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000f0ad  test    bl, bl
0x18000f0af  jz      short loc_18000F0BE
0x18000f0b1  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000f0b8  call    cs:__imp_OutputDebugStringW
0x18000f0be  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000f0c3  jnz     short loc_18000F0CE
0x18000f0c5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000f0cc  jz      short loc_18000F0E0
0x18000f0ce  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000f0d5  test    rax, rax
0x18000f0d8  jz      short loc_18000F0E0
0x18000f0da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0df  nop
0x18000f0e0  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000f0e5  jz      short loc_18000F0F2
0x18000f0e7  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000f0ec  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000f0f2  test    r12b, r12b
0x18000f0f5  jz      short loc_18000F10F
0x18000f0f7  lea     rdx, [rbp+13F0h+OutputString]
0x18000f0fe  lea     rcx, [rsp+14F0h+var_14D0]
0x18000f103  mov     rax, cs:g_pfnThrowPlatformException
0x18000f10a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f10f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000f114  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000f119  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000f11e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
