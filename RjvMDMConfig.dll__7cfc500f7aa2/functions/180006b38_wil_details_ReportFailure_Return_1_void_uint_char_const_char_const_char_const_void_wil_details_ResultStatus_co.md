# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180006b38`
- end: `0x180006dd6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `670`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800067f8`

## callees

- `0x180001c60`
- `0x1800026d8`
- `0x180003be4`
- `0x180006b38`
- `0x18000bff0`
- `0x180011170`
- `0x18001132c`
- `0x18001cf10`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006be5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006be5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006d6f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006d6f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006cdf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006cdf`

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
0x180006b38  push    rbp
0x180006b3a  push    rbx
0x180006b3b  push    rsi
0x180006b3c  push    rdi
0x180006b3d  push    r12
0x180006b3f  push    r14
0x180006b41  push    r15
0x180006b43  lea     rbp, [rsp-13D0h]
0x180006b4b  mov     eax, 14D0h
0x180006b50  call    _alloca_probe
0x180006b55  sub     rsp, rax
0x180006b58  mov     rax, cs:__security_cookie
0x180006b5f  xor     rax, rsp
0x180006b62  mov     [rbp+1400h+var_40], rax
0x180006b69  mov     rdi, [rbp+1400h+arg_28]
0x180006b70  mov     r14, r8
0x180006b73  mov     esi, edx
0x180006b75  mov     r15, rcx
0x180006b78  xor     edx, edx; Val
0x180006b7a  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180006b7f  mov     r8d, 98h; Size
0x180006b85  call    memset_0
0x180006b8a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180006b91  xor     r12d, r12d
0x180006b94  mov     [rbp+1400h+OutputString], r12w
0x180006b9c  mov     [rbp+1400h+var_1440], r12b
0x180006ba0  mov     ecx, [rdx]; this
0x180006ba2  mov     eax, [rdx+4]
0x180006ba5  mov     [rsp+1500h+var_14D8], ecx
0x180006ba9  mov     [rsp+1500h+var_14D4], eax
0x180006bad  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006bb2  cmp     dword ptr [rdx+8], 1
0x180006bb6  mov     ebx, eax
0x180006bb8  lea     eax, [r12+8]
0x180006bbd  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180006bc5  mov     ecx, r12d
0x180006bc8  cmovz   ecx, eax
0x180006bcb  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180006bcf  lea     ecx, [rax-7]
0x180006bd2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006bda  inc     ecx
0x180006bdc  mov     [rsp+1500h+var_14C8], r12
0x180006be1  mov     [rsp+1500h+var_14D0], ecx
0x180006be5  call    cs:__imp_GetCurrentThreadId
0x180006bec  nop     dword ptr [rax+rax+00h]
0x180006bf1  xorps   xmm0, xmm0
0x180006bf4  mov     [rsp+1500h+var_14A8], r14
0x180006bf9  mov     [rsp+1500h+var_14C0], eax
0x180006bfd  xorps   xmm1, xmm1
0x180006c00  xor     eax, eax
0x180006c02  mov     [rsp+1500h+var_14A0], esi
0x180006c06  mov     [rbp+1400h+var_1468], rax
0x180006c0a  mov     [rbp+1400h+var_1480], rax
0x180006c0e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006c15  mov     [rsp+1500h+var_149C], ebx
0x180006c19  mov     [rsp+1500h+var_14B8], r12
0x180006c1e  mov     [rsp+1500h+var_14B0], r12
0x180006c23  mov     [rbp+1400h+var_1458], rdi
0x180006c27  mov     [rbp+1400h+var_1450], r15
0x180006c2b  mov     [rsp+1500h+var_1498], r12
0x180006c30  movups  [rbp+1400h+var_1478], xmm0
0x180006c34  movups  [rsp+1500h+var_1490], xmm1
0x180006c39  test    rax, rax
0x180006c3c  jz      short loc_180006C49
0x180006c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c43  mov     [rbp+1400h+var_1460], rax
0x180006c47  jmp     short loc_180006C4D
0x180006c49  mov     [rbp+1400h+var_1460], r12
0x180006c4d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006c54  test    rax, rax
0x180006c57  jz      short loc_180006C63
0x180006c59  lea     rcx, [rsp+1500h+var_14E0]
0x180006c5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c63  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006c6a  test    rax, rax
0x180006c6d  jz      short loc_180006C83
0x180006c6f  mov     r8d, 400h
0x180006c75  lea     rdx, [rbp+1400h+var_1440]
0x180006c79  lea     rcx, [rsp+1500h+var_14E0]
0x180006c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c83  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006c8a  test    rax, rax
0x180006c8d  jz      short loc_180006C99
0x180006c8f  lea     rcx, [rsp+1500h+var_14E0]
0x180006c94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c99  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006ca0  test    rax, rax
0x180006ca3  jz      short loc_180006CB6
0x180006ca5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006caa  jnz     short loc_180006CB6
0x180006cac  lea     rcx, [rsp+1500h+var_14E0]
0x180006cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cb6  cmp     [rsp+1500h+var_14D8], r12d
0x180006cbb  jge     loc_180006DD0
0x180006cc1  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180006cc8  jnz     short loc_180006CEF
0x180006cca  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006cd1  test    rax, rax
0x180006cd4  jz      short loc_180006CDF
0x180006cd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cdb  test    al, al
0x180006cdd  jmp     short loc_180006CED
0x180006cdf  call    cs:__imp_IsDebuggerPresent
0x180006ce6  nop     dword ptr [rax+rax+00h]
0x180006ceb  test    eax, eax
0x180006ced  jz      short loc_180006CF6
0x180006cef  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006cf4  jz      short loc_180006D1C
0x180006cf6  mov     rax, cs:g_pfnResultLoggingCallback
0x180006cfd  test    rax, rax
0x180006d00  jz      short loc_180006D7B
0x180006d02  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180006d09  jnz     short loc_180006D7B
0x180006d0b  xor     r8d, r8d
0x180006d0e  lea     rcx, [rsp+1500h+var_14E0]
0x180006d13  xor     edx, edx
0x180006d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d1a  jmp     short loc_180006D7B
0x180006d1c  mov     rax, cs:g_pfnResultLoggingCallback
0x180006d23  mov     ebx, 800h
0x180006d28  test    rax, rax
0x180006d2b  jz      short loc_180006D4A
0x180006d2d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180006d34  jnz     short loc_180006D4A
0x180006d36  mov     r8d, ebx
0x180006d39  lea     rdx, [rbp+1400h+OutputString]
0x180006d40  lea     rcx, [rsp+1500h+var_14E0]
0x180006d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d4a  cmp     [rbp+1400h+OutputString], r12w
0x180006d52  jnz     short loc_180006D68
0x180006d54  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180006d59  mov     rdx, rbx; unsigned __int16 *
0x180006d5c  lea     rcx, [rbp+1400h+OutputString]; this
0x180006d63  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006d68  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180006d6f  call    cs:__imp_OutputDebugStringW
0x180006d76  nop     dword ptr [rax+rax+00h]
0x180006d7b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180006d80  jnz     short loc_180006D8B
0x180006d82  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180006d89  jz      short loc_180006D9C
0x180006d8b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006d92  test    rax, rax
0x180006d95  jz      short loc_180006D9C
0x180006d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d9c  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180006da1  jnz     short loc_180006DC5
0x180006da3  mov     rcx, [rbp+1400h+var_40]
0x180006daa  xor     rcx, rsp; StackCookie
0x180006dad  call    __security_check_cookie
0x180006db2  add     rsp, 14D0h
0x180006db9  pop     r15
0x180006dbb  pop     r14
0x180006dbd  pop     r12
0x180006dbf  pop     rdi
0x180006dc0  pop     rsi
0x180006dc1  pop     rbx
0x180006dc2  pop     rbp
0x180006dc3  retn
0x180006dc5  lea     rcx, [rsp+1500h+var_14E0]; this
0x180006dca  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180006dd0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
