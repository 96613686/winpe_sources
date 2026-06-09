# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004a0c`
- end: `0x140004d05`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400024e4`
- `0x140002828`

## callees

- `0x140002424`
- `0x140003ea4`
- `0x140004708`
- `0x140004a0c`
- `0x140005654`
- `0x140005670`
- `0x1400057f4`
- `0x140005810`
- `0x140007160`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004b2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004b2f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004c4e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004c4e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004cc0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004cc0`

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
0x140004a0c  mov     [rsp+arg_10], rbx
0x140004a11  mov     [rsp+arg_8], edx
0x140004a15  mov     [rsp+arg_0], rcx
0x140004a1a  push    rbp
0x140004a1b  push    rsi
0x140004a1c  push    rdi
0x140004a1d  push    r12
0x140004a1f  push    r13
0x140004a21  push    r14
0x140004a23  push    r15
0x140004a25  sub     rsp, 40h
0x140004a29  mov     r12, r9
0x140004a2c  mov     r13, r8
0x140004a2f  mov     r10, rcx
0x140004a32  xor     eax, eax
0x140004a34  mov     rsi, [rsp+78h+lpOutputString]
0x140004a3c  mov     [rsi], ax
0x140004a3f  mov     rax, [rsp+78h+arg_60]
0x140004a47  mov     byte ptr [rax], 0
0x140004a4a  mov     r14, [rsp+78h+arg_38]
0x140004a52  mov     edi, [r14]
0x140004a55  mov     rbx, [rsp+78h+arg_78]
0x140004a5d  mov     [rbx+8], edi
0x140004a60  mov     eax, [r14+4]
0x140004a64  mov     [rbx+0Ch], eax
0x140004a67  xor     ebp, ebp
0x140004a69  mov     r15d, [rsp+78h+arg_30]
0x140004a71  mov     ecx, r15d
0x140004a74  test    r15d, r15d
0x140004a77  jz      short loc_140004ADF
0x140004a79  sub     ecx, 1
0x140004a7c  jz      short loc_140004AD6
0x140004a7e  sub     ecx, 1
0x140004a81  jz      short loc_140004A91
0x140004a83  cmp     ecx, 1
0x140004a86  jnz     short loc_140004AE8
0x140004a88  mov     ecx, edi; this
0x140004a8a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004a8f  jmp     short loc_140004AE6
0x140004a91  test    edi, edi
0x140004a93  js      short loc_140004ACD
0x140004a95  mov     edi, 8007029Ch
0x140004a9a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140004a9e  mov     rax, [rsp+78h+arg_28]
0x140004aa6  mov     [rsp+78h+var_50], rax; __int64
0x140004aab  mov     rax, [rsp+78h+arg_20]
0x140004ab3  mov     [rsp+78h+var_58], rax; __int64
0x140004ab8  mov     rcx, r10; int
0x140004abb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004ac0  mov     [rbx+8], edi
0x140004ac3  mov     ecx, edi; this
0x140004ac5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004aca  mov     [rbx+0Ch], eax
0x140004acd  mov     ecx, edi; this
0x140004acf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004ad4  jmp     short loc_140004AE6
0x140004ad6  mov     ecx, edi; this
0x140004ad8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004add  jmp     short loc_140004AE6
0x140004adf  mov     ecx, edi; this
0x140004ae1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004ae6  mov     ebp, eax
0x140004ae8  mov     [rbx], r15d
0x140004aeb  mov     eax, [rsp+78h+arg_70]
0x140004af2  mov     [rbx+4], eax
0x140004af5  cmp     dword ptr [r14+8], 1
0x140004afa  jnz     short loc_140004B02
0x140004afc  or      eax, 8
0x140004aff  mov     [rbx+4], eax
0x140004b02  mov     eax, 1
0x140004b07  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004b0f  inc     eax
0x140004b11  mov     [rbx+10h], eax
0x140004b14  mov     rax, [rsp+78h+arg_40]
0x140004b1c  xor     edi, edi
0x140004b1e  test    rax, rax
0x140004b21  jz      short loc_140004B28
0x140004b23  cmp     [rax], di
0x140004b26  jnz     short loc_140004B2B
0x140004b28  mov     rax, rdi
0x140004b2b  mov     [rbx+18h], rax
0x140004b2f  call    cs:__imp_GetCurrentThreadId
0x140004b35  mov     [rbx+20h], eax
0x140004b38  mov     [rbx+38h], r13
0x140004b3c  mov     eax, [rsp+78h+arg_8]
0x140004b43  mov     [rbx+40h], eax
0x140004b46  mov     [rbx+44h], ebp
0x140004b49  mov     rax, [rsp+78h+arg_20]
0x140004b51  mov     [rbx+28h], rax
0x140004b55  mov     [rbx+30h], r12
0x140004b59  mov     rax, [rsp+78h+arg_28]
0x140004b61  mov     [rbx+88h], rax
0x140004b68  mov     rax, [rsp+78h+arg_0]
0x140004b70  mov     [rbx+90h], rax
0x140004b77  mov     [rbx+48h], rdi
0x140004b7b  xorps   xmm0, xmm0
0x140004b7e  xor     eax, eax
0x140004b80  movups  xmmword ptr [rbx+68h], xmm0
0x140004b84  mov     [rbx+78h], rax
0x140004b88  movups  xmmword ptr [rbx+50h], xmm0
0x140004b8c  mov     [rbx+60h], rax
0x140004b90  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004b97  test    rax, rax
0x140004b9a  jz      short loc_140004BA3
0x140004b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ba1  jmp     short loc_140004BA6
0x140004ba3  mov     rax, rdi
0x140004ba6  mov     [rbx+80h], rax
0x140004bad  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004bb4  test    rax, rax
0x140004bb7  jz      short loc_140004BC1
0x140004bb9  mov     rcx, rbx
0x140004bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004bc1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004bc8  test    rax, rax
0x140004bcb  jz      short loc_140004BE3
0x140004bcd  mov     r8d, 400h
0x140004bd3  mov     rdx, [rsp+78h+arg_60]
0x140004bdb  mov     rcx, rbx
0x140004bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004be3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004bea  test    rax, rax
0x140004bed  jz      short loc_140004BF7
0x140004bef  mov     rcx, rbx
0x140004bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004bf7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004bfe  test    rax, rax
0x140004c01  jz      short loc_140004C11
0x140004c03  test    byte ptr [rbx+4], 2
0x140004c07  jnz     short loc_140004C11
0x140004c09  mov     rcx, rbx
0x140004c0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c11  cmp     [rbx+8], edi
0x140004c14  jl      short loc_140004C30
0x140004c16  cmp     r15d, 3
0x140004c1a  jnz     loc_140004CFF
0x140004c20  mov     ecx, 8000FFFFh; this
0x140004c25  mov     [rbx+8], ecx
0x140004c28  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004c2d  mov     [rbx+0Ch], eax
0x140004c30  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140004c37  jnz     short loc_140004C58
0x140004c39  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004c40  test    rax, rax
0x140004c43  jz      short loc_140004C4E
0x140004c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c4a  test    al, al
0x140004c4c  jmp     short loc_140004C56
0x140004c4e  call    cs:__imp_IsDebuggerPresent
0x140004c54  test    eax, eax
0x140004c56  jz      short loc_140004C5E
0x140004c58  test    byte ptr [rbx+4], 2
0x140004c5c  jz      short loc_140004C82
0x140004c5e  mov     rax, cs:g_pfnResultLoggingCallback
0x140004c65  test    rax, rax
0x140004c68  jz      short loc_140004CC6
0x140004c6a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004c71  jnz     short loc_140004CC6
0x140004c73  xor     r8d, r8d
0x140004c76  xor     edx, edx
0x140004c78  mov     rcx, rbx
0x140004c7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004c80  jmp     short loc_140004CC6
0x140004c82  mov     ebp, 800h
0x140004c87  mov     rax, cs:g_pfnResultLoggingCallback
0x140004c8e  test    rax, rax
0x140004c91  jz      short loc_140004CAA
0x140004c93  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004c9a  jnz     short loc_140004CAA
0x140004c9c  mov     r8d, ebp
0x140004c9f  mov     rdx, rsi
0x140004ca2  mov     rcx, rbx
0x140004ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004caa  cmp     [rsi], di
0x140004cad  jnz     short loc_140004CBD
0x140004caf  mov     r8, rbx; unsigned __int64
0x140004cb2  mov     rdx, rbp; unsigned __int16 *
0x140004cb5  mov     rcx, rsi; this
0x140004cb8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004cbd  mov     rcx, rsi; lpOutputString
0x140004cc0  call    cs:__imp_OutputDebugStringW
0x140004cc6  test    byte ptr [rbx+4], 4
0x140004cca  jnz     short loc_140004CD5
0x140004ccc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140004cd3  jz      short loc_140004CE7
0x140004cd5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004cdc  test    rax, rax
0x140004cdf  jz      short loc_140004CE7
0x140004ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ce6  nop
0x140004ce7  mov     rbx, [rsp+78h+arg_10]
0x140004cef  add     rsp, 40h
0x140004cf3  pop     r15
0x140004cf5  pop     r14
0x140004cf7  pop     r13
0x140004cf9  pop     r12
0x140004cfb  pop     rdi
0x140004cfc  pop     rsi
0x140004cfd  pop     rbp
0x140004cfe  retn
0x140004cff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
