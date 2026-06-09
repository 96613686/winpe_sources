# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180016640`
- end: `0x180016939`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000874c`
- `0x180008a98`

## callees

- `0x18000868c`
- `0x180015884`
- `0x180016128`
- `0x180016640`
- `0x1800180cc`
- `0x1800180f0`
- `0x180018240`
- `0x18001825c`
- `0x18001a804`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016763`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016763`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180016882`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180016882`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800168f4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800168f4`

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
0x180016640  mov     [rsp+arg_10], rbx
0x180016645  mov     [rsp+arg_8], edx
0x180016649  mov     [rsp+arg_0], rcx
0x18001664e  push    rbp
0x18001664f  push    rsi
0x180016650  push    rdi
0x180016651  push    r12
0x180016653  push    r13
0x180016655  push    r14
0x180016657  push    r15
0x180016659  sub     rsp, 40h
0x18001665d  mov     r12, r9
0x180016660  mov     r13, r8
0x180016663  mov     r10, rcx
0x180016666  xor     eax, eax
0x180016668  mov     rsi, [rsp+78h+lpOutputString]
0x180016670  mov     [rsi], ax
0x180016673  mov     rax, [rsp+78h+arg_60]
0x18001667b  mov     byte ptr [rax], 0
0x18001667e  mov     r14, [rsp+78h+arg_38]
0x180016686  mov     edi, [r14]
0x180016689  mov     rbx, [rsp+78h+arg_78]
0x180016691  mov     [rbx+8], edi
0x180016694  mov     eax, [r14+4]
0x180016698  mov     [rbx+0Ch], eax
0x18001669b  xor     ebp, ebp
0x18001669d  mov     r15d, [rsp+78h+arg_30]
0x1800166a5  mov     ecx, r15d
0x1800166a8  test    r15d, r15d
0x1800166ab  jz      short loc_180016713
0x1800166ad  sub     ecx, 1
0x1800166b0  jz      short loc_18001670A
0x1800166b2  sub     ecx, 1
0x1800166b5  jz      short loc_1800166C5
0x1800166b7  cmp     ecx, 1
0x1800166ba  jnz     short loc_18001671C
0x1800166bc  mov     ecx, edi; this
0x1800166be  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800166c3  jmp     short loc_18001671A
0x1800166c5  test    edi, edi
0x1800166c7  js      short loc_180016701
0x1800166c9  mov     edi, 8007029Ch
0x1800166ce  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800166d2  mov     rax, [rsp+78h+arg_28]
0x1800166da  mov     [rsp+78h+var_50], rax; __int64
0x1800166df  mov     rax, [rsp+78h+arg_20]
0x1800166e7  mov     [rsp+78h+var_58], rax; __int64
0x1800166ec  mov     rcx, r10; int
0x1800166ef  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800166f4  mov     [rbx+8], edi
0x1800166f7  mov     ecx, edi; this
0x1800166f9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800166fe  mov     [rbx+0Ch], eax
0x180016701  mov     ecx, edi; this
0x180016703  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180016708  jmp     short loc_18001671A
0x18001670a  mov     ecx, edi; this
0x18001670c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180016711  jmp     short loc_18001671A
0x180016713  mov     ecx, edi; this
0x180016715  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001671a  mov     ebp, eax
0x18001671c  mov     [rbx], r15d
0x18001671f  mov     eax, [rsp+78h+arg_70]
0x180016726  mov     [rbx+4], eax
0x180016729  cmp     dword ptr [r14+8], 1
0x18001672e  jnz     short loc_180016736
0x180016730  or      eax, 8
0x180016733  mov     [rbx+4], eax
0x180016736  mov     eax, 1
0x18001673b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180016743  inc     eax
0x180016745  mov     [rbx+10h], eax
0x180016748  mov     rax, [rsp+78h+arg_40]
0x180016750  xor     edi, edi
0x180016752  test    rax, rax
0x180016755  jz      short loc_18001675C
0x180016757  cmp     [rax], di
0x18001675a  jnz     short loc_18001675F
0x18001675c  mov     rax, rdi
0x18001675f  mov     [rbx+18h], rax
0x180016763  call    cs:__imp_GetCurrentThreadId
0x180016769  mov     [rbx+20h], eax
0x18001676c  mov     [rbx+38h], r13
0x180016770  mov     eax, [rsp+78h+arg_8]
0x180016777  mov     [rbx+40h], eax
0x18001677a  mov     [rbx+44h], ebp
0x18001677d  mov     rax, [rsp+78h+arg_20]
0x180016785  mov     [rbx+28h], rax
0x180016789  mov     [rbx+30h], r12
0x18001678d  mov     rax, [rsp+78h+arg_28]
0x180016795  mov     [rbx+88h], rax
0x18001679c  mov     rax, [rsp+78h+arg_0]
0x1800167a4  mov     [rbx+90h], rax
0x1800167ab  mov     [rbx+48h], rdi
0x1800167af  xorps   xmm0, xmm0
0x1800167b2  xor     eax, eax
0x1800167b4  movups  xmmword ptr [rbx+68h], xmm0
0x1800167b8  mov     [rbx+78h], rax
0x1800167bc  movups  xmmword ptr [rbx+50h], xmm0
0x1800167c0  mov     [rbx+60h], rax
0x1800167c4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800167cb  test    rax, rax
0x1800167ce  jz      short loc_1800167D7
0x1800167d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167d5  jmp     short loc_1800167DA
0x1800167d7  mov     rax, rdi
0x1800167da  mov     [rbx+80h], rax
0x1800167e1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800167e8  test    rax, rax
0x1800167eb  jz      short loc_1800167F5
0x1800167ed  mov     rcx, rbx
0x1800167f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167f5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800167fc  test    rax, rax
0x1800167ff  jz      short loc_180016817
0x180016801  mov     r8d, 400h
0x180016807  mov     rdx, [rsp+78h+arg_60]
0x18001680f  mov     rcx, rbx
0x180016812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016817  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001681e  test    rax, rax
0x180016821  jz      short loc_18001682B
0x180016823  mov     rcx, rbx
0x180016826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001682b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180016832  test    rax, rax
0x180016835  jz      short loc_180016845
0x180016837  test    byte ptr [rbx+4], 2
0x18001683b  jnz     short loc_180016845
0x18001683d  mov     rcx, rbx
0x180016840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016845  cmp     [rbx+8], edi
0x180016848  jl      short loc_180016864
0x18001684a  cmp     r15d, 3
0x18001684e  jnz     loc_180016933
0x180016854  mov     ecx, 8000FFFFh; this
0x180016859  mov     [rbx+8], ecx
0x18001685c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180016861  mov     [rbx+0Ch], eax
0x180016864  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001686b  jnz     short loc_18001688C
0x18001686d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180016874  test    rax, rax
0x180016877  jz      short loc_180016882
0x180016879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001687e  test    al, al
0x180016880  jmp     short loc_18001688A
0x180016882  call    cs:__imp_IsDebuggerPresent
0x180016888  test    eax, eax
0x18001688a  jz      short loc_180016892
0x18001688c  test    byte ptr [rbx+4], 2
0x180016890  jz      short loc_1800168B6
0x180016892  mov     rax, cs:g_pfnResultLoggingCallback
0x180016899  test    rax, rax
0x18001689c  jz      short loc_1800168FA
0x18001689e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800168a5  jnz     short loc_1800168FA
0x1800168a7  xor     r8d, r8d
0x1800168aa  xor     edx, edx
0x1800168ac  mov     rcx, rbx
0x1800168af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168b4  jmp     short loc_1800168FA
0x1800168b6  mov     ebp, 800h
0x1800168bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800168c2  test    rax, rax
0x1800168c5  jz      short loc_1800168DE
0x1800168c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800168ce  jnz     short loc_1800168DE
0x1800168d0  mov     r8d, ebp
0x1800168d3  mov     rdx, rsi
0x1800168d6  mov     rcx, rbx
0x1800168d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168de  cmp     [rsi], di
0x1800168e1  jnz     short loc_1800168F1
0x1800168e3  mov     r8, rbx; unsigned __int64
0x1800168e6  mov     rdx, rbp; unsigned __int16 *
0x1800168e9  mov     rcx, rsi; this
0x1800168ec  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800168f1  mov     rcx, rsi; lpOutputString
0x1800168f4  call    cs:__imp_OutputDebugStringW
0x1800168fa  test    byte ptr [rbx+4], 4
0x1800168fe  jnz     short loc_180016909
0x180016900  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180016907  jz      short loc_18001691B
0x180016909  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180016910  test    rax, rax
0x180016913  jz      short loc_18001691B
0x180016915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001691a  nop
0x18001691b  mov     rbx, [rsp+78h+arg_10]
0x180016923  add     rsp, 40h
0x180016927  pop     r15
0x180016929  pop     r14
0x18001692b  pop     r13
0x18001692d  pop     r12
0x18001692f  pop     rdi
0x180016930  pop     rsi
0x180016931  pop     rbp
0x180016932  retn
0x180016933  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
