# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008544`
- end: `0x18000881d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `729`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180004d64`
- `0x180005090`

## callees

- `0x180003e30`
- `0x180004ca4`
- `0x180007920`
- `0x1800080fc`
- `0x1800082e4`
- `0x180008544`
- `0x18000969c`
- `0x180009828`
- `0x180009844`
- `0x18000b858`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800087b5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800087b5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008667`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008667`

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
        WCHAR *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  __int64 ModuleName; // rax
  __int64 v27; // rcx
  const struct wil::FailureInfo *v28; // r9
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::details::IsDebuggerPresent(v25) || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v28);
    OutputDebugStringW(lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v27);
  }
}

```

## disassembly

```asm
0x180008544  mov     [rsp+arg_10], rbx
0x180008549  mov     [rsp+arg_8], edx
0x18000854d  mov     [rsp+arg_0], rcx
0x180008552  push    rbp
0x180008553  push    rsi
0x180008554  push    rdi
0x180008555  push    r12
0x180008557  push    r13
0x180008559  push    r14
0x18000855b  push    r15
0x18000855d  sub     rsp, 40h
0x180008561  mov     r14, [rsp+78h+arg_38]
0x180008569  xor     eax, eax
0x18000856b  mov     rbx, [rsp+78h+arg_78]
0x180008573  xor     ebp, ebp
0x180008575  mov     r15d, [rsp+78h+arg_30]
0x18000857d  mov     r10, rcx
0x180008580  mov     rsi, [rsp+78h+lpOutputString]
0x180008588  mov     r12, r9
0x18000858b  mov     r13, r8
0x18000858e  mov     ecx, r15d
0x180008591  mov     [rsi], ax
0x180008594  mov     rax, [rsp+78h+arg_60]
0x18000859c  mov     byte ptr [rax], 0
0x18000859f  mov     edi, [r14]
0x1800085a2  mov     [rbx+8], edi
0x1800085a5  mov     eax, [r14+4]
0x1800085a9  mov     [rbx+0Ch], eax
0x1800085ac  test    r15d, r15d
0x1800085af  jz      short loc_180008617
0x1800085b1  sub     ecx, 1
0x1800085b4  jz      short loc_18000860E
0x1800085b6  sub     ecx, 1
0x1800085b9  jz      short loc_1800085C9
0x1800085bb  cmp     ecx, 1
0x1800085be  jnz     short loc_180008620
0x1800085c0  mov     ecx, edi; this
0x1800085c2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800085c7  jmp     short loc_18000861E
0x1800085c9  test    edi, edi
0x1800085cb  js      short loc_180008605
0x1800085cd  mov     rax, [rsp+78h+arg_28]
0x1800085d5  mov     edi, 8007029Ch
0x1800085da  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800085de  mov     rcx, r10; int
0x1800085e1  mov     [rsp+78h+var_50], rax; __int64
0x1800085e6  mov     rax, [rsp+78h+arg_20]
0x1800085ee  mov     [rsp+78h+var_58], rax; __int64
0x1800085f3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800085f8  mov     ecx, edi; this
0x1800085fa  mov     [rbx+8], edi
0x1800085fd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008602  mov     [rbx+0Ch], eax
0x180008605  mov     ecx, edi; this
0x180008607  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000860c  jmp     short loc_18000861E
0x18000860e  mov     ecx, edi; this
0x180008610  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008615  jmp     short loc_18000861E
0x180008617  mov     ecx, edi; this
0x180008619  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000861e  mov     ebp, eax
0x180008620  mov     eax, [rsp+78h+arg_70]
0x180008627  mov     [rbx+4], eax
0x18000862a  mov     [rbx], r15d
0x18000862d  cmp     dword ptr [r14+8], 1
0x180008632  jnz     short loc_18000863A
0x180008634  or      eax, 8
0x180008637  mov     [rbx+4], eax
0x18000863a  mov     eax, 1
0x18000863f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008647  inc     eax
0x180008649  xor     edi, edi
0x18000864b  mov     [rbx+10h], eax
0x18000864e  mov     rax, [rsp+78h+arg_40]
0x180008656  test    rax, rax
0x180008659  jz      short loc_180008660
0x18000865b  cmp     [rax], di
0x18000865e  jnz     short loc_180008663
0x180008660  mov     rax, rdi
0x180008663  mov     [rbx+18h], rax
0x180008667  call    cs:__imp_GetCurrentThreadId
0x18000866d  mov     [rbx+38h], r13
0x180008671  xorps   xmm0, xmm0
0x180008674  mov     [rbx+20h], eax
0x180008677  mov     eax, [rsp+78h+arg_8]
0x18000867e  mov     [rbx+40h], eax
0x180008681  mov     rax, [rsp+78h+arg_20]
0x180008689  mov     [rbx+28h], rax
0x18000868d  mov     rax, [rsp+78h+arg_28]
0x180008695  mov     [rbx+88h], rax
0x18000869c  mov     rax, [rsp+78h+arg_0]
0x1800086a4  mov     [rbx+90h], rax
0x1800086ab  xor     eax, eax
0x1800086ad  mov     [rbx+44h], ebp
0x1800086b0  mov     [rbx+30h], r12
0x1800086b4  mov     [rbx+48h], rdi
0x1800086b8  movups  xmmword ptr [rbx+68h], xmm0
0x1800086bc  mov     [rbx+78h], rax
0x1800086c0  movups  xmmword ptr [rbx+50h], xmm0
0x1800086c4  mov     [rbx+60h], rax
0x1800086c8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800086cf  test    rax, rax
0x1800086d2  jz      short loc_1800086DB
0x1800086d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086d9  jmp     short loc_1800086DE
0x1800086db  mov     rax, rdi
0x1800086de  mov     [rbx+80h], rax
0x1800086e5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800086ec  test    rax, rax
0x1800086ef  jz      short loc_1800086F9
0x1800086f1  mov     rcx, rbx
0x1800086f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086f9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008700  test    rax, rax
0x180008703  jz      short loc_18000871B
0x180008705  mov     rdx, [rsp+78h+arg_60]
0x18000870d  mov     r8d, 400h
0x180008713  mov     rcx, rbx
0x180008716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000871b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008722  test    rax, rax
0x180008725  jz      short loc_18000872F
0x180008727  mov     rcx, rbx
0x18000872a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000872f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008736  test    rax, rax
0x180008739  jz      short loc_180008749
0x18000873b  test    byte ptr [rbx+4], 2
0x18000873f  jnz     short loc_180008749
0x180008741  mov     rcx, rbx
0x180008744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008749  cmp     [rbx+8], edi
0x18000874c  jl      short loc_180008768
0x18000874e  cmp     r15d, 3
0x180008752  jnz     loc_180008817
0x180008758  mov     ecx, 8000FFFFh; this
0x18000875d  mov     [rbx+8], ecx
0x180008760  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008765  mov     [rbx+0Ch], eax
0x180008768  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x18000876d  test    al, al
0x18000876f  jz      short loc_1800087BD
0x180008771  test    byte ptr [rbx+4], 2
0x180008775  jnz     short loc_1800087BD
0x180008777  mov     rax, cs:g_pfnResultLoggingCallback
0x18000877e  mov     ebp, 800h
0x180008783  test    rax, rax
0x180008786  jz      short loc_18000879F
0x180008788  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000878f  jnz     short loc_18000879F
0x180008791  mov     r8d, ebp
0x180008794  mov     rdx, rsi
0x180008797  mov     rcx, rbx
0x18000879a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000879f  cmp     [rsi], di
0x1800087a2  jnz     short loc_1800087B2
0x1800087a4  mov     r8, rbx; unsigned __int64
0x1800087a7  mov     rdx, rbp; unsigned __int16 *
0x1800087aa  mov     rcx, rsi; pszDest
0x1800087ad  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800087b2  mov     rcx, rsi; lpOutputString
0x1800087b5  call    cs:__imp_OutputDebugStringW
0x1800087bb  jmp     short loc_1800087DF
0x1800087bd  mov     rax, cs:g_pfnResultLoggingCallback
0x1800087c4  test    rax, rax
0x1800087c7  jz      short loc_1800087DF
0x1800087c9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800087d0  jnz     short loc_1800087DF
0x1800087d2  xor     r8d, r8d
0x1800087d5  xor     edx, edx
0x1800087d7  mov     rcx, rbx
0x1800087da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087df  test    byte ptr [rbx+4], 4
0x1800087e3  jnz     short loc_1800087EE
0x1800087e5  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800087ec  jz      short loc_1800087FF
0x1800087ee  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800087f5  test    rax, rax
0x1800087f8  jz      short loc_1800087FF
0x1800087fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087ff  mov     rbx, [rsp+78h+arg_10]
0x180008807  add     rsp, 40h
0x18000880b  pop     r15
0x18000880d  pop     r14
0x18000880f  pop     r13
0x180008811  pop     r12
0x180008813  pop     rdi
0x180008814  pop     rsi
0x180008815  pop     rbp
0x180008816  retn
0x180008817  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
