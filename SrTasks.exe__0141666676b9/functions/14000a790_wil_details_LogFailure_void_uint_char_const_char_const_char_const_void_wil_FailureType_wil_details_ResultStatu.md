# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000a790`
- end: `0x14000aa88`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140008424`

## callees

- `0x140007e60`
- `0x140009e34`
- `0x14000a5cc`
- `0x14000a790`
- `0x14000b0d4`
- `0x14000b0f0`
- `0x14000b218`
- `0x14000b234`
- `0x14000cdac`
- `0x140011010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x14000aa44`
- `KERNEL32!OutputDebugStringW` at `0x14000aa44`
- `KERNEL32!IsDebuggerPresent` at `0x14000a9d2`
- `KERNEL32!IsDebuggerPresent` at `0x14000a9d2`
- `KERNEL32!GetCurrentThreadId` at `0x14000a8b3`
- `KERNEL32!GetCurrentThreadId` at `0x14000a8b3`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x14000a790  mov     [rsp+arg_10], rbx
0x14000a795  mov     [rsp+arg_8], edx
0x14000a799  mov     [rsp+arg_0], rcx
0x14000a79e  push    rbp
0x14000a79f  push    rsi
0x14000a7a0  push    rdi
0x14000a7a1  push    r12
0x14000a7a3  push    r13
0x14000a7a5  push    r14
0x14000a7a7  push    r15
0x14000a7a9  sub     rsp, 40h
0x14000a7ad  mov     r14, [rsp+78h+arg_38]
0x14000a7b5  xor     eax, eax
0x14000a7b7  mov     rbx, [rsp+78h+arg_78]
0x14000a7bf  xor     ebp, ebp
0x14000a7c1  mov     r15d, [rsp+78h+arg_30]
0x14000a7c9  mov     r10, rcx
0x14000a7cc  mov     rsi, [rsp+78h+lpOutputString]
0x14000a7d4  mov     r12, r9
0x14000a7d7  mov     r13, r8
0x14000a7da  mov     ecx, r15d
0x14000a7dd  mov     [rsi], ax
0x14000a7e0  mov     rax, [rsp+78h+arg_60]
0x14000a7e8  mov     byte ptr [rax], 0
0x14000a7eb  mov     edi, [r14]
0x14000a7ee  mov     [rbx+8], edi
0x14000a7f1  mov     eax, [r14+4]
0x14000a7f5  mov     [rbx+0Ch], eax
0x14000a7f8  test    r15d, r15d
0x14000a7fb  jz      short loc_14000A863
0x14000a7fd  sub     ecx, 1
0x14000a800  jz      short loc_14000A85A
0x14000a802  sub     ecx, 1
0x14000a805  jz      short loc_14000A815
0x14000a807  cmp     ecx, 1
0x14000a80a  jnz     short loc_14000A86C
0x14000a80c  mov     ecx, edi; this
0x14000a80e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000a813  jmp     short loc_14000A86A
0x14000a815  test    edi, edi
0x14000a817  js      short loc_14000A851
0x14000a819  mov     rax, [rsp+78h+arg_28]
0x14000a821  mov     edi, 8007029Ch
0x14000a826  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000a82a  mov     rcx, r10; int
0x14000a82d  mov     [rsp+78h+var_50], rax; __int64
0x14000a832  mov     rax, [rsp+78h+arg_20]
0x14000a83a  mov     [rsp+78h+var_58], rax; __int64
0x14000a83f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000a844  mov     ecx, edi; this
0x14000a846  mov     [rbx+8], edi
0x14000a849  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000a84e  mov     [rbx+0Ch], eax
0x14000a851  mov     ecx, edi; this
0x14000a853  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000a858  jmp     short loc_14000A86A
0x14000a85a  mov     ecx, edi; this
0x14000a85c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000a861  jmp     short loc_14000A86A
0x14000a863  mov     ecx, edi; this
0x14000a865  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000a86a  mov     ebp, eax
0x14000a86c  mov     eax, [rsp+78h+arg_70]
0x14000a873  mov     [rbx+4], eax
0x14000a876  mov     [rbx], r15d
0x14000a879  cmp     dword ptr [r14+8], 1
0x14000a87e  jnz     short loc_14000A886
0x14000a880  or      eax, 8
0x14000a883  mov     [rbx+4], eax
0x14000a886  mov     eax, 1
0x14000a88b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000a893  inc     eax
0x14000a895  xor     edi, edi
0x14000a897  mov     [rbx+10h], eax
0x14000a89a  mov     rax, [rsp+78h+arg_40]
0x14000a8a2  test    rax, rax
0x14000a8a5  jz      short loc_14000A8AC
0x14000a8a7  cmp     [rax], di
0x14000a8aa  jnz     short loc_14000A8AF
0x14000a8ac  mov     rax, rdi
0x14000a8af  mov     [rbx+18h], rax
0x14000a8b3  call    cs:__imp_GetCurrentThreadId
0x14000a8b9  mov     [rbx+38h], r13
0x14000a8bd  xorps   xmm0, xmm0
0x14000a8c0  mov     [rbx+20h], eax
0x14000a8c3  mov     eax, [rsp+78h+arg_8]
0x14000a8ca  mov     [rbx+40h], eax
0x14000a8cd  mov     rax, [rsp+78h+arg_20]
0x14000a8d5  mov     [rbx+28h], rax
0x14000a8d9  mov     rax, [rsp+78h+arg_28]
0x14000a8e1  mov     [rbx+88h], rax
0x14000a8e8  mov     rax, [rsp+78h+arg_0]
0x14000a8f0  mov     [rbx+90h], rax
0x14000a8f7  xor     eax, eax
0x14000a8f9  mov     [rbx+44h], ebp
0x14000a8fc  mov     [rbx+30h], r12
0x14000a900  mov     [rbx+48h], rdi
0x14000a904  movups  xmmword ptr [rbx+68h], xmm0
0x14000a908  mov     [rbx+78h], rax
0x14000a90c  movups  xmmword ptr [rbx+50h], xmm0
0x14000a910  mov     [rbx+60h], rax
0x14000a914  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000a91b  test    rax, rax
0x14000a91e  jz      short loc_14000A927
0x14000a920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a925  jmp     short loc_14000A92A
0x14000a927  mov     rax, rdi
0x14000a92a  mov     [rbx+80h], rax
0x14000a931  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000a938  test    rax, rax
0x14000a93b  jz      short loc_14000A945
0x14000a93d  mov     rcx, rbx
0x14000a940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a945  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000a94c  test    rax, rax
0x14000a94f  jz      short loc_14000A967
0x14000a951  mov     rdx, [rsp+78h+arg_60]
0x14000a959  mov     r8d, 400h
0x14000a95f  mov     rcx, rbx
0x14000a962  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a967  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a96e  test    rax, rax
0x14000a971  jz      short loc_14000A97B
0x14000a973  mov     rcx, rbx
0x14000a976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a97b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a982  test    rax, rax
0x14000a985  jz      short loc_14000A995
0x14000a987  test    byte ptr [rbx+4], 2
0x14000a98b  jnz     short loc_14000A995
0x14000a98d  mov     rcx, rbx
0x14000a990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a995  cmp     [rbx+8], edi
0x14000a998  jl      short loc_14000A9B4
0x14000a99a  cmp     r15d, 3
0x14000a99e  jnz     loc_14000AA82
0x14000a9a4  mov     ecx, 8000FFFFh; this
0x14000a9a9  mov     [rbx+8], ecx
0x14000a9ac  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000a9b1  mov     [rbx+0Ch], eax
0x14000a9b4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000a9bb  jnz     short loc_14000A9DC
0x14000a9bd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000a9c4  test    rax, rax
0x14000a9c7  jz      short loc_14000A9D2
0x14000a9c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a9ce  test    al, al
0x14000a9d0  jmp     short loc_14000A9DA
0x14000a9d2  call    cs:__imp_IsDebuggerPresent
0x14000a9d8  test    eax, eax
0x14000a9da  jz      short loc_14000A9E2
0x14000a9dc  test    byte ptr [rbx+4], 2
0x14000a9e0  jz      short loc_14000AA06
0x14000a9e2  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a9e9  test    rax, rax
0x14000a9ec  jz      short loc_14000AA4A
0x14000a9ee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000a9f5  jnz     short loc_14000AA4A
0x14000a9f7  xor     r8d, r8d
0x14000a9fa  xor     edx, edx
0x14000a9fc  mov     rcx, rbx
0x14000a9ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa04  jmp     short loc_14000AA4A
0x14000aa06  mov     rax, cs:g_pfnResultLoggingCallback
0x14000aa0d  mov     ebp, 800h
0x14000aa12  test    rax, rax
0x14000aa15  jz      short loc_14000AA2E
0x14000aa17  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000aa1e  jnz     short loc_14000AA2E
0x14000aa20  mov     r8d, ebp
0x14000aa23  mov     rdx, rsi
0x14000aa26  mov     rcx, rbx
0x14000aa29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa2e  cmp     [rsi], di
0x14000aa31  jnz     short loc_14000AA41
0x14000aa33  mov     r8, rbx; unsigned __int64
0x14000aa36  mov     rdx, rbp; unsigned __int16 *
0x14000aa39  mov     rcx, rsi; this
0x14000aa3c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000aa41  mov     rcx, rsi; lpOutputString
0x14000aa44  call    cs:__imp_OutputDebugStringW
0x14000aa4a  test    byte ptr [rbx+4], 4
0x14000aa4e  jnz     short loc_14000AA59
0x14000aa50  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000aa57  jz      short loc_14000AA6A
0x14000aa59  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000aa60  test    rax, rax
0x14000aa63  jz      short loc_14000AA6A
0x14000aa65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa6a  mov     rbx, [rsp+78h+arg_10]
0x14000aa72  add     rsp, 40h
0x14000aa76  pop     r15
0x14000aa78  pop     r14
0x14000aa7a  pop     r13
0x14000aa7c  pop     r12
0x14000aa7e  pop     rdi
0x14000aa7f  pop     rsi
0x14000aa80  pop     rbp
0x14000aa81  retn
0x14000aa82  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
