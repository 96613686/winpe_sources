# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000673c`
- end: `0x180006a35`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180004e4c`
- `0x180005190`

## callees

- `0x180004d8c`
- `0x180005d94`
- `0x180006578`
- `0x18000673c`
- `0x180006d68`
- `0x180006d90`
- `0x180006da4`
- `0x180006dc0`
- `0x180007a94`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000685f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000685f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000697e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000697e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800069f0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800069f0`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int *a8,
        _WORD *a9,
        __int64 a10,
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v19 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v19 = v20;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v19;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v24);
  else
    ModuleName = 0;
  *(_QWORD *)(a16 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a16, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a16);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
        v27)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x18000673c  mov     [rsp+arg_10], rbx
0x180006741  mov     [rsp+arg_8], edx
0x180006745  mov     [rsp+arg_0], rcx
0x18000674a  push    rbp
0x18000674b  push    rsi
0x18000674c  push    rdi
0x18000674d  push    r12
0x18000674f  push    r13
0x180006751  push    r14
0x180006753  push    r15
0x180006755  sub     rsp, 40h
0x180006759  mov     r12, r9
0x18000675c  mov     r13, r8
0x18000675f  mov     r10, rcx
0x180006762  xor     eax, eax
0x180006764  mov     rsi, [rsp+78h+lpOutputString]
0x18000676c  mov     [rsi], ax
0x18000676f  mov     rax, [rsp+78h+arg_60]
0x180006777  mov     byte ptr [rax], 0
0x18000677a  mov     r14, [rsp+78h+arg_38]
0x180006782  mov     edi, [r14]
0x180006785  mov     rbx, [rsp+78h+arg_78]
0x18000678d  mov     [rbx+8], edi
0x180006790  mov     eax, [r14+4]
0x180006794  mov     [rbx+0Ch], eax
0x180006797  xor     ebp, ebp
0x180006799  mov     r15d, [rsp+78h+arg_30]
0x1800067a1  mov     ecx, r15d
0x1800067a4  test    r15d, r15d
0x1800067a7  jz      short loc_18000680F
0x1800067a9  sub     ecx, 1
0x1800067ac  jz      short loc_180006806
0x1800067ae  sub     ecx, 1
0x1800067b1  jz      short loc_1800067C1
0x1800067b3  cmp     ecx, 1
0x1800067b6  jnz     short loc_180006818
0x1800067b8  mov     ecx, edi; this
0x1800067ba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800067bf  jmp     short loc_180006816
0x1800067c1  test    edi, edi
0x1800067c3  js      short loc_1800067FD
0x1800067c5  mov     edi, 8007029Ch
0x1800067ca  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800067ce  mov     rax, [rsp+78h+arg_28]
0x1800067d6  mov     [rsp+78h+var_50], rax; __int64
0x1800067db  mov     rax, [rsp+78h+arg_20]
0x1800067e3  mov     [rsp+78h+var_58], rax; __int64
0x1800067e8  mov     rcx, r10; int
0x1800067eb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800067f0  mov     [rbx+8], edi
0x1800067f3  mov     ecx, edi; this
0x1800067f5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800067fa  mov     [rbx+0Ch], eax
0x1800067fd  mov     ecx, edi; this
0x1800067ff  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006804  jmp     short loc_180006816
0x180006806  mov     ecx, edi; this
0x180006808  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000680d  jmp     short loc_180006816
0x18000680f  mov     ecx, edi; this
0x180006811  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006816  mov     ebp, eax
0x180006818  mov     [rbx], r15d
0x18000681b  mov     eax, [rsp+78h+arg_70]
0x180006822  mov     [rbx+4], eax
0x180006825  cmp     dword ptr [r14+8], 1
0x18000682a  jnz     short loc_180006832
0x18000682c  or      eax, 8
0x18000682f  mov     [rbx+4], eax
0x180006832  mov     eax, 1
0x180006837  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000683f  inc     eax
0x180006841  mov     [rbx+10h], eax
0x180006844  mov     rax, [rsp+78h+arg_40]
0x18000684c  xor     edi, edi
0x18000684e  test    rax, rax
0x180006851  jz      short loc_180006858
0x180006853  cmp     [rax], di
0x180006856  jnz     short loc_18000685B
0x180006858  mov     rax, rdi
0x18000685b  mov     [rbx+18h], rax
0x18000685f  call    cs:__imp_GetCurrentThreadId
0x180006865  mov     [rbx+20h], eax
0x180006868  mov     [rbx+38h], r13
0x18000686c  mov     eax, [rsp+78h+arg_8]
0x180006873  mov     [rbx+40h], eax
0x180006876  mov     [rbx+44h], ebp
0x180006879  mov     rax, [rsp+78h+arg_20]
0x180006881  mov     [rbx+28h], rax
0x180006885  mov     [rbx+30h], r12
0x180006889  mov     rax, [rsp+78h+arg_28]
0x180006891  mov     [rbx+88h], rax
0x180006898  mov     rax, [rsp+78h+arg_0]
0x1800068a0  mov     [rbx+90h], rax
0x1800068a7  mov     [rbx+48h], rdi
0x1800068ab  xorps   xmm0, xmm0
0x1800068ae  xor     eax, eax
0x1800068b0  movups  xmmword ptr [rbx+68h], xmm0
0x1800068b4  mov     [rbx+78h], rax
0x1800068b8  movups  xmmword ptr [rbx+50h], xmm0
0x1800068bc  mov     [rbx+60h], rax
0x1800068c0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800068c7  test    rax, rax
0x1800068ca  jz      short loc_1800068D3
0x1800068cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068d1  jmp     short loc_1800068D6
0x1800068d3  mov     rax, rdi
0x1800068d6  mov     [rbx+80h], rax
0x1800068dd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800068e4  test    rax, rax
0x1800068e7  jz      short loc_1800068F1
0x1800068e9  mov     rcx, rbx
0x1800068ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068f1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800068f8  test    rax, rax
0x1800068fb  jz      short loc_180006913
0x1800068fd  mov     r8d, 400h
0x180006903  mov     rdx, [rsp+78h+arg_60]
0x18000690b  mov     rcx, rbx
0x18000690e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006913  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000691a  test    rax, rax
0x18000691d  jz      short loc_180006927
0x18000691f  mov     rcx, rbx
0x180006922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006927  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000692e  test    rax, rax
0x180006931  jz      short loc_180006941
0x180006933  test    byte ptr [rbx+4], 2
0x180006937  jnz     short loc_180006941
0x180006939  mov     rcx, rbx
0x18000693c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006941  cmp     [rbx+8], edi
0x180006944  jl      short loc_180006960
0x180006946  cmp     r15d, 3
0x18000694a  jnz     loc_180006A2F
0x180006950  mov     ecx, 8000FFFFh; this
0x180006955  mov     [rbx+8], ecx
0x180006958  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000695d  mov     [rbx+0Ch], eax
0x180006960  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006967  jnz     short loc_180006988
0x180006969  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006970  test    rax, rax
0x180006973  jz      short loc_18000697E
0x180006975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000697a  test    al, al
0x18000697c  jmp     short loc_180006986
0x18000697e  call    cs:__imp_IsDebuggerPresent
0x180006984  test    eax, eax
0x180006986  jz      short loc_18000698E
0x180006988  test    byte ptr [rbx+4], 2
0x18000698c  jz      short loc_1800069B2
0x18000698e  mov     rax, cs:g_pfnResultLoggingCallback
0x180006995  test    rax, rax
0x180006998  jz      short loc_1800069F6
0x18000699a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800069a1  jnz     short loc_1800069F6
0x1800069a3  xor     r8d, r8d
0x1800069a6  xor     edx, edx
0x1800069a8  mov     rcx, rbx
0x1800069ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069b0  jmp     short loc_1800069F6
0x1800069b2  mov     ebp, 800h
0x1800069b7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800069be  test    rax, rax
0x1800069c1  jz      short loc_1800069DA
0x1800069c3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800069ca  jnz     short loc_1800069DA
0x1800069cc  mov     r8d, ebp
0x1800069cf  mov     rdx, rsi
0x1800069d2  mov     rcx, rbx
0x1800069d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069da  cmp     [rsi], di
0x1800069dd  jnz     short loc_1800069ED
0x1800069df  mov     r8, rbx; unsigned __int64
0x1800069e2  mov     rdx, rbp; unsigned __int16 *
0x1800069e5  mov     rcx, rsi; this
0x1800069e8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800069ed  mov     rcx, rsi; lpOutputString
0x1800069f0  call    cs:__imp_OutputDebugStringW
0x1800069f6  test    byte ptr [rbx+4], 4
0x1800069fa  jnz     short loc_180006A05
0x1800069fc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006a03  jz      short loc_180006A17
0x180006a05  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006a0c  test    rax, rax
0x180006a0f  jz      short loc_180006A17
0x180006a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a16  nop
0x180006a17  mov     rbx, [rsp+78h+arg_10]
0x180006a1f  add     rsp, 40h
0x180006a23  pop     r15
0x180006a25  pop     r14
0x180006a27  pop     r13
0x180006a29  pop     r12
0x180006a2b  pop     rdi
0x180006a2c  pop     rsi
0x180006a2d  pop     rbp
0x180006a2e  retn
0x180006a2f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
