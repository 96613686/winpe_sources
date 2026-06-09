# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800053f8`
- end: `0x1800056f1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800038d4`
- `0x180009638`

## callees

- `0x1800035dc`
- `0x1800049b4`
- `0x180005130`
- `0x1800053f8`
- `0x180005b3c`
- `0x180005b58`
- `0x180005b6c`
- `0x180005b88`
- `0x180006828`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000551b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000551b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800056ac`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800056ac`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000563a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000563a`

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
    ModuleName = wil::details::g_pfnGetModuleName();
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x1800053f8  mov     [rsp+arg_10], rbx
0x1800053fd  mov     [rsp+arg_8], edx
0x180005401  mov     [rsp+arg_0], rcx
0x180005406  push    rbp
0x180005407  push    rsi
0x180005408  push    rdi
0x180005409  push    r12
0x18000540b  push    r13
0x18000540d  push    r14
0x18000540f  push    r15
0x180005411  sub     rsp, 40h
0x180005415  mov     r12, r9
0x180005418  mov     r13, r8
0x18000541b  mov     r10, rcx
0x18000541e  xor     eax, eax
0x180005420  mov     rsi, [rsp+78h+lpOutputString]
0x180005428  mov     [rsi], ax
0x18000542b  mov     rax, [rsp+78h+arg_60]
0x180005433  mov     byte ptr [rax], 0
0x180005436  mov     r14, [rsp+78h+arg_38]
0x18000543e  mov     edi, [r14]
0x180005441  mov     rbx, [rsp+78h+arg_78]
0x180005449  mov     [rbx+8], edi
0x18000544c  mov     eax, [r14+4]
0x180005450  mov     [rbx+0Ch], eax
0x180005453  xor     ebp, ebp
0x180005455  mov     r15d, [rsp+78h+arg_30]
0x18000545d  mov     ecx, r15d
0x180005460  test    r15d, r15d
0x180005463  jz      short loc_1800054CB
0x180005465  sub     ecx, 1
0x180005468  jz      short loc_1800054C2
0x18000546a  sub     ecx, 1
0x18000546d  jz      short loc_18000547D
0x18000546f  cmp     ecx, 1
0x180005472  jnz     short loc_1800054D4
0x180005474  mov     ecx, edi; this
0x180005476  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000547b  jmp     short loc_1800054D2
0x18000547d  test    edi, edi
0x18000547f  js      short loc_1800054B9
0x180005481  mov     edi, 8007029Ch
0x180005486  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000548a  mov     rax, [rsp+78h+arg_28]
0x180005492  mov     [rsp+78h+var_50], rax; __int64
0x180005497  mov     rax, [rsp+78h+arg_20]
0x18000549f  mov     [rsp+78h+var_58], rax; __int64
0x1800054a4  mov     rcx, r10; int
0x1800054a7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800054ac  mov     [rbx+8], edi
0x1800054af  mov     ecx, edi; this
0x1800054b1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800054b6  mov     [rbx+0Ch], eax
0x1800054b9  mov     ecx, edi; this
0x1800054bb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800054c0  jmp     short loc_1800054D2
0x1800054c2  mov     ecx, edi; this
0x1800054c4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800054c9  jmp     short loc_1800054D2
0x1800054cb  mov     ecx, edi; this
0x1800054cd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800054d2  mov     ebp, eax
0x1800054d4  mov     [rbx], r15d
0x1800054d7  mov     eax, [rsp+78h+arg_70]
0x1800054de  mov     [rbx+4], eax
0x1800054e1  cmp     dword ptr [r14+8], 1
0x1800054e6  jnz     short loc_1800054EE
0x1800054e8  or      eax, 8
0x1800054eb  mov     [rbx+4], eax
0x1800054ee  mov     eax, 1
0x1800054f3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800054fb  inc     eax
0x1800054fd  mov     [rbx+10h], eax
0x180005500  mov     rax, [rsp+78h+arg_40]
0x180005508  xor     edi, edi
0x18000550a  test    rax, rax
0x18000550d  jz      short loc_180005514
0x18000550f  cmp     [rax], di
0x180005512  jnz     short loc_180005517
0x180005514  mov     rax, rdi
0x180005517  mov     [rbx+18h], rax
0x18000551b  call    cs:__imp_GetCurrentThreadId
0x180005521  mov     [rbx+20h], eax
0x180005524  mov     [rbx+38h], r13
0x180005528  mov     eax, [rsp+78h+arg_8]
0x18000552f  mov     [rbx+40h], eax
0x180005532  mov     [rbx+44h], ebp
0x180005535  mov     rax, [rsp+78h+arg_20]
0x18000553d  mov     [rbx+28h], rax
0x180005541  mov     [rbx+30h], r12
0x180005545  mov     rax, [rsp+78h+arg_28]
0x18000554d  mov     [rbx+88h], rax
0x180005554  mov     rax, [rsp+78h+arg_0]
0x18000555c  mov     [rbx+90h], rax
0x180005563  mov     [rbx+48h], rdi
0x180005567  xorps   xmm0, xmm0
0x18000556a  xor     eax, eax
0x18000556c  movups  xmmword ptr [rbx+68h], xmm0
0x180005570  mov     [rbx+78h], rax
0x180005574  movups  xmmword ptr [rbx+50h], xmm0
0x180005578  mov     [rbx+60h], rax
0x18000557c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005583  test    rax, rax
0x180005586  jz      short loc_18000558F
0x180005588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000558d  jmp     short loc_180005592
0x18000558f  mov     rax, rdi
0x180005592  mov     [rbx+80h], rax
0x180005599  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800055a0  test    rax, rax
0x1800055a3  jz      short loc_1800055AD
0x1800055a5  mov     rcx, rbx
0x1800055a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055ad  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800055b4  test    rax, rax
0x1800055b7  jz      short loc_1800055CF
0x1800055b9  mov     r8d, 400h
0x1800055bf  mov     rdx, [rsp+78h+arg_60]
0x1800055c7  mov     rcx, rbx
0x1800055ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055cf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800055d6  test    rax, rax
0x1800055d9  jz      short loc_1800055E3
0x1800055db  mov     rcx, rbx
0x1800055de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055e3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800055ea  test    rax, rax
0x1800055ed  jz      short loc_1800055FD
0x1800055ef  test    byte ptr [rbx+4], 2
0x1800055f3  jnz     short loc_1800055FD
0x1800055f5  mov     rcx, rbx
0x1800055f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055fd  cmp     [rbx+8], edi
0x180005600  jl      short loc_18000561C
0x180005602  cmp     r15d, 3
0x180005606  jnz     loc_1800056EB
0x18000560c  mov     ecx, 8000FFFFh; this
0x180005611  mov     [rbx+8], ecx
0x180005614  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005619  mov     [rbx+0Ch], eax
0x18000561c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005623  jnz     short loc_180005644
0x180005625  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000562c  test    rax, rax
0x18000562f  jz      short loc_18000563A
0x180005631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005636  test    al, al
0x180005638  jmp     short loc_180005642
0x18000563a  call    cs:__imp_IsDebuggerPresent
0x180005640  test    eax, eax
0x180005642  jz      short loc_18000564A
0x180005644  test    byte ptr [rbx+4], 2
0x180005648  jz      short loc_18000566E
0x18000564a  mov     rax, cs:g_pfnResultLoggingCallback
0x180005651  test    rax, rax
0x180005654  jz      short loc_1800056B2
0x180005656  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000565d  jnz     short loc_1800056B2
0x18000565f  xor     r8d, r8d
0x180005662  xor     edx, edx
0x180005664  mov     rcx, rbx
0x180005667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000566c  jmp     short loc_1800056B2
0x18000566e  mov     ebp, 800h
0x180005673  mov     rax, cs:g_pfnResultLoggingCallback
0x18000567a  test    rax, rax
0x18000567d  jz      short loc_180005696
0x18000567f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005686  jnz     short loc_180005696
0x180005688  mov     r8d, ebp
0x18000568b  mov     rdx, rsi
0x18000568e  mov     rcx, rbx
0x180005691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005696  cmp     [rsi], di
0x180005699  jnz     short loc_1800056A9
0x18000569b  mov     r8, rbx; unsigned __int64
0x18000569e  mov     rdx, rbp; unsigned __int16 *
0x1800056a1  mov     rcx, rsi; this
0x1800056a4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800056a9  mov     rcx, rsi; lpOutputString
0x1800056ac  call    cs:__imp_OutputDebugStringW
0x1800056b2  test    byte ptr [rbx+4], 4
0x1800056b6  jnz     short loc_1800056C1
0x1800056b8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800056bf  jz      short loc_1800056D3
0x1800056c1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800056c8  test    rax, rax
0x1800056cb  jz      short loc_1800056D3
0x1800056cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056d2  nop
0x1800056d3  mov     rbx, [rsp+78h+arg_10]
0x1800056db  add     rsp, 40h
0x1800056df  pop     r15
0x1800056e1  pop     r14
0x1800056e3  pop     r13
0x1800056e5  pop     r12
0x1800056e7  pop     rdi
0x1800056e8  pop     rsi
0x1800056e9  pop     rbp
0x1800056ea  retn
0x1800056eb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
