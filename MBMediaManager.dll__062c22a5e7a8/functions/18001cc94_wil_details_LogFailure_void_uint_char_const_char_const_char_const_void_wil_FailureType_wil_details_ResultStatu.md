# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001cc94`
- end: `0x18001cf89`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18001bea4`
- `0x18001cb98`
- `0x18002f70c`
- `0x180034934`

## callees

- `0x180016e68`
- `0x18001bde8`
- `0x18001cc94`
- `0x18001cf90`
- `0x18002feb4`
- `0x180030748`
- `0x180030764`
- `0x180030780`
- `0x1800310d4`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cdb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cdb7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001ced8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001ced8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001cf4a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001cf4a`

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
0x18001cc94  mov     [rsp+arg_10], rbx
0x18001cc99  mov     [rsp+arg_8], edx
0x18001cc9d  mov     [rsp+arg_0], rcx
0x18001cca2  push    rbp
0x18001cca3  push    rsi
0x18001cca4  push    rdi
0x18001cca5  push    r12
0x18001cca7  push    r13
0x18001cca9  push    r14
0x18001ccab  push    r15
0x18001ccad  sub     rsp, 40h
0x18001ccb1  mov     r12, r9
0x18001ccb4  mov     r13, r8
0x18001ccb7  mov     r10, rcx
0x18001ccba  xor     eax, eax
0x18001ccbc  mov     rsi, [rsp+78h+lpOutputString]
0x18001ccc4  mov     [rsi], ax
0x18001ccc7  mov     rax, [rsp+78h+arg_60]
0x18001cccf  mov     byte ptr [rax], 0
0x18001ccd2  mov     r14, [rsp+78h+arg_38]
0x18001ccda  mov     edi, [r14]
0x18001ccdd  mov     rbx, [rsp+78h+arg_78]
0x18001cce5  mov     [rbx+8], edi
0x18001cce8  mov     eax, [r14+4]
0x18001ccec  mov     [rbx+0Ch], eax
0x18001ccef  xor     ebp, ebp
0x18001ccf1  mov     r15d, [rsp+78h+arg_30]
0x18001ccf9  mov     ecx, r15d
0x18001ccfc  test    r15d, r15d
0x18001ccff  jz      short loc_18001CD67
0x18001cd01  sub     ecx, 1
0x18001cd04  jz      short loc_18001CD5E
0x18001cd06  sub     ecx, 1
0x18001cd09  jz      short loc_18001CD19
0x18001cd0b  cmp     ecx, 1
0x18001cd0e  jnz     short loc_18001CD70
0x18001cd10  mov     ecx, edi; this
0x18001cd12  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001cd17  jmp     short loc_18001CD6E
0x18001cd19  test    edi, edi
0x18001cd1b  js      short loc_18001CD55
0x18001cd1d  mov     edi, 8007029Ch
0x18001cd22  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001cd26  mov     rax, [rsp+78h+arg_28]
0x18001cd2e  mov     [rsp+78h+var_50], rax; __int64
0x18001cd33  mov     rax, [rsp+78h+arg_20]
0x18001cd3b  mov     [rsp+78h+var_58], rax; __int64
0x18001cd40  mov     rcx, r10; int
0x18001cd43  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001cd48  mov     [rbx+8], edi
0x18001cd4b  mov     ecx, edi; this
0x18001cd4d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001cd52  mov     [rbx+0Ch], eax
0x18001cd55  mov     ecx, edi; this
0x18001cd57  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001cd5c  jmp     short loc_18001CD6E
0x18001cd5e  mov     ecx, edi; this
0x18001cd60  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001cd65  jmp     short loc_18001CD6E
0x18001cd67  mov     ecx, edi; this
0x18001cd69  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001cd6e  mov     ebp, eax
0x18001cd70  mov     [rbx], r15d
0x18001cd73  mov     eax, [rsp+78h+arg_70]
0x18001cd7a  mov     [rbx+4], eax
0x18001cd7d  cmp     dword ptr [r14+8], 1
0x18001cd82  jnz     short loc_18001CD8A
0x18001cd84  or      eax, 8
0x18001cd87  mov     [rbx+4], eax
0x18001cd8a  mov     eax, 1
0x18001cd8f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001cd97  inc     eax
0x18001cd99  mov     [rbx+10h], eax
0x18001cd9c  mov     rax, [rsp+78h+arg_40]
0x18001cda4  xor     edi, edi
0x18001cda6  test    rax, rax
0x18001cda9  jz      short loc_18001CDB0
0x18001cdab  cmp     [rax], di
0x18001cdae  jnz     short loc_18001CDB3
0x18001cdb0  mov     rax, rdi
0x18001cdb3  mov     [rbx+18h], rax
0x18001cdb7  call    cs:__imp_GetCurrentThreadId
0x18001cdbd  mov     [rbx+20h], eax
0x18001cdc0  mov     [rbx+38h], r13
0x18001cdc4  mov     eax, [rsp+78h+arg_8]
0x18001cdcb  mov     [rbx+40h], eax
0x18001cdce  mov     [rbx+44h], ebp
0x18001cdd1  mov     rax, [rsp+78h+arg_20]
0x18001cdd9  mov     [rbx+28h], rax
0x18001cddd  mov     [rbx+30h], r12
0x18001cde1  mov     rax, [rsp+78h+arg_28]
0x18001cde9  mov     [rbx+88h], rax
0x18001cdf0  mov     rax, [rsp+78h+arg_0]
0x18001cdf8  mov     [rbx+90h], rax
0x18001cdff  mov     [rbx+48h], rdi
0x18001ce03  xorps   xmm0, xmm0
0x18001ce06  xor     eax, eax
0x18001ce08  movups  xmmword ptr [rbx+68h], xmm0
0x18001ce0c  mov     [rbx+78h], rax
0x18001ce10  movups  xmmword ptr [rbx+50h], xmm0
0x18001ce14  mov     [rbx+60h], rax
0x18001ce18  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001ce1f  test    rax, rax
0x18001ce22  jz      short loc_18001CE2B
0x18001ce24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce29  jmp     short loc_18001CE2E
0x18001ce2b  mov     rax, rdi
0x18001ce2e  mov     [rbx+80h], rax
0x18001ce35  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001ce3c  test    rax, rax
0x18001ce3f  jz      short loc_18001CE49
0x18001ce41  mov     rcx, rbx
0x18001ce44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce49  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001ce50  test    rax, rax
0x18001ce53  jz      short loc_18001CE6B
0x18001ce55  mov     r8d, 400h
0x18001ce5b  mov     rdx, [rsp+78h+arg_60]
0x18001ce63  mov     rcx, rbx
0x18001ce66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce6b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001ce72  test    rax, rax
0x18001ce75  jz      short loc_18001CE7F
0x18001ce77  mov     rcx, rbx
0x18001ce7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce7f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001ce86  test    rax, rax
0x18001ce89  jz      short loc_18001CE99
0x18001ce8b  test    byte ptr [rbx+4], 2
0x18001ce8f  jnz     short loc_18001CE99
0x18001ce91  mov     rcx, rbx
0x18001ce94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ce99  cmp     [rbx+8], edi
0x18001ce9c  jl      short loc_18001CEBA
0x18001ce9e  cmp     r15d, 3
0x18001cea2  jz      short loc_18001CEAA
0x18001cea4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001ceaa  mov     ecx, 8000FFFFh; this
0x18001ceaf  mov     [rbx+8], ecx
0x18001ceb2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001ceb7  mov     [rbx+0Ch], eax
0x18001ceba  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001cec1  jnz     short loc_18001CEE2
0x18001cec3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001ceca  test    rax, rax
0x18001cecd  jz      short loc_18001CED8
0x18001cecf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ced4  test    al, al
0x18001ced6  jmp     short loc_18001CEE0
0x18001ced8  call    cs:__imp_IsDebuggerPresent
0x18001cede  test    eax, eax
0x18001cee0  jz      short loc_18001CEE8
0x18001cee2  test    byte ptr [rbx+4], 2
0x18001cee6  jz      short loc_18001CF0C
0x18001cee8  mov     rax, cs:g_pfnResultLoggingCallback
0x18001ceef  test    rax, rax
0x18001cef2  jz      short loc_18001CF50
0x18001cef4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001cefb  jnz     short loc_18001CF50
0x18001cefd  xor     r8d, r8d
0x18001cf00  xor     edx, edx
0x18001cf02  mov     rcx, rbx
0x18001cf05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf0a  jmp     short loc_18001CF50
0x18001cf0c  mov     ebp, 800h
0x18001cf11  mov     rax, cs:g_pfnResultLoggingCallback
0x18001cf18  test    rax, rax
0x18001cf1b  jz      short loc_18001CF34
0x18001cf1d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001cf24  jnz     short loc_18001CF34
0x18001cf26  mov     r8d, ebp
0x18001cf29  mov     rdx, rsi
0x18001cf2c  mov     rcx, rbx
0x18001cf2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf34  cmp     [rsi], di
0x18001cf37  jnz     short loc_18001CF47
0x18001cf39  mov     r8, rbx; unsigned __int64
0x18001cf3c  mov     rdx, rbp; unsigned __int16 *
0x18001cf3f  mov     rcx, rsi; this
0x18001cf42  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001cf47  mov     rcx, rsi; lpOutputString
0x18001cf4a  call    cs:__imp_OutputDebugStringW
0x18001cf50  test    byte ptr [rbx+4], 4
0x18001cf54  jnz     short loc_18001CF5F
0x18001cf56  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001cf5d  jz      short loc_18001CF71
0x18001cf5f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001cf66  test    rax, rax
0x18001cf69  jz      short loc_18001CF71
0x18001cf6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf70  nop
0x18001cf71  mov     rbx, [rsp+78h+arg_10]
0x18001cf79  add     rsp, 40h
0x18001cf7d  pop     r15
0x18001cf7f  pop     r14
0x18001cf81  pop     r13
0x18001cf83  pop     r12
0x18001cf85  pop     rdi
0x18001cf86  pop     rsi
0x18001cf87  pop     rbp
0x18001cf88  retn
```
