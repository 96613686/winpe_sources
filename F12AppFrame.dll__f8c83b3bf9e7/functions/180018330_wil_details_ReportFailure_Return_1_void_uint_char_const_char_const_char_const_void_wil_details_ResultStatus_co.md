# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180018330`
- end: `0x1800185bd`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180017e10`

## callees

- `0x180001800`
- `0x180002678`
- `0x180018330`
- `0x180019f4c`
- `0x18001c230`
- `0x18001e070`
- `0x18001e14c`
- `0x180032a50`
- `0x180035010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800183de`
- `KERNEL32!GetCurrentThreadId` at `0x1800183de`
- `KERNEL32!IsDebuggerPresent` at `0x1800184d2`
- `KERNEL32!IsDebuggerPresent` at `0x1800184d2`
- `KERNEL32!OutputDebugStringW` at `0x18001855c`
- `KERNEL32!OutputDebugStringW` at `0x18001855c`

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
0x180018330  push    rbp
0x180018332  push    rbx
0x180018333  push    rsi
0x180018334  push    rdi
0x180018335  push    r12
0x180018337  push    r14
0x180018339  push    r15
0x18001833b  lea     rbp, [rsp-13D0h]
0x180018343  mov     eax, 14D0h
0x180018348  call    _alloca_probe
0x18001834d  sub     rsp, rax
0x180018350  mov     rax, cs:__security_cookie
0x180018357  xor     rax, rsp
0x18001835a  mov     [rbp+1400h+var_40], rax
0x180018361  mov     r14, r8
0x180018364  mov     esi, edx
0x180018366  mov     r15, rcx
0x180018369  mov     rdi, [rbp+1400h+arg_28]
0x180018370  xor     edx, edx; Val
0x180018372  mov     r8d, 98h; Size
0x180018378  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18001837d  call    memset_0
0x180018382  nop
0x180018383  xor     r12d, r12d
0x180018386  mov     [rbp+1400h+OutputString], r12w
0x18001838e  mov     [rbp+1400h+var_1440], r12b
0x180018392  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180018399  mov     ecx, [rdx]; this
0x18001839b  mov     [rsp+1500h+var_14D8], ecx
0x18001839f  mov     eax, [rdx+4]
0x1800183a2  mov     [rsp+1500h+var_14D4], eax
0x1800183a6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800183ab  mov     ebx, eax
0x1800183ad  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800183b5  mov     ecx, r12d
0x1800183b8  lea     eax, [r12+8]
0x1800183bd  cmp     dword ptr [rdx+8], 1
0x1800183c1  cmovz   ecx, eax
0x1800183c4  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800183c8  lea     ecx, [rax-7]
0x1800183cb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800183d3  inc     ecx
0x1800183d5  mov     [rsp+1500h+var_14D0], ecx
0x1800183d9  mov     [rsp+1500h+var_14C8], r12
0x1800183de  call    cs:__imp_GetCurrentThreadId
0x1800183e4  mov     [rsp+1500h+var_14C0], eax
0x1800183e8  mov     [rsp+1500h+var_14A8], r14
0x1800183ed  mov     [rsp+1500h+var_14A0], esi
0x1800183f1  mov     [rsp+1500h+var_149C], ebx
0x1800183f5  mov     [rsp+1500h+var_14B8], r12
0x1800183fa  mov     [rsp+1500h+var_14B0], r12
0x1800183ff  mov     [rbp+1400h+var_1458], rdi
0x180018403  mov     [rbp+1400h+var_1450], r15
0x180018407  mov     [rsp+1500h+var_1498], r12
0x18001840c  xorps   xmm0, xmm0
0x18001840f  xor     eax, eax
0x180018411  movups  [rbp+1400h+var_1478], xmm0
0x180018415  mov     [rbp+1400h+var_1468], rax
0x180018419  xorps   xmm1, xmm1
0x18001841c  movups  [rsp+1500h+var_1490], xmm1
0x180018421  mov     [rbp+1400h+var_1480], rax
0x180018425  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001842c  test    rax, rax
0x18001842f  jz      short loc_18001843C
0x180018431  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018436  mov     [rbp+1400h+var_1460], rax
0x18001843a  jmp     short loc_180018440
0x18001843c  mov     [rbp+1400h+var_1460], r12
0x180018440  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180018447  test    rax, rax
0x18001844a  jz      short loc_180018456
0x18001844c  lea     rcx, [rsp+1500h+var_14E0]
0x180018451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018456  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001845d  test    rax, rax
0x180018460  jz      short loc_180018476
0x180018462  mov     r8d, 400h
0x180018468  lea     rdx, [rbp+1400h+var_1440]
0x18001846c  lea     rcx, [rsp+1500h+var_14E0]
0x180018471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018476  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001847d  test    rax, rax
0x180018480  jz      short loc_18001848C
0x180018482  lea     rcx, [rsp+1500h+var_14E0]
0x180018487  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001848c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180018493  test    rax, rax
0x180018496  jz      short loc_1800184A9
0x180018498  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18001849d  jnz     short loc_1800184A9
0x18001849f  lea     rcx, [rsp+1500h+var_14E0]
0x1800184a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184a9  cmp     [rsp+1500h+var_14D8], r12d
0x1800184ae  jge     loc_1800185B7
0x1800184b4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800184bb  jnz     short loc_1800184DC
0x1800184bd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800184c4  test    rax, rax
0x1800184c7  jz      short loc_1800184D2
0x1800184c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800184ce  test    al, al
0x1800184d0  jmp     short loc_1800184DA
0x1800184d2  call    cs:__imp_IsDebuggerPresent
0x1800184d8  test    eax, eax
0x1800184da  jz      short loc_1800184E3
0x1800184dc  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800184e1  jz      short loc_180018509
0x1800184e3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800184ea  test    rax, rax
0x1800184ed  jz      short loc_180018562
0x1800184ef  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800184f6  jnz     short loc_180018562
0x1800184f8  xor     r8d, r8d
0x1800184fb  xor     edx, edx
0x1800184fd  lea     rcx, [rsp+1500h+var_14E0]
0x180018502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018507  jmp     short loc_180018562
0x180018509  mov     ebx, 800h
0x18001850e  mov     rax, cs:g_pfnResultLoggingCallback
0x180018515  test    rax, rax
0x180018518  jz      short loc_180018537
0x18001851a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180018521  jnz     short loc_180018537
0x180018523  mov     r8d, ebx
0x180018526  lea     rdx, [rbp+1400h+OutputString]
0x18001852d  lea     rcx, [rsp+1500h+var_14E0]
0x180018532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018537  cmp     [rbp+1400h+OutputString], r12w
0x18001853f  jnz     short loc_180018555
0x180018541  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180018546  mov     rdx, rbx; unsigned __int16 *
0x180018549  lea     rcx, [rbp+1400h+OutputString]; this
0x180018550  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180018555  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18001855c  call    cs:__imp_OutputDebugStringW
0x180018562  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180018567  jnz     short loc_180018572
0x180018569  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180018570  jz      short loc_180018584
0x180018572  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180018579  test    rax, rax
0x18001857c  jz      short loc_180018584
0x18001857e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018583  nop
0x180018584  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180018589  jnz     short loc_1800185AC
0x18001858b  mov     rcx, [rbp+1400h+var_40]
0x180018592  xor     rcx, rsp; StackCookie
0x180018595  call    __security_check_cookie
0x18001859a  add     rsp, 14D0h
0x1800185a1  pop     r15
0x1800185a3  pop     r14
0x1800185a5  pop     r12
0x1800185a7  pop     rdi
0x1800185a8  pop     rsi
0x1800185a9  pop     rbx
0x1800185aa  pop     rbp
0x1800185ab  retn
0x1800185ac  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800185b1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800185b7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
