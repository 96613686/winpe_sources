# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001cabc`
- end: `0x18001cdb1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18001c8b8`
- `0x18001c9b4`
- `0x180022778`
- `0x180022838`

## callees

- `0x18001cabc`
- `0x18001ce54`
- `0x1800226c0`
- `0x180023374`
- `0x180024104`
- `0x180024120`
- `0x1800241fc`
- `0x180024218`
- `0x180024f8c`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cbdf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001cbdf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001cd72`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001cd72`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001cd00`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001cd00`

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
0x18001cabc  mov     [rsp+arg_10], rbx
0x18001cac1  mov     [rsp+arg_8], edx
0x18001cac5  mov     [rsp+arg_0], rcx
0x18001caca  push    rbp
0x18001cacb  push    rsi
0x18001cacc  push    rdi
0x18001cacd  push    r12
0x18001cacf  push    r13
0x18001cad1  push    r14
0x18001cad3  push    r15
0x18001cad5  sub     rsp, 40h
0x18001cad9  mov     r12, r9
0x18001cadc  mov     r13, r8
0x18001cadf  mov     r10, rcx
0x18001cae2  xor     eax, eax
0x18001cae4  mov     rsi, [rsp+78h+lpOutputString]
0x18001caec  mov     [rsi], ax
0x18001caef  mov     rax, [rsp+78h+arg_60]
0x18001caf7  mov     byte ptr [rax], 0
0x18001cafa  mov     r14, [rsp+78h+arg_38]
0x18001cb02  mov     edi, [r14]
0x18001cb05  mov     rbx, [rsp+78h+arg_78]
0x18001cb0d  mov     [rbx+8], edi
0x18001cb10  mov     eax, [r14+4]
0x18001cb14  mov     [rbx+0Ch], eax
0x18001cb17  xor     ebp, ebp
0x18001cb19  mov     r15d, [rsp+78h+arg_30]
0x18001cb21  mov     ecx, r15d
0x18001cb24  test    r15d, r15d
0x18001cb27  jz      short loc_18001CB8F
0x18001cb29  sub     ecx, 1
0x18001cb2c  jz      short loc_18001CB86
0x18001cb2e  sub     ecx, 1
0x18001cb31  jz      short loc_18001CB41
0x18001cb33  cmp     ecx, 1
0x18001cb36  jnz     short loc_18001CB98
0x18001cb38  mov     ecx, edi; this
0x18001cb3a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001cb3f  jmp     short loc_18001CB96
0x18001cb41  test    edi, edi
0x18001cb43  js      short loc_18001CB7D
0x18001cb45  mov     edi, 8007029Ch
0x18001cb4a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001cb4e  mov     rax, [rsp+78h+arg_28]
0x18001cb56  mov     [rsp+78h+var_50], rax; __int64
0x18001cb5b  mov     rax, [rsp+78h+arg_20]
0x18001cb63  mov     [rsp+78h+var_58], rax; __int64
0x18001cb68  mov     rcx, r10; int
0x18001cb6b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001cb70  mov     [rbx+8], edi
0x18001cb73  mov     ecx, edi; this
0x18001cb75  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001cb7a  mov     [rbx+0Ch], eax
0x18001cb7d  mov     ecx, edi; this
0x18001cb7f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001cb84  jmp     short loc_18001CB96
0x18001cb86  mov     ecx, edi; this
0x18001cb88  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001cb8d  jmp     short loc_18001CB96
0x18001cb8f  mov     ecx, edi; this
0x18001cb91  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001cb96  mov     ebp, eax
0x18001cb98  mov     [rbx], r15d
0x18001cb9b  mov     eax, [rsp+78h+arg_70]
0x18001cba2  mov     [rbx+4], eax
0x18001cba5  cmp     dword ptr [r14+8], 1
0x18001cbaa  jnz     short loc_18001CBB2
0x18001cbac  or      eax, 8
0x18001cbaf  mov     [rbx+4], eax
0x18001cbb2  mov     eax, 1
0x18001cbb7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001cbbf  inc     eax
0x18001cbc1  mov     [rbx+10h], eax
0x18001cbc4  mov     rax, [rsp+78h+arg_40]
0x18001cbcc  xor     edi, edi
0x18001cbce  test    rax, rax
0x18001cbd1  jz      short loc_18001CBD8
0x18001cbd3  cmp     [rax], di
0x18001cbd6  jnz     short loc_18001CBDB
0x18001cbd8  mov     rax, rdi
0x18001cbdb  mov     [rbx+18h], rax
0x18001cbdf  call    cs:__imp_GetCurrentThreadId
0x18001cbe5  mov     [rbx+20h], eax
0x18001cbe8  mov     [rbx+38h], r13
0x18001cbec  mov     eax, [rsp+78h+arg_8]
0x18001cbf3  mov     [rbx+40h], eax
0x18001cbf6  mov     [rbx+44h], ebp
0x18001cbf9  mov     rax, [rsp+78h+arg_20]
0x18001cc01  mov     [rbx+28h], rax
0x18001cc05  mov     [rbx+30h], r12
0x18001cc09  mov     rax, [rsp+78h+arg_28]
0x18001cc11  mov     [rbx+88h], rax
0x18001cc18  mov     rax, [rsp+78h+arg_0]
0x18001cc20  mov     [rbx+90h], rax
0x18001cc27  mov     [rbx+48h], rdi
0x18001cc2b  xorps   xmm0, xmm0
0x18001cc2e  xor     eax, eax
0x18001cc30  movups  xmmword ptr [rbx+68h], xmm0
0x18001cc34  mov     [rbx+78h], rax
0x18001cc38  movups  xmmword ptr [rbx+50h], xmm0
0x18001cc3c  mov     [rbx+60h], rax
0x18001cc40  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001cc47  test    rax, rax
0x18001cc4a  jz      short loc_18001CC53
0x18001cc4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc51  jmp     short loc_18001CC56
0x18001cc53  mov     rax, rdi
0x18001cc56  mov     [rbx+80h], rax
0x18001cc5d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001cc64  test    rax, rax
0x18001cc67  jz      short loc_18001CC71
0x18001cc69  mov     rcx, rbx
0x18001cc6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc71  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001cc78  test    rax, rax
0x18001cc7b  jz      short loc_18001CC93
0x18001cc7d  mov     r8d, 400h
0x18001cc83  mov     rdx, [rsp+78h+arg_60]
0x18001cc8b  mov     rcx, rbx
0x18001cc8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc93  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001cc9a  test    rax, rax
0x18001cc9d  jz      short loc_18001CCA7
0x18001cc9f  mov     rcx, rbx
0x18001cca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cca7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001ccae  test    rax, rax
0x18001ccb1  jz      short loc_18001CCC1
0x18001ccb3  test    byte ptr [rbx+4], 2
0x18001ccb7  jnz     short loc_18001CCC1
0x18001ccb9  mov     rcx, rbx
0x18001ccbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccc1  cmp     [rbx+8], edi
0x18001ccc4  jl      short loc_18001CCE2
0x18001ccc6  cmp     r15d, 3
0x18001ccca  jz      short loc_18001CCD2
0x18001cccc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001ccd2  mov     ecx, 8000FFFFh; this
0x18001ccd7  mov     [rbx+8], ecx
0x18001ccda  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001ccdf  mov     [rbx+0Ch], eax
0x18001cce2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001cce9  jnz     short loc_18001CD0A
0x18001cceb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001ccf2  test    rax, rax
0x18001ccf5  jz      short loc_18001CD00
0x18001ccf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ccfc  test    al, al
0x18001ccfe  jmp     short loc_18001CD08
0x18001cd00  call    cs:__imp_IsDebuggerPresent
0x18001cd06  test    eax, eax
0x18001cd08  jz      short loc_18001CD10
0x18001cd0a  test    byte ptr [rbx+4], 2
0x18001cd0e  jz      short loc_18001CD34
0x18001cd10  mov     rax, cs:g_pfnResultLoggingCallback
0x18001cd17  test    rax, rax
0x18001cd1a  jz      short loc_18001CD78
0x18001cd1c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001cd23  jnz     short loc_18001CD78
0x18001cd25  xor     r8d, r8d
0x18001cd28  xor     edx, edx
0x18001cd2a  mov     rcx, rbx
0x18001cd2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd32  jmp     short loc_18001CD78
0x18001cd34  mov     ebp, 800h
0x18001cd39  mov     rax, cs:g_pfnResultLoggingCallback
0x18001cd40  test    rax, rax
0x18001cd43  jz      short loc_18001CD5C
0x18001cd45  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001cd4c  jnz     short loc_18001CD5C
0x18001cd4e  mov     r8d, ebp
0x18001cd51  mov     rdx, rsi
0x18001cd54  mov     rcx, rbx
0x18001cd57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd5c  cmp     [rsi], di
0x18001cd5f  jnz     short loc_18001CD6F
0x18001cd61  mov     r8, rbx; unsigned __int64
0x18001cd64  mov     rdx, rbp; unsigned __int16 *
0x18001cd67  mov     rcx, rsi; this
0x18001cd6a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001cd6f  mov     rcx, rsi; lpOutputString
0x18001cd72  call    cs:__imp_OutputDebugStringW
0x18001cd78  test    byte ptr [rbx+4], 4
0x18001cd7c  jnz     short loc_18001CD87
0x18001cd7e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001cd85  jz      short loc_18001CD99
0x18001cd87  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001cd8e  test    rax, rax
0x18001cd91  jz      short loc_18001CD99
0x18001cd93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd98  nop
0x18001cd99  mov     rbx, [rsp+78h+arg_10]
0x18001cda1  add     rsp, 40h
0x18001cda5  pop     r15
0x18001cda7  pop     r14
0x18001cda9  pop     r13
0x18001cdab  pop     r12
0x18001cdad  pop     rdi
0x18001cdae  pop     rsi
0x18001cdaf  pop     rbp
0x18001cdb0  retn
```
