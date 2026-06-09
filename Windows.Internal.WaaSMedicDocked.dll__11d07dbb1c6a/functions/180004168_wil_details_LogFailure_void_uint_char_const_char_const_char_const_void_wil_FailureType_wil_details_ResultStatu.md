# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004168`
- end: `0x180004461`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002920`

## callees

- `0x18000234c`
- `0x180003804`
- `0x180003fa4`
- `0x180004168`
- `0x1800046ac`
- `0x1800046d0`
- `0x1800046e4`
- `0x180004700`
- `0x1800056ec`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000428b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000428b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000441c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000441c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800043aa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800043aa`

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
0x180004168  mov     [rsp+arg_10], rbx
0x18000416d  mov     [rsp+arg_8], edx
0x180004171  mov     [rsp+arg_0], rcx
0x180004176  push    rbp
0x180004177  push    rsi
0x180004178  push    rdi
0x180004179  push    r12
0x18000417b  push    r13
0x18000417d  push    r14
0x18000417f  push    r15
0x180004181  sub     rsp, 40h
0x180004185  mov     r12, r9
0x180004188  mov     r13, r8
0x18000418b  mov     r10, rcx
0x18000418e  xor     eax, eax
0x180004190  mov     rsi, [rsp+78h+lpOutputString]
0x180004198  mov     [rsi], ax
0x18000419b  mov     rax, [rsp+78h+arg_60]
0x1800041a3  mov     byte ptr [rax], 0
0x1800041a6  mov     r14, [rsp+78h+arg_38]
0x1800041ae  mov     edi, [r14]
0x1800041b1  mov     rbx, [rsp+78h+arg_78]
0x1800041b9  mov     [rbx+8], edi
0x1800041bc  mov     eax, [r14+4]
0x1800041c0  mov     [rbx+0Ch], eax
0x1800041c3  xor     ebp, ebp
0x1800041c5  mov     r15d, [rsp+78h+arg_30]
0x1800041cd  mov     ecx, r15d
0x1800041d0  test    r15d, r15d
0x1800041d3  jz      short loc_18000423B
0x1800041d5  sub     ecx, 1
0x1800041d8  jz      short loc_180004232
0x1800041da  sub     ecx, 1
0x1800041dd  jz      short loc_1800041ED
0x1800041df  cmp     ecx, 1
0x1800041e2  jnz     short loc_180004244
0x1800041e4  mov     ecx, edi; this
0x1800041e6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800041eb  jmp     short loc_180004242
0x1800041ed  test    edi, edi
0x1800041ef  js      short loc_180004229
0x1800041f1  mov     edi, 8007029Ch
0x1800041f6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800041fa  mov     rax, [rsp+78h+arg_28]
0x180004202  mov     [rsp+78h+var_50], rax; __int64
0x180004207  mov     rax, [rsp+78h+arg_20]
0x18000420f  mov     [rsp+78h+var_58], rax; __int64
0x180004214  mov     rcx, r10; int
0x180004217  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000421c  mov     [rbx+8], edi
0x18000421f  mov     ecx, edi; this
0x180004221  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004226  mov     [rbx+0Ch], eax
0x180004229  mov     ecx, edi; this
0x18000422b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004230  jmp     short loc_180004242
0x180004232  mov     ecx, edi; this
0x180004234  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004239  jmp     short loc_180004242
0x18000423b  mov     ecx, edi; this
0x18000423d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004242  mov     ebp, eax
0x180004244  mov     [rbx], r15d
0x180004247  mov     eax, [rsp+78h+arg_70]
0x18000424e  mov     [rbx+4], eax
0x180004251  cmp     dword ptr [r14+8], 1
0x180004256  jnz     short loc_18000425E
0x180004258  or      eax, 8
0x18000425b  mov     [rbx+4], eax
0x18000425e  mov     eax, 1
0x180004263  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000426b  inc     eax
0x18000426d  mov     [rbx+10h], eax
0x180004270  mov     rax, [rsp+78h+arg_40]
0x180004278  xor     edi, edi
0x18000427a  test    rax, rax
0x18000427d  jz      short loc_180004284
0x18000427f  cmp     [rax], di
0x180004282  jnz     short loc_180004287
0x180004284  mov     rax, rdi
0x180004287  mov     [rbx+18h], rax
0x18000428b  call    cs:__imp_GetCurrentThreadId
0x180004291  mov     [rbx+20h], eax
0x180004294  mov     [rbx+38h], r13
0x180004298  mov     eax, [rsp+78h+arg_8]
0x18000429f  mov     [rbx+40h], eax
0x1800042a2  mov     [rbx+44h], ebp
0x1800042a5  mov     rax, [rsp+78h+arg_20]
0x1800042ad  mov     [rbx+28h], rax
0x1800042b1  mov     [rbx+30h], r12
0x1800042b5  mov     rax, [rsp+78h+arg_28]
0x1800042bd  mov     [rbx+88h], rax
0x1800042c4  mov     rax, [rsp+78h+arg_0]
0x1800042cc  mov     [rbx+90h], rax
0x1800042d3  mov     [rbx+48h], rdi
0x1800042d7  xorps   xmm0, xmm0
0x1800042da  xor     eax, eax
0x1800042dc  movups  xmmword ptr [rbx+68h], xmm0
0x1800042e0  mov     [rbx+78h], rax
0x1800042e4  movups  xmmword ptr [rbx+50h], xmm0
0x1800042e8  mov     [rbx+60h], rax
0x1800042ec  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800042f3  test    rax, rax
0x1800042f6  jz      short loc_1800042FF
0x1800042f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042fd  jmp     short loc_180004302
0x1800042ff  mov     rax, rdi
0x180004302  mov     [rbx+80h], rax
0x180004309  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004310  test    rax, rax
0x180004313  jz      short loc_18000431D
0x180004315  mov     rcx, rbx
0x180004318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000431d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004324  test    rax, rax
0x180004327  jz      short loc_18000433F
0x180004329  mov     r8d, 400h
0x18000432f  mov     rdx, [rsp+78h+arg_60]
0x180004337  mov     rcx, rbx
0x18000433a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000433f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004346  test    rax, rax
0x180004349  jz      short loc_180004353
0x18000434b  mov     rcx, rbx
0x18000434e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004353  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000435a  test    rax, rax
0x18000435d  jz      short loc_18000436D
0x18000435f  test    byte ptr [rbx+4], 2
0x180004363  jnz     short loc_18000436D
0x180004365  mov     rcx, rbx
0x180004368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000436d  cmp     [rbx+8], edi
0x180004370  jl      short loc_18000438C
0x180004372  cmp     r15d, 3
0x180004376  jnz     loc_18000445B
0x18000437c  mov     ecx, 8000FFFFh; this
0x180004381  mov     [rbx+8], ecx
0x180004384  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004389  mov     [rbx+0Ch], eax
0x18000438c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004393  jnz     short loc_1800043B4
0x180004395  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000439c  test    rax, rax
0x18000439f  jz      short loc_1800043AA
0x1800043a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043a6  test    al, al
0x1800043a8  jmp     short loc_1800043B2
0x1800043aa  call    cs:__imp_IsDebuggerPresent
0x1800043b0  test    eax, eax
0x1800043b2  jz      short loc_1800043BA
0x1800043b4  test    byte ptr [rbx+4], 2
0x1800043b8  jz      short loc_1800043DE
0x1800043ba  mov     rax, cs:g_pfnResultLoggingCallback
0x1800043c1  test    rax, rax
0x1800043c4  jz      short loc_180004422
0x1800043c6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800043cd  jnz     short loc_180004422
0x1800043cf  xor     r8d, r8d
0x1800043d2  xor     edx, edx
0x1800043d4  mov     rcx, rbx
0x1800043d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043dc  jmp     short loc_180004422
0x1800043de  mov     ebp, 800h
0x1800043e3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800043ea  test    rax, rax
0x1800043ed  jz      short loc_180004406
0x1800043ef  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800043f6  jnz     short loc_180004406
0x1800043f8  mov     r8d, ebp
0x1800043fb  mov     rdx, rsi
0x1800043fe  mov     rcx, rbx
0x180004401  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004406  cmp     [rsi], di
0x180004409  jnz     short loc_180004419
0x18000440b  mov     r8, rbx; unsigned __int64
0x18000440e  mov     rdx, rbp; unsigned __int16 *
0x180004411  mov     rcx, rsi; this
0x180004414  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004419  mov     rcx, rsi; lpOutputString
0x18000441c  call    cs:__imp_OutputDebugStringW
0x180004422  test    byte ptr [rbx+4], 4
0x180004426  jnz     short loc_180004431
0x180004428  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000442f  jz      short loc_180004443
0x180004431  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004438  test    rax, rax
0x18000443b  jz      short loc_180004443
0x18000443d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004442  nop
0x180004443  mov     rbx, [rsp+78h+arg_10]
0x18000444b  add     rsp, 40h
0x18000444f  pop     r15
0x180004451  pop     r14
0x180004453  pop     r13
0x180004455  pop     r12
0x180004457  pop     rdi
0x180004458  pop     rsi
0x180004459  pop     rbp
0x18000445a  retn
0x18000445b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
