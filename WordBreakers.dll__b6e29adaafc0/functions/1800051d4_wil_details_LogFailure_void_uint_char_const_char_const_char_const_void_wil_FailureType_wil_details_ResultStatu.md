# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800051d4`
- end: `0x1800054cd`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800037e4`

## callees

- `0x180003220`
- `0x180004874`
- `0x180005010`
- `0x1800051d4`
- `0x18000571c`
- `0x180005740`
- `0x180005754`
- `0x180005770`
- `0x18000669c`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800052f7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005416`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005416`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005488`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005488`

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
0x1800051d4  mov     [rsp+arg_10], rbx
0x1800051d9  mov     [rsp+arg_8], edx
0x1800051dd  mov     [rsp+arg_0], rcx
0x1800051e2  push    rbp
0x1800051e3  push    rsi
0x1800051e4  push    rdi
0x1800051e5  push    r12
0x1800051e7  push    r13
0x1800051e9  push    r14
0x1800051eb  push    r15
0x1800051ed  sub     rsp, 40h
0x1800051f1  mov     r12, r9
0x1800051f4  mov     r13, r8
0x1800051f7  mov     r10, rcx
0x1800051fa  xor     eax, eax
0x1800051fc  mov     rsi, [rsp+78h+lpOutputString]
0x180005204  mov     [rsi], ax
0x180005207  mov     rax, [rsp+78h+arg_60]
0x18000520f  mov     byte ptr [rax], 0
0x180005212  mov     r14, [rsp+78h+arg_38]
0x18000521a  mov     edi, [r14]
0x18000521d  mov     rbx, [rsp+78h+arg_78]
0x180005225  mov     [rbx+8], edi
0x180005228  mov     eax, [r14+4]
0x18000522c  mov     [rbx+0Ch], eax
0x18000522f  xor     ebp, ebp
0x180005231  mov     r15d, [rsp+78h+arg_30]
0x180005239  mov     ecx, r15d
0x18000523c  test    r15d, r15d
0x18000523f  jz      short loc_1800052A7
0x180005241  sub     ecx, 1
0x180005244  jz      short loc_18000529E
0x180005246  sub     ecx, 1
0x180005249  jz      short loc_180005259
0x18000524b  cmp     ecx, 1
0x18000524e  jnz     short loc_1800052B0
0x180005250  mov     ecx, edi; this
0x180005252  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005257  jmp     short loc_1800052AE
0x180005259  test    edi, edi
0x18000525b  js      short loc_180005295
0x18000525d  mov     edi, 8007029Ch
0x180005262  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005266  mov     rax, [rsp+78h+arg_28]
0x18000526e  mov     [rsp+78h+var_50], rax; __int64
0x180005273  mov     rax, [rsp+78h+arg_20]
0x18000527b  mov     [rsp+78h+var_58], rax; __int64
0x180005280  mov     rcx, r10; int
0x180005283  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005288  mov     [rbx+8], edi
0x18000528b  mov     ecx, edi; this
0x18000528d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005292  mov     [rbx+0Ch], eax
0x180005295  mov     ecx, edi; this
0x180005297  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000529c  jmp     short loc_1800052AE
0x18000529e  mov     ecx, edi; this
0x1800052a0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800052a5  jmp     short loc_1800052AE
0x1800052a7  mov     ecx, edi; this
0x1800052a9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800052ae  mov     ebp, eax
0x1800052b0  mov     [rbx], r15d
0x1800052b3  mov     eax, [rsp+78h+arg_70]
0x1800052ba  mov     [rbx+4], eax
0x1800052bd  cmp     dword ptr [r14+8], 1
0x1800052c2  jnz     short loc_1800052CA
0x1800052c4  or      eax, 8
0x1800052c7  mov     [rbx+4], eax
0x1800052ca  mov     eax, 1
0x1800052cf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800052d7  inc     eax
0x1800052d9  mov     [rbx+10h], eax
0x1800052dc  mov     rax, [rsp+78h+arg_40]
0x1800052e4  xor     edi, edi
0x1800052e6  test    rax, rax
0x1800052e9  jz      short loc_1800052F0
0x1800052eb  cmp     [rax], di
0x1800052ee  jnz     short loc_1800052F3
0x1800052f0  mov     rax, rdi
0x1800052f3  mov     [rbx+18h], rax
0x1800052f7  call    cs:__imp_GetCurrentThreadId
0x1800052fd  mov     [rbx+20h], eax
0x180005300  mov     [rbx+38h], r13
0x180005304  mov     eax, [rsp+78h+arg_8]
0x18000530b  mov     [rbx+40h], eax
0x18000530e  mov     [rbx+44h], ebp
0x180005311  mov     rax, [rsp+78h+arg_20]
0x180005319  mov     [rbx+28h], rax
0x18000531d  mov     [rbx+30h], r12
0x180005321  mov     rax, [rsp+78h+arg_28]
0x180005329  mov     [rbx+88h], rax
0x180005330  mov     rax, [rsp+78h+arg_0]
0x180005338  mov     [rbx+90h], rax
0x18000533f  mov     [rbx+48h], rdi
0x180005343  xorps   xmm0, xmm0
0x180005346  xor     eax, eax
0x180005348  movups  xmmword ptr [rbx+68h], xmm0
0x18000534c  mov     [rbx+78h], rax
0x180005350  movups  xmmword ptr [rbx+50h], xmm0
0x180005354  mov     [rbx+60h], rax
0x180005358  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000535f  test    rax, rax
0x180005362  jz      short loc_18000536B
0x180005364  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005369  jmp     short loc_18000536E
0x18000536b  mov     rax, rdi
0x18000536e  mov     [rbx+80h], rax
0x180005375  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000537c  test    rax, rax
0x18000537f  jz      short loc_180005389
0x180005381  mov     rcx, rbx
0x180005384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005389  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005390  test    rax, rax
0x180005393  jz      short loc_1800053AB
0x180005395  mov     r8d, 400h
0x18000539b  mov     rdx, [rsp+78h+arg_60]
0x1800053a3  mov     rcx, rbx
0x1800053a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053ab  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800053b2  test    rax, rax
0x1800053b5  jz      short loc_1800053BF
0x1800053b7  mov     rcx, rbx
0x1800053ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053bf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800053c6  test    rax, rax
0x1800053c9  jz      short loc_1800053D9
0x1800053cb  test    byte ptr [rbx+4], 2
0x1800053cf  jnz     short loc_1800053D9
0x1800053d1  mov     rcx, rbx
0x1800053d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053d9  cmp     [rbx+8], edi
0x1800053dc  jl      short loc_1800053F8
0x1800053de  cmp     r15d, 3
0x1800053e2  jnz     loc_1800054C7
0x1800053e8  mov     ecx, 8000FFFFh; this
0x1800053ed  mov     [rbx+8], ecx
0x1800053f0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800053f5  mov     [rbx+0Ch], eax
0x1800053f8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800053ff  jnz     short loc_180005420
0x180005401  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005408  test    rax, rax
0x18000540b  jz      short loc_180005416
0x18000540d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005412  test    al, al
0x180005414  jmp     short loc_18000541E
0x180005416  call    cs:__imp_IsDebuggerPresent
0x18000541c  test    eax, eax
0x18000541e  jz      short loc_180005426
0x180005420  test    byte ptr [rbx+4], 2
0x180005424  jz      short loc_18000544A
0x180005426  mov     rax, cs:g_pfnResultLoggingCallback
0x18000542d  test    rax, rax
0x180005430  jz      short loc_18000548E
0x180005432  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005439  jnz     short loc_18000548E
0x18000543b  xor     r8d, r8d
0x18000543e  xor     edx, edx
0x180005440  mov     rcx, rbx
0x180005443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005448  jmp     short loc_18000548E
0x18000544a  mov     ebp, 800h
0x18000544f  mov     rax, cs:g_pfnResultLoggingCallback
0x180005456  test    rax, rax
0x180005459  jz      short loc_180005472
0x18000545b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005462  jnz     short loc_180005472
0x180005464  mov     r8d, ebp
0x180005467  mov     rdx, rsi
0x18000546a  mov     rcx, rbx
0x18000546d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005472  cmp     [rsi], di
0x180005475  jnz     short loc_180005485
0x180005477  mov     r8, rbx; unsigned __int64
0x18000547a  mov     rdx, rbp; unsigned __int16 *
0x18000547d  mov     rcx, rsi; this
0x180005480  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005485  mov     rcx, rsi; lpOutputString
0x180005488  call    cs:__imp_OutputDebugStringW
0x18000548e  test    byte ptr [rbx+4], 4
0x180005492  jnz     short loc_18000549D
0x180005494  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000549b  jz      short loc_1800054AF
0x18000549d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800054a4  test    rax, rax
0x1800054a7  jz      short loc_1800054AF
0x1800054a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054ae  nop
0x1800054af  mov     rbx, [rsp+78h+arg_10]
0x1800054b7  add     rsp, 40h
0x1800054bb  pop     r15
0x1800054bd  pop     r14
0x1800054bf  pop     r13
0x1800054c1  pop     r12
0x1800054c3  pop     rdi
0x1800054c4  pop     rsi
0x1800054c5  pop     rbp
0x1800054c6  retn
0x1800054c7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
