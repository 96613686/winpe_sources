# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x14000783c`
- end: `0x140007aef`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140007664`

## callees

- `0x14000295f`
- `0x140004284`
- `0x140005174`
- `0x140005d30`
- `0x140006060`
- `0x140006234`
- `0x14000783c`
- `0x14000e280`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400078e5`
- `KERNEL32!GetCurrentThreadId` at `0x1400078e5`
- `KERNEL32!OutputDebugStringW` at `0x140007a83`
- `KERNEL32!OutputDebugStringW` at `0x140007a83`
- `KERNEL32!IsDebuggerPresent` at `0x1400079e7`
- `KERNEL32!IsDebuggerPresent` at `0x1400079e7`

## string_xrefs

- `0x1400078ef`: `onecoreuap\internal\shell\inc\cloudexperiencehostbrokerhelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v9; // r15
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  char v17; // bl
  const struct wil::FailureInfo *v18; // rdx
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v9 = g_pfnThrowPlatformException != 0;
  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v21 = *a7;
  v22 = a7[1];
  v10 = wil::details::RecordException((wil::details *)(unsigned int)v21, (int)a7);
  v19 = 0;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v20 = v11;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v28 = "onecoreuap\\internal\\shell\\inc\\cloudexperiencehostbrokerhelpers.h";
  v29 = a2;
  v30 = v10;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && !v9 && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v17 = 1, (v20 & 2) != 0) )
  {
    v17 = 0;
  }
  if ( v9 || v17 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v15);
    if ( v17 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v13);
  if ( v9 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v19, OutputString);
  wil::ThrowResultException((wil *)&v19, v13);
  wil::details::WilFailFast((wil::details *)&v19, v18);
}

```

## disassembly

```asm
0x14000783c  mov     [rsp-8+arg_10], rbx
0x140007841  mov     [rsp-8+arg_18], rsi
0x140007846  push    rbp
0x140007847  push    rdi
0x140007848  push    r12
0x14000784a  push    r14
0x14000784c  push    r15
0x14000784e  lea     rbp, [rsp-13C0h]
0x140007856  mov     eax, 14C0h
0x14000785b  call    _alloca_probe
0x140007860  sub     rsp, rax
0x140007863  mov     esi, edx
0x140007865  mov     r14, rcx
0x140007868  mov     rdi, [rbp+13E0h+arg_28]
0x14000786f  xor     r12d, r12d
0x140007872  cmp     cs:g_pfnThrowPlatformException, r12
0x140007879  setnz   r15b
0x14000787d  xor     edx, edx; Val
0x14000787f  mov     r8d, 98h; Size
0x140007885  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x14000788a  call    memset_0
0x14000788f  nop
0x140007890  mov     [rbp+13E0h+OutputString], r12w
0x140007898  mov     [rbp+13E0h+var_1420], r12b
0x14000789c  mov     rdx, qword ptr [rbp+13E0h+arg_30]; int
0x1400078a3  mov     ecx, [rdx]; this
0x1400078a5  mov     [rsp+14E0h+var_14B8], ecx
0x1400078a9  mov     eax, [rdx+4]
0x1400078ac  mov     [rsp+14E0h+var_14B4], eax
0x1400078b0  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400078b5  mov     ebx, eax
0x1400078b7  mov     dword ptr [rsp+14E0h+var_14C0], r12d
0x1400078bc  mov     ecx, r12d
0x1400078bf  lea     eax, [r12+8]
0x1400078c4  cmp     dword ptr [rdx+8], 1
0x1400078c8  cmovz   ecx, eax
0x1400078cb  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1400078cf  lea     ecx, [rax-7]
0x1400078d2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400078da  inc     ecx
0x1400078dc  mov     [rsp+14E0h+var_14B0], ecx
0x1400078e0  mov     [rsp+14E0h+var_14A8], r12
0x1400078e5  call    cs:__imp_GetCurrentThreadId
0x1400078eb  mov     [rsp+14E0h+var_14A0], eax
0x1400078ef  lea     rax, aOnecoreuapInte; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x1400078f6  mov     [rsp+14E0h+var_1488], rax
0x1400078fb  mov     [rsp+14E0h+var_1480], esi
0x1400078ff  mov     [rsp+14E0h+var_147C], ebx
0x140007903  mov     [rsp+14E0h+var_1498], r12
0x140007908  mov     [rsp+14E0h+var_1490], r12
0x14000790d  mov     [rbp+13E0h+var_1438], rdi
0x140007911  mov     [rbp+13E0h+var_1430], r14
0x140007915  mov     [rsp+14E0h+var_1478], r12
0x14000791a  xorps   xmm0, xmm0
0x14000791d  xor     eax, eax
0x14000791f  movups  [rbp+13E0h+var_1458], xmm0
0x140007923  mov     [rbp+13E0h+var_1448], rax
0x140007927  xorps   xmm1, xmm1
0x14000792a  movups  [rsp+14E0h+var_1470], xmm1
0x14000792f  mov     [rbp+13E0h+var_1460], rax
0x140007933  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000793a  test    rax, rax
0x14000793d  jz      short loc_14000794A
0x14000793f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007944  mov     [rbp+13E0h+var_1440], rax
0x140007948  jmp     short loc_14000794E
0x14000794a  mov     [rbp+13E0h+var_1440], r12
0x14000794e  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140007955  test    rax, rax
0x140007958  jz      short loc_140007964
0x14000795a  lea     rcx, [rsp+14E0h+var_14C0]
0x14000795f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007964  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000796b  test    rax, rax
0x14000796e  jz      short loc_140007984
0x140007970  mov     r8d, 400h
0x140007976  lea     rdx, [rbp+13E0h+var_1420]
0x14000797a  lea     rcx, [rsp+14E0h+var_14C0]
0x14000797f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007984  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000798b  test    rax, rax
0x14000798e  jz      short loc_14000799A
0x140007990  lea     rcx, [rsp+14E0h+var_14C0]
0x140007995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000799a  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400079a1  test    rax, rax
0x1400079a4  jz      short loc_1400079BC
0x1400079a6  test    r15b, r15b
0x1400079a9  jnz     short loc_1400079BC
0x1400079ab  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1400079b0  jnz     short loc_1400079BC
0x1400079b2  lea     rcx, [rsp+14E0h+var_14C0]
0x1400079b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400079bc  cmp     [rsp+14E0h+var_14B8], r12d
0x1400079c1  jl      short loc_1400079C9
0x1400079c3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400079c9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400079d0  jnz     short loc_1400079F1
0x1400079d2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400079d9  test    rax, rax
0x1400079dc  jz      short loc_1400079E7
0x1400079de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400079e3  test    al, al
0x1400079e5  jmp     short loc_1400079EF
0x1400079e7  call    cs:__imp_IsDebuggerPresent
0x1400079ed  test    eax, eax
0x1400079ef  jz      short loc_1400079FA
0x1400079f1  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1400079f6  mov     bl, 1
0x1400079f8  jz      short loc_1400079FD
0x1400079fa  mov     bl, r12b
0x1400079fd  test    r15b, r15b
0x140007a00  jnz     short loc_140007A2C
0x140007a02  test    bl, bl
0x140007a04  jnz     short loc_140007A2C
0x140007a06  mov     rax, cs:g_pfnResultLoggingCallback
0x140007a0d  test    rax, rax
0x140007a10  jz      short loc_140007A89
0x140007a12  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140007a19  jnz     short loc_140007A89
0x140007a1b  xor     r8d, r8d
0x140007a1e  xor     edx, edx
0x140007a20  lea     rcx, [rsp+14E0h+var_14C0]
0x140007a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a2a  jmp     short loc_140007A89
0x140007a2c  mov     edi, 800h
0x140007a31  mov     rax, cs:g_pfnResultLoggingCallback
0x140007a38  test    rax, rax
0x140007a3b  jz      short loc_140007A5A
0x140007a3d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140007a44  jnz     short loc_140007A5A
0x140007a46  mov     r8d, edi
0x140007a49  lea     rdx, [rbp+13E0h+OutputString]
0x140007a50  lea     rcx, [rsp+14E0h+var_14C0]
0x140007a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007a5a  cmp     [rbp+13E0h+OutputString], r12w
0x140007a62  jnz     short loc_140007A78
0x140007a64  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x140007a69  mov     rdx, rdi; unsigned __int16 *
0x140007a6c  lea     rcx, [rbp+13E0h+OutputString]; this
0x140007a73  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140007a78  test    bl, bl
0x140007a7a  jz      short loc_140007A89
0x140007a7c  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x140007a83  call    cs:__imp_OutputDebugStringW
0x140007a89  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x140007a8e  jnz     short loc_140007A99
0x140007a90  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140007a97  jz      short loc_140007AAB
0x140007a99  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140007aa0  test    rax, rax
0x140007aa3  jz      short loc_140007AAB
0x140007aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007aaa  nop
0x140007aab  test    byte ptr [rsp+14E0h+var_14C0+4], 1
0x140007ab0  jz      short loc_140007ABD
0x140007ab2  lea     rcx, [rsp+14E0h+var_14C0]; this
0x140007ab7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140007abd  test    r15b, r15b
0x140007ac0  jz      short loc_140007ADA
0x140007ac2  lea     rdx, [rbp+13E0h+OutputString]
0x140007ac9  lea     rcx, [rsp+14E0h+var_14C0]
0x140007ace  mov     rax, cs:g_pfnThrowPlatformException
0x140007ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ada  lea     rcx, [rsp+14E0h+var_14C0]; this
0x140007adf  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x140007ae4  lea     rcx, [rsp+14E0h+var_14C0]; this
0x140007ae9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
