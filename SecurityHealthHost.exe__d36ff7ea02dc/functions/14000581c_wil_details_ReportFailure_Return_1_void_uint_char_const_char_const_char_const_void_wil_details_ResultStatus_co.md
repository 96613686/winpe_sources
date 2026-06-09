# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x14000581c`
- end: `0x140005aa9`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000570c`

## callees

- `0x1400015f0`
- `0x1400022ec`
- `0x14000581c`
- `0x140005d20`
- `0x140006730`
- `0x140006810`
- `0x1400068ec`
- `0x14000fa20`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400058ca`
- `KERNEL32!GetCurrentThreadId` at `0x1400058ca`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005a48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005a48`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400059be`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400059be`

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
0x14000581c  push    rbp
0x14000581e  push    rbx
0x14000581f  push    rsi
0x140005820  push    rdi
0x140005821  push    r12
0x140005823  push    r14
0x140005825  push    r15
0x140005827  lea     rbp, [rsp-13D0h]
0x14000582f  mov     eax, 14D0h
0x140005834  call    _alloca_probe
0x140005839  sub     rsp, rax
0x14000583c  mov     rax, cs:__security_cookie
0x140005843  xor     rax, rsp
0x140005846  mov     [rbp+1400h+var_40], rax
0x14000584d  mov     r14, r8
0x140005850  mov     esi, edx
0x140005852  mov     r15, rcx
0x140005855  mov     rdi, [rbp+1400h+arg_28]
0x14000585c  xor     edx, edx; Val
0x14000585e  mov     r8d, 98h; Size
0x140005864  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140005869  call    memset_0
0x14000586e  nop
0x14000586f  xor     r12d, r12d
0x140005872  mov     [rbp+1400h+OutputString], r12w
0x14000587a  mov     [rbp+1400h+var_1440], r12b
0x14000587e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x140005885  mov     ecx, [rdx]; this
0x140005887  mov     [rsp+1500h+var_14D8], ecx
0x14000588b  mov     eax, [rdx+4]
0x14000588e  mov     [rsp+1500h+var_14D4], eax
0x140005892  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140005897  mov     ebx, eax
0x140005899  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1400058a1  mov     ecx, r12d
0x1400058a4  lea     eax, [r12+8]
0x1400058a9  cmp     dword ptr [rdx+8], 1
0x1400058ad  cmovz   ecx, eax
0x1400058b0  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1400058b4  lea     ecx, [rax-7]
0x1400058b7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400058bf  inc     ecx
0x1400058c1  mov     [rsp+1500h+var_14D0], ecx
0x1400058c5  mov     [rsp+1500h+var_14C8], r12
0x1400058ca  call    cs:__imp_GetCurrentThreadId
0x1400058d0  mov     [rsp+1500h+var_14C0], eax
0x1400058d4  mov     [rsp+1500h+var_14A8], r14
0x1400058d9  mov     [rsp+1500h+var_14A0], esi
0x1400058dd  mov     [rsp+1500h+var_149C], ebx
0x1400058e1  mov     [rsp+1500h+var_14B8], r12
0x1400058e6  mov     [rsp+1500h+var_14B0], r12
0x1400058eb  mov     [rbp+1400h+var_1458], rdi
0x1400058ef  mov     [rbp+1400h+var_1450], r15
0x1400058f3  mov     [rsp+1500h+var_1498], r12
0x1400058f8  xorps   xmm0, xmm0
0x1400058fb  xor     eax, eax
0x1400058fd  movups  [rbp+1400h+var_1478], xmm0
0x140005901  mov     [rbp+1400h+var_1468], rax
0x140005905  xorps   xmm1, xmm1
0x140005908  movups  [rsp+1500h+var_1490], xmm1
0x14000590d  mov     [rbp+1400h+var_1480], rax
0x140005911  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005918  test    rax, rax
0x14000591b  jz      short loc_140005928
0x14000591d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005922  mov     [rbp+1400h+var_1460], rax
0x140005926  jmp     short loc_14000592C
0x140005928  mov     [rbp+1400h+var_1460], r12
0x14000592c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140005933  test    rax, rax
0x140005936  jz      short loc_140005942
0x140005938  lea     rcx, [rsp+1500h+var_14E0]
0x14000593d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005942  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140005949  test    rax, rax
0x14000594c  jz      short loc_140005962
0x14000594e  mov     r8d, 400h
0x140005954  lea     rdx, [rbp+1400h+var_1440]
0x140005958  lea     rcx, [rsp+1500h+var_14E0]
0x14000595d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005962  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005969  test    rax, rax
0x14000596c  jz      short loc_140005978
0x14000596e  lea     rcx, [rsp+1500h+var_14E0]
0x140005973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005978  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000597f  test    rax, rax
0x140005982  jz      short loc_140005995
0x140005984  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140005989  jnz     short loc_140005995
0x14000598b  lea     rcx, [rsp+1500h+var_14E0]
0x140005990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005995  cmp     [rsp+1500h+var_14D8], r12d
0x14000599a  jge     loc_140005AA3
0x1400059a0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400059a7  jnz     short loc_1400059C8
0x1400059a9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400059b0  test    rax, rax
0x1400059b3  jz      short loc_1400059BE
0x1400059b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059ba  test    al, al
0x1400059bc  jmp     short loc_1400059C6
0x1400059be  call    cs:__imp_IsDebuggerPresent
0x1400059c4  test    eax, eax
0x1400059c6  jz      short loc_1400059CF
0x1400059c8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400059cd  jz      short loc_1400059F5
0x1400059cf  mov     rax, cs:g_pfnResultLoggingCallback
0x1400059d6  test    rax, rax
0x1400059d9  jz      short loc_140005A4E
0x1400059db  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400059e2  jnz     short loc_140005A4E
0x1400059e4  xor     r8d, r8d
0x1400059e7  xor     edx, edx
0x1400059e9  lea     rcx, [rsp+1500h+var_14E0]
0x1400059ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059f3  jmp     short loc_140005A4E
0x1400059f5  mov     ebx, 800h
0x1400059fa  mov     rax, cs:g_pfnResultLoggingCallback
0x140005a01  test    rax, rax
0x140005a04  jz      short loc_140005A23
0x140005a06  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140005a0d  jnz     short loc_140005A23
0x140005a0f  mov     r8d, ebx
0x140005a12  lea     rdx, [rbp+1400h+OutputString]
0x140005a19  lea     rcx, [rsp+1500h+var_14E0]
0x140005a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a23  cmp     [rbp+1400h+OutputString], r12w
0x140005a2b  jnz     short loc_140005A41
0x140005a2d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140005a32  mov     rdx, rbx; unsigned __int16 *
0x140005a35  lea     rcx, [rbp+1400h+OutputString]; this
0x140005a3c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140005a41  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140005a48  call    cs:__imp_OutputDebugStringW
0x140005a4e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140005a53  jnz     short loc_140005A5E
0x140005a55  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140005a5c  jz      short loc_140005A70
0x140005a5e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140005a65  test    rax, rax
0x140005a68  jz      short loc_140005A70
0x140005a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a6f  nop
0x140005a70  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140005a75  jnz     short loc_140005A98
0x140005a77  mov     rcx, [rbp+1400h+var_40]
0x140005a7e  xor     rcx, rsp; StackCookie
0x140005a81  call    __security_check_cookie
0x140005a86  add     rsp, 14D0h
0x140005a8d  pop     r15
0x140005a8f  pop     r14
0x140005a91  pop     r12
0x140005a93  pop     rdi
0x140005a94  pop     rsi
0x140005a95  pop     rbx
0x140005a96  pop     rbp
0x140005a97  retn
0x140005a98  lea     rcx, [rsp+1500h+var_14E0]; this
0x140005a9d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140005aa3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
