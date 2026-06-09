# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180006108`
- end: `0x180006395`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005be0`

## callees

- `0x180003a60`
- `0x180004998`
- `0x180006108`
- `0x1800077f4`
- `0x180008730`
- `0x180009790`
- `0x18000986c`
- `0x18006b600`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800061b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800061b6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006334`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006334`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800062aa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800062aa`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x180006108  push    rbp
0x18000610a  push    rbx
0x18000610b  push    rsi
0x18000610c  push    rdi
0x18000610d  push    r12
0x18000610f  push    r14
0x180006111  push    r15
0x180006113  lea     rbp, [rsp-13D0h]
0x18000611b  mov     eax, 14D0h
0x180006120  call    _alloca_probe
0x180006125  sub     rsp, rax
0x180006128  mov     rax, cs:__security_cookie
0x18000612f  xor     rax, rsp
0x180006132  mov     [rbp+1400h+var_40], rax
0x180006139  mov     r14, r8
0x18000613c  mov     esi, edx
0x18000613e  mov     r15, rcx
0x180006141  mov     rdi, [rbp+1400h+arg_28]
0x180006148  xor     edx, edx; Val
0x18000614a  mov     r8d, 98h; Size
0x180006150  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180006155  call    memset_0
0x18000615a  nop
0x18000615b  xor     r12d, r12d
0x18000615e  mov     [rbp+1400h+OutputString], r12w
0x180006166  mov     [rbp+1400h+var_1440], r12b
0x18000616a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180006171  mov     ecx, [rdx]; this
0x180006173  mov     [rsp+1500h+var_14D8], ecx
0x180006177  mov     eax, [rdx+4]
0x18000617a  mov     [rsp+1500h+var_14D4], eax
0x18000617e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006183  mov     ebx, eax
0x180006185  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000618d  mov     ecx, r12d
0x180006190  lea     eax, [r12+8]
0x180006195  cmp     dword ptr [rdx+8], 1
0x180006199  cmovz   ecx, eax
0x18000619c  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800061a0  lea     ecx, [rax-7]
0x1800061a3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800061ab  inc     ecx
0x1800061ad  mov     [rsp+1500h+var_14D0], ecx
0x1800061b1  mov     [rsp+1500h+var_14C8], r12
0x1800061b6  call    cs:__imp_GetCurrentThreadId
0x1800061bc  mov     [rsp+1500h+var_14C0], eax
0x1800061c0  mov     [rsp+1500h+var_14A8], r14
0x1800061c5  mov     [rsp+1500h+var_14A0], esi
0x1800061c9  mov     [rsp+1500h+var_149C], ebx
0x1800061cd  mov     [rsp+1500h+var_14B8], r12
0x1800061d2  mov     [rsp+1500h+var_14B0], r12
0x1800061d7  mov     [rbp+1400h+var_1458], rdi
0x1800061db  mov     [rbp+1400h+var_1450], r15
0x1800061df  mov     [rsp+1500h+var_1498], r12
0x1800061e4  xorps   xmm0, xmm0
0x1800061e7  xor     eax, eax
0x1800061e9  movups  [rbp+1400h+var_1478], xmm0
0x1800061ed  mov     [rbp+1400h+var_1468], rax
0x1800061f1  xorps   xmm1, xmm1
0x1800061f4  movups  [rsp+1500h+var_1490], xmm1
0x1800061f9  mov     [rbp+1400h+var_1480], rax
0x1800061fd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006204  test    rax, rax
0x180006207  jz      short loc_180006214
0x180006209  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000620e  mov     [rbp+1400h+var_1460], rax
0x180006212  jmp     short loc_180006218
0x180006214  mov     [rbp+1400h+var_1460], r12
0x180006218  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000621f  test    rax, rax
0x180006222  jz      short loc_18000622E
0x180006224  lea     rcx, [rsp+1500h+var_14E0]
0x180006229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000622e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006235  test    rax, rax
0x180006238  jz      short loc_18000624E
0x18000623a  mov     r8d, 400h
0x180006240  lea     rdx, [rbp+1400h+var_1440]
0x180006244  lea     rcx, [rsp+1500h+var_14E0]
0x180006249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000624e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006255  test    rax, rax
0x180006258  jz      short loc_180006264
0x18000625a  lea     rcx, [rsp+1500h+var_14E0]
0x18000625f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006264  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000626b  test    rax, rax
0x18000626e  jz      short loc_180006281
0x180006270  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006275  jnz     short loc_180006281
0x180006277  lea     rcx, [rsp+1500h+var_14E0]
0x18000627c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006281  cmp     [rsp+1500h+var_14D8], r12d
0x180006286  jge     loc_18000638F
0x18000628c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180006293  jnz     short loc_1800062B4
0x180006295  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000629c  test    rax, rax
0x18000629f  jz      short loc_1800062AA
0x1800062a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062a6  test    al, al
0x1800062a8  jmp     short loc_1800062B2
0x1800062aa  call    cs:__imp_IsDebuggerPresent
0x1800062b0  test    eax, eax
0x1800062b2  jz      short loc_1800062BB
0x1800062b4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800062b9  jz      short loc_1800062E1
0x1800062bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800062c2  test    rax, rax
0x1800062c5  jz      short loc_18000633A
0x1800062c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800062ce  jnz     short loc_18000633A
0x1800062d0  xor     r8d, r8d
0x1800062d3  xor     edx, edx
0x1800062d5  lea     rcx, [rsp+1500h+var_14E0]
0x1800062da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062df  jmp     short loc_18000633A
0x1800062e1  mov     ebx, 800h
0x1800062e6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800062ed  test    rax, rax
0x1800062f0  jz      short loc_18000630F
0x1800062f2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800062f9  jnz     short loc_18000630F
0x1800062fb  mov     r8d, ebx
0x1800062fe  lea     rdx, [rbp+1400h+OutputString]
0x180006305  lea     rcx, [rsp+1500h+var_14E0]
0x18000630a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000630f  cmp     [rbp+1400h+OutputString], r12w
0x180006317  jnz     short loc_18000632D
0x180006319  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000631e  mov     rdx, rbx; unsigned __int16 *
0x180006321  lea     rcx, [rbp+1400h+OutputString]; this
0x180006328  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000632d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180006334  call    cs:__imp_OutputDebugStringW
0x18000633a  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000633f  jnz     short loc_18000634A
0x180006341  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180006348  jz      short loc_18000635C
0x18000634a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006351  test    rax, rax
0x180006354  jz      short loc_18000635C
0x180006356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000635b  nop
0x18000635c  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180006361  jnz     short loc_180006384
0x180006363  mov     rcx, [rbp+1400h+var_40]
0x18000636a  xor     rcx, rsp; StackCookie
0x18000636d  call    __security_check_cookie
0x180006372  add     rsp, 14D0h
0x180006379  pop     r15
0x18000637b  pop     r14
0x18000637d  pop     r12
0x18000637f  pop     rdi
0x180006380  pop     rsi
0x180006381  pop     rbx
0x180006382  pop     rbp
0x180006383  retn
0x180006384  lea     rcx, [rsp+1500h+var_14E0]; this
0x180006389  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000638f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
