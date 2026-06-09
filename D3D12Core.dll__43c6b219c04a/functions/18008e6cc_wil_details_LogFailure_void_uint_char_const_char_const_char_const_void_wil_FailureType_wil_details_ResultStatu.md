# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18008e6cc`
- end: `0x18008e9c1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18008e5d0`
- `0x1800c026c`
- `0x1800c032c`
- `0x18012914c`

## callees

- `0x180071d38`
- `0x18008e6cc`
- `0x18008e9d0`
- `0x1800c01b8`
- `0x1800c3fc4`
- `0x1800c54c4`
- `0x1800c54e0`
- `0x1800c54fc`
- `0x1800c6e8c`
- `0x180262020`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008e7ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008e7ef`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18008e910`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18008e910`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18008e982`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18008e982`

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
0x18008e6cc  mov     [rsp+arg_10], rbx
0x18008e6d1  mov     [rsp+arg_8], edx
0x18008e6d5  mov     [rsp+arg_0], rcx
0x18008e6da  push    rbp
0x18008e6db  push    rsi
0x18008e6dc  push    rdi
0x18008e6dd  push    r12
0x18008e6df  push    r13
0x18008e6e1  push    r14
0x18008e6e3  push    r15
0x18008e6e5  sub     rsp, 40h
0x18008e6e9  mov     r12, r9
0x18008e6ec  mov     r13, r8
0x18008e6ef  mov     r10, rcx
0x18008e6f2  xor     eax, eax
0x18008e6f4  mov     rsi, [rsp+78h+lpOutputString]
0x18008e6fc  mov     [rsi], ax
0x18008e6ff  mov     rax, [rsp+78h+arg_60]
0x18008e707  mov     byte ptr [rax], 0
0x18008e70a  mov     r14, [rsp+78h+arg_38]
0x18008e712  mov     edi, [r14]
0x18008e715  mov     rbx, [rsp+78h+arg_78]
0x18008e71d  mov     [rbx+8], edi
0x18008e720  mov     eax, [r14+4]
0x18008e724  mov     [rbx+0Ch], eax
0x18008e727  xor     ebp, ebp
0x18008e729  mov     r15d, [rsp+78h+arg_30]
0x18008e731  mov     ecx, r15d
0x18008e734  test    r15d, r15d
0x18008e737  jz      short loc_18008E79F
0x18008e739  sub     ecx, 1
0x18008e73c  jz      short loc_18008E796
0x18008e73e  sub     ecx, 1
0x18008e741  jz      short loc_18008E751
0x18008e743  cmp     ecx, 1
0x18008e746  jnz     short loc_18008E7A8
0x18008e748  mov     ecx, edi; this
0x18008e74a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18008e74f  jmp     short loc_18008E7A6
0x18008e751  test    edi, edi
0x18008e753  js      short loc_18008E78D
0x18008e755  mov     edi, 8007029Ch
0x18008e75a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18008e75e  mov     rax, [rsp+78h+arg_28]
0x18008e766  mov     [rsp+78h+var_50], rax; __int64
0x18008e76b  mov     rax, [rsp+78h+arg_20]
0x18008e773  mov     [rsp+78h+var_58], rax; __int64
0x18008e778  mov     rcx, r10; int
0x18008e77b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18008e780  mov     [rbx+8], edi
0x18008e783  mov     ecx, edi; this
0x18008e785  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18008e78a  mov     [rbx+0Ch], eax
0x18008e78d  mov     ecx, edi; this
0x18008e78f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18008e794  jmp     short loc_18008E7A6
0x18008e796  mov     ecx, edi; this
0x18008e798  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18008e79d  jmp     short loc_18008E7A6
0x18008e79f  mov     ecx, edi; this
0x18008e7a1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18008e7a6  mov     ebp, eax
0x18008e7a8  mov     [rbx], r15d
0x18008e7ab  mov     eax, [rsp+78h+arg_70]
0x18008e7b2  mov     [rbx+4], eax
0x18008e7b5  cmp     dword ptr [r14+8], 1
0x18008e7ba  jnz     short loc_18008E7C2
0x18008e7bc  or      eax, 8
0x18008e7bf  mov     [rbx+4], eax
0x18008e7c2  mov     eax, 1
0x18008e7c7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18008e7cf  inc     eax
0x18008e7d1  mov     [rbx+10h], eax
0x18008e7d4  mov     rax, [rsp+78h+arg_40]
0x18008e7dc  xor     edi, edi
0x18008e7de  test    rax, rax
0x18008e7e1  jz      short loc_18008E7E8
0x18008e7e3  cmp     [rax], di
0x18008e7e6  jnz     short loc_18008E7EB
0x18008e7e8  mov     rax, rdi
0x18008e7eb  mov     [rbx+18h], rax
0x18008e7ef  call    cs:__imp_GetCurrentThreadId
0x18008e7f5  mov     [rbx+20h], eax
0x18008e7f8  mov     [rbx+38h], r13
0x18008e7fc  mov     eax, [rsp+78h+arg_8]
0x18008e803  mov     [rbx+40h], eax
0x18008e806  mov     [rbx+44h], ebp
0x18008e809  mov     rax, [rsp+78h+arg_20]
0x18008e811  mov     [rbx+28h], rax
0x18008e815  mov     [rbx+30h], r12
0x18008e819  mov     rax, [rsp+78h+arg_28]
0x18008e821  mov     [rbx+88h], rax
0x18008e828  mov     rax, [rsp+78h+arg_0]
0x18008e830  mov     [rbx+90h], rax
0x18008e837  mov     [rbx+48h], rdi
0x18008e83b  xorps   xmm0, xmm0
0x18008e83e  xor     eax, eax
0x18008e840  movups  xmmword ptr [rbx+68h], xmm0
0x18008e844  mov     [rbx+78h], rax
0x18008e848  movups  xmmword ptr [rbx+50h], xmm0
0x18008e84c  mov     [rbx+60h], rax
0x18008e850  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18008e857  test    rax, rax
0x18008e85a  jz      short loc_18008E863
0x18008e85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e861  jmp     short loc_18008E866
0x18008e863  mov     rax, rdi
0x18008e866  mov     [rbx+80h], rax
0x18008e86d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18008e874  test    rax, rax
0x18008e877  jz      short loc_18008E881
0x18008e879  mov     rcx, rbx
0x18008e87c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e881  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18008e888  test    rax, rax
0x18008e88b  jz      short loc_18008E8A3
0x18008e88d  mov     r8d, 400h
0x18008e893  mov     rdx, [rsp+78h+arg_60]
0x18008e89b  mov     rcx, rbx
0x18008e89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e8a3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18008e8aa  test    rax, rax
0x18008e8ad  jz      short loc_18008E8B7
0x18008e8af  mov     rcx, rbx
0x18008e8b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e8b7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18008e8be  test    rax, rax
0x18008e8c1  jz      short loc_18008E8D1
0x18008e8c3  test    byte ptr [rbx+4], 2
0x18008e8c7  jnz     short loc_18008E8D1
0x18008e8c9  mov     rcx, rbx
0x18008e8cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e8d1  cmp     [rbx+8], edi
0x18008e8d4  jl      short loc_18008E8F2
0x18008e8d6  cmp     r15d, 3
0x18008e8da  jz      short loc_18008E8E2
0x18008e8dc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18008e8e2  mov     ecx, 8000FFFFh; this
0x18008e8e7  mov     [rbx+8], ecx
0x18008e8ea  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18008e8ef  mov     [rbx+0Ch], eax
0x18008e8f2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18008e8f9  jnz     short loc_18008E91A
0x18008e8fb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18008e902  test    rax, rax
0x18008e905  jz      short loc_18008E910
0x18008e907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e90c  test    al, al
0x18008e90e  jmp     short loc_18008E918
0x18008e910  call    cs:__imp_IsDebuggerPresent
0x18008e916  test    eax, eax
0x18008e918  jz      short loc_18008E920
0x18008e91a  test    byte ptr [rbx+4], 2
0x18008e91e  jz      short loc_18008E944
0x18008e920  mov     rax, cs:g_pfnResultLoggingCallback
0x18008e927  test    rax, rax
0x18008e92a  jz      short loc_18008E988
0x18008e92c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18008e933  jnz     short loc_18008E988
0x18008e935  xor     r8d, r8d
0x18008e938  xor     edx, edx
0x18008e93a  mov     rcx, rbx
0x18008e93d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e942  jmp     short loc_18008E988
0x18008e944  mov     ebp, 800h
0x18008e949  mov     rax, cs:g_pfnResultLoggingCallback
0x18008e950  test    rax, rax
0x18008e953  jz      short loc_18008E96C
0x18008e955  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18008e95c  jnz     short loc_18008E96C
0x18008e95e  mov     r8d, ebp
0x18008e961  mov     rdx, rsi
0x18008e964  mov     rcx, rbx
0x18008e967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e96c  cmp     [rsi], di
0x18008e96f  jnz     short loc_18008E97F
0x18008e971  mov     r8, rbx; unsigned __int64
0x18008e974  mov     rdx, rbp; unsigned __int16 *
0x18008e977  mov     rcx, rsi; this
0x18008e97a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18008e97f  mov     rcx, rsi; lpOutputString
0x18008e982  call    cs:__imp_OutputDebugStringW
0x18008e988  test    byte ptr [rbx+4], 4
0x18008e98c  jnz     short loc_18008E997
0x18008e98e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18008e995  jz      short loc_18008E9A9
0x18008e997  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18008e99e  test    rax, rax
0x18008e9a1  jz      short loc_18008E9A9
0x18008e9a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e9a8  nop
0x18008e9a9  mov     rbx, [rsp+78h+arg_10]
0x18008e9b1  add     rsp, 40h
0x18008e9b5  pop     r15
0x18008e9b7  pop     r14
0x18008e9b9  pop     r13
0x18008e9bb  pop     r12
0x18008e9bd  pop     rdi
0x18008e9be  pop     rsi
0x18008e9bf  pop     rbp
0x18008e9c0  retn
```
