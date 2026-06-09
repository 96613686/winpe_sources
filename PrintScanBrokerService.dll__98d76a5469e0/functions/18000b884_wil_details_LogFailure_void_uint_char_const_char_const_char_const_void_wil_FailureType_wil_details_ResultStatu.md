# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000b884`
- end: `0x18000bb7d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800057cc`
- `0x18000588c`
- `0x180005c44`

## callees

- `0x180005704`
- `0x18000a324`
- `0x18000b0d0`
- `0x18000b884`
- `0x18000cb54`
- `0x18000cb70`
- `0x18000ccf4`
- `0x18000cd10`
- `0x18000f7dc`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b9a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b9a7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bb38`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000bb38`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bac6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000bac6`

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
0x18000b884  mov     [rsp+arg_10], rbx
0x18000b889  mov     [rsp+arg_8], edx
0x18000b88d  mov     [rsp+arg_0], rcx
0x18000b892  push    rbp
0x18000b893  push    rsi
0x18000b894  push    rdi
0x18000b895  push    r12
0x18000b897  push    r13
0x18000b899  push    r14
0x18000b89b  push    r15
0x18000b89d  sub     rsp, 40h
0x18000b8a1  mov     r12, r9
0x18000b8a4  mov     r13, r8
0x18000b8a7  mov     r10, rcx
0x18000b8aa  xor     eax, eax
0x18000b8ac  mov     rsi, [rsp+78h+lpOutputString]
0x18000b8b4  mov     [rsi], ax
0x18000b8b7  mov     rax, [rsp+78h+arg_60]
0x18000b8bf  mov     byte ptr [rax], 0
0x18000b8c2  mov     r14, [rsp+78h+arg_38]
0x18000b8ca  mov     edi, [r14]
0x18000b8cd  mov     rbx, [rsp+78h+arg_78]
0x18000b8d5  mov     [rbx+8], edi
0x18000b8d8  mov     eax, [r14+4]
0x18000b8dc  mov     [rbx+0Ch], eax
0x18000b8df  xor     ebp, ebp
0x18000b8e1  mov     r15d, [rsp+78h+arg_30]
0x18000b8e9  mov     ecx, r15d
0x18000b8ec  test    r15d, r15d
0x18000b8ef  jz      short loc_18000B957
0x18000b8f1  sub     ecx, 1
0x18000b8f4  jz      short loc_18000B94E
0x18000b8f6  sub     ecx, 1
0x18000b8f9  jz      short loc_18000B909
0x18000b8fb  cmp     ecx, 1
0x18000b8fe  jnz     short loc_18000B960
0x18000b900  mov     ecx, edi; this
0x18000b902  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000b907  jmp     short loc_18000B95E
0x18000b909  test    edi, edi
0x18000b90b  js      short loc_18000B945
0x18000b90d  mov     edi, 8007029Ch
0x18000b912  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000b916  mov     rax, [rsp+78h+arg_28]
0x18000b91e  mov     [rsp+78h+var_50], rax; __int64
0x18000b923  mov     rax, [rsp+78h+arg_20]
0x18000b92b  mov     [rsp+78h+var_58], rax; __int64
0x18000b930  mov     rcx, r10; int
0x18000b933  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000b938  mov     [rbx+8], edi
0x18000b93b  mov     ecx, edi; this
0x18000b93d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000b942  mov     [rbx+0Ch], eax
0x18000b945  mov     ecx, edi; this
0x18000b947  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000b94c  jmp     short loc_18000B95E
0x18000b94e  mov     ecx, edi; this
0x18000b950  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000b955  jmp     short loc_18000B95E
0x18000b957  mov     ecx, edi; this
0x18000b959  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000b95e  mov     ebp, eax
0x18000b960  mov     [rbx], r15d
0x18000b963  mov     eax, [rsp+78h+arg_70]
0x18000b96a  mov     [rbx+4], eax
0x18000b96d  cmp     dword ptr [r14+8], 1
0x18000b972  jnz     short loc_18000B97A
0x18000b974  or      eax, 8
0x18000b977  mov     [rbx+4], eax
0x18000b97a  mov     eax, 1
0x18000b97f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000b987  inc     eax
0x18000b989  mov     [rbx+10h], eax
0x18000b98c  mov     rax, [rsp+78h+arg_40]
0x18000b994  xor     edi, edi
0x18000b996  test    rax, rax
0x18000b999  jz      short loc_18000B9A0
0x18000b99b  cmp     [rax], di
0x18000b99e  jnz     short loc_18000B9A3
0x18000b9a0  mov     rax, rdi
0x18000b9a3  mov     [rbx+18h], rax
0x18000b9a7  call    cs:__imp_GetCurrentThreadId
0x18000b9ad  mov     [rbx+20h], eax
0x18000b9b0  mov     [rbx+38h], r13
0x18000b9b4  mov     eax, [rsp+78h+arg_8]
0x18000b9bb  mov     [rbx+40h], eax
0x18000b9be  mov     [rbx+44h], ebp
0x18000b9c1  mov     rax, [rsp+78h+arg_20]
0x18000b9c9  mov     [rbx+28h], rax
0x18000b9cd  mov     [rbx+30h], r12
0x18000b9d1  mov     rax, [rsp+78h+arg_28]
0x18000b9d9  mov     [rbx+88h], rax
0x18000b9e0  mov     rax, [rsp+78h+arg_0]
0x18000b9e8  mov     [rbx+90h], rax
0x18000b9ef  mov     [rbx+48h], rdi
0x18000b9f3  xorps   xmm0, xmm0
0x18000b9f6  xor     eax, eax
0x18000b9f8  movups  xmmword ptr [rbx+68h], xmm0
0x18000b9fc  mov     [rbx+78h], rax
0x18000ba00  movups  xmmword ptr [rbx+50h], xmm0
0x18000ba04  mov     [rbx+60h], rax
0x18000ba08  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000ba0f  test    rax, rax
0x18000ba12  jz      short loc_18000BA1B
0x18000ba14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba19  jmp     short loc_18000BA1E
0x18000ba1b  mov     rax, rdi
0x18000ba1e  mov     [rbx+80h], rax
0x18000ba25  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000ba2c  test    rax, rax
0x18000ba2f  jz      short loc_18000BA39
0x18000ba31  mov     rcx, rbx
0x18000ba34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba39  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000ba40  test    rax, rax
0x18000ba43  jz      short loc_18000BA5B
0x18000ba45  mov     r8d, 400h
0x18000ba4b  mov     rdx, [rsp+78h+arg_60]
0x18000ba53  mov     rcx, rbx
0x18000ba56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba5b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ba62  test    rax, rax
0x18000ba65  jz      short loc_18000BA6F
0x18000ba67  mov     rcx, rbx
0x18000ba6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba6f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ba76  test    rax, rax
0x18000ba79  jz      short loc_18000BA89
0x18000ba7b  test    byte ptr [rbx+4], 2
0x18000ba7f  jnz     short loc_18000BA89
0x18000ba81  mov     rcx, rbx
0x18000ba84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba89  cmp     [rbx+8], edi
0x18000ba8c  jl      short loc_18000BAA8
0x18000ba8e  cmp     r15d, 3
0x18000ba92  jnz     loc_18000BB77
0x18000ba98  mov     ecx, 8000FFFFh; this
0x18000ba9d  mov     [rbx+8], ecx
0x18000baa0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000baa5  mov     [rbx+0Ch], eax
0x18000baa8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000baaf  jnz     short loc_18000BAD0
0x18000bab1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000bab8  test    rax, rax
0x18000babb  jz      short loc_18000BAC6
0x18000babd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bac2  test    al, al
0x18000bac4  jmp     short loc_18000BACE
0x18000bac6  call    cs:__imp_IsDebuggerPresent
0x18000bacc  test    eax, eax
0x18000bace  jz      short loc_18000BAD6
0x18000bad0  test    byte ptr [rbx+4], 2
0x18000bad4  jz      short loc_18000BAFA
0x18000bad6  mov     rax, cs:g_pfnResultLoggingCallback
0x18000badd  test    rax, rax
0x18000bae0  jz      short loc_18000BB3E
0x18000bae2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000bae9  jnz     short loc_18000BB3E
0x18000baeb  xor     r8d, r8d
0x18000baee  xor     edx, edx
0x18000baf0  mov     rcx, rbx
0x18000baf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baf8  jmp     short loc_18000BB3E
0x18000bafa  mov     ebp, 800h
0x18000baff  mov     rax, cs:g_pfnResultLoggingCallback
0x18000bb06  test    rax, rax
0x18000bb09  jz      short loc_18000BB22
0x18000bb0b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000bb12  jnz     short loc_18000BB22
0x18000bb14  mov     r8d, ebp
0x18000bb17  mov     rdx, rsi
0x18000bb1a  mov     rcx, rbx
0x18000bb1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb22  cmp     [rsi], di
0x18000bb25  jnz     short loc_18000BB35
0x18000bb27  mov     r8, rbx; unsigned __int64
0x18000bb2a  mov     rdx, rbp; unsigned __int16 *
0x18000bb2d  mov     rcx, rsi; this
0x18000bb30  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000bb35  mov     rcx, rsi; lpOutputString
0x18000bb38  call    cs:__imp_OutputDebugStringW
0x18000bb3e  test    byte ptr [rbx+4], 4
0x18000bb42  jnz     short loc_18000BB4D
0x18000bb44  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000bb4b  jz      short loc_18000BB5F
0x18000bb4d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000bb54  test    rax, rax
0x18000bb57  jz      short loc_18000BB5F
0x18000bb59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb5e  nop
0x18000bb5f  mov     rbx, [rsp+78h+arg_10]
0x18000bb67  add     rsp, 40h
0x18000bb6b  pop     r15
0x18000bb6d  pop     r14
0x18000bb6f  pop     r13
0x18000bb71  pop     r12
0x18000bb73  pop     rdi
0x18000bb74  pop     rsi
0x18000bb75  pop     rbp
0x18000bb76  retn
0x18000bb77  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
