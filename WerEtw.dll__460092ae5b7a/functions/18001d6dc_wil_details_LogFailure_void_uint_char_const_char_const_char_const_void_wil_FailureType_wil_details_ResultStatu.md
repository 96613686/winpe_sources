# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001d6dc`
- end: `0x18001d9d5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18001a2a0`

## callees

- `0x180019cdc`
- `0x18001cc84`
- `0x18001d420`
- `0x18001d6dc`
- `0x18001e508`
- `0x18001e530`
- `0x18001e544`
- `0x18001e560`
- `0x18001f8ec`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d7ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001d7ff`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001d91e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001d91e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d990`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001d990`

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
0x18001d6dc  mov     [rsp+arg_10], rbx
0x18001d6e1  mov     [rsp+arg_8], edx
0x18001d6e5  mov     [rsp+arg_0], rcx
0x18001d6ea  push    rbp
0x18001d6eb  push    rsi
0x18001d6ec  push    rdi
0x18001d6ed  push    r12
0x18001d6ef  push    r13
0x18001d6f1  push    r14
0x18001d6f3  push    r15
0x18001d6f5  sub     rsp, 40h
0x18001d6f9  mov     r12, r9
0x18001d6fc  mov     r13, r8
0x18001d6ff  mov     r10, rcx
0x18001d702  xor     eax, eax
0x18001d704  mov     rsi, [rsp+78h+lpOutputString]
0x18001d70c  mov     [rsi], ax
0x18001d70f  mov     rax, [rsp+78h+arg_60]
0x18001d717  mov     byte ptr [rax], 0
0x18001d71a  mov     r14, [rsp+78h+arg_38]
0x18001d722  mov     edi, [r14]
0x18001d725  mov     rbx, [rsp+78h+arg_78]
0x18001d72d  mov     [rbx+8], edi
0x18001d730  mov     eax, [r14+4]
0x18001d734  mov     [rbx+0Ch], eax
0x18001d737  xor     ebp, ebp
0x18001d739  mov     r15d, [rsp+78h+arg_30]
0x18001d741  mov     ecx, r15d
0x18001d744  test    r15d, r15d
0x18001d747  jz      short loc_18001D7AF
0x18001d749  sub     ecx, 1
0x18001d74c  jz      short loc_18001D7A6
0x18001d74e  sub     ecx, 1
0x18001d751  jz      short loc_18001D761
0x18001d753  cmp     ecx, 1
0x18001d756  jnz     short loc_18001D7B8
0x18001d758  mov     ecx, edi; this
0x18001d75a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001d75f  jmp     short loc_18001D7B6
0x18001d761  test    edi, edi
0x18001d763  js      short loc_18001D79D
0x18001d765  mov     edi, 8007029Ch
0x18001d76a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001d76e  mov     rax, [rsp+78h+arg_28]
0x18001d776  mov     [rsp+78h+var_50], rax; __int64
0x18001d77b  mov     rax, [rsp+78h+arg_20]
0x18001d783  mov     [rsp+78h+var_58], rax; __int64
0x18001d788  mov     rcx, r10; int
0x18001d78b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001d790  mov     [rbx+8], edi
0x18001d793  mov     ecx, edi; this
0x18001d795  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001d79a  mov     [rbx+0Ch], eax
0x18001d79d  mov     ecx, edi; this
0x18001d79f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001d7a4  jmp     short loc_18001D7B6
0x18001d7a6  mov     ecx, edi; this
0x18001d7a8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001d7ad  jmp     short loc_18001D7B6
0x18001d7af  mov     ecx, edi; this
0x18001d7b1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001d7b6  mov     ebp, eax
0x18001d7b8  mov     [rbx], r15d
0x18001d7bb  mov     eax, [rsp+78h+arg_70]
0x18001d7c2  mov     [rbx+4], eax
0x18001d7c5  cmp     dword ptr [r14+8], 1
0x18001d7ca  jnz     short loc_18001D7D2
0x18001d7cc  or      eax, 8
0x18001d7cf  mov     [rbx+4], eax
0x18001d7d2  mov     eax, 1
0x18001d7d7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001d7df  inc     eax
0x18001d7e1  mov     [rbx+10h], eax
0x18001d7e4  mov     rax, [rsp+78h+arg_40]
0x18001d7ec  xor     edi, edi
0x18001d7ee  test    rax, rax
0x18001d7f1  jz      short loc_18001D7F8
0x18001d7f3  cmp     [rax], di
0x18001d7f6  jnz     short loc_18001D7FB
0x18001d7f8  mov     rax, rdi
0x18001d7fb  mov     [rbx+18h], rax
0x18001d7ff  call    cs:__imp_GetCurrentThreadId
0x18001d805  mov     [rbx+20h], eax
0x18001d808  mov     [rbx+38h], r13
0x18001d80c  mov     eax, [rsp+78h+arg_8]
0x18001d813  mov     [rbx+40h], eax
0x18001d816  mov     [rbx+44h], ebp
0x18001d819  mov     rax, [rsp+78h+arg_20]
0x18001d821  mov     [rbx+28h], rax
0x18001d825  mov     [rbx+30h], r12
0x18001d829  mov     rax, [rsp+78h+arg_28]
0x18001d831  mov     [rbx+88h], rax
0x18001d838  mov     rax, [rsp+78h+arg_0]
0x18001d840  mov     [rbx+90h], rax
0x18001d847  mov     [rbx+48h], rdi
0x18001d84b  xorps   xmm0, xmm0
0x18001d84e  xor     eax, eax
0x18001d850  movups  xmmword ptr [rbx+68h], xmm0
0x18001d854  mov     [rbx+78h], rax
0x18001d858  movups  xmmword ptr [rbx+50h], xmm0
0x18001d85c  mov     [rbx+60h], rax
0x18001d860  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001d867  test    rax, rax
0x18001d86a  jz      short loc_18001D873
0x18001d86c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d871  jmp     short loc_18001D876
0x18001d873  mov     rax, rdi
0x18001d876  mov     [rbx+80h], rax
0x18001d87d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001d884  test    rax, rax
0x18001d887  jz      short loc_18001D891
0x18001d889  mov     rcx, rbx
0x18001d88c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d891  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001d898  test    rax, rax
0x18001d89b  jz      short loc_18001D8B3
0x18001d89d  mov     r8d, 400h
0x18001d8a3  mov     rdx, [rsp+78h+arg_60]
0x18001d8ab  mov     rcx, rbx
0x18001d8ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8b3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001d8ba  test    rax, rax
0x18001d8bd  jz      short loc_18001D8C7
0x18001d8bf  mov     rcx, rbx
0x18001d8c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8c7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001d8ce  test    rax, rax
0x18001d8d1  jz      short loc_18001D8E1
0x18001d8d3  test    byte ptr [rbx+4], 2
0x18001d8d7  jnz     short loc_18001D8E1
0x18001d8d9  mov     rcx, rbx
0x18001d8dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d8e1  cmp     [rbx+8], edi
0x18001d8e4  jl      short loc_18001D900
0x18001d8e6  cmp     r15d, 3
0x18001d8ea  jnz     loc_18001D9CF
0x18001d8f0  mov     ecx, 8000FFFFh; this
0x18001d8f5  mov     [rbx+8], ecx
0x18001d8f8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001d8fd  mov     [rbx+0Ch], eax
0x18001d900  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001d907  jnz     short loc_18001D928
0x18001d909  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001d910  test    rax, rax
0x18001d913  jz      short loc_18001D91E
0x18001d915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d91a  test    al, al
0x18001d91c  jmp     short loc_18001D926
0x18001d91e  call    cs:__imp_IsDebuggerPresent
0x18001d924  test    eax, eax
0x18001d926  jz      short loc_18001D92E
0x18001d928  test    byte ptr [rbx+4], 2
0x18001d92c  jz      short loc_18001D952
0x18001d92e  mov     rax, cs:g_pfnResultLoggingCallback
0x18001d935  test    rax, rax
0x18001d938  jz      short loc_18001D996
0x18001d93a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001d941  jnz     short loc_18001D996
0x18001d943  xor     r8d, r8d
0x18001d946  xor     edx, edx
0x18001d948  mov     rcx, rbx
0x18001d94b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d950  jmp     short loc_18001D996
0x18001d952  mov     ebp, 800h
0x18001d957  mov     rax, cs:g_pfnResultLoggingCallback
0x18001d95e  test    rax, rax
0x18001d961  jz      short loc_18001D97A
0x18001d963  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001d96a  jnz     short loc_18001D97A
0x18001d96c  mov     r8d, ebp
0x18001d96f  mov     rdx, rsi
0x18001d972  mov     rcx, rbx
0x18001d975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d97a  cmp     [rsi], di
0x18001d97d  jnz     short loc_18001D98D
0x18001d97f  mov     r8, rbx; unsigned __int64
0x18001d982  mov     rdx, rbp; unsigned __int16 *
0x18001d985  mov     rcx, rsi; this
0x18001d988  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001d98d  mov     rcx, rsi; lpOutputString
0x18001d990  call    cs:__imp_OutputDebugStringW
0x18001d996  test    byte ptr [rbx+4], 4
0x18001d99a  jnz     short loc_18001D9A5
0x18001d99c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001d9a3  jz      short loc_18001D9B7
0x18001d9a5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001d9ac  test    rax, rax
0x18001d9af  jz      short loc_18001D9B7
0x18001d9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9b6  nop
0x18001d9b7  mov     rbx, [rsp+78h+arg_10]
0x18001d9bf  add     rsp, 40h
0x18001d9c3  pop     r15
0x18001d9c5  pop     r14
0x18001d9c7  pop     r13
0x18001d9c9  pop     r12
0x18001d9cb  pop     rdi
0x18001d9cc  pop     rsi
0x18001d9cd  pop     rbp
0x18001d9ce  retn
0x18001d9cf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
