# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006ab0`
- end: `0x180006dbc`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180003a44`
- `0x180003dc4`
- `0x18000db60`

## callees

- `0x18000397c`
- `0x180005d44`
- `0x180006620`
- `0x180006ab0`
- `0x180007a24`
- `0x180007a50`
- `0x180007bf0`
- `0x180007c10`
- `0x180009c78`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006bd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006bd3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006cf8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006cf8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006d70`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006d70`

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
0x180006ab0  mov     [rsp+arg_10], rbx
0x180006ab5  mov     [rsp+arg_8], edx
0x180006ab9  mov     [rsp+arg_0], rcx
0x180006abe  push    rbp
0x180006abf  push    rsi
0x180006ac0  push    rdi
0x180006ac1  push    r12
0x180006ac3  push    r13
0x180006ac5  push    r14
0x180006ac7  push    r15
0x180006ac9  sub     rsp, 40h
0x180006acd  mov     r12, r9
0x180006ad0  mov     r13, r8
0x180006ad3  mov     r10, rcx
0x180006ad6  xor     eax, eax
0x180006ad8  mov     rsi, [rsp+78h+lpOutputString]
0x180006ae0  mov     [rsi], ax
0x180006ae3  mov     rax, [rsp+78h+arg_60]
0x180006aeb  mov     byte ptr [rax], 0
0x180006aee  mov     r14, [rsp+78h+arg_38]
0x180006af6  mov     edi, [r14]
0x180006af9  mov     rbx, [rsp+78h+arg_78]
0x180006b01  mov     [rbx+8], edi
0x180006b04  mov     eax, [r14+4]
0x180006b08  mov     [rbx+0Ch], eax
0x180006b0b  xor     ebp, ebp
0x180006b0d  mov     r15d, [rsp+78h+arg_30]
0x180006b15  mov     ecx, r15d
0x180006b18  test    r15d, r15d
0x180006b1b  jz      short loc_180006B83
0x180006b1d  sub     ecx, 1
0x180006b20  jz      short loc_180006B7A
0x180006b22  sub     ecx, 1
0x180006b25  jz      short loc_180006B35
0x180006b27  cmp     ecx, 1
0x180006b2a  jnz     short loc_180006B8C
0x180006b2c  mov     ecx, edi; this
0x180006b2e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006b33  jmp     short loc_180006B8A
0x180006b35  test    edi, edi
0x180006b37  js      short loc_180006B71
0x180006b39  mov     edi, 8007029Ch
0x180006b3e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006b42  mov     rax, [rsp+78h+arg_28]
0x180006b4a  mov     [rsp+78h+var_50], rax; __int64
0x180006b4f  mov     rax, [rsp+78h+arg_20]
0x180006b57  mov     [rsp+78h+var_58], rax; __int64
0x180006b5c  mov     rcx, r10; int
0x180006b5f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006b64  mov     [rbx+8], edi
0x180006b67  mov     ecx, edi; this
0x180006b69  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006b6e  mov     [rbx+0Ch], eax
0x180006b71  mov     ecx, edi; this
0x180006b73  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006b78  jmp     short loc_180006B8A
0x180006b7a  mov     ecx, edi; this
0x180006b7c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006b81  jmp     short loc_180006B8A
0x180006b83  mov     ecx, edi; this
0x180006b85  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006b8a  mov     ebp, eax
0x180006b8c  mov     [rbx], r15d
0x180006b8f  mov     eax, [rsp+78h+arg_70]
0x180006b96  mov     [rbx+4], eax
0x180006b99  cmp     dword ptr [r14+8], 1
0x180006b9e  jnz     short loc_180006BA6
0x180006ba0  or      eax, 8
0x180006ba3  mov     [rbx+4], eax
0x180006ba6  mov     eax, 1
0x180006bab  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006bb3  inc     eax
0x180006bb5  mov     [rbx+10h], eax
0x180006bb8  mov     rax, [rsp+78h+arg_40]
0x180006bc0  xor     edi, edi
0x180006bc2  test    rax, rax
0x180006bc5  jz      short loc_180006BCC
0x180006bc7  cmp     [rax], di
0x180006bca  jnz     short loc_180006BCF
0x180006bcc  mov     rax, rdi
0x180006bcf  mov     [rbx+18h], rax
0x180006bd3  call    cs:__imp_GetCurrentThreadId
0x180006bda  nop     dword ptr [rax+rax+00h]
0x180006bdf  mov     [rbx+20h], eax
0x180006be2  mov     [rbx+38h], r13
0x180006be6  mov     eax, [rsp+78h+arg_8]
0x180006bed  mov     [rbx+40h], eax
0x180006bf0  mov     [rbx+44h], ebp
0x180006bf3  mov     rax, [rsp+78h+arg_20]
0x180006bfb  mov     [rbx+28h], rax
0x180006bff  mov     [rbx+30h], r12
0x180006c03  mov     rax, [rsp+78h+arg_28]
0x180006c0b  mov     [rbx+88h], rax
0x180006c12  mov     rax, [rsp+78h+arg_0]
0x180006c1a  mov     [rbx+90h], rax
0x180006c21  mov     [rbx+48h], rdi
0x180006c25  xorps   xmm0, xmm0
0x180006c28  xor     eax, eax
0x180006c2a  movups  xmmword ptr [rbx+68h], xmm0
0x180006c2e  mov     [rbx+78h], rax
0x180006c32  movups  xmmword ptr [rbx+50h], xmm0
0x180006c36  mov     [rbx+60h], rax
0x180006c3a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006c41  test    rax, rax
0x180006c44  jz      short loc_180006C4D
0x180006c46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c4b  jmp     short loc_180006C50
0x180006c4d  mov     rax, rdi
0x180006c50  mov     [rbx+80h], rax
0x180006c57  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006c5e  test    rax, rax
0x180006c61  jz      short loc_180006C6B
0x180006c63  mov     rcx, rbx
0x180006c66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c6b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006c72  test    rax, rax
0x180006c75  jz      short loc_180006C8D
0x180006c77  mov     r8d, 400h
0x180006c7d  mov     rdx, [rsp+78h+arg_60]
0x180006c85  mov     rcx, rbx
0x180006c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c8d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006c94  test    rax, rax
0x180006c97  jz      short loc_180006CA1
0x180006c99  mov     rcx, rbx
0x180006c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ca1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006ca8  test    rax, rax
0x180006cab  jz      short loc_180006CBB
0x180006cad  test    byte ptr [rbx+4], 2
0x180006cb1  jnz     short loc_180006CBB
0x180006cb3  mov     rcx, rbx
0x180006cb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cbb  cmp     [rbx+8], edi
0x180006cbe  jl      short loc_180006CDA
0x180006cc0  cmp     r15d, 3
0x180006cc4  jnz     loc_180006DB6
0x180006cca  mov     ecx, 8000FFFFh; this
0x180006ccf  mov     [rbx+8], ecx
0x180006cd2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006cd7  mov     [rbx+0Ch], eax
0x180006cda  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006ce1  jnz     short loc_180006D08
0x180006ce3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006cea  test    rax, rax
0x180006ced  jz      short loc_180006CF8
0x180006cef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cf4  test    al, al
0x180006cf6  jmp     short loc_180006D06
0x180006cf8  call    cs:__imp_IsDebuggerPresent
0x180006cff  nop     dword ptr [rax+rax+00h]
0x180006d04  test    eax, eax
0x180006d06  jz      short loc_180006D0E
0x180006d08  test    byte ptr [rbx+4], 2
0x180006d0c  jz      short loc_180006D32
0x180006d0e  mov     rax, cs:g_pfnResultLoggingCallback
0x180006d15  test    rax, rax
0x180006d18  jz      short loc_180006D7C
0x180006d1a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006d21  jnz     short loc_180006D7C
0x180006d23  xor     r8d, r8d
0x180006d26  xor     edx, edx
0x180006d28  mov     rcx, rbx
0x180006d2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d30  jmp     short loc_180006D7C
0x180006d32  mov     ebp, 800h
0x180006d37  mov     rax, cs:g_pfnResultLoggingCallback
0x180006d3e  test    rax, rax
0x180006d41  jz      short loc_180006D5A
0x180006d43  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006d4a  jnz     short loc_180006D5A
0x180006d4c  mov     r8d, ebp
0x180006d4f  mov     rdx, rsi
0x180006d52  mov     rcx, rbx
0x180006d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d5a  cmp     [rsi], di
0x180006d5d  jnz     short loc_180006D6D
0x180006d5f  mov     r8, rbx; unsigned __int64
0x180006d62  mov     rdx, rbp; unsigned __int16 *
0x180006d65  mov     rcx, rsi; this
0x180006d68  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006d6d  mov     rcx, rsi; lpOutputString
0x180006d70  call    cs:__imp_OutputDebugStringW
0x180006d77  nop     dword ptr [rax+rax+00h]
0x180006d7c  test    byte ptr [rbx+4], 4
0x180006d80  jnz     short loc_180006D8B
0x180006d82  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006d89  jz      short loc_180006D9D
0x180006d8b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006d92  test    rax, rax
0x180006d95  jz      short loc_180006D9D
0x180006d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d9c  nop
0x180006d9d  mov     rbx, [rsp+78h+arg_10]
0x180006da5  add     rsp, 40h
0x180006da9  pop     r15
0x180006dab  pop     r14
0x180006dad  pop     r13
0x180006daf  pop     r12
0x180006db1  pop     rdi
0x180006db2  pop     rsi
0x180006db3  pop     rbp
0x180006db4  retn
0x180006db6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
