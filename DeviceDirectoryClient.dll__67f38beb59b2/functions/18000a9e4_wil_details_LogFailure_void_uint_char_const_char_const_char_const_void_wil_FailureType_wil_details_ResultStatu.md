# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000a9e4`
- end: `0x18000acdd`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180007e7c`
- `0x1800081e8`
- `0x180013e24`

## callees

- `0x180007db4`
- `0x180009b84`
- `0x18000a3e8`
- `0x18000a9e4`
- `0x18000b854`
- `0x18000b870`
- `0x18000b9f4`
- `0x18000ba10`
- `0x18000e4a4`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ab07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ab07`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000ac26`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000ac26`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ac98`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ac98`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x18000a9e4  mov     [rsp+arg_10], rbx
0x18000a9e9  mov     [rsp+arg_8], edx
0x18000a9ed  mov     [rsp+arg_0], rcx
0x18000a9f2  push    rbp
0x18000a9f3  push    rsi
0x18000a9f4  push    rdi
0x18000a9f5  push    r12
0x18000a9f7  push    r13
0x18000a9f9  push    r14
0x18000a9fb  push    r15
0x18000a9fd  sub     rsp, 40h
0x18000aa01  mov     r12, r9
0x18000aa04  mov     r13, r8
0x18000aa07  mov     r10, rcx
0x18000aa0a  xor     eax, eax
0x18000aa0c  mov     rsi, [rsp+78h+lpOutputString]
0x18000aa14  mov     [rsi], ax
0x18000aa17  mov     rax, [rsp+78h+arg_60]
0x18000aa1f  mov     byte ptr [rax], 0
0x18000aa22  mov     r14, [rsp+78h+arg_38]
0x18000aa2a  mov     edi, [r14]
0x18000aa2d  mov     rbx, [rsp+78h+arg_78]
0x18000aa35  mov     [rbx+8], edi
0x18000aa38  mov     eax, [r14+4]
0x18000aa3c  mov     [rbx+0Ch], eax
0x18000aa3f  xor     ebp, ebp
0x18000aa41  mov     r15d, [rsp+78h+arg_30]
0x18000aa49  mov     ecx, r15d
0x18000aa4c  test    r15d, r15d
0x18000aa4f  jz      short loc_18000AAB7
0x18000aa51  sub     ecx, 1
0x18000aa54  jz      short loc_18000AAAE
0x18000aa56  sub     ecx, 1
0x18000aa59  jz      short loc_18000AA69
0x18000aa5b  cmp     ecx, 1
0x18000aa5e  jnz     short loc_18000AAC0
0x18000aa60  mov     ecx, edi; this
0x18000aa62  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000aa67  jmp     short loc_18000AABE
0x18000aa69  test    edi, edi
0x18000aa6b  js      short loc_18000AAA5
0x18000aa6d  mov     edi, 8007029Ch
0x18000aa72  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000aa76  mov     rax, [rsp+78h+arg_28]
0x18000aa7e  mov     [rsp+78h+var_50], rax; __int64
0x18000aa83  mov     rax, [rsp+78h+arg_20]
0x18000aa8b  mov     [rsp+78h+var_58], rax; __int64
0x18000aa90  mov     rcx, r10; int
0x18000aa93  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000aa98  mov     [rbx+8], edi
0x18000aa9b  mov     ecx, edi; this
0x18000aa9d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000aaa2  mov     [rbx+0Ch], eax
0x18000aaa5  mov     ecx, edi; this
0x18000aaa7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000aaac  jmp     short loc_18000AABE
0x18000aaae  mov     ecx, edi; this
0x18000aab0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000aab5  jmp     short loc_18000AABE
0x18000aab7  mov     ecx, edi; this
0x18000aab9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000aabe  mov     ebp, eax
0x18000aac0  mov     [rbx], r15d
0x18000aac3  mov     eax, [rsp+78h+arg_70]
0x18000aaca  mov     [rbx+4], eax
0x18000aacd  cmp     dword ptr [r14+8], 1
0x18000aad2  jnz     short loc_18000AADA
0x18000aad4  or      eax, 8
0x18000aad7  mov     [rbx+4], eax
0x18000aada  mov     eax, 1
0x18000aadf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000aae7  inc     eax
0x18000aae9  mov     [rbx+10h], eax
0x18000aaec  mov     rax, [rsp+78h+arg_40]
0x18000aaf4  xor     edi, edi
0x18000aaf6  test    rax, rax
0x18000aaf9  jz      short loc_18000AB00
0x18000aafb  cmp     [rax], di
0x18000aafe  jnz     short loc_18000AB03
0x18000ab00  mov     rax, rdi
0x18000ab03  mov     [rbx+18h], rax
0x18000ab07  call    cs:__imp_GetCurrentThreadId
0x18000ab0d  mov     [rbx+20h], eax
0x18000ab10  mov     [rbx+38h], r13
0x18000ab14  mov     eax, [rsp+78h+arg_8]
0x18000ab1b  mov     [rbx+40h], eax
0x18000ab1e  mov     [rbx+44h], ebp
0x18000ab21  mov     rax, [rsp+78h+arg_20]
0x18000ab29  mov     [rbx+28h], rax
0x18000ab2d  mov     [rbx+30h], r12
0x18000ab31  mov     rax, [rsp+78h+arg_28]
0x18000ab39  mov     [rbx+88h], rax
0x18000ab40  mov     rax, [rsp+78h+arg_0]
0x18000ab48  mov     [rbx+90h], rax
0x18000ab4f  mov     [rbx+48h], rdi
0x18000ab53  xorps   xmm0, xmm0
0x18000ab56  xor     eax, eax
0x18000ab58  movups  xmmword ptr [rbx+68h], xmm0
0x18000ab5c  mov     [rbx+78h], rax
0x18000ab60  movups  xmmword ptr [rbx+50h], xmm0
0x18000ab64  mov     [rbx+60h], rax
0x18000ab68  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000ab6f  test    rax, rax
0x18000ab72  jz      short loc_18000AB7B
0x18000ab74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab79  jmp     short loc_18000AB7E
0x18000ab7b  mov     rax, rdi
0x18000ab7e  mov     [rbx+80h], rax
0x18000ab85  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000ab8c  test    rax, rax
0x18000ab8f  jz      short loc_18000AB99
0x18000ab91  mov     rcx, rbx
0x18000ab94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab99  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000aba0  test    rax, rax
0x18000aba3  jz      short loc_18000ABBB
0x18000aba5  mov     r8d, 400h
0x18000abab  mov     rdx, [rsp+78h+arg_60]
0x18000abb3  mov     rcx, rbx
0x18000abb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abbb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000abc2  test    rax, rax
0x18000abc5  jz      short loc_18000ABCF
0x18000abc7  mov     rcx, rbx
0x18000abca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abcf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000abd6  test    rax, rax
0x18000abd9  jz      short loc_18000ABE9
0x18000abdb  test    byte ptr [rbx+4], 2
0x18000abdf  jnz     short loc_18000ABE9
0x18000abe1  mov     rcx, rbx
0x18000abe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abe9  cmp     [rbx+8], edi
0x18000abec  jl      short loc_18000AC08
0x18000abee  cmp     r15d, 3
0x18000abf2  jnz     loc_18000ACD7
0x18000abf8  mov     ecx, 8000FFFFh; this
0x18000abfd  mov     [rbx+8], ecx
0x18000ac00  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ac05  mov     [rbx+0Ch], eax
0x18000ac08  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000ac0f  jnz     short loc_18000AC30
0x18000ac11  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000ac18  test    rax, rax
0x18000ac1b  jz      short loc_18000AC26
0x18000ac1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac22  test    al, al
0x18000ac24  jmp     short loc_18000AC2E
0x18000ac26  call    cs:__imp_IsDebuggerPresent
0x18000ac2c  test    eax, eax
0x18000ac2e  jz      short loc_18000AC36
0x18000ac30  test    byte ptr [rbx+4], 2
0x18000ac34  jz      short loc_18000AC5A
0x18000ac36  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ac3d  test    rax, rax
0x18000ac40  jz      short loc_18000AC9E
0x18000ac42  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000ac49  jnz     short loc_18000AC9E
0x18000ac4b  xor     r8d, r8d
0x18000ac4e  xor     edx, edx
0x18000ac50  mov     rcx, rbx
0x18000ac53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac58  jmp     short loc_18000AC9E
0x18000ac5a  mov     ebp, 800h
0x18000ac5f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ac66  test    rax, rax
0x18000ac69  jz      short loc_18000AC82
0x18000ac6b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000ac72  jnz     short loc_18000AC82
0x18000ac74  mov     r8d, ebp
0x18000ac77  mov     rdx, rsi
0x18000ac7a  mov     rcx, rbx
0x18000ac7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac82  cmp     [rsi], di
0x18000ac85  jnz     short loc_18000AC95
0x18000ac87  mov     r8, rbx; unsigned __int64
0x18000ac8a  mov     rdx, rbp; unsigned __int16 *
0x18000ac8d  mov     rcx, rsi; this
0x18000ac90  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000ac95  mov     rcx, rsi; lpOutputString
0x18000ac98  call    cs:__imp_OutputDebugStringW
0x18000ac9e  test    byte ptr [rbx+4], 4
0x18000aca2  jnz     short loc_18000ACAD
0x18000aca4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000acab  jz      short loc_18000ACBF
0x18000acad  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000acb4  test    rax, rax
0x18000acb7  jz      short loc_18000ACBF
0x18000acb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acbe  nop
0x18000acbf  mov     rbx, [rsp+78h+arg_10]
0x18000acc7  add     rsp, 40h
0x18000accb  pop     r15
0x18000accd  pop     r14
0x18000accf  pop     r13
0x18000acd1  pop     r12
0x18000acd3  pop     rdi
0x18000acd4  pop     rsi
0x18000acd5  pop     rbp
0x18000acd6  retn
0x18000acd7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
