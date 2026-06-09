# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000fde8`
- end: `0x180010073`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000faa4`

## callees

- `0x18000eb70`
- `0x18000f4dc`
- `0x18000fde8`
- `0x180011174`
- `0x180012be8`
- `0x180014018`
- `0x1800141d0`
- `0x180028390`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe95`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010013`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010013`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000ff89`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000ff89`

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
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x18000fde8  push    rbp
0x18000fdea  push    rbx
0x18000fdeb  push    rsi
0x18000fdec  push    rdi
0x18000fded  push    r12
0x18000fdef  push    r14
0x18000fdf1  push    r15
0x18000fdf3  lea     rbp, [rsp-13D0h]
0x18000fdfb  mov     eax, 14D0h
0x18000fe00  call    _alloca_probe
0x18000fe05  sub     rsp, rax
0x18000fe08  mov     rax, cs:__security_cookie
0x18000fe0f  xor     rax, rsp
0x18000fe12  mov     [rbp+1400h+var_40], rax
0x18000fe19  mov     rdi, [rbp+1400h+arg_28]
0x18000fe20  mov     r14, r8
0x18000fe23  mov     esi, edx
0x18000fe25  mov     r15, rcx
0x18000fe28  xor     edx, edx; Val
0x18000fe2a  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000fe2f  mov     r8d, 98h; Size
0x18000fe35  call    memset_0
0x18000fe3a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000fe41  xor     r12d, r12d
0x18000fe44  mov     [rbp+1400h+OutputString], r12w
0x18000fe4c  mov     [rbp+1400h+var_1440], r12b
0x18000fe50  mov     ecx, [rdx]; this
0x18000fe52  mov     eax, [rdx+4]
0x18000fe55  mov     [rsp+1500h+var_14D8], ecx
0x18000fe59  mov     [rsp+1500h+var_14D4], eax
0x18000fe5d  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000fe62  cmp     dword ptr [rdx+8], 1
0x18000fe66  mov     ebx, eax
0x18000fe68  lea     eax, [r12+8]
0x18000fe6d  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000fe75  mov     ecx, r12d
0x18000fe78  cmovz   ecx, eax
0x18000fe7b  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000fe7f  lea     ecx, [rax-7]
0x18000fe82  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000fe8a  inc     ecx
0x18000fe8c  mov     [rsp+1500h+var_14C8], r12
0x18000fe91  mov     [rsp+1500h+var_14D0], ecx
0x18000fe95  call    cs:__imp_GetCurrentThreadId
0x18000fe9b  xorps   xmm0, xmm0
0x18000fe9e  mov     [rsp+1500h+var_14A8], r14
0x18000fea3  mov     [rsp+1500h+var_14C0], eax
0x18000fea7  xorps   xmm1, xmm1
0x18000feaa  xor     eax, eax
0x18000feac  mov     [rsp+1500h+var_14A0], esi
0x18000feb0  mov     [rbp+1400h+var_1468], rax
0x18000feb4  mov     [rbp+1400h+var_1480], rax
0x18000feb8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000febf  mov     [rsp+1500h+var_149C], ebx
0x18000fec3  mov     [rsp+1500h+var_14B8], r12
0x18000fec8  mov     [rsp+1500h+var_14B0], r12
0x18000fecd  mov     [rbp+1400h+var_1458], rdi
0x18000fed1  mov     [rbp+1400h+var_1450], r15
0x18000fed5  mov     [rsp+1500h+var_1498], r12
0x18000feda  movups  [rbp+1400h+var_1478], xmm0
0x18000fede  movups  [rsp+1500h+var_1490], xmm1
0x18000fee3  test    rax, rax
0x18000fee6  jz      short loc_18000FEF3
0x18000fee8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000feed  mov     [rbp+1400h+var_1460], rax
0x18000fef1  jmp     short loc_18000FEF7
0x18000fef3  mov     [rbp+1400h+var_1460], r12
0x18000fef7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000fefe  test    rax, rax
0x18000ff01  jz      short loc_18000FF0D
0x18000ff03  lea     rcx, [rsp+1500h+var_14E0]
0x18000ff08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff0d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000ff14  test    rax, rax
0x18000ff17  jz      short loc_18000FF2D
0x18000ff19  mov     r8d, 400h
0x18000ff1f  lea     rdx, [rbp+1400h+var_1440]
0x18000ff23  lea     rcx, [rsp+1500h+var_14E0]
0x18000ff28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff2d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ff34  test    rax, rax
0x18000ff37  jz      short loc_18000FF43
0x18000ff39  lea     rcx, [rsp+1500h+var_14E0]
0x18000ff3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff43  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ff4a  test    rax, rax
0x18000ff4d  jz      short loc_18000FF60
0x18000ff4f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000ff54  jnz     short loc_18000FF60
0x18000ff56  lea     rcx, [rsp+1500h+var_14E0]
0x18000ff5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff60  cmp     [rsp+1500h+var_14D8], r12d
0x18000ff65  jge     loc_180010062
0x18000ff6b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000ff72  jnz     short loc_18000FF93
0x18000ff74  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000ff7b  test    rax, rax
0x18000ff7e  jz      short loc_18000FF89
0x18000ff80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff85  test    al, al
0x18000ff87  jmp     short loc_18000FF91
0x18000ff89  call    cs:__imp_IsDebuggerPresent
0x18000ff8f  test    eax, eax
0x18000ff91  jz      short loc_18000FF9A
0x18000ff93  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000ff98  jz      short loc_18000FFC0
0x18000ff9a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ffa1  test    rax, rax
0x18000ffa4  jz      short loc_180010019
0x18000ffa6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000ffad  jnz     short loc_180010019
0x18000ffaf  xor     r8d, r8d
0x18000ffb2  lea     rcx, [rsp+1500h+var_14E0]
0x18000ffb7  xor     edx, edx
0x18000ffb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffbe  jmp     short loc_180010019
0x18000ffc0  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ffc7  mov     ebx, 800h
0x18000ffcc  test    rax, rax
0x18000ffcf  jz      short loc_18000FFEE
0x18000ffd1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000ffd8  jnz     short loc_18000FFEE
0x18000ffda  mov     r8d, ebx
0x18000ffdd  lea     rdx, [rbp+1400h+OutputString]
0x18000ffe4  lea     rcx, [rsp+1500h+var_14E0]
0x18000ffe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffee  cmp     [rbp+1400h+OutputString], r12w
0x18000fff6  jnz     short loc_18001000C
0x18000fff8  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000fffd  mov     rdx, rbx; unsigned __int16 *
0x180010000  lea     rcx, [rbp+1400h+OutputString]; pszDest
0x180010007  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001000c  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180010013  call    cs:__imp_OutputDebugStringW
0x180010019  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18001001e  jnz     short loc_180010029
0x180010020  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180010027  jz      short loc_18001003A
0x180010029  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180010030  test    rax, rax
0x180010033  jz      short loc_18001003A
0x180010035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001003a  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18001003f  jnz     short loc_180010068
0x180010041  mov     rcx, [rbp+1400h+var_40]
0x180010048  xor     rcx, rsp; StackCookie
0x18001004b  call    __security_check_cookie
0x180010050  add     rsp, 14D0h
0x180010057  pop     r15
0x180010059  pop     r14
0x18001005b  pop     r12
0x18001005d  pop     rdi
0x18001005e  pop     rsi
0x18001005f  pop     rbx
0x180010060  pop     rbp
0x180010061  retn
0x180010062  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180010068  lea     rcx, [rsp+1500h+var_14E0]; this
0x18001006d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
