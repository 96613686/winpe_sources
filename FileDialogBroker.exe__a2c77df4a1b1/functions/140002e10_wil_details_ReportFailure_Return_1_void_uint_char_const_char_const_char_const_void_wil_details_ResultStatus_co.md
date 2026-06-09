# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002e10`
- end: `0x1400030b6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002a98`

## callees

- `0x140001c80`
- `0x1400028a8`
- `0x140002e10`
- `0x140003c94`
- `0x140004da0`
- `0x140005968`
- `0x140005b64`
- `0x140011360`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002ed6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002ed6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002fcb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002fcb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003055`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003055`

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
0x140002e10  push    rbp
0x140002e12  push    rbx
0x140002e13  push    rsi
0x140002e14  push    rdi
0x140002e15  push    r12
0x140002e17  push    r14
0x140002e19  push    r15
0x140002e1b  lea     rbp, [rsp-13D0h]
0x140002e23  mov     eax, 14D0h
0x140002e28  call    _alloca_probe
0x140002e2d  sub     rsp, rax
0x140002e30  mov     rax, cs:__security_cookie
0x140002e37  xor     rax, rsp
0x140002e3a  mov     [rbp+1400h+var_40], rax
0x140002e41  mov     rsi, r8
0x140002e44  mov     edi, edx
0x140002e46  mov     rbx, rcx
0x140002e49  mov     r14, [rbp+1400h+arg_28]
0x140002e50  xor     edx, edx; Val
0x140002e52  mov     r8d, 98h; Size
0x140002e58  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140002e5d  call    memset_0
0x140002e62  nop
0x140002e63  xor     r12d, r12d
0x140002e66  mov     [rbp+1400h+OutputString], r12w
0x140002e6e  mov     [rbp+1400h+var_1440], r12b
0x140002e72  mov     rdx, [rbp+1400h+arg_30]; int
0x140002e79  mov     ecx, [rdx]; this
0x140002e7b  mov     [rsp+1500h+var_14D8], ecx
0x140002e7f  mov     eax, [rdx+4]
0x140002e82  mov     [rsp+1500h+var_14D4], eax
0x140002e86  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002e8b  mov     r15d, eax
0x140002e8e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140002e96  mov     ecx, r12d
0x140002e99  lea     eax, [r12+8]
0x140002e9e  cmp     dword ptr [rdx+8], 1
0x140002ea2  cmovz   ecx, eax
0x140002ea5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140002ea9  lea     ecx, [rax-7]
0x140002eac  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002eb4  inc     ecx
0x140002eb6  mov     [rsp+1500h+var_14D0], ecx
0x140002eba  mov     rcx, [rbp+1400h+arg_38]
0x140002ec1  test    rcx, rcx
0x140002ec4  jz      short loc_140002ED1
0x140002ec6  cmp     [rcx], r12w
0x140002eca  mov     [rsp+1500h+var_14C8], rcx
0x140002ecf  jnz     short loc_140002ED6
0x140002ed1  mov     [rsp+1500h+var_14C8], r12
0x140002ed6  call    cs:__imp_GetCurrentThreadId
0x140002edc  mov     [rsp+1500h+var_14C0], eax
0x140002ee0  mov     [rsp+1500h+var_14A8], rsi
0x140002ee5  mov     [rsp+1500h+var_14A0], edi
0x140002ee9  mov     [rsp+1500h+var_149C], r15d
0x140002eee  mov     [rsp+1500h+var_14B8], r12
0x140002ef3  mov     [rsp+1500h+var_14B0], r12
0x140002ef8  mov     [rbp+1400h+var_1458], r14
0x140002efc  mov     [rbp+1400h+var_1450], rbx
0x140002f00  mov     [rsp+1500h+var_1498], r12
0x140002f05  xorps   xmm0, xmm0
0x140002f08  xor     eax, eax
0x140002f0a  movups  [rbp+1400h+var_1478], xmm0
0x140002f0e  mov     [rbp+1400h+var_1468], rax
0x140002f12  xorps   xmm1, xmm1
0x140002f15  movups  [rsp+1500h+var_1490], xmm1
0x140002f1a  mov     [rbp+1400h+var_1480], rax
0x140002f1e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002f25  test    rax, rax
0x140002f28  jz      short loc_140002F35
0x140002f2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f2f  mov     [rbp+1400h+var_1460], rax
0x140002f33  jmp     short loc_140002F39
0x140002f35  mov     [rbp+1400h+var_1460], r12
0x140002f39  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002f40  test    rax, rax
0x140002f43  jz      short loc_140002F4F
0x140002f45  lea     rcx, [rsp+1500h+var_14E0]
0x140002f4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f4f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002f56  test    rax, rax
0x140002f59  jz      short loc_140002F6F
0x140002f5b  mov     r8d, 400h
0x140002f61  lea     rdx, [rbp+1400h+var_1440]
0x140002f65  lea     rcx, [rsp+1500h+var_14E0]
0x140002f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f6f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002f76  test    rax, rax
0x140002f79  jz      short loc_140002F85
0x140002f7b  lea     rcx, [rsp+1500h+var_14E0]
0x140002f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f85  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002f8c  test    rax, rax
0x140002f8f  jz      short loc_140002FA2
0x140002f91  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002f96  jnz     short loc_140002FA2
0x140002f98  lea     rcx, [rsp+1500h+var_14E0]
0x140002f9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002fa2  cmp     [rsp+1500h+var_14D8], r12d
0x140002fa7  jge     loc_1400030B0
0x140002fad  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140002fb4  jnz     short loc_140002FD5
0x140002fb6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002fbd  test    rax, rax
0x140002fc0  jz      short loc_140002FCB
0x140002fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002fc7  test    al, al
0x140002fc9  jmp     short loc_140002FD3
0x140002fcb  call    cs:__imp_IsDebuggerPresent
0x140002fd1  test    eax, eax
0x140002fd3  jz      short loc_140002FDC
0x140002fd5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002fda  jz      short loc_140003002
0x140002fdc  mov     rax, cs:g_pfnResultLoggingCallback
0x140002fe3  test    rax, rax
0x140002fe6  jz      short loc_14000305B
0x140002fe8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002fef  jnz     short loc_14000305B
0x140002ff1  xor     r8d, r8d
0x140002ff4  xor     edx, edx
0x140002ff6  lea     rcx, [rsp+1500h+var_14E0]
0x140002ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003000  jmp     short loc_14000305B
0x140003002  mov     ebx, 800h
0x140003007  mov     rax, cs:g_pfnResultLoggingCallback
0x14000300e  test    rax, rax
0x140003011  jz      short loc_140003030
0x140003013  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000301a  jnz     short loc_140003030
0x14000301c  mov     r8d, ebx
0x14000301f  lea     rdx, [rbp+1400h+OutputString]
0x140003026  lea     rcx, [rsp+1500h+var_14E0]
0x14000302b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003030  cmp     [rbp+1400h+OutputString], r12w
0x140003038  jnz     short loc_14000304E
0x14000303a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x14000303f  mov     rdx, rbx; unsigned __int16 *
0x140003042  lea     rcx, [rbp+1400h+OutputString]; this
0x140003049  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000304e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140003055  call    cs:__imp_OutputDebugStringW
0x14000305b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140003060  jnz     short loc_14000306B
0x140003062  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140003069  jz      short loc_14000307D
0x14000306b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003072  test    rax, rax
0x140003075  jz      short loc_14000307D
0x140003077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000307c  nop
0x14000307d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140003082  jnz     short loc_1400030A5
0x140003084  mov     rcx, [rbp+1400h+var_40]
0x14000308b  xor     rcx, rsp; StackCookie
0x14000308e  call    __security_check_cookie
0x140003093  add     rsp, 14D0h
0x14000309a  pop     r15
0x14000309c  pop     r14
0x14000309e  pop     r12
0x1400030a0  pop     rdi
0x1400030a1  pop     rsi
0x1400030a2  pop     rbx
0x1400030a3  pop     rbp
0x1400030a4  retn
0x1400030a5  lea     rcx, [rsp+1500h+var_14E0]; this
0x1400030aa  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400030b0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
