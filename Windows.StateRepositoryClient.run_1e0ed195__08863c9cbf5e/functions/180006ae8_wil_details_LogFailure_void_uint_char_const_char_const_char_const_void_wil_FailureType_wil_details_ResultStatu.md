# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006ae8`
- end: `0x180006de1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180004980`
- `0x180004cc4`

## callees

- `0x1800048c0`
- `0x180005f94`
- `0x180006810`
- `0x180006ae8`
- `0x1800071bc`
- `0x1800071e0`
- `0x1800071f4`
- `0x180007210`
- `0x1800082d4`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c0b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c0b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006d9c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006d9c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006d2a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006d2a`

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
0x180006ae8  mov     [rsp+arg_10], rbx
0x180006aed  mov     [rsp+arg_8], edx
0x180006af1  mov     [rsp+arg_0], rcx
0x180006af6  push    rbp
0x180006af7  push    rsi
0x180006af8  push    rdi
0x180006af9  push    r12
0x180006afb  push    r13
0x180006afd  push    r14
0x180006aff  push    r15
0x180006b01  sub     rsp, 40h
0x180006b05  mov     r12, r9
0x180006b08  mov     r13, r8
0x180006b0b  mov     r10, rcx
0x180006b0e  xor     eax, eax
0x180006b10  mov     rsi, [rsp+78h+lpOutputString]
0x180006b18  mov     [rsi], ax
0x180006b1b  mov     rax, [rsp+78h+arg_60]
0x180006b23  mov     byte ptr [rax], 0
0x180006b26  mov     r14, [rsp+78h+arg_38]
0x180006b2e  mov     edi, [r14]
0x180006b31  mov     rbx, [rsp+78h+arg_78]
0x180006b39  mov     [rbx+8], edi
0x180006b3c  mov     eax, [r14+4]
0x180006b40  mov     [rbx+0Ch], eax
0x180006b43  xor     ebp, ebp
0x180006b45  mov     r15d, [rsp+78h+arg_30]
0x180006b4d  mov     ecx, r15d
0x180006b50  test    r15d, r15d
0x180006b53  jz      short loc_180006BBB
0x180006b55  sub     ecx, 1
0x180006b58  jz      short loc_180006BB2
0x180006b5a  sub     ecx, 1
0x180006b5d  jz      short loc_180006B6D
0x180006b5f  cmp     ecx, 1
0x180006b62  jnz     short loc_180006BC4
0x180006b64  mov     ecx, edi; this
0x180006b66  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006b6b  jmp     short loc_180006BC2
0x180006b6d  test    edi, edi
0x180006b6f  js      short loc_180006BA9
0x180006b71  mov     edi, 8007029Ch
0x180006b76  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006b7a  mov     rax, [rsp+78h+arg_28]
0x180006b82  mov     [rsp+78h+var_50], rax; __int64
0x180006b87  mov     rax, [rsp+78h+arg_20]
0x180006b8f  mov     [rsp+78h+var_58], rax; __int64
0x180006b94  mov     rcx, r10; int
0x180006b97  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006b9c  mov     [rbx+8], edi
0x180006b9f  mov     ecx, edi; this
0x180006ba1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006ba6  mov     [rbx+0Ch], eax
0x180006ba9  mov     ecx, edi; this
0x180006bab  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006bb0  jmp     short loc_180006BC2
0x180006bb2  mov     ecx, edi; this
0x180006bb4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006bb9  jmp     short loc_180006BC2
0x180006bbb  mov     ecx, edi; this
0x180006bbd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006bc2  mov     ebp, eax
0x180006bc4  mov     [rbx], r15d
0x180006bc7  mov     eax, [rsp+78h+arg_70]
0x180006bce  mov     [rbx+4], eax
0x180006bd1  cmp     dword ptr [r14+8], 1
0x180006bd6  jnz     short loc_180006BDE
0x180006bd8  or      eax, 8
0x180006bdb  mov     [rbx+4], eax
0x180006bde  mov     eax, 1
0x180006be3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006beb  inc     eax
0x180006bed  mov     [rbx+10h], eax
0x180006bf0  mov     rax, [rsp+78h+arg_40]
0x180006bf8  xor     edi, edi
0x180006bfa  test    rax, rax
0x180006bfd  jz      short loc_180006C04
0x180006bff  cmp     [rax], di
0x180006c02  jnz     short loc_180006C07
0x180006c04  mov     rax, rdi
0x180006c07  mov     [rbx+18h], rax
0x180006c0b  call    cs:__imp_GetCurrentThreadId
0x180006c11  mov     [rbx+20h], eax
0x180006c14  mov     [rbx+38h], r13
0x180006c18  mov     eax, [rsp+78h+arg_8]
0x180006c1f  mov     [rbx+40h], eax
0x180006c22  mov     [rbx+44h], ebp
0x180006c25  mov     rax, [rsp+78h+arg_20]
0x180006c2d  mov     [rbx+28h], rax
0x180006c31  mov     [rbx+30h], r12
0x180006c35  mov     rax, [rsp+78h+arg_28]
0x180006c3d  mov     [rbx+88h], rax
0x180006c44  mov     rax, [rsp+78h+arg_0]
0x180006c4c  mov     [rbx+90h], rax
0x180006c53  mov     [rbx+48h], rdi
0x180006c57  xorps   xmm0, xmm0
0x180006c5a  xor     eax, eax
0x180006c5c  movups  xmmword ptr [rbx+68h], xmm0
0x180006c60  mov     [rbx+78h], rax
0x180006c64  movups  xmmword ptr [rbx+50h], xmm0
0x180006c68  mov     [rbx+60h], rax
0x180006c6c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006c73  test    rax, rax
0x180006c76  jz      short loc_180006C7F
0x180006c78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c7d  jmp     short loc_180006C82
0x180006c7f  mov     rax, rdi
0x180006c82  mov     [rbx+80h], rax
0x180006c89  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006c90  test    rax, rax
0x180006c93  jz      short loc_180006C9D
0x180006c95  mov     rcx, rbx
0x180006c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c9d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006ca4  test    rax, rax
0x180006ca7  jz      short loc_180006CBF
0x180006ca9  mov     r8d, 400h
0x180006caf  mov     rdx, [rsp+78h+arg_60]
0x180006cb7  mov     rcx, rbx
0x180006cba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cbf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006cc6  test    rax, rax
0x180006cc9  jz      short loc_180006CD3
0x180006ccb  mov     rcx, rbx
0x180006cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cd3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006cda  test    rax, rax
0x180006cdd  jz      short loc_180006CED
0x180006cdf  test    byte ptr [rbx+4], 2
0x180006ce3  jnz     short loc_180006CED
0x180006ce5  mov     rcx, rbx
0x180006ce8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ced  cmp     [rbx+8], edi
0x180006cf0  jl      short loc_180006D0C
0x180006cf2  cmp     r15d, 3
0x180006cf6  jnz     loc_180006DDB
0x180006cfc  mov     ecx, 8000FFFFh; this
0x180006d01  mov     [rbx+8], ecx
0x180006d04  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006d09  mov     [rbx+0Ch], eax
0x180006d0c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006d13  jnz     short loc_180006D34
0x180006d15  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006d1c  test    rax, rax
0x180006d1f  jz      short loc_180006D2A
0x180006d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d26  test    al, al
0x180006d28  jmp     short loc_180006D32
0x180006d2a  call    cs:__imp_IsDebuggerPresent
0x180006d30  test    eax, eax
0x180006d32  jz      short loc_180006D3A
0x180006d34  test    byte ptr [rbx+4], 2
0x180006d38  jz      short loc_180006D5E
0x180006d3a  mov     rax, cs:g_pfnResultLoggingCallback
0x180006d41  test    rax, rax
0x180006d44  jz      short loc_180006DA2
0x180006d46  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006d4d  jnz     short loc_180006DA2
0x180006d4f  xor     r8d, r8d
0x180006d52  xor     edx, edx
0x180006d54  mov     rcx, rbx
0x180006d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d5c  jmp     short loc_180006DA2
0x180006d5e  mov     ebp, 800h
0x180006d63  mov     rax, cs:g_pfnResultLoggingCallback
0x180006d6a  test    rax, rax
0x180006d6d  jz      short loc_180006D86
0x180006d6f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006d76  jnz     short loc_180006D86
0x180006d78  mov     r8d, ebp
0x180006d7b  mov     rdx, rsi
0x180006d7e  mov     rcx, rbx
0x180006d81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d86  cmp     [rsi], di
0x180006d89  jnz     short loc_180006D99
0x180006d8b  mov     r8, rbx; unsigned __int64
0x180006d8e  mov     rdx, rbp; unsigned __int16 *
0x180006d91  mov     rcx, rsi; this
0x180006d94  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006d99  mov     rcx, rsi; lpOutputString
0x180006d9c  call    cs:__imp_OutputDebugStringW
0x180006da2  test    byte ptr [rbx+4], 4
0x180006da6  jnz     short loc_180006DB1
0x180006da8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006daf  jz      short loc_180006DC3
0x180006db1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006db8  test    rax, rax
0x180006dbb  jz      short loc_180006DC3
0x180006dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dc2  nop
0x180006dc3  mov     rbx, [rsp+78h+arg_10]
0x180006dcb  add     rsp, 40h
0x180006dcf  pop     r15
0x180006dd1  pop     r14
0x180006dd3  pop     r13
0x180006dd5  pop     r12
0x180006dd7  pop     rdi
0x180006dd8  pop     rsi
0x180006dd9  pop     rbp
0x180006dda  retn
0x180006ddb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
