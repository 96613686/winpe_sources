# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000a194`
- end: `0x18000a4a0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800097c8`

## callees

- `0x180009210`
- `0x180009a4c`
- `0x180009fd0`
- `0x18000a194`
- `0x18000ac28`
- `0x18000ac50`
- `0x18000ac64`
- `0x18000ac84`
- `0x18000ada0`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a2b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a2b7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a454`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a454`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a3dc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a3dc`

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
0x18000a194  mov     [rsp+arg_10], rbx
0x18000a199  mov     [rsp+arg_8], edx
0x18000a19d  mov     [rsp+arg_0], rcx
0x18000a1a2  push    rbp
0x18000a1a3  push    rsi
0x18000a1a4  push    rdi
0x18000a1a5  push    r12
0x18000a1a7  push    r13
0x18000a1a9  push    r14
0x18000a1ab  push    r15
0x18000a1ad  sub     rsp, 40h
0x18000a1b1  mov     r12, r9
0x18000a1b4  mov     r13, r8
0x18000a1b7  mov     r10, rcx
0x18000a1ba  xor     eax, eax
0x18000a1bc  mov     rsi, [rsp+78h+lpOutputString]
0x18000a1c4  mov     [rsi], ax
0x18000a1c7  mov     rax, [rsp+78h+arg_60]
0x18000a1cf  mov     byte ptr [rax], 0
0x18000a1d2  mov     r14, [rsp+78h+arg_38]
0x18000a1da  mov     edi, [r14]
0x18000a1dd  mov     rbx, [rsp+78h+arg_78]
0x18000a1e5  mov     [rbx+8], edi
0x18000a1e8  mov     eax, [r14+4]
0x18000a1ec  mov     [rbx+0Ch], eax
0x18000a1ef  xor     ebp, ebp
0x18000a1f1  mov     r15d, [rsp+78h+arg_30]
0x18000a1f9  mov     ecx, r15d
0x18000a1fc  test    r15d, r15d
0x18000a1ff  jz      short loc_18000A267
0x18000a201  sub     ecx, 1
0x18000a204  jz      short loc_18000A25E
0x18000a206  sub     ecx, 1
0x18000a209  jz      short loc_18000A219
0x18000a20b  cmp     ecx, 1
0x18000a20e  jnz     short loc_18000A270
0x18000a210  mov     ecx, edi; this
0x18000a212  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a217  jmp     short loc_18000A26E
0x18000a219  test    edi, edi
0x18000a21b  js      short loc_18000A255
0x18000a21d  mov     edi, 8007029Ch
0x18000a222  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a226  mov     rax, [rsp+78h+arg_28]
0x18000a22e  mov     [rsp+78h+var_50], rax; __int64
0x18000a233  mov     rax, [rsp+78h+arg_20]
0x18000a23b  mov     [rsp+78h+var_58], rax; __int64
0x18000a240  mov     rcx, r10; int
0x18000a243  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a248  mov     [rbx+8], edi
0x18000a24b  mov     ecx, edi; this
0x18000a24d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a252  mov     [rbx+0Ch], eax
0x18000a255  mov     ecx, edi; this
0x18000a257  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a25c  jmp     short loc_18000A26E
0x18000a25e  mov     ecx, edi; this
0x18000a260  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a265  jmp     short loc_18000A26E
0x18000a267  mov     ecx, edi; this
0x18000a269  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a26e  mov     ebp, eax
0x18000a270  mov     [rbx], r15d
0x18000a273  mov     eax, [rsp+78h+arg_70]
0x18000a27a  mov     [rbx+4], eax
0x18000a27d  cmp     dword ptr [r14+8], 1
0x18000a282  jnz     short loc_18000A28A
0x18000a284  or      eax, 8
0x18000a287  mov     [rbx+4], eax
0x18000a28a  mov     eax, 1
0x18000a28f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a297  inc     eax
0x18000a299  mov     [rbx+10h], eax
0x18000a29c  mov     rax, [rsp+78h+arg_40]
0x18000a2a4  xor     edi, edi
0x18000a2a6  test    rax, rax
0x18000a2a9  jz      short loc_18000A2B0
0x18000a2ab  cmp     [rax], di
0x18000a2ae  jnz     short loc_18000A2B3
0x18000a2b0  mov     rax, rdi
0x18000a2b3  mov     [rbx+18h], rax
0x18000a2b7  call    cs:__imp_GetCurrentThreadId
0x18000a2be  nop     dword ptr [rax+rax+00h]
0x18000a2c3  mov     [rbx+20h], eax
0x18000a2c6  mov     [rbx+38h], r13
0x18000a2ca  mov     eax, [rsp+78h+arg_8]
0x18000a2d1  mov     [rbx+40h], eax
0x18000a2d4  mov     [rbx+44h], ebp
0x18000a2d7  mov     rax, [rsp+78h+arg_20]
0x18000a2df  mov     [rbx+28h], rax
0x18000a2e3  mov     [rbx+30h], r12
0x18000a2e7  mov     rax, [rsp+78h+arg_28]
0x18000a2ef  mov     [rbx+88h], rax
0x18000a2f6  mov     rax, [rsp+78h+arg_0]
0x18000a2fe  mov     [rbx+90h], rax
0x18000a305  mov     [rbx+48h], rdi
0x18000a309  xorps   xmm0, xmm0
0x18000a30c  xor     eax, eax
0x18000a30e  movups  xmmword ptr [rbx+68h], xmm0
0x18000a312  mov     [rbx+78h], rax
0x18000a316  movups  xmmword ptr [rbx+50h], xmm0
0x18000a31a  mov     [rbx+60h], rax
0x18000a31e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a325  test    rax, rax
0x18000a328  jz      short loc_18000A331
0x18000a32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a32f  jmp     short loc_18000A334
0x18000a331  mov     rax, rdi
0x18000a334  mov     [rbx+80h], rax
0x18000a33b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a342  test    rax, rax
0x18000a345  jz      short loc_18000A34F
0x18000a347  mov     rcx, rbx
0x18000a34a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a34f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a356  test    rax, rax
0x18000a359  jz      short loc_18000A371
0x18000a35b  mov     r8d, 400h
0x18000a361  mov     rdx, [rsp+78h+arg_60]
0x18000a369  mov     rcx, rbx
0x18000a36c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a371  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a378  test    rax, rax
0x18000a37b  jz      short loc_18000A385
0x18000a37d  mov     rcx, rbx
0x18000a380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a385  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a38c  test    rax, rax
0x18000a38f  jz      short loc_18000A39F
0x18000a391  test    byte ptr [rbx+4], 2
0x18000a395  jnz     short loc_18000A39F
0x18000a397  mov     rcx, rbx
0x18000a39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a39f  cmp     [rbx+8], edi
0x18000a3a2  jl      short loc_18000A3BE
0x18000a3a4  cmp     r15d, 3
0x18000a3a8  jnz     loc_18000A49A
0x18000a3ae  mov     ecx, 8000FFFFh; this
0x18000a3b3  mov     [rbx+8], ecx
0x18000a3b6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a3bb  mov     [rbx+0Ch], eax
0x18000a3be  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a3c5  jnz     short loc_18000A3EC
0x18000a3c7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a3ce  test    rax, rax
0x18000a3d1  jz      short loc_18000A3DC
0x18000a3d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3d8  test    al, al
0x18000a3da  jmp     short loc_18000A3EA
0x18000a3dc  call    cs:__imp_IsDebuggerPresent
0x18000a3e3  nop     dword ptr [rax+rax+00h]
0x18000a3e8  test    eax, eax
0x18000a3ea  jz      short loc_18000A3F2
0x18000a3ec  test    byte ptr [rbx+4], 2
0x18000a3f0  jz      short loc_18000A416
0x18000a3f2  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a3f9  test    rax, rax
0x18000a3fc  jz      short loc_18000A460
0x18000a3fe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a405  jnz     short loc_18000A460
0x18000a407  xor     r8d, r8d
0x18000a40a  xor     edx, edx
0x18000a40c  mov     rcx, rbx
0x18000a40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a414  jmp     short loc_18000A460
0x18000a416  mov     ebp, 800h
0x18000a41b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a422  test    rax, rax
0x18000a425  jz      short loc_18000A43E
0x18000a427  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a42e  jnz     short loc_18000A43E
0x18000a430  mov     r8d, ebp
0x18000a433  mov     rdx, rsi
0x18000a436  mov     rcx, rbx
0x18000a439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a43e  cmp     [rsi], di
0x18000a441  jnz     short loc_18000A451
0x18000a443  mov     r8, rbx; unsigned __int64
0x18000a446  mov     rdx, rbp; unsigned __int16 *
0x18000a449  mov     rcx, rsi; this
0x18000a44c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a451  mov     rcx, rsi; lpOutputString
0x18000a454  call    cs:__imp_OutputDebugStringW
0x18000a45b  nop     dword ptr [rax+rax+00h]
0x18000a460  test    byte ptr [rbx+4], 4
0x18000a464  jnz     short loc_18000A46F
0x18000a466  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a46d  jz      short loc_18000A481
0x18000a46f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a476  test    rax, rax
0x18000a479  jz      short loc_18000A481
0x18000a47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a480  nop
0x18000a481  mov     rbx, [rsp+78h+arg_10]
0x18000a489  add     rsp, 40h
0x18000a48d  pop     r15
0x18000a48f  pop     r14
0x18000a491  pop     r13
0x18000a493  pop     r12
0x18000a495  pop     rdi
0x18000a496  pop     rsi
0x18000a497  pop     rbp
0x18000a498  retn
0x18000a49a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
