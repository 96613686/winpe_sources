# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000cb14`
- end: `0x18000ce0d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800067fc`

## callees

- `0x180005f8c`
- `0x18000b994`
- `0x18000c13c`
- `0x18000cb14`
- `0x18000d9e8`
- `0x18000da10`
- `0x18000db3c`
- `0x18000db58`
- `0x1800108c4`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc37`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cd56`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cd56`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000cdc8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000cdc8`

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
0x18000cb14  mov     [rsp+arg_10], rbx
0x18000cb19  mov     [rsp+arg_8], edx
0x18000cb1d  mov     [rsp+arg_0], rcx
0x18000cb22  push    rbp
0x18000cb23  push    rsi
0x18000cb24  push    rdi
0x18000cb25  push    r12
0x18000cb27  push    r13
0x18000cb29  push    r14
0x18000cb2b  push    r15
0x18000cb2d  sub     rsp, 40h
0x18000cb31  mov     r12, r9
0x18000cb34  mov     r13, r8
0x18000cb37  mov     r10, rcx
0x18000cb3a  xor     eax, eax
0x18000cb3c  mov     rsi, [rsp+78h+lpOutputString]
0x18000cb44  mov     [rsi], ax
0x18000cb47  mov     rax, [rsp+78h+arg_60]
0x18000cb4f  mov     byte ptr [rax], 0
0x18000cb52  mov     r14, [rsp+78h+arg_38]
0x18000cb5a  mov     edi, [r14]
0x18000cb5d  mov     rbx, [rsp+78h+arg_78]
0x18000cb65  mov     [rbx+8], edi
0x18000cb68  mov     eax, [r14+4]
0x18000cb6c  mov     [rbx+0Ch], eax
0x18000cb6f  xor     ebp, ebp
0x18000cb71  mov     r15d, [rsp+78h+arg_30]
0x18000cb79  mov     ecx, r15d
0x18000cb7c  test    r15d, r15d
0x18000cb7f  jz      short loc_18000CBE7
0x18000cb81  sub     ecx, 1
0x18000cb84  jz      short loc_18000CBDE
0x18000cb86  sub     ecx, 1
0x18000cb89  jz      short loc_18000CB99
0x18000cb8b  cmp     ecx, 1
0x18000cb8e  jnz     short loc_18000CBF0
0x18000cb90  mov     ecx, edi; this
0x18000cb92  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000cb97  jmp     short loc_18000CBEE
0x18000cb99  test    edi, edi
0x18000cb9b  js      short loc_18000CBD5
0x18000cb9d  mov     edi, 8007029Ch
0x18000cba2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000cba6  mov     rax, [rsp+78h+arg_28]
0x18000cbae  mov     [rsp+78h+var_50], rax; __int64
0x18000cbb3  mov     rax, [rsp+78h+arg_20]
0x18000cbbb  mov     [rsp+78h+var_58], rax; __int64
0x18000cbc0  mov     rcx, r10; int
0x18000cbc3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000cbc8  mov     [rbx+8], edi
0x18000cbcb  mov     ecx, edi; this
0x18000cbcd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000cbd2  mov     [rbx+0Ch], eax
0x18000cbd5  mov     ecx, edi; this
0x18000cbd7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000cbdc  jmp     short loc_18000CBEE
0x18000cbde  mov     ecx, edi; this
0x18000cbe0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000cbe5  jmp     short loc_18000CBEE
0x18000cbe7  mov     ecx, edi; this
0x18000cbe9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000cbee  mov     ebp, eax
0x18000cbf0  mov     [rbx], r15d
0x18000cbf3  mov     eax, [rsp+78h+arg_70]
0x18000cbfa  mov     [rbx+4], eax
0x18000cbfd  cmp     dword ptr [r14+8], 1
0x18000cc02  jnz     short loc_18000CC0A
0x18000cc04  or      eax, 8
0x18000cc07  mov     [rbx+4], eax
0x18000cc0a  mov     eax, 1
0x18000cc0f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000cc17  inc     eax
0x18000cc19  mov     [rbx+10h], eax
0x18000cc1c  mov     rax, [rsp+78h+arg_40]
0x18000cc24  xor     edi, edi
0x18000cc26  test    rax, rax
0x18000cc29  jz      short loc_18000CC30
0x18000cc2b  cmp     [rax], di
0x18000cc2e  jnz     short loc_18000CC33
0x18000cc30  mov     rax, rdi
0x18000cc33  mov     [rbx+18h], rax
0x18000cc37  call    cs:__imp_GetCurrentThreadId
0x18000cc3d  mov     [rbx+20h], eax
0x18000cc40  mov     [rbx+38h], r13
0x18000cc44  mov     eax, [rsp+78h+arg_8]
0x18000cc4b  mov     [rbx+40h], eax
0x18000cc4e  mov     [rbx+44h], ebp
0x18000cc51  mov     rax, [rsp+78h+arg_20]
0x18000cc59  mov     [rbx+28h], rax
0x18000cc5d  mov     [rbx+30h], r12
0x18000cc61  mov     rax, [rsp+78h+arg_28]
0x18000cc69  mov     [rbx+88h], rax
0x18000cc70  mov     rax, [rsp+78h+arg_0]
0x18000cc78  mov     [rbx+90h], rax
0x18000cc7f  mov     [rbx+48h], rdi
0x18000cc83  xorps   xmm0, xmm0
0x18000cc86  xor     eax, eax
0x18000cc88  movups  xmmword ptr [rbx+68h], xmm0
0x18000cc8c  mov     [rbx+78h], rax
0x18000cc90  movups  xmmword ptr [rbx+50h], xmm0
0x18000cc94  mov     [rbx+60h], rax
0x18000cc98  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000cc9f  test    rax, rax
0x18000cca2  jz      short loc_18000CCAB
0x18000cca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cca9  jmp     short loc_18000CCAE
0x18000ccab  mov     rax, rdi
0x18000ccae  mov     [rbx+80h], rax
0x18000ccb5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000ccbc  test    rax, rax
0x18000ccbf  jz      short loc_18000CCC9
0x18000ccc1  mov     rcx, rbx
0x18000ccc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccc9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000ccd0  test    rax, rax
0x18000ccd3  jz      short loc_18000CCEB
0x18000ccd5  mov     r8d, 400h
0x18000ccdb  mov     rdx, [rsp+78h+arg_60]
0x18000cce3  mov     rcx, rbx
0x18000cce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cceb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ccf2  test    rax, rax
0x18000ccf5  jz      short loc_18000CCFF
0x18000ccf7  mov     rcx, rbx
0x18000ccfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccff  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cd06  test    rax, rax
0x18000cd09  jz      short loc_18000CD19
0x18000cd0b  test    byte ptr [rbx+4], 2
0x18000cd0f  jnz     short loc_18000CD19
0x18000cd11  mov     rcx, rbx
0x18000cd14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd19  cmp     [rbx+8], edi
0x18000cd1c  jl      short loc_18000CD38
0x18000cd1e  cmp     r15d, 3
0x18000cd22  jnz     loc_18000CE07
0x18000cd28  mov     ecx, 8000FFFFh; this
0x18000cd2d  mov     [rbx+8], ecx
0x18000cd30  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000cd35  mov     [rbx+0Ch], eax
0x18000cd38  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000cd3f  jnz     short loc_18000CD60
0x18000cd41  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000cd48  test    rax, rax
0x18000cd4b  jz      short loc_18000CD56
0x18000cd4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd52  test    al, al
0x18000cd54  jmp     short loc_18000CD5E
0x18000cd56  call    cs:__imp_IsDebuggerPresent
0x18000cd5c  test    eax, eax
0x18000cd5e  jz      short loc_18000CD66
0x18000cd60  test    byte ptr [rbx+4], 2
0x18000cd64  jz      short loc_18000CD8A
0x18000cd66  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cd6d  test    rax, rax
0x18000cd70  jz      short loc_18000CDCE
0x18000cd72  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000cd79  jnz     short loc_18000CDCE
0x18000cd7b  xor     r8d, r8d
0x18000cd7e  xor     edx, edx
0x18000cd80  mov     rcx, rbx
0x18000cd83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd88  jmp     short loc_18000CDCE
0x18000cd8a  mov     ebp, 800h
0x18000cd8f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cd96  test    rax, rax
0x18000cd99  jz      short loc_18000CDB2
0x18000cd9b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000cda2  jnz     short loc_18000CDB2
0x18000cda4  mov     r8d, ebp
0x18000cda7  mov     rdx, rsi
0x18000cdaa  mov     rcx, rbx
0x18000cdad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdb2  cmp     [rsi], di
0x18000cdb5  jnz     short loc_18000CDC5
0x18000cdb7  mov     r8, rbx; unsigned __int64
0x18000cdba  mov     rdx, rbp; unsigned __int16 *
0x18000cdbd  mov     rcx, rsi; this
0x18000cdc0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000cdc5  mov     rcx, rsi; lpOutputString
0x18000cdc8  call    cs:__imp_OutputDebugStringW
0x18000cdce  test    byte ptr [rbx+4], 4
0x18000cdd2  jnz     short loc_18000CDDD
0x18000cdd4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000cddb  jz      short loc_18000CDEF
0x18000cddd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000cde4  test    rax, rax
0x18000cde7  jz      short loc_18000CDEF
0x18000cde9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdee  nop
0x18000cdef  mov     rbx, [rsp+78h+arg_10]
0x18000cdf7  add     rsp, 40h
0x18000cdfb  pop     r15
0x18000cdfd  pop     r14
0x18000cdff  pop     r13
0x18000ce01  pop     r12
0x18000ce03  pop     rdi
0x18000ce04  pop     rsi
0x18000ce05  pop     rbp
0x18000ce06  retn
0x18000ce07  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
