# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000d9a4`
- end: `0x18000dc2f`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000d664`

## callees

- `0x18000d9a4`
- `0x18000e544`
- `0x18000f380`
- `0x18000fb18`
- `0x18000fc48`
- `0x18005292a`
- `0x180052950`
- `0x1800529e0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000da51`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000da51`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000db45`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000db45`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000dbcf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000dbcf`

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
0x18000d9a4  push    rbp
0x18000d9a6  push    rbx
0x18000d9a7  push    rsi
0x18000d9a8  push    rdi
0x18000d9a9  push    r12
0x18000d9ab  push    r14
0x18000d9ad  push    r15
0x18000d9af  lea     rbp, [rsp-13D0h]
0x18000d9b7  mov     eax, 14D0h
0x18000d9bc  call    _alloca_probe
0x18000d9c1  sub     rsp, rax
0x18000d9c4  mov     rax, cs:__security_cookie
0x18000d9cb  xor     rax, rsp
0x18000d9ce  mov     [rbp+1400h+var_40], rax
0x18000d9d5  mov     rdi, [rbp+1400h+arg_28]
0x18000d9dc  mov     r14, r8
0x18000d9df  mov     esi, edx
0x18000d9e1  mov     r15, rcx
0x18000d9e4  xor     edx, edx; Val
0x18000d9e6  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000d9eb  mov     r8d, 98h; Size
0x18000d9f1  call    memset_0
0x18000d9f6  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000d9fd  xor     r12d, r12d
0x18000da00  mov     [rbp+1400h+OutputString], r12w
0x18000da08  mov     [rbp+1400h+var_1440], r12b
0x18000da0c  mov     ecx, [rdx]; this
0x18000da0e  mov     eax, [rdx+4]
0x18000da11  mov     [rsp+1500h+var_14D8], ecx
0x18000da15  mov     [rsp+1500h+var_14D4], eax
0x18000da19  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000da1e  cmp     dword ptr [rdx+8], 1
0x18000da22  mov     ebx, eax
0x18000da24  lea     eax, [r12+8]
0x18000da29  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000da31  mov     ecx, r12d
0x18000da34  cmovz   ecx, eax
0x18000da37  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000da3b  lea     ecx, [rax-7]
0x18000da3e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000da46  inc     ecx
0x18000da48  mov     [rsp+1500h+var_14C8], r12
0x18000da4d  mov     [rsp+1500h+var_14D0], ecx
0x18000da51  call    cs:__imp_GetCurrentThreadId
0x18000da57  xorps   xmm0, xmm0
0x18000da5a  mov     [rsp+1500h+var_14A8], r14
0x18000da5f  mov     [rsp+1500h+var_14C0], eax
0x18000da63  xorps   xmm1, xmm1
0x18000da66  xor     eax, eax
0x18000da68  mov     [rsp+1500h+var_14A0], esi
0x18000da6c  mov     [rbp+1400h+var_1468], rax
0x18000da70  mov     [rbp+1400h+var_1480], rax
0x18000da74  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000da7b  mov     [rsp+1500h+var_149C], ebx
0x18000da7f  mov     [rsp+1500h+var_14B8], r12
0x18000da84  mov     [rsp+1500h+var_14B0], r12
0x18000da89  mov     [rbp+1400h+var_1458], rdi
0x18000da8d  mov     [rbp+1400h+var_1450], r15
0x18000da91  mov     [rsp+1500h+var_1498], r12
0x18000da96  movups  [rbp+1400h+var_1478], xmm0
0x18000da9a  movups  [rsp+1500h+var_1490], xmm1
0x18000da9f  test    rax, rax
0x18000daa2  jz      short loc_18000DAAF
0x18000daa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daa9  mov     [rbp+1400h+var_1460], rax
0x18000daad  jmp     short loc_18000DAB3
0x18000daaf  mov     [rbp+1400h+var_1460], r12
0x18000dab3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000daba  test    rax, rax
0x18000dabd  jz      short loc_18000DAC9
0x18000dabf  lea     rcx, [rsp+1500h+var_14E0]
0x18000dac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dac9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000dad0  test    rax, rax
0x18000dad3  jz      short loc_18000DAE9
0x18000dad5  mov     r8d, 400h
0x18000dadb  lea     rdx, [rbp+1400h+var_1440]
0x18000dadf  lea     rcx, [rsp+1500h+var_14E0]
0x18000dae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dae9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000daf0  test    rax, rax
0x18000daf3  jz      short loc_18000DAFF
0x18000daf5  lea     rcx, [rsp+1500h+var_14E0]
0x18000dafa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daff  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000db06  test    rax, rax
0x18000db09  jz      short loc_18000DB1C
0x18000db0b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000db10  jnz     short loc_18000DB1C
0x18000db12  lea     rcx, [rsp+1500h+var_14E0]
0x18000db17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db1c  cmp     [rsp+1500h+var_14D8], r12d
0x18000db21  jge     loc_18000DC1E
0x18000db27  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000db2e  jnz     short loc_18000DB4F
0x18000db30  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000db37  test    rax, rax
0x18000db3a  jz      short loc_18000DB45
0x18000db3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db41  test    al, al
0x18000db43  jmp     short loc_18000DB4D
0x18000db45  call    cs:__imp_IsDebuggerPresent
0x18000db4b  test    eax, eax
0x18000db4d  jz      short loc_18000DB56
0x18000db4f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000db54  jz      short loc_18000DB7C
0x18000db56  mov     rax, cs:g_pfnResultLoggingCallback
0x18000db5d  test    rax, rax
0x18000db60  jz      short loc_18000DBD5
0x18000db62  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000db69  jnz     short loc_18000DBD5
0x18000db6b  xor     r8d, r8d
0x18000db6e  lea     rcx, [rsp+1500h+var_14E0]
0x18000db73  xor     edx, edx
0x18000db75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db7a  jmp     short loc_18000DBD5
0x18000db7c  mov     rax, cs:g_pfnResultLoggingCallback
0x18000db83  mov     ebx, 800h
0x18000db88  test    rax, rax
0x18000db8b  jz      short loc_18000DBAA
0x18000db8d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000db94  jnz     short loc_18000DBAA
0x18000db96  mov     r8d, ebx
0x18000db99  lea     rdx, [rbp+1400h+OutputString]
0x18000dba0  lea     rcx, [rsp+1500h+var_14E0]
0x18000dba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbaa  cmp     [rbp+1400h+OutputString], r12w
0x18000dbb2  jnz     short loc_18000DBC8
0x18000dbb4  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000dbb9  mov     rdx, rbx; unsigned __int16 *
0x18000dbbc  lea     rcx, [rbp+1400h+OutputString]; this
0x18000dbc3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000dbc8  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000dbcf  call    cs:__imp_OutputDebugStringW
0x18000dbd5  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000dbda  jnz     short loc_18000DBE5
0x18000dbdc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000dbe3  jz      short loc_18000DBF6
0x18000dbe5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000dbec  test    rax, rax
0x18000dbef  jz      short loc_18000DBF6
0x18000dbf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbf6  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000dbfb  jnz     short loc_18000DC24
0x18000dbfd  mov     rcx, [rbp+1400h+var_40]
0x18000dc04  xor     rcx, rsp; StackCookie
0x18000dc07  call    __security_check_cookie
0x18000dc0c  add     rsp, 14D0h
0x18000dc13  pop     r15
0x18000dc15  pop     r14
0x18000dc17  pop     r12
0x18000dc19  pop     rdi
0x18000dc1a  pop     rsi
0x18000dc1b  pop     rbx
0x18000dc1c  pop     rbp
0x18000dc1d  retn
0x18000dc1e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000dc24  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000dc29  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
