# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140009c40`
- end: `0x140009ee6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140009590`

## callees

- `0x140008660`
- `0x1400090ec`
- `0x140009c40`
- `0x14000b4c4`
- `0x14000c100`
- `0x14000d200`
- `0x14000d2dc`
- `0x1400167a0`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009d06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140009d06`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140009e85`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140009e85`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140009dfb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140009dfb`

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
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x140009c40  push    rbp
0x140009c42  push    rbx
0x140009c43  push    rsi
0x140009c44  push    rdi
0x140009c45  push    r12
0x140009c47  push    r14
0x140009c49  push    r15
0x140009c4b  lea     rbp, [rsp-13D0h]
0x140009c53  mov     eax, 14D0h
0x140009c58  call    _alloca_probe
0x140009c5d  sub     rsp, rax
0x140009c60  mov     rax, cs:__security_cookie
0x140009c67  xor     rax, rsp
0x140009c6a  mov     [rbp+1400h+var_40], rax
0x140009c71  mov     rsi, r8
0x140009c74  mov     edi, edx
0x140009c76  mov     rbx, rcx
0x140009c79  mov     r14, [rbp+1400h+arg_28]
0x140009c80  xor     edx, edx; Val
0x140009c82  mov     r8d, 98h; Size
0x140009c88  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140009c8d  call    memset_0
0x140009c92  nop
0x140009c93  xor     r12d, r12d
0x140009c96  mov     [rbp+1400h+OutputString], r12w
0x140009c9e  mov     [rbp+1400h+var_1440], r12b
0x140009ca2  mov     rdx, [rbp+1400h+arg_30]; int
0x140009ca9  mov     ecx, [rdx]; this
0x140009cab  mov     [rsp+1500h+var_14D8], ecx
0x140009caf  mov     eax, [rdx+4]
0x140009cb2  mov     [rsp+1500h+var_14D4], eax
0x140009cb6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140009cbb  mov     r15d, eax
0x140009cbe  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140009cc6  mov     ecx, r12d
0x140009cc9  lea     eax, [r12+8]
0x140009cce  cmp     dword ptr [rdx+8], 1
0x140009cd2  cmovz   ecx, eax
0x140009cd5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140009cd9  lea     ecx, [rax-7]
0x140009cdc  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140009ce4  inc     ecx
0x140009ce6  mov     [rsp+1500h+var_14D0], ecx
0x140009cea  mov     rcx, [rbp+1400h+arg_38]
0x140009cf1  test    rcx, rcx
0x140009cf4  jz      short loc_140009D01
0x140009cf6  cmp     [rcx], r12w
0x140009cfa  mov     [rsp+1500h+var_14C8], rcx
0x140009cff  jnz     short loc_140009D06
0x140009d01  mov     [rsp+1500h+var_14C8], r12
0x140009d06  call    cs:__imp_GetCurrentThreadId
0x140009d0c  mov     [rsp+1500h+var_14C0], eax
0x140009d10  mov     [rsp+1500h+var_14A8], rsi
0x140009d15  mov     [rsp+1500h+var_14A0], edi
0x140009d19  mov     [rsp+1500h+var_149C], r15d
0x140009d1e  mov     [rsp+1500h+var_14B8], r12
0x140009d23  mov     [rsp+1500h+var_14B0], r12
0x140009d28  mov     [rbp+1400h+var_1458], r14
0x140009d2c  mov     [rbp+1400h+var_1450], rbx
0x140009d30  mov     [rsp+1500h+var_1498], r12
0x140009d35  xorps   xmm0, xmm0
0x140009d38  xor     eax, eax
0x140009d3a  movups  [rbp+1400h+var_1478], xmm0
0x140009d3e  mov     [rbp+1400h+var_1468], rax
0x140009d42  xorps   xmm1, xmm1
0x140009d45  movups  [rsp+1500h+var_1490], xmm1
0x140009d4a  mov     [rbp+1400h+var_1480], rax
0x140009d4e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140009d55  test    rax, rax
0x140009d58  jz      short loc_140009D65
0x140009d5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d5f  mov     [rbp+1400h+var_1460], rax
0x140009d63  jmp     short loc_140009D69
0x140009d65  mov     [rbp+1400h+var_1460], r12
0x140009d69  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140009d70  test    rax, rax
0x140009d73  jz      short loc_140009D7F
0x140009d75  lea     rcx, [rsp+1500h+var_14E0]
0x140009d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d7f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140009d86  test    rax, rax
0x140009d89  jz      short loc_140009D9F
0x140009d8b  mov     r8d, 400h
0x140009d91  lea     rdx, [rbp+1400h+var_1440]
0x140009d95  lea     rcx, [rsp+1500h+var_14E0]
0x140009d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d9f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140009da6  test    rax, rax
0x140009da9  jz      short loc_140009DB5
0x140009dab  lea     rcx, [rsp+1500h+var_14E0]
0x140009db0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009db5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140009dbc  test    rax, rax
0x140009dbf  jz      short loc_140009DD2
0x140009dc1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140009dc6  jnz     short loc_140009DD2
0x140009dc8  lea     rcx, [rsp+1500h+var_14E0]
0x140009dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009dd2  cmp     [rsp+1500h+var_14D8], r12d
0x140009dd7  jge     loc_140009EE0
0x140009ddd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140009de4  jnz     short loc_140009E05
0x140009de6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140009ded  test    rax, rax
0x140009df0  jz      short loc_140009DFB
0x140009df2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009df7  test    al, al
0x140009df9  jmp     short loc_140009E03
0x140009dfb  call    cs:__imp_IsDebuggerPresent
0x140009e01  test    eax, eax
0x140009e03  jz      short loc_140009E0C
0x140009e05  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140009e0a  jz      short loc_140009E32
0x140009e0c  mov     rax, cs:g_pfnResultLoggingCallback
0x140009e13  test    rax, rax
0x140009e16  jz      short loc_140009E8B
0x140009e18  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140009e1f  jnz     short loc_140009E8B
0x140009e21  xor     r8d, r8d
0x140009e24  xor     edx, edx
0x140009e26  lea     rcx, [rsp+1500h+var_14E0]
0x140009e2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e30  jmp     short loc_140009E8B
0x140009e32  mov     ebx, 800h
0x140009e37  mov     rax, cs:g_pfnResultLoggingCallback
0x140009e3e  test    rax, rax
0x140009e41  jz      short loc_140009E60
0x140009e43  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140009e4a  jnz     short loc_140009E60
0x140009e4c  mov     r8d, ebx
0x140009e4f  lea     rdx, [rbp+1400h+OutputString]
0x140009e56  lea     rcx, [rsp+1500h+var_14E0]
0x140009e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e60  cmp     [rbp+1400h+OutputString], r12w
0x140009e68  jnz     short loc_140009E7E
0x140009e6a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140009e6f  mov     rdx, rbx; unsigned __int16 *
0x140009e72  lea     rcx, [rbp+1400h+OutputString]; this
0x140009e79  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140009e7e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140009e85  call    cs:__imp_OutputDebugStringW
0x140009e8b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140009e90  jnz     short loc_140009E9B
0x140009e92  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140009e99  jz      short loc_140009EAD
0x140009e9b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140009ea2  test    rax, rax
0x140009ea5  jz      short loc_140009EAD
0x140009ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009eac  nop
0x140009ead  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140009eb2  jnz     short loc_140009ED5
0x140009eb4  mov     rcx, [rbp+1400h+var_40]
0x140009ebb  xor     rcx, rsp; StackCookie
0x140009ebe  call    __security_check_cookie
0x140009ec3  add     rsp, 14D0h
0x140009eca  pop     r15
0x140009ecc  pop     r14
0x140009ece  pop     r12
0x140009ed0  pop     rdi
0x140009ed1  pop     rsi
0x140009ed2  pop     rbx
0x140009ed3  pop     rbp
0x140009ed4  retn
0x140009ed5  lea     rcx, [rsp+1500h+var_14E0]; this
0x140009eda  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140009ee0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
