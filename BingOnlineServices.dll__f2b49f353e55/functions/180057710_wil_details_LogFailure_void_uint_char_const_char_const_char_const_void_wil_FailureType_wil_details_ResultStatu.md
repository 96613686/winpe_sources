# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180057710`
- end: `0x180057a09`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180055d80`
- `0x1800560cc`

## callees

- `0x180055cc0`
- `0x180056c64`
- `0x18005754c`
- `0x180057710`
- `0x180057dd4`
- `0x180057df0`
- `0x180057e04`
- `0x180057e20`
- `0x180058b80`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057833`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180057833`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800579c4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800579c4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180057952`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180057952`

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
0x180057710  mov     [rsp+arg_10], rbx
0x180057715  mov     [rsp+arg_8], edx
0x180057719  mov     [rsp+arg_0], rcx
0x18005771e  push    rbp
0x18005771f  push    rsi
0x180057720  push    rdi
0x180057721  push    r12
0x180057723  push    r13
0x180057725  push    r14
0x180057727  push    r15
0x180057729  sub     rsp, 40h
0x18005772d  mov     r12, r9
0x180057730  mov     r13, r8
0x180057733  mov     r10, rcx
0x180057736  xor     eax, eax
0x180057738  mov     rsi, [rsp+78h+lpOutputString]
0x180057740  mov     [rsi], ax
0x180057743  mov     rax, [rsp+78h+arg_60]
0x18005774b  mov     byte ptr [rax], 0
0x18005774e  mov     r14, [rsp+78h+arg_38]
0x180057756  mov     edi, [r14]
0x180057759  mov     rbx, [rsp+78h+arg_78]
0x180057761  mov     [rbx+8], edi
0x180057764  mov     eax, [r14+4]
0x180057768  mov     [rbx+0Ch], eax
0x18005776b  xor     ebp, ebp
0x18005776d  mov     r15d, [rsp+78h+arg_30]
0x180057775  mov     ecx, r15d
0x180057778  test    r15d, r15d
0x18005777b  jz      short loc_1800577E3
0x18005777d  sub     ecx, 1
0x180057780  jz      short loc_1800577DA
0x180057782  sub     ecx, 1
0x180057785  jz      short loc_180057795
0x180057787  cmp     ecx, 1
0x18005778a  jnz     short loc_1800577EC
0x18005778c  mov     ecx, edi; this
0x18005778e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180057793  jmp     short loc_1800577EA
0x180057795  test    edi, edi
0x180057797  js      short loc_1800577D1
0x180057799  mov     edi, 8007029Ch
0x18005779e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800577a2  mov     rax, [rsp+78h+arg_28]
0x1800577aa  mov     [rsp+78h+var_50], rax; __int64
0x1800577af  mov     rax, [rsp+78h+arg_20]
0x1800577b7  mov     [rsp+78h+var_58], rax; __int64
0x1800577bc  mov     rcx, r10; int
0x1800577bf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800577c4  mov     [rbx+8], edi
0x1800577c7  mov     ecx, edi; this
0x1800577c9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800577ce  mov     [rbx+0Ch], eax
0x1800577d1  mov     ecx, edi; this
0x1800577d3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800577d8  jmp     short loc_1800577EA
0x1800577da  mov     ecx, edi; this
0x1800577dc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800577e1  jmp     short loc_1800577EA
0x1800577e3  mov     ecx, edi; this
0x1800577e5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800577ea  mov     ebp, eax
0x1800577ec  mov     [rbx], r15d
0x1800577ef  mov     eax, [rsp+78h+arg_70]
0x1800577f6  mov     [rbx+4], eax
0x1800577f9  cmp     dword ptr [r14+8], 1
0x1800577fe  jnz     short loc_180057806
0x180057800  or      eax, 8
0x180057803  mov     [rbx+4], eax
0x180057806  mov     eax, 1
0x18005780b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180057813  inc     eax
0x180057815  mov     [rbx+10h], eax
0x180057818  mov     rax, [rsp+78h+arg_40]
0x180057820  xor     edi, edi
0x180057822  test    rax, rax
0x180057825  jz      short loc_18005782C
0x180057827  cmp     [rax], di
0x18005782a  jnz     short loc_18005782F
0x18005782c  mov     rax, rdi
0x18005782f  mov     [rbx+18h], rax
0x180057833  call    cs:__imp_GetCurrentThreadId
0x180057839  mov     [rbx+20h], eax
0x18005783c  mov     [rbx+38h], r13
0x180057840  mov     eax, [rsp+78h+arg_8]
0x180057847  mov     [rbx+40h], eax
0x18005784a  mov     [rbx+44h], ebp
0x18005784d  mov     rax, [rsp+78h+arg_20]
0x180057855  mov     [rbx+28h], rax
0x180057859  mov     [rbx+30h], r12
0x18005785d  mov     rax, [rsp+78h+arg_28]
0x180057865  mov     [rbx+88h], rax
0x18005786c  mov     rax, [rsp+78h+arg_0]
0x180057874  mov     [rbx+90h], rax
0x18005787b  mov     [rbx+48h], rdi
0x18005787f  xorps   xmm0, xmm0
0x180057882  xor     eax, eax
0x180057884  movups  xmmword ptr [rbx+68h], xmm0
0x180057888  mov     [rbx+78h], rax
0x18005788c  movups  xmmword ptr [rbx+50h], xmm0
0x180057890  mov     [rbx+60h], rax
0x180057894  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18005789b  test    rax, rax
0x18005789e  jz      short loc_1800578A7
0x1800578a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800578a5  jmp     short loc_1800578AA
0x1800578a7  mov     rax, rdi
0x1800578aa  mov     [rbx+80h], rax
0x1800578b1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800578b8  test    rax, rax
0x1800578bb  jz      short loc_1800578C5
0x1800578bd  mov     rcx, rbx
0x1800578c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800578c5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800578cc  test    rax, rax
0x1800578cf  jz      short loc_1800578E7
0x1800578d1  mov     r8d, 400h
0x1800578d7  mov     rdx, [rsp+78h+arg_60]
0x1800578df  mov     rcx, rbx
0x1800578e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800578e7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800578ee  test    rax, rax
0x1800578f1  jz      short loc_1800578FB
0x1800578f3  mov     rcx, rbx
0x1800578f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800578fb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180057902  test    rax, rax
0x180057905  jz      short loc_180057915
0x180057907  test    byte ptr [rbx+4], 2
0x18005790b  jnz     short loc_180057915
0x18005790d  mov     rcx, rbx
0x180057910  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057915  cmp     [rbx+8], edi
0x180057918  jl      short loc_180057934
0x18005791a  cmp     r15d, 3
0x18005791e  jnz     loc_180057A03
0x180057924  mov     ecx, 8000FFFFh; this
0x180057929  mov     [rbx+8], ecx
0x18005792c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180057931  mov     [rbx+0Ch], eax
0x180057934  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18005793b  jnz     short loc_18005795C
0x18005793d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180057944  test    rax, rax
0x180057947  jz      short loc_180057952
0x180057949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005794e  test    al, al
0x180057950  jmp     short loc_18005795A
0x180057952  call    cs:__imp_IsDebuggerPresent
0x180057958  test    eax, eax
0x18005795a  jz      short loc_180057962
0x18005795c  test    byte ptr [rbx+4], 2
0x180057960  jz      short loc_180057986
0x180057962  mov     rax, cs:g_pfnResultLoggingCallback
0x180057969  test    rax, rax
0x18005796c  jz      short loc_1800579CA
0x18005796e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180057975  jnz     short loc_1800579CA
0x180057977  xor     r8d, r8d
0x18005797a  xor     edx, edx
0x18005797c  mov     rcx, rbx
0x18005797f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057984  jmp     short loc_1800579CA
0x180057986  mov     ebp, 800h
0x18005798b  mov     rax, cs:g_pfnResultLoggingCallback
0x180057992  test    rax, rax
0x180057995  jz      short loc_1800579AE
0x180057997  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005799e  jnz     short loc_1800579AE
0x1800579a0  mov     r8d, ebp
0x1800579a3  mov     rdx, rsi
0x1800579a6  mov     rcx, rbx
0x1800579a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800579ae  cmp     [rsi], di
0x1800579b1  jnz     short loc_1800579C1
0x1800579b3  mov     r8, rbx; unsigned __int64
0x1800579b6  mov     rdx, rbp; unsigned __int16 *
0x1800579b9  mov     rcx, rsi; this
0x1800579bc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800579c1  mov     rcx, rsi; lpOutputString
0x1800579c4  call    cs:__imp_OutputDebugStringW
0x1800579ca  test    byte ptr [rbx+4], 4
0x1800579ce  jnz     short loc_1800579D9
0x1800579d0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800579d7  jz      short loc_1800579EB
0x1800579d9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800579e0  test    rax, rax
0x1800579e3  jz      short loc_1800579EB
0x1800579e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800579ea  nop
0x1800579eb  mov     rbx, [rsp+78h+arg_10]
0x1800579f3  add     rsp, 40h
0x1800579f7  pop     r15
0x1800579f9  pop     r14
0x1800579fb  pop     r13
0x1800579fd  pop     r12
0x1800579ff  pop     rdi
0x180057a00  pop     rsi
0x180057a01  pop     rbp
0x180057a02  retn
0x180057a03  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
