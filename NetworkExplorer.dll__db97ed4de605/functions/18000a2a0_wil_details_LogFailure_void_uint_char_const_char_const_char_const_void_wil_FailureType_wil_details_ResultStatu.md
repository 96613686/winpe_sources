# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000a2a0`
- end: `0x18000a599`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180008218`
- `0x180008560`

## callees

- `0x180006f5c`
- `0x180008160`
- `0x1800097dc`
- `0x18000a2a0`
- `0x18000ad50`
- `0x18000ad70`
- `0x18000ad84`
- `0x18000ada0`
- `0x18000c664`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a3c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a3c3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a4e2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a4e2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a554`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a554`

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
0x18000a2a0  mov     [rsp+arg_10], rbx
0x18000a2a5  mov     [rsp+arg_8], edx
0x18000a2a9  mov     [rsp+arg_0], rcx
0x18000a2ae  push    rbp
0x18000a2af  push    rsi
0x18000a2b0  push    rdi
0x18000a2b1  push    r12
0x18000a2b3  push    r13
0x18000a2b5  push    r14
0x18000a2b7  push    r15
0x18000a2b9  sub     rsp, 40h
0x18000a2bd  mov     r12, r9
0x18000a2c0  mov     r13, r8
0x18000a2c3  mov     r10, rcx
0x18000a2c6  xor     eax, eax
0x18000a2c8  mov     rsi, [rsp+78h+lpOutputString]
0x18000a2d0  mov     [rsi], ax
0x18000a2d3  mov     rax, [rsp+78h+arg_60]
0x18000a2db  mov     byte ptr [rax], 0
0x18000a2de  mov     r14, [rsp+78h+arg_38]
0x18000a2e6  mov     edi, [r14]
0x18000a2e9  mov     rbx, [rsp+78h+arg_78]
0x18000a2f1  mov     [rbx+8], edi
0x18000a2f4  mov     eax, [r14+4]
0x18000a2f8  mov     [rbx+0Ch], eax
0x18000a2fb  xor     ebp, ebp
0x18000a2fd  mov     r15d, [rsp+78h+arg_30]
0x18000a305  mov     ecx, r15d
0x18000a308  test    r15d, r15d
0x18000a30b  jz      short loc_18000A373
0x18000a30d  sub     ecx, 1
0x18000a310  jz      short loc_18000A36A
0x18000a312  sub     ecx, 1
0x18000a315  jz      short loc_18000A325
0x18000a317  cmp     ecx, 1
0x18000a31a  jnz     short loc_18000A37C
0x18000a31c  mov     ecx, edi; this
0x18000a31e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a323  jmp     short loc_18000A37A
0x18000a325  test    edi, edi
0x18000a327  js      short loc_18000A361
0x18000a329  mov     edi, 8007029Ch
0x18000a32e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a332  mov     rax, [rsp+78h+arg_28]
0x18000a33a  mov     [rsp+78h+var_50], rax; __int64
0x18000a33f  mov     rax, [rsp+78h+arg_20]
0x18000a347  mov     [rsp+78h+var_58], rax; __int64
0x18000a34c  mov     rcx, r10; int
0x18000a34f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a354  mov     [rbx+8], edi
0x18000a357  mov     ecx, edi; this
0x18000a359  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a35e  mov     [rbx+0Ch], eax
0x18000a361  mov     ecx, edi; this
0x18000a363  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a368  jmp     short loc_18000A37A
0x18000a36a  mov     ecx, edi; this
0x18000a36c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a371  jmp     short loc_18000A37A
0x18000a373  mov     ecx, edi; this
0x18000a375  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a37a  mov     ebp, eax
0x18000a37c  mov     [rbx], r15d
0x18000a37f  mov     eax, [rsp+78h+arg_70]
0x18000a386  mov     [rbx+4], eax
0x18000a389  cmp     dword ptr [r14+8], 1
0x18000a38e  jnz     short loc_18000A396
0x18000a390  or      eax, 8
0x18000a393  mov     [rbx+4], eax
0x18000a396  mov     eax, 1
0x18000a39b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a3a3  inc     eax
0x18000a3a5  mov     [rbx+10h], eax
0x18000a3a8  mov     rax, [rsp+78h+arg_40]
0x18000a3b0  xor     edi, edi
0x18000a3b2  test    rax, rax
0x18000a3b5  jz      short loc_18000A3BC
0x18000a3b7  cmp     [rax], di
0x18000a3ba  jnz     short loc_18000A3BF
0x18000a3bc  mov     rax, rdi
0x18000a3bf  mov     [rbx+18h], rax
0x18000a3c3  call    cs:__imp_GetCurrentThreadId
0x18000a3c9  mov     [rbx+20h], eax
0x18000a3cc  mov     [rbx+38h], r13
0x18000a3d0  mov     eax, [rsp+78h+arg_8]
0x18000a3d7  mov     [rbx+40h], eax
0x18000a3da  mov     [rbx+44h], ebp
0x18000a3dd  mov     rax, [rsp+78h+arg_20]
0x18000a3e5  mov     [rbx+28h], rax
0x18000a3e9  mov     [rbx+30h], r12
0x18000a3ed  mov     rax, [rsp+78h+arg_28]
0x18000a3f5  mov     [rbx+88h], rax
0x18000a3fc  mov     rax, [rsp+78h+arg_0]
0x18000a404  mov     [rbx+90h], rax
0x18000a40b  mov     [rbx+48h], rdi
0x18000a40f  xorps   xmm0, xmm0
0x18000a412  xor     eax, eax
0x18000a414  movups  xmmword ptr [rbx+68h], xmm0
0x18000a418  mov     [rbx+78h], rax
0x18000a41c  movups  xmmword ptr [rbx+50h], xmm0
0x18000a420  mov     [rbx+60h], rax
0x18000a424  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a42b  test    rax, rax
0x18000a42e  jz      short loc_18000A437
0x18000a430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a435  jmp     short loc_18000A43A
0x18000a437  mov     rax, rdi
0x18000a43a  mov     [rbx+80h], rax
0x18000a441  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a448  test    rax, rax
0x18000a44b  jz      short loc_18000A455
0x18000a44d  mov     rcx, rbx
0x18000a450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a455  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a45c  test    rax, rax
0x18000a45f  jz      short loc_18000A477
0x18000a461  mov     r8d, 400h
0x18000a467  mov     rdx, [rsp+78h+arg_60]
0x18000a46f  mov     rcx, rbx
0x18000a472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a477  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a47e  test    rax, rax
0x18000a481  jz      short loc_18000A48B
0x18000a483  mov     rcx, rbx
0x18000a486  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a48b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a492  test    rax, rax
0x18000a495  jz      short loc_18000A4A5
0x18000a497  test    byte ptr [rbx+4], 2
0x18000a49b  jnz     short loc_18000A4A5
0x18000a49d  mov     rcx, rbx
0x18000a4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4a5  cmp     [rbx+8], edi
0x18000a4a8  jl      short loc_18000A4C4
0x18000a4aa  cmp     r15d, 3
0x18000a4ae  jnz     loc_18000A593
0x18000a4b4  mov     ecx, 8000FFFFh; this
0x18000a4b9  mov     [rbx+8], ecx
0x18000a4bc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a4c1  mov     [rbx+0Ch], eax
0x18000a4c4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a4cb  jnz     short loc_18000A4EC
0x18000a4cd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a4d4  test    rax, rax
0x18000a4d7  jz      short loc_18000A4E2
0x18000a4d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4de  test    al, al
0x18000a4e0  jmp     short loc_18000A4EA
0x18000a4e2  call    cs:__imp_IsDebuggerPresent
0x18000a4e8  test    eax, eax
0x18000a4ea  jz      short loc_18000A4F2
0x18000a4ec  test    byte ptr [rbx+4], 2
0x18000a4f0  jz      short loc_18000A516
0x18000a4f2  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a4f9  test    rax, rax
0x18000a4fc  jz      short loc_18000A55A
0x18000a4fe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a505  jnz     short loc_18000A55A
0x18000a507  xor     r8d, r8d
0x18000a50a  xor     edx, edx
0x18000a50c  mov     rcx, rbx
0x18000a50f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a514  jmp     short loc_18000A55A
0x18000a516  mov     ebp, 800h
0x18000a51b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a522  test    rax, rax
0x18000a525  jz      short loc_18000A53E
0x18000a527  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a52e  jnz     short loc_18000A53E
0x18000a530  mov     r8d, ebp
0x18000a533  mov     rdx, rsi
0x18000a536  mov     rcx, rbx
0x18000a539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a53e  cmp     [rsi], di
0x18000a541  jnz     short loc_18000A551
0x18000a543  mov     r8, rbx; unsigned __int64
0x18000a546  mov     rdx, rbp; unsigned __int16 *
0x18000a549  mov     rcx, rsi; this
0x18000a54c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a551  mov     rcx, rsi; lpOutputString
0x18000a554  call    cs:__imp_OutputDebugStringW
0x18000a55a  test    byte ptr [rbx+4], 4
0x18000a55e  jnz     short loc_18000A569
0x18000a560  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a567  jz      short loc_18000A57B
0x18000a569  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a570  test    rax, rax
0x18000a573  jz      short loc_18000A57B
0x18000a575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a57a  nop
0x18000a57b  mov     rbx, [rsp+78h+arg_10]
0x18000a583  add     rsp, 40h
0x18000a587  pop     r15
0x18000a589  pop     r14
0x18000a58b  pop     r13
0x18000a58d  pop     r12
0x18000a58f  pop     rdi
0x18000a590  pop     rsi
0x18000a591  pop     rbp
0x18000a592  retn
0x18000a593  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
