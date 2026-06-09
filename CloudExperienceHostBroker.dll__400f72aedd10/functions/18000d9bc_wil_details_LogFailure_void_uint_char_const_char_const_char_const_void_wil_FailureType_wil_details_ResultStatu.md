# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000d9bc`
- end: `0x18000dcb5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180006f98`
- `0x1800070a0`
- `0x18000c504`

## callees

- `0x180006a0c`
- `0x180007160`
- `0x18000c190`
- `0x18000d204`
- `0x18000d9bc`
- `0x18000e110`
- `0x18000e130`
- `0x18000e144`
- `0x18000f178`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dadf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000dadf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000dbfe`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000dbfe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000dc70`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000dc70`

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
0x18000d9bc  mov     [rsp+arg_10], rbx
0x18000d9c1  mov     [rsp+arg_8], edx
0x18000d9c5  mov     [rsp+arg_0], rcx
0x18000d9ca  push    rbp
0x18000d9cb  push    rsi
0x18000d9cc  push    rdi
0x18000d9cd  push    r12
0x18000d9cf  push    r13
0x18000d9d1  push    r14
0x18000d9d3  push    r15
0x18000d9d5  sub     rsp, 40h
0x18000d9d9  mov     r12, r9
0x18000d9dc  mov     r13, r8
0x18000d9df  mov     r10, rcx
0x18000d9e2  xor     eax, eax
0x18000d9e4  mov     rsi, [rsp+78h+lpOutputString]
0x18000d9ec  mov     [rsi], ax
0x18000d9ef  mov     rax, [rsp+78h+arg_60]
0x18000d9f7  mov     byte ptr [rax], 0
0x18000d9fa  mov     r14, [rsp+78h+arg_38]
0x18000da02  mov     edi, [r14]
0x18000da05  mov     rbx, [rsp+78h+arg_78]
0x18000da0d  mov     [rbx+8], edi
0x18000da10  mov     eax, [r14+4]
0x18000da14  mov     [rbx+0Ch], eax
0x18000da17  xor     ebp, ebp
0x18000da19  mov     r15d, [rsp+78h+arg_30]
0x18000da21  mov     ecx, r15d
0x18000da24  test    r15d, r15d
0x18000da27  jz      short loc_18000DA8F
0x18000da29  sub     ecx, 1
0x18000da2c  jz      short loc_18000DA86
0x18000da2e  sub     ecx, 1
0x18000da31  jz      short loc_18000DA41
0x18000da33  cmp     ecx, 1
0x18000da36  jnz     short loc_18000DA98
0x18000da38  mov     ecx, edi; this
0x18000da3a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000da3f  jmp     short loc_18000DA96
0x18000da41  test    edi, edi
0x18000da43  js      short loc_18000DA7D
0x18000da45  mov     edi, 8007029Ch
0x18000da4a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000da4e  mov     rax, [rsp+78h+arg_28]
0x18000da56  mov     [rsp+78h+var_50], rax; __int64
0x18000da5b  mov     rax, [rsp+78h+arg_20]
0x18000da63  mov     [rsp+78h+var_58], rax; __int64
0x18000da68  mov     rcx, r10; int
0x18000da6b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000da70  mov     [rbx+8], edi
0x18000da73  mov     ecx, edi; this
0x18000da75  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000da7a  mov     [rbx+0Ch], eax
0x18000da7d  mov     ecx, edi; this
0x18000da7f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000da84  jmp     short loc_18000DA96
0x18000da86  mov     ecx, edi; this
0x18000da88  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000da8d  jmp     short loc_18000DA96
0x18000da8f  mov     ecx, edi; this
0x18000da91  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000da96  mov     ebp, eax
0x18000da98  mov     [rbx], r15d
0x18000da9b  mov     eax, [rsp+78h+arg_70]
0x18000daa2  mov     [rbx+4], eax
0x18000daa5  cmp     dword ptr [r14+8], 1
0x18000daaa  jnz     short loc_18000DAB2
0x18000daac  or      eax, 8
0x18000daaf  mov     [rbx+4], eax
0x18000dab2  mov     eax, 1
0x18000dab7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000dabf  inc     eax
0x18000dac1  mov     [rbx+10h], eax
0x18000dac4  mov     rax, [rsp+78h+arg_40]
0x18000dacc  xor     edi, edi
0x18000dace  test    rax, rax
0x18000dad1  jz      short loc_18000DAD8
0x18000dad3  cmp     [rax], di
0x18000dad6  jnz     short loc_18000DADB
0x18000dad8  mov     rax, rdi
0x18000dadb  mov     [rbx+18h], rax
0x18000dadf  call    cs:__imp_GetCurrentThreadId
0x18000dae5  mov     [rbx+20h], eax
0x18000dae8  mov     [rbx+38h], r13
0x18000daec  mov     eax, [rsp+78h+arg_8]
0x18000daf3  mov     [rbx+40h], eax
0x18000daf6  mov     [rbx+44h], ebp
0x18000daf9  mov     rax, [rsp+78h+arg_20]
0x18000db01  mov     [rbx+28h], rax
0x18000db05  mov     [rbx+30h], r12
0x18000db09  mov     rax, [rsp+78h+arg_28]
0x18000db11  mov     [rbx+88h], rax
0x18000db18  mov     rax, [rsp+78h+arg_0]
0x18000db20  mov     [rbx+90h], rax
0x18000db27  mov     [rbx+48h], rdi
0x18000db2b  xorps   xmm0, xmm0
0x18000db2e  xor     eax, eax
0x18000db30  movups  xmmword ptr [rbx+68h], xmm0
0x18000db34  mov     [rbx+78h], rax
0x18000db38  movups  xmmword ptr [rbx+50h], xmm0
0x18000db3c  mov     [rbx+60h], rax
0x18000db40  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000db47  test    rax, rax
0x18000db4a  jz      short loc_18000DB53
0x18000db4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db51  jmp     short loc_18000DB56
0x18000db53  mov     rax, rdi
0x18000db56  mov     [rbx+80h], rax
0x18000db5d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000db64  test    rax, rax
0x18000db67  jz      short loc_18000DB71
0x18000db69  mov     rcx, rbx
0x18000db6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db71  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000db78  test    rax, rax
0x18000db7b  jz      short loc_18000DB93
0x18000db7d  mov     r8d, 400h
0x18000db83  mov     rdx, [rsp+78h+arg_60]
0x18000db8b  mov     rcx, rbx
0x18000db8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db93  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000db9a  test    rax, rax
0x18000db9d  jz      short loc_18000DBA7
0x18000db9f  mov     rcx, rbx
0x18000dba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dba7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000dbae  test    rax, rax
0x18000dbb1  jz      short loc_18000DBC1
0x18000dbb3  test    byte ptr [rbx+4], 2
0x18000dbb7  jnz     short loc_18000DBC1
0x18000dbb9  mov     rcx, rbx
0x18000dbbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbc1  cmp     [rbx+8], edi
0x18000dbc4  jl      short loc_18000DBE0
0x18000dbc6  cmp     r15d, 3
0x18000dbca  jnz     loc_18000DCAF
0x18000dbd0  mov     ecx, 8000FFFFh; this
0x18000dbd5  mov     [rbx+8], ecx
0x18000dbd8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000dbdd  mov     [rbx+0Ch], eax
0x18000dbe0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000dbe7  jnz     short loc_18000DC08
0x18000dbe9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000dbf0  test    rax, rax
0x18000dbf3  jz      short loc_18000DBFE
0x18000dbf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbfa  test    al, al
0x18000dbfc  jmp     short loc_18000DC06
0x18000dbfe  call    cs:__imp_IsDebuggerPresent
0x18000dc04  test    eax, eax
0x18000dc06  jz      short loc_18000DC0E
0x18000dc08  test    byte ptr [rbx+4], 2
0x18000dc0c  jz      short loc_18000DC32
0x18000dc0e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000dc15  test    rax, rax
0x18000dc18  jz      short loc_18000DC76
0x18000dc1a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000dc21  jnz     short loc_18000DC76
0x18000dc23  xor     r8d, r8d
0x18000dc26  xor     edx, edx
0x18000dc28  mov     rcx, rbx
0x18000dc2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc30  jmp     short loc_18000DC76
0x18000dc32  mov     ebp, 800h
0x18000dc37  mov     rax, cs:g_pfnResultLoggingCallback
0x18000dc3e  test    rax, rax
0x18000dc41  jz      short loc_18000DC5A
0x18000dc43  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000dc4a  jnz     short loc_18000DC5A
0x18000dc4c  mov     r8d, ebp
0x18000dc4f  mov     rdx, rsi
0x18000dc52  mov     rcx, rbx
0x18000dc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc5a  cmp     [rsi], di
0x18000dc5d  jnz     short loc_18000DC6D
0x18000dc5f  mov     r8, rbx; unsigned __int64
0x18000dc62  mov     rdx, rbp; unsigned __int16 *
0x18000dc65  mov     rcx, rsi; this
0x18000dc68  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000dc6d  mov     rcx, rsi; lpOutputString
0x18000dc70  call    cs:__imp_OutputDebugStringW
0x18000dc76  test    byte ptr [rbx+4], 4
0x18000dc7a  jnz     short loc_18000DC85
0x18000dc7c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000dc83  jz      short loc_18000DC97
0x18000dc85  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000dc8c  test    rax, rax
0x18000dc8f  jz      short loc_18000DC97
0x18000dc91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc96  nop
0x18000dc97  mov     rbx, [rsp+78h+arg_10]
0x18000dc9f  add     rsp, 40h
0x18000dca3  pop     r15
0x18000dca5  pop     r14
0x18000dca7  pop     r13
0x18000dca9  pop     r12
0x18000dcab  pop     rdi
0x18000dcac  pop     rsi
0x18000dcad  pop     rbp
0x18000dcae  retn
0x18000dcaf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
