# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800059c4`
- end: `0x180005cbd`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004014`

## callees

- `0x180003a20`
- `0x180004fb4`
- `0x180005800`
- `0x1800059c4`
- `0x180005f44`
- `0x180005f60`
- `0x180005f74`
- `0x180005f90`
- `0x180007198`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005ae7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005ae7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005c78`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005c78`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005c06`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005c06`

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
0x1800059c4  mov     [rsp+arg_10], rbx
0x1800059c9  mov     [rsp+arg_8], edx
0x1800059cd  mov     [rsp+arg_0], rcx
0x1800059d2  push    rbp
0x1800059d3  push    rsi
0x1800059d4  push    rdi
0x1800059d5  push    r12
0x1800059d7  push    r13
0x1800059d9  push    r14
0x1800059db  push    r15
0x1800059dd  sub     rsp, 40h
0x1800059e1  mov     r12, r9
0x1800059e4  mov     r13, r8
0x1800059e7  mov     r10, rcx
0x1800059ea  xor     eax, eax
0x1800059ec  mov     rsi, [rsp+78h+lpOutputString]
0x1800059f4  mov     [rsi], ax
0x1800059f7  mov     rax, [rsp+78h+arg_60]
0x1800059ff  mov     byte ptr [rax], 0
0x180005a02  mov     r14, [rsp+78h+arg_38]
0x180005a0a  mov     edi, [r14]
0x180005a0d  mov     rbx, [rsp+78h+arg_78]
0x180005a15  mov     [rbx+8], edi
0x180005a18  mov     eax, [r14+4]
0x180005a1c  mov     [rbx+0Ch], eax
0x180005a1f  xor     ebp, ebp
0x180005a21  mov     r15d, [rsp+78h+arg_30]
0x180005a29  mov     ecx, r15d
0x180005a2c  test    r15d, r15d
0x180005a2f  jz      short loc_180005A97
0x180005a31  sub     ecx, 1
0x180005a34  jz      short loc_180005A8E
0x180005a36  sub     ecx, 1
0x180005a39  jz      short loc_180005A49
0x180005a3b  cmp     ecx, 1
0x180005a3e  jnz     short loc_180005AA0
0x180005a40  mov     ecx, edi; this
0x180005a42  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005a47  jmp     short loc_180005A9E
0x180005a49  test    edi, edi
0x180005a4b  js      short loc_180005A85
0x180005a4d  mov     edi, 8007029Ch
0x180005a52  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005a56  mov     rax, [rsp+78h+arg_28]
0x180005a5e  mov     [rsp+78h+var_50], rax; __int64
0x180005a63  mov     rax, [rsp+78h+arg_20]
0x180005a6b  mov     [rsp+78h+var_58], rax; __int64
0x180005a70  mov     rcx, r10; int
0x180005a73  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005a78  mov     [rbx+8], edi
0x180005a7b  mov     ecx, edi; this
0x180005a7d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005a82  mov     [rbx+0Ch], eax
0x180005a85  mov     ecx, edi; this
0x180005a87  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005a8c  jmp     short loc_180005A9E
0x180005a8e  mov     ecx, edi; this
0x180005a90  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005a95  jmp     short loc_180005A9E
0x180005a97  mov     ecx, edi; this
0x180005a99  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005a9e  mov     ebp, eax
0x180005aa0  mov     [rbx], r15d
0x180005aa3  mov     eax, [rsp+78h+arg_70]
0x180005aaa  mov     [rbx+4], eax
0x180005aad  cmp     dword ptr [r14+8], 1
0x180005ab2  jnz     short loc_180005ABA
0x180005ab4  or      eax, 8
0x180005ab7  mov     [rbx+4], eax
0x180005aba  mov     eax, 1
0x180005abf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005ac7  inc     eax
0x180005ac9  mov     [rbx+10h], eax
0x180005acc  mov     rax, [rsp+78h+arg_40]
0x180005ad4  xor     edi, edi
0x180005ad6  test    rax, rax
0x180005ad9  jz      short loc_180005AE0
0x180005adb  cmp     [rax], di
0x180005ade  jnz     short loc_180005AE3
0x180005ae0  mov     rax, rdi
0x180005ae3  mov     [rbx+18h], rax
0x180005ae7  call    cs:__imp_GetCurrentThreadId
0x180005aed  mov     [rbx+20h], eax
0x180005af0  mov     [rbx+38h], r13
0x180005af4  mov     eax, [rsp+78h+arg_8]
0x180005afb  mov     [rbx+40h], eax
0x180005afe  mov     [rbx+44h], ebp
0x180005b01  mov     rax, [rsp+78h+arg_20]
0x180005b09  mov     [rbx+28h], rax
0x180005b0d  mov     [rbx+30h], r12
0x180005b11  mov     rax, [rsp+78h+arg_28]
0x180005b19  mov     [rbx+88h], rax
0x180005b20  mov     rax, [rsp+78h+arg_0]
0x180005b28  mov     [rbx+90h], rax
0x180005b2f  mov     [rbx+48h], rdi
0x180005b33  xorps   xmm0, xmm0
0x180005b36  xor     eax, eax
0x180005b38  movups  xmmword ptr [rbx+68h], xmm0
0x180005b3c  mov     [rbx+78h], rax
0x180005b40  movups  xmmword ptr [rbx+50h], xmm0
0x180005b44  mov     [rbx+60h], rax
0x180005b48  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005b4f  test    rax, rax
0x180005b52  jz      short loc_180005B5B
0x180005b54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b59  jmp     short loc_180005B5E
0x180005b5b  mov     rax, rdi
0x180005b5e  mov     [rbx+80h], rax
0x180005b65  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005b6c  test    rax, rax
0x180005b6f  jz      short loc_180005B79
0x180005b71  mov     rcx, rbx
0x180005b74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b79  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005b80  test    rax, rax
0x180005b83  jz      short loc_180005B9B
0x180005b85  mov     r8d, 400h
0x180005b8b  mov     rdx, [rsp+78h+arg_60]
0x180005b93  mov     rcx, rbx
0x180005b96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b9b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005ba2  test    rax, rax
0x180005ba5  jz      short loc_180005BAF
0x180005ba7  mov     rcx, rbx
0x180005baa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005baf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005bb6  test    rax, rax
0x180005bb9  jz      short loc_180005BC9
0x180005bbb  test    byte ptr [rbx+4], 2
0x180005bbf  jnz     short loc_180005BC9
0x180005bc1  mov     rcx, rbx
0x180005bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bc9  cmp     [rbx+8], edi
0x180005bcc  jl      short loc_180005BE8
0x180005bce  cmp     r15d, 3
0x180005bd2  jnz     loc_180005CB7
0x180005bd8  mov     ecx, 8000FFFFh; this
0x180005bdd  mov     [rbx+8], ecx
0x180005be0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005be5  mov     [rbx+0Ch], eax
0x180005be8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005bef  jnz     short loc_180005C10
0x180005bf1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005bf8  test    rax, rax
0x180005bfb  jz      short loc_180005C06
0x180005bfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c02  test    al, al
0x180005c04  jmp     short loc_180005C0E
0x180005c06  call    cs:__imp_IsDebuggerPresent
0x180005c0c  test    eax, eax
0x180005c0e  jz      short loc_180005C16
0x180005c10  test    byte ptr [rbx+4], 2
0x180005c14  jz      short loc_180005C3A
0x180005c16  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c1d  test    rax, rax
0x180005c20  jz      short loc_180005C7E
0x180005c22  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005c29  jnz     short loc_180005C7E
0x180005c2b  xor     r8d, r8d
0x180005c2e  xor     edx, edx
0x180005c30  mov     rcx, rbx
0x180005c33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c38  jmp     short loc_180005C7E
0x180005c3a  mov     ebp, 800h
0x180005c3f  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c46  test    rax, rax
0x180005c49  jz      short loc_180005C62
0x180005c4b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005c52  jnz     short loc_180005C62
0x180005c54  mov     r8d, ebp
0x180005c57  mov     rdx, rsi
0x180005c5a  mov     rcx, rbx
0x180005c5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c62  cmp     [rsi], di
0x180005c65  jnz     short loc_180005C75
0x180005c67  mov     r8, rbx; unsigned __int64
0x180005c6a  mov     rdx, rbp; unsigned __int16 *
0x180005c6d  mov     rcx, rsi; this
0x180005c70  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005c75  mov     rcx, rsi; lpOutputString
0x180005c78  call    cs:__imp_OutputDebugStringW
0x180005c7e  test    byte ptr [rbx+4], 4
0x180005c82  jnz     short loc_180005C8D
0x180005c84  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005c8b  jz      short loc_180005C9F
0x180005c8d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005c94  test    rax, rax
0x180005c97  jz      short loc_180005C9F
0x180005c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c9e  nop
0x180005c9f  mov     rbx, [rsp+78h+arg_10]
0x180005ca7  add     rsp, 40h
0x180005cab  pop     r15
0x180005cad  pop     r14
0x180005caf  pop     r13
0x180005cb1  pop     r12
0x180005cb3  pop     rdi
0x180005cb4  pop     rsi
0x180005cb5  pop     rbp
0x180005cb6  retn
0x180005cb7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
