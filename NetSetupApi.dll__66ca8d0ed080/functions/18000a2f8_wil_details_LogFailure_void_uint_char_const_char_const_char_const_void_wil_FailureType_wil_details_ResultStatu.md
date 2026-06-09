# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000a2f8`
- end: `0x18000a5f5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `765`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180008f74`
- `0x180009028`
- `0x180009118`

## callees

- `0x180007c78`
- `0x180008ec4`
- `0x180009b94`
- `0x18000a2f8`
- `0x18000a9ac`
- `0x18000a9d0`
- `0x18000a9e4`
- `0x18000aa00`
- `0x18000b3c4`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a423`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a423`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a544`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a544`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a5b6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a5b6`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v25)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0, v23);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v23);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v23);
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
0x18000a2f8  mov     rax, rsp
0x18000a2fb  mov     [rax+10h], edx
0x18000a2fe  mov     [rax+8], rcx
0x18000a302  push    rbp
0x18000a303  push    rsi
0x18000a304  push    rdi
0x18000a305  push    r12
0x18000a307  push    r13
0x18000a309  push    r14
0x18000a30b  push    r15
0x18000a30d  sub     rsp, 50h
0x18000a311  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18000a319  mov     [rax+18h], rbx
0x18000a31d  mov     r12, r9
0x18000a320  mov     r13, r8
0x18000a323  mov     r10, rcx
0x18000a326  xor     eax, eax
0x18000a328  mov     rsi, [rsp+88h+lpOutputString]
0x18000a330  mov     [rsi], ax
0x18000a333  mov     rax, [rsp+88h+arg_60]
0x18000a33b  mov     byte ptr [rax], 0
0x18000a33e  mov     r14, [rsp+88h+arg_38]
0x18000a346  mov     edi, [r14]
0x18000a349  mov     rbx, [rsp+88h+arg_78]
0x18000a351  mov     [rbx+8], edi
0x18000a354  mov     eax, [r14+4]
0x18000a358  mov     [rbx+0Ch], eax
0x18000a35b  xor     ebp, ebp
0x18000a35d  mov     r15d, [rsp+88h+arg_30]
0x18000a365  mov     ecx, r15d
0x18000a368  test    r15d, r15d
0x18000a36b  jz      short loc_18000A3D3
0x18000a36d  sub     ecx, 1
0x18000a370  jz      short loc_18000A3CA
0x18000a372  sub     ecx, 1
0x18000a375  jz      short loc_18000A385
0x18000a377  cmp     ecx, 1
0x18000a37a  jnz     short loc_18000A3DC
0x18000a37c  mov     ecx, edi; this
0x18000a37e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a383  jmp     short loc_18000A3DA
0x18000a385  test    edi, edi
0x18000a387  js      short loc_18000A3C1
0x18000a389  mov     edi, 8007029Ch
0x18000a38e  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x18000a392  mov     rax, [rsp+88h+arg_28]
0x18000a39a  mov     [rsp+88h+var_60], rax; __int64
0x18000a39f  mov     rax, [rsp+88h+arg_20]
0x18000a3a7  mov     [rsp+88h+var_68], rax; __int64
0x18000a3ac  mov     rcx, r10; int
0x18000a3af  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a3b4  mov     [rbx+8], edi
0x18000a3b7  mov     ecx, edi; this
0x18000a3b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a3be  mov     [rbx+0Ch], eax
0x18000a3c1  mov     ecx, edi; this
0x18000a3c3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a3c8  jmp     short loc_18000A3DA
0x18000a3ca  mov     ecx, edi; this
0x18000a3cc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a3d1  jmp     short loc_18000A3DA
0x18000a3d3  mov     ecx, edi; this
0x18000a3d5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a3da  mov     ebp, eax
0x18000a3dc  mov     [rbx], r15d
0x18000a3df  mov     eax, [rsp+88h+arg_70]
0x18000a3e6  mov     [rbx+4], eax
0x18000a3e9  cmp     dword ptr [r14+8], 1
0x18000a3ee  jnz     short loc_18000A3F6
0x18000a3f0  or      eax, 8
0x18000a3f3  mov     [rbx+4], eax
0x18000a3f6  mov     eax, 1
0x18000a3fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a403  inc     eax
0x18000a405  mov     [rbx+10h], eax
0x18000a408  mov     rax, [rsp+88h+arg_40]
0x18000a410  xor     edi, edi
0x18000a412  test    rax, rax
0x18000a415  jz      short loc_18000A41C
0x18000a417  cmp     [rax], di
0x18000a41a  jnz     short loc_18000A41F
0x18000a41c  mov     rax, rdi
0x18000a41f  mov     [rbx+18h], rax
0x18000a423  call    cs:__imp_GetCurrentThreadId
0x18000a429  mov     [rbx+20h], eax
0x18000a42c  mov     [rbx+38h], r13
0x18000a430  mov     eax, [rsp+88h+arg_8]
0x18000a437  mov     [rbx+40h], eax
0x18000a43a  mov     [rbx+44h], ebp
0x18000a43d  mov     rax, [rsp+88h+arg_20]
0x18000a445  mov     [rbx+28h], rax
0x18000a449  mov     [rbx+30h], r12
0x18000a44d  mov     rax, [rsp+88h+arg_28]
0x18000a455  mov     [rbx+88h], rax
0x18000a45c  mov     rax, [rsp+88h+arg_0]
0x18000a464  mov     [rbx+90h], rax
0x18000a46b  mov     [rbx+48h], rdi
0x18000a46f  xorps   xmm0, xmm0
0x18000a472  xor     eax, eax
0x18000a474  movups  xmmword ptr [rbx+68h], xmm0
0x18000a478  mov     [rbx+78h], rax
0x18000a47c  movups  xmmword ptr [rbx+50h], xmm0
0x18000a480  mov     [rbx+60h], rax
0x18000a484  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a48b  test    rax, rax
0x18000a48e  jz      short loc_18000A497
0x18000a490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a495  jmp     short loc_18000A49A
0x18000a497  mov     rax, rdi
0x18000a49a  mov     [rbx+80h], rax
0x18000a4a1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a4a8  test    rax, rax
0x18000a4ab  jz      short loc_18000A4B5
0x18000a4ad  mov     rcx, rbx
0x18000a4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4b5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a4bc  test    rax, rax
0x18000a4bf  jz      short loc_18000A4D7
0x18000a4c1  mov     r8d, 400h
0x18000a4c7  mov     rdx, [rsp+88h+arg_60]
0x18000a4cf  mov     rcx, rbx
0x18000a4d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4d7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a4de  test    rax, rax
0x18000a4e1  jz      short loc_18000A4EB
0x18000a4e3  mov     rcx, rbx
0x18000a4e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4eb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a4f2  test    rax, rax
0x18000a4f5  jz      short loc_18000A505
0x18000a4f7  test    byte ptr [rbx+4], 2
0x18000a4fb  jnz     short loc_18000A505
0x18000a4fd  mov     rcx, rbx
0x18000a500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a505  cmp     [rbx+8], edi
0x18000a508  jl      short loc_18000A526
0x18000a50a  cmp     r15d, 3
0x18000a50e  jz      short loc_18000A516
0x18000a510  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a516  mov     ecx, 8000FFFFh; this
0x18000a51b  mov     [rbx+8], ecx
0x18000a51e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a523  mov     [rbx+0Ch], eax
0x18000a526  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a52d  jnz     short loc_18000A54E
0x18000a52f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a536  test    rax, rax
0x18000a539  jz      short loc_18000A544
0x18000a53b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a540  test    al, al
0x18000a542  jmp     short loc_18000A54C
0x18000a544  call    cs:__imp_IsDebuggerPresent
0x18000a54a  test    eax, eax
0x18000a54c  jz      short loc_18000A554
0x18000a54e  test    byte ptr [rbx+4], 2
0x18000a552  jz      short loc_18000A578
0x18000a554  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a55b  test    rax, rax
0x18000a55e  jz      short loc_18000A5BC
0x18000a560  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a567  jnz     short loc_18000A5BC
0x18000a569  xor     r8d, r8d
0x18000a56c  xor     edx, edx
0x18000a56e  mov     rcx, rbx
0x18000a571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a576  jmp     short loc_18000A5BC
0x18000a578  mov     ebp, 800h
0x18000a57d  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a584  test    rax, rax
0x18000a587  jz      short loc_18000A5A0
0x18000a589  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a590  jnz     short loc_18000A5A0
0x18000a592  mov     r8d, ebp
0x18000a595  mov     rdx, rsi
0x18000a598  mov     rcx, rbx
0x18000a59b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5a0  cmp     [rsi], di
0x18000a5a3  jnz     short loc_18000A5B3
0x18000a5a5  mov     r8, rbx; unsigned __int64
0x18000a5a8  mov     rdx, rbp; wchar_t *
0x18000a5ab  mov     rcx, rsi; this
0x18000a5ae  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000a5b3  mov     rcx, rsi; lpOutputString
0x18000a5b6  call    cs:__imp_OutputDebugStringW
0x18000a5bc  test    byte ptr [rbx+4], 4
0x18000a5c0  jnz     short loc_18000A5CB
0x18000a5c2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a5c9  jz      short loc_18000A5DD
0x18000a5cb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a5d2  test    rax, rax
0x18000a5d5  jz      short loc_18000A5DD
0x18000a5d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5dc  nop
0x18000a5dd  mov     rbx, [rsp+88h+arg_10]
0x18000a5e5  add     rsp, 50h
0x18000a5e9  pop     r15
0x18000a5eb  pop     r14
0x18000a5ed  pop     r13
0x18000a5ef  pop     r12
0x18000a5f1  pop     rdi
0x18000a5f2  pop     rsi
0x18000a5f3  pop     rbp
0x18000a5f4  retn
```
