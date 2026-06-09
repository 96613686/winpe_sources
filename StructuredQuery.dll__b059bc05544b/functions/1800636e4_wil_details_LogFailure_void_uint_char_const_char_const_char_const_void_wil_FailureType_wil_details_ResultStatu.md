# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800636e4`
- end: `0x1800639e1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `765`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18005fe74`
- `0x1800601e0`

## callees

- `0x180055f54`
- `0x18005a480`
- `0x18005fdac`
- `0x180062578`
- `0x1800636e4`
- `0x18006453c`
- `0x180064560`
- `0x1800646b0`
- `0x180066fc0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006380b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006380b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006392a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18006392a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18006399c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18006399c`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x1800636e4  mov     [rsp+arg_10], rbx
0x1800636e9  mov     [rsp+arg_8], edx
0x1800636ed  mov     [rsp+arg_0], rcx
0x1800636f2  push    rbp
0x1800636f3  push    rsi
0x1800636f4  push    rdi
0x1800636f5  push    r12
0x1800636f7  push    r13
0x1800636f9  push    r14
0x1800636fb  push    r15
0x1800636fd  sub     rsp, 40h
0x180063701  mov     r12, r9
0x180063704  mov     r13, r8
0x180063707  mov     r10, rcx
0x18006370a  xor     eax, eax
0x18006370c  mov     rsi, [rsp+78h+lpOutputString]
0x180063714  mov     [rsi], ax
0x180063717  mov     rax, [rsp+78h+arg_60]
0x18006371f  mov     byte ptr [rax], 0
0x180063722  mov     r14, [rsp+78h+arg_38]
0x18006372a  mov     edi, [r14]
0x18006372d  mov     rbx, [rsp+78h+arg_78]
0x180063735  mov     [rbx+8], edi
0x180063738  mov     eax, [r14+4]
0x18006373c  mov     [rbx+0Ch], eax
0x18006373f  xor     ebp, ebp
0x180063741  mov     r15d, [rsp+78h+arg_30]
0x180063749  mov     ecx, r15d
0x18006374c  test    r15d, r15d
0x18006374f  jz      short loc_1800637BB
0x180063751  sub     ecx, 1
0x180063754  jz      short loc_1800637B2
0x180063756  sub     ecx, 1
0x180063759  jz      short loc_180063769
0x18006375b  cmp     ecx, 1
0x18006375e  jnz     short loc_1800637C4
0x180063760  mov     ecx, edi; this
0x180063762  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180063767  jmp     short loc_1800637C2
0x180063769  test    edi, edi
0x18006376b  js      short loc_1800637A9
0x18006376d  mov     [rsp+78h+var_40], ebp
0x180063771  mov     edi, 8007029Ch
0x180063776  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18006377a  mov     rax, [rsp+78h+arg_28]
0x180063782  mov     [rsp+78h+var_50], rax; __int64
0x180063787  mov     rax, [rsp+78h+arg_20]
0x18006378f  mov     [rsp+78h+var_58], rax; __int64
0x180063794  mov     rcx, r10; int
0x180063797  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18006379c  mov     [rbx+8], edi
0x18006379f  mov     ecx, edi; this
0x1800637a1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800637a6  mov     [rbx+0Ch], eax
0x1800637a9  mov     ecx, edi; this
0x1800637ab  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800637b0  jmp     short loc_1800637C2
0x1800637b2  mov     ecx, edi; this
0x1800637b4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800637b9  jmp     short loc_1800637C2
0x1800637bb  mov     ecx, edi; this
0x1800637bd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800637c2  mov     ebp, eax
0x1800637c4  mov     [rbx], r15d
0x1800637c7  mov     eax, [rsp+78h+arg_70]
0x1800637ce  mov     [rbx+4], eax
0x1800637d1  cmp     dword ptr [r14+8], 1
0x1800637d6  jnz     short loc_1800637DE
0x1800637d8  or      eax, 8
0x1800637db  mov     [rbx+4], eax
0x1800637de  mov     eax, 1
0x1800637e3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800637eb  inc     eax
0x1800637ed  mov     [rbx+10h], eax
0x1800637f0  mov     rax, [rsp+78h+arg_40]
0x1800637f8  xor     edi, edi
0x1800637fa  test    rax, rax
0x1800637fd  jz      short loc_180063804
0x1800637ff  cmp     [rax], di
0x180063802  jnz     short loc_180063807
0x180063804  mov     rax, rdi
0x180063807  mov     [rbx+18h], rax
0x18006380b  call    cs:__imp_GetCurrentThreadId
0x180063811  mov     [rbx+20h], eax
0x180063814  mov     [rbx+38h], r13
0x180063818  mov     eax, [rsp+78h+arg_8]
0x18006381f  mov     [rbx+40h], eax
0x180063822  mov     [rbx+44h], ebp
0x180063825  mov     rax, [rsp+78h+arg_20]
0x18006382d  mov     [rbx+28h], rax
0x180063831  mov     [rbx+30h], r12
0x180063835  mov     rax, [rsp+78h+arg_28]
0x18006383d  mov     [rbx+88h], rax
0x180063844  mov     rax, [rsp+78h+arg_0]
0x18006384c  mov     [rbx+90h], rax
0x180063853  mov     [rbx+48h], rdi
0x180063857  xorps   xmm0, xmm0
0x18006385a  xor     eax, eax
0x18006385c  movups  xmmword ptr [rbx+68h], xmm0
0x180063860  mov     [rbx+78h], rax
0x180063864  movups  xmmword ptr [rbx+50h], xmm0
0x180063868  mov     [rbx+60h], rax
0x18006386c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180063873  test    rax, rax
0x180063876  jz      short loc_18006387F
0x180063878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006387d  jmp     short loc_180063882
0x18006387f  mov     rax, rdi
0x180063882  mov     [rbx+80h], rax
0x180063889  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180063890  test    rax, rax
0x180063893  jz      short loc_18006389D
0x180063895  mov     rcx, rbx
0x180063898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006389d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800638a4  test    rax, rax
0x1800638a7  jz      short loc_1800638BF
0x1800638a9  mov     r8d, 400h
0x1800638af  mov     rdx, [rsp+78h+arg_60]
0x1800638b7  mov     rcx, rbx
0x1800638ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800638bf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800638c6  test    rax, rax
0x1800638c9  jz      short loc_1800638D3
0x1800638cb  mov     rcx, rbx
0x1800638ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800638d3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800638da  test    rax, rax
0x1800638dd  jz      short loc_1800638ED
0x1800638df  test    byte ptr [rbx+4], 2
0x1800638e3  jnz     short loc_1800638ED
0x1800638e5  mov     rcx, rbx
0x1800638e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800638ed  cmp     [rbx+8], edi
0x1800638f0  jl      short loc_18006390C
0x1800638f2  cmp     r15d, 3
0x1800638f6  jnz     loc_1800639DB
0x1800638fc  mov     ecx, 8000FFFFh; this
0x180063901  mov     [rbx+8], ecx
0x180063904  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180063909  mov     [rbx+0Ch], eax
0x18006390c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180063913  jnz     short loc_180063934
0x180063915  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18006391c  test    rax, rax
0x18006391f  jz      short loc_18006392A
0x180063921  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063926  test    al, al
0x180063928  jmp     short loc_180063932
0x18006392a  call    cs:__imp_IsDebuggerPresent
0x180063930  test    eax, eax
0x180063932  jz      short loc_18006393A
0x180063934  test    byte ptr [rbx+4], 2
0x180063938  jz      short loc_18006395E
0x18006393a  mov     rax, cs:g_pfnResultLoggingCallback
0x180063941  test    rax, rax
0x180063944  jz      short loc_1800639A2
0x180063946  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18006394d  jnz     short loc_1800639A2
0x18006394f  xor     r8d, r8d
0x180063952  xor     edx, edx
0x180063954  mov     rcx, rbx
0x180063957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006395c  jmp     short loc_1800639A2
0x18006395e  mov     ebp, 800h
0x180063963  mov     rax, cs:g_pfnResultLoggingCallback
0x18006396a  test    rax, rax
0x18006396d  jz      short loc_180063986
0x18006396f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180063976  jnz     short loc_180063986
0x180063978  mov     r8d, ebp
0x18006397b  mov     rdx, rsi
0x18006397e  mov     rcx, rbx
0x180063981  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063986  cmp     [rsi], di
0x180063989  jnz     short loc_180063999
0x18006398b  mov     r8, rbx; unsigned __int64
0x18006398e  mov     rdx, rbp; wchar_t *
0x180063991  mov     rcx, rsi; this
0x180063994  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180063999  mov     rcx, rsi; lpOutputString
0x18006399c  call    cs:__imp_OutputDebugStringW
0x1800639a2  test    byte ptr [rbx+4], 4
0x1800639a6  jnz     short loc_1800639B1
0x1800639a8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800639af  jz      short loc_1800639C3
0x1800639b1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800639b8  test    rax, rax
0x1800639bb  jz      short loc_1800639C3
0x1800639bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800639c2  nop
0x1800639c3  mov     rbx, [rsp+78h+arg_10]
0x1800639cb  add     rsp, 40h
0x1800639cf  pop     r15
0x1800639d1  pop     r14
0x1800639d3  pop     r13
0x1800639d5  pop     r12
0x1800639d7  pop     rdi
0x1800639d8  pop     rsi
0x1800639d9  pop     rbp
0x1800639da  retn
0x1800639db  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
