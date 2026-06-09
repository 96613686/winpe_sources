# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007ab4`
- end: `0x180007dad`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180004418`
- `0x1800044d8`
- `0x18000488c`

## callees

- `0x180004268`
- `0x1800069e4`
- `0x180007278`
- `0x180007ab4`
- `0x180008d08`
- `0x180008d30`
- `0x180008d44`
- `0x180008d60`
- `0x18000a348`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007bd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007bd7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007cf6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007cf6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007d68`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007d68`

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
0x180007ab4  mov     [rsp+arg_10], rbx
0x180007ab9  mov     [rsp+arg_8], edx
0x180007abd  mov     [rsp+arg_0], rcx
0x180007ac2  push    rbp
0x180007ac3  push    rsi
0x180007ac4  push    rdi
0x180007ac5  push    r12
0x180007ac7  push    r13
0x180007ac9  push    r14
0x180007acb  push    r15
0x180007acd  sub     rsp, 40h
0x180007ad1  mov     r12, r9
0x180007ad4  mov     r13, r8
0x180007ad7  mov     r10, rcx
0x180007ada  xor     eax, eax
0x180007adc  mov     rsi, [rsp+78h+lpOutputString]
0x180007ae4  mov     [rsi], ax
0x180007ae7  mov     rax, [rsp+78h+arg_60]
0x180007aef  mov     byte ptr [rax], 0
0x180007af2  mov     r14, [rsp+78h+arg_38]
0x180007afa  mov     edi, [r14]
0x180007afd  mov     rbx, [rsp+78h+arg_78]
0x180007b05  mov     [rbx+8], edi
0x180007b08  mov     eax, [r14+4]
0x180007b0c  mov     [rbx+0Ch], eax
0x180007b0f  xor     ebp, ebp
0x180007b11  mov     r15d, [rsp+78h+arg_30]
0x180007b19  mov     ecx, r15d
0x180007b1c  test    r15d, r15d
0x180007b1f  jz      short loc_180007B87
0x180007b21  sub     ecx, 1
0x180007b24  jz      short loc_180007B7E
0x180007b26  sub     ecx, 1
0x180007b29  jz      short loc_180007B39
0x180007b2b  cmp     ecx, 1
0x180007b2e  jnz     short loc_180007B90
0x180007b30  mov     ecx, edi; this
0x180007b32  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007b37  jmp     short loc_180007B8E
0x180007b39  test    edi, edi
0x180007b3b  js      short loc_180007B75
0x180007b3d  mov     edi, 8007029Ch
0x180007b42  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007b46  mov     rax, [rsp+78h+arg_28]
0x180007b4e  mov     [rsp+78h+var_50], rax; __int64
0x180007b53  mov     rax, [rsp+78h+arg_20]
0x180007b5b  mov     [rsp+78h+var_58], rax; __int64
0x180007b60  mov     rcx, r10; int
0x180007b63  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007b68  mov     [rbx+8], edi
0x180007b6b  mov     ecx, edi; this
0x180007b6d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007b72  mov     [rbx+0Ch], eax
0x180007b75  mov     ecx, edi; this
0x180007b77  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007b7c  jmp     short loc_180007B8E
0x180007b7e  mov     ecx, edi; this
0x180007b80  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007b85  jmp     short loc_180007B8E
0x180007b87  mov     ecx, edi; this
0x180007b89  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007b8e  mov     ebp, eax
0x180007b90  mov     [rbx], r15d
0x180007b93  mov     eax, [rsp+78h+arg_70]
0x180007b9a  mov     [rbx+4], eax
0x180007b9d  cmp     dword ptr [r14+8], 1
0x180007ba2  jnz     short loc_180007BAA
0x180007ba4  or      eax, 8
0x180007ba7  mov     [rbx+4], eax
0x180007baa  mov     eax, 1
0x180007baf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007bb7  inc     eax
0x180007bb9  mov     [rbx+10h], eax
0x180007bbc  mov     rax, [rsp+78h+arg_40]
0x180007bc4  xor     edi, edi
0x180007bc6  test    rax, rax
0x180007bc9  jz      short loc_180007BD0
0x180007bcb  cmp     [rax], di
0x180007bce  jnz     short loc_180007BD3
0x180007bd0  mov     rax, rdi
0x180007bd3  mov     [rbx+18h], rax
0x180007bd7  call    cs:__imp_GetCurrentThreadId
0x180007bdd  mov     [rbx+20h], eax
0x180007be0  mov     [rbx+38h], r13
0x180007be4  mov     eax, [rsp+78h+arg_8]
0x180007beb  mov     [rbx+40h], eax
0x180007bee  mov     [rbx+44h], ebp
0x180007bf1  mov     rax, [rsp+78h+arg_20]
0x180007bf9  mov     [rbx+28h], rax
0x180007bfd  mov     [rbx+30h], r12
0x180007c01  mov     rax, [rsp+78h+arg_28]
0x180007c09  mov     [rbx+88h], rax
0x180007c10  mov     rax, [rsp+78h+arg_0]
0x180007c18  mov     [rbx+90h], rax
0x180007c1f  mov     [rbx+48h], rdi
0x180007c23  xorps   xmm0, xmm0
0x180007c26  xor     eax, eax
0x180007c28  movups  xmmword ptr [rbx+68h], xmm0
0x180007c2c  mov     [rbx+78h], rax
0x180007c30  movups  xmmword ptr [rbx+50h], xmm0
0x180007c34  mov     [rbx+60h], rax
0x180007c38  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007c3f  test    rax, rax
0x180007c42  jz      short loc_180007C4B
0x180007c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c49  jmp     short loc_180007C4E
0x180007c4b  mov     rax, rdi
0x180007c4e  mov     [rbx+80h], rax
0x180007c55  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007c5c  test    rax, rax
0x180007c5f  jz      short loc_180007C69
0x180007c61  mov     rcx, rbx
0x180007c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c69  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007c70  test    rax, rax
0x180007c73  jz      short loc_180007C8B
0x180007c75  mov     r8d, 400h
0x180007c7b  mov     rdx, [rsp+78h+arg_60]
0x180007c83  mov     rcx, rbx
0x180007c86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c8b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007c92  test    rax, rax
0x180007c95  jz      short loc_180007C9F
0x180007c97  mov     rcx, rbx
0x180007c9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c9f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007ca6  test    rax, rax
0x180007ca9  jz      short loc_180007CB9
0x180007cab  test    byte ptr [rbx+4], 2
0x180007caf  jnz     short loc_180007CB9
0x180007cb1  mov     rcx, rbx
0x180007cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cb9  cmp     [rbx+8], edi
0x180007cbc  jl      short loc_180007CD8
0x180007cbe  cmp     r15d, 3
0x180007cc2  jnz     loc_180007DA7
0x180007cc8  mov     ecx, 8000FFFFh; this
0x180007ccd  mov     [rbx+8], ecx
0x180007cd0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007cd5  mov     [rbx+0Ch], eax
0x180007cd8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007cdf  jnz     short loc_180007D00
0x180007ce1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007ce8  test    rax, rax
0x180007ceb  jz      short loc_180007CF6
0x180007ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cf2  test    al, al
0x180007cf4  jmp     short loc_180007CFE
0x180007cf6  call    cs:__imp_IsDebuggerPresent
0x180007cfc  test    eax, eax
0x180007cfe  jz      short loc_180007D06
0x180007d00  test    byte ptr [rbx+4], 2
0x180007d04  jz      short loc_180007D2A
0x180007d06  mov     rax, cs:g_pfnResultLoggingCallback
0x180007d0d  test    rax, rax
0x180007d10  jz      short loc_180007D6E
0x180007d12  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007d19  jnz     short loc_180007D6E
0x180007d1b  xor     r8d, r8d
0x180007d1e  xor     edx, edx
0x180007d20  mov     rcx, rbx
0x180007d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d28  jmp     short loc_180007D6E
0x180007d2a  mov     ebp, 800h
0x180007d2f  mov     rax, cs:g_pfnResultLoggingCallback
0x180007d36  test    rax, rax
0x180007d39  jz      short loc_180007D52
0x180007d3b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007d42  jnz     short loc_180007D52
0x180007d44  mov     r8d, ebp
0x180007d47  mov     rdx, rsi
0x180007d4a  mov     rcx, rbx
0x180007d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d52  cmp     [rsi], di
0x180007d55  jnz     short loc_180007D65
0x180007d57  mov     r8, rbx; unsigned __int64
0x180007d5a  mov     rdx, rbp; unsigned __int16 *
0x180007d5d  mov     rcx, rsi; this
0x180007d60  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007d65  mov     rcx, rsi; lpOutputString
0x180007d68  call    cs:__imp_OutputDebugStringW
0x180007d6e  test    byte ptr [rbx+4], 4
0x180007d72  jnz     short loc_180007D7D
0x180007d74  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007d7b  jz      short loc_180007D8F
0x180007d7d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007d84  test    rax, rax
0x180007d87  jz      short loc_180007D8F
0x180007d89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d8e  nop
0x180007d8f  mov     rbx, [rsp+78h+arg_10]
0x180007d97  add     rsp, 40h
0x180007d9b  pop     r15
0x180007d9d  pop     r14
0x180007d9f  pop     r13
0x180007da1  pop     r12
0x180007da3  pop     rdi
0x180007da4  pop     rsi
0x180007da5  pop     rbp
0x180007da6  retn
0x180007da7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
