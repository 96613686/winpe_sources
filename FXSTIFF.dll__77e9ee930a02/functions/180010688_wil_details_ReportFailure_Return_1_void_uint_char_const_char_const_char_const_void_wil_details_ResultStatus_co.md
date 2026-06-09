# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180010688`
- end: `0x180010931`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001014c`

## callees

- `0x180010688`
- `0x1800127e4`
- `0x180014178`
- `0x180016460`
- `0x180016634`
- `0x18001899e`
- `0x1800189d0`
- `0x180018a60`
- `0x180019010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180010834`
- `KERNEL32!IsDebuggerPresent` at `0x180010834`
- `KERNEL32!OutputDebugStringW` at `0x1800108c4`
- `KERNEL32!OutputDebugStringW` at `0x1800108c4`
- `KERNEL32!GetCurrentThreadId` at `0x180010733`
- `KERNEL32!GetCurrentThreadId` at `0x180010733`

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
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180010688  mov     [rsp-8+arg_10], rbx
0x18001068d  push    rbp
0x18001068e  push    rsi
0x18001068f  push    rdi
0x180010690  push    r14
0x180010692  push    r15
0x180010694  lea     rbp, [rsp-13D0h]
0x18001069c  mov     eax, 14D0h
0x1800106a1  call    _alloca_probe
0x1800106a6  sub     rsp, rax
0x1800106a9  mov     rax, cs:__security_cookie
0x1800106b0  xor     rax, rsp
0x1800106b3  mov     [rbp+13F0h+var_30], rax
0x1800106ba  mov     esi, edx
0x1800106bc  mov     r14, rcx
0x1800106bf  mov     rdi, [rbp+13F0h+arg_28]
0x1800106c6  xor     edx, edx; Val
0x1800106c8  mov     r8d, 98h; Size
0x1800106ce  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800106d3  call    memset_0
0x1800106d8  nop
0x1800106d9  xor     r15d, r15d
0x1800106dc  mov     [rbp+13F0h+OutputString], r15w
0x1800106e4  mov     [rbp+13F0h+var_1430], r15b
0x1800106e8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800106ef  mov     ecx, [rdx]; this
0x1800106f1  mov     [rsp+14F0h+var_14C8], ecx
0x1800106f5  mov     eax, [rdx+4]
0x1800106f8  mov     [rsp+14F0h+var_14C4], eax
0x1800106fc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180010701  mov     ebx, eax
0x180010703  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18001070b  mov     ecx, r15d
0x18001070e  lea     eax, [r15+8]
0x180010712  cmp     dword ptr [rdx+8], 1
0x180010716  cmovz   ecx, eax
0x180010719  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001071d  lea     ecx, [rax-7]
0x180010720  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180010728  inc     ecx
0x18001072a  mov     [rsp+14F0h+var_14C0], ecx
0x18001072e  mov     [rsp+14F0h+var_14B8], r15
0x180010733  call    cs:__imp_GetCurrentThreadId
0x18001073a  nop     dword ptr [rax+rax+00h]
0x18001073f  mov     [rsp+14F0h+var_14B0], eax
0x180010743  lea     rax, aWil; "wil"
0x18001074a  mov     [rsp+14F0h+var_1498], rax
0x18001074f  mov     [rsp+14F0h+var_1490], esi
0x180010753  mov     [rsp+14F0h+var_148C], ebx
0x180010757  mov     [rsp+14F0h+var_14A8], r15
0x18001075c  mov     [rsp+14F0h+var_14A0], r15
0x180010761  mov     [rbp+13F0h+var_1448], rdi
0x180010765  mov     [rbp+13F0h+var_1440], r14
0x180010769  mov     [rsp+14F0h+var_1488], r15
0x18001076e  xorps   xmm0, xmm0
0x180010771  xor     eax, eax
0x180010773  movups  [rbp+13F0h+var_1468], xmm0
0x180010777  mov     [rbp+13F0h+var_1458], rax
0x18001077b  xorps   xmm1, xmm1
0x18001077e  movups  [rsp+14F0h+var_1480], xmm1
0x180010783  mov     [rbp+13F0h+var_1470], rax
0x180010787  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001078e  test    rax, rax
0x180010791  jz      short loc_18001079E
0x180010793  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010798  mov     [rbp+13F0h+var_1450], rax
0x18001079c  jmp     short loc_1800107A2
0x18001079e  mov     [rbp+13F0h+var_1450], r15
0x1800107a2  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800107a9  test    rax, rax
0x1800107ac  jz      short loc_1800107B8
0x1800107ae  lea     rcx, [rsp+14F0h+var_14D0]
0x1800107b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107b8  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800107bf  test    rax, rax
0x1800107c2  jz      short loc_1800107D8
0x1800107c4  mov     r8d, 400h
0x1800107ca  lea     rdx, [rbp+13F0h+var_1430]
0x1800107ce  lea     rcx, [rsp+14F0h+var_14D0]
0x1800107d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107d8  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800107df  test    rax, rax
0x1800107e2  jz      short loc_1800107EE
0x1800107e4  lea     rcx, [rsp+14F0h+var_14D0]
0x1800107e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107ee  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800107f5  test    rax, rax
0x1800107f8  jz      short loc_18001080B
0x1800107fa  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800107ff  jnz     short loc_18001080B
0x180010801  lea     rcx, [rsp+14F0h+var_14D0]
0x180010806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001080b  cmp     [rsp+14F0h+var_14C8], r15d
0x180010810  jge     loc_18001092B
0x180010816  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x18001081d  jnz     short loc_180010844
0x18001081f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180010826  test    rax, rax
0x180010829  jz      short loc_180010834
0x18001082b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010830  test    al, al
0x180010832  jmp     short loc_180010842
0x180010834  call    cs:__imp_IsDebuggerPresent
0x18001083b  nop     dword ptr [rax+rax+00h]
0x180010840  test    eax, eax
0x180010842  jz      short loc_18001084B
0x180010844  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180010849  jz      short loc_180010871
0x18001084b  mov     rax, cs:g_pfnResultLoggingCallback
0x180010852  test    rax, rax
0x180010855  jz      short loc_1800108D0
0x180010857  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001085e  jnz     short loc_1800108D0
0x180010860  xor     r8d, r8d
0x180010863  xor     edx, edx
0x180010865  lea     rcx, [rsp+14F0h+var_14D0]
0x18001086a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001086f  jmp     short loc_1800108D0
0x180010871  mov     ebx, 800h
0x180010876  mov     rax, cs:g_pfnResultLoggingCallback
0x18001087d  test    rax, rax
0x180010880  jz      short loc_18001089F
0x180010882  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180010889  jnz     short loc_18001089F
0x18001088b  mov     r8d, ebx
0x18001088e  lea     rdx, [rbp+13F0h+OutputString]
0x180010895  lea     rcx, [rsp+14F0h+var_14D0]
0x18001089a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001089f  cmp     [rbp+13F0h+OutputString], r15w
0x1800108a7  jnz     short loc_1800108BD
0x1800108a9  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800108ae  mov     rdx, rbx; unsigned __int16 *
0x1800108b1  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800108b8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800108bd  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800108c4  call    cs:__imp_OutputDebugStringW
0x1800108cb  nop     dword ptr [rax+rax+00h]
0x1800108d0  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800108d5  jnz     short loc_1800108E0
0x1800108d7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800108de  jz      short loc_1800108F2
0x1800108e0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800108e7  test    rax, rax
0x1800108ea  jz      short loc_1800108F2
0x1800108ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108f1  nop
0x1800108f2  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800108f7  jnz     short loc_180010920
0x1800108f9  mov     rcx, [rbp+13F0h+var_30]
0x180010900  xor     rcx, rsp; StackCookie
0x180010903  call    __security_check_cookie
0x180010908  mov     rbx, [rsp+14F0h+arg_10]
0x180010910  add     rsp, 14D0h
0x180010917  pop     r15
0x180010919  pop     r14
0x18001091b  pop     rdi
0x18001091c  pop     rsi
0x18001091d  pop     rbp
0x18001091e  retn
0x180010920  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180010925  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001092b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
