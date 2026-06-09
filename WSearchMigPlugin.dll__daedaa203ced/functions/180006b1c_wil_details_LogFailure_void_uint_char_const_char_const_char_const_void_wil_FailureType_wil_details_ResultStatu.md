# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006b1c`
- end: `0x180006e1d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800040c4`

## callees

- `0x180003adc`
- `0x1800060b4`
- `0x180006870`
- `0x180006b1c`
- `0x180007850`
- `0x180007870`
- `0x1800079a4`
- `0x1800079c0`
- `0x180009efc`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c47`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006dd8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006dd8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006d66`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006d66`

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
  wil::details *v26; // [rsp+30h] [rbp-58h]

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v23);
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
0x180006b1c  mov     rax, rsp
0x180006b1f  mov     [rax+10h], edx
0x180006b22  mov     [rax+8], rcx
0x180006b26  push    rbp
0x180006b27  push    rsi
0x180006b28  push    rdi
0x180006b29  push    r12
0x180006b2b  push    r13
0x180006b2d  push    r14
0x180006b2f  push    r15
0x180006b31  sub     rsp, 50h
0x180006b35  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x180006b3d  mov     [rax+18h], rbx
0x180006b41  mov     r12, r9
0x180006b44  mov     r13, r8
0x180006b47  mov     r10, rcx
0x180006b4a  xor     eax, eax
0x180006b4c  mov     rsi, [rsp+88h+lpOutputString]
0x180006b54  mov     [rsi], ax
0x180006b57  mov     rax, [rsp+88h+arg_60]
0x180006b5f  mov     byte ptr [rax], 0
0x180006b62  mov     r14, [rsp+88h+arg_38]
0x180006b6a  mov     edi, [r14]
0x180006b6d  mov     rbx, [rsp+88h+arg_78]
0x180006b75  mov     [rbx+8], edi
0x180006b78  mov     eax, [r14+4]
0x180006b7c  mov     [rbx+0Ch], eax
0x180006b7f  xor     ebp, ebp
0x180006b81  mov     r15d, [rsp+88h+arg_30]
0x180006b89  mov     ecx, r15d
0x180006b8c  test    r15d, r15d
0x180006b8f  jz      short loc_180006BF7
0x180006b91  sub     ecx, 1
0x180006b94  jz      short loc_180006BEE
0x180006b96  sub     ecx, 1
0x180006b99  jz      short loc_180006BA9
0x180006b9b  cmp     ecx, 1
0x180006b9e  jnz     short loc_180006C00
0x180006ba0  mov     ecx, edi; this
0x180006ba2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006ba7  jmp     short loc_180006BFE
0x180006ba9  test    edi, edi
0x180006bab  js      short loc_180006BE5
0x180006bad  mov     edi, 8007029Ch
0x180006bb2  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x180006bb6  mov     rax, [rsp+88h+arg_28]
0x180006bbe  mov     [rsp+88h+var_60], rax; __int64
0x180006bc3  mov     rax, [rsp+88h+arg_20]
0x180006bcb  mov     [rsp+88h+var_68], rax; __int64
0x180006bd0  mov     rcx, r10; int
0x180006bd3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006bd8  mov     [rbx+8], edi
0x180006bdb  mov     ecx, edi; this
0x180006bdd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006be2  mov     [rbx+0Ch], eax
0x180006be5  mov     ecx, edi; this
0x180006be7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006bec  jmp     short loc_180006BFE
0x180006bee  mov     ecx, edi; this
0x180006bf0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006bf5  jmp     short loc_180006BFE
0x180006bf7  mov     ecx, edi; this
0x180006bf9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006bfe  mov     ebp, eax
0x180006c00  mov     [rbx], r15d
0x180006c03  mov     eax, [rsp+88h+arg_70]
0x180006c0a  mov     [rbx+4], eax
0x180006c0d  cmp     dword ptr [r14+8], 1
0x180006c12  jnz     short loc_180006C1A
0x180006c14  or      eax, 8
0x180006c17  mov     [rbx+4], eax
0x180006c1a  mov     eax, 1
0x180006c1f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006c27  inc     eax
0x180006c29  mov     [rbx+10h], eax
0x180006c2c  mov     rax, [rsp+88h+arg_40]
0x180006c34  xor     edi, edi
0x180006c36  test    rax, rax
0x180006c39  jz      short loc_180006C40
0x180006c3b  cmp     [rax], di
0x180006c3e  jnz     short loc_180006C43
0x180006c40  mov     rax, rdi
0x180006c43  mov     [rbx+18h], rax
0x180006c47  call    cs:__imp_GetCurrentThreadId
0x180006c4d  mov     [rbx+20h], eax
0x180006c50  mov     [rbx+38h], r13
0x180006c54  mov     eax, [rsp+88h+arg_8]
0x180006c5b  mov     [rbx+40h], eax
0x180006c5e  mov     [rbx+44h], ebp
0x180006c61  mov     rax, [rsp+88h+arg_20]
0x180006c69  mov     [rbx+28h], rax
0x180006c6d  mov     [rbx+30h], r12
0x180006c71  mov     rax, [rsp+88h+arg_28]
0x180006c79  mov     [rbx+88h], rax
0x180006c80  mov     rax, [rsp+88h+arg_0]
0x180006c88  mov     [rbx+90h], rax
0x180006c8f  mov     [rbx+48h], rdi
0x180006c93  xorps   xmm0, xmm0
0x180006c96  xor     eax, eax
0x180006c98  movups  xmmword ptr [rbx+68h], xmm0
0x180006c9c  mov     [rbx+78h], rax
0x180006ca0  movups  xmmword ptr [rbx+50h], xmm0
0x180006ca4  mov     [rbx+60h], rax
0x180006ca8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006caf  test    rax, rax
0x180006cb2  jz      short loc_180006CBB
0x180006cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cb9  jmp     short loc_180006CBE
0x180006cbb  mov     rax, rdi
0x180006cbe  mov     [rbx+80h], rax
0x180006cc5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006ccc  test    rax, rax
0x180006ccf  jz      short loc_180006CD9
0x180006cd1  mov     rcx, rbx
0x180006cd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cd9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006ce0  test    rax, rax
0x180006ce3  jz      short loc_180006CFB
0x180006ce5  mov     r8d, 400h
0x180006ceb  mov     rdx, [rsp+88h+arg_60]
0x180006cf3  mov     rcx, rbx
0x180006cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cfb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006d02  test    rax, rax
0x180006d05  jz      short loc_180006D0F
0x180006d07  mov     rcx, rbx
0x180006d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d0f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006d16  test    rax, rax
0x180006d19  jz      short loc_180006D29
0x180006d1b  test    byte ptr [rbx+4], 2
0x180006d1f  jnz     short loc_180006D29
0x180006d21  mov     rcx, rbx
0x180006d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d29  cmp     [rbx+8], edi
0x180006d2c  jl      short loc_180006D48
0x180006d2e  cmp     r15d, 3
0x180006d32  jnz     loc_180006E17
0x180006d38  mov     ecx, 8000FFFFh; this
0x180006d3d  mov     [rbx+8], ecx
0x180006d40  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006d45  mov     [rbx+0Ch], eax
0x180006d48  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006d4f  jnz     short loc_180006D70
0x180006d51  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006d58  test    rax, rax
0x180006d5b  jz      short loc_180006D66
0x180006d5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d62  test    al, al
0x180006d64  jmp     short loc_180006D6E
0x180006d66  call    cs:__imp_IsDebuggerPresent
0x180006d6c  test    eax, eax
0x180006d6e  jz      short loc_180006D76
0x180006d70  test    byte ptr [rbx+4], 2
0x180006d74  jz      short loc_180006D9A
0x180006d76  mov     rax, cs:g_pfnResultLoggingCallback
0x180006d7d  test    rax, rax
0x180006d80  jz      short loc_180006DDE
0x180006d82  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006d89  jnz     short loc_180006DDE
0x180006d8b  xor     r8d, r8d
0x180006d8e  xor     edx, edx
0x180006d90  mov     rcx, rbx
0x180006d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d98  jmp     short loc_180006DDE
0x180006d9a  mov     ebp, 800h
0x180006d9f  mov     rax, cs:g_pfnResultLoggingCallback
0x180006da6  test    rax, rax
0x180006da9  jz      short loc_180006DC2
0x180006dab  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006db2  jnz     short loc_180006DC2
0x180006db4  mov     r8d, ebp
0x180006db7  mov     rdx, rsi
0x180006dba  mov     rcx, rbx
0x180006dbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dc2  cmp     [rsi], di
0x180006dc5  jnz     short loc_180006DD5
0x180006dc7  mov     r8, rbx; unsigned __int64
0x180006dca  mov     rdx, rbp; wchar_t *
0x180006dcd  mov     rcx, rsi; this
0x180006dd0  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180006dd5  mov     rcx, rsi; lpOutputString
0x180006dd8  call    cs:__imp_OutputDebugStringW
0x180006dde  test    byte ptr [rbx+4], 4
0x180006de2  jnz     short loc_180006DED
0x180006de4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006deb  jz      short loc_180006DFF
0x180006ded  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006df4  test    rax, rax
0x180006df7  jz      short loc_180006DFF
0x180006df9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dfe  nop
0x180006dff  mov     rbx, [rsp+88h+arg_10]
0x180006e07  add     rsp, 50h
0x180006e0b  pop     r15
0x180006e0d  pop     r14
0x180006e0f  pop     r13
0x180006e11  pop     r12
0x180006e13  pop     rdi
0x180006e14  pop     rsi
0x180006e15  pop     rbp
0x180006e16  retn
0x180006e17  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
