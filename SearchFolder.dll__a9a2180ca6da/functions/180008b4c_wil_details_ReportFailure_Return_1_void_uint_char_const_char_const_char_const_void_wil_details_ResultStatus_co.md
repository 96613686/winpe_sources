# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180008b4c`
- end: `0x180008df2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800087b4`

## callees

- `0x180006900`
- `0x1800076dc`
- `0x180008b4c`
- `0x18000b394`
- `0x18000d0b8`
- `0x18000fad8`
- `0x18000fe60`
- `0x18004faa0`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008c12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008c12`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008d91`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008d91`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008d07`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008d07`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180008b4c  push    rbp
0x180008b4e  push    rbx
0x180008b4f  push    rsi
0x180008b50  push    rdi
0x180008b51  push    r12
0x180008b53  push    r14
0x180008b55  push    r15
0x180008b57  lea     rbp, [rsp-13D0h]
0x180008b5f  mov     eax, 14D0h
0x180008b64  call    _alloca_probe
0x180008b69  sub     rsp, rax
0x180008b6c  mov     rax, cs:__security_cookie
0x180008b73  xor     rax, rsp
0x180008b76  mov     [rbp+1400h+var_40], rax
0x180008b7d  mov     rsi, r8
0x180008b80  mov     edi, edx
0x180008b82  mov     rbx, rcx
0x180008b85  mov     r14, [rbp+1400h+arg_28]
0x180008b8c  xor     edx, edx; Val
0x180008b8e  mov     r8d, 98h; Size
0x180008b94  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180008b99  call    memset_0
0x180008b9e  nop
0x180008b9f  xor     r12d, r12d
0x180008ba2  mov     [rbp+1400h+OutputString], r12w
0x180008baa  mov     [rbp+1400h+var_1440], r12b
0x180008bae  mov     rdx, [rbp+1400h+arg_30]; int
0x180008bb5  mov     ecx, [rdx]; this
0x180008bb7  mov     [rsp+1500h+var_14D8], ecx
0x180008bbb  mov     eax, [rdx+4]
0x180008bbe  mov     [rsp+1500h+var_14D4], eax
0x180008bc2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008bc7  mov     r15d, eax
0x180008bca  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180008bd2  mov     ecx, r12d
0x180008bd5  lea     eax, [r12+8]
0x180008bda  cmp     dword ptr [rdx+8], 1
0x180008bde  cmovz   ecx, eax
0x180008be1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180008be5  lea     ecx, [rax-7]
0x180008be8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008bf0  inc     ecx
0x180008bf2  mov     [rsp+1500h+var_14D0], ecx
0x180008bf6  mov     rcx, [rbp+1400h+arg_38]
0x180008bfd  test    rcx, rcx
0x180008c00  jz      short loc_180008C0D
0x180008c02  cmp     [rcx], r12w
0x180008c06  mov     [rsp+1500h+var_14C8], rcx
0x180008c0b  jnz     short loc_180008C12
0x180008c0d  mov     [rsp+1500h+var_14C8], r12
0x180008c12  call    cs:__imp_GetCurrentThreadId
0x180008c18  mov     [rsp+1500h+var_14C0], eax
0x180008c1c  mov     [rsp+1500h+var_14A8], rsi
0x180008c21  mov     [rsp+1500h+var_14A0], edi
0x180008c25  mov     [rsp+1500h+var_149C], r15d
0x180008c2a  mov     [rsp+1500h+var_14B8], r12
0x180008c2f  mov     [rsp+1500h+var_14B0], r12
0x180008c34  mov     [rbp+1400h+var_1458], r14
0x180008c38  mov     [rbp+1400h+var_1450], rbx
0x180008c3c  mov     [rsp+1500h+var_1498], r12
0x180008c41  xorps   xmm0, xmm0
0x180008c44  xor     eax, eax
0x180008c46  movups  [rbp+1400h+var_1478], xmm0
0x180008c4a  mov     [rbp+1400h+var_1468], rax
0x180008c4e  xorps   xmm1, xmm1
0x180008c51  movups  [rsp+1500h+var_1490], xmm1
0x180008c56  mov     [rbp+1400h+var_1480], rax
0x180008c5a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008c61  test    rax, rax
0x180008c64  jz      short loc_180008C71
0x180008c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c6b  mov     [rbp+1400h+var_1460], rax
0x180008c6f  jmp     short loc_180008C75
0x180008c71  mov     [rbp+1400h+var_1460], r12
0x180008c75  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008c7c  test    rax, rax
0x180008c7f  jz      short loc_180008C8B
0x180008c81  lea     rcx, [rsp+1500h+var_14E0]
0x180008c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c8b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008c92  test    rax, rax
0x180008c95  jz      short loc_180008CAB
0x180008c97  mov     r8d, 400h
0x180008c9d  lea     rdx, [rbp+1400h+var_1440]
0x180008ca1  lea     rcx, [rsp+1500h+var_14E0]
0x180008ca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cab  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008cb2  test    rax, rax
0x180008cb5  jz      short loc_180008CC1
0x180008cb7  lea     rcx, [rsp+1500h+var_14E0]
0x180008cbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cc1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008cc8  test    rax, rax
0x180008ccb  jz      short loc_180008CDE
0x180008ccd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180008cd2  jnz     short loc_180008CDE
0x180008cd4  lea     rcx, [rsp+1500h+var_14E0]
0x180008cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cde  cmp     [rsp+1500h+var_14D8], r12d
0x180008ce3  jge     loc_180008DEC
0x180008ce9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180008cf0  jnz     short loc_180008D11
0x180008cf2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008cf9  test    rax, rax
0x180008cfc  jz      short loc_180008D07
0x180008cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d03  test    al, al
0x180008d05  jmp     short loc_180008D0F
0x180008d07  call    cs:__imp_IsDebuggerPresent
0x180008d0d  test    eax, eax
0x180008d0f  jz      short loc_180008D18
0x180008d11  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180008d16  jz      short loc_180008D3E
0x180008d18  mov     rax, cs:g_pfnResultLoggingCallback
0x180008d1f  test    rax, rax
0x180008d22  jz      short loc_180008D97
0x180008d24  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180008d2b  jnz     short loc_180008D97
0x180008d2d  xor     r8d, r8d
0x180008d30  xor     edx, edx
0x180008d32  lea     rcx, [rsp+1500h+var_14E0]
0x180008d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d3c  jmp     short loc_180008D97
0x180008d3e  mov     ebx, 800h
0x180008d43  mov     rax, cs:g_pfnResultLoggingCallback
0x180008d4a  test    rax, rax
0x180008d4d  jz      short loc_180008D6C
0x180008d4f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180008d56  jnz     short loc_180008D6C
0x180008d58  mov     r8d, ebx
0x180008d5b  lea     rdx, [rbp+1400h+OutputString]
0x180008d62  lea     rcx, [rsp+1500h+var_14E0]
0x180008d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d6c  cmp     [rbp+1400h+OutputString], r12w
0x180008d74  jnz     short loc_180008D8A
0x180008d76  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180008d7b  mov     rdx, rbx; unsigned __int16 *
0x180008d7e  lea     rcx, [rbp+1400h+OutputString]; this
0x180008d85  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008d8a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180008d91  call    cs:__imp_OutputDebugStringW
0x180008d97  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180008d9c  jnz     short loc_180008DA7
0x180008d9e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180008da5  jz      short loc_180008DB9
0x180008da7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008dae  test    rax, rax
0x180008db1  jz      short loc_180008DB9
0x180008db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008db8  nop
0x180008db9  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180008dbe  jnz     short loc_180008DE1
0x180008dc0  mov     rcx, [rbp+1400h+var_40]
0x180008dc7  xor     rcx, rsp; StackCookie
0x180008dca  call    __security_check_cookie
0x180008dcf  add     rsp, 14D0h
0x180008dd6  pop     r15
0x180008dd8  pop     r14
0x180008dda  pop     r12
0x180008ddc  pop     rdi
0x180008ddd  pop     rsi
0x180008dde  pop     rbx
0x180008ddf  pop     rbp
0x180008de0  retn
0x180008de1  lea     rcx, [rsp+1500h+var_14E0]; this
0x180008de6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180008dec  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
