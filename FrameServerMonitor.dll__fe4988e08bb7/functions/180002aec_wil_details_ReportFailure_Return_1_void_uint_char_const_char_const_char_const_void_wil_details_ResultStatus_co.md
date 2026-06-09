# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002aec`
- end: `0x180002d77`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800027b0`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180002aec`
- `0x180003924`
- `0x180004a50`
- `0x180005358`
- `0x180005434`
- `0x18004bef0`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b99`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002b99`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002c8d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002c8d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002d17`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002d17`

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
0x180002aec  push    rbp
0x180002aee  push    rbx
0x180002aef  push    rsi
0x180002af0  push    rdi
0x180002af1  push    r12
0x180002af3  push    r14
0x180002af5  push    r15
0x180002af7  lea     rbp, [rsp-13D0h]
0x180002aff  mov     eax, 14D0h
0x180002b04  call    _alloca_probe
0x180002b09  sub     rsp, rax
0x180002b0c  mov     rax, cs:__security_cookie
0x180002b13  xor     rax, rsp
0x180002b16  mov     [rbp+1400h+var_40], rax
0x180002b1d  mov     rdi, [rbp+1400h+arg_28]
0x180002b24  mov     r14, r8
0x180002b27  mov     esi, edx
0x180002b29  mov     r15, rcx
0x180002b2c  xor     edx, edx; Val
0x180002b2e  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002b33  mov     r8d, 98h; Size
0x180002b39  call    memset_0
0x180002b3e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180002b45  xor     r12d, r12d
0x180002b48  mov     [rbp+1400h+OutputString], r12w
0x180002b50  mov     [rbp+1400h+var_1440], r12b
0x180002b54  mov     ecx, [rdx]; this
0x180002b56  mov     eax, [rdx+4]
0x180002b59  mov     [rsp+1500h+var_14D8], ecx
0x180002b5d  mov     [rsp+1500h+var_14D4], eax
0x180002b61  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002b66  cmp     dword ptr [rdx+8], 1
0x180002b6a  mov     ebx, eax
0x180002b6c  lea     eax, [r12+8]
0x180002b71  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180002b79  mov     ecx, r12d
0x180002b7c  cmovz   ecx, eax
0x180002b7f  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180002b83  lea     ecx, [rax-7]
0x180002b86  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002b8e  inc     ecx
0x180002b90  mov     [rsp+1500h+var_14C8], r12
0x180002b95  mov     [rsp+1500h+var_14D0], ecx
0x180002b99  call    cs:__imp_GetCurrentThreadId
0x180002b9f  xorps   xmm0, xmm0
0x180002ba2  mov     [rsp+1500h+var_14A8], r14
0x180002ba7  mov     [rsp+1500h+var_14C0], eax
0x180002bab  xorps   xmm1, xmm1
0x180002bae  xor     eax, eax
0x180002bb0  mov     [rsp+1500h+var_14A0], esi
0x180002bb4  mov     [rbp+1400h+var_1468], rax
0x180002bb8  mov     [rbp+1400h+var_1480], rax
0x180002bbc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002bc3  mov     [rsp+1500h+var_149C], ebx
0x180002bc7  mov     [rsp+1500h+var_14B8], r12
0x180002bcc  mov     [rsp+1500h+var_14B0], r12
0x180002bd1  mov     [rbp+1400h+var_1458], rdi
0x180002bd5  mov     [rbp+1400h+var_1450], r15
0x180002bd9  mov     [rsp+1500h+var_1498], r12
0x180002bde  movups  [rbp+1400h+var_1478], xmm0
0x180002be2  movups  [rsp+1500h+var_1490], xmm1
0x180002be7  test    rax, rax
0x180002bea  jz      short loc_180002BF7
0x180002bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bf1  mov     [rbp+1400h+var_1460], rax
0x180002bf5  jmp     short loc_180002BFB
0x180002bf7  mov     [rbp+1400h+var_1460], r12
0x180002bfb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002c02  test    rax, rax
0x180002c05  jz      short loc_180002C11
0x180002c07  lea     rcx, [rsp+1500h+var_14E0]
0x180002c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c11  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002c18  test    rax, rax
0x180002c1b  jz      short loc_180002C31
0x180002c1d  mov     r8d, 400h
0x180002c23  lea     rdx, [rbp+1400h+var_1440]
0x180002c27  lea     rcx, [rsp+1500h+var_14E0]
0x180002c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c31  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002c38  test    rax, rax
0x180002c3b  jz      short loc_180002C47
0x180002c3d  lea     rcx, [rsp+1500h+var_14E0]
0x180002c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c47  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002c4e  test    rax, rax
0x180002c51  jz      short loc_180002C64
0x180002c53  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002c58  jnz     short loc_180002C64
0x180002c5a  lea     rcx, [rsp+1500h+var_14E0]
0x180002c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c64  cmp     [rsp+1500h+var_14D8], r12d
0x180002c69  jge     loc_180002D66
0x180002c6f  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002c76  jnz     short loc_180002C97
0x180002c78  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002c7f  test    rax, rax
0x180002c82  jz      short loc_180002C8D
0x180002c84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c89  test    al, al
0x180002c8b  jmp     short loc_180002C95
0x180002c8d  call    cs:__imp_IsDebuggerPresent
0x180002c93  test    eax, eax
0x180002c95  jz      short loc_180002C9E
0x180002c97  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002c9c  jz      short loc_180002CC4
0x180002c9e  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ca5  test    rax, rax
0x180002ca8  jz      short loc_180002D1D
0x180002caa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002cb1  jnz     short loc_180002D1D
0x180002cb3  xor     r8d, r8d
0x180002cb6  lea     rcx, [rsp+1500h+var_14E0]
0x180002cbb  xor     edx, edx
0x180002cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cc2  jmp     short loc_180002D1D
0x180002cc4  mov     rax, cs:g_pfnResultLoggingCallback
0x180002ccb  mov     ebx, 800h
0x180002cd0  test    rax, rax
0x180002cd3  jz      short loc_180002CF2
0x180002cd5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002cdc  jnz     short loc_180002CF2
0x180002cde  mov     r8d, ebx
0x180002ce1  lea     rdx, [rbp+1400h+OutputString]
0x180002ce8  lea     rcx, [rsp+1500h+var_14E0]
0x180002ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cf2  cmp     [rbp+1400h+OutputString], r12w
0x180002cfa  jnz     short loc_180002D10
0x180002cfc  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180002d01  mov     rdx, rbx; unsigned __int16 *
0x180002d04  lea     rcx, [rbp+1400h+OutputString]; this
0x180002d0b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002d10  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180002d17  call    cs:__imp_OutputDebugStringW
0x180002d1d  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180002d22  jnz     short loc_180002D2D
0x180002d24  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002d2b  jz      short loc_180002D3E
0x180002d2d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002d34  test    rax, rax
0x180002d37  jz      short loc_180002D3E
0x180002d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d3e  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180002d43  jnz     short loc_180002D6C
0x180002d45  mov     rcx, [rbp+1400h+var_40]
0x180002d4c  xor     rcx, rsp; StackCookie
0x180002d4f  call    __security_check_cookie
0x180002d54  add     rsp, 14D0h
0x180002d5b  pop     r15
0x180002d5d  pop     r14
0x180002d5f  pop     r12
0x180002d61  pop     rdi
0x180002d62  pop     rsi
0x180002d63  pop     rbx
0x180002d64  pop     rbp
0x180002d65  retn
0x180002d66  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180002d6c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002d71  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
