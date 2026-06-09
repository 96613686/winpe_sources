# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005218`
- end: `0x1800054be`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004de8`

## callees

- `0x1800030e0`
- `0x180003c64`
- `0x180005218`
- `0x1800074c4`
- `0x180009898`
- `0x18000b8a8`
- `0x18000bb40`
- `0x1800579d0`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052de`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000545d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000545d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800053d3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800053d3`

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
    wil::details::in1diag3::FailFastImmediate_Unexpected(v15);
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
0x180005218  push    rbp
0x18000521a  push    rbx
0x18000521b  push    rsi
0x18000521c  push    rdi
0x18000521d  push    r12
0x18000521f  push    r14
0x180005221  push    r15
0x180005223  lea     rbp, [rsp-13D0h]
0x18000522b  mov     eax, 14D0h
0x180005230  call    _alloca_probe
0x180005235  sub     rsp, rax
0x180005238  mov     rax, cs:__security_cookie
0x18000523f  xor     rax, rsp
0x180005242  mov     [rbp+1400h+var_40], rax
0x180005249  mov     rsi, r8
0x18000524c  mov     edi, edx
0x18000524e  mov     rbx, rcx
0x180005251  mov     r14, [rbp+1400h+arg_28]
0x180005258  xor     edx, edx; Val
0x18000525a  mov     r8d, 98h; Size
0x180005260  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180005265  call    memset_0
0x18000526a  nop
0x18000526b  xor     r12d, r12d
0x18000526e  mov     [rbp+1400h+OutputString], r12w
0x180005276  mov     [rbp+1400h+var_1440], r12b
0x18000527a  mov     rdx, [rbp+1400h+arg_30]; int
0x180005281  mov     ecx, [rdx]; this
0x180005283  mov     [rsp+1500h+var_14D8], ecx
0x180005287  mov     eax, [rdx+4]
0x18000528a  mov     [rsp+1500h+var_14D4], eax
0x18000528e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005293  mov     r15d, eax
0x180005296  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000529e  mov     ecx, r12d
0x1800052a1  lea     eax, [r12+8]
0x1800052a6  cmp     dword ptr [rdx+8], 1
0x1800052aa  cmovz   ecx, eax
0x1800052ad  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800052b1  lea     ecx, [rax-7]
0x1800052b4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800052bc  inc     ecx
0x1800052be  mov     [rsp+1500h+var_14D0], ecx
0x1800052c2  mov     rcx, [rbp+1400h+arg_38]
0x1800052c9  test    rcx, rcx
0x1800052cc  jz      short loc_1800052D9
0x1800052ce  cmp     [rcx], r12w
0x1800052d2  mov     [rsp+1500h+var_14C8], rcx
0x1800052d7  jnz     short loc_1800052DE
0x1800052d9  mov     [rsp+1500h+var_14C8], r12
0x1800052de  call    cs:__imp_GetCurrentThreadId
0x1800052e4  mov     [rsp+1500h+var_14C0], eax
0x1800052e8  mov     [rsp+1500h+var_14A8], rsi
0x1800052ed  mov     [rsp+1500h+var_14A0], edi
0x1800052f1  mov     [rsp+1500h+var_149C], r15d
0x1800052f6  mov     [rsp+1500h+var_14B8], r12
0x1800052fb  mov     [rsp+1500h+var_14B0], r12
0x180005300  mov     [rbp+1400h+var_1458], r14
0x180005304  mov     [rbp+1400h+var_1450], rbx
0x180005308  mov     [rsp+1500h+var_1498], r12
0x18000530d  xorps   xmm0, xmm0
0x180005310  xor     eax, eax
0x180005312  movups  [rbp+1400h+var_1478], xmm0
0x180005316  mov     [rbp+1400h+var_1468], rax
0x18000531a  xorps   xmm1, xmm1
0x18000531d  movups  [rsp+1500h+var_1490], xmm1
0x180005322  mov     [rbp+1400h+var_1480], rax
0x180005326  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000532d  test    rax, rax
0x180005330  jz      short loc_18000533D
0x180005332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005337  mov     [rbp+1400h+var_1460], rax
0x18000533b  jmp     short loc_180005341
0x18000533d  mov     [rbp+1400h+var_1460], r12
0x180005341  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005348  test    rax, rax
0x18000534b  jz      short loc_180005357
0x18000534d  lea     rcx, [rsp+1500h+var_14E0]
0x180005352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005357  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000535e  test    rax, rax
0x180005361  jz      short loc_180005377
0x180005363  mov     r8d, 400h
0x180005369  lea     rdx, [rbp+1400h+var_1440]
0x18000536d  lea     rcx, [rsp+1500h+var_14E0]
0x180005372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005377  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000537e  test    rax, rax
0x180005381  jz      short loc_18000538D
0x180005383  lea     rcx, [rsp+1500h+var_14E0]
0x180005388  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000538d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005394  test    rax, rax
0x180005397  jz      short loc_1800053AA
0x180005399  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000539e  jnz     short loc_1800053AA
0x1800053a0  lea     rcx, [rsp+1500h+var_14E0]
0x1800053a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053aa  cmp     [rsp+1500h+var_14D8], r12d
0x1800053af  jge     loc_1800054B8
0x1800053b5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800053bc  jnz     short loc_1800053DD
0x1800053be  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800053c5  test    rax, rax
0x1800053c8  jz      short loc_1800053D3
0x1800053ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053cf  test    al, al
0x1800053d1  jmp     short loc_1800053DB
0x1800053d3  call    cs:__imp_IsDebuggerPresent
0x1800053d9  test    eax, eax
0x1800053db  jz      short loc_1800053E4
0x1800053dd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800053e2  jz      short loc_18000540A
0x1800053e4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800053eb  test    rax, rax
0x1800053ee  jz      short loc_180005463
0x1800053f0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800053f7  jnz     short loc_180005463
0x1800053f9  xor     r8d, r8d
0x1800053fc  xor     edx, edx
0x1800053fe  lea     rcx, [rsp+1500h+var_14E0]
0x180005403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005408  jmp     short loc_180005463
0x18000540a  mov     ebx, 800h
0x18000540f  mov     rax, cs:g_pfnResultLoggingCallback
0x180005416  test    rax, rax
0x180005419  jz      short loc_180005438
0x18000541b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005422  jnz     short loc_180005438
0x180005424  mov     r8d, ebx
0x180005427  lea     rdx, [rbp+1400h+OutputString]
0x18000542e  lea     rcx, [rsp+1500h+var_14E0]
0x180005433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005438  cmp     [rbp+1400h+OutputString], r12w
0x180005440  jnz     short loc_180005456
0x180005442  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180005447  mov     rdx, rbx; unsigned __int16 *
0x18000544a  lea     rcx, [rbp+1400h+OutputString]; this
0x180005451  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005456  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000545d  call    cs:__imp_OutputDebugStringW
0x180005463  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180005468  jnz     short loc_180005473
0x18000546a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180005471  jz      short loc_180005485
0x180005473  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000547a  test    rax, rax
0x18000547d  jz      short loc_180005485
0x18000547f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005484  nop
0x180005485  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000548a  jnz     short loc_1800054AD
0x18000548c  mov     rcx, [rbp+1400h+var_40]
0x180005493  xor     rcx, rsp; StackCookie
0x180005496  call    __security_check_cookie
0x18000549b  add     rsp, 14D0h
0x1800054a2  pop     r15
0x1800054a4  pop     r14
0x1800054a6  pop     r12
0x1800054a8  pop     rdi
0x1800054a9  pop     rsi
0x1800054aa  pop     rbx
0x1800054ab  pop     rbp
0x1800054ac  retn
0x1800054ad  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800054b2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800054b8  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
