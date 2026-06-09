# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000eac0`
- end: `0x18000edb8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000c0dc`

## callees

- `0x18000a684`
- `0x18000aa6c`
- `0x18000add0`
- `0x18000bb20`
- `0x18000eac0`
- `0x18000ee64`
- `0x18000ee80`
- `0x18000ee9c`
- `0x18000f6e0`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ebe3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ebe3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ed74`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ed74`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000ed02`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000ed02`

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
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

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
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x18000eac0  mov     [rsp+arg_10], rbx
0x18000eac5  mov     [rsp+arg_8], edx
0x18000eac9  mov     [rsp+arg_0], rcx
0x18000eace  push    rbp
0x18000eacf  push    rsi
0x18000ead0  push    rdi
0x18000ead1  push    r12
0x18000ead3  push    r13
0x18000ead5  push    r14
0x18000ead7  push    r15
0x18000ead9  sub     rsp, 40h
0x18000eadd  mov     r14, [rsp+78h+arg_38]
0x18000eae5  xor     eax, eax
0x18000eae7  mov     rbx, [rsp+78h+arg_78]
0x18000eaef  xor     ebp, ebp
0x18000eaf1  mov     r15d, [rsp+78h+arg_30]
0x18000eaf9  mov     r10, rcx
0x18000eafc  mov     rsi, [rsp+78h+lpOutputString]
0x18000eb04  mov     r12, r9
0x18000eb07  mov     r13, r8
0x18000eb0a  mov     ecx, r15d
0x18000eb0d  mov     [rsi], ax
0x18000eb10  mov     rax, [rsp+78h+arg_60]
0x18000eb18  mov     byte ptr [rax], 0
0x18000eb1b  mov     edi, [r14]
0x18000eb1e  mov     [rbx+8], edi
0x18000eb21  mov     eax, [r14+4]
0x18000eb25  mov     [rbx+0Ch], eax
0x18000eb28  test    r15d, r15d
0x18000eb2b  jz      short loc_18000EB93
0x18000eb2d  sub     ecx, 1
0x18000eb30  jz      short loc_18000EB8A
0x18000eb32  sub     ecx, 1
0x18000eb35  jz      short loc_18000EB45
0x18000eb37  cmp     ecx, 1
0x18000eb3a  jnz     short loc_18000EB9C
0x18000eb3c  mov     ecx, edi; this
0x18000eb3e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000eb43  jmp     short loc_18000EB9A
0x18000eb45  test    edi, edi
0x18000eb47  js      short loc_18000EB81
0x18000eb49  mov     rax, [rsp+78h+arg_28]
0x18000eb51  mov     edi, 8007029Ch
0x18000eb56  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000eb5a  mov     rcx, r10; int
0x18000eb5d  mov     [rsp+78h+var_50], rax; __int64
0x18000eb62  mov     rax, [rsp+78h+arg_20]
0x18000eb6a  mov     [rsp+78h+var_58], rax; __int64
0x18000eb6f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000eb74  mov     ecx, edi; this
0x18000eb76  mov     [rbx+8], edi
0x18000eb79  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000eb7e  mov     [rbx+0Ch], eax
0x18000eb81  mov     ecx, edi; this
0x18000eb83  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000eb88  jmp     short loc_18000EB9A
0x18000eb8a  mov     ecx, edi; this
0x18000eb8c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000eb91  jmp     short loc_18000EB9A
0x18000eb93  mov     ecx, edi; this
0x18000eb95  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000eb9a  mov     ebp, eax
0x18000eb9c  mov     eax, [rsp+78h+arg_70]
0x18000eba3  mov     [rbx+4], eax
0x18000eba6  mov     [rbx], r15d
0x18000eba9  cmp     dword ptr [r14+8], 1
0x18000ebae  jnz     short loc_18000EBB6
0x18000ebb0  or      eax, 8
0x18000ebb3  mov     [rbx+4], eax
0x18000ebb6  mov     eax, 1
0x18000ebbb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ebc3  inc     eax
0x18000ebc5  xor     edi, edi
0x18000ebc7  mov     [rbx+10h], eax
0x18000ebca  mov     rax, [rsp+78h+arg_40]
0x18000ebd2  test    rax, rax
0x18000ebd5  jz      short loc_18000EBDC
0x18000ebd7  cmp     [rax], di
0x18000ebda  jnz     short loc_18000EBDF
0x18000ebdc  mov     rax, rdi
0x18000ebdf  mov     [rbx+18h], rax
0x18000ebe3  call    cs:__imp_GetCurrentThreadId
0x18000ebe9  mov     [rbx+38h], r13
0x18000ebed  xorps   xmm0, xmm0
0x18000ebf0  mov     [rbx+20h], eax
0x18000ebf3  mov     eax, [rsp+78h+arg_8]
0x18000ebfa  mov     [rbx+40h], eax
0x18000ebfd  mov     rax, [rsp+78h+arg_20]
0x18000ec05  mov     [rbx+28h], rax
0x18000ec09  mov     rax, [rsp+78h+arg_28]
0x18000ec11  mov     [rbx+88h], rax
0x18000ec18  mov     rax, [rsp+78h+arg_0]
0x18000ec20  mov     [rbx+90h], rax
0x18000ec27  xor     eax, eax
0x18000ec29  mov     [rbx+44h], ebp
0x18000ec2c  mov     [rbx+30h], r12
0x18000ec30  mov     [rbx+48h], rdi
0x18000ec34  movups  xmmword ptr [rbx+68h], xmm0
0x18000ec38  mov     [rbx+78h], rax
0x18000ec3c  movups  xmmword ptr [rbx+50h], xmm0
0x18000ec40  mov     [rbx+60h], rax
0x18000ec44  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000ec4b  test    rax, rax
0x18000ec4e  jz      short loc_18000EC57
0x18000ec50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec55  jmp     short loc_18000EC5A
0x18000ec57  mov     rax, rdi
0x18000ec5a  mov     [rbx+80h], rax
0x18000ec61  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000ec68  test    rax, rax
0x18000ec6b  jz      short loc_18000EC75
0x18000ec6d  mov     rcx, rbx
0x18000ec70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec75  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000ec7c  test    rax, rax
0x18000ec7f  jz      short loc_18000EC97
0x18000ec81  mov     rdx, [rsp+78h+arg_60]
0x18000ec89  mov     r8d, 400h
0x18000ec8f  mov     rcx, rbx
0x18000ec92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec97  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ec9e  test    rax, rax
0x18000eca1  jz      short loc_18000ECAB
0x18000eca3  mov     rcx, rbx
0x18000eca6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecab  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ecb2  test    rax, rax
0x18000ecb5  jz      short loc_18000ECC5
0x18000ecb7  test    byte ptr [rbx+4], 2
0x18000ecbb  jnz     short loc_18000ECC5
0x18000ecbd  mov     rcx, rbx
0x18000ecc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecc5  cmp     [rbx+8], edi
0x18000ecc8  jl      short loc_18000ECE4
0x18000ecca  cmp     r15d, 3
0x18000ecce  jnz     loc_18000EDB2
0x18000ecd4  mov     ecx, 8000FFFFh; this
0x18000ecd9  mov     [rbx+8], ecx
0x18000ecdc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ece1  mov     [rbx+0Ch], eax
0x18000ece4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000eceb  jnz     short loc_18000ED0C
0x18000eced  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000ecf4  test    rax, rax
0x18000ecf7  jz      short loc_18000ED02
0x18000ecf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecfe  test    al, al
0x18000ed00  jmp     short loc_18000ED0A
0x18000ed02  call    cs:__imp_IsDebuggerPresent
0x18000ed08  test    eax, eax
0x18000ed0a  jz      short loc_18000ED12
0x18000ed0c  test    byte ptr [rbx+4], 2
0x18000ed10  jz      short loc_18000ED36
0x18000ed12  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ed19  test    rax, rax
0x18000ed1c  jz      short loc_18000ED7A
0x18000ed1e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000ed25  jnz     short loc_18000ED7A
0x18000ed27  xor     r8d, r8d
0x18000ed2a  xor     edx, edx
0x18000ed2c  mov     rcx, rbx
0x18000ed2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed34  jmp     short loc_18000ED7A
0x18000ed36  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ed3d  mov     ebp, 800h
0x18000ed42  test    rax, rax
0x18000ed45  jz      short loc_18000ED5E
0x18000ed47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000ed4e  jnz     short loc_18000ED5E
0x18000ed50  mov     r8d, ebp
0x18000ed53  mov     rdx, rsi
0x18000ed56  mov     rcx, rbx
0x18000ed59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed5e  cmp     [rsi], di
0x18000ed61  jnz     short loc_18000ED71
0x18000ed63  mov     r8, rbx; unsigned __int64
0x18000ed66  mov     rdx, rbp; unsigned __int16 *
0x18000ed69  mov     rcx, rsi; this
0x18000ed6c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000ed71  mov     rcx, rsi; lpOutputString
0x18000ed74  call    cs:__imp_OutputDebugStringW
0x18000ed7a  test    byte ptr [rbx+4], 4
0x18000ed7e  jnz     short loc_18000ED89
0x18000ed80  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000ed87  jz      short loc_18000ED9A
0x18000ed89  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000ed90  test    rax, rax
0x18000ed93  jz      short loc_18000ED9A
0x18000ed95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed9a  mov     rbx, [rsp+78h+arg_10]
0x18000eda2  add     rsp, 40h
0x18000eda6  pop     r15
0x18000eda8  pop     r14
0x18000edaa  pop     r13
0x18000edac  pop     r12
0x18000edae  pop     rdi
0x18000edaf  pop     rsi
0x18000edb0  pop     rbp
0x18000edb1  retn
0x18000edb2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
