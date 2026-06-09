# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000454c`
- end: `0x1800047f2`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004050`

## callees

- `0x180002dc0`
- `0x18000399c`
- `0x18000454c`
- `0x1800067c0`
- `0x180007a60`
- `0x180008858`
- `0x180008a44`
- `0x1800284d0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004612`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004612`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004707`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004707`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004791`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004791`

## pseudocode

```c
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
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
0x18000454c  push    rbp
0x18000454e  push    rbx
0x18000454f  push    rsi
0x180004550  push    rdi
0x180004551  push    r12
0x180004553  push    r14
0x180004555  push    r15
0x180004557  lea     rbp, [rsp-13D0h]
0x18000455f  mov     eax, 14D0h
0x180004564  call    _alloca_probe
0x180004569  sub     rsp, rax
0x18000456c  mov     rax, cs:__security_cookie
0x180004573  xor     rax, rsp
0x180004576  mov     [rbp+1400h+var_40], rax
0x18000457d  mov     rsi, r8
0x180004580  mov     edi, edx
0x180004582  mov     rbx, rcx
0x180004585  mov     r14, [rbp+1400h+arg_28]
0x18000458c  xor     edx, edx; Val
0x18000458e  mov     r8d, 98h; Size
0x180004594  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004599  call    memset_0
0x18000459e  nop
0x18000459f  xor     r12d, r12d
0x1800045a2  mov     [rbp+1400h+OutputString], r12w
0x1800045aa  mov     [rbp+1400h+var_1440], r12b
0x1800045ae  mov     rdx, [rbp+1400h+arg_30]; int
0x1800045b5  mov     ecx, [rdx]; this
0x1800045b7  mov     [rsp+1500h+var_14D8], ecx
0x1800045bb  mov     eax, [rdx+4]
0x1800045be  mov     [rsp+1500h+var_14D4], eax
0x1800045c2  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800045c7  mov     r15d, eax
0x1800045ca  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800045d2  mov     ecx, r12d
0x1800045d5  lea     eax, [r12+8]
0x1800045da  cmp     dword ptr [rdx+8], 1
0x1800045de  cmovz   ecx, eax
0x1800045e1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800045e5  lea     ecx, [rax-7]
0x1800045e8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800045f0  inc     ecx
0x1800045f2  mov     [rsp+1500h+var_14D0], ecx
0x1800045f6  mov     rcx, [rbp+1400h+arg_38]
0x1800045fd  test    rcx, rcx
0x180004600  jz      short loc_18000460D
0x180004602  cmp     [rcx], r12w
0x180004606  mov     [rsp+1500h+var_14C8], rcx
0x18000460b  jnz     short loc_180004612
0x18000460d  mov     [rsp+1500h+var_14C8], r12
0x180004612  call    cs:__imp_GetCurrentThreadId
0x180004618  mov     [rsp+1500h+var_14C0], eax
0x18000461c  mov     [rsp+1500h+var_14A8], rsi
0x180004621  mov     [rsp+1500h+var_14A0], edi
0x180004625  mov     [rsp+1500h+var_149C], r15d
0x18000462a  mov     [rsp+1500h+var_14B8], r12
0x18000462f  mov     [rsp+1500h+var_14B0], r12
0x180004634  mov     [rbp+1400h+var_1458], r14
0x180004638  mov     [rbp+1400h+var_1450], rbx
0x18000463c  mov     [rsp+1500h+var_1498], r12
0x180004641  xorps   xmm0, xmm0
0x180004644  xor     eax, eax
0x180004646  movups  [rbp+1400h+var_1478], xmm0
0x18000464a  mov     [rbp+1400h+var_1468], rax
0x18000464e  xorps   xmm1, xmm1
0x180004651  movups  [rsp+1500h+var_1490], xmm1
0x180004656  mov     [rbp+1400h+var_1480], rax
0x18000465a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004661  test    rax, rax
0x180004664  jz      short loc_180004671
0x180004666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000466b  mov     [rbp+1400h+var_1460], rax
0x18000466f  jmp     short loc_180004675
0x180004671  mov     [rbp+1400h+var_1460], r12
0x180004675  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000467c  test    rax, rax
0x18000467f  jz      short loc_18000468B
0x180004681  lea     rcx, [rsp+1500h+var_14E0]
0x180004686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000468b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004692  test    rax, rax
0x180004695  jz      short loc_1800046AB
0x180004697  mov     r8d, 400h
0x18000469d  lea     rdx, [rbp+1400h+var_1440]
0x1800046a1  lea     rcx, [rsp+1500h+var_14E0]
0x1800046a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ab  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800046b2  test    rax, rax
0x1800046b5  jz      short loc_1800046C1
0x1800046b7  lea     rcx, [rsp+1500h+var_14E0]
0x1800046bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046c1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800046c8  test    rax, rax
0x1800046cb  jz      short loc_1800046DE
0x1800046cd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800046d2  jnz     short loc_1800046DE
0x1800046d4  lea     rcx, [rsp+1500h+var_14E0]
0x1800046d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046de  cmp     [rsp+1500h+var_14D8], r12d
0x1800046e3  jge     loc_1800047EC
0x1800046e9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800046f0  jnz     short loc_180004711
0x1800046f2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800046f9  test    rax, rax
0x1800046fc  jz      short loc_180004707
0x1800046fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004703  test    al, al
0x180004705  jmp     short loc_18000470F
0x180004707  call    cs:__imp_IsDebuggerPresent
0x18000470d  test    eax, eax
0x18000470f  jz      short loc_180004718
0x180004711  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004716  jz      short loc_18000473E
0x180004718  mov     rax, cs:g_pfnResultLoggingCallback
0x18000471f  test    rax, rax
0x180004722  jz      short loc_180004797
0x180004724  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000472b  jnz     short loc_180004797
0x18000472d  xor     r8d, r8d
0x180004730  xor     edx, edx
0x180004732  lea     rcx, [rsp+1500h+var_14E0]
0x180004737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000473c  jmp     short loc_180004797
0x18000473e  mov     ebx, 800h
0x180004743  mov     rax, cs:g_pfnResultLoggingCallback
0x18000474a  test    rax, rax
0x18000474d  jz      short loc_18000476C
0x18000474f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004756  jnz     short loc_18000476C
0x180004758  mov     r8d, ebx
0x18000475b  lea     rdx, [rbp+1400h+OutputString]
0x180004762  lea     rcx, [rsp+1500h+var_14E0]
0x180004767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000476c  cmp     [rbp+1400h+OutputString], r12w
0x180004774  jnz     short loc_18000478A
0x180004776  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000477b  mov     rdx, rbx; unsigned __int16 *
0x18000477e  lea     rcx, [rbp+1400h+OutputString]; this
0x180004785  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000478a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004791  call    cs:__imp_OutputDebugStringW
0x180004797  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000479c  jnz     short loc_1800047A7
0x18000479e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800047a5  jz      short loc_1800047B9
0x1800047a7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800047ae  test    rax, rax
0x1800047b1  jz      short loc_1800047B9
0x1800047b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800047b8  nop
0x1800047b9  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800047be  jnz     short loc_1800047E1
0x1800047c0  mov     rcx, [rbp+1400h+var_40]
0x1800047c7  xor     rcx, rsp; StackCookie
0x1800047ca  call    __security_check_cookie
0x1800047cf  add     rsp, 14D0h
0x1800047d6  pop     r15
0x1800047d8  pop     r14
0x1800047da  pop     r12
0x1800047dc  pop     rdi
0x1800047dd  pop     rsi
0x1800047de  pop     rbx
0x1800047df  pop     rbp
0x1800047e0  retn
0x1800047e1  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800047e6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800047ec  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
