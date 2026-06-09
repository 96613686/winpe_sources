# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400030b0`
- end: `0x14000333d`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002d74`

## callees

- `0x1400030b0`
- `0x140004564`
- `0x1400055b0`
- `0x140006058`
- `0x140006340`
- `0x14001a8aa`
- `0x14001a8d0`
- `0x14001a960`
- `0x14001c010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1400032dc`
- `KERNEL32!OutputDebugStringW` at `0x1400032dc`
- `KERNEL32!IsDebuggerPresent` at `0x140003252`
- `KERNEL32!IsDebuggerPresent` at `0x140003252`
- `KERNEL32!GetCurrentThreadId` at `0x14000315e`
- `KERNEL32!GetCurrentThreadId` at `0x14000315e`

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
0x1400030b0  push    rbp
0x1400030b2  push    rbx
0x1400030b3  push    rsi
0x1400030b4  push    rdi
0x1400030b5  push    r12
0x1400030b7  push    r14
0x1400030b9  push    r15
0x1400030bb  lea     rbp, [rsp-13D0h]
0x1400030c3  mov     eax, 14D0h
0x1400030c8  call    _alloca_probe
0x1400030cd  sub     rsp, rax
0x1400030d0  mov     rax, cs:__security_cookie
0x1400030d7  xor     rax, rsp
0x1400030da  mov     [rbp+1400h+var_40], rax
0x1400030e1  mov     r14, r8
0x1400030e4  mov     esi, edx
0x1400030e6  mov     r15, rcx
0x1400030e9  mov     rdi, [rbp+1400h+arg_28]
0x1400030f0  xor     edx, edx; Val
0x1400030f2  mov     r8d, 98h; Size
0x1400030f8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400030fd  call    memset_0
0x140003102  nop
0x140003103  xor     r12d, r12d
0x140003106  mov     [rbp+1400h+OutputString], r12w
0x14000310e  mov     [rbp+1400h+var_1440], r12b
0x140003112  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x140003119  mov     ecx, [rdx]; this
0x14000311b  mov     [rsp+1500h+var_14D8], ecx
0x14000311f  mov     eax, [rdx+4]
0x140003122  mov     [rsp+1500h+var_14D4], eax
0x140003126  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000312b  mov     ebx, eax
0x14000312d  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140003135  mov     ecx, r12d
0x140003138  lea     eax, [r12+8]
0x14000313d  cmp     dword ptr [rdx+8], 1
0x140003141  cmovz   ecx, eax
0x140003144  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140003148  lea     ecx, [rax-7]
0x14000314b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003153  inc     ecx
0x140003155  mov     [rsp+1500h+var_14D0], ecx
0x140003159  mov     [rsp+1500h+var_14C8], r12
0x14000315e  call    cs:__imp_GetCurrentThreadId
0x140003164  mov     [rsp+1500h+var_14C0], eax
0x140003168  mov     [rsp+1500h+var_14A8], r14
0x14000316d  mov     [rsp+1500h+var_14A0], esi
0x140003171  mov     [rsp+1500h+var_149C], ebx
0x140003175  mov     [rsp+1500h+var_14B8], r12
0x14000317a  mov     [rsp+1500h+var_14B0], r12
0x14000317f  mov     [rbp+1400h+var_1458], rdi
0x140003183  mov     [rbp+1400h+var_1450], r15
0x140003187  mov     [rsp+1500h+var_1498], r12
0x14000318c  xorps   xmm0, xmm0
0x14000318f  xor     eax, eax
0x140003191  movups  [rbp+1400h+var_1478], xmm0
0x140003195  mov     [rbp+1400h+var_1468], rax
0x140003199  xorps   xmm1, xmm1
0x14000319c  movups  [rsp+1500h+var_1490], xmm1
0x1400031a1  mov     [rbp+1400h+var_1480], rax
0x1400031a5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400031ac  test    rax, rax
0x1400031af  jz      short loc_1400031BC
0x1400031b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031b6  mov     [rbp+1400h+var_1460], rax
0x1400031ba  jmp     short loc_1400031C0
0x1400031bc  mov     [rbp+1400h+var_1460], r12
0x1400031c0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400031c7  test    rax, rax
0x1400031ca  jz      short loc_1400031D6
0x1400031cc  lea     rcx, [rsp+1500h+var_14E0]
0x1400031d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031d6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400031dd  test    rax, rax
0x1400031e0  jz      short loc_1400031F6
0x1400031e2  mov     r8d, 400h
0x1400031e8  lea     rdx, [rbp+1400h+var_1440]
0x1400031ec  lea     rcx, [rsp+1500h+var_14E0]
0x1400031f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031f6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400031fd  test    rax, rax
0x140003200  jz      short loc_14000320C
0x140003202  lea     rcx, [rsp+1500h+var_14E0]
0x140003207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000320c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003213  test    rax, rax
0x140003216  jz      short loc_140003229
0x140003218  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x14000321d  jnz     short loc_140003229
0x14000321f  lea     rcx, [rsp+1500h+var_14E0]
0x140003224  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003229  cmp     [rsp+1500h+var_14D8], r12d
0x14000322e  jge     loc_140003337
0x140003234  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000323b  jnz     short loc_14000325C
0x14000323d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003244  test    rax, rax
0x140003247  jz      short loc_140003252
0x140003249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000324e  test    al, al
0x140003250  jmp     short loc_14000325A
0x140003252  call    cs:__imp_IsDebuggerPresent
0x140003258  test    eax, eax
0x14000325a  jz      short loc_140003263
0x14000325c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003261  jz      short loc_140003289
0x140003263  mov     rax, cs:g_pfnResultLoggingCallback
0x14000326a  test    rax, rax
0x14000326d  jz      short loc_1400032E2
0x14000326f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003276  jnz     short loc_1400032E2
0x140003278  xor     r8d, r8d
0x14000327b  xor     edx, edx
0x14000327d  lea     rcx, [rsp+1500h+var_14E0]
0x140003282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003287  jmp     short loc_1400032E2
0x140003289  mov     ebx, 800h
0x14000328e  mov     rax, cs:g_pfnResultLoggingCallback
0x140003295  test    rax, rax
0x140003298  jz      short loc_1400032B7
0x14000329a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400032a1  jnz     short loc_1400032B7
0x1400032a3  mov     r8d, ebx
0x1400032a6  lea     rdx, [rbp+1400h+OutputString]
0x1400032ad  lea     rcx, [rsp+1500h+var_14E0]
0x1400032b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400032b7  cmp     [rbp+1400h+OutputString], r12w
0x1400032bf  jnz     short loc_1400032D5
0x1400032c1  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1400032c6  mov     rdx, rbx; unsigned __int16 *
0x1400032c9  lea     rcx, [rbp+1400h+OutputString]; this
0x1400032d0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400032d5  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1400032dc  call    cs:__imp_OutputDebugStringW
0x1400032e2  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1400032e7  jnz     short loc_1400032F2
0x1400032e9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400032f0  jz      short loc_140003304
0x1400032f2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400032f9  test    rax, rax
0x1400032fc  jz      short loc_140003304
0x1400032fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003303  nop
0x140003304  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140003309  jnz     short loc_14000332C
0x14000330b  mov     rcx, [rbp+1400h+var_40]
0x140003312  xor     rcx, rsp; StackCookie
0x140003315  call    __security_check_cookie
0x14000331a  add     rsp, 14D0h
0x140003321  pop     r15
0x140003323  pop     r14
0x140003325  pop     r12
0x140003327  pop     rdi
0x140003328  pop     rsi
0x140003329  pop     rbx
0x14000332a  pop     rbp
0x14000332b  retn
0x14000332c  lea     rcx, [rsp+1500h+var_14E0]; this
0x140003331  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140003337  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
