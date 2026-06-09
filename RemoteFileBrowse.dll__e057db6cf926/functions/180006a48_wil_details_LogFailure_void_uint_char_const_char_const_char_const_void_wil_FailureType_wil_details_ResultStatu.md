# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006a48`
- end: `0x180006d41`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005250`

## callees

- `0x180003324`
- `0x18000370c`
- `0x180003ab0`
- `0x1800048d4`
- `0x180006a48`
- `0x180006f10`
- `0x180006f2c`
- `0x180006f48`
- `0x180007298`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006b6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006b6b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006c8a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006c8a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006cfc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006cfc`

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
0x180006a48  mov     [rsp+arg_10], rbx
0x180006a4d  mov     [rsp+arg_8], edx
0x180006a51  mov     [rsp+arg_0], rcx
0x180006a56  push    rbp
0x180006a57  push    rsi
0x180006a58  push    rdi
0x180006a59  push    r12
0x180006a5b  push    r13
0x180006a5d  push    r14
0x180006a5f  push    r15
0x180006a61  sub     rsp, 40h
0x180006a65  mov     r12, r9
0x180006a68  mov     r13, r8
0x180006a6b  mov     r10, rcx
0x180006a6e  xor     eax, eax
0x180006a70  mov     rsi, [rsp+78h+lpOutputString]
0x180006a78  mov     [rsi], ax
0x180006a7b  mov     rax, [rsp+78h+arg_60]
0x180006a83  mov     byte ptr [rax], 0
0x180006a86  mov     r14, [rsp+78h+arg_38]
0x180006a8e  mov     edi, [r14]
0x180006a91  mov     rbx, [rsp+78h+arg_78]
0x180006a99  mov     [rbx+8], edi
0x180006a9c  mov     eax, [r14+4]
0x180006aa0  mov     [rbx+0Ch], eax
0x180006aa3  xor     ebp, ebp
0x180006aa5  mov     r15d, [rsp+78h+arg_30]
0x180006aad  mov     ecx, r15d
0x180006ab0  test    r15d, r15d
0x180006ab3  jz      short loc_180006B1B
0x180006ab5  sub     ecx, 1
0x180006ab8  jz      short loc_180006B12
0x180006aba  sub     ecx, 1
0x180006abd  jz      short loc_180006ACD
0x180006abf  cmp     ecx, 1
0x180006ac2  jnz     short loc_180006B24
0x180006ac4  mov     ecx, edi; this
0x180006ac6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006acb  jmp     short loc_180006B22
0x180006acd  test    edi, edi
0x180006acf  js      short loc_180006B09
0x180006ad1  mov     edi, 8007029Ch
0x180006ad6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006ada  mov     rax, [rsp+78h+arg_28]
0x180006ae2  mov     [rsp+78h+var_50], rax; __int64
0x180006ae7  mov     rax, [rsp+78h+arg_20]
0x180006aef  mov     [rsp+78h+var_58], rax; __int64
0x180006af4  mov     rcx, r10; int
0x180006af7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006afc  mov     [rbx+8], edi
0x180006aff  mov     ecx, edi; this
0x180006b01  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006b06  mov     [rbx+0Ch], eax
0x180006b09  mov     ecx, edi; this
0x180006b0b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006b10  jmp     short loc_180006B22
0x180006b12  mov     ecx, edi; this
0x180006b14  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006b19  jmp     short loc_180006B22
0x180006b1b  mov     ecx, edi; this
0x180006b1d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006b22  mov     ebp, eax
0x180006b24  mov     [rbx], r15d
0x180006b27  mov     eax, [rsp+78h+arg_70]
0x180006b2e  mov     [rbx+4], eax
0x180006b31  cmp     dword ptr [r14+8], 1
0x180006b36  jnz     short loc_180006B3E
0x180006b38  or      eax, 8
0x180006b3b  mov     [rbx+4], eax
0x180006b3e  mov     eax, 1
0x180006b43  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006b4b  inc     eax
0x180006b4d  mov     [rbx+10h], eax
0x180006b50  mov     rax, [rsp+78h+arg_40]
0x180006b58  xor     edi, edi
0x180006b5a  test    rax, rax
0x180006b5d  jz      short loc_180006B64
0x180006b5f  cmp     [rax], di
0x180006b62  jnz     short loc_180006B67
0x180006b64  mov     rax, rdi
0x180006b67  mov     [rbx+18h], rax
0x180006b6b  call    cs:__imp_GetCurrentThreadId
0x180006b71  mov     [rbx+20h], eax
0x180006b74  mov     [rbx+38h], r13
0x180006b78  mov     eax, [rsp+78h+arg_8]
0x180006b7f  mov     [rbx+40h], eax
0x180006b82  mov     [rbx+44h], ebp
0x180006b85  mov     rax, [rsp+78h+arg_20]
0x180006b8d  mov     [rbx+28h], rax
0x180006b91  mov     [rbx+30h], r12
0x180006b95  mov     rax, [rsp+78h+arg_28]
0x180006b9d  mov     [rbx+88h], rax
0x180006ba4  mov     rax, [rsp+78h+arg_0]
0x180006bac  mov     [rbx+90h], rax
0x180006bb3  mov     [rbx+48h], rdi
0x180006bb7  xorps   xmm0, xmm0
0x180006bba  xor     eax, eax
0x180006bbc  movups  xmmword ptr [rbx+68h], xmm0
0x180006bc0  mov     [rbx+78h], rax
0x180006bc4  movups  xmmword ptr [rbx+50h], xmm0
0x180006bc8  mov     [rbx+60h], rax
0x180006bcc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006bd3  test    rax, rax
0x180006bd6  jz      short loc_180006BDF
0x180006bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bdd  jmp     short loc_180006BE2
0x180006bdf  mov     rax, rdi
0x180006be2  mov     [rbx+80h], rax
0x180006be9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006bf0  test    rax, rax
0x180006bf3  jz      short loc_180006BFD
0x180006bf5  mov     rcx, rbx
0x180006bf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bfd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006c04  test    rax, rax
0x180006c07  jz      short loc_180006C1F
0x180006c09  mov     r8d, 400h
0x180006c0f  mov     rdx, [rsp+78h+arg_60]
0x180006c17  mov     rcx, rbx
0x180006c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c1f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006c26  test    rax, rax
0x180006c29  jz      short loc_180006C33
0x180006c2b  mov     rcx, rbx
0x180006c2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c33  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006c3a  test    rax, rax
0x180006c3d  jz      short loc_180006C4D
0x180006c3f  test    byte ptr [rbx+4], 2
0x180006c43  jnz     short loc_180006C4D
0x180006c45  mov     rcx, rbx
0x180006c48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c4d  cmp     [rbx+8], edi
0x180006c50  jl      short loc_180006C6C
0x180006c52  cmp     r15d, 3
0x180006c56  jnz     loc_180006D3B
0x180006c5c  mov     ecx, 8000FFFFh; this
0x180006c61  mov     [rbx+8], ecx
0x180006c64  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006c69  mov     [rbx+0Ch], eax
0x180006c6c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006c73  jnz     short loc_180006C94
0x180006c75  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006c7c  test    rax, rax
0x180006c7f  jz      short loc_180006C8A
0x180006c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c86  test    al, al
0x180006c88  jmp     short loc_180006C92
0x180006c8a  call    cs:__imp_IsDebuggerPresent
0x180006c90  test    eax, eax
0x180006c92  jz      short loc_180006C9A
0x180006c94  test    byte ptr [rbx+4], 2
0x180006c98  jz      short loc_180006CBE
0x180006c9a  mov     rax, cs:g_pfnResultLoggingCallback
0x180006ca1  test    rax, rax
0x180006ca4  jz      short loc_180006D02
0x180006ca6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006cad  jnz     short loc_180006D02
0x180006caf  xor     r8d, r8d
0x180006cb2  xor     edx, edx
0x180006cb4  mov     rcx, rbx
0x180006cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cbc  jmp     short loc_180006D02
0x180006cbe  mov     ebp, 800h
0x180006cc3  mov     rax, cs:g_pfnResultLoggingCallback
0x180006cca  test    rax, rax
0x180006ccd  jz      short loc_180006CE6
0x180006ccf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006cd6  jnz     short loc_180006CE6
0x180006cd8  mov     r8d, ebp
0x180006cdb  mov     rdx, rsi
0x180006cde  mov     rcx, rbx
0x180006ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ce6  cmp     [rsi], di
0x180006ce9  jnz     short loc_180006CF9
0x180006ceb  mov     r8, rbx; unsigned __int64
0x180006cee  mov     rdx, rbp; unsigned __int16 *
0x180006cf1  mov     rcx, rsi; this
0x180006cf4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006cf9  mov     rcx, rsi; lpOutputString
0x180006cfc  call    cs:__imp_OutputDebugStringW
0x180006d02  test    byte ptr [rbx+4], 4
0x180006d06  jnz     short loc_180006D11
0x180006d08  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006d0f  jz      short loc_180006D23
0x180006d11  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006d18  test    rax, rax
0x180006d1b  jz      short loc_180006D23
0x180006d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d22  nop
0x180006d23  mov     rbx, [rsp+78h+arg_10]
0x180006d2b  add     rsp, 40h
0x180006d2f  pop     r15
0x180006d31  pop     r14
0x180006d33  pop     r13
0x180006d35  pop     r12
0x180006d37  pop     rdi
0x180006d38  pop     rsi
0x180006d39  pop     rbp
0x180006d3a  retn
0x180006d3b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
