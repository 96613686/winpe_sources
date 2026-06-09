# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180005fb0`
- end: `0x180006256`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005c30`

## callees

- `0x180002380`
- `0x1800032dc`
- `0x180005fb0`
- `0x180006e94`
- `0x180008060`
- `0x180008d08`
- `0x180008ec4`
- `0x1800227b0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006076`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006076`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800061f5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800061f5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000616b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000616b`

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
0x180005fb0  push    rbp
0x180005fb2  push    rbx
0x180005fb3  push    rsi
0x180005fb4  push    rdi
0x180005fb5  push    r12
0x180005fb7  push    r14
0x180005fb9  push    r15
0x180005fbb  lea     rbp, [rsp-13D0h]
0x180005fc3  mov     eax, 14D0h
0x180005fc8  call    _alloca_probe
0x180005fcd  sub     rsp, rax
0x180005fd0  mov     rax, cs:__security_cookie
0x180005fd7  xor     rax, rsp
0x180005fda  mov     [rbp+1400h+var_40], rax
0x180005fe1  mov     rsi, r8
0x180005fe4  mov     edi, edx
0x180005fe6  mov     rbx, rcx
0x180005fe9  mov     r14, [rbp+1400h+arg_28]
0x180005ff0  xor     edx, edx; Val
0x180005ff2  mov     r8d, 98h; Size
0x180005ff8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180005ffd  call    memset_0
0x180006002  nop
0x180006003  xor     r12d, r12d
0x180006006  mov     [rbp+1400h+OutputString], r12w
0x18000600e  mov     [rbp+1400h+var_1440], r12b
0x180006012  mov     rdx, [rbp+1400h+arg_30]; int
0x180006019  mov     ecx, [rdx]; this
0x18000601b  mov     [rsp+1500h+var_14D8], ecx
0x18000601f  mov     eax, [rdx+4]
0x180006022  mov     [rsp+1500h+var_14D4], eax
0x180006026  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000602b  mov     r15d, eax
0x18000602e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180006036  mov     ecx, r12d
0x180006039  lea     eax, [r12+8]
0x18000603e  cmp     dword ptr [rdx+8], 1
0x180006042  cmovz   ecx, eax
0x180006045  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180006049  lea     ecx, [rax-7]
0x18000604c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006054  inc     ecx
0x180006056  mov     [rsp+1500h+var_14D0], ecx
0x18000605a  mov     rcx, [rbp+1400h+arg_38]
0x180006061  test    rcx, rcx
0x180006064  jz      short loc_180006071
0x180006066  cmp     [rcx], r12w
0x18000606a  mov     [rsp+1500h+var_14C8], rcx
0x18000606f  jnz     short loc_180006076
0x180006071  mov     [rsp+1500h+var_14C8], r12
0x180006076  call    cs:__imp_GetCurrentThreadId
0x18000607c  mov     [rsp+1500h+var_14C0], eax
0x180006080  mov     [rsp+1500h+var_14A8], rsi
0x180006085  mov     [rsp+1500h+var_14A0], edi
0x180006089  mov     [rsp+1500h+var_149C], r15d
0x18000608e  mov     [rsp+1500h+var_14B8], r12
0x180006093  mov     [rsp+1500h+var_14B0], r12
0x180006098  mov     [rbp+1400h+var_1458], r14
0x18000609c  mov     [rbp+1400h+var_1450], rbx
0x1800060a0  mov     [rsp+1500h+var_1498], r12
0x1800060a5  xorps   xmm0, xmm0
0x1800060a8  xor     eax, eax
0x1800060aa  movups  [rbp+1400h+var_1478], xmm0
0x1800060ae  mov     [rbp+1400h+var_1468], rax
0x1800060b2  xorps   xmm1, xmm1
0x1800060b5  movups  [rsp+1500h+var_1490], xmm1
0x1800060ba  mov     [rbp+1400h+var_1480], rax
0x1800060be  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800060c5  test    rax, rax
0x1800060c8  jz      short loc_1800060D5
0x1800060ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060cf  mov     [rbp+1400h+var_1460], rax
0x1800060d3  jmp     short loc_1800060D9
0x1800060d5  mov     [rbp+1400h+var_1460], r12
0x1800060d9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800060e0  test    rax, rax
0x1800060e3  jz      short loc_1800060EF
0x1800060e5  lea     rcx, [rsp+1500h+var_14E0]
0x1800060ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060ef  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800060f6  test    rax, rax
0x1800060f9  jz      short loc_18000610F
0x1800060fb  mov     r8d, 400h
0x180006101  lea     rdx, [rbp+1400h+var_1440]
0x180006105  lea     rcx, [rsp+1500h+var_14E0]
0x18000610a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000610f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006116  test    rax, rax
0x180006119  jz      short loc_180006125
0x18000611b  lea     rcx, [rsp+1500h+var_14E0]
0x180006120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006125  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000612c  test    rax, rax
0x18000612f  jz      short loc_180006142
0x180006131  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006136  jnz     short loc_180006142
0x180006138  lea     rcx, [rsp+1500h+var_14E0]
0x18000613d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006142  cmp     [rsp+1500h+var_14D8], r12d
0x180006147  jge     loc_180006250
0x18000614d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180006154  jnz     short loc_180006175
0x180006156  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000615d  test    rax, rax
0x180006160  jz      short loc_18000616B
0x180006162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006167  test    al, al
0x180006169  jmp     short loc_180006173
0x18000616b  call    cs:__imp_IsDebuggerPresent
0x180006171  test    eax, eax
0x180006173  jz      short loc_18000617C
0x180006175  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000617a  jz      short loc_1800061A2
0x18000617c  mov     rax, cs:g_pfnResultLoggingCallback
0x180006183  test    rax, rax
0x180006186  jz      short loc_1800061FB
0x180006188  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000618f  jnz     short loc_1800061FB
0x180006191  xor     r8d, r8d
0x180006194  xor     edx, edx
0x180006196  lea     rcx, [rsp+1500h+var_14E0]
0x18000619b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061a0  jmp     short loc_1800061FB
0x1800061a2  mov     ebx, 800h
0x1800061a7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800061ae  test    rax, rax
0x1800061b1  jz      short loc_1800061D0
0x1800061b3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800061ba  jnz     short loc_1800061D0
0x1800061bc  mov     r8d, ebx
0x1800061bf  lea     rdx, [rbp+1400h+OutputString]
0x1800061c6  lea     rcx, [rsp+1500h+var_14E0]
0x1800061cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061d0  cmp     [rbp+1400h+OutputString], r12w
0x1800061d8  jnz     short loc_1800061EE
0x1800061da  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800061df  mov     rdx, rbx; unsigned __int16 *
0x1800061e2  lea     rcx, [rbp+1400h+OutputString]; this
0x1800061e9  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800061ee  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800061f5  call    cs:__imp_OutputDebugStringW
0x1800061fb  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180006200  jnz     short loc_18000620B
0x180006202  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180006209  jz      short loc_18000621D
0x18000620b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006212  test    rax, rax
0x180006215  jz      short loc_18000621D
0x180006217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000621c  nop
0x18000621d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180006222  jnz     short loc_180006245
0x180006224  mov     rcx, [rbp+1400h+var_40]
0x18000622b  xor     rcx, rsp; StackCookie
0x18000622e  call    __security_check_cookie
0x180006233  add     rsp, 14D0h
0x18000623a  pop     r15
0x18000623c  pop     r14
0x18000623e  pop     r12
0x180006240  pop     rdi
0x180006241  pop     rsi
0x180006242  pop     rbx
0x180006243  pop     rbp
0x180006244  retn
0x180006245  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000624a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180006250  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
