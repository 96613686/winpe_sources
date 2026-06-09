# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180053950`
- end: `0x180053c4d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `765`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180050504`
- `0x1800505b4`
- `0x1800506a8`

## callees

- `0x18004dd78`
- `0x180050458`
- `0x1800523fc`
- `0x180053950`
- `0x1800546e0`
- `0x180054700`
- `0x1800547bc`
- `0x1800547d8`
- `0x180056120`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053a7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053a7b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180053b9c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180053b9c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180053c0e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180053c0e`

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
  wil::details *v28; // [rsp+30h] [rbp-58h]

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
0x180053950  mov     rax, rsp
0x180053953  mov     [rax+10h], edx
0x180053956  mov     [rax+8], rcx
0x18005395a  push    rbp
0x18005395b  push    rsi
0x18005395c  push    rdi
0x18005395d  push    r12
0x18005395f  push    r13
0x180053961  push    r14
0x180053963  push    r15
0x180053965  sub     rsp, 50h
0x180053969  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180053971  mov     [rax+18h], rbx
0x180053975  mov     r12, r9
0x180053978  mov     r13, r8
0x18005397b  mov     r10, rcx
0x18005397e  xor     eax, eax
0x180053980  mov     rsi, [rsp+88h+lpOutputString]
0x180053988  mov     [rsi], ax
0x18005398b  mov     rax, [rsp+88h+arg_60]
0x180053993  mov     byte ptr [rax], 0
0x180053996  mov     r14, [rsp+88h+arg_38]
0x18005399e  mov     edi, [r14]
0x1800539a1  mov     rbx, [rsp+88h+arg_78]
0x1800539a9  mov     [rbx+8], edi
0x1800539ac  mov     eax, [r14+4]
0x1800539b0  mov     [rbx+0Ch], eax
0x1800539b3  xor     ebp, ebp
0x1800539b5  mov     r15d, [rsp+88h+arg_30]
0x1800539bd  mov     ecx, r15d
0x1800539c0  test    r15d, r15d
0x1800539c3  jz      short loc_180053A2B
0x1800539c5  sub     ecx, 1
0x1800539c8  jz      short loc_180053A22
0x1800539ca  sub     ecx, 1
0x1800539cd  jz      short loc_1800539DD
0x1800539cf  cmp     ecx, 1
0x1800539d2  jnz     short loc_180053A34
0x1800539d4  mov     ecx, edi; this
0x1800539d6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800539db  jmp     short loc_180053A32
0x1800539dd  test    edi, edi
0x1800539df  js      short loc_180053A19
0x1800539e1  mov     edi, 8007029Ch
0x1800539e6  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x1800539ea  mov     rax, [rsp+88h+arg_28]
0x1800539f2  mov     [rsp+88h+var_60], rax; __int64
0x1800539f7  mov     rax, [rsp+88h+arg_20]
0x1800539ff  mov     [rsp+88h+var_68], rax; __int64
0x180053a04  mov     rcx, r10; int
0x180053a07  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180053a0c  mov     [rbx+8], edi
0x180053a0f  mov     ecx, edi; this
0x180053a11  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180053a16  mov     [rbx+0Ch], eax
0x180053a19  mov     ecx, edi; this
0x180053a1b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180053a20  jmp     short loc_180053A32
0x180053a22  mov     ecx, edi; this
0x180053a24  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180053a29  jmp     short loc_180053A32
0x180053a2b  mov     ecx, edi; this
0x180053a2d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180053a32  mov     ebp, eax
0x180053a34  mov     [rbx], r15d
0x180053a37  mov     eax, [rsp+88h+arg_70]
0x180053a3e  mov     [rbx+4], eax
0x180053a41  cmp     dword ptr [r14+8], 1
0x180053a46  jnz     short loc_180053A4E
0x180053a48  or      eax, 8
0x180053a4b  mov     [rbx+4], eax
0x180053a4e  mov     eax, 1
0x180053a53  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180053a5b  inc     eax
0x180053a5d  mov     [rbx+10h], eax
0x180053a60  mov     rax, [rsp+88h+arg_40]
0x180053a68  xor     edi, edi
0x180053a6a  test    rax, rax
0x180053a6d  jz      short loc_180053A74
0x180053a6f  cmp     [rax], di
0x180053a72  jnz     short loc_180053A77
0x180053a74  mov     rax, rdi
0x180053a77  mov     [rbx+18h], rax
0x180053a7b  call    cs:__imp_GetCurrentThreadId
0x180053a81  mov     [rbx+20h], eax
0x180053a84  mov     [rbx+38h], r13
0x180053a88  mov     eax, [rsp+88h+arg_8]
0x180053a8f  mov     [rbx+40h], eax
0x180053a92  mov     [rbx+44h], ebp
0x180053a95  mov     rax, [rsp+88h+arg_20]
0x180053a9d  mov     [rbx+28h], rax
0x180053aa1  mov     [rbx+30h], r12
0x180053aa5  mov     rax, [rsp+88h+arg_28]
0x180053aad  mov     [rbx+88h], rax
0x180053ab4  mov     rax, [rsp+88h+arg_0]
0x180053abc  mov     [rbx+90h], rax
0x180053ac3  mov     [rbx+48h], rdi
0x180053ac7  xorps   xmm0, xmm0
0x180053aca  xor     eax, eax
0x180053acc  movups  xmmword ptr [rbx+68h], xmm0
0x180053ad0  mov     [rbx+78h], rax
0x180053ad4  movups  xmmword ptr [rbx+50h], xmm0
0x180053ad8  mov     [rbx+60h], rax
0x180053adc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180053ae3  test    rax, rax
0x180053ae6  jz      short loc_180053AEF
0x180053ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053aed  jmp     short loc_180053AF2
0x180053aef  mov     rax, rdi
0x180053af2  mov     [rbx+80h], rax
0x180053af9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180053b00  test    rax, rax
0x180053b03  jz      short loc_180053B0D
0x180053b05  mov     rcx, rbx
0x180053b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b0d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180053b14  test    rax, rax
0x180053b17  jz      short loc_180053B2F
0x180053b19  mov     r8d, 400h
0x180053b1f  mov     rdx, [rsp+88h+arg_60]
0x180053b27  mov     rcx, rbx
0x180053b2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b2f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180053b36  test    rax, rax
0x180053b39  jz      short loc_180053B43
0x180053b3b  mov     rcx, rbx
0x180053b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b43  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180053b4a  test    rax, rax
0x180053b4d  jz      short loc_180053B5D
0x180053b4f  test    byte ptr [rbx+4], 2
0x180053b53  jnz     short loc_180053B5D
0x180053b55  mov     rcx, rbx
0x180053b58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b5d  cmp     [rbx+8], edi
0x180053b60  jl      short loc_180053B7E
0x180053b62  cmp     r15d, 3
0x180053b66  jz      short loc_180053B6E
0x180053b68  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180053b6e  mov     ecx, 8000FFFFh; this
0x180053b73  mov     [rbx+8], ecx
0x180053b76  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180053b7b  mov     [rbx+0Ch], eax
0x180053b7e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180053b85  jnz     short loc_180053BA6
0x180053b87  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180053b8e  test    rax, rax
0x180053b91  jz      short loc_180053B9C
0x180053b93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b98  test    al, al
0x180053b9a  jmp     short loc_180053BA4
0x180053b9c  call    cs:__imp_IsDebuggerPresent
0x180053ba2  test    eax, eax
0x180053ba4  jz      short loc_180053BAC
0x180053ba6  test    byte ptr [rbx+4], 2
0x180053baa  jz      short loc_180053BD0
0x180053bac  mov     rax, cs:g_pfnResultLoggingCallback
0x180053bb3  test    rax, rax
0x180053bb6  jz      short loc_180053C14
0x180053bb8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180053bbf  jnz     short loc_180053C14
0x180053bc1  xor     r8d, r8d
0x180053bc4  xor     edx, edx
0x180053bc6  mov     rcx, rbx
0x180053bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053bce  jmp     short loc_180053C14
0x180053bd0  mov     ebp, 800h
0x180053bd5  mov     rax, cs:g_pfnResultLoggingCallback
0x180053bdc  test    rax, rax
0x180053bdf  jz      short loc_180053BF8
0x180053be1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180053be8  jnz     short loc_180053BF8
0x180053bea  mov     r8d, ebp
0x180053bed  mov     rdx, rsi
0x180053bf0  mov     rcx, rbx
0x180053bf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053bf8  cmp     [rsi], di
0x180053bfb  jnz     short loc_180053C0B
0x180053bfd  mov     r8, rbx; unsigned __int64
0x180053c00  mov     rdx, rbp; unsigned __int16 *
0x180053c03  mov     rcx, rsi; this
0x180053c06  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180053c0b  mov     rcx, rsi; lpOutputString
0x180053c0e  call    cs:__imp_OutputDebugStringW
0x180053c14  test    byte ptr [rbx+4], 4
0x180053c18  jnz     short loc_180053C23
0x180053c1a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180053c21  jz      short loc_180053C35
0x180053c23  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180053c2a  test    rax, rax
0x180053c2d  jz      short loc_180053C35
0x180053c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c34  nop
0x180053c35  mov     rbx, [rsp+88h+arg_10]
0x180053c3d  add     rsp, 50h
0x180053c41  pop     r15
0x180053c43  pop     r14
0x180053c45  pop     r13
0x180053c47  pop     r12
0x180053c49  pop     rdi
0x180053c4a  pop     rsi
0x180053c4b  pop     rbp
0x180053c4c  retn
```
