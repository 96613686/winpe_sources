# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18001ee64`
- end: `0x18001f0f8`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001e96c`

## callees

- `0x18001ee64`
- `0x1800204e4`
- `0x180021e60`
- `0x180023350`
- `0x18002350c`
- `0x180023d86`
- `0x180023dd0`
- `0x180023e60`
- `0x180064010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18001f093`
- `KERNEL32!OutputDebugStringW` at `0x18001f093`
- `KERNEL32!IsDebuggerPresent` at `0x18001f009`
- `KERNEL32!IsDebuggerPresent` at `0x18001f009`
- `KERNEL32!GetCurrentThreadId` at `0x18001ef0e`
- `KERNEL32!GetCurrentThreadId` at `0x18001ef0e`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
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
  v28 = "wil";
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
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
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x18001ee64  mov     [rsp-8+arg_10], rbx
0x18001ee69  push    rbp
0x18001ee6a  push    rsi
0x18001ee6b  push    rdi
0x18001ee6c  push    r14
0x18001ee6e  push    r15
0x18001ee70  lea     rbp, [rsp-13D0h]
0x18001ee78  mov     eax, 14D0h
0x18001ee7d  call    _alloca_probe
0x18001ee82  sub     rsp, rax
0x18001ee85  mov     rax, cs:__security_cookie
0x18001ee8c  xor     rax, rsp
0x18001ee8f  mov     [rbp+13F0h+var_30], rax
0x18001ee96  mov     rdi, [rbp+13F0h+arg_28]
0x18001ee9d  mov     esi, edx
0x18001ee9f  mov     r14, rcx
0x18001eea2  xor     edx, edx; Val
0x18001eea4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001eea9  mov     r8d, 98h; Size
0x18001eeaf  call    memset_0
0x18001eeb4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18001eebb  xor     r15d, r15d
0x18001eebe  mov     [rbp+13F0h+OutputString], r15w
0x18001eec6  mov     [rbp+13F0h+var_1430], r15b
0x18001eeca  mov     ecx, [rdx]; this
0x18001eecc  mov     eax, [rdx+4]
0x18001eecf  mov     [rsp+14F0h+var_14C8], ecx
0x18001eed3  mov     [rsp+14F0h+var_14C4], eax
0x18001eed7  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001eedc  cmp     dword ptr [rdx+8], 1
0x18001eee0  mov     ebx, eax
0x18001eee2  lea     eax, [r15+8]
0x18001eee6  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18001eeee  mov     ecx, r15d
0x18001eef1  cmovz   ecx, eax
0x18001eef4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001eef8  lea     ecx, [rax-7]
0x18001eefb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001ef03  inc     ecx
0x18001ef05  mov     [rsp+14F0h+var_14B8], r15
0x18001ef0a  mov     [rsp+14F0h+var_14C0], ecx
0x18001ef0e  call    cs:__imp_GetCurrentThreadId
0x18001ef14  xorps   xmm0, xmm0
0x18001ef17  mov     [rsp+14F0h+var_1490], esi
0x18001ef1b  mov     [rsp+14F0h+var_14B0], eax
0x18001ef1f  xorps   xmm1, xmm1
0x18001ef22  lea     rax, aWil; "wil"
0x18001ef29  mov     [rsp+14F0h+var_148C], ebx
0x18001ef2d  mov     [rsp+14F0h+var_1498], rax
0x18001ef32  xor     eax, eax
0x18001ef34  mov     [rbp+13F0h+var_1458], rax
0x18001ef38  mov     [rbp+13F0h+var_1470], rax
0x18001ef3c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001ef43  mov     [rsp+14F0h+var_14A8], r15
0x18001ef48  mov     [rsp+14F0h+var_14A0], r15
0x18001ef4d  mov     [rbp+13F0h+var_1448], rdi
0x18001ef51  mov     [rbp+13F0h+var_1440], r14
0x18001ef55  mov     [rsp+14F0h+var_1488], r15
0x18001ef5a  movups  [rbp+13F0h+var_1468], xmm0
0x18001ef5e  movups  [rsp+14F0h+var_1480], xmm1
0x18001ef63  test    rax, rax
0x18001ef66  jz      short loc_18001EF73
0x18001ef68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef6d  mov     [rbp+13F0h+var_1450], rax
0x18001ef71  jmp     short loc_18001EF77
0x18001ef73  mov     [rbp+13F0h+var_1450], r15
0x18001ef77  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001ef7e  test    rax, rax
0x18001ef81  jz      short loc_18001EF8D
0x18001ef83  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ef88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ef8d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001ef94  test    rax, rax
0x18001ef97  jz      short loc_18001EFAD
0x18001ef99  mov     r8d, 400h
0x18001ef9f  lea     rdx, [rbp+13F0h+var_1430]
0x18001efa3  lea     rcx, [rsp+14F0h+var_14D0]
0x18001efa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efad  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001efb4  test    rax, rax
0x18001efb7  jz      short loc_18001EFC3
0x18001efb9  lea     rcx, [rsp+14F0h+var_14D0]
0x18001efbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efc3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001efca  test    rax, rax
0x18001efcd  jz      short loc_18001EFE0
0x18001efcf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001efd4  jnz     short loc_18001EFE0
0x18001efd6  lea     rcx, [rsp+14F0h+var_14D0]
0x18001efdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001efe0  cmp     [rsp+14F0h+var_14C8], r15d
0x18001efe5  jge     loc_18001F0E7
0x18001efeb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18001eff2  jnz     short loc_18001F013
0x18001eff4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001effb  test    rax, rax
0x18001effe  jz      short loc_18001F009
0x18001f000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f005  test    al, al
0x18001f007  jmp     short loc_18001F011
0x18001f009  call    cs:__imp_IsDebuggerPresent
0x18001f00f  test    eax, eax
0x18001f011  jz      short loc_18001F01A
0x18001f013  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001f018  jz      short loc_18001F040
0x18001f01a  mov     rax, cs:g_pfnResultLoggingCallback
0x18001f021  test    rax, rax
0x18001f024  jz      short loc_18001F099
0x18001f026  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001f02d  jnz     short loc_18001F099
0x18001f02f  xor     r8d, r8d
0x18001f032  lea     rcx, [rsp+14F0h+var_14D0]
0x18001f037  xor     edx, edx
0x18001f039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f03e  jmp     short loc_18001F099
0x18001f040  mov     rax, cs:g_pfnResultLoggingCallback
0x18001f047  mov     ebx, 800h
0x18001f04c  test    rax, rax
0x18001f04f  jz      short loc_18001F06E
0x18001f051  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001f058  jnz     short loc_18001F06E
0x18001f05a  mov     r8d, ebx
0x18001f05d  lea     rdx, [rbp+13F0h+OutputString]
0x18001f064  lea     rcx, [rsp+14F0h+var_14D0]
0x18001f069  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f06e  cmp     [rbp+13F0h+OutputString], r15w
0x18001f076  jnz     short loc_18001F08C
0x18001f078  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001f07d  mov     rdx, rbx; unsigned __int16 *
0x18001f080  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001f087  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001f08c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001f093  call    cs:__imp_OutputDebugStringW
0x18001f099  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001f09e  jnz     short loc_18001F0A9
0x18001f0a0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18001f0a7  jz      short loc_18001F0BA
0x18001f0a9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001f0b0  test    rax, rax
0x18001f0b3  jz      short loc_18001F0BA
0x18001f0b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0ba  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18001f0bf  jnz     short loc_18001F0ED
0x18001f0c1  mov     rcx, [rbp+13F0h+var_30]
0x18001f0c8  xor     rcx, rsp; StackCookie
0x18001f0cb  call    __security_check_cookie
0x18001f0d0  mov     rbx, [rsp+14F0h+arg_10]
0x18001f0d8  add     rsp, 14D0h
0x18001f0df  pop     r15
0x18001f0e1  pop     r14
0x18001f0e3  pop     rdi
0x18001f0e4  pop     rsi
0x18001f0e5  pop     rbp
0x18001f0e6  retn
0x18001f0e7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001f0ed  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001f0f2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
