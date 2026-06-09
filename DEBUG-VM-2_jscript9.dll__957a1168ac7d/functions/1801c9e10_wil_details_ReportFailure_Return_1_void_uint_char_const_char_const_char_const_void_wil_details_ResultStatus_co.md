# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1801c9e10`
- end: `0x1801ca11b`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1801c99c0`

## callees

- `0x1801c9e10`
- `0x1801cb954`
- `0x1801cde34`
- `0x1801cf924`
- `0x1801cfbd8`
- `0x180341dd0`
- `0x180341e00`
- `0x18035e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1801ca025`
- `KERNEL32!IsDebuggerPresent` at `0x1801ca025`
- `KERNEL32!GetCurrentThreadId` at `0x1801c9f2e`
- `KERNEL32!GetCurrentThreadId` at `0x1801c9f2e`
- `KERNEL32!OutputDebugStringW` at `0x1801ca092`
- `KERNEL32!OutputDebugStringW` at `0x1801ca092`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _WORD *a8,
        int a9,
        int a10)
{
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  unsigned int v18; // [rsp+20h] [rbp-E0h]
  unsigned __int64 v19[2]; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v20; // [rsp+40h] [rbp-C0h]
  __int128 v21; // [rsp+50h] [rbp-B0h]
  __int128 v22; // [rsp+60h] [rbp-A0h]
  __int128 v23; // [rsp+70h] [rbp-90h]
  __int128 v24; // [rsp+80h] [rbp-80h]
  _OWORD v25[2]; // [rsp+90h] [rbp-70h] BYREF
  __int128 v26; // [rsp+B0h] [rbp-50h]
  __int64 v27; // [rsp+C0h] [rbp-40h]
  __int64 v28; // [rsp+D0h] [rbp-30h]
  _BYTE v29[1024]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR OutputString[2048]; // [rsp+4E0h] [rbp+3E0h] BYREF

  v28 = -2;
  *(_OWORD *)v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  v24 = 0;
  memset(v25, 0, sizeof(v25));
  v26 = 0;
  v27 = 0;
  OutputString[0] = 0;
  v29[0] = 0;
  v19[1] = *(_QWORD *)a7;
  v18 = wil::details::RecordReturn((wil::details *)LODWORD(v19[1]), a2);
  LODWORD(v19[0]) = 1;
  HIDWORD(v19[0]) = a10;
  if ( *(_DWORD *)(a7 + 8) == 1 )
    HIDWORD(v19[0]) = a10 | 8;
  LODWORD(v20) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( a8 && *a8 )
    *((_QWORD *)&v20 + 1) = a8;
  else
    *((_QWORD *)&v20 + 1) = 0;
  LODWORD(v21) = GetCurrentThreadId();
  *((_QWORD *)&v22 + 1) = a3;
  v23 = __PAIR64__(v18, a2);
  *((_QWORD *)&v21 + 1) = a5;
  *(_QWORD *)&v22 = a4;
  *((_QWORD *)&v26 + 1) = a6;
  v27 = a1;
  v24 = 0;
  memset(v25, 0, sizeof(v25));
  if ( wil::details::g_pfnGetModuleName )
    *(_QWORD *)&v26 = wil::details::g_pfnGetModuleName();
  else
    *(_QWORD *)&v26 = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v19, v29, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v19);
  if ( wil::details::g_pfnOriginateCallback && (v19[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v19);
  if ( SLODWORD(v19[1]) >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v17)
    || !wil::g_fResultOutputDebugString
    || (v19[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)v19, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak();
  if ( (v19[0] & 0x100000000LL) != 0 )
    wil::details::WilFailFast((wil::details *)v19, v14);
}

```

## disassembly

```asm
0x1801c9e10  mov     [rsp-8+arg_18], r9
0x1801c9e15  mov     [rsp-8+arg_10], r8
0x1801c9e1a  mov     [rsp-8+arg_8], edx
0x1801c9e1e  mov     [rsp-8+arg_0], rcx
0x1801c9e23  push    rbp
0x1801c9e24  push    rbx
0x1801c9e25  push    rsi
0x1801c9e26  push    rdi
0x1801c9e27  push    r12
0x1801c9e29  push    r13
0x1801c9e2b  push    r14
0x1801c9e2d  push    r15
0x1801c9e2f  lea     rbp, [rsp-13F8h]
0x1801c9e37  mov     eax, 14F8h
0x1801c9e3c  call    _alloca_probe
0x1801c9e41  sub     rsp, rax
0x1801c9e44  mov     [rbp+1430h+var_1460], 0FFFFFFFFFFFFFFFEh
0x1801c9e4c  mov     rax, cs:__security_cookie
0x1801c9e53  xor     rax, rsp
0x1801c9e56  mov     [rbp+1430h+var_50], rax
0x1801c9e5d  mov     rdi, [rbp+1430h+arg_0]
0x1801c9e64  mov     esi, [rbp+1430h+arg_8]
0x1801c9e6a  mov     r14, [rbp+1430h+arg_10]
0x1801c9e71  mov     r15, [rbp+1430h+arg_18]
0x1801c9e78  mov     r12, [rbp+1430h+arg_20]
0x1801c9e7f  mov     r13, [rbp+1430h+arg_28]
0x1801c9e86  xorps   xmm0, xmm0
0x1801c9e89  xor     eax, eax
0x1801c9e8b  movups  xmmword ptr [rsp+1530h+var_1500], xmm0
0x1801c9e90  movups  [rsp+1530h+var_14F0], xmm0
0x1801c9e95  movups  [rsp+1530h+var_14E0], xmm0
0x1801c9e9a  movups  [rsp+1530h+var_14D0], xmm0
0x1801c9e9f  movups  [rsp+1530h+var_14C0], xmm0
0x1801c9ea4  movups  [rbp+1430h+var_14B0], xmm0
0x1801c9ea8  movups  [rbp+1430h+var_14A0], xmm0
0x1801c9eac  movups  [rbp+1430h+var_1490], xmm0
0x1801c9eb0  movups  [rbp+1430h+var_1480], xmm0
0x1801c9eb4  mov     [rbp+1430h+var_1470], rax
0x1801c9eb8  mov     [rbp+1430h+OutputString], ax
0x1801c9ebf  mov     [rbp+1430h+var_1450], al
0x1801c9ec2  mov     rbx, [rbp+1430h+arg_30]
0x1801c9ec9  mov     ecx, [rbx]; this
0x1801c9ecb  mov     dword ptr [rsp+1530h+var_1500+8], ecx
0x1801c9ecf  mov     eax, [rbx+4]
0x1801c9ed2  mov     dword ptr [rsp+1530h+var_1500+0Ch], eax
0x1801c9ed6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1801c9edb  mov     [rsp+1530h+var_1510], eax
0x1801c9edf  mov     ecx, 1
0x1801c9ee4  mov     dword ptr [rsp+1530h+var_1500], ecx
0x1801c9ee8  mov     edx, [rbp+1430h+arg_48]
0x1801c9eee  mov     dword ptr [rsp+1530h+var_1500+4], edx
0x1801c9ef2  cmp     [rbx+8], ecx
0x1801c9ef5  jnz     short loc_1801C9EFE
0x1801c9ef7  or      edx, 8
0x1801c9efa  mov     dword ptr [rsp+1530h+var_1500+4], edx
0x1801c9efe  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1801c9f06  inc     ecx
0x1801c9f08  mov     dword ptr [rsp+1530h+var_14F0], ecx
0x1801c9f0c  mov     rax, [rbp+1430h+arg_38]
0x1801c9f13  test    rax, rax
0x1801c9f16  jz      short loc_1801C9F27
0x1801c9f18  cmp     word ptr [rax], 0
0x1801c9f1c  jz      short loc_1801C9F27
0x1801c9f1e  mov     qword ptr [rsp+1530h+var_14F0+8], rax
0x1801c9f23  xor     ebx, ebx
0x1801c9f25  jmp     short loc_1801C9F2E
0x1801c9f27  xor     ebx, ebx
0x1801c9f29  mov     qword ptr [rsp+1530h+var_14F0+8], rbx
0x1801c9f2e  call    cs:__imp_GetCurrentThreadId
0x1801c9f34  mov     dword ptr [rsp+1530h+var_14E0], eax
0x1801c9f38  mov     qword ptr [rsp+1530h+var_14D0+8], r14
0x1801c9f3d  mov     dword ptr [rsp+1530h+var_14C0], esi
0x1801c9f41  mov     eax, [rsp+1530h+var_1510]
0x1801c9f45  mov     dword ptr [rsp+1530h+var_14C0+4], eax
0x1801c9f49  mov     qword ptr [rsp+1530h+var_14E0+8], r12
0x1801c9f4e  mov     qword ptr [rsp+1530h+var_14D0], r15
0x1801c9f53  mov     qword ptr [rbp+1430h+var_1480+8], r13
0x1801c9f57  mov     [rbp+1430h+var_1470], rdi
0x1801c9f5b  mov     qword ptr [rsp+1530h+var_14C0+8], rbx
0x1801c9f60  xorps   xmm0, xmm0
0x1801c9f63  xor     eax, eax
0x1801c9f65  movups  [rbp+1430h+var_14A0+8], xmm0
0x1801c9f69  mov     qword ptr [rbp+1430h+var_1490+8], rax
0x1801c9f6d  xorps   xmm1, xmm1
0x1801c9f70  movups  [rbp+1430h+var_14B0], xmm1
0x1801c9f74  mov     qword ptr [rbp+1430h+var_14A0], rax
0x1801c9f78  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1801c9f7f  test    rax, rax
0x1801c9f82  jz      short loc_1801C9F8F
0x1801c9f84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c9f89  mov     qword ptr [rbp+1430h+var_1480], rax
0x1801c9f8d  jmp     short loc_1801C9F93
0x1801c9f8f  mov     qword ptr [rbp+1430h+var_1480], rbx
0x1801c9f93  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1801c9f9a  test    rax, rax
0x1801c9f9d  jz      short loc_1801C9FA9
0x1801c9f9f  lea     rcx, [rsp+1530h+var_1500]
0x1801c9fa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c9fa9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1801c9fb0  test    rax, rax
0x1801c9fb3  jz      short loc_1801C9FC9
0x1801c9fb5  mov     r8d, 400h
0x1801c9fbb  lea     rdx, [rbp+1430h+var_1450]
0x1801c9fbf  lea     rcx, [rsp+1530h+var_1500]
0x1801c9fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c9fc9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1801c9fd0  test    rax, rax
0x1801c9fd3  jz      short loc_1801C9FDF
0x1801c9fd5  lea     rcx, [rsp+1530h+var_1500]
0x1801c9fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c9fdf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1801c9fe6  test    rax, rax
0x1801c9fe9  jz      short loc_1801C9FFC
0x1801c9feb  test    byte ptr [rsp+1530h+var_1500+4], 2
0x1801c9ff0  jnz     short loc_1801C9FFC
0x1801c9ff2  lea     rcx, [rsp+1530h+var_1500]
0x1801c9ff7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801c9ffc  cmp     dword ptr [rsp+1530h+var_1500+8], 0
0x1801ca001  jge     loc_1801CA115
0x1801ca007  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x1801ca00e  jnz     short loc_1801CA02F
0x1801ca010  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1801ca017  test    rax, rax
0x1801ca01a  jz      short loc_1801CA025
0x1801ca01c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ca021  test    al, al
0x1801ca023  jmp     short loc_1801CA02D
0x1801ca025  call    cs:__imp_IsDebuggerPresent
0x1801ca02b  test    eax, eax
0x1801ca02d  jz      short loc_1801CA09A
0x1801ca02f  cmp     cs:?g_fResultOutputDebugString@wil@@3_NA, 0; bool wil::g_fResultOutputDebugString
0x1801ca036  jz      short loc_1801CA09A
0x1801ca038  test    byte ptr [rsp+1530h+var_1500+4], 2
0x1801ca03d  jnz     short loc_1801CA09A
0x1801ca03f  mov     rax, cs:g_pfnResultLoggingCallback
0x1801ca046  test    rax, rax
0x1801ca049  jz      short loc_1801CA06B
0x1801ca04b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1801ca052  jnz     short loc_1801CA06B
0x1801ca054  mov     r8d, 800h
0x1801ca05a  lea     rdx, [rbp+1430h+OutputString]
0x1801ca061  lea     rcx, [rsp+1530h+var_1500]
0x1801ca066  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ca06b  cmp     [rbp+1430h+OutputString], 0
0x1801ca073  jnz     short loc_1801CA08B
0x1801ca075  lea     r8, [rsp+1530h+var_1500]; unsigned __int64
0x1801ca07a  mov     edx, 800h; unsigned __int16 *
0x1801ca07f  lea     rcx, [rbp+1430h+OutputString]; this
0x1801ca086  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1801ca08b  lea     rcx, [rbp+1430h+OutputString]; lpOutputString
0x1801ca092  call    cs:__imp_OutputDebugStringW
0x1801ca098  jmp     short loc_1801CA0BE
0x1801ca09a  mov     rax, cs:g_pfnResultLoggingCallback
0x1801ca0a1  test    rax, rax
0x1801ca0a4  jz      short loc_1801CA0BE
0x1801ca0a6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1801ca0ad  jnz     short loc_1801CA0BE
0x1801ca0af  xor     r8d, r8d
0x1801ca0b2  xor     edx, edx
0x1801ca0b4  lea     rcx, [rsp+1530h+var_1500]
0x1801ca0b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ca0be  test    byte ptr [rsp+1530h+var_1500+4], 4
0x1801ca0c3  jnz     short loc_1801CA0CE
0x1801ca0c5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x1801ca0cc  jz      short loc_1801CA0E0
0x1801ca0ce  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1801ca0d5  test    rax, rax
0x1801ca0d8  jz      short loc_1801CA0E0
0x1801ca0da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801ca0df  nop
0x1801ca0e0  test    byte ptr [rsp+1530h+var_1500+4], 1
0x1801ca0e5  jnz     short loc_1801CA10A
0x1801ca0e7  mov     rcx, [rbp+1430h+var_50]
0x1801ca0ee  xor     rcx, rsp; StackCookie
0x1801ca0f1  call    __security_check_cookie
0x1801ca0f6  add     rsp, 14F8h
0x1801ca0fd  pop     r15
0x1801ca0ff  pop     r14
0x1801ca101  pop     r13
0x1801ca103  pop     r12
0x1801ca105  pop     rdi
0x1801ca106  pop     rsi
0x1801ca107  pop     rbx
0x1801ca108  pop     rbp
0x1801ca109  retn
0x1801ca10a  lea     rcx, [rsp+1530h+var_1500]; this
0x1801ca10f  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1801ca115  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
