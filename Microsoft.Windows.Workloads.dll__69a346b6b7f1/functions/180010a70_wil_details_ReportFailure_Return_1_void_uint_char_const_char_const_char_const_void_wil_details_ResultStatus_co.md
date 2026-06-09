# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180010a70`
- end: `0x180010d0b`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `667`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180010d10`

## callees

- `0x180002c90`
- `0x180002e40`
- `0x180002f70`
- `0x1800035a0`
- `0x180010a70`
- `0x180034ef0`
- `0x180035c10`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180010c18`
- `KERNEL32!IsDebuggerPresent` at `0x180010c18`
- `KERNEL32!GetCurrentThreadId` at `0x180010b1e`
- `KERNEL32!GetCurrentThreadId` at `0x180010b1e`
- `KERNEL32!OutputDebugStringW` at `0x180010ca9`
- `KERNEL32!OutputDebugStringW` at `0x180010ca9`

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
  int IsDebuggerPresent; // ebx
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // r8
  bool v15; // zf
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  _WORD *v24; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h]
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

  IsDebuggerPresent = 0;
  OutputString[0] = 0;
  v39[0] = 0;
  v21 = *a7;
  v22 = a7[1];
  v12 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, a2);
  v19 = 1;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v20 = v13;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v15 = *a8 == 0, v24 = a8, v15) )
    v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v28 = a3;
  v29 = a2;
  v30 = v12;
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
    ModuleName = wil::details::g_pfnGetModuleName(v17);
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17)),
         IsDebuggerPresent))
    && (v20 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v19, v18);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v16);
}

```

## disassembly

```asm
0x180010a70  push    rbp
0x180010a72  push    rbx
0x180010a73  push    rsi
0x180010a74  push    rdi
0x180010a75  push    r12
0x180010a77  push    r14
0x180010a79  push    r15
0x180010a7b  lea     rbp, [rsp-13D0h]
0x180010a83  mov     eax, 14D0h
0x180010a88  call    _alloca_probe
0x180010a8d  sub     rsp, rax
0x180010a90  mov     rax, cs:__security_cookie
0x180010a97  xor     rax, rsp
0x180010a9a  mov     [rbp+1400h+var_40], rax
0x180010aa1  mov     r14, r8
0x180010aa4  mov     esi, edx
0x180010aa6  mov     rdi, rcx
0x180010aa9  mov     r15, [rbp+1400h+arg_28]
0x180010ab0  xor     ebx, ebx
0x180010ab2  mov     [rbp+1400h+OutputString], bx
0x180010ab9  mov     [rbp+1400h+var_1440], bl
0x180010abc  mov     r8, [rbp+1400h+arg_30]
0x180010ac3  mov     ecx, [r8]; this
0x180010ac6  mov     [rsp+1500h+var_14D8], ecx
0x180010aca  mov     eax, [r8+4]
0x180010ace  mov     [rsp+1500h+var_14D4], eax
0x180010ad2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180010ad7  mov     r12d, eax
0x180010ada  mov     edx, 1
0x180010adf  mov     dword ptr [rsp+1500h+var_14E0], edx
0x180010ae3  mov     ecx, ebx
0x180010ae5  mov     eax, 8
0x180010aea  cmp     [r8+8], edx
0x180010aee  cmovz   ecx, eax
0x180010af1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180010af5  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, edx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180010afd  inc     edx
0x180010aff  mov     [rsp+1500h+var_14D0], edx
0x180010b03  mov     rcx, [rbp+1400h+arg_38]
0x180010b0a  test    rcx, rcx
0x180010b0d  jz      short loc_180010B19
0x180010b0f  cmp     [rcx], bx
0x180010b12  mov     [rsp+1500h+var_14C8], rcx
0x180010b17  jnz     short loc_180010B1E
0x180010b19  mov     [rsp+1500h+var_14C8], rbx
0x180010b1e  call    cs:__imp_GetCurrentThreadId
0x180010b24  mov     [rsp+1500h+var_14C0], eax
0x180010b28  mov     [rsp+1500h+var_14A8], r14
0x180010b2d  mov     [rsp+1500h+var_14A0], esi
0x180010b31  mov     [rsp+1500h+var_149C], r12d
0x180010b36  mov     [rsp+1500h+var_14B8], rbx
0x180010b3b  mov     [rsp+1500h+var_14B0], rbx
0x180010b40  mov     [rbp+1400h+var_1458], r15
0x180010b44  mov     [rbp+1400h+var_1450], rdi
0x180010b48  mov     [rsp+1500h+var_1498], rbx
0x180010b4d  xorps   xmm0, xmm0
0x180010b50  xor     eax, eax
0x180010b52  movups  [rbp+1400h+var_1478], xmm0
0x180010b56  mov     [rbp+1400h+var_1468], rax
0x180010b5a  xorps   xmm1, xmm1
0x180010b5d  movups  [rsp+1500h+var_1490], xmm1
0x180010b62  mov     [rbp+1400h+var_1480], rax
0x180010b66  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180010b6d  test    rax, rax
0x180010b70  jz      short loc_180010B7E
0x180010b72  call    cs:__guard_dispatch_icall_fptr
0x180010b78  mov     [rbp+1400h+var_1460], rax
0x180010b7c  jmp     short loc_180010B82
0x180010b7e  mov     [rbp+1400h+var_1460], rbx
0x180010b82  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180010b89  test    rax, rax
0x180010b8c  jz      short loc_180010B99
0x180010b8e  lea     rcx, [rsp+1500h+var_14E0]
0x180010b93  call    cs:__guard_dispatch_icall_fptr
0x180010b99  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180010ba0  test    rax, rax
0x180010ba3  jz      short loc_180010BBA
0x180010ba5  mov     r8d, 400h
0x180010bab  lea     rdx, [rbp+1400h+var_1440]
0x180010baf  lea     rcx, [rsp+1500h+var_14E0]
0x180010bb4  call    cs:__guard_dispatch_icall_fptr
0x180010bba  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010bc1  test    rax, rax
0x180010bc4  jz      short loc_180010BD1
0x180010bc6  lea     rcx, [rsp+1500h+var_14E0]
0x180010bcb  call    cs:__guard_dispatch_icall_fptr
0x180010bd1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010bd8  test    rax, rax
0x180010bdb  jz      short loc_180010BEF
0x180010bdd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180010be2  jnz     short loc_180010BEF
0x180010be4  lea     rcx, [rsp+1500h+var_14E0]
0x180010be9  call    cs:__guard_dispatch_icall_fptr
0x180010bef  cmp     [rsp+1500h+var_14D8], ebx
0x180010bf3  jge     loc_180010D05
0x180010bf9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, bl; bool wil::g_fIsDebuggerPresent
0x180010bff  jnz     short loc_180010C27
0x180010c01  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180010c08  test    rax, rax
0x180010c0b  jz      short loc_180010C18
0x180010c0d  call    cs:__guard_dispatch_icall_fptr
0x180010c13  movzx   ebx, al
0x180010c16  jmp     short loc_180010C23
0x180010c18  call    cs:__imp_IsDebuggerPresent
0x180010c1e  test    eax, eax
0x180010c20  setnz   bl
0x180010c23  test    ebx, ebx
0x180010c25  jz      short loc_180010C2E
0x180010c27  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180010c2c  jz      short loc_180010C55
0x180010c2e  mov     rax, cs:g_pfnResultLoggingCallback
0x180010c35  test    rax, rax
0x180010c38  jz      short loc_180010CAF
0x180010c3a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180010c41  jnz     short loc_180010CAF
0x180010c43  xor     r8d, r8d
0x180010c46  xor     edx, edx
0x180010c48  lea     rcx, [rsp+1500h+var_14E0]
0x180010c4d  call    cs:__guard_dispatch_icall_fptr
0x180010c53  jmp     short loc_180010CAF
0x180010c55  mov     rax, cs:g_pfnResultLoggingCallback
0x180010c5c  test    rax, rax
0x180010c5f  jz      short loc_180010C82
0x180010c61  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180010c68  jnz     short loc_180010C82
0x180010c6a  mov     r8d, 800h
0x180010c70  lea     rdx, [rbp+1400h+OutputString]
0x180010c77  lea     rcx, [rsp+1500h+var_14E0]
0x180010c7c  call    cs:__guard_dispatch_icall_fptr
0x180010c82  cmp     [rbp+1400h+OutputString], 0
0x180010c8a  jnz     short loc_180010CA2
0x180010c8c  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180010c91  mov     edx, 800h; wchar_t *
0x180010c96  lea     rcx, [rbp+1400h+OutputString]; this
0x180010c9d  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180010ca2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180010ca9  call    cs:__imp_OutputDebugStringW
0x180010caf  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180010cb4  jnz     short loc_180010CBF
0x180010cb6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x180010cbd  jz      short loc_180010CD2
0x180010cbf  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180010cc6  test    rax, rax
0x180010cc9  jz      short loc_180010CD2
0x180010ccb  call    cs:__guard_dispatch_icall_fptr
0x180010cd1  nop
0x180010cd2  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180010cd7  jnz     short loc_180010CFA
0x180010cd9  mov     rcx, [rbp+1400h+var_40]
0x180010ce0  xor     rcx, rsp; StackCookie
0x180010ce3  call    __security_check_cookie
0x180010ce8  add     rsp, 14D0h
0x180010cef  pop     r15
0x180010cf1  pop     r14
0x180010cf3  pop     r12
0x180010cf5  pop     rdi
0x180010cf6  pop     rsi
0x180010cf7  pop     rbx
0x180010cf8  pop     rbp
0x180010cf9  retn
0x180010cfa  lea     rcx, [rsp+1500h+var_14E0]; this
0x180010cff  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180010d05  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
