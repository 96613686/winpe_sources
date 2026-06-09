# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140008aa4`
- end: `0x140008d9d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140006a30`

## callees

- `0x14000612c`
- `0x140007f74`
- `0x14000887c`
- `0x140008aa4`
- `0x1400091a0`
- `0x1400091c0`
- `0x1400091d4`
- `0x1400091f0`
- `0x14000a698`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008bc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140008bc7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140008ce6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140008ce6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140008d58`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140008d58`

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
0x140008aa4  mov     [rsp+arg_10], rbx
0x140008aa9  mov     [rsp+arg_8], edx
0x140008aad  mov     [rsp+arg_0], rcx
0x140008ab2  push    rbp
0x140008ab3  push    rsi
0x140008ab4  push    rdi
0x140008ab5  push    r12
0x140008ab7  push    r13
0x140008ab9  push    r14
0x140008abb  push    r15
0x140008abd  sub     rsp, 40h
0x140008ac1  mov     r12, r9
0x140008ac4  mov     r13, r8
0x140008ac7  mov     r10, rcx
0x140008aca  xor     eax, eax
0x140008acc  mov     rsi, [rsp+78h+lpOutputString]
0x140008ad4  mov     [rsi], ax
0x140008ad7  mov     rax, [rsp+78h+arg_60]
0x140008adf  mov     byte ptr [rax], 0
0x140008ae2  mov     r14, [rsp+78h+arg_38]
0x140008aea  mov     edi, [r14]
0x140008aed  mov     rbx, [rsp+78h+arg_78]
0x140008af5  mov     [rbx+8], edi
0x140008af8  mov     eax, [r14+4]
0x140008afc  mov     [rbx+0Ch], eax
0x140008aff  xor     ebp, ebp
0x140008b01  mov     r15d, [rsp+78h+arg_30]
0x140008b09  mov     ecx, r15d
0x140008b0c  test    r15d, r15d
0x140008b0f  jz      short loc_140008B77
0x140008b11  sub     ecx, 1
0x140008b14  jz      short loc_140008B6E
0x140008b16  sub     ecx, 1
0x140008b19  jz      short loc_140008B29
0x140008b1b  cmp     ecx, 1
0x140008b1e  jnz     short loc_140008B80
0x140008b20  mov     ecx, edi; this
0x140008b22  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140008b27  jmp     short loc_140008B7E
0x140008b29  test    edi, edi
0x140008b2b  js      short loc_140008B65
0x140008b2d  mov     edi, 8007029Ch
0x140008b32  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140008b36  mov     rax, [rsp+78h+arg_28]
0x140008b3e  mov     [rsp+78h+var_50], rax; __int64
0x140008b43  mov     rax, [rsp+78h+arg_20]
0x140008b4b  mov     [rsp+78h+var_58], rax; __int64
0x140008b50  mov     rcx, r10; int
0x140008b53  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140008b58  mov     [rbx+8], edi
0x140008b5b  mov     ecx, edi; this
0x140008b5d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140008b62  mov     [rbx+0Ch], eax
0x140008b65  mov     ecx, edi; this
0x140008b67  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140008b6c  jmp     short loc_140008B7E
0x140008b6e  mov     ecx, edi; this
0x140008b70  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140008b75  jmp     short loc_140008B7E
0x140008b77  mov     ecx, edi; this
0x140008b79  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140008b7e  mov     ebp, eax
0x140008b80  mov     [rbx], r15d
0x140008b83  mov     eax, [rsp+78h+arg_70]
0x140008b8a  mov     [rbx+4], eax
0x140008b8d  cmp     dword ptr [r14+8], 1
0x140008b92  jnz     short loc_140008B9A
0x140008b94  or      eax, 8
0x140008b97  mov     [rbx+4], eax
0x140008b9a  mov     eax, 1
0x140008b9f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140008ba7  inc     eax
0x140008ba9  mov     [rbx+10h], eax
0x140008bac  mov     rax, [rsp+78h+arg_40]
0x140008bb4  xor     edi, edi
0x140008bb6  test    rax, rax
0x140008bb9  jz      short loc_140008BC0
0x140008bbb  cmp     [rax], di
0x140008bbe  jnz     short loc_140008BC3
0x140008bc0  mov     rax, rdi
0x140008bc3  mov     [rbx+18h], rax
0x140008bc7  call    cs:__imp_GetCurrentThreadId
0x140008bcd  mov     [rbx+20h], eax
0x140008bd0  mov     [rbx+38h], r13
0x140008bd4  mov     eax, [rsp+78h+arg_8]
0x140008bdb  mov     [rbx+40h], eax
0x140008bde  mov     [rbx+44h], ebp
0x140008be1  mov     rax, [rsp+78h+arg_20]
0x140008be9  mov     [rbx+28h], rax
0x140008bed  mov     [rbx+30h], r12
0x140008bf1  mov     rax, [rsp+78h+arg_28]
0x140008bf9  mov     [rbx+88h], rax
0x140008c00  mov     rax, [rsp+78h+arg_0]
0x140008c08  mov     [rbx+90h], rax
0x140008c0f  mov     [rbx+48h], rdi
0x140008c13  xorps   xmm0, xmm0
0x140008c16  xor     eax, eax
0x140008c18  movups  xmmword ptr [rbx+68h], xmm0
0x140008c1c  mov     [rbx+78h], rax
0x140008c20  movups  xmmword ptr [rbx+50h], xmm0
0x140008c24  mov     [rbx+60h], rax
0x140008c28  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140008c2f  test    rax, rax
0x140008c32  jz      short loc_140008C3B
0x140008c34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c39  jmp     short loc_140008C3E
0x140008c3b  mov     rax, rdi
0x140008c3e  mov     [rbx+80h], rax
0x140008c45  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140008c4c  test    rax, rax
0x140008c4f  jz      short loc_140008C59
0x140008c51  mov     rcx, rbx
0x140008c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c59  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140008c60  test    rax, rax
0x140008c63  jz      short loc_140008C7B
0x140008c65  mov     r8d, 400h
0x140008c6b  mov     rdx, [rsp+78h+arg_60]
0x140008c73  mov     rcx, rbx
0x140008c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c7b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140008c82  test    rax, rax
0x140008c85  jz      short loc_140008C8F
0x140008c87  mov     rcx, rbx
0x140008c8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008c8f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140008c96  test    rax, rax
0x140008c99  jz      short loc_140008CA9
0x140008c9b  test    byte ptr [rbx+4], 2
0x140008c9f  jnz     short loc_140008CA9
0x140008ca1  mov     rcx, rbx
0x140008ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008ca9  cmp     [rbx+8], edi
0x140008cac  jl      short loc_140008CC8
0x140008cae  cmp     r15d, 3
0x140008cb2  jnz     loc_140008D97
0x140008cb8  mov     ecx, 8000FFFFh; this
0x140008cbd  mov     [rbx+8], ecx
0x140008cc0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140008cc5  mov     [rbx+0Ch], eax
0x140008cc8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140008ccf  jnz     short loc_140008CF0
0x140008cd1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140008cd8  test    rax, rax
0x140008cdb  jz      short loc_140008CE6
0x140008cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008ce2  test    al, al
0x140008ce4  jmp     short loc_140008CEE
0x140008ce6  call    cs:__imp_IsDebuggerPresent
0x140008cec  test    eax, eax
0x140008cee  jz      short loc_140008CF6
0x140008cf0  test    byte ptr [rbx+4], 2
0x140008cf4  jz      short loc_140008D1A
0x140008cf6  mov     rax, cs:g_pfnResultLoggingCallback
0x140008cfd  test    rax, rax
0x140008d00  jz      short loc_140008D5E
0x140008d02  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140008d09  jnz     short loc_140008D5E
0x140008d0b  xor     r8d, r8d
0x140008d0e  xor     edx, edx
0x140008d10  mov     rcx, rbx
0x140008d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008d18  jmp     short loc_140008D5E
0x140008d1a  mov     ebp, 800h
0x140008d1f  mov     rax, cs:g_pfnResultLoggingCallback
0x140008d26  test    rax, rax
0x140008d29  jz      short loc_140008D42
0x140008d2b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140008d32  jnz     short loc_140008D42
0x140008d34  mov     r8d, ebp
0x140008d37  mov     rdx, rsi
0x140008d3a  mov     rcx, rbx
0x140008d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008d42  cmp     [rsi], di
0x140008d45  jnz     short loc_140008D55
0x140008d47  mov     r8, rbx; unsigned __int64
0x140008d4a  mov     rdx, rbp; unsigned __int16 *
0x140008d4d  mov     rcx, rsi; this
0x140008d50  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140008d55  mov     rcx, rsi; lpOutputString
0x140008d58  call    cs:__imp_OutputDebugStringW
0x140008d5e  test    byte ptr [rbx+4], 4
0x140008d62  jnz     short loc_140008D6D
0x140008d64  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140008d6b  jz      short loc_140008D7F
0x140008d6d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140008d74  test    rax, rax
0x140008d77  jz      short loc_140008D7F
0x140008d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008d7e  nop
0x140008d7f  mov     rbx, [rsp+78h+arg_10]
0x140008d87  add     rsp, 40h
0x140008d8b  pop     r15
0x140008d8d  pop     r14
0x140008d8f  pop     r13
0x140008d91  pop     r12
0x140008d93  pop     rdi
0x140008d94  pop     rsi
0x140008d95  pop     rbp
0x140008d96  retn
0x140008d97  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
