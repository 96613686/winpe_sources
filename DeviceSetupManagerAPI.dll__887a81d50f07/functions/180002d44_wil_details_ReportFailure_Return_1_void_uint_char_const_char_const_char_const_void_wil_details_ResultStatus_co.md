# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180002d44`
- end: `0x180002fd1`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002818`

## callees

- `0x1800017c0`
- `0x180002570`
- `0x180002d44`
- `0x180004dc4`
- `0x180006298`
- `0x180008460`
- `0x18000862c`
- `0x18000e3e0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002df2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002df2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002f70`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002f70`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002ee6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002ee6`

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
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180002d44  push    rbp
0x180002d46  push    rbx
0x180002d47  push    rsi
0x180002d48  push    rdi
0x180002d49  push    r12
0x180002d4b  push    r14
0x180002d4d  push    r15
0x180002d4f  lea     rbp, [rsp-13D0h]
0x180002d57  mov     eax, 14D0h
0x180002d5c  call    _alloca_probe
0x180002d61  sub     rsp, rax
0x180002d64  mov     rax, cs:__security_cookie
0x180002d6b  xor     rax, rsp
0x180002d6e  mov     [rbp+1400h+var_40], rax
0x180002d75  mov     r14, r8
0x180002d78  mov     esi, edx
0x180002d7a  mov     r15, rcx
0x180002d7d  mov     rdi, [rbp+1400h+arg_28]
0x180002d84  xor     edx, edx; Val
0x180002d86  mov     r8d, 98h; Size
0x180002d8c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002d91  call    memset_0
0x180002d96  nop
0x180002d97  xor     r12d, r12d
0x180002d9a  mov     [rbp+1400h+OutputString], r12w
0x180002da2  mov     [rbp+1400h+var_1440], r12b
0x180002da6  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180002dad  mov     ecx, [rdx]; this
0x180002daf  mov     [rsp+1500h+var_14D8], ecx
0x180002db3  mov     eax, [rdx+4]
0x180002db6  mov     [rsp+1500h+var_14D4], eax
0x180002dba  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180002dbf  mov     ebx, eax
0x180002dc1  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180002dc9  mov     ecx, r12d
0x180002dcc  lea     eax, [r12+8]
0x180002dd1  cmp     dword ptr [rdx+8], 1
0x180002dd5  cmovz   ecx, eax
0x180002dd8  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180002ddc  lea     ecx, [rax-7]
0x180002ddf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002de7  inc     ecx
0x180002de9  mov     [rsp+1500h+var_14D0], ecx
0x180002ded  mov     [rsp+1500h+var_14C8], r12
0x180002df2  call    cs:__imp_GetCurrentThreadId
0x180002df8  mov     [rsp+1500h+var_14C0], eax
0x180002dfc  mov     [rsp+1500h+var_14A8], r14
0x180002e01  mov     [rsp+1500h+var_14A0], esi
0x180002e05  mov     [rsp+1500h+var_149C], ebx
0x180002e09  mov     [rsp+1500h+var_14B8], r12
0x180002e0e  mov     [rsp+1500h+var_14B0], r12
0x180002e13  mov     [rbp+1400h+var_1458], rdi
0x180002e17  mov     [rbp+1400h+var_1450], r15
0x180002e1b  mov     [rsp+1500h+var_1498], r12
0x180002e20  xorps   xmm0, xmm0
0x180002e23  xor     eax, eax
0x180002e25  movups  [rbp+1400h+var_1478], xmm0
0x180002e29  mov     [rbp+1400h+var_1468], rax
0x180002e2d  xorps   xmm1, xmm1
0x180002e30  movups  [rsp+1500h+var_1490], xmm1
0x180002e35  mov     [rbp+1400h+var_1480], rax
0x180002e39  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002e40  test    rax, rax
0x180002e43  jz      short loc_180002E50
0x180002e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e4a  mov     [rbp+1400h+var_1460], rax
0x180002e4e  jmp     short loc_180002E54
0x180002e50  mov     [rbp+1400h+var_1460], r12
0x180002e54  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002e5b  test    rax, rax
0x180002e5e  jz      short loc_180002E6A
0x180002e60  lea     rcx, [rsp+1500h+var_14E0]
0x180002e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e6a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002e71  test    rax, rax
0x180002e74  jz      short loc_180002E8A
0x180002e76  mov     r8d, 400h
0x180002e7c  lea     rdx, [rbp+1400h+var_1440]
0x180002e80  lea     rcx, [rsp+1500h+var_14E0]
0x180002e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e8a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002e91  test    rax, rax
0x180002e94  jz      short loc_180002EA0
0x180002e96  lea     rcx, [rsp+1500h+var_14E0]
0x180002e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ea0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002ea7  test    rax, rax
0x180002eaa  jz      short loc_180002EBD
0x180002eac  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002eb1  jnz     short loc_180002EBD
0x180002eb3  lea     rcx, [rsp+1500h+var_14E0]
0x180002eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ebd  cmp     [rsp+1500h+var_14D8], r12d
0x180002ec2  jge     loc_180002FCB
0x180002ec8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002ecf  jnz     short loc_180002EF0
0x180002ed1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002ed8  test    rax, rax
0x180002edb  jz      short loc_180002EE6
0x180002edd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ee2  test    al, al
0x180002ee4  jmp     short loc_180002EEE
0x180002ee6  call    cs:__imp_IsDebuggerPresent
0x180002eec  test    eax, eax
0x180002eee  jz      short loc_180002EF7
0x180002ef0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180002ef5  jz      short loc_180002F1D
0x180002ef7  mov     rax, cs:g_pfnResultLoggingCallback
0x180002efe  test    rax, rax
0x180002f01  jz      short loc_180002F76
0x180002f03  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002f0a  jnz     short loc_180002F76
0x180002f0c  xor     r8d, r8d
0x180002f0f  xor     edx, edx
0x180002f11  lea     rcx, [rsp+1500h+var_14E0]
0x180002f16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f1b  jmp     short loc_180002F76
0x180002f1d  mov     ebx, 800h
0x180002f22  mov     rax, cs:g_pfnResultLoggingCallback
0x180002f29  test    rax, rax
0x180002f2c  jz      short loc_180002F4B
0x180002f2e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180002f35  jnz     short loc_180002F4B
0x180002f37  mov     r8d, ebx
0x180002f3a  lea     rdx, [rbp+1400h+OutputString]
0x180002f41  lea     rcx, [rsp+1500h+var_14E0]
0x180002f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f4b  cmp     [rbp+1400h+OutputString], r12w
0x180002f53  jnz     short loc_180002F69
0x180002f55  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180002f5a  mov     rdx, rbx; unsigned __int16 *
0x180002f5d  lea     rcx, [rbp+1400h+OutputString]; this
0x180002f64  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002f69  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180002f70  call    cs:__imp_OutputDebugStringW
0x180002f76  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180002f7b  jnz     short loc_180002F86
0x180002f7d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002f84  jz      short loc_180002F98
0x180002f86  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002f8d  test    rax, rax
0x180002f90  jz      short loc_180002F98
0x180002f92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f97  nop
0x180002f98  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180002f9d  jnz     short loc_180002FC0
0x180002f9f  mov     rcx, [rbp+1400h+var_40]
0x180002fa6  xor     rcx, rsp; StackCookie
0x180002fa9  call    __security_check_cookie
0x180002fae  add     rsp, 14D0h
0x180002fb5  pop     r15
0x180002fb7  pop     r14
0x180002fb9  pop     r12
0x180002fbb  pop     rdi
0x180002fbc  pop     rsi
0x180002fbd  pop     rbx
0x180002fbe  pop     rbp
0x180002fbf  retn
0x180002fc0  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002fc5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002fcb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
