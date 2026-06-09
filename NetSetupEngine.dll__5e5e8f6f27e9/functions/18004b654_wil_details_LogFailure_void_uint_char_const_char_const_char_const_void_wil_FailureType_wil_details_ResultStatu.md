# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18004b654`
- end: `0x18004b951`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `765`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18004b564`
- `0x180065afc`
- `0x180065bac`
- `0x18007e714`

## callees

- `0x180046354`
- `0x18004b654`
- `0x18004b960`
- `0x18005cbf8`
- `0x180065a50`
- `0x180066968`
- `0x180066984`
- `0x1800669a0`
- `0x180066e3c`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b77f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004b77f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004b8a0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004b8a0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004b912`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004b912`

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
  wil::details *v28; // [rsp+30h] [rbp-58h]

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x18004b654  mov     rax, rsp
0x18004b657  mov     [rax+10h], edx
0x18004b65a  mov     [rax+8], rcx
0x18004b65e  push    rbp
0x18004b65f  push    rsi
0x18004b660  push    rdi
0x18004b661  push    r12
0x18004b663  push    r13
0x18004b665  push    r14
0x18004b667  push    r15
0x18004b669  sub     rsp, 50h
0x18004b66d  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18004b675  mov     [rax+18h], rbx
0x18004b679  mov     r12, r9
0x18004b67c  mov     r13, r8
0x18004b67f  mov     r10, rcx
0x18004b682  xor     eax, eax
0x18004b684  mov     rsi, [rsp+88h+lpOutputString]
0x18004b68c  mov     [rsi], ax
0x18004b68f  mov     rax, [rsp+88h+arg_60]
0x18004b697  mov     byte ptr [rax], 0
0x18004b69a  mov     r14, [rsp+88h+arg_38]
0x18004b6a2  mov     edi, [r14]
0x18004b6a5  mov     rbx, [rsp+88h+arg_78]
0x18004b6ad  mov     [rbx+8], edi
0x18004b6b0  mov     eax, [r14+4]
0x18004b6b4  mov     [rbx+0Ch], eax
0x18004b6b7  xor     ebp, ebp
0x18004b6b9  mov     r15d, [rsp+88h+arg_30]
0x18004b6c1  mov     ecx, r15d
0x18004b6c4  test    r15d, r15d
0x18004b6c7  jz      short loc_18004B72F
0x18004b6c9  sub     ecx, 1
0x18004b6cc  jz      short loc_18004B726
0x18004b6ce  sub     ecx, 1
0x18004b6d1  jz      short loc_18004B6E1
0x18004b6d3  cmp     ecx, 1
0x18004b6d6  jnz     short loc_18004B738
0x18004b6d8  mov     ecx, edi; this
0x18004b6da  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18004b6df  jmp     short loc_18004B736
0x18004b6e1  test    edi, edi
0x18004b6e3  js      short loc_18004B71D
0x18004b6e5  mov     edi, 8007029Ch
0x18004b6ea  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x18004b6ee  mov     rax, [rsp+88h+arg_28]
0x18004b6f6  mov     [rsp+88h+var_60], rax; __int64
0x18004b6fb  mov     rax, [rsp+88h+arg_20]
0x18004b703  mov     [rsp+88h+var_68], rax; __int64
0x18004b708  mov     rcx, r10; int
0x18004b70b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18004b710  mov     [rbx+8], edi
0x18004b713  mov     ecx, edi; this
0x18004b715  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004b71a  mov     [rbx+0Ch], eax
0x18004b71d  mov     ecx, edi; this
0x18004b71f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18004b724  jmp     short loc_18004B736
0x18004b726  mov     ecx, edi; this
0x18004b728  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18004b72d  jmp     short loc_18004B736
0x18004b72f  mov     ecx, edi; this
0x18004b731  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18004b736  mov     ebp, eax
0x18004b738  mov     [rbx], r15d
0x18004b73b  mov     eax, [rsp+88h+arg_70]
0x18004b742  mov     [rbx+4], eax
0x18004b745  cmp     dword ptr [r14+8], 1
0x18004b74a  jnz     short loc_18004B752
0x18004b74c  or      eax, 8
0x18004b74f  mov     [rbx+4], eax
0x18004b752  mov     eax, 1
0x18004b757  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18004b75f  inc     eax
0x18004b761  mov     [rbx+10h], eax
0x18004b764  mov     rax, [rsp+88h+arg_40]
0x18004b76c  xor     edi, edi
0x18004b76e  test    rax, rax
0x18004b771  jz      short loc_18004B778
0x18004b773  cmp     [rax], di
0x18004b776  jnz     short loc_18004B77B
0x18004b778  mov     rax, rdi
0x18004b77b  mov     [rbx+18h], rax
0x18004b77f  call    cs:__imp_GetCurrentThreadId
0x18004b785  mov     [rbx+20h], eax
0x18004b788  mov     [rbx+38h], r13
0x18004b78c  mov     eax, [rsp+88h+arg_8]
0x18004b793  mov     [rbx+40h], eax
0x18004b796  mov     [rbx+44h], ebp
0x18004b799  mov     rax, [rsp+88h+arg_20]
0x18004b7a1  mov     [rbx+28h], rax
0x18004b7a5  mov     [rbx+30h], r12
0x18004b7a9  mov     rax, [rsp+88h+arg_28]
0x18004b7b1  mov     [rbx+88h], rax
0x18004b7b8  mov     rax, [rsp+88h+arg_0]
0x18004b7c0  mov     [rbx+90h], rax
0x18004b7c7  mov     [rbx+48h], rdi
0x18004b7cb  xorps   xmm0, xmm0
0x18004b7ce  xor     eax, eax
0x18004b7d0  movups  xmmword ptr [rbx+68h], xmm0
0x18004b7d4  mov     [rbx+78h], rax
0x18004b7d8  movups  xmmword ptr [rbx+50h], xmm0
0x18004b7dc  mov     [rbx+60h], rax
0x18004b7e0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18004b7e7  test    rax, rax
0x18004b7ea  jz      short loc_18004B7F3
0x18004b7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b7f1  jmp     short loc_18004B7F6
0x18004b7f3  mov     rax, rdi
0x18004b7f6  mov     [rbx+80h], rax
0x18004b7fd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18004b804  test    rax, rax
0x18004b807  jz      short loc_18004B811
0x18004b809  mov     rcx, rbx
0x18004b80c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b811  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18004b818  test    rax, rax
0x18004b81b  jz      short loc_18004B833
0x18004b81d  mov     r8d, 400h
0x18004b823  mov     rdx, [rsp+88h+arg_60]
0x18004b82b  mov     rcx, rbx
0x18004b82e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b833  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004b83a  test    rax, rax
0x18004b83d  jz      short loc_18004B847
0x18004b83f  mov     rcx, rbx
0x18004b842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b847  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004b84e  test    rax, rax
0x18004b851  jz      short loc_18004B861
0x18004b853  test    byte ptr [rbx+4], 2
0x18004b857  jnz     short loc_18004B861
0x18004b859  mov     rcx, rbx
0x18004b85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b861  cmp     [rbx+8], edi
0x18004b864  jl      short loc_18004B882
0x18004b866  cmp     r15d, 3
0x18004b86a  jz      short loc_18004B872
0x18004b86c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18004b872  mov     ecx, 8000FFFFh; this
0x18004b877  mov     [rbx+8], ecx
0x18004b87a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004b87f  mov     [rbx+0Ch], eax
0x18004b882  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18004b889  jnz     short loc_18004B8AA
0x18004b88b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18004b892  test    rax, rax
0x18004b895  jz      short loc_18004B8A0
0x18004b897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b89c  test    al, al
0x18004b89e  jmp     short loc_18004B8A8
0x18004b8a0  call    cs:__imp_IsDebuggerPresent
0x18004b8a6  test    eax, eax
0x18004b8a8  jz      short loc_18004B8B0
0x18004b8aa  test    byte ptr [rbx+4], 2
0x18004b8ae  jz      short loc_18004B8D4
0x18004b8b0  mov     rax, cs:g_pfnResultLoggingCallback
0x18004b8b7  test    rax, rax
0x18004b8ba  jz      short loc_18004B918
0x18004b8bc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18004b8c3  jnz     short loc_18004B918
0x18004b8c5  xor     r8d, r8d
0x18004b8c8  xor     edx, edx
0x18004b8ca  mov     rcx, rbx
0x18004b8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b8d2  jmp     short loc_18004B918
0x18004b8d4  mov     ebp, 800h
0x18004b8d9  mov     rax, cs:g_pfnResultLoggingCallback
0x18004b8e0  test    rax, rax
0x18004b8e3  jz      short loc_18004B8FC
0x18004b8e5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18004b8ec  jnz     short loc_18004B8FC
0x18004b8ee  mov     r8d, ebp
0x18004b8f1  mov     rdx, rsi
0x18004b8f4  mov     rcx, rbx
0x18004b8f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b8fc  cmp     [rsi], di
0x18004b8ff  jnz     short loc_18004B90F
0x18004b901  mov     r8, rbx; unsigned __int64
0x18004b904  mov     rdx, rbp; wchar_t *
0x18004b907  mov     rcx, rsi; this
0x18004b90a  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18004b90f  mov     rcx, rsi; lpOutputString
0x18004b912  call    cs:__imp_OutputDebugStringW
0x18004b918  test    byte ptr [rbx+4], 4
0x18004b91c  jnz     short loc_18004B927
0x18004b91e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18004b925  jz      short loc_18004B939
0x18004b927  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18004b92e  test    rax, rax
0x18004b931  jz      short loc_18004B939
0x18004b933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b938  nop
0x18004b939  mov     rbx, [rsp+88h+arg_10]
0x18004b941  add     rsp, 50h
0x18004b945  pop     r15
0x18004b947  pop     r14
0x18004b949  pop     r13
0x18004b94b  pop     r12
0x18004b94d  pop     rdi
0x18004b94e  pop     rsi
0x18004b94f  pop     rbp
0x18004b950  retn
```
