# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180009f98`
- end: `0x18000a291`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800095e8`

## callees

- `0x180009058`
- `0x180009868`
- `0x180009dd4`
- `0x180009f98`
- `0x18000aa14`
- `0x18000aa30`
- `0x18000aa44`
- `0x18000aa60`
- `0x18000ab78`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a0bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a0bb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a24c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a24c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a1da`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a1da`

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
0x180009f98  mov     [rsp+arg_10], rbx
0x180009f9d  mov     [rsp+arg_8], edx
0x180009fa1  mov     [rsp+arg_0], rcx
0x180009fa6  push    rbp
0x180009fa7  push    rsi
0x180009fa8  push    rdi
0x180009fa9  push    r12
0x180009fab  push    r13
0x180009fad  push    r14
0x180009faf  push    r15
0x180009fb1  sub     rsp, 40h
0x180009fb5  mov     r12, r9
0x180009fb8  mov     r13, r8
0x180009fbb  mov     r10, rcx
0x180009fbe  xor     eax, eax
0x180009fc0  mov     rsi, [rsp+78h+lpOutputString]
0x180009fc8  mov     [rsi], ax
0x180009fcb  mov     rax, [rsp+78h+arg_60]
0x180009fd3  mov     byte ptr [rax], 0
0x180009fd6  mov     r14, [rsp+78h+arg_38]
0x180009fde  mov     edi, [r14]
0x180009fe1  mov     rbx, [rsp+78h+arg_78]
0x180009fe9  mov     [rbx+8], edi
0x180009fec  mov     eax, [r14+4]
0x180009ff0  mov     [rbx+0Ch], eax
0x180009ff3  xor     ebp, ebp
0x180009ff5  mov     r15d, [rsp+78h+arg_30]
0x180009ffd  mov     ecx, r15d
0x18000a000  test    r15d, r15d
0x18000a003  jz      short loc_18000A06B
0x18000a005  sub     ecx, 1
0x18000a008  jz      short loc_18000A062
0x18000a00a  sub     ecx, 1
0x18000a00d  jz      short loc_18000A01D
0x18000a00f  cmp     ecx, 1
0x18000a012  jnz     short loc_18000A074
0x18000a014  mov     ecx, edi; this
0x18000a016  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a01b  jmp     short loc_18000A072
0x18000a01d  test    edi, edi
0x18000a01f  js      short loc_18000A059
0x18000a021  mov     edi, 8007029Ch
0x18000a026  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a02a  mov     rax, [rsp+78h+arg_28]
0x18000a032  mov     [rsp+78h+var_50], rax; __int64
0x18000a037  mov     rax, [rsp+78h+arg_20]
0x18000a03f  mov     [rsp+78h+var_58], rax; __int64
0x18000a044  mov     rcx, r10; int
0x18000a047  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a04c  mov     [rbx+8], edi
0x18000a04f  mov     ecx, edi; this
0x18000a051  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a056  mov     [rbx+0Ch], eax
0x18000a059  mov     ecx, edi; this
0x18000a05b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a060  jmp     short loc_18000A072
0x18000a062  mov     ecx, edi; this
0x18000a064  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a069  jmp     short loc_18000A072
0x18000a06b  mov     ecx, edi; this
0x18000a06d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a072  mov     ebp, eax
0x18000a074  mov     [rbx], r15d
0x18000a077  mov     eax, [rsp+78h+arg_70]
0x18000a07e  mov     [rbx+4], eax
0x18000a081  cmp     dword ptr [r14+8], 1
0x18000a086  jnz     short loc_18000A08E
0x18000a088  or      eax, 8
0x18000a08b  mov     [rbx+4], eax
0x18000a08e  mov     eax, 1
0x18000a093  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a09b  inc     eax
0x18000a09d  mov     [rbx+10h], eax
0x18000a0a0  mov     rax, [rsp+78h+arg_40]
0x18000a0a8  xor     edi, edi
0x18000a0aa  test    rax, rax
0x18000a0ad  jz      short loc_18000A0B4
0x18000a0af  cmp     [rax], di
0x18000a0b2  jnz     short loc_18000A0B7
0x18000a0b4  mov     rax, rdi
0x18000a0b7  mov     [rbx+18h], rax
0x18000a0bb  call    cs:__imp_GetCurrentThreadId
0x18000a0c1  mov     [rbx+20h], eax
0x18000a0c4  mov     [rbx+38h], r13
0x18000a0c8  mov     eax, [rsp+78h+arg_8]
0x18000a0cf  mov     [rbx+40h], eax
0x18000a0d2  mov     [rbx+44h], ebp
0x18000a0d5  mov     rax, [rsp+78h+arg_20]
0x18000a0dd  mov     [rbx+28h], rax
0x18000a0e1  mov     [rbx+30h], r12
0x18000a0e5  mov     rax, [rsp+78h+arg_28]
0x18000a0ed  mov     [rbx+88h], rax
0x18000a0f4  mov     rax, [rsp+78h+arg_0]
0x18000a0fc  mov     [rbx+90h], rax
0x18000a103  mov     [rbx+48h], rdi
0x18000a107  xorps   xmm0, xmm0
0x18000a10a  xor     eax, eax
0x18000a10c  movups  xmmword ptr [rbx+68h], xmm0
0x18000a110  mov     [rbx+78h], rax
0x18000a114  movups  xmmword ptr [rbx+50h], xmm0
0x18000a118  mov     [rbx+60h], rax
0x18000a11c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a123  test    rax, rax
0x18000a126  jz      short loc_18000A12F
0x18000a128  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a12d  jmp     short loc_18000A132
0x18000a12f  mov     rax, rdi
0x18000a132  mov     [rbx+80h], rax
0x18000a139  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a140  test    rax, rax
0x18000a143  jz      short loc_18000A14D
0x18000a145  mov     rcx, rbx
0x18000a148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a14d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a154  test    rax, rax
0x18000a157  jz      short loc_18000A16F
0x18000a159  mov     r8d, 400h
0x18000a15f  mov     rdx, [rsp+78h+arg_60]
0x18000a167  mov     rcx, rbx
0x18000a16a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a16f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a176  test    rax, rax
0x18000a179  jz      short loc_18000A183
0x18000a17b  mov     rcx, rbx
0x18000a17e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a183  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a18a  test    rax, rax
0x18000a18d  jz      short loc_18000A19D
0x18000a18f  test    byte ptr [rbx+4], 2
0x18000a193  jnz     short loc_18000A19D
0x18000a195  mov     rcx, rbx
0x18000a198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a19d  cmp     [rbx+8], edi
0x18000a1a0  jl      short loc_18000A1BC
0x18000a1a2  cmp     r15d, 3
0x18000a1a6  jnz     loc_18000A28B
0x18000a1ac  mov     ecx, 8000FFFFh; this
0x18000a1b1  mov     [rbx+8], ecx
0x18000a1b4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a1b9  mov     [rbx+0Ch], eax
0x18000a1bc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a1c3  jnz     short loc_18000A1E4
0x18000a1c5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a1cc  test    rax, rax
0x18000a1cf  jz      short loc_18000A1DA
0x18000a1d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1d6  test    al, al
0x18000a1d8  jmp     short loc_18000A1E2
0x18000a1da  call    cs:__imp_IsDebuggerPresent
0x18000a1e0  test    eax, eax
0x18000a1e2  jz      short loc_18000A1EA
0x18000a1e4  test    byte ptr [rbx+4], 2
0x18000a1e8  jz      short loc_18000A20E
0x18000a1ea  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a1f1  test    rax, rax
0x18000a1f4  jz      short loc_18000A252
0x18000a1f6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a1fd  jnz     short loc_18000A252
0x18000a1ff  xor     r8d, r8d
0x18000a202  xor     edx, edx
0x18000a204  mov     rcx, rbx
0x18000a207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a20c  jmp     short loc_18000A252
0x18000a20e  mov     ebp, 800h
0x18000a213  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a21a  test    rax, rax
0x18000a21d  jz      short loc_18000A236
0x18000a21f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a226  jnz     short loc_18000A236
0x18000a228  mov     r8d, ebp
0x18000a22b  mov     rdx, rsi
0x18000a22e  mov     rcx, rbx
0x18000a231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a236  cmp     [rsi], di
0x18000a239  jnz     short loc_18000A249
0x18000a23b  mov     r8, rbx; unsigned __int64
0x18000a23e  mov     rdx, rbp; unsigned __int16 *
0x18000a241  mov     rcx, rsi; this
0x18000a244  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a249  mov     rcx, rsi; lpOutputString
0x18000a24c  call    cs:__imp_OutputDebugStringW
0x18000a252  test    byte ptr [rbx+4], 4
0x18000a256  jnz     short loc_18000A261
0x18000a258  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a25f  jz      short loc_18000A273
0x18000a261  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a268  test    rax, rax
0x18000a26b  jz      short loc_18000A273
0x18000a26d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a272  nop
0x18000a273  mov     rbx, [rsp+78h+arg_10]
0x18000a27b  add     rsp, 40h
0x18000a27f  pop     r15
0x18000a281  pop     r14
0x18000a283  pop     r13
0x18000a285  pop     r12
0x18000a287  pop     rdi
0x18000a288  pop     rsi
0x18000a289  pop     rbp
0x18000a28a  retn
0x18000a28b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
