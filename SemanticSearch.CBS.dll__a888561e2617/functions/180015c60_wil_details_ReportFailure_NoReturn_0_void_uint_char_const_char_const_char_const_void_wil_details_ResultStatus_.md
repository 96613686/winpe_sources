# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180015c60`
- end: `0x180015f10`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `688`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180015f10`

## callees

- `0x180015c60`
- `0x180015fe0`
- `0x1800161b0`
- `0x180016290`
- `0x180016870`
- `0x1800168c0`
- `0x1800514d0`
- `0x18005e260`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180015ea2`
- `KERNEL32!OutputDebugStringW` at `0x180015ea2`
- `KERNEL32!GetCurrentThreadId` at `0x180015cfa`
- `KERNEL32!GetCurrentThreadId` at `0x180015cfa`
- `KERNEL32!IsDebuggerPresent` at `0x180015dfd`
- `KERNEL32!IsDebuggerPresent` at `0x180015dfd`

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
  bool v10; // r13
  int IsDebuggerPresent; // r12d
  int v12; // ebx
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // bl
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
  IsDebuggerPresent = 0;
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v21 = v13;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v12;
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
    ModuleName = wil::details::g_pfnGetModuleName(v16);
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  v18 = (wil::g_fIsDebuggerPresent
      || (!wil::g_pfnIsDebuggerPresent
        ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
        : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16)),
          IsDebuggerPresent))
     && (v21 & 2) == 0;
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (wchar_t *)0x800, (unsigned __int64)&v20, v17);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v15);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v15);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x180015c60  mov     [rsp-8+arg_18], rbx
0x180015c65  push    rbp
0x180015c66  push    rsi
0x180015c67  push    rdi
0x180015c68  push    r12
0x180015c6a  push    r13
0x180015c6c  push    r14
0x180015c6e  push    r15
0x180015c70  lea     rbp, [rsp-13C0h]
0x180015c78  mov     eax, 14C0h
0x180015c7d  call    _alloca_probe
0x180015c82  sub     rsp, rax
0x180015c85  mov     r14, r8
0x180015c88  mov     esi, edx
0x180015c8a  mov     r15, rcx
0x180015c8d  mov     rdi, [rbp+13F0h+arg_28]
0x180015c94  cmp     cs:g_pfnThrowPlatformException, 0
0x180015c9c  setnz   r13b
0x180015ca0  xor     r12d, r12d
0x180015ca3  mov     [rbp+13F0h+OutputString], r12w
0x180015cab  mov     [rbp+13F0h+var_1430], r12b
0x180015caf  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180015cb6  mov     ecx, [rdx]; this
0x180015cb8  mov     [rsp+14F0h+var_14C8], ecx
0x180015cbc  mov     eax, [rdx+4]
0x180015cbf  mov     [rsp+14F0h+var_14C4], eax
0x180015cc3  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180015cc8  mov     ebx, eax
0x180015cca  mov     dword ptr [rsp+14F0h+var_14D0], r12d
0x180015ccf  mov     ecx, r12d
0x180015cd2  mov     eax, 8
0x180015cd7  cmp     dword ptr [rdx+8], 1
0x180015cdb  cmovz   ecx, eax
0x180015cde  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180015ce2  mov     ecx, 1
0x180015ce7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180015cef  inc     ecx
0x180015cf1  mov     [rsp+14F0h+var_14C0], ecx
0x180015cf5  mov     [rsp+14F0h+var_14B8], r12
0x180015cfa  call    cs:__imp_GetCurrentThreadId
0x180015d00  mov     [rsp+14F0h+var_14B0], eax
0x180015d04  mov     [rsp+14F0h+var_1498], r14
0x180015d09  mov     [rsp+14F0h+var_1490], esi
0x180015d0d  mov     [rsp+14F0h+var_148C], ebx
0x180015d11  mov     [rsp+14F0h+var_14A8], r12
0x180015d16  mov     [rsp+14F0h+var_14A0], r12
0x180015d1b  mov     [rbp+13F0h+var_1448], rdi
0x180015d1f  mov     [rbp+13F0h+var_1440], r15
0x180015d23  mov     [rsp+14F0h+var_1488], r12
0x180015d28  xorps   xmm0, xmm0
0x180015d2b  xor     eax, eax
0x180015d2d  movups  [rbp+13F0h+var_1468], xmm0
0x180015d31  mov     [rbp+13F0h+var_1458], rax
0x180015d35  xorps   xmm1, xmm1
0x180015d38  movups  [rsp+14F0h+var_1480], xmm1
0x180015d3d  mov     [rbp+13F0h+var_1470], rax
0x180015d41  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180015d48  test    rax, rax
0x180015d4b  jz      short loc_180015D59
0x180015d4d  call    cs:__guard_dispatch_icall_fptr
0x180015d53  mov     [rbp+13F0h+var_1450], rax
0x180015d57  jmp     short loc_180015D5D
0x180015d59  mov     [rbp+13F0h+var_1450], r12
0x180015d5d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180015d64  test    rax, rax
0x180015d67  jz      short loc_180015D74
0x180015d69  lea     rcx, [rsp+14F0h+var_14D0]
0x180015d6e  call    cs:__guard_dispatch_icall_fptr
0x180015d74  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180015d7b  test    rax, rax
0x180015d7e  jz      short loc_180015D95
0x180015d80  mov     r8d, 400h
0x180015d86  lea     rdx, [rbp+13F0h+var_1430]
0x180015d8a  lea     rcx, [rsp+14F0h+var_14D0]
0x180015d8f  call    cs:__guard_dispatch_icall_fptr
0x180015d95  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015d9c  test    rax, rax
0x180015d9f  jz      short loc_180015DAC
0x180015da1  lea     rcx, [rsp+14F0h+var_14D0]
0x180015da6  call    cs:__guard_dispatch_icall_fptr
0x180015dac  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015db3  test    rax, rax
0x180015db6  jz      short loc_180015DCF
0x180015db8  test    r13b, r13b
0x180015dbb  jnz     short loc_180015DCF
0x180015dbd  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180015dc2  jnz     short loc_180015DCF
0x180015dc4  lea     rcx, [rsp+14F0h+var_14D0]
0x180015dc9  call    cs:__guard_dispatch_icall_fptr
0x180015dcf  cmp     [rsp+14F0h+var_14C8], r12d
0x180015dd4  jl      short loc_180015DDC
0x180015dd6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180015ddc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180015de3  jnz     short loc_180015E0E
0x180015de5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180015dec  test    rax, rax
0x180015def  jz      short loc_180015DFD
0x180015df1  call    cs:__guard_dispatch_icall_fptr
0x180015df7  movzx   r12d, al
0x180015dfb  jmp     short loc_180015E09
0x180015dfd  call    cs:__imp_IsDebuggerPresent
0x180015e03  test    eax, eax
0x180015e05  setnz   r12b
0x180015e09  test    r12d, r12d
0x180015e0c  jz      short loc_180015E19
0x180015e0e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180015e13  jnz     short loc_180015E19
0x180015e15  mov     bl, 1
0x180015e17  jmp     short loc_180015E1B
0x180015e19  xor     bl, bl
0x180015e1b  test    r13b, r13b
0x180015e1e  jnz     short loc_180015E4A
0x180015e20  test    bl, bl
0x180015e22  jnz     short loc_180015E4A
0x180015e24  mov     rax, cs:g_pfnResultLoggingCallback
0x180015e2b  test    rax, rax
0x180015e2e  jz      short loc_180015EA8
0x180015e30  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x180015e36  jnz     short loc_180015EA8
0x180015e38  xor     r8d, r8d
0x180015e3b  xor     edx, edx
0x180015e3d  lea     rcx, [rsp+14F0h+var_14D0]
0x180015e42  call    cs:__guard_dispatch_icall_fptr
0x180015e48  jmp     short loc_180015EA8
0x180015e4a  mov     rax, cs:g_pfnResultLoggingCallback
0x180015e51  test    rax, rax
0x180015e54  jz      short loc_180015E77
0x180015e56  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180015e5d  jnz     short loc_180015E77
0x180015e5f  mov     r8d, 800h
0x180015e65  lea     rdx, [rbp+13F0h+OutputString]
0x180015e6c  lea     rcx, [rsp+14F0h+var_14D0]
0x180015e71  call    cs:__guard_dispatch_icall_fptr
0x180015e77  cmp     [rbp+13F0h+OutputString], 0
0x180015e7f  jnz     short loc_180015E97
0x180015e81  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180015e86  mov     edx, 800h; wchar_t *
0x180015e8b  lea     rcx, [rbp+13F0h+OutputString]; Buffer
0x180015e92  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180015e97  test    bl, bl
0x180015e99  jz      short loc_180015EA8
0x180015e9b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180015ea2  call    cs:__imp_OutputDebugStringW
0x180015ea8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180015ead  jnz     short loc_180015EB8
0x180015eaf  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x180015eb6  jz      short loc_180015ECB
0x180015eb8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180015ebf  test    rax, rax
0x180015ec2  jz      short loc_180015ECB
0x180015ec4  call    cs:__guard_dispatch_icall_fptr
0x180015eca  nop
0x180015ecb  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180015ed0  jz      short loc_180015EDD
0x180015ed2  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180015ed7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180015edd  test    r13b, r13b
0x180015ee0  jz      short loc_180015EFB
0x180015ee2  lea     rdx, [rbp+13F0h+OutputString]
0x180015ee9  lea     rcx, [rsp+14F0h+var_14D0]
0x180015eee  mov     rax, cs:g_pfnThrowPlatformException
0x180015ef5  call    cs:__guard_dispatch_icall_fptr
0x180015efb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180015f00  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180015f05  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180015f0a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
