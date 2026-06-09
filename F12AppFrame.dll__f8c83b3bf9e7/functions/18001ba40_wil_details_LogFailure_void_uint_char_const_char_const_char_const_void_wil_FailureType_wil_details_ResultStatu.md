# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001ba40`
- end: `0x18001bd39`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800185c4`

## callees

- `0x180018008`
- `0x180019f4c`
- `0x18001a674`
- `0x18001ba40`
- `0x18001c1e0`
- `0x18001c200`
- `0x18001c214`
- `0x18001c230`
- `0x18001e14c`
- `0x180035010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001bb63`
- `KERNEL32!GetCurrentThreadId` at `0x18001bb63`
- `KERNEL32!IsDebuggerPresent` at `0x18001bc82`
- `KERNEL32!IsDebuggerPresent` at `0x18001bc82`
- `KERNEL32!OutputDebugStringW` at `0x18001bcf4`
- `KERNEL32!OutputDebugStringW` at `0x18001bcf4`

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
0x18001ba40  mov     [rsp+arg_10], rbx
0x18001ba45  mov     [rsp+arg_8], edx
0x18001ba49  mov     [rsp+arg_0], rcx
0x18001ba4e  push    rbp
0x18001ba4f  push    rsi
0x18001ba50  push    rdi
0x18001ba51  push    r12
0x18001ba53  push    r13
0x18001ba55  push    r14
0x18001ba57  push    r15
0x18001ba59  sub     rsp, 40h
0x18001ba5d  mov     r12, r9
0x18001ba60  mov     r13, r8
0x18001ba63  mov     r10, rcx
0x18001ba66  xor     eax, eax
0x18001ba68  mov     rsi, [rsp+78h+lpOutputString]
0x18001ba70  mov     [rsi], ax
0x18001ba73  mov     rax, [rsp+78h+arg_60]
0x18001ba7b  mov     byte ptr [rax], 0
0x18001ba7e  mov     r14, [rsp+78h+arg_38]
0x18001ba86  mov     edi, [r14]
0x18001ba89  mov     rbx, [rsp+78h+arg_78]
0x18001ba91  mov     [rbx+8], edi
0x18001ba94  mov     eax, [r14+4]
0x18001ba98  mov     [rbx+0Ch], eax
0x18001ba9b  xor     ebp, ebp
0x18001ba9d  mov     r15d, [rsp+78h+arg_30]
0x18001baa5  mov     ecx, r15d
0x18001baa8  test    r15d, r15d
0x18001baab  jz      short loc_18001BB13
0x18001baad  sub     ecx, 1
0x18001bab0  jz      short loc_18001BB0A
0x18001bab2  sub     ecx, 1
0x18001bab5  jz      short loc_18001BAC5
0x18001bab7  cmp     ecx, 1
0x18001baba  jnz     short loc_18001BB1C
0x18001babc  mov     ecx, edi; this
0x18001babe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001bac3  jmp     short loc_18001BB1A
0x18001bac5  test    edi, edi
0x18001bac7  js      short loc_18001BB01
0x18001bac9  mov     edi, 8007029Ch
0x18001bace  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001bad2  mov     rax, [rsp+78h+arg_28]
0x18001bada  mov     [rsp+78h+var_50], rax; __int64
0x18001badf  mov     rax, [rsp+78h+arg_20]
0x18001bae7  mov     [rsp+78h+var_58], rax; __int64
0x18001baec  mov     rcx, r10; int
0x18001baef  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001baf4  mov     [rbx+8], edi
0x18001baf7  mov     ecx, edi; this
0x18001baf9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001bafe  mov     [rbx+0Ch], eax
0x18001bb01  mov     ecx, edi; this
0x18001bb03  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001bb08  jmp     short loc_18001BB1A
0x18001bb0a  mov     ecx, edi; this
0x18001bb0c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001bb11  jmp     short loc_18001BB1A
0x18001bb13  mov     ecx, edi; this
0x18001bb15  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001bb1a  mov     ebp, eax
0x18001bb1c  mov     [rbx], r15d
0x18001bb1f  mov     eax, [rsp+78h+arg_70]
0x18001bb26  mov     [rbx+4], eax
0x18001bb29  cmp     dword ptr [r14+8], 1
0x18001bb2e  jnz     short loc_18001BB36
0x18001bb30  or      eax, 8
0x18001bb33  mov     [rbx+4], eax
0x18001bb36  mov     eax, 1
0x18001bb3b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001bb43  inc     eax
0x18001bb45  mov     [rbx+10h], eax
0x18001bb48  mov     rax, [rsp+78h+arg_40]
0x18001bb50  xor     edi, edi
0x18001bb52  test    rax, rax
0x18001bb55  jz      short loc_18001BB5C
0x18001bb57  cmp     [rax], di
0x18001bb5a  jnz     short loc_18001BB5F
0x18001bb5c  mov     rax, rdi
0x18001bb5f  mov     [rbx+18h], rax
0x18001bb63  call    cs:__imp_GetCurrentThreadId
0x18001bb69  mov     [rbx+20h], eax
0x18001bb6c  mov     [rbx+38h], r13
0x18001bb70  mov     eax, [rsp+78h+arg_8]
0x18001bb77  mov     [rbx+40h], eax
0x18001bb7a  mov     [rbx+44h], ebp
0x18001bb7d  mov     rax, [rsp+78h+arg_20]
0x18001bb85  mov     [rbx+28h], rax
0x18001bb89  mov     [rbx+30h], r12
0x18001bb8d  mov     rax, [rsp+78h+arg_28]
0x18001bb95  mov     [rbx+88h], rax
0x18001bb9c  mov     rax, [rsp+78h+arg_0]
0x18001bba4  mov     [rbx+90h], rax
0x18001bbab  mov     [rbx+48h], rdi
0x18001bbaf  xorps   xmm0, xmm0
0x18001bbb2  xor     eax, eax
0x18001bbb4  movups  xmmword ptr [rbx+68h], xmm0
0x18001bbb8  mov     [rbx+78h], rax
0x18001bbbc  movups  xmmword ptr [rbx+50h], xmm0
0x18001bbc0  mov     [rbx+60h], rax
0x18001bbc4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001bbcb  test    rax, rax
0x18001bbce  jz      short loc_18001BBD7
0x18001bbd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbd5  jmp     short loc_18001BBDA
0x18001bbd7  mov     rax, rdi
0x18001bbda  mov     [rbx+80h], rax
0x18001bbe1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001bbe8  test    rax, rax
0x18001bbeb  jz      short loc_18001BBF5
0x18001bbed  mov     rcx, rbx
0x18001bbf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bbf5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001bbfc  test    rax, rax
0x18001bbff  jz      short loc_18001BC17
0x18001bc01  mov     r8d, 400h
0x18001bc07  mov     rdx, [rsp+78h+arg_60]
0x18001bc0f  mov     rcx, rbx
0x18001bc12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc17  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001bc1e  test    rax, rax
0x18001bc21  jz      short loc_18001BC2B
0x18001bc23  mov     rcx, rbx
0x18001bc26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc2b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001bc32  test    rax, rax
0x18001bc35  jz      short loc_18001BC45
0x18001bc37  test    byte ptr [rbx+4], 2
0x18001bc3b  jnz     short loc_18001BC45
0x18001bc3d  mov     rcx, rbx
0x18001bc40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc45  cmp     [rbx+8], edi
0x18001bc48  jl      short loc_18001BC64
0x18001bc4a  cmp     r15d, 3
0x18001bc4e  jnz     loc_18001BD33
0x18001bc54  mov     ecx, 8000FFFFh; this
0x18001bc59  mov     [rbx+8], ecx
0x18001bc5c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001bc61  mov     [rbx+0Ch], eax
0x18001bc64  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001bc6b  jnz     short loc_18001BC8C
0x18001bc6d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001bc74  test    rax, rax
0x18001bc77  jz      short loc_18001BC82
0x18001bc79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bc7e  test    al, al
0x18001bc80  jmp     short loc_18001BC8A
0x18001bc82  call    cs:__imp_IsDebuggerPresent
0x18001bc88  test    eax, eax
0x18001bc8a  jz      short loc_18001BC92
0x18001bc8c  test    byte ptr [rbx+4], 2
0x18001bc90  jz      short loc_18001BCB6
0x18001bc92  mov     rax, cs:g_pfnResultLoggingCallback
0x18001bc99  test    rax, rax
0x18001bc9c  jz      short loc_18001BCFA
0x18001bc9e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001bca5  jnz     short loc_18001BCFA
0x18001bca7  xor     r8d, r8d
0x18001bcaa  xor     edx, edx
0x18001bcac  mov     rcx, rbx
0x18001bcaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcb4  jmp     short loc_18001BCFA
0x18001bcb6  mov     ebp, 800h
0x18001bcbb  mov     rax, cs:g_pfnResultLoggingCallback
0x18001bcc2  test    rax, rax
0x18001bcc5  jz      short loc_18001BCDE
0x18001bcc7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001bcce  jnz     short loc_18001BCDE
0x18001bcd0  mov     r8d, ebp
0x18001bcd3  mov     rdx, rsi
0x18001bcd6  mov     rcx, rbx
0x18001bcd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bcde  cmp     [rsi], di
0x18001bce1  jnz     short loc_18001BCF1
0x18001bce3  mov     r8, rbx; unsigned __int64
0x18001bce6  mov     rdx, rbp; unsigned __int16 *
0x18001bce9  mov     rcx, rsi; this
0x18001bcec  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001bcf1  mov     rcx, rsi; lpOutputString
0x18001bcf4  call    cs:__imp_OutputDebugStringW
0x18001bcfa  test    byte ptr [rbx+4], 4
0x18001bcfe  jnz     short loc_18001BD09
0x18001bd00  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001bd07  jz      short loc_18001BD1B
0x18001bd09  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001bd10  test    rax, rax
0x18001bd13  jz      short loc_18001BD1B
0x18001bd15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd1a  nop
0x18001bd1b  mov     rbx, [rsp+78h+arg_10]
0x18001bd23  add     rsp, 40h
0x18001bd27  pop     r15
0x18001bd29  pop     r14
0x18001bd2b  pop     r13
0x18001bd2d  pop     r12
0x18001bd2f  pop     rdi
0x18001bd30  pop     rsi
0x18001bd31  pop     rbp
0x18001bd32  retn
0x18001bd33  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
