# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800058b4`
- end: `0x180005bac`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002f88`

## callees

- `0x1800029c4`
- `0x180004e44`
- `0x1800055dc`
- `0x1800058b4`
- `0x1800063d8`
- `0x180006400`
- `0x180006528`
- `0x180006544`
- `0x180009474`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800059d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800059d7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005b68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005b68`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005af6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005af6`

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
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x1800058b4  mov     [rsp+arg_10], rbx
0x1800058b9  mov     [rsp+arg_8], edx
0x1800058bd  mov     [rsp+arg_0], rcx
0x1800058c2  push    rbp
0x1800058c3  push    rsi
0x1800058c4  push    rdi
0x1800058c5  push    r12
0x1800058c7  push    r13
0x1800058c9  push    r14
0x1800058cb  push    r15
0x1800058cd  sub     rsp, 40h
0x1800058d1  mov     r14, [rsp+78h+arg_38]
0x1800058d9  xor     eax, eax
0x1800058db  mov     rbx, [rsp+78h+arg_78]
0x1800058e3  xor     ebp, ebp
0x1800058e5  mov     r15d, [rsp+78h+arg_30]
0x1800058ed  mov     r10, rcx
0x1800058f0  mov     rsi, [rsp+78h+lpOutputString]
0x1800058f8  mov     r12, r9
0x1800058fb  mov     r13, r8
0x1800058fe  mov     ecx, r15d
0x180005901  mov     [rsi], ax
0x180005904  mov     rax, [rsp+78h+arg_60]
0x18000590c  mov     byte ptr [rax], 0
0x18000590f  mov     edi, [r14]
0x180005912  mov     [rbx+8], edi
0x180005915  mov     eax, [r14+4]
0x180005919  mov     [rbx+0Ch], eax
0x18000591c  test    r15d, r15d
0x18000591f  jz      short loc_180005987
0x180005921  sub     ecx, 1
0x180005924  jz      short loc_18000597E
0x180005926  sub     ecx, 1
0x180005929  jz      short loc_180005939
0x18000592b  cmp     ecx, 1
0x18000592e  jnz     short loc_180005990
0x180005930  mov     ecx, edi; this
0x180005932  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005937  jmp     short loc_18000598E
0x180005939  test    edi, edi
0x18000593b  js      short loc_180005975
0x18000593d  mov     rax, [rsp+78h+arg_28]
0x180005945  mov     edi, 8007029Ch
0x18000594a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000594e  mov     rcx, r10; int
0x180005951  mov     [rsp+78h+var_50], rax; __int64
0x180005956  mov     rax, [rsp+78h+arg_20]
0x18000595e  mov     [rsp+78h+var_58], rax; __int64
0x180005963  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005968  mov     ecx, edi; this
0x18000596a  mov     [rbx+8], edi
0x18000596d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005972  mov     [rbx+0Ch], eax
0x180005975  mov     ecx, edi; this
0x180005977  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000597c  jmp     short loc_18000598E
0x18000597e  mov     ecx, edi; this
0x180005980  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005985  jmp     short loc_18000598E
0x180005987  mov     ecx, edi; this
0x180005989  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000598e  mov     ebp, eax
0x180005990  mov     eax, [rsp+78h+arg_70]
0x180005997  mov     [rbx+4], eax
0x18000599a  mov     [rbx], r15d
0x18000599d  cmp     dword ptr [r14+8], 1
0x1800059a2  jnz     short loc_1800059AA
0x1800059a4  or      eax, 8
0x1800059a7  mov     [rbx+4], eax
0x1800059aa  mov     eax, 1
0x1800059af  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800059b7  inc     eax
0x1800059b9  xor     edi, edi
0x1800059bb  mov     [rbx+10h], eax
0x1800059be  mov     rax, [rsp+78h+arg_40]
0x1800059c6  test    rax, rax
0x1800059c9  jz      short loc_1800059D0
0x1800059cb  cmp     [rax], di
0x1800059ce  jnz     short loc_1800059D3
0x1800059d0  mov     rax, rdi
0x1800059d3  mov     [rbx+18h], rax
0x1800059d7  call    cs:__imp_GetCurrentThreadId
0x1800059dd  mov     [rbx+38h], r13
0x1800059e1  xorps   xmm0, xmm0
0x1800059e4  mov     [rbx+20h], eax
0x1800059e7  mov     eax, [rsp+78h+arg_8]
0x1800059ee  mov     [rbx+40h], eax
0x1800059f1  mov     rax, [rsp+78h+arg_20]
0x1800059f9  mov     [rbx+28h], rax
0x1800059fd  mov     rax, [rsp+78h+arg_28]
0x180005a05  mov     [rbx+88h], rax
0x180005a0c  mov     rax, [rsp+78h+arg_0]
0x180005a14  mov     [rbx+90h], rax
0x180005a1b  xor     eax, eax
0x180005a1d  mov     [rbx+44h], ebp
0x180005a20  mov     [rbx+30h], r12
0x180005a24  mov     [rbx+48h], rdi
0x180005a28  movups  xmmword ptr [rbx+68h], xmm0
0x180005a2c  mov     [rbx+78h], rax
0x180005a30  movups  xmmword ptr [rbx+50h], xmm0
0x180005a34  mov     [rbx+60h], rax
0x180005a38  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005a3f  test    rax, rax
0x180005a42  jz      short loc_180005A4B
0x180005a44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a49  jmp     short loc_180005A4E
0x180005a4b  mov     rax, rdi
0x180005a4e  mov     [rbx+80h], rax
0x180005a55  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005a5c  test    rax, rax
0x180005a5f  jz      short loc_180005A69
0x180005a61  mov     rcx, rbx
0x180005a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a69  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005a70  test    rax, rax
0x180005a73  jz      short loc_180005A8B
0x180005a75  mov     rdx, [rsp+78h+arg_60]
0x180005a7d  mov     r8d, 400h
0x180005a83  mov     rcx, rbx
0x180005a86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a8b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005a92  test    rax, rax
0x180005a95  jz      short loc_180005A9F
0x180005a97  mov     rcx, rbx
0x180005a9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a9f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005aa6  test    rax, rax
0x180005aa9  jz      short loc_180005AB9
0x180005aab  test    byte ptr [rbx+4], 2
0x180005aaf  jnz     short loc_180005AB9
0x180005ab1  mov     rcx, rbx
0x180005ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ab9  cmp     [rbx+8], edi
0x180005abc  jl      short loc_180005AD8
0x180005abe  cmp     r15d, 3
0x180005ac2  jnz     loc_180005BA6
0x180005ac8  mov     ecx, 8000FFFFh; this
0x180005acd  mov     [rbx+8], ecx
0x180005ad0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005ad5  mov     [rbx+0Ch], eax
0x180005ad8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005adf  jnz     short loc_180005B00
0x180005ae1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005ae8  test    rax, rax
0x180005aeb  jz      short loc_180005AF6
0x180005aed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af2  test    al, al
0x180005af4  jmp     short loc_180005AFE
0x180005af6  call    cs:__imp_IsDebuggerPresent
0x180005afc  test    eax, eax
0x180005afe  jz      short loc_180005B06
0x180005b00  test    byte ptr [rbx+4], 2
0x180005b04  jz      short loc_180005B2A
0x180005b06  mov     rax, cs:g_pfnResultLoggingCallback
0x180005b0d  test    rax, rax
0x180005b10  jz      short loc_180005B6E
0x180005b12  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005b19  jnz     short loc_180005B6E
0x180005b1b  xor     r8d, r8d
0x180005b1e  xor     edx, edx
0x180005b20  mov     rcx, rbx
0x180005b23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b28  jmp     short loc_180005B6E
0x180005b2a  mov     rax, cs:g_pfnResultLoggingCallback
0x180005b31  mov     ebp, 800h
0x180005b36  test    rax, rax
0x180005b39  jz      short loc_180005B52
0x180005b3b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005b42  jnz     short loc_180005B52
0x180005b44  mov     r8d, ebp
0x180005b47  mov     rdx, rsi
0x180005b4a  mov     rcx, rbx
0x180005b4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b52  cmp     [rsi], di
0x180005b55  jnz     short loc_180005B65
0x180005b57  mov     r8, rbx; unsigned __int64
0x180005b5a  mov     rdx, rbp; unsigned __int16 *
0x180005b5d  mov     rcx, rsi; this
0x180005b60  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005b65  mov     rcx, rsi; lpOutputString
0x180005b68  call    cs:__imp_OutputDebugStringW
0x180005b6e  test    byte ptr [rbx+4], 4
0x180005b72  jnz     short loc_180005B7D
0x180005b74  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005b7b  jz      short loc_180005B8E
0x180005b7d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005b84  test    rax, rax
0x180005b87  jz      short loc_180005B8E
0x180005b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b8e  mov     rbx, [rsp+78h+arg_10]
0x180005b96  add     rsp, 40h
0x180005b9a  pop     r15
0x180005b9c  pop     r14
0x180005b9e  pop     r13
0x180005ba0  pop     r12
0x180005ba2  pop     rdi
0x180005ba3  pop     rsi
0x180005ba4  pop     rbp
0x180005ba5  retn
0x180005ba6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
