# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180010ec8`
- end: `0x18001115c`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800109b0`

## callees

- `0x180010ec8`
- `0x180011ce4`
- `0x180012c20`
- `0x180013370`
- `0x18001344c`
- `0x18001358e`
- `0x1800135c0`
- `0x180013650`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180010f72`
- `KERNEL32!GetCurrentThreadId` at `0x180010f72`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001106d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001106d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800110f7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800110f7`

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
0x180010ec8  mov     [rsp-8+arg_10], rbx
0x180010ecd  push    rbp
0x180010ece  push    rsi
0x180010ecf  push    rdi
0x180010ed0  push    r14
0x180010ed2  push    r15
0x180010ed4  lea     rbp, [rsp-13D0h]
0x180010edc  mov     eax, 14D0h
0x180010ee1  call    _alloca_probe
0x180010ee6  sub     rsp, rax
0x180010ee9  mov     rax, cs:__security_cookie
0x180010ef0  xor     rax, rsp
0x180010ef3  mov     [rbp+13F0h+var_30], rax
0x180010efa  mov     rdi, [rbp+13F0h+arg_28]
0x180010f01  mov     esi, edx
0x180010f03  mov     r14, rcx
0x180010f06  xor     edx, edx; Val
0x180010f08  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180010f0d  mov     r8d, 98h; Size
0x180010f13  call    memset_0
0x180010f18  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180010f1f  xor     r15d, r15d
0x180010f22  mov     [rbp+13F0h+OutputString], r15w
0x180010f2a  mov     [rbp+13F0h+var_1430], r15b
0x180010f2e  mov     ecx, [rdx]; this
0x180010f30  mov     eax, [rdx+4]
0x180010f33  mov     [rsp+14F0h+var_14C8], ecx
0x180010f37  mov     [rsp+14F0h+var_14C4], eax
0x180010f3b  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180010f40  cmp     dword ptr [rdx+8], 1
0x180010f44  mov     ebx, eax
0x180010f46  lea     eax, [r15+8]
0x180010f4a  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180010f52  mov     ecx, r15d
0x180010f55  cmovz   ecx, eax
0x180010f58  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180010f5c  lea     ecx, [rax-7]
0x180010f5f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180010f67  inc     ecx
0x180010f69  mov     [rsp+14F0h+var_14B8], r15
0x180010f6e  mov     [rsp+14F0h+var_14C0], ecx
0x180010f72  call    cs:__imp_GetCurrentThreadId
0x180010f78  xorps   xmm0, xmm0
0x180010f7b  mov     [rsp+14F0h+var_1490], esi
0x180010f7f  mov     [rsp+14F0h+var_14B0], eax
0x180010f83  xorps   xmm1, xmm1
0x180010f86  lea     rax, aWil; "wil"
0x180010f8d  mov     [rsp+14F0h+var_148C], ebx
0x180010f91  mov     [rsp+14F0h+var_1498], rax
0x180010f96  xor     eax, eax
0x180010f98  mov     [rbp+13F0h+var_1458], rax
0x180010f9c  mov     [rbp+13F0h+var_1470], rax
0x180010fa0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180010fa7  mov     [rsp+14F0h+var_14A8], r15
0x180010fac  mov     [rsp+14F0h+var_14A0], r15
0x180010fb1  mov     [rbp+13F0h+var_1448], rdi
0x180010fb5  mov     [rbp+13F0h+var_1440], r14
0x180010fb9  mov     [rsp+14F0h+var_1488], r15
0x180010fbe  movups  [rbp+13F0h+var_1468], xmm0
0x180010fc2  movups  [rsp+14F0h+var_1480], xmm1
0x180010fc7  test    rax, rax
0x180010fca  jz      short loc_180010FD7
0x180010fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fd1  mov     [rbp+13F0h+var_1450], rax
0x180010fd5  jmp     short loc_180010FDB
0x180010fd7  mov     [rbp+13F0h+var_1450], r15
0x180010fdb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180010fe2  test    rax, rax
0x180010fe5  jz      short loc_180010FF1
0x180010fe7  lea     rcx, [rsp+14F0h+var_14D0]
0x180010fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ff1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180010ff8  test    rax, rax
0x180010ffb  jz      short loc_180011011
0x180010ffd  mov     r8d, 400h
0x180011003  lea     rdx, [rbp+13F0h+var_1430]
0x180011007  lea     rcx, [rsp+14F0h+var_14D0]
0x18001100c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011011  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011018  test    rax, rax
0x18001101b  jz      short loc_180011027
0x18001101d  lea     rcx, [rsp+14F0h+var_14D0]
0x180011022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011027  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001102e  test    rax, rax
0x180011031  jz      short loc_180011044
0x180011033  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180011038  jnz     short loc_180011044
0x18001103a  lea     rcx, [rsp+14F0h+var_14D0]
0x18001103f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011044  cmp     [rsp+14F0h+var_14C8], r15d
0x180011049  jge     loc_18001114B
0x18001104f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180011056  jnz     short loc_180011077
0x180011058  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001105f  test    rax, rax
0x180011062  jz      short loc_18001106D
0x180011064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011069  test    al, al
0x18001106b  jmp     short loc_180011075
0x18001106d  call    cs:__imp_IsDebuggerPresent
0x180011073  test    eax, eax
0x180011075  jz      short loc_18001107E
0x180011077  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001107c  jz      short loc_1800110A4
0x18001107e  mov     rax, cs:g_pfnResultLoggingCallback
0x180011085  test    rax, rax
0x180011088  jz      short loc_1800110FD
0x18001108a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180011091  jnz     short loc_1800110FD
0x180011093  xor     r8d, r8d
0x180011096  lea     rcx, [rsp+14F0h+var_14D0]
0x18001109b  xor     edx, edx
0x18001109d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110a2  jmp     short loc_1800110FD
0x1800110a4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800110ab  mov     ebx, 800h
0x1800110b0  test    rax, rax
0x1800110b3  jz      short loc_1800110D2
0x1800110b5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800110bc  jnz     short loc_1800110D2
0x1800110be  mov     r8d, ebx
0x1800110c1  lea     rdx, [rbp+13F0h+OutputString]
0x1800110c8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800110cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110d2  cmp     [rbp+13F0h+OutputString], r15w
0x1800110da  jnz     short loc_1800110F0
0x1800110dc  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800110e1  mov     rdx, rbx; unsigned __int16 *
0x1800110e4  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800110eb  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800110f0  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800110f7  call    cs:__imp_OutputDebugStringW
0x1800110fd  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180011102  jnz     short loc_18001110D
0x180011104  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18001110b  jz      short loc_18001111E
0x18001110d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180011114  test    rax, rax
0x180011117  jz      short loc_18001111E
0x180011119  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001111e  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180011123  jnz     short loc_180011151
0x180011125  mov     rcx, [rbp+13F0h+var_30]
0x18001112c  xor     rcx, rsp; StackCookie
0x18001112f  call    __security_check_cookie
0x180011134  mov     rbx, [rsp+14F0h+arg_10]
0x18001113c  add     rsp, 14D0h
0x180011143  pop     r15
0x180011145  pop     r14
0x180011147  pop     rdi
0x180011148  pop     rsi
0x180011149  pop     rbp
0x18001114a  retn
0x18001114b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180011151  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180011156  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
