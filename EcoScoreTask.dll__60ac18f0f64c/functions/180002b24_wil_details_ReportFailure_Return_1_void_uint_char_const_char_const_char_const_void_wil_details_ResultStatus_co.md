# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002b24`
- end: `0x180002daf`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002604`

## callees

- `0x180002b24`
- `0x180004334`
- `0x180005960`
- `0x180007260`
- `0x1800078e4`
- `0x180007c62`
- `0x180007c90`
- `0x180007d20`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002bd1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002bd1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002cc5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002cc5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002d4f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002d4f`

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
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x180002b24  push    rbp
0x180002b26  push    rbx
0x180002b27  push    rsi
0x180002b28  push    rdi
0x180002b29  push    r12
0x180002b2b  push    r14
0x180002b2d  push    r15
0x180002b2f  lea     rbp, [rsp-13D0h]
0x180002b37  mov     eax, 14D0h
0x180002b3c  call    _alloca_probe
0x180002b41  sub     rsp, rax
0x180002b44  mov     rax, cs:__security_cookie
0x180002b4b  xor     rax, rsp
0x180002b4e  mov     [rbp+1400h+var_40], rax
0x180002b55  mov     rdi, [rbp+1400h+arg_28]
0x180002b5c  mov     r14, r8
0x180002b5f  mov     esi, edx
0x180002b61  mov     r15, rcx
0x180002b64  xor     edx, edx; Val
0x180002b66  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002b6b  mov     r8d, 98h; Size
0x180002b71  call    memset_0
0x180002b76  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180002b7d  xor     r12d, r12d
0x180002b80  mov     [rbp+1400h+OutputString], r12w
0x180002b88  mov     [rbp+1400h+var_1440], r12b
0x180002b8c  mov     ecx, [rdx]; this
0x180002b8e  mov     eax, [rdx+4]
0x180002b91  mov     [rsp+1500h+var_14D8], ecx
0x180002b95  mov     [rsp+1500h+var_14D4], eax
0x180002b99  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002b9e  cmp     dword ptr [rdx+8], 1
0x180002ba2  mov     ebx, eax
0x180002ba4  lea     eax, [r12+8]
0x180002ba9  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180002bb1  mov     ecx, r12d
0x180002bb4  cmovz   ecx, eax
0x180002bb7  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180002bbb  lea     ecx, [rax-7]
0x180002bbe  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002bc6  inc     ecx
0x180002bc8  mov     [rsp+1500h+var_14C8], r12
0x180002bcd  mov     [rsp+1500h+var_14D0], ecx
0x180002bd1  call    cs:__imp_GetCurrentThreadId
0x180002bd7  xorps   xmm0, xmm0
0x180002bda  mov     [rsp+1500h+var_14A8], r14
0x180002bdf  mov     [rsp+1500h+var_14C0], eax
0x180002be3  xorps   xmm1, xmm1
0x180002be6  xor     eax, eax
0x180002be8  mov     [rsp+1500h+var_14A0], esi
0x180002bec  mov     [rbp+1400h+var_1468], rax
0x180002bf0  mov     [rbp+1400h+var_1480], rax
0x180002bf4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002bfb  mov     [rsp+1500h+var_149C], ebx
0x180002bff  mov     [rsp+1500h+var_14B8], r12
0x180002c04  mov     [rsp+1500h+var_14B0], r12
0x180002c09  mov     [rbp+1400h+var_1458], rdi
0x180002c0d  mov     [rbp+1400h+var_1450], r15
0x180002c11  mov     [rsp+1500h+var_1498], r12
0x180002c16  movups  [rbp+1400h+var_1478], xmm0
0x180002c1a  movups  [rsp+1500h+var_1490], xmm1
0x180002c1f  test    rax, rax
0x180002c22  jz      short loc_180002C2F
0x180002c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c29  mov     [rbp+1400h+var_1460], rax
0x180002c2d  jmp     short loc_180002C33
0x180002c2f  mov     [rbp+1400h+var_1460], r12
0x180002c33  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002c3a  test    rax, rax
0x180002c3d  jz      short loc_180002C49
0x180002c3f  lea     rcx, [rsp+1500h+var_14E0]
0x180002c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c49  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002c50  test    rax, rax
0x180002c53  jz      short loc_180002C69
0x180002c55  mov     r8d, 400h
0x180002c5b  lea     rdx, [rbp+1400h+var_1440]
0x180002c5f  lea     rcx, [rsp+1500h+var_14E0]
0x180002c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c69  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002c70  test    rax, rax
0x180002c73  jz      short loc_180002C7F
0x180002c75  lea     rcx, [rsp+1500h+var_14E0]
0x180002c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c7f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002c86  test    rax, rax
0x180002c89  jz      short loc_180002C9C
0x180002c8b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002c90  jnz     short loc_180002C9C
0x180002c92  lea     rcx, [rsp+1500h+var_14E0]
0x180002c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c9c  cmp     [rsp+1500h+var_14D8], r12d
0x180002ca1  jge     loc_180002D9E
0x180002ca7  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002cae  jnz     short loc_180002CCF
0x180002cb0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002cb7  test    rax, rax
0x180002cba  jz      short loc_180002CC5
0x180002cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc1  test    al, al
0x180002cc3  jmp     short loc_180002CCD
0x180002cc5  call    cs:__imp_IsDebuggerPresent
0x180002ccb  test    eax, eax
0x180002ccd  jz      short loc_180002CD6
0x180002ccf  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002cd4  jz      short loc_180002CFC
0x180002cd6  mov     rax, cs:g_pfnResultLoggingCallback
0x180002cdd  test    rax, rax
0x180002ce0  jz      short loc_180002D55
0x180002ce2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002ce9  jnz     short loc_180002D55
0x180002ceb  xor     r8d, r8d
0x180002cee  lea     rcx, [rsp+1500h+var_14E0]
0x180002cf3  xor     edx, edx
0x180002cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cfa  jmp     short loc_180002D55
0x180002cfc  mov     rax, cs:g_pfnResultLoggingCallback
0x180002d03  mov     ebx, 800h
0x180002d08  test    rax, rax
0x180002d0b  jz      short loc_180002D2A
0x180002d0d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002d14  jnz     short loc_180002D2A
0x180002d16  mov     r8d, ebx
0x180002d19  lea     rdx, [rbp+1400h+OutputString]
0x180002d20  lea     rcx, [rsp+1500h+var_14E0]
0x180002d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d2a  cmp     [rbp+1400h+OutputString], r12w
0x180002d32  jnz     short loc_180002D48
0x180002d34  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180002d39  mov     rdx, rbx; unsigned __int16 *
0x180002d3c  lea     rcx, [rbp+1400h+OutputString]; this
0x180002d43  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002d48  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180002d4f  call    cs:__imp_OutputDebugStringW
0x180002d55  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180002d5a  jnz     short loc_180002D65
0x180002d5c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002d63  jz      short loc_180002D76
0x180002d65  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002d6c  test    rax, rax
0x180002d6f  jz      short loc_180002D76
0x180002d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d76  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180002d7b  jnz     short loc_180002DA4
0x180002d7d  mov     rcx, [rbp+1400h+var_40]
0x180002d84  xor     rcx, rsp; StackCookie
0x180002d87  call    __security_check_cookie
0x180002d8c  add     rsp, 14D0h
0x180002d93  pop     r15
0x180002d95  pop     r14
0x180002d97  pop     r12
0x180002d99  pop     rdi
0x180002d9a  pop     rsi
0x180002d9b  pop     rbx
0x180002d9c  pop     rbp
0x180002d9d  retn
0x180002d9e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180002da4  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002da9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
