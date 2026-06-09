# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180075694`
- end: `0x180075928`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `660`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18007519c`

## callees

- `0x180075694`
- `0x180077204`
- `0x180079330`
- `0x18007acd0`
- `0x18007ae8c`
- `0x18009110a`
- `0x180091140`
- `0x1800911d0`
- `0x180092010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18007573e`
- `KERNEL32!GetCurrentThreadId` at `0x18007573e`
- `KERNEL32!IsDebuggerPresent` at `0x180075839`
- `KERNEL32!IsDebuggerPresent` at `0x180075839`
- `KERNEL32!OutputDebugStringW` at `0x1800758c3`
- `KERNEL32!OutputDebugStringW` at `0x1800758c3`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  int v12; // ebx
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v18 = *(_DWORD *)(v11 + 8) == 1;
  v12 = v10;
  v19 = 1;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "wil";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x180075694  mov     [rsp-8+arg_10], rbx
0x180075699  push    rbp
0x18007569a  push    rsi
0x18007569b  push    rdi
0x18007569c  push    r14
0x18007569e  push    r15
0x1800756a0  lea     rbp, [rsp-13D0h]
0x1800756a8  mov     eax, 14D0h
0x1800756ad  call    _alloca_probe
0x1800756b2  sub     rsp, rax
0x1800756b5  mov     rax, cs:__security_cookie
0x1800756bc  xor     rax, rsp
0x1800756bf  mov     [rbp+13F0h+var_30], rax
0x1800756c6  mov     rdi, [rbp+13F0h+arg_28]
0x1800756cd  mov     esi, edx
0x1800756cf  mov     r14, rcx
0x1800756d2  xor     edx, edx; Val
0x1800756d4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800756d9  mov     r8d, 98h; Size
0x1800756df  call    memset_0
0x1800756e4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800756eb  xor     r15d, r15d
0x1800756ee  mov     [rbp+13F0h+OutputString], r15w
0x1800756f6  mov     [rbp+13F0h+var_1430], r15b
0x1800756fa  mov     ecx, [rdx]; this
0x1800756fc  mov     eax, [rdx+4]
0x1800756ff  mov     [rsp+14F0h+var_14C8], ecx
0x180075703  mov     [rsp+14F0h+var_14C4], eax
0x180075707  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18007570c  cmp     dword ptr [rdx+8], 1
0x180075710  mov     ebx, eax
0x180075712  lea     eax, [r15+8]
0x180075716  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x18007571e  mov     ecx, r15d
0x180075721  cmovz   ecx, eax
0x180075724  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180075728  lea     ecx, [rax-7]
0x18007572b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180075733  inc     ecx
0x180075735  mov     [rsp+14F0h+var_14B8], r15
0x18007573a  mov     [rsp+14F0h+var_14C0], ecx
0x18007573e  call    cs:__imp_GetCurrentThreadId
0x180075744  xorps   xmm0, xmm0
0x180075747  mov     [rsp+14F0h+var_1490], esi
0x18007574b  mov     [rsp+14F0h+var_14B0], eax
0x18007574f  xorps   xmm1, xmm1
0x180075752  lea     rax, aWil; "wil"
0x180075759  mov     [rsp+14F0h+var_148C], ebx
0x18007575d  mov     [rsp+14F0h+var_1498], rax
0x180075762  xor     eax, eax
0x180075764  mov     [rbp+13F0h+var_1458], rax
0x180075768  mov     [rbp+13F0h+var_1470], rax
0x18007576c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180075773  mov     [rsp+14F0h+var_14A8], r15
0x180075778  mov     [rsp+14F0h+var_14A0], r15
0x18007577d  mov     [rbp+13F0h+var_1448], rdi
0x180075781  mov     [rbp+13F0h+var_1440], r14
0x180075785  mov     [rsp+14F0h+var_1488], r15
0x18007578a  movups  [rbp+13F0h+var_1468], xmm0
0x18007578e  movups  [rsp+14F0h+var_1480], xmm1
0x180075793  test    rax, rax
0x180075796  jz      short loc_1800757A3
0x180075798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007579d  mov     [rbp+13F0h+var_1450], rax
0x1800757a1  jmp     short loc_1800757A7
0x1800757a3  mov     [rbp+13F0h+var_1450], r15
0x1800757a7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800757ae  test    rax, rax
0x1800757b1  jz      short loc_1800757BD
0x1800757b3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800757b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800757bd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800757c4  test    rax, rax
0x1800757c7  jz      short loc_1800757DD
0x1800757c9  mov     r8d, 400h
0x1800757cf  lea     rdx, [rbp+13F0h+var_1430]
0x1800757d3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800757d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800757dd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800757e4  test    rax, rax
0x1800757e7  jz      short loc_1800757F3
0x1800757e9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800757ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800757f3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800757fa  test    rax, rax
0x1800757fd  jz      short loc_180075810
0x1800757ff  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180075804  jnz     short loc_180075810
0x180075806  lea     rcx, [rsp+14F0h+var_14D0]
0x18007580b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075810  cmp     [rsp+14F0h+var_14C8], r15d
0x180075815  jge     loc_180075917
0x18007581b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180075822  jnz     short loc_180075843
0x180075824  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18007582b  test    rax, rax
0x18007582e  jz      short loc_180075839
0x180075830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075835  test    al, al
0x180075837  jmp     short loc_180075841
0x180075839  call    cs:__imp_IsDebuggerPresent
0x18007583f  test    eax, eax
0x180075841  jz      short loc_18007584A
0x180075843  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180075848  jz      short loc_180075870
0x18007584a  mov     rax, cs:g_pfnResultLoggingCallback
0x180075851  test    rax, rax
0x180075854  jz      short loc_1800758C9
0x180075856  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18007585d  jnz     short loc_1800758C9
0x18007585f  xor     r8d, r8d
0x180075862  lea     rcx, [rsp+14F0h+var_14D0]
0x180075867  xor     edx, edx
0x180075869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007586e  jmp     short loc_1800758C9
0x180075870  mov     rax, cs:g_pfnResultLoggingCallback
0x180075877  mov     ebx, 800h
0x18007587c  test    rax, rax
0x18007587f  jz      short loc_18007589E
0x180075881  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180075888  jnz     short loc_18007589E
0x18007588a  mov     r8d, ebx
0x18007588d  lea     rdx, [rbp+13F0h+OutputString]
0x180075894  lea     rcx, [rsp+14F0h+var_14D0]
0x180075899  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007589e  cmp     [rbp+13F0h+OutputString], r15w
0x1800758a6  jnz     short loc_1800758BC
0x1800758a8  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800758ad  mov     rdx, rbx; unsigned __int16 *
0x1800758b0  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800758b7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800758bc  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800758c3  call    cs:__imp_OutputDebugStringW
0x1800758c9  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800758ce  jnz     short loc_1800758D9
0x1800758d0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x1800758d7  jz      short loc_1800758EA
0x1800758d9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800758e0  test    rax, rax
0x1800758e3  jz      short loc_1800758EA
0x1800758e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800758ea  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800758ef  jnz     short loc_18007591D
0x1800758f1  mov     rcx, [rbp+13F0h+var_30]
0x1800758f8  xor     rcx, rsp; StackCookie
0x1800758fb  call    __security_check_cookie
0x180075900  mov     rbx, [rsp+14F0h+arg_10]
0x180075908  add     rsp, 14D0h
0x18007590f  pop     r15
0x180075911  pop     r14
0x180075913  pop     rdi
0x180075914  pop     rsi
0x180075915  pop     rbp
0x180075916  retn
0x180075917  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18007591d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180075922  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
