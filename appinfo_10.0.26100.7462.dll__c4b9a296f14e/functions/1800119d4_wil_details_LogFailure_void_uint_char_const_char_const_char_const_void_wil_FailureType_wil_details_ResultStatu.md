# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)

- ea: `0x1800119d4`
- end: `0x180011cd7`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7PEAUFailureInfo@2@@Z`
- size: `771`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800118e0`
- `0x18001ddf0`
- `0x18001dea4`

## callees

- `0x1800119d4`
- `0x1800121d0`
- `0x1800133cc`
- `0x18001dd40`
- `0x18001f9d8`
- `0x180020998`
- `0x1800209c0`
- `0x180020ac8`
- `0x180022b18`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011af3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011af3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011c19`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011c19`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011c92`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011c92`

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
        unsigned __int64 a15)
{
  int v17; // esi
  unsigned int v18; // edi
  int v19; // eax
  int v20; // edx
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  v17 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a15 + 8) = *a8;
  *(_DWORD *)(a15 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v19 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a15 + 8) = -2147024228;
          *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v20);
        }
        v19 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v19 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v19 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v17 = v19;
LABEL_12:
  *(_DWORD *)a15 = a7;
  *(_DWORD *)(a15 + 4) = 0;
  if ( a8[2] == 1 )
    *(_DWORD *)(a15 + 4) = 8;
  *(_DWORD *)(a15 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a15 + 24) = v21;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a15 + 56) = a3;
  *(_DWORD *)(a15 + 32) = CurrentThreadId;
  *(_DWORD *)(a15 + 64) = a2;
  *(_QWORD *)(a15 + 40) = a5;
  *(_QWORD *)(a15 + 136) = a6;
  *(_QWORD *)(a15 + 144) = a1;
  *(_DWORD *)(a15 + 68) = v17;
  *(_QWORD *)(a15 + 48) = a4;
  *(_QWORD *)(a15 + 72) = 0;
  *(_OWORD *)(a15 + 104) = 0;
  *(_QWORD *)(a15 + 120) = 0;
  *(_OWORD *)(a15 + 80) = 0;
  *(_QWORD *)(a15 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a15 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a15, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a15);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a15 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a15);
  if ( *(int *)(a15 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a15 + 8) = -2147418113;
    *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
    || (*(_BYTE *)(a15 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a15, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a15 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x1800119d4  mov     [rsp+arg_10], rbx
0x1800119d9  mov     [rsp+arg_8], edx
0x1800119dd  mov     [rsp+arg_0], rcx
0x1800119e2  push    rbp
0x1800119e3  push    rsi
0x1800119e4  push    rdi
0x1800119e5  push    r12
0x1800119e7  push    r13
0x1800119e9  push    r14
0x1800119eb  push    r15
0x1800119ed  sub     rsp, 40h
0x1800119f1  mov     rax, [rsp+78h+arg_60]
0x1800119f9  mov     r13, r8
0x1800119fc  mov     r15, [rsp+78h+arg_38]
0x180011a04  xor     r8d, r8d
0x180011a07  mov     rbx, [rsp+78h+arg_70]
0x180011a0f  mov     r10, rcx
0x180011a12  mov     ebp, [rsp+78h+arg_30]
0x180011a19  mov     r12, r9
0x180011a1c  mov     r14, [rsp+78h+lpOutputString]
0x180011a24  mov     esi, r8d
0x180011a27  mov     ecx, ebp
0x180011a29  mov     [r14], r8w
0x180011a2d  mov     [rax], r8b
0x180011a30  mov     edi, [r15]
0x180011a33  mov     [rbx+8], edi
0x180011a36  mov     eax, [r15+4]
0x180011a3a  mov     [rbx+0Ch], eax
0x180011a3d  test    ebp, ebp
0x180011a3f  jz      short loc_180011AAA
0x180011a41  sub     ecx, 1
0x180011a44  jz      short loc_180011AA1
0x180011a46  sub     ecx, 1
0x180011a49  jz      short loc_180011A59
0x180011a4b  cmp     ecx, 1
0x180011a4e  jnz     short loc_180011AB3
0x180011a50  mov     ecx, edi; this
0x180011a52  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180011a57  jmp     short loc_180011AB1
0x180011a59  test    edi, edi
0x180011a5b  js      short loc_180011A98
0x180011a5d  mov     rax, [rsp+78h+arg_28]
0x180011a65  mov     edi, 8007029Ch
0x180011a6a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180011a6e  mov     r8, r13; int
0x180011a71  mov     [rsp+78h+var_50], rax; __int64
0x180011a76  mov     rcx, r10; int
0x180011a79  mov     rax, [rsp+78h+arg_20]
0x180011a81  mov     [rsp+78h+var_58], rax; __int64
0x180011a86  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x180011a8b  mov     ecx, edi; this
0x180011a8d  mov     [rbx+8], edi
0x180011a90  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011a95  mov     [rbx+0Ch], eax
0x180011a98  mov     ecx, edi; this
0x180011a9a  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180011a9f  jmp     short loc_180011AB1
0x180011aa1  mov     ecx, edi; this
0x180011aa3  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180011aa8  jmp     short loc_180011AB1
0x180011aaa  mov     ecx, edi; this
0x180011aac  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180011ab1  mov     esi, eax
0x180011ab3  xor     edi, edi
0x180011ab5  mov     [rbx], ebp
0x180011ab7  mov     [rbx+4], edi
0x180011aba  cmp     dword ptr [r15+8], 1
0x180011abf  jnz     short loc_180011AC8
0x180011ac1  mov     dword ptr [rbx+4], 8
0x180011ac8  mov     eax, 1
0x180011acd  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180011ad5  inc     eax
0x180011ad7  mov     [rbx+10h], eax
0x180011ada  mov     rax, [rsp+78h+arg_40]
0x180011ae2  test    rax, rax
0x180011ae5  jz      short loc_180011AEC
0x180011ae7  cmp     [rax], di
0x180011aea  jnz     short loc_180011AEF
0x180011aec  mov     rax, rdi
0x180011aef  mov     [rbx+18h], rax
0x180011af3  call    cs:__imp_GetCurrentThreadId
0x180011afa  nop     dword ptr [rax+rax+00h]
0x180011aff  mov     [rbx+38h], r13
0x180011b03  xorps   xmm0, xmm0
0x180011b06  mov     [rbx+20h], eax
0x180011b09  mov     eax, [rsp+78h+arg_8]
0x180011b10  mov     [rbx+40h], eax
0x180011b13  mov     rax, [rsp+78h+arg_20]
0x180011b1b  mov     [rbx+28h], rax
0x180011b1f  mov     rax, [rsp+78h+arg_28]
0x180011b27  mov     [rbx+88h], rax
0x180011b2e  mov     rax, [rsp+78h+arg_0]
0x180011b36  mov     [rbx+90h], rax
0x180011b3d  xor     eax, eax
0x180011b3f  mov     [rbx+44h], esi
0x180011b42  mov     [rbx+30h], r12
0x180011b46  mov     [rbx+48h], rdi
0x180011b4a  movups  xmmword ptr [rbx+68h], xmm0
0x180011b4e  mov     [rbx+78h], rax
0x180011b52  movups  xmmword ptr [rbx+50h], xmm0
0x180011b56  mov     [rbx+60h], rax
0x180011b5a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180011b61  test    rax, rax
0x180011b64  jz      short loc_180011B6D
0x180011b66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b6b  jmp     short loc_180011B70
0x180011b6d  mov     rax, rdi
0x180011b70  mov     [rbx+80h], rax
0x180011b77  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180011b7e  test    rax, rax
0x180011b81  jz      short loc_180011B8B
0x180011b83  mov     rcx, rbx
0x180011b86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b8b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180011b92  test    rax, rax
0x180011b95  jz      short loc_180011BAD
0x180011b97  mov     rdx, [rsp+78h+arg_60]
0x180011b9f  mov     r8d, 400h
0x180011ba5  mov     rcx, rbx
0x180011ba8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bad  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011bb4  test    rax, rax
0x180011bb7  jz      short loc_180011BC1
0x180011bb9  mov     rcx, rbx
0x180011bbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bc1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011bc8  test    rax, rax
0x180011bcb  jz      short loc_180011BDB
0x180011bcd  test    byte ptr [rbx+4], 2
0x180011bd1  jnz     short loc_180011BDB
0x180011bd3  mov     rcx, rbx
0x180011bd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bdb  cmp     [rbx+8], edi
0x180011bde  jl      short loc_180011BFB
0x180011be0  cmp     ebp, 3
0x180011be3  jz      short loc_180011BEB
0x180011be5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180011beb  mov     ecx, 8000FFFFh; this
0x180011bf0  mov     [rbx+8], ecx
0x180011bf3  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011bf8  mov     [rbx+0Ch], eax
0x180011bfb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180011c02  jnz     short loc_180011C29
0x180011c04  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180011c0b  test    rax, rax
0x180011c0e  jz      short loc_180011C19
0x180011c10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c15  test    al, al
0x180011c17  jmp     short loc_180011C27
0x180011c19  call    cs:__imp_IsDebuggerPresent
0x180011c20  nop     dword ptr [rax+rax+00h]
0x180011c25  test    eax, eax
0x180011c27  jz      short loc_180011C2F
0x180011c29  test    byte ptr [rbx+4], 2
0x180011c2d  jz      short loc_180011C53
0x180011c2f  mov     rax, cs:g_pfnResultLoggingCallback
0x180011c36  test    rax, rax
0x180011c39  jz      short loc_180011C9E
0x180011c3b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011c42  jnz     short loc_180011C9E
0x180011c44  xor     r8d, r8d
0x180011c47  xor     edx, edx
0x180011c49  mov     rcx, rbx
0x180011c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c51  jmp     short loc_180011C9E
0x180011c53  mov     rax, cs:g_pfnResultLoggingCallback
0x180011c5a  mov     esi, 800h
0x180011c5f  test    rax, rax
0x180011c62  jz      short loc_180011C7B
0x180011c64  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011c6b  jnz     short loc_180011C7B
0x180011c6d  mov     r8d, esi
0x180011c70  mov     rdx, r14
0x180011c73  mov     rcx, rbx
0x180011c76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c7b  cmp     [r14], di
0x180011c7f  jnz     short loc_180011C8F
0x180011c81  mov     r8, rbx; unsigned __int64
0x180011c84  mov     rdx, rsi; unsigned __int16 *
0x180011c87  mov     rcx, r14; this
0x180011c8a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180011c8f  mov     rcx, r14; lpOutputString
0x180011c92  call    cs:__imp_OutputDebugStringW
0x180011c99  nop     dword ptr [rax+rax+00h]
0x180011c9e  test    byte ptr [rbx+4], 4
0x180011ca2  jnz     short loc_180011CAD
0x180011ca4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180011cab  jz      short loc_180011CBE
0x180011cad  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180011cb4  test    rax, rax
0x180011cb7  jz      short loc_180011CBE
0x180011cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cbe  mov     rbx, [rsp+78h+arg_10]
0x180011cc6  add     rsp, 40h
0x180011cca  pop     r15
0x180011ccc  pop     r14
0x180011cce  pop     r13
0x180011cd0  pop     r12
0x180011cd2  pop     rdi
0x180011cd3  pop     rsi
0x180011cd4  pop     rbp
0x180011cd5  retn
```
