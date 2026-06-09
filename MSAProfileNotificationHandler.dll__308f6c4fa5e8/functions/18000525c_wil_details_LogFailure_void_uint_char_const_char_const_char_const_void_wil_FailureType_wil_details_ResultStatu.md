# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000525c`
- end: `0x180005555`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003868`

## callees

- `0x1800032a4`
- `0x1800048e4`
- `0x180005080`
- `0x18000525c`
- `0x1800058d8`
- `0x180005900`
- `0x180005914`
- `0x180005930`
- `0x180006efc`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000537f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000537f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005510`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005510`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000549e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000549e`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x18000525c  mov     [rsp+arg_10], rbx
0x180005261  mov     [rsp+arg_8], edx
0x180005265  mov     [rsp+arg_0], rcx
0x18000526a  push    rbp
0x18000526b  push    rsi
0x18000526c  push    rdi
0x18000526d  push    r12
0x18000526f  push    r13
0x180005271  push    r14
0x180005273  push    r15
0x180005275  sub     rsp, 40h
0x180005279  mov     r12, r9
0x18000527c  mov     r13, r8
0x18000527f  mov     r10, rcx
0x180005282  xor     eax, eax
0x180005284  mov     rsi, [rsp+78h+lpOutputString]
0x18000528c  mov     [rsi], ax
0x18000528f  mov     rax, [rsp+78h+arg_60]
0x180005297  mov     byte ptr [rax], 0
0x18000529a  mov     r14, [rsp+78h+arg_38]
0x1800052a2  mov     edi, [r14]
0x1800052a5  mov     rbx, [rsp+78h+arg_78]
0x1800052ad  mov     [rbx+8], edi
0x1800052b0  mov     eax, [r14+4]
0x1800052b4  mov     [rbx+0Ch], eax
0x1800052b7  xor     ebp, ebp
0x1800052b9  mov     r15d, [rsp+78h+arg_30]
0x1800052c1  mov     ecx, r15d
0x1800052c4  test    r15d, r15d
0x1800052c7  jz      short loc_18000532F
0x1800052c9  sub     ecx, 1
0x1800052cc  jz      short loc_180005326
0x1800052ce  sub     ecx, 1
0x1800052d1  jz      short loc_1800052E1
0x1800052d3  cmp     ecx, 1
0x1800052d6  jnz     short loc_180005338
0x1800052d8  mov     ecx, edi; this
0x1800052da  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800052df  jmp     short loc_180005336
0x1800052e1  test    edi, edi
0x1800052e3  js      short loc_18000531D
0x1800052e5  mov     edi, 8007029Ch
0x1800052ea  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800052ee  mov     rax, [rsp+78h+arg_28]
0x1800052f6  mov     [rsp+78h+var_50], rax; __int64
0x1800052fb  mov     rax, [rsp+78h+arg_20]
0x180005303  mov     [rsp+78h+var_58], rax; __int64
0x180005308  mov     rcx, r10; int
0x18000530b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005310  mov     [rbx+8], edi
0x180005313  mov     ecx, edi; this
0x180005315  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000531a  mov     [rbx+0Ch], eax
0x18000531d  mov     ecx, edi; this
0x18000531f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005324  jmp     short loc_180005336
0x180005326  mov     ecx, edi; this
0x180005328  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000532d  jmp     short loc_180005336
0x18000532f  mov     ecx, edi; this
0x180005331  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005336  mov     ebp, eax
0x180005338  mov     [rbx], r15d
0x18000533b  mov     eax, [rsp+78h+arg_70]
0x180005342  mov     [rbx+4], eax
0x180005345  cmp     dword ptr [r14+8], 1
0x18000534a  jnz     short loc_180005352
0x18000534c  or      eax, 8
0x18000534f  mov     [rbx+4], eax
0x180005352  mov     eax, 1
0x180005357  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000535f  inc     eax
0x180005361  mov     [rbx+10h], eax
0x180005364  mov     rax, [rsp+78h+arg_40]
0x18000536c  xor     edi, edi
0x18000536e  test    rax, rax
0x180005371  jz      short loc_180005378
0x180005373  cmp     [rax], di
0x180005376  jnz     short loc_18000537B
0x180005378  mov     rax, rdi
0x18000537b  mov     [rbx+18h], rax
0x18000537f  call    cs:__imp_GetCurrentThreadId
0x180005385  mov     [rbx+20h], eax
0x180005388  mov     [rbx+38h], r13
0x18000538c  mov     eax, [rsp+78h+arg_8]
0x180005393  mov     [rbx+40h], eax
0x180005396  mov     [rbx+44h], ebp
0x180005399  mov     rax, [rsp+78h+arg_20]
0x1800053a1  mov     [rbx+28h], rax
0x1800053a5  mov     [rbx+30h], r12
0x1800053a9  mov     rax, [rsp+78h+arg_28]
0x1800053b1  mov     [rbx+88h], rax
0x1800053b8  mov     rax, [rsp+78h+arg_0]
0x1800053c0  mov     [rbx+90h], rax
0x1800053c7  mov     [rbx+48h], rdi
0x1800053cb  xorps   xmm0, xmm0
0x1800053ce  xor     eax, eax
0x1800053d0  movups  xmmword ptr [rbx+68h], xmm0
0x1800053d4  mov     [rbx+78h], rax
0x1800053d8  movups  xmmword ptr [rbx+50h], xmm0
0x1800053dc  mov     [rbx+60h], rax
0x1800053e0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800053e7  test    rax, rax
0x1800053ea  jz      short loc_1800053F3
0x1800053ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053f1  jmp     short loc_1800053F6
0x1800053f3  mov     rax, rdi
0x1800053f6  mov     [rbx+80h], rax
0x1800053fd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005404  test    rax, rax
0x180005407  jz      short loc_180005411
0x180005409  mov     rcx, rbx
0x18000540c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005411  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005418  test    rax, rax
0x18000541b  jz      short loc_180005433
0x18000541d  mov     r8d, 400h
0x180005423  mov     rdx, [rsp+78h+arg_60]
0x18000542b  mov     rcx, rbx
0x18000542e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005433  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000543a  test    rax, rax
0x18000543d  jz      short loc_180005447
0x18000543f  mov     rcx, rbx
0x180005442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005447  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000544e  test    rax, rax
0x180005451  jz      short loc_180005461
0x180005453  test    byte ptr [rbx+4], 2
0x180005457  jnz     short loc_180005461
0x180005459  mov     rcx, rbx
0x18000545c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005461  cmp     [rbx+8], edi
0x180005464  jl      short loc_180005480
0x180005466  cmp     r15d, 3
0x18000546a  jnz     loc_18000554F
0x180005470  mov     ecx, 8000FFFFh; this
0x180005475  mov     [rbx+8], ecx
0x180005478  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000547d  mov     [rbx+0Ch], eax
0x180005480  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005487  jnz     short loc_1800054A8
0x180005489  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005490  test    rax, rax
0x180005493  jz      short loc_18000549E
0x180005495  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000549a  test    al, al
0x18000549c  jmp     short loc_1800054A6
0x18000549e  call    cs:__imp_IsDebuggerPresent
0x1800054a4  test    eax, eax
0x1800054a6  jz      short loc_1800054AE
0x1800054a8  test    byte ptr [rbx+4], 2
0x1800054ac  jz      short loc_1800054D2
0x1800054ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800054b5  test    rax, rax
0x1800054b8  jz      short loc_180005516
0x1800054ba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800054c1  jnz     short loc_180005516
0x1800054c3  xor     r8d, r8d
0x1800054c6  xor     edx, edx
0x1800054c8  mov     rcx, rbx
0x1800054cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054d0  jmp     short loc_180005516
0x1800054d2  mov     ebp, 800h
0x1800054d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800054de  test    rax, rax
0x1800054e1  jz      short loc_1800054FA
0x1800054e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800054ea  jnz     short loc_1800054FA
0x1800054ec  mov     r8d, ebp
0x1800054ef  mov     rdx, rsi
0x1800054f2  mov     rcx, rbx
0x1800054f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054fa  cmp     [rsi], di
0x1800054fd  jnz     short loc_18000550D
0x1800054ff  mov     r8, rbx; unsigned __int64
0x180005502  mov     rdx, rbp; unsigned __int16 *
0x180005505  mov     rcx, rsi; this
0x180005508  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000550d  mov     rcx, rsi; lpOutputString
0x180005510  call    cs:__imp_OutputDebugStringW
0x180005516  test    byte ptr [rbx+4], 4
0x18000551a  jnz     short loc_180005525
0x18000551c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005523  jz      short loc_180005537
0x180005525  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000552c  test    rax, rax
0x18000552f  jz      short loc_180005537
0x180005531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005536  nop
0x180005537  mov     rbx, [rsp+78h+arg_10]
0x18000553f  add     rsp, 40h
0x180005543  pop     r15
0x180005545  pop     r14
0x180005547  pop     r13
0x180005549  pop     r12
0x18000554b  pop     rdi
0x18000554c  pop     rsi
0x18000554d  pop     rbp
0x18000554e  retn
0x18000554f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
