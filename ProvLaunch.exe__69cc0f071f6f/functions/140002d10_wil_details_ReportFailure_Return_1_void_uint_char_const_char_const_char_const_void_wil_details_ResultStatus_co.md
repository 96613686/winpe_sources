# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002d10`
- end: `0x140002fb6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002378`

## callees

- `0x140002d10`
- `0x1400042f4`
- `0x140005230`
- `0x140006100`
- `0x140006474`
- `0x14000a33e`
- `0x14000a370`
- `0x14000a430`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002dd6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002dd6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002ecb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002ecb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002f55`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002f55`

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
0x140002d10  push    rbp
0x140002d12  push    rbx
0x140002d13  push    rsi
0x140002d14  push    rdi
0x140002d15  push    r12
0x140002d17  push    r14
0x140002d19  push    r15
0x140002d1b  lea     rbp, [rsp-13D0h]
0x140002d23  mov     eax, 14D0h
0x140002d28  call    _alloca_probe
0x140002d2d  sub     rsp, rax
0x140002d30  mov     rax, cs:__security_cookie
0x140002d37  xor     rax, rsp
0x140002d3a  mov     [rbp+1400h+var_40], rax
0x140002d41  mov     rsi, r8
0x140002d44  mov     edi, edx
0x140002d46  mov     rbx, rcx
0x140002d49  mov     r14, [rbp+1400h+arg_28]
0x140002d50  xor     edx, edx; Val
0x140002d52  mov     r8d, 98h; Size
0x140002d58  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140002d5d  call    memset_0
0x140002d62  nop
0x140002d63  xor     r12d, r12d
0x140002d66  mov     [rbp+1400h+OutputString], r12w
0x140002d6e  mov     [rbp+1400h+var_1440], r12b
0x140002d72  mov     rdx, [rbp+1400h+arg_30]; int
0x140002d79  mov     ecx, [rdx]; this
0x140002d7b  mov     [rsp+1500h+var_14D8], ecx
0x140002d7f  mov     eax, [rdx+4]
0x140002d82  mov     [rsp+1500h+var_14D4], eax
0x140002d86  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002d8b  mov     r15d, eax
0x140002d8e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140002d96  mov     ecx, r12d
0x140002d99  lea     eax, [r12+8]
0x140002d9e  cmp     dword ptr [rdx+8], 1
0x140002da2  cmovz   ecx, eax
0x140002da5  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140002da9  lea     ecx, [rax-7]
0x140002dac  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002db4  inc     ecx
0x140002db6  mov     [rsp+1500h+var_14D0], ecx
0x140002dba  mov     rcx, [rbp+1400h+arg_38]
0x140002dc1  test    rcx, rcx
0x140002dc4  jz      short loc_140002DD1
0x140002dc6  cmp     [rcx], r12w
0x140002dca  mov     [rsp+1500h+var_14C8], rcx
0x140002dcf  jnz     short loc_140002DD6
0x140002dd1  mov     [rsp+1500h+var_14C8], r12
0x140002dd6  call    cs:__imp_GetCurrentThreadId
0x140002ddc  mov     [rsp+1500h+var_14C0], eax
0x140002de0  mov     [rsp+1500h+var_14A8], rsi
0x140002de5  mov     [rsp+1500h+var_14A0], edi
0x140002de9  mov     [rsp+1500h+var_149C], r15d
0x140002dee  mov     [rsp+1500h+var_14B8], r12
0x140002df3  mov     [rsp+1500h+var_14B0], r12
0x140002df8  mov     [rbp+1400h+var_1458], r14
0x140002dfc  mov     [rbp+1400h+var_1450], rbx
0x140002e00  mov     [rsp+1500h+var_1498], r12
0x140002e05  xorps   xmm0, xmm0
0x140002e08  xor     eax, eax
0x140002e0a  movups  [rbp+1400h+var_1478], xmm0
0x140002e0e  mov     [rbp+1400h+var_1468], rax
0x140002e12  xorps   xmm1, xmm1
0x140002e15  movups  [rsp+1500h+var_1490], xmm1
0x140002e1a  mov     [rbp+1400h+var_1480], rax
0x140002e1e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002e25  test    rax, rax
0x140002e28  jz      short loc_140002E35
0x140002e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e2f  mov     [rbp+1400h+var_1460], rax
0x140002e33  jmp     short loc_140002E39
0x140002e35  mov     [rbp+1400h+var_1460], r12
0x140002e39  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002e40  test    rax, rax
0x140002e43  jz      short loc_140002E4F
0x140002e45  lea     rcx, [rsp+1500h+var_14E0]
0x140002e4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e4f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002e56  test    rax, rax
0x140002e59  jz      short loc_140002E6F
0x140002e5b  mov     r8d, 400h
0x140002e61  lea     rdx, [rbp+1400h+var_1440]
0x140002e65  lea     rcx, [rsp+1500h+var_14E0]
0x140002e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e6f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002e76  test    rax, rax
0x140002e79  jz      short loc_140002E85
0x140002e7b  lea     rcx, [rsp+1500h+var_14E0]
0x140002e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e85  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002e8c  test    rax, rax
0x140002e8f  jz      short loc_140002EA2
0x140002e91  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002e96  jnz     short loc_140002EA2
0x140002e98  lea     rcx, [rsp+1500h+var_14E0]
0x140002e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ea2  cmp     [rsp+1500h+var_14D8], r12d
0x140002ea7  jge     loc_140002FB0
0x140002ead  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140002eb4  jnz     short loc_140002ED5
0x140002eb6  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002ebd  test    rax, rax
0x140002ec0  jz      short loc_140002ECB
0x140002ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ec7  test    al, al
0x140002ec9  jmp     short loc_140002ED3
0x140002ecb  call    cs:__imp_IsDebuggerPresent
0x140002ed1  test    eax, eax
0x140002ed3  jz      short loc_140002EDC
0x140002ed5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002eda  jz      short loc_140002F02
0x140002edc  mov     rax, cs:g_pfnResultLoggingCallback
0x140002ee3  test    rax, rax
0x140002ee6  jz      short loc_140002F5B
0x140002ee8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002eef  jnz     short loc_140002F5B
0x140002ef1  xor     r8d, r8d
0x140002ef4  xor     edx, edx
0x140002ef6  lea     rcx, [rsp+1500h+var_14E0]
0x140002efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f00  jmp     short loc_140002F5B
0x140002f02  mov     ebx, 800h
0x140002f07  mov     rax, cs:g_pfnResultLoggingCallback
0x140002f0e  test    rax, rax
0x140002f11  jz      short loc_140002F30
0x140002f13  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002f1a  jnz     short loc_140002F30
0x140002f1c  mov     r8d, ebx
0x140002f1f  lea     rdx, [rbp+1400h+OutputString]
0x140002f26  lea     rcx, [rsp+1500h+var_14E0]
0x140002f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f30  cmp     [rbp+1400h+OutputString], r12w
0x140002f38  jnz     short loc_140002F4E
0x140002f3a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140002f3f  mov     rdx, rbx; unsigned __int16 *
0x140002f42  lea     rcx, [rbp+1400h+OutputString]; this
0x140002f49  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002f4e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140002f55  call    cs:__imp_OutputDebugStringW
0x140002f5b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140002f60  jnz     short loc_140002F6B
0x140002f62  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140002f69  jz      short loc_140002F7D
0x140002f6b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002f72  test    rax, rax
0x140002f75  jz      short loc_140002F7D
0x140002f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f7c  nop
0x140002f7d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140002f82  jnz     short loc_140002FA5
0x140002f84  mov     rcx, [rbp+1400h+var_40]
0x140002f8b  xor     rcx, rsp; StackCookie
0x140002f8e  call    __security_check_cookie
0x140002f93  add     rsp, 14D0h
0x140002f9a  pop     r15
0x140002f9c  pop     r14
0x140002f9e  pop     r12
0x140002fa0  pop     rdi
0x140002fa1  pop     rsi
0x140002fa2  pop     rbx
0x140002fa3  pop     rbp
0x140002fa4  retn
0x140002fa5  lea     rcx, [rsp+1500h+var_14E0]; this
0x140002faa  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002fb0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
