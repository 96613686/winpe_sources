# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006ae0`
- end: `0x180006dd9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002e18`

## callees

- `0x180002854`
- `0x180006054`
- `0x18000680c`
- `0x180006ae0`
- `0x180007794`
- `0x1800077b0`
- `0x1800078e0`
- `0x1800078fc`
- `0x18000b848`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c03`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006d22`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006d22`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006d94`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006d94`

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
0x180006ae0  mov     [rsp+arg_10], rbx
0x180006ae5  mov     [rsp+arg_8], edx
0x180006ae9  mov     [rsp+arg_0], rcx
0x180006aee  push    rbp
0x180006aef  push    rsi
0x180006af0  push    rdi
0x180006af1  push    r12
0x180006af3  push    r13
0x180006af5  push    r14
0x180006af7  push    r15
0x180006af9  sub     rsp, 40h
0x180006afd  mov     r12, r9
0x180006b00  mov     r13, r8
0x180006b03  mov     r10, rcx
0x180006b06  xor     eax, eax
0x180006b08  mov     rsi, [rsp+78h+lpOutputString]
0x180006b10  mov     [rsi], ax
0x180006b13  mov     rax, [rsp+78h+arg_60]
0x180006b1b  mov     byte ptr [rax], 0
0x180006b1e  mov     r14, [rsp+78h+arg_38]
0x180006b26  mov     edi, [r14]
0x180006b29  mov     rbx, [rsp+78h+arg_78]
0x180006b31  mov     [rbx+8], edi
0x180006b34  mov     eax, [r14+4]
0x180006b38  mov     [rbx+0Ch], eax
0x180006b3b  xor     ebp, ebp
0x180006b3d  mov     r15d, [rsp+78h+arg_30]
0x180006b45  mov     ecx, r15d
0x180006b48  test    r15d, r15d
0x180006b4b  jz      short loc_180006BB3
0x180006b4d  sub     ecx, 1
0x180006b50  jz      short loc_180006BAA
0x180006b52  sub     ecx, 1
0x180006b55  jz      short loc_180006B65
0x180006b57  cmp     ecx, 1
0x180006b5a  jnz     short loc_180006BBC
0x180006b5c  mov     ecx, edi; this
0x180006b5e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006b63  jmp     short loc_180006BBA
0x180006b65  test    edi, edi
0x180006b67  js      short loc_180006BA1
0x180006b69  mov     edi, 8007029Ch
0x180006b6e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006b72  mov     rax, [rsp+78h+arg_28]
0x180006b7a  mov     [rsp+78h+var_50], rax; __int64
0x180006b7f  mov     rax, [rsp+78h+arg_20]
0x180006b87  mov     [rsp+78h+var_58], rax; __int64
0x180006b8c  mov     rcx, r10; int
0x180006b8f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006b94  mov     [rbx+8], edi
0x180006b97  mov     ecx, edi; this
0x180006b99  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006b9e  mov     [rbx+0Ch], eax
0x180006ba1  mov     ecx, edi; this
0x180006ba3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006ba8  jmp     short loc_180006BBA
0x180006baa  mov     ecx, edi; this
0x180006bac  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006bb1  jmp     short loc_180006BBA
0x180006bb3  mov     ecx, edi; this
0x180006bb5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006bba  mov     ebp, eax
0x180006bbc  mov     [rbx], r15d
0x180006bbf  mov     eax, [rsp+78h+arg_70]
0x180006bc6  mov     [rbx+4], eax
0x180006bc9  cmp     dword ptr [r14+8], 1
0x180006bce  jnz     short loc_180006BD6
0x180006bd0  or      eax, 8
0x180006bd3  mov     [rbx+4], eax
0x180006bd6  mov     eax, 1
0x180006bdb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006be3  inc     eax
0x180006be5  mov     [rbx+10h], eax
0x180006be8  mov     rax, [rsp+78h+arg_40]
0x180006bf0  xor     edi, edi
0x180006bf2  test    rax, rax
0x180006bf5  jz      short loc_180006BFC
0x180006bf7  cmp     [rax], di
0x180006bfa  jnz     short loc_180006BFF
0x180006bfc  mov     rax, rdi
0x180006bff  mov     [rbx+18h], rax
0x180006c03  call    cs:__imp_GetCurrentThreadId
0x180006c09  mov     [rbx+20h], eax
0x180006c0c  mov     [rbx+38h], r13
0x180006c10  mov     eax, [rsp+78h+arg_8]
0x180006c17  mov     [rbx+40h], eax
0x180006c1a  mov     [rbx+44h], ebp
0x180006c1d  mov     rax, [rsp+78h+arg_20]
0x180006c25  mov     [rbx+28h], rax
0x180006c29  mov     [rbx+30h], r12
0x180006c2d  mov     rax, [rsp+78h+arg_28]
0x180006c35  mov     [rbx+88h], rax
0x180006c3c  mov     rax, [rsp+78h+arg_0]
0x180006c44  mov     [rbx+90h], rax
0x180006c4b  mov     [rbx+48h], rdi
0x180006c4f  xorps   xmm0, xmm0
0x180006c52  xor     eax, eax
0x180006c54  movups  xmmword ptr [rbx+68h], xmm0
0x180006c58  mov     [rbx+78h], rax
0x180006c5c  movups  xmmword ptr [rbx+50h], xmm0
0x180006c60  mov     [rbx+60h], rax
0x180006c64  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006c6b  test    rax, rax
0x180006c6e  jz      short loc_180006C77
0x180006c70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c75  jmp     short loc_180006C7A
0x180006c77  mov     rax, rdi
0x180006c7a  mov     [rbx+80h], rax
0x180006c81  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006c88  test    rax, rax
0x180006c8b  jz      short loc_180006C95
0x180006c8d  mov     rcx, rbx
0x180006c90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c95  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006c9c  test    rax, rax
0x180006c9f  jz      short loc_180006CB7
0x180006ca1  mov     r8d, 400h
0x180006ca7  mov     rdx, [rsp+78h+arg_60]
0x180006caf  mov     rcx, rbx
0x180006cb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cb7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006cbe  test    rax, rax
0x180006cc1  jz      short loc_180006CCB
0x180006cc3  mov     rcx, rbx
0x180006cc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ccb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006cd2  test    rax, rax
0x180006cd5  jz      short loc_180006CE5
0x180006cd7  test    byte ptr [rbx+4], 2
0x180006cdb  jnz     short loc_180006CE5
0x180006cdd  mov     rcx, rbx
0x180006ce0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ce5  cmp     [rbx+8], edi
0x180006ce8  jl      short loc_180006D04
0x180006cea  cmp     r15d, 3
0x180006cee  jnz     loc_180006DD3
0x180006cf4  mov     ecx, 8000FFFFh; this
0x180006cf9  mov     [rbx+8], ecx
0x180006cfc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006d01  mov     [rbx+0Ch], eax
0x180006d04  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006d0b  jnz     short loc_180006D2C
0x180006d0d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006d14  test    rax, rax
0x180006d17  jz      short loc_180006D22
0x180006d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d1e  test    al, al
0x180006d20  jmp     short loc_180006D2A
0x180006d22  call    cs:__imp_IsDebuggerPresent
0x180006d28  test    eax, eax
0x180006d2a  jz      short loc_180006D32
0x180006d2c  test    byte ptr [rbx+4], 2
0x180006d30  jz      short loc_180006D56
0x180006d32  mov     rax, cs:g_pfnResultLoggingCallback
0x180006d39  test    rax, rax
0x180006d3c  jz      short loc_180006D9A
0x180006d3e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006d45  jnz     short loc_180006D9A
0x180006d47  xor     r8d, r8d
0x180006d4a  xor     edx, edx
0x180006d4c  mov     rcx, rbx
0x180006d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d54  jmp     short loc_180006D9A
0x180006d56  mov     ebp, 800h
0x180006d5b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006d62  test    rax, rax
0x180006d65  jz      short loc_180006D7E
0x180006d67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006d6e  jnz     short loc_180006D7E
0x180006d70  mov     r8d, ebp
0x180006d73  mov     rdx, rsi
0x180006d76  mov     rcx, rbx
0x180006d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d7e  cmp     [rsi], di
0x180006d81  jnz     short loc_180006D91
0x180006d83  mov     r8, rbx; unsigned __int64
0x180006d86  mov     rdx, rbp; unsigned __int16 *
0x180006d89  mov     rcx, rsi; this
0x180006d8c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006d91  mov     rcx, rsi; lpOutputString
0x180006d94  call    cs:__imp_OutputDebugStringW
0x180006d9a  test    byte ptr [rbx+4], 4
0x180006d9e  jnz     short loc_180006DA9
0x180006da0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006da7  jz      short loc_180006DBB
0x180006da9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006db0  test    rax, rax
0x180006db3  jz      short loc_180006DBB
0x180006db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dba  nop
0x180006dbb  mov     rbx, [rsp+78h+arg_10]
0x180006dc3  add     rsp, 40h
0x180006dc7  pop     r15
0x180006dc9  pop     r14
0x180006dcb  pop     r13
0x180006dcd  pop     r12
0x180006dcf  pop     rdi
0x180006dd0  pop     rsi
0x180006dd1  pop     rbp
0x180006dd2  retn
0x180006dd3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
