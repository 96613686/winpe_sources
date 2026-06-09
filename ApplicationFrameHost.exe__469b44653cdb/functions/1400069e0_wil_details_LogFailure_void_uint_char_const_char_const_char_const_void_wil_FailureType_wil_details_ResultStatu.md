# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400069e0`
- end: `0x140006cd9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140004534`
- `0x140004878`

## callees

- `0x1400025e0`
- `0x140004464`
- `0x1400060a4`
- `0x1400069e0`
- `0x14000770c`
- `0x140007730`
- `0x140007880`
- `0x14000789c`
- `0x140009554`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006b03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006b03`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006c94`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006c94`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006c22`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006c22`

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
0x1400069e0  mov     [rsp+arg_10], rbx
0x1400069e5  mov     [rsp+arg_8], edx
0x1400069e9  mov     [rsp+arg_0], rcx
0x1400069ee  push    rbp
0x1400069ef  push    rsi
0x1400069f0  push    rdi
0x1400069f1  push    r12
0x1400069f3  push    r13
0x1400069f5  push    r14
0x1400069f7  push    r15
0x1400069f9  sub     rsp, 40h
0x1400069fd  mov     r12, r9
0x140006a00  mov     r13, r8
0x140006a03  mov     r10, rcx
0x140006a06  xor     eax, eax
0x140006a08  mov     rsi, [rsp+78h+lpOutputString]
0x140006a10  mov     [rsi], ax
0x140006a13  mov     rax, [rsp+78h+arg_60]
0x140006a1b  mov     byte ptr [rax], 0
0x140006a1e  mov     r14, [rsp+78h+arg_38]
0x140006a26  mov     edi, [r14]
0x140006a29  mov     rbx, [rsp+78h+arg_78]
0x140006a31  mov     [rbx+8], edi
0x140006a34  mov     eax, [r14+4]
0x140006a38  mov     [rbx+0Ch], eax
0x140006a3b  xor     ebp, ebp
0x140006a3d  mov     r15d, [rsp+78h+arg_30]
0x140006a45  mov     ecx, r15d
0x140006a48  test    r15d, r15d
0x140006a4b  jz      short loc_140006AB3
0x140006a4d  sub     ecx, 1
0x140006a50  jz      short loc_140006AAA
0x140006a52  sub     ecx, 1
0x140006a55  jz      short loc_140006A65
0x140006a57  cmp     ecx, 1
0x140006a5a  jnz     short loc_140006ABC
0x140006a5c  mov     ecx, edi; this
0x140006a5e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140006a63  jmp     short loc_140006ABA
0x140006a65  test    edi, edi
0x140006a67  js      short loc_140006AA1
0x140006a69  mov     edi, 8007029Ch
0x140006a6e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140006a72  mov     rax, [rsp+78h+arg_28]
0x140006a7a  mov     [rsp+78h+var_50], rax; __int64
0x140006a7f  mov     rax, [rsp+78h+arg_20]
0x140006a87  mov     [rsp+78h+var_58], rax; __int64
0x140006a8c  mov     rcx, r10; int
0x140006a8f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140006a94  mov     [rbx+8], edi
0x140006a97  mov     ecx, edi; this
0x140006a99  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006a9e  mov     [rbx+0Ch], eax
0x140006aa1  mov     ecx, edi; this
0x140006aa3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140006aa8  jmp     short loc_140006ABA
0x140006aaa  mov     ecx, edi; this
0x140006aac  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140006ab1  jmp     short loc_140006ABA
0x140006ab3  mov     ecx, edi; this
0x140006ab5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140006aba  mov     ebp, eax
0x140006abc  mov     [rbx], r15d
0x140006abf  mov     eax, [rsp+78h+arg_70]
0x140006ac6  mov     [rbx+4], eax
0x140006ac9  cmp     dword ptr [r14+8], 1
0x140006ace  jnz     short loc_140006AD6
0x140006ad0  or      eax, 8
0x140006ad3  mov     [rbx+4], eax
0x140006ad6  mov     eax, 1
0x140006adb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006ae3  inc     eax
0x140006ae5  mov     [rbx+10h], eax
0x140006ae8  mov     rax, [rsp+78h+arg_40]
0x140006af0  xor     edi, edi
0x140006af2  test    rax, rax
0x140006af5  jz      short loc_140006AFC
0x140006af7  cmp     [rax], di
0x140006afa  jnz     short loc_140006AFF
0x140006afc  mov     rax, rdi
0x140006aff  mov     [rbx+18h], rax
0x140006b03  call    cs:__imp_GetCurrentThreadId
0x140006b09  mov     [rbx+20h], eax
0x140006b0c  mov     [rbx+38h], r13
0x140006b10  mov     eax, [rsp+78h+arg_8]
0x140006b17  mov     [rbx+40h], eax
0x140006b1a  mov     [rbx+44h], ebp
0x140006b1d  mov     rax, [rsp+78h+arg_20]
0x140006b25  mov     [rbx+28h], rax
0x140006b29  mov     [rbx+30h], r12
0x140006b2d  mov     rax, [rsp+78h+arg_28]
0x140006b35  mov     [rbx+88h], rax
0x140006b3c  mov     rax, [rsp+78h+arg_0]
0x140006b44  mov     [rbx+90h], rax
0x140006b4b  mov     [rbx+48h], rdi
0x140006b4f  xorps   xmm0, xmm0
0x140006b52  xor     eax, eax
0x140006b54  movups  xmmword ptr [rbx+68h], xmm0
0x140006b58  mov     [rbx+78h], rax
0x140006b5c  movups  xmmword ptr [rbx+50h], xmm0
0x140006b60  mov     [rbx+60h], rax
0x140006b64  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006b6b  test    rax, rax
0x140006b6e  jz      short loc_140006B77
0x140006b70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b75  jmp     short loc_140006B7A
0x140006b77  mov     rax, rdi
0x140006b7a  mov     [rbx+80h], rax
0x140006b81  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006b88  test    rax, rax
0x140006b8b  jz      short loc_140006B95
0x140006b8d  mov     rcx, rbx
0x140006b90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b95  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140006b9c  test    rax, rax
0x140006b9f  jz      short loc_140006BB7
0x140006ba1  mov     r8d, 400h
0x140006ba7  mov     rdx, [rsp+78h+arg_60]
0x140006baf  mov     rcx, rbx
0x140006bb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006bb7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006bbe  test    rax, rax
0x140006bc1  jz      short loc_140006BCB
0x140006bc3  mov     rcx, rbx
0x140006bc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006bcb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006bd2  test    rax, rax
0x140006bd5  jz      short loc_140006BE5
0x140006bd7  test    byte ptr [rbx+4], 2
0x140006bdb  jnz     short loc_140006BE5
0x140006bdd  mov     rcx, rbx
0x140006be0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006be5  cmp     [rbx+8], edi
0x140006be8  jl      short loc_140006C04
0x140006bea  cmp     r15d, 3
0x140006bee  jnz     loc_140006CD3
0x140006bf4  mov     ecx, 8000FFFFh; this
0x140006bf9  mov     [rbx+8], ecx
0x140006bfc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006c01  mov     [rbx+0Ch], eax
0x140006c04  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140006c0b  jnz     short loc_140006C2C
0x140006c0d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006c14  test    rax, rax
0x140006c17  jz      short loc_140006C22
0x140006c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c1e  test    al, al
0x140006c20  jmp     short loc_140006C2A
0x140006c22  call    cs:__imp_IsDebuggerPresent
0x140006c28  test    eax, eax
0x140006c2a  jz      short loc_140006C32
0x140006c2c  test    byte ptr [rbx+4], 2
0x140006c30  jz      short loc_140006C56
0x140006c32  mov     rax, cs:g_pfnResultLoggingCallback
0x140006c39  test    rax, rax
0x140006c3c  jz      short loc_140006C9A
0x140006c3e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140006c45  jnz     short loc_140006C9A
0x140006c47  xor     r8d, r8d
0x140006c4a  xor     edx, edx
0x140006c4c  mov     rcx, rbx
0x140006c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c54  jmp     short loc_140006C9A
0x140006c56  mov     ebp, 800h
0x140006c5b  mov     rax, cs:g_pfnResultLoggingCallback
0x140006c62  test    rax, rax
0x140006c65  jz      short loc_140006C7E
0x140006c67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140006c6e  jnz     short loc_140006C7E
0x140006c70  mov     r8d, ebp
0x140006c73  mov     rdx, rsi
0x140006c76  mov     rcx, rbx
0x140006c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c7e  cmp     [rsi], di
0x140006c81  jnz     short loc_140006C91
0x140006c83  mov     r8, rbx; unsigned __int64
0x140006c86  mov     rdx, rbp; unsigned __int16 *
0x140006c89  mov     rcx, rsi; this
0x140006c8c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006c91  mov     rcx, rsi; lpOutputString
0x140006c94  call    cs:__imp_OutputDebugStringW
0x140006c9a  test    byte ptr [rbx+4], 4
0x140006c9e  jnz     short loc_140006CA9
0x140006ca0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140006ca7  jz      short loc_140006CBB
0x140006ca9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140006cb0  test    rax, rax
0x140006cb3  jz      short loc_140006CBB
0x140006cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006cba  nop
0x140006cbb  mov     rbx, [rsp+78h+arg_10]
0x140006cc3  add     rsp, 40h
0x140006cc7  pop     r15
0x140006cc9  pop     r14
0x140006ccb  pop     r13
0x140006ccd  pop     r12
0x140006ccf  pop     rdi
0x140006cd0  pop     rsi
0x140006cd1  pop     rbp
0x140006cd2  retn
0x140006cd3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
