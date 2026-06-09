# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18001d490`
- end: `0x18001d736`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800161f8`

## callees

- `0x180015be0`
- `0x18001a540`
- `0x18001b004`
- `0x18001d490`
- `0x18001e3d4`
- `0x18001ee90`
- `0x18001fe48`
- `0x1800d8c00`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d556`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d556`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001d64b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001d64b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d6d5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d6d5`

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
0x18001d490  push    rbp
0x18001d492  push    rbx
0x18001d493  push    rsi
0x18001d494  push    rdi
0x18001d495  push    r12
0x18001d497  push    r14
0x18001d499  push    r15
0x18001d49b  lea     rbp, [rsp-13D0h]
0x18001d4a3  mov     eax, 14D0h
0x18001d4a8  call    _alloca_probe
0x18001d4ad  sub     rsp, rax
0x18001d4b0  mov     rax, cs:__security_cookie
0x18001d4b7  xor     rax, rsp
0x18001d4ba  mov     [rbp+1400h+var_40], rax
0x18001d4c1  mov     rsi, r8
0x18001d4c4  mov     edi, edx
0x18001d4c6  mov     rbx, rcx
0x18001d4c9  mov     r14, [rbp+1400h+arg_28]
0x18001d4d0  xor     edx, edx; Val
0x18001d4d2  mov     r8d, 98h; Size
0x18001d4d8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18001d4dd  call    memset_0
0x18001d4e2  nop
0x18001d4e3  xor     r12d, r12d
0x18001d4e6  mov     [rbp+1400h+OutputString], r12w
0x18001d4ee  mov     [rbp+1400h+var_1440], r12b
0x18001d4f2  mov     rdx, [rbp+1400h+arg_30]; int
0x18001d4f9  mov     ecx, [rdx]; this
0x18001d4fb  mov     [rsp+1500h+var_14D8], ecx
0x18001d4ff  mov     eax, [rdx+4]
0x18001d502  mov     [rsp+1500h+var_14D4], eax
0x18001d506  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001d50b  mov     r15d, eax
0x18001d50e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18001d516  mov     ecx, r12d
0x18001d519  lea     eax, [r12+8]
0x18001d51e  cmp     dword ptr [rdx+8], 1
0x18001d522  cmovz   ecx, eax
0x18001d525  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18001d529  lea     ecx, [rax-7]
0x18001d52c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001d534  inc     ecx
0x18001d536  mov     [rsp+1500h+var_14D0], ecx
0x18001d53a  mov     rcx, [rbp+1400h+arg_38]
0x18001d541  test    rcx, rcx
0x18001d544  jz      short loc_18001D551
0x18001d546  cmp     [rcx], r12w
0x18001d54a  mov     [rsp+1500h+var_14C8], rcx
0x18001d54f  jnz     short loc_18001D556
0x18001d551  mov     [rsp+1500h+var_14C8], r12
0x18001d556  call    cs:__imp_GetCurrentThreadId
0x18001d55c  mov     [rsp+1500h+var_14C0], eax
0x18001d560  mov     [rsp+1500h+var_14A8], rsi
0x18001d565  mov     [rsp+1500h+var_14A0], edi
0x18001d569  mov     [rsp+1500h+var_149C], r15d
0x18001d56e  mov     [rsp+1500h+var_14B8], r12
0x18001d573  mov     [rsp+1500h+var_14B0], r12
0x18001d578  mov     [rbp+1400h+var_1458], r14
0x18001d57c  mov     [rbp+1400h+var_1450], rbx
0x18001d580  mov     [rsp+1500h+var_1498], r12
0x18001d585  xorps   xmm0, xmm0
0x18001d588  xor     eax, eax
0x18001d58a  movups  [rbp+1400h+var_1478], xmm0
0x18001d58e  mov     [rbp+1400h+var_1468], rax
0x18001d592  xorps   xmm1, xmm1
0x18001d595  movups  [rsp+1500h+var_1490], xmm1
0x18001d59a  mov     [rbp+1400h+var_1480], rax
0x18001d59e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001d5a5  test    rax, rax
0x18001d5a8  jz      short loc_18001D5B5
0x18001d5aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5af  mov     [rbp+1400h+var_1460], rax
0x18001d5b3  jmp     short loc_18001D5B9
0x18001d5b5  mov     [rbp+1400h+var_1460], r12
0x18001d5b9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001d5c0  test    rax, rax
0x18001d5c3  jz      short loc_18001D5CF
0x18001d5c5  lea     rcx, [rsp+1500h+var_14E0]
0x18001d5ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5cf  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001d5d6  test    rax, rax
0x18001d5d9  jz      short loc_18001D5EF
0x18001d5db  mov     r8d, 400h
0x18001d5e1  lea     rdx, [rbp+1400h+var_1440]
0x18001d5e5  lea     rcx, [rsp+1500h+var_14E0]
0x18001d5ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5ef  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001d5f6  test    rax, rax
0x18001d5f9  jz      short loc_18001D605
0x18001d5fb  lea     rcx, [rsp+1500h+var_14E0]
0x18001d600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d605  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001d60c  test    rax, rax
0x18001d60f  jz      short loc_18001D622
0x18001d611  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18001d616  jnz     short loc_18001D622
0x18001d618  lea     rcx, [rsp+1500h+var_14E0]
0x18001d61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d622  cmp     [rsp+1500h+var_14D8], r12d
0x18001d627  jge     loc_18001D730
0x18001d62d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18001d634  jnz     short loc_18001D655
0x18001d636  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001d63d  test    rax, rax
0x18001d640  jz      short loc_18001D64B
0x18001d642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d647  test    al, al
0x18001d649  jmp     short loc_18001D653
0x18001d64b  call    cs:__imp_IsDebuggerPresent
0x18001d651  test    eax, eax
0x18001d653  jz      short loc_18001D65C
0x18001d655  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18001d65a  jz      short loc_18001D682
0x18001d65c  mov     rax, cs:g_pfnResultLoggingCallback
0x18001d663  test    rax, rax
0x18001d666  jz      short loc_18001D6DB
0x18001d668  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18001d66f  jnz     short loc_18001D6DB
0x18001d671  xor     r8d, r8d
0x18001d674  xor     edx, edx
0x18001d676  lea     rcx, [rsp+1500h+var_14E0]
0x18001d67b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d680  jmp     short loc_18001D6DB
0x18001d682  mov     ebx, 800h
0x18001d687  mov     rax, cs:g_pfnResultLoggingCallback
0x18001d68e  test    rax, rax
0x18001d691  jz      short loc_18001D6B0
0x18001d693  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18001d69a  jnz     short loc_18001D6B0
0x18001d69c  mov     r8d, ebx
0x18001d69f  lea     rdx, [rbp+1400h+OutputString]
0x18001d6a6  lea     rcx, [rsp+1500h+var_14E0]
0x18001d6ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6b0  cmp     [rbp+1400h+OutputString], r12w
0x18001d6b8  jnz     short loc_18001D6CE
0x18001d6ba  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18001d6bf  mov     rdx, rbx; unsigned __int16 *
0x18001d6c2  lea     rcx, [rbp+1400h+OutputString]; this
0x18001d6c9  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001d6ce  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18001d6d5  call    cs:__imp_OutputDebugStringW
0x18001d6db  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18001d6e0  jnz     short loc_18001D6EB
0x18001d6e2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18001d6e9  jz      short loc_18001D6FD
0x18001d6eb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001d6f2  test    rax, rax
0x18001d6f5  jz      short loc_18001D6FD
0x18001d6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d6fc  nop
0x18001d6fd  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18001d702  jnz     short loc_18001D725
0x18001d704  mov     rcx, [rbp+1400h+var_40]
0x18001d70b  xor     rcx, rsp; StackCookie
0x18001d70e  call    __security_check_cookie
0x18001d713  add     rsp, 14D0h
0x18001d71a  pop     r15
0x18001d71c  pop     r14
0x18001d71e  pop     r12
0x18001d720  pop     rdi
0x18001d721  pop     rsi
0x18001d722  pop     rbx
0x18001d723  pop     rbp
0x18001d724  retn
0x18001d725  lea     rcx, [rsp+1500h+var_14E0]; this
0x18001d72a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001d730  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
