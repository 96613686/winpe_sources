# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800f8024`
- end: `0x1800f8309`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `741`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1800f76c8`

## callees

- `0x180003060`
- `0x180003a40`
- `0x1800e4d20`
- `0x1800e5570`
- `0x1800e8820`
- `0x1800e98fc`
- `0x1800ec390`
- `0x1800ec608`
- `0x1800f8024`
- `0x1800f95b0`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f812b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f812b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800f82a0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800f82a0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800f821b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800f821b`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // ebx
  int v13; // eax
  int v14; // edx
  int v15; // eax
  int v16; // ebx
  int v17; // ecx
  DWORD CurrentThreadId; // eax
  wchar_t *v19; // rdx
  wil::details::in1diag3 *v20; // rcx
  const struct wil::FailureInfo *v21; // r9
  bool v22; // zf
  wil::details *v23; // [rsp+30h] [rbp-D0h]
  int v24; // [rsp+40h] [rbp-C0h] BYREF
  int v25; // [rsp+44h] [rbp-BCh]
  int v26; // [rsp+48h] [rbp-B8h]
  int v27; // [rsp+4Ch] [rbp-B4h]
  signed __int32 v28; // [rsp+50h] [rbp-B0h]
  _WORD *v29; // [rsp+58h] [rbp-A8h]
  DWORD v30; // [rsp+60h] [rbp-A0h]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int64 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+78h] [rbp-88h]
  int v34; // [rsp+80h] [rbp-80h]
  int v35; // [rsp+84h] [rbp-7Ch]
  __int64 v36; // [rsp+88h] [rbp-78h]
  __int128 v37; // [rsp+90h] [rbp-70h]
  __int64 v38; // [rsp+A0h] [rbp-60h]
  __int128 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B8h] [rbp-48h]
  __int64 ModuleName; // [rsp+C0h] [rbp-40h]
  __int64 v42; // [rsp+C8h] [rbp-38h]
  __int64 v43; // [rsp+D0h] [rbp-30h]
  char v44[1024]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR OutputString[2048]; // [rsp+4E0h] [rbp+3E0h] BYREF

  memset_0(&v24, 0, 0x98u);
  OutputString[0] = 0;
  v44[0] = 0;
  v12 = *a7;
  v13 = a7[1];
  v26 = v12;
  v27 = v13;
  if ( v12 >= 0 )
  {
    v12 = -2147024228;
    LODWORD(v23) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, 0, 0, a6, v23);
    v26 = -2147024228;
    v27 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v14);
  }
  v15 = wil::details::RecordLog((wil::details *)(unsigned int)v12, v11);
  v22 = a7[2] == 1;
  v16 = v15;
  v24 = 2;
  v17 = 0;
  if ( v22 )
    v17 = 8;
  v25 = v17;
  v28 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v29 = a8, !*a8) )
    v29 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v33 = a3;
  v30 = CurrentThreadId;
  v34 = a2;
  v40 = 0;
  v38 = 0;
  v35 = v16;
  v31 = 0;
  v32 = 0;
  v42 = a6;
  v43 = a1;
  v36 = 0;
  v39 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v20);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v24);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v24, v44, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v24);
  if ( wil::details::g_pfnOriginateCallback && (v25 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v24);
  if ( v26 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v20);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v22 = !IsDebuggerPresent())
      : (v22 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v20) == 0),
        v22)
    || (v25 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v24, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v24, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, v19, (unsigned __int64)&v24, v21);
    OutputDebugStringW(OutputString);
  }
  if ( ((v25 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v20);
  if ( (v25 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v24, (const struct wil::FailureInfo *)v19);
}

```

## disassembly

```asm
0x1800f8024  mov     [rsp-8+arg_18], rbx
0x1800f8029  push    rbp
0x1800f802a  push    rsi
0x1800f802b  push    rdi
0x1800f802c  push    r12
0x1800f802e  push    r13
0x1800f8030  push    r14
0x1800f8032  push    r15
0x1800f8034  lea     rbp, [rsp-13F0h]
0x1800f803c  mov     eax, 14F0h
0x1800f8041  call    _alloca_probe
0x1800f8046  sub     rsp, rax
0x1800f8049  mov     rax, cs:__security_cookie
0x1800f8050  xor     rax, rsp
0x1800f8053  mov     [rbp+1420h+var_40], rax
0x1800f805a  mov     r15, [rbp+1420h+arg_28]
0x1800f8061  mov     r14, r8
0x1800f8064  mov     esi, edx
0x1800f8066  mov     rdi, rcx
0x1800f8069  xor     edx, edx; Val
0x1800f806b  lea     rcx, [rsp+1520h+var_14E0]; void *
0x1800f8070  mov     r8d, 98h; Size
0x1800f8076  call    memset_0
0x1800f807b  mov     r12, [rbp+1420h+arg_30]
0x1800f8082  xor     r13d, r13d
0x1800f8085  mov     [rbp+1420h+OutputString], r13w
0x1800f808d  mov     [rbp+1420h+var_1440], r13b
0x1800f8091  mov     ebx, [r12]
0x1800f8095  mov     eax, [r12+4]
0x1800f809a  mov     [rsp+1520h+var_14D8], ebx
0x1800f809e  mov     [rsp+1520h+var_14D4], eax
0x1800f80a2  test    ebx, ebx
0x1800f80a4  js      short loc_1800F80D8
0x1800f80a6  mov     ebx, 8007029Ch
0x1800f80ab  xor     r9d, r9d; int
0x1800f80ae  mov     dword ptr [rsp+1520h+var_14F0], ebx; wil::details *
0x1800f80b2  mov     r8, r14; int
0x1800f80b5  mov     [rsp+1520h+var_14F8], r15; __int64
0x1800f80ba  mov     edx, esi; int
0x1800f80bc  mov     rcx, rdi; int
0x1800f80bf  mov     [rsp+1520h+var_1500], r13; __int64
0x1800f80c4  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800f80c9  mov     ecx, ebx; this
0x1800f80cb  mov     [rsp+1520h+var_14D8], ebx
0x1800f80cf  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800f80d4  mov     [rsp+1520h+var_14D4], eax
0x1800f80d8  mov     ecx, ebx; this
0x1800f80da  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800f80df  cmp     dword ptr [r12+8], 1
0x1800f80e5  mov     ebx, eax
0x1800f80e7  mov     eax, 8
0x1800f80ec  mov     dword ptr [rsp+1520h+var_14E0], 2
0x1800f80f4  mov     ecx, r13d
0x1800f80f7  cmovz   ecx, eax
0x1800f80fa  mov     dword ptr [rsp+1520h+var_14E0+4], ecx
0x1800f80fe  lea     ecx, [rax-7]
0x1800f8101  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800f8109  inc     ecx
0x1800f810b  mov     [rsp+1520h+var_14D0], ecx
0x1800f810f  mov     rcx, [rbp+1420h+arg_38]
0x1800f8116  test    rcx, rcx
0x1800f8119  jz      short loc_1800F8126
0x1800f811b  mov     [rsp+1520h+var_14C8], rcx
0x1800f8120  cmp     [rcx], r13w
0x1800f8124  jnz     short loc_1800F812B
0x1800f8126  mov     [rsp+1520h+var_14C8], r13
0x1800f812b  call    cs:__imp_GetCurrentThreadId
0x1800f8131  xorps   xmm0, xmm0
0x1800f8134  mov     [rsp+1520h+var_14A8], r14
0x1800f8139  mov     [rsp+1520h+var_14C0], eax
0x1800f813d  xorps   xmm1, xmm1
0x1800f8140  xor     eax, eax
0x1800f8142  mov     [rbp+1420h+var_14A0], esi
0x1800f8145  mov     [rbp+1420h+var_1468], rax
0x1800f8149  mov     [rbp+1420h+var_1480], rax
0x1800f814d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800f8154  mov     [rbp+1420h+var_149C], ebx
0x1800f8157  mov     [rsp+1520h+var_14B8], r13
0x1800f815c  mov     [rsp+1520h+var_14B0], r13
0x1800f8161  mov     [rbp+1420h+var_1458], r15
0x1800f8165  mov     [rbp+1420h+var_1450], rdi
0x1800f8169  mov     [rbp+1420h+var_1498], r13
0x1800f816d  movups  [rbp+1420h+var_1478], xmm0
0x1800f8171  movups  [rbp+1420h+var_1490], xmm1
0x1800f8175  test    rax, rax
0x1800f8178  jz      short loc_1800F8185
0x1800f817a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f817f  mov     [rbp+1420h+var_1460], rax
0x1800f8183  jmp     short loc_1800F8189
0x1800f8185  mov     [rbp+1420h+var_1460], r13
0x1800f8189  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800f8190  test    rax, rax
0x1800f8193  jz      short loc_1800F819F
0x1800f8195  lea     rcx, [rsp+1520h+var_14E0]
0x1800f819a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f819f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800f81a6  test    rax, rax
0x1800f81a9  jz      short loc_1800F81BF
0x1800f81ab  mov     r8d, 400h
0x1800f81b1  lea     rdx, [rbp+1420h+var_1440]
0x1800f81b5  lea     rcx, [rsp+1520h+var_14E0]
0x1800f81ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f81bf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800f81c6  test    rax, rax
0x1800f81c9  jz      short loc_1800F81D5
0x1800f81cb  lea     rcx, [rsp+1520h+var_14E0]
0x1800f81d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f81d5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800f81dc  test    rax, rax
0x1800f81df  jz      short loc_1800F81F2
0x1800f81e1  test    byte ptr [rsp+1520h+var_14E0+4], 2
0x1800f81e6  jnz     short loc_1800F81F2
0x1800f81e8  lea     rcx, [rsp+1520h+var_14E0]
0x1800f81ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f81f2  cmp     [rsp+1520h+var_14D8], r13d
0x1800f81f7  jge     loc_1800F8303
0x1800f81fd  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800f8204  jnz     short loc_1800F8225
0x1800f8206  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800f820d  test    rax, rax
0x1800f8210  jz      short loc_1800F821B
0x1800f8212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8217  test    al, al
0x1800f8219  jmp     short loc_1800F8223
0x1800f821b  call    cs:__imp_IsDebuggerPresent
0x1800f8221  test    eax, eax
0x1800f8223  jz      short loc_1800F822C
0x1800f8225  test    byte ptr [rsp+1520h+var_14E0+4], 2
0x1800f822a  jz      short loc_1800F8252
0x1800f822c  mov     rax, cs:g_pfnResultLoggingCallback
0x1800f8233  test    rax, rax
0x1800f8236  jz      short loc_1800F82A6
0x1800f8238  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800f823f  jnz     short loc_1800F82A6
0x1800f8241  xor     r8d, r8d
0x1800f8244  lea     rcx, [rsp+1520h+var_14E0]
0x1800f8249  xor     edx, edx
0x1800f824b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f8250  jmp     short loc_1800F82A6
0x1800f8252  mov     rax, cs:g_pfnResultLoggingCallback
0x1800f8259  test    rax, rax
0x1800f825c  jz      short loc_1800F827E
0x1800f825e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800f8265  jnz     short loc_1800F827E
0x1800f8267  mov     r8d, 800h
0x1800f826d  lea     rdx, [rbp+1420h+OutputString]
0x1800f8274  lea     rcx, [rsp+1520h+var_14E0]
0x1800f8279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f827e  cmp     [rbp+1420h+OutputString], r13w
0x1800f8286  jnz     short loc_1800F8299
0x1800f8288  lea     r8, [rsp+1520h+var_14E0]; unsigned __int64
0x1800f828d  lea     rcx, [rbp+1420h+OutputString]; this
0x1800f8294  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800f8299  lea     rcx, [rbp+1420h+OutputString]; lpOutputString
0x1800f82a0  call    cs:__imp_OutputDebugStringW
0x1800f82a6  test    byte ptr [rsp+1520h+var_14E0+4], 4
0x1800f82ab  jnz     short loc_1800F82B6
0x1800f82ad  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800f82b4  jz      short loc_1800F82C7
0x1800f82b6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800f82bd  test    rax, rax
0x1800f82c0  jz      short loc_1800F82C7
0x1800f82c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f82c7  test    byte ptr [rsp+1520h+var_14E0+4], 1
0x1800f82cc  jnz     short loc_1800F82F8
0x1800f82ce  mov     rcx, [rbp+1420h+var_40]
0x1800f82d5  xor     rcx, rsp; StackCookie
0x1800f82d8  call    __security_check_cookie
0x1800f82dd  mov     rbx, [rsp+1520h+arg_18]
0x1800f82e5  add     rsp, 14F0h
0x1800f82ec  pop     r15
0x1800f82ee  pop     r14
0x1800f82f0  pop     r13
0x1800f82f2  pop     r12
0x1800f82f4  pop     rdi
0x1800f82f5  pop     rsi
0x1800f82f6  pop     rbp
0x1800f82f7  retn
0x1800f82f8  lea     rcx, [rsp+1520h+var_14E0]; this
0x1800f82fd  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800f8303  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
