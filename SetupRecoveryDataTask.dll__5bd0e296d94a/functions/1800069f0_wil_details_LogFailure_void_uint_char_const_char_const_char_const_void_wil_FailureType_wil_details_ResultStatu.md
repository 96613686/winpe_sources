# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800069f0`
- end: `0x180006ce9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002ba8`

## callees

- `0x1800025e4`
- `0x1800055e4`
- `0x180005d9c`
- `0x1800069f0`
- `0x1800076a4`
- `0x1800076c0`
- `0x1800077f0`
- `0x18000780c`
- `0x18000ab0c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006b13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006b13`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006c32`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006c32`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006ca4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006ca4`

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
0x1800069f0  mov     [rsp+arg_10], rbx
0x1800069f5  mov     [rsp+arg_8], edx
0x1800069f9  mov     [rsp+arg_0], rcx
0x1800069fe  push    rbp
0x1800069ff  push    rsi
0x180006a00  push    rdi
0x180006a01  push    r12
0x180006a03  push    r13
0x180006a05  push    r14
0x180006a07  push    r15
0x180006a09  sub     rsp, 40h
0x180006a0d  mov     r12, r9
0x180006a10  mov     r13, r8
0x180006a13  mov     r10, rcx
0x180006a16  xor     eax, eax
0x180006a18  mov     rsi, [rsp+78h+lpOutputString]
0x180006a20  mov     [rsi], ax
0x180006a23  mov     rax, [rsp+78h+arg_60]
0x180006a2b  mov     byte ptr [rax], 0
0x180006a2e  mov     r14, [rsp+78h+arg_38]
0x180006a36  mov     edi, [r14]
0x180006a39  mov     rbx, [rsp+78h+arg_78]
0x180006a41  mov     [rbx+8], edi
0x180006a44  mov     eax, [r14+4]
0x180006a48  mov     [rbx+0Ch], eax
0x180006a4b  xor     ebp, ebp
0x180006a4d  mov     r15d, [rsp+78h+arg_30]
0x180006a55  mov     ecx, r15d
0x180006a58  test    r15d, r15d
0x180006a5b  jz      short loc_180006AC3
0x180006a5d  sub     ecx, 1
0x180006a60  jz      short loc_180006ABA
0x180006a62  sub     ecx, 1
0x180006a65  jz      short loc_180006A75
0x180006a67  cmp     ecx, 1
0x180006a6a  jnz     short loc_180006ACC
0x180006a6c  mov     ecx, edi; this
0x180006a6e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006a73  jmp     short loc_180006ACA
0x180006a75  test    edi, edi
0x180006a77  js      short loc_180006AB1
0x180006a79  mov     edi, 8007029Ch
0x180006a7e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006a82  mov     rax, [rsp+78h+arg_28]
0x180006a8a  mov     [rsp+78h+var_50], rax; __int64
0x180006a8f  mov     rax, [rsp+78h+arg_20]
0x180006a97  mov     [rsp+78h+var_58], rax; __int64
0x180006a9c  mov     rcx, r10; int
0x180006a9f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006aa4  mov     [rbx+8], edi
0x180006aa7  mov     ecx, edi; this
0x180006aa9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006aae  mov     [rbx+0Ch], eax
0x180006ab1  mov     ecx, edi; this
0x180006ab3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006ab8  jmp     short loc_180006ACA
0x180006aba  mov     ecx, edi; this
0x180006abc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006ac1  jmp     short loc_180006ACA
0x180006ac3  mov     ecx, edi; this
0x180006ac5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006aca  mov     ebp, eax
0x180006acc  mov     [rbx], r15d
0x180006acf  mov     eax, [rsp+78h+arg_70]
0x180006ad6  mov     [rbx+4], eax
0x180006ad9  cmp     dword ptr [r14+8], 1
0x180006ade  jnz     short loc_180006AE6
0x180006ae0  or      eax, 8
0x180006ae3  mov     [rbx+4], eax
0x180006ae6  mov     eax, 1
0x180006aeb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006af3  inc     eax
0x180006af5  mov     [rbx+10h], eax
0x180006af8  mov     rax, [rsp+78h+arg_40]
0x180006b00  xor     edi, edi
0x180006b02  test    rax, rax
0x180006b05  jz      short loc_180006B0C
0x180006b07  cmp     [rax], di
0x180006b0a  jnz     short loc_180006B0F
0x180006b0c  mov     rax, rdi
0x180006b0f  mov     [rbx+18h], rax
0x180006b13  call    cs:__imp_GetCurrentThreadId
0x180006b19  mov     [rbx+20h], eax
0x180006b1c  mov     [rbx+38h], r13
0x180006b20  mov     eax, [rsp+78h+arg_8]
0x180006b27  mov     [rbx+40h], eax
0x180006b2a  mov     [rbx+44h], ebp
0x180006b2d  mov     rax, [rsp+78h+arg_20]
0x180006b35  mov     [rbx+28h], rax
0x180006b39  mov     [rbx+30h], r12
0x180006b3d  mov     rax, [rsp+78h+arg_28]
0x180006b45  mov     [rbx+88h], rax
0x180006b4c  mov     rax, [rsp+78h+arg_0]
0x180006b54  mov     [rbx+90h], rax
0x180006b5b  mov     [rbx+48h], rdi
0x180006b5f  xorps   xmm0, xmm0
0x180006b62  xor     eax, eax
0x180006b64  movups  xmmword ptr [rbx+68h], xmm0
0x180006b68  mov     [rbx+78h], rax
0x180006b6c  movups  xmmword ptr [rbx+50h], xmm0
0x180006b70  mov     [rbx+60h], rax
0x180006b74  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006b7b  test    rax, rax
0x180006b7e  jz      short loc_180006B87
0x180006b80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b85  jmp     short loc_180006B8A
0x180006b87  mov     rax, rdi
0x180006b8a  mov     [rbx+80h], rax
0x180006b91  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006b98  test    rax, rax
0x180006b9b  jz      short loc_180006BA5
0x180006b9d  mov     rcx, rbx
0x180006ba0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ba5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006bac  test    rax, rax
0x180006baf  jz      short loc_180006BC7
0x180006bb1  mov     r8d, 400h
0x180006bb7  mov     rdx, [rsp+78h+arg_60]
0x180006bbf  mov     rcx, rbx
0x180006bc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bc7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006bce  test    rax, rax
0x180006bd1  jz      short loc_180006BDB
0x180006bd3  mov     rcx, rbx
0x180006bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bdb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006be2  test    rax, rax
0x180006be5  jz      short loc_180006BF5
0x180006be7  test    byte ptr [rbx+4], 2
0x180006beb  jnz     short loc_180006BF5
0x180006bed  mov     rcx, rbx
0x180006bf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bf5  cmp     [rbx+8], edi
0x180006bf8  jl      short loc_180006C14
0x180006bfa  cmp     r15d, 3
0x180006bfe  jnz     loc_180006CE3
0x180006c04  mov     ecx, 8000FFFFh; this
0x180006c09  mov     [rbx+8], ecx
0x180006c0c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006c11  mov     [rbx+0Ch], eax
0x180006c14  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006c1b  jnz     short loc_180006C3C
0x180006c1d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006c24  test    rax, rax
0x180006c27  jz      short loc_180006C32
0x180006c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c2e  test    al, al
0x180006c30  jmp     short loc_180006C3A
0x180006c32  call    cs:__imp_IsDebuggerPresent
0x180006c38  test    eax, eax
0x180006c3a  jz      short loc_180006C42
0x180006c3c  test    byte ptr [rbx+4], 2
0x180006c40  jz      short loc_180006C66
0x180006c42  mov     rax, cs:g_pfnResultLoggingCallback
0x180006c49  test    rax, rax
0x180006c4c  jz      short loc_180006CAA
0x180006c4e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006c55  jnz     short loc_180006CAA
0x180006c57  xor     r8d, r8d
0x180006c5a  xor     edx, edx
0x180006c5c  mov     rcx, rbx
0x180006c5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c64  jmp     short loc_180006CAA
0x180006c66  mov     ebp, 800h
0x180006c6b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006c72  test    rax, rax
0x180006c75  jz      short loc_180006C8E
0x180006c77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006c7e  jnz     short loc_180006C8E
0x180006c80  mov     r8d, ebp
0x180006c83  mov     rdx, rsi
0x180006c86  mov     rcx, rbx
0x180006c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c8e  cmp     [rsi], di
0x180006c91  jnz     short loc_180006CA1
0x180006c93  mov     r8, rbx; unsigned __int64
0x180006c96  mov     rdx, rbp; unsigned __int16 *
0x180006c99  mov     rcx, rsi; this
0x180006c9c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006ca1  mov     rcx, rsi; lpOutputString
0x180006ca4  call    cs:__imp_OutputDebugStringW
0x180006caa  test    byte ptr [rbx+4], 4
0x180006cae  jnz     short loc_180006CB9
0x180006cb0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006cb7  jz      short loc_180006CCB
0x180006cb9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006cc0  test    rax, rax
0x180006cc3  jz      short loc_180006CCB
0x180006cc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cca  nop
0x180006ccb  mov     rbx, [rsp+78h+arg_10]
0x180006cd3  add     rsp, 40h
0x180006cd7  pop     r15
0x180006cd9  pop     r14
0x180006cdb  pop     r13
0x180006cdd  pop     r12
0x180006cdf  pop     rdi
0x180006ce0  pop     rsi
0x180006ce1  pop     rbp
0x180006ce2  retn
0x180006ce3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
