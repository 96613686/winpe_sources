# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180043330`
- end: `0x1800435cb`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `667`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800430f0`

## callees

- `0x180016000`
- `0x1800161b0`
- `0x180016290`
- `0x1800168c0`
- `0x180043330`
- `0x18004c070`
- `0x1800514d0`
- `0x18005e260`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180043569`
- `KERNEL32!OutputDebugStringW` at `0x180043569`
- `KERNEL32!GetCurrentThreadId` at `0x1800433de`
- `KERNEL32!GetCurrentThreadId` at `0x1800433de`
- `KERNEL32!IsDebuggerPresent` at `0x1800434d8`
- `KERNEL32!IsDebuggerPresent` at `0x1800434d8`

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
  int IsDebuggerPresent; // ebx
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // r8
  bool v15; // zf
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  _WORD *v24; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  __int64 v28; // [rsp+58h] [rbp-A8h]
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

  IsDebuggerPresent = 0;
  OutputString[0] = 0;
  v39[0] = 0;
  v21 = *a7;
  v22 = a7[1];
  v12 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, a2);
  v19 = 1;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v20 = v13;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v15 = *a8 == 0, v24 = a8, v15) )
    v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v28 = a3;
  v29 = a2;
  v30 = v12;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17)),
         IsDebuggerPresent))
    && (v20 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (wchar_t *)0x800, (unsigned __int64)&v19, v18);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v16);
}

```

## disassembly

```asm
0x180043330  push    rbp
0x180043332  push    rbx
0x180043333  push    rsi
0x180043334  push    rdi
0x180043335  push    r12
0x180043337  push    r14
0x180043339  push    r15
0x18004333b  lea     rbp, [rsp-13D0h]
0x180043343  mov     eax, 14D0h
0x180043348  call    _alloca_probe
0x18004334d  sub     rsp, rax
0x180043350  mov     rax, cs:__security_cookie
0x180043357  xor     rax, rsp
0x18004335a  mov     [rbp+1400h+var_40], rax
0x180043361  mov     r14, r8
0x180043364  mov     esi, edx
0x180043366  mov     rdi, rcx
0x180043369  mov     r15, [rbp+1400h+arg_28]
0x180043370  xor     ebx, ebx
0x180043372  mov     [rbp+1400h+OutputString], bx
0x180043379  mov     [rbp+1400h+var_1440], bl
0x18004337c  mov     r8, [rbp+1400h+arg_30]
0x180043383  mov     ecx, [r8]; this
0x180043386  mov     [rsp+1500h+var_14D8], ecx
0x18004338a  mov     eax, [r8+4]
0x18004338e  mov     [rsp+1500h+var_14D4], eax
0x180043392  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180043397  mov     r12d, eax
0x18004339a  mov     edx, 1
0x18004339f  mov     dword ptr [rsp+1500h+var_14E0], edx
0x1800433a3  mov     ecx, ebx
0x1800433a5  mov     eax, 8
0x1800433aa  cmp     [r8+8], edx
0x1800433ae  cmovz   ecx, eax
0x1800433b1  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800433b5  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, edx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800433bd  inc     edx
0x1800433bf  mov     [rsp+1500h+var_14D0], edx
0x1800433c3  mov     rcx, [rbp+1400h+arg_38]
0x1800433ca  test    rcx, rcx
0x1800433cd  jz      short loc_1800433D9
0x1800433cf  cmp     [rcx], bx
0x1800433d2  mov     [rsp+1500h+var_14C8], rcx
0x1800433d7  jnz     short loc_1800433DE
0x1800433d9  mov     [rsp+1500h+var_14C8], rbx
0x1800433de  call    cs:__imp_GetCurrentThreadId
0x1800433e4  mov     [rsp+1500h+var_14C0], eax
0x1800433e8  mov     [rsp+1500h+var_14A8], r14
0x1800433ed  mov     [rsp+1500h+var_14A0], esi
0x1800433f1  mov     [rsp+1500h+var_149C], r12d
0x1800433f6  mov     [rsp+1500h+var_14B8], rbx
0x1800433fb  mov     [rsp+1500h+var_14B0], rbx
0x180043400  mov     [rbp+1400h+var_1458], r15
0x180043404  mov     [rbp+1400h+var_1450], rdi
0x180043408  mov     [rsp+1500h+var_1498], rbx
0x18004340d  xorps   xmm0, xmm0
0x180043410  xor     eax, eax
0x180043412  movups  [rbp+1400h+var_1478], xmm0
0x180043416  mov     [rbp+1400h+var_1468], rax
0x18004341a  xorps   xmm1, xmm1
0x18004341d  movups  [rsp+1500h+var_1490], xmm1
0x180043422  mov     [rbp+1400h+var_1480], rax
0x180043426  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18004342d  test    rax, rax
0x180043430  jz      short loc_18004343E
0x180043432  call    cs:__guard_dispatch_icall_fptr
0x180043438  mov     [rbp+1400h+var_1460], rax
0x18004343c  jmp     short loc_180043442
0x18004343e  mov     [rbp+1400h+var_1460], rbx
0x180043442  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180043449  test    rax, rax
0x18004344c  jz      short loc_180043459
0x18004344e  lea     rcx, [rsp+1500h+var_14E0]
0x180043453  call    cs:__guard_dispatch_icall_fptr
0x180043459  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180043460  test    rax, rax
0x180043463  jz      short loc_18004347A
0x180043465  mov     r8d, 400h
0x18004346b  lea     rdx, [rbp+1400h+var_1440]
0x18004346f  lea     rcx, [rsp+1500h+var_14E0]
0x180043474  call    cs:__guard_dispatch_icall_fptr
0x18004347a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180043481  test    rax, rax
0x180043484  jz      short loc_180043491
0x180043486  lea     rcx, [rsp+1500h+var_14E0]
0x18004348b  call    cs:__guard_dispatch_icall_fptr
0x180043491  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180043498  test    rax, rax
0x18004349b  jz      short loc_1800434AF
0x18004349d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800434a2  jnz     short loc_1800434AF
0x1800434a4  lea     rcx, [rsp+1500h+var_14E0]
0x1800434a9  call    cs:__guard_dispatch_icall_fptr
0x1800434af  cmp     [rsp+1500h+var_14D8], ebx
0x1800434b3  jge     loc_1800435C5
0x1800434b9  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, bl; bool wil::g_fIsDebuggerPresent
0x1800434bf  jnz     short loc_1800434E7
0x1800434c1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800434c8  test    rax, rax
0x1800434cb  jz      short loc_1800434D8
0x1800434cd  call    cs:__guard_dispatch_icall_fptr
0x1800434d3  movzx   ebx, al
0x1800434d6  jmp     short loc_1800434E3
0x1800434d8  call    cs:__imp_IsDebuggerPresent
0x1800434de  test    eax, eax
0x1800434e0  setnz   bl
0x1800434e3  test    ebx, ebx
0x1800434e5  jz      short loc_1800434EE
0x1800434e7  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800434ec  jz      short loc_180043515
0x1800434ee  mov     rax, cs:g_pfnResultLoggingCallback
0x1800434f5  test    rax, rax
0x1800434f8  jz      short loc_18004356F
0x1800434fa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180043501  jnz     short loc_18004356F
0x180043503  xor     r8d, r8d
0x180043506  xor     edx, edx
0x180043508  lea     rcx, [rsp+1500h+var_14E0]
0x18004350d  call    cs:__guard_dispatch_icall_fptr
0x180043513  jmp     short loc_18004356F
0x180043515  mov     rax, cs:g_pfnResultLoggingCallback
0x18004351c  test    rax, rax
0x18004351f  jz      short loc_180043542
0x180043521  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180043528  jnz     short loc_180043542
0x18004352a  mov     r8d, 800h
0x180043530  lea     rdx, [rbp+1400h+OutputString]
0x180043537  lea     rcx, [rsp+1500h+var_14E0]
0x18004353c  call    cs:__guard_dispatch_icall_fptr
0x180043542  cmp     [rbp+1400h+OutputString], 0
0x18004354a  jnz     short loc_180043562
0x18004354c  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180043551  mov     edx, 800h; wchar_t *
0x180043556  lea     rcx, [rbp+1400h+OutputString]; Buffer
0x18004355d  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180043562  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180043569  call    cs:__imp_OutputDebugStringW
0x18004356f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180043574  jnz     short loc_18004357F
0x180043576  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x18004357d  jz      short loc_180043592
0x18004357f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180043586  test    rax, rax
0x180043589  jz      short loc_180043592
0x18004358b  call    cs:__guard_dispatch_icall_fptr
0x180043591  nop
0x180043592  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180043597  jnz     short loc_1800435BA
0x180043599  mov     rcx, [rbp+1400h+var_40]
0x1800435a0  xor     rcx, rsp; StackCookie
0x1800435a3  call    __security_check_cookie
0x1800435a8  add     rsp, 14D0h
0x1800435af  pop     r15
0x1800435b1  pop     r14
0x1800435b3  pop     r12
0x1800435b5  pop     rdi
0x1800435b6  pop     rsi
0x1800435b7  pop     rbx
0x1800435b8  pop     rbp
0x1800435b9  retn
0x1800435ba  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800435bf  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800435c5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
