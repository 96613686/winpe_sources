# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000498c`
- end: `0x180004c32`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004378`

## callees

- `0x1800033d0`
- `0x180004184`
- `0x18000498c`
- `0x180005794`
- `0x1800069a0`
- `0x180007428`
- `0x180007558`
- `0x1800173f0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a52`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004bd1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004bd1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004b47`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004b47`

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
0x18000498c  push    rbp
0x18000498e  push    rbx
0x18000498f  push    rsi
0x180004990  push    rdi
0x180004991  push    r12
0x180004993  push    r14
0x180004995  push    r15
0x180004997  lea     rbp, [rsp-13D0h]
0x18000499f  mov     eax, 14D0h
0x1800049a4  call    _alloca_probe
0x1800049a9  sub     rsp, rax
0x1800049ac  mov     rax, cs:__security_cookie
0x1800049b3  xor     rax, rsp
0x1800049b6  mov     [rbp+1400h+var_40], rax
0x1800049bd  mov     rsi, r8
0x1800049c0  mov     edi, edx
0x1800049c2  mov     rbx, rcx
0x1800049c5  mov     r14, [rbp+1400h+arg_28]
0x1800049cc  xor     edx, edx; Val
0x1800049ce  mov     r8d, 98h; Size
0x1800049d4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800049d9  call    memset_0
0x1800049de  nop
0x1800049df  xor     r12d, r12d
0x1800049e2  mov     [rbp+1400h+OutputString], r12w
0x1800049ea  mov     [rbp+1400h+var_1440], r12b
0x1800049ee  mov     rdx, [rbp+1400h+arg_30]; int
0x1800049f5  mov     ecx, [rdx]; this
0x1800049f7  mov     [rsp+1500h+var_14D8], ecx
0x1800049fb  mov     eax, [rdx+4]
0x1800049fe  mov     [rsp+1500h+var_14D4], eax
0x180004a02  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004a07  mov     r15d, eax
0x180004a0a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004a12  mov     ecx, r12d
0x180004a15  lea     eax, [r12+8]
0x180004a1a  cmp     dword ptr [rdx+8], 1
0x180004a1e  cmovz   ecx, eax
0x180004a21  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004a25  lea     ecx, [rax-7]
0x180004a28  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004a30  inc     ecx
0x180004a32  mov     [rsp+1500h+var_14D0], ecx
0x180004a36  mov     rcx, [rbp+1400h+arg_38]
0x180004a3d  test    rcx, rcx
0x180004a40  jz      short loc_180004A4D
0x180004a42  cmp     [rcx], r12w
0x180004a46  mov     [rsp+1500h+var_14C8], rcx
0x180004a4b  jnz     short loc_180004A52
0x180004a4d  mov     [rsp+1500h+var_14C8], r12
0x180004a52  call    cs:__imp_GetCurrentThreadId
0x180004a58  mov     [rsp+1500h+var_14C0], eax
0x180004a5c  mov     [rsp+1500h+var_14A8], rsi
0x180004a61  mov     [rsp+1500h+var_14A0], edi
0x180004a65  mov     [rsp+1500h+var_149C], r15d
0x180004a6a  mov     [rsp+1500h+var_14B8], r12
0x180004a6f  mov     [rsp+1500h+var_14B0], r12
0x180004a74  mov     [rbp+1400h+var_1458], r14
0x180004a78  mov     [rbp+1400h+var_1450], rbx
0x180004a7c  mov     [rsp+1500h+var_1498], r12
0x180004a81  xorps   xmm0, xmm0
0x180004a84  xor     eax, eax
0x180004a86  movups  [rbp+1400h+var_1478], xmm0
0x180004a8a  mov     [rbp+1400h+var_1468], rax
0x180004a8e  xorps   xmm1, xmm1
0x180004a91  movups  [rsp+1500h+var_1490], xmm1
0x180004a96  mov     [rbp+1400h+var_1480], rax
0x180004a9a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004aa1  test    rax, rax
0x180004aa4  jz      short loc_180004AB1
0x180004aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aab  mov     [rbp+1400h+var_1460], rax
0x180004aaf  jmp     short loc_180004AB5
0x180004ab1  mov     [rbp+1400h+var_1460], r12
0x180004ab5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004abc  test    rax, rax
0x180004abf  jz      short loc_180004ACB
0x180004ac1  lea     rcx, [rsp+1500h+var_14E0]
0x180004ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004acb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004ad2  test    rax, rax
0x180004ad5  jz      short loc_180004AEB
0x180004ad7  mov     r8d, 400h
0x180004add  lea     rdx, [rbp+1400h+var_1440]
0x180004ae1  lea     rcx, [rsp+1500h+var_14E0]
0x180004ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aeb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004af2  test    rax, rax
0x180004af5  jz      short loc_180004B01
0x180004af7  lea     rcx, [rsp+1500h+var_14E0]
0x180004afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b01  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004b08  test    rax, rax
0x180004b0b  jz      short loc_180004B1E
0x180004b0d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004b12  jnz     short loc_180004B1E
0x180004b14  lea     rcx, [rsp+1500h+var_14E0]
0x180004b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b1e  cmp     [rsp+1500h+var_14D8], r12d
0x180004b23  jge     loc_180004C2C
0x180004b29  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004b30  jnz     short loc_180004B51
0x180004b32  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004b39  test    rax, rax
0x180004b3c  jz      short loc_180004B47
0x180004b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b43  test    al, al
0x180004b45  jmp     short loc_180004B4F
0x180004b47  call    cs:__imp_IsDebuggerPresent
0x180004b4d  test    eax, eax
0x180004b4f  jz      short loc_180004B58
0x180004b51  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004b56  jz      short loc_180004B7E
0x180004b58  mov     rax, cs:g_pfnResultLoggingCallback
0x180004b5f  test    rax, rax
0x180004b62  jz      short loc_180004BD7
0x180004b64  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004b6b  jnz     short loc_180004BD7
0x180004b6d  xor     r8d, r8d
0x180004b70  xor     edx, edx
0x180004b72  lea     rcx, [rsp+1500h+var_14E0]
0x180004b77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b7c  jmp     short loc_180004BD7
0x180004b7e  mov     ebx, 800h
0x180004b83  mov     rax, cs:g_pfnResultLoggingCallback
0x180004b8a  test    rax, rax
0x180004b8d  jz      short loc_180004BAC
0x180004b8f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004b96  jnz     short loc_180004BAC
0x180004b98  mov     r8d, ebx
0x180004b9b  lea     rdx, [rbp+1400h+OutputString]
0x180004ba2  lea     rcx, [rsp+1500h+var_14E0]
0x180004ba7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bac  cmp     [rbp+1400h+OutputString], r12w
0x180004bb4  jnz     short loc_180004BCA
0x180004bb6  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004bbb  mov     rdx, rbx; unsigned __int16 *
0x180004bbe  lea     rcx, [rbp+1400h+OutputString]; this
0x180004bc5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004bca  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004bd1  call    cs:__imp_OutputDebugStringW
0x180004bd7  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004bdc  jnz     short loc_180004BE7
0x180004bde  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004be5  jz      short loc_180004BF9
0x180004be7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004bee  test    rax, rax
0x180004bf1  jz      short loc_180004BF9
0x180004bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bf8  nop
0x180004bf9  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004bfe  jnz     short loc_180004C21
0x180004c00  mov     rcx, [rbp+1400h+var_40]
0x180004c07  xor     rcx, rsp; StackCookie
0x180004c0a  call    __security_check_cookie
0x180004c0f  add     rsp, 14D0h
0x180004c16  pop     r15
0x180004c18  pop     r14
0x180004c1a  pop     r12
0x180004c1c  pop     rdi
0x180004c1d  pop     rsi
0x180004c1e  pop     rbx
0x180004c1f  pop     rbp
0x180004c20  retn
0x180004c21  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004c26  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004c2c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
