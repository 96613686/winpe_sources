# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000438c`
- end: `0x140004619`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140003e64`

## callees

- `0x140002600`
- `0x1400030dc`
- `0x14000438c`
- `0x140006464`
- `0x1400078e0`
- `0x140009260`
- `0x1400093e8`
- `0x14001bb30`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000443a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000443a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400045b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400045b8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000452e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000452e`

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
0x14000438c  push    rbp
0x14000438e  push    rbx
0x14000438f  push    rsi
0x140004390  push    rdi
0x140004391  push    r12
0x140004393  push    r14
0x140004395  push    r15
0x140004397  lea     rbp, [rsp-13D0h]
0x14000439f  mov     eax, 14D0h
0x1400043a4  call    _alloca_probe
0x1400043a9  sub     rsp, rax
0x1400043ac  mov     rax, cs:__security_cookie
0x1400043b3  xor     rax, rsp
0x1400043b6  mov     [rbp+1400h+var_40], rax
0x1400043bd  mov     r14, r8
0x1400043c0  mov     esi, edx
0x1400043c2  mov     r15, rcx
0x1400043c5  mov     rdi, [rbp+1400h+arg_28]
0x1400043cc  xor     edx, edx; Val
0x1400043ce  mov     r8d, 98h; Size
0x1400043d4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400043d9  call    memset_0
0x1400043de  nop
0x1400043df  xor     r12d, r12d
0x1400043e2  mov     [rbp+1400h+OutputString], r12w
0x1400043ea  mov     [rbp+1400h+var_1440], r12b
0x1400043ee  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1400043f5  mov     ecx, [rdx]; this
0x1400043f7  mov     [rsp+1500h+var_14D8], ecx
0x1400043fb  mov     eax, [rdx+4]
0x1400043fe  mov     [rsp+1500h+var_14D4], eax
0x140004402  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004407  mov     ebx, eax
0x140004409  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140004411  mov     ecx, r12d
0x140004414  lea     eax, [r12+8]
0x140004419  cmp     dword ptr [rdx+8], 1
0x14000441d  cmovz   ecx, eax
0x140004420  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140004424  lea     ecx, [rax-7]
0x140004427  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000442f  inc     ecx
0x140004431  mov     [rsp+1500h+var_14D0], ecx
0x140004435  mov     [rsp+1500h+var_14C8], r12
0x14000443a  call    cs:__imp_GetCurrentThreadId
0x140004440  mov     [rsp+1500h+var_14C0], eax
0x140004444  mov     [rsp+1500h+var_14A8], r14
0x140004449  mov     [rsp+1500h+var_14A0], esi
0x14000444d  mov     [rsp+1500h+var_149C], ebx
0x140004451  mov     [rsp+1500h+var_14B8], r12
0x140004456  mov     [rsp+1500h+var_14B0], r12
0x14000445b  mov     [rbp+1400h+var_1458], rdi
0x14000445f  mov     [rbp+1400h+var_1450], r15
0x140004463  mov     [rsp+1500h+var_1498], r12
0x140004468  xorps   xmm0, xmm0
0x14000446b  xor     eax, eax
0x14000446d  movups  [rbp+1400h+var_1478], xmm0
0x140004471  mov     [rbp+1400h+var_1468], rax
0x140004475  xorps   xmm1, xmm1
0x140004478  movups  [rsp+1500h+var_1490], xmm1
0x14000447d  mov     [rbp+1400h+var_1480], rax
0x140004481  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004488  test    rax, rax
0x14000448b  jz      short loc_140004498
0x14000448d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004492  mov     [rbp+1400h+var_1460], rax
0x140004496  jmp     short loc_14000449C
0x140004498  mov     [rbp+1400h+var_1460], r12
0x14000449c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400044a3  test    rax, rax
0x1400044a6  jz      short loc_1400044B2
0x1400044a8  lea     rcx, [rsp+1500h+var_14E0]
0x1400044ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044b2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400044b9  test    rax, rax
0x1400044bc  jz      short loc_1400044D2
0x1400044be  mov     r8d, 400h
0x1400044c4  lea     rdx, [rbp+1400h+var_1440]
0x1400044c8  lea     rcx, [rsp+1500h+var_14E0]
0x1400044cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044d2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400044d9  test    rax, rax
0x1400044dc  jz      short loc_1400044E8
0x1400044de  lea     rcx, [rsp+1500h+var_14E0]
0x1400044e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400044e8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400044ef  test    rax, rax
0x1400044f2  jz      short loc_140004505
0x1400044f4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400044f9  jnz     short loc_140004505
0x1400044fb  lea     rcx, [rsp+1500h+var_14E0]
0x140004500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004505  cmp     [rsp+1500h+var_14D8], r12d
0x14000450a  jge     loc_140004613
0x140004510  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140004517  jnz     short loc_140004538
0x140004519  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004520  test    rax, rax
0x140004523  jz      short loc_14000452E
0x140004525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000452a  test    al, al
0x14000452c  jmp     short loc_140004536
0x14000452e  call    cs:__imp_IsDebuggerPresent
0x140004534  test    eax, eax
0x140004536  jz      short loc_14000453F
0x140004538  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000453d  jz      short loc_140004565
0x14000453f  mov     rax, cs:g_pfnResultLoggingCallback
0x140004546  test    rax, rax
0x140004549  jz      short loc_1400045BE
0x14000454b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140004552  jnz     short loc_1400045BE
0x140004554  xor     r8d, r8d
0x140004557  xor     edx, edx
0x140004559  lea     rcx, [rsp+1500h+var_14E0]
0x14000455e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004563  jmp     short loc_1400045BE
0x140004565  mov     ebx, 800h
0x14000456a  mov     rax, cs:g_pfnResultLoggingCallback
0x140004571  test    rax, rax
0x140004574  jz      short loc_140004593
0x140004576  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000457d  jnz     short loc_140004593
0x14000457f  mov     r8d, ebx
0x140004582  lea     rdx, [rbp+1400h+OutputString]
0x140004589  lea     rcx, [rsp+1500h+var_14E0]
0x14000458e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004593  cmp     [rbp+1400h+OutputString], r12w
0x14000459b  jnz     short loc_1400045B1
0x14000459d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1400045a2  mov     rdx, rbx; unsigned __int16 *
0x1400045a5  lea     rcx, [rbp+1400h+OutputString]; this
0x1400045ac  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400045b1  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1400045b8  call    cs:__imp_OutputDebugStringW
0x1400045be  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1400045c3  jnz     short loc_1400045CE
0x1400045c5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400045cc  jz      short loc_1400045E0
0x1400045ce  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400045d5  test    rax, rax
0x1400045d8  jz      short loc_1400045E0
0x1400045da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045df  nop
0x1400045e0  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1400045e5  jnz     short loc_140004608
0x1400045e7  mov     rcx, [rbp+1400h+var_40]
0x1400045ee  xor     rcx, rsp; StackCookie
0x1400045f1  call    __security_check_cookie
0x1400045f6  add     rsp, 14D0h
0x1400045fd  pop     r15
0x1400045ff  pop     r14
0x140004601  pop     r12
0x140004603  pop     rdi
0x140004604  pop     rsi
0x140004605  pop     rbx
0x140004606  pop     rbp
0x140004607  retn
0x140004608  lea     rcx, [rsp+1500h+var_14E0]; this
0x14000460d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140004613  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
