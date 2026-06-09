# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800053e0`
- end: `0x180005676`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180005180`

## callees

- `0x1800022e0`
- `0x180002780`
- `0x180003cc0`
- `0x180003f10`
- `0x1800053e0`
- `0x180007280`
- `0x18000b8d0`
- `0x18000b930`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180005479`
- `KERNEL32!GetCurrentThreadId` at `0x180005479`
- `KERNEL32!OutputDebugStringW` at `0x18000560f`
- `KERNEL32!OutputDebugStringW` at `0x18000560f`
- `KERNEL32!IsDebuggerPresent` at `0x18000557c`
- `KERNEL32!IsDebuggerPresent` at `0x18000557c`

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
  int IsDebuggerPresent; // r15d
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // r8
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
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

  IsDebuggerPresent = 0;
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, a2);
  v16 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v17 = v11;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v10;
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
    ModuleName = wil::details::g_pfnGetModuleName(v14);
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14)),
         IsDebuggerPresent))
    && (v17 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v16, v15);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v13);
}

```

## disassembly

```asm
0x1800053e0  mov     [rsp-8+arg_10], rbx
0x1800053e5  push    rbp
0x1800053e6  push    rsi
0x1800053e7  push    rdi
0x1800053e8  push    r14
0x1800053ea  push    r15
0x1800053ec  lea     rbp, [rsp-13D0h]
0x1800053f4  mov     eax, 14D0h
0x1800053f9  call    _alloca_probe
0x1800053fe  sub     rsp, rax
0x180005401  mov     rax, cs:__security_cookie
0x180005408  xor     rax, rsp
0x18000540b  mov     [rbp+13F0h+var_30], rax
0x180005412  mov     esi, edx
0x180005414  mov     r14, rcx
0x180005417  mov     rdi, [rbp+13F0h+arg_28]
0x18000541e  xor     r15d, r15d
0x180005421  mov     [rbp+13F0h+OutputString], r15w
0x180005429  mov     [rbp+13F0h+var_1430], r15b
0x18000542d  mov     r8, [rbp+13F0h+arg_30]
0x180005434  mov     ecx, [r8]; this
0x180005437  mov     [rsp+14F0h+var_14C8], ecx
0x18000543b  mov     eax, [r8+4]
0x18000543f  mov     [rsp+14F0h+var_14C4], eax
0x180005443  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005448  mov     ebx, eax
0x18000544a  mov     edx, 1
0x18000544f  mov     dword ptr [rsp+14F0h+var_14D0], edx
0x180005453  mov     ecx, r15d
0x180005456  mov     eax, 8
0x18000545b  cmp     [r8+8], edx
0x18000545f  cmovz   ecx, eax
0x180005462  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005466  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, edx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000546e  inc     edx
0x180005470  mov     [rsp+14F0h+var_14C0], edx
0x180005474  mov     [rsp+14F0h+var_14B8], r15
0x180005479  call    cs:__imp_GetCurrentThreadId
0x18000547f  mov     [rsp+14F0h+var_14B0], eax
0x180005483  lea     rax, aWil; "wil"
0x18000548a  mov     [rsp+14F0h+var_1498], rax
0x18000548f  mov     [rsp+14F0h+var_1490], esi
0x180005493  mov     [rsp+14F0h+var_148C], ebx
0x180005497  mov     [rsp+14F0h+var_14A8], r15
0x18000549c  mov     [rsp+14F0h+var_14A0], r15
0x1800054a1  mov     [rbp+13F0h+var_1448], rdi
0x1800054a5  mov     [rbp+13F0h+var_1440], r14
0x1800054a9  mov     [rsp+14F0h+var_1488], r15
0x1800054ae  xorps   xmm0, xmm0
0x1800054b1  xor     eax, eax
0x1800054b3  movups  [rbp+13F0h+var_1468], xmm0
0x1800054b7  mov     [rbp+13F0h+var_1458], rax
0x1800054bb  xorps   xmm1, xmm1
0x1800054be  movups  [rsp+14F0h+var_1480], xmm1
0x1800054c3  mov     [rbp+13F0h+var_1470], rax
0x1800054c7  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800054ce  test    rax, rax
0x1800054d1  jz      short loc_1800054DF
0x1800054d3  call    cs:__guard_dispatch_icall_fptr
0x1800054d9  mov     [rbp+13F0h+var_1450], rax
0x1800054dd  jmp     short loc_1800054E3
0x1800054df  mov     [rbp+13F0h+var_1450], r15
0x1800054e3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800054ea  test    rax, rax
0x1800054ed  jz      short loc_1800054FA
0x1800054ef  lea     rcx, [rsp+14F0h+var_14D0]
0x1800054f4  call    cs:__guard_dispatch_icall_fptr
0x1800054fa  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005501  test    rax, rax
0x180005504  jz      short loc_18000551B
0x180005506  mov     r8d, 400h
0x18000550c  lea     rdx, [rbp+13F0h+var_1430]
0x180005510  lea     rcx, [rsp+14F0h+var_14D0]
0x180005515  call    cs:__guard_dispatch_icall_fptr
0x18000551b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005522  test    rax, rax
0x180005525  jz      short loc_180005532
0x180005527  lea     rcx, [rsp+14F0h+var_14D0]
0x18000552c  call    cs:__guard_dispatch_icall_fptr
0x180005532  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005539  test    rax, rax
0x18000553c  jz      short loc_180005550
0x18000553e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005543  jnz     short loc_180005550
0x180005545  lea     rcx, [rsp+14F0h+var_14D0]
0x18000554a  call    cs:__guard_dispatch_icall_fptr
0x180005550  cmp     [rsp+14F0h+var_14C8], r15d
0x180005555  jge     loc_180005670
0x18000555b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180005562  jnz     short loc_18000558D
0x180005564  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000556b  test    rax, rax
0x18000556e  jz      short loc_18000557C
0x180005570  call    cs:__guard_dispatch_icall_fptr
0x180005576  movzx   r15d, al
0x18000557a  jmp     short loc_180005588
0x18000557c  call    cs:__imp_IsDebuggerPresent
0x180005582  test    eax, eax
0x180005584  setnz   r15b
0x180005588  test    r15d, r15d
0x18000558b  jz      short loc_180005594
0x18000558d  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180005592  jz      short loc_1800055BB
0x180005594  mov     rax, cs:g_pfnResultLoggingCallback
0x18000559b  test    rax, rax
0x18000559e  jz      short loc_180005615
0x1800055a0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1800055a7  jnz     short loc_180005615
0x1800055a9  xor     r8d, r8d
0x1800055ac  xor     edx, edx
0x1800055ae  lea     rcx, [rsp+14F0h+var_14D0]
0x1800055b3  call    cs:__guard_dispatch_icall_fptr
0x1800055b9  jmp     short loc_180005615
0x1800055bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800055c2  test    rax, rax
0x1800055c5  jz      short loc_1800055E8
0x1800055c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x1800055ce  jnz     short loc_1800055E8
0x1800055d0  mov     r8d, 800h
0x1800055d6  lea     rdx, [rbp+13F0h+OutputString]
0x1800055dd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800055e2  call    cs:__guard_dispatch_icall_fptr
0x1800055e8  cmp     [rbp+13F0h+OutputString], 0
0x1800055f0  jnz     short loc_180005608
0x1800055f2  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800055f7  mov     edx, 800h; wchar_t *
0x1800055fc  lea     rcx, [rbp+13F0h+OutputString]; this
0x180005603  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180005608  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000560f  call    cs:__imp_OutputDebugStringW
0x180005615  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000561a  jnz     short loc_180005625
0x18000561c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x180005623  jz      short loc_180005638
0x180005625  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000562c  test    rax, rax
0x18000562f  jz      short loc_180005638
0x180005631  call    cs:__guard_dispatch_icall_fptr
0x180005637  nop
0x180005638  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000563d  jnz     short loc_180005665
0x18000563f  mov     rcx, [rbp+13F0h+var_30]
0x180005646  xor     rcx, rsp; StackCookie
0x180005649  call    __security_check_cookie
0x18000564e  mov     rbx, [rsp+14F0h+arg_10]
0x180005656  add     rsp, 14D0h
0x18000565d  pop     r15
0x18000565f  pop     r14
0x180005661  pop     rdi
0x180005662  pop     rsi
0x180005663  pop     rbp
0x180005664  retn
0x180005665  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000566a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005670  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
