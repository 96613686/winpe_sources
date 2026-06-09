# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180023a94`
- end: `0x180023d4b`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `695`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800233d4`

## callees

- `0x180001f20`
- `0x180002938`
- `0x180023a94`
- `0x18002582c`
- `0x180026e58`
- `0x180028b1c`
- `0x180028cf0`
- `0x18005e040`
- `0x18005f010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180023c54`
- `KERNEL32!IsDebuggerPresent` at `0x180023c54`
- `KERNEL32!OutputDebugStringW` at `0x180023ce4`
- `KERNEL32!OutputDebugStringW` at `0x180023ce4`
- `KERNEL32!GetCurrentThreadId` at `0x180023b59`
- `KERNEL32!GetCurrentThreadId` at `0x180023b59`

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
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  int v14; // r15d
  int v15; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v17; // rdx
  wil::details::in1diag3 *v18; // rcx
  const struct wil::FailureInfo *v19; // r9
  bool v20; // zf
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD v27; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v11 = a7[1];
  v23 = *a7;
  v24 = v11;
  v12 = wil::details::RecordReturn((wil::details *)(unsigned int)v23);
  v20 = *(_DWORD *)(v13 + 8) == 1;
  v14 = v12;
  v21 = 1;
  v15 = 0;
  if ( v20 )
    v15 = 8;
  v22 = v15;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v26 = a8, !*a8) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v27 = CurrentThreadId;
  v31 = a2;
  v37 = 0;
  v35 = 0;
  v32 = v14;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v18);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v18);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v20 = !IsDebuggerPresent())
      : (v20 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v18) == 0),
        v20)
    || (v22 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v21, v19);
    OutputDebugStringW(OutputString);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v18);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v17);
}

```

## disassembly

```asm
0x180023a94  push    rbp
0x180023a96  push    rbx
0x180023a97  push    rsi
0x180023a98  push    rdi
0x180023a99  push    r12
0x180023a9b  push    r14
0x180023a9d  push    r15
0x180023a9f  lea     rbp, [rsp-13D0h]
0x180023aa7  mov     eax, 14D0h
0x180023aac  call    _alloca_probe
0x180023ab1  sub     rsp, rax
0x180023ab4  mov     rax, cs:__security_cookie
0x180023abb  xor     rax, rsp
0x180023abe  mov     [rbp+1400h+var_40], rax
0x180023ac5  mov     r14, [rbp+1400h+arg_28]
0x180023acc  mov     rsi, r8
0x180023acf  mov     edi, edx
0x180023ad1  mov     rbx, rcx
0x180023ad4  xor     edx, edx; Val
0x180023ad6  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180023adb  mov     r8d, 98h; Size
0x180023ae1  call    memset_0
0x180023ae6  mov     rdx, [rbp+1400h+arg_30]; int
0x180023aed  xor     r12d, r12d
0x180023af0  mov     [rbp+1400h+OutputString], r12w
0x180023af8  mov     [rbp+1400h+var_1440], r12b
0x180023afc  mov     ecx, [rdx]; this
0x180023afe  mov     eax, [rdx+4]
0x180023b01  mov     [rsp+1500h+var_14D8], ecx
0x180023b05  mov     [rsp+1500h+var_14D4], eax
0x180023b09  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180023b0e  cmp     dword ptr [rdx+8], 1
0x180023b12  mov     r15d, eax
0x180023b15  lea     eax, [r12+8]
0x180023b1a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180023b22  mov     ecx, r12d
0x180023b25  cmovz   ecx, eax
0x180023b28  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180023b2c  lea     ecx, [rax-7]
0x180023b2f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180023b37  inc     ecx
0x180023b39  mov     [rsp+1500h+var_14D0], ecx
0x180023b3d  mov     rcx, [rbp+1400h+arg_38]
0x180023b44  test    rcx, rcx
0x180023b47  jz      short loc_180023B54
0x180023b49  mov     [rsp+1500h+var_14C8], rcx
0x180023b4e  cmp     [rcx], r12w
0x180023b52  jnz     short loc_180023B59
0x180023b54  mov     [rsp+1500h+var_14C8], r12
0x180023b59  call    cs:__imp_GetCurrentThreadId
0x180023b60  nop     dword ptr [rax+rax+00h]
0x180023b65  xorps   xmm0, xmm0
0x180023b68  mov     [rsp+1500h+var_14A8], rsi
0x180023b6d  mov     [rsp+1500h+var_14C0], eax
0x180023b71  xorps   xmm1, xmm1
0x180023b74  xor     eax, eax
0x180023b76  mov     [rsp+1500h+var_14A0], edi
0x180023b7a  mov     [rbp+1400h+var_1468], rax
0x180023b7e  mov     [rbp+1400h+var_1480], rax
0x180023b82  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180023b89  mov     [rsp+1500h+var_149C], r15d
0x180023b8e  mov     [rsp+1500h+var_14B8], r12
0x180023b93  mov     [rsp+1500h+var_14B0], r12
0x180023b98  mov     [rbp+1400h+var_1458], r14
0x180023b9c  mov     [rbp+1400h+var_1450], rbx
0x180023ba0  mov     [rsp+1500h+var_1498], r12
0x180023ba5  movups  [rbp+1400h+var_1478], xmm0
0x180023ba9  movups  [rsp+1500h+var_1490], xmm1
0x180023bae  test    rax, rax
0x180023bb1  jz      short loc_180023BBE
0x180023bb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bb8  mov     [rbp+1400h+var_1460], rax
0x180023bbc  jmp     short loc_180023BC2
0x180023bbe  mov     [rbp+1400h+var_1460], r12
0x180023bc2  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180023bc9  test    rax, rax
0x180023bcc  jz      short loc_180023BD8
0x180023bce  lea     rcx, [rsp+1500h+var_14E0]
0x180023bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bd8  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180023bdf  test    rax, rax
0x180023be2  jz      short loc_180023BF8
0x180023be4  mov     r8d, 400h
0x180023bea  lea     rdx, [rbp+1400h+var_1440]
0x180023bee  lea     rcx, [rsp+1500h+var_14E0]
0x180023bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023bf8  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180023bff  test    rax, rax
0x180023c02  jz      short loc_180023C0E
0x180023c04  lea     rcx, [rsp+1500h+var_14E0]
0x180023c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c0e  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180023c15  test    rax, rax
0x180023c18  jz      short loc_180023C2B
0x180023c1a  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180023c1f  jnz     short loc_180023C2B
0x180023c21  lea     rcx, [rsp+1500h+var_14E0]
0x180023c26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c2b  cmp     [rsp+1500h+var_14D8], r12d
0x180023c30  jge     loc_180023D3A
0x180023c36  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180023c3d  jnz     short loc_180023C64
0x180023c3f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180023c46  test    rax, rax
0x180023c49  jz      short loc_180023C54
0x180023c4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c50  test    al, al
0x180023c52  jmp     short loc_180023C62
0x180023c54  call    cs:__imp_IsDebuggerPresent
0x180023c5b  nop     dword ptr [rax+rax+00h]
0x180023c60  test    eax, eax
0x180023c62  jz      short loc_180023C6B
0x180023c64  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180023c69  jz      short loc_180023C91
0x180023c6b  mov     rax, cs:g_pfnResultLoggingCallback
0x180023c72  test    rax, rax
0x180023c75  jz      short loc_180023CF0
0x180023c77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180023c7e  jnz     short loc_180023CF0
0x180023c80  xor     r8d, r8d
0x180023c83  lea     rcx, [rsp+1500h+var_14E0]
0x180023c88  xor     edx, edx
0x180023c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c8f  jmp     short loc_180023CF0
0x180023c91  mov     rax, cs:g_pfnResultLoggingCallback
0x180023c98  mov     ebx, 800h
0x180023c9d  test    rax, rax
0x180023ca0  jz      short loc_180023CBF
0x180023ca2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180023ca9  jnz     short loc_180023CBF
0x180023cab  mov     r8d, ebx
0x180023cae  lea     rdx, [rbp+1400h+OutputString]
0x180023cb5  lea     rcx, [rsp+1500h+var_14E0]
0x180023cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023cbf  cmp     [rbp+1400h+OutputString], r12w
0x180023cc7  jnz     short loc_180023CDD
0x180023cc9  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180023cce  mov     rdx, rbx; unsigned __int16 *
0x180023cd1  lea     rcx, [rbp+1400h+OutputString]; this
0x180023cd8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180023cdd  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180023ce4  call    cs:__imp_OutputDebugStringW
0x180023ceb  nop     dword ptr [rax+rax+00h]
0x180023cf0  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180023cf5  jnz     short loc_180023D00
0x180023cf7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180023cfe  jz      short loc_180023D11
0x180023d00  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180023d07  test    rax, rax
0x180023d0a  jz      short loc_180023D11
0x180023d0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023d11  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180023d16  jnz     short loc_180023D40
0x180023d18  mov     rcx, [rbp+1400h+var_40]
0x180023d1f  xor     rcx, rsp; StackCookie
0x180023d22  call    __security_check_cookie
0x180023d27  add     rsp, 14D0h
0x180023d2e  pop     r15
0x180023d30  pop     r14
0x180023d32  pop     r12
0x180023d34  pop     rdi
0x180023d35  pop     rsi
0x180023d36  pop     rbx
0x180023d37  pop     rbp
0x180023d38  retn
0x180023d3a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180023d40  lea     rcx, [rsp+1500h+var_14E0]; this
0x180023d45  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
