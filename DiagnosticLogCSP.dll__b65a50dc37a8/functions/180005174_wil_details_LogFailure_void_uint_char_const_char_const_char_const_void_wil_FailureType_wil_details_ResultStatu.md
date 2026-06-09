# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005174`
- end: `0x180005480`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003bd4`

## callees

- `0x1800035f0`
- `0x1800047a4`
- `0x180004fb0`
- `0x180005174`
- `0x180005954`
- `0x180005980`
- `0x180005994`
- `0x1800059b4`
- `0x180006978`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005297`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005297`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005434`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005434`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800053bc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800053bc`

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x180005174  mov     [rsp+arg_10], rbx
0x180005179  mov     [rsp+arg_8], edx
0x18000517d  mov     [rsp+arg_0], rcx
0x180005182  push    rbp
0x180005183  push    rsi
0x180005184  push    rdi
0x180005185  push    r12
0x180005187  push    r13
0x180005189  push    r14
0x18000518b  push    r15
0x18000518d  sub     rsp, 40h
0x180005191  mov     r12, r9
0x180005194  mov     r13, r8
0x180005197  mov     r10, rcx
0x18000519a  xor     eax, eax
0x18000519c  mov     rsi, [rsp+78h+lpOutputString]
0x1800051a4  mov     [rsi], ax
0x1800051a7  mov     rax, [rsp+78h+arg_60]
0x1800051af  mov     byte ptr [rax], 0
0x1800051b2  mov     r14, [rsp+78h+arg_38]
0x1800051ba  mov     edi, [r14]
0x1800051bd  mov     rbx, [rsp+78h+arg_78]
0x1800051c5  mov     [rbx+8], edi
0x1800051c8  mov     eax, [r14+4]
0x1800051cc  mov     [rbx+0Ch], eax
0x1800051cf  xor     ebp, ebp
0x1800051d1  mov     r15d, [rsp+78h+arg_30]
0x1800051d9  mov     ecx, r15d
0x1800051dc  test    r15d, r15d
0x1800051df  jz      short loc_180005247
0x1800051e1  sub     ecx, 1
0x1800051e4  jz      short loc_18000523E
0x1800051e6  sub     ecx, 1
0x1800051e9  jz      short loc_1800051F9
0x1800051eb  cmp     ecx, 1
0x1800051ee  jnz     short loc_180005250
0x1800051f0  mov     ecx, edi; this
0x1800051f2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800051f7  jmp     short loc_18000524E
0x1800051f9  test    edi, edi
0x1800051fb  js      short loc_180005235
0x1800051fd  mov     edi, 8007029Ch
0x180005202  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005206  mov     rax, [rsp+78h+arg_28]
0x18000520e  mov     [rsp+78h+var_50], rax; __int64
0x180005213  mov     rax, [rsp+78h+arg_20]
0x18000521b  mov     [rsp+78h+var_58], rax; __int64
0x180005220  mov     rcx, r10; int
0x180005223  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005228  mov     [rbx+8], edi
0x18000522b  mov     ecx, edi; this
0x18000522d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005232  mov     [rbx+0Ch], eax
0x180005235  mov     ecx, edi; this
0x180005237  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000523c  jmp     short loc_18000524E
0x18000523e  mov     ecx, edi; this
0x180005240  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005245  jmp     short loc_18000524E
0x180005247  mov     ecx, edi; this
0x180005249  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000524e  mov     ebp, eax
0x180005250  mov     [rbx], r15d
0x180005253  mov     eax, [rsp+78h+arg_70]
0x18000525a  mov     [rbx+4], eax
0x18000525d  cmp     dword ptr [r14+8], 1
0x180005262  jnz     short loc_18000526A
0x180005264  or      eax, 8
0x180005267  mov     [rbx+4], eax
0x18000526a  mov     eax, 1
0x18000526f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005277  inc     eax
0x180005279  mov     [rbx+10h], eax
0x18000527c  mov     rax, [rsp+78h+arg_40]
0x180005284  xor     edi, edi
0x180005286  test    rax, rax
0x180005289  jz      short loc_180005290
0x18000528b  cmp     [rax], di
0x18000528e  jnz     short loc_180005293
0x180005290  mov     rax, rdi
0x180005293  mov     [rbx+18h], rax
0x180005297  call    cs:__imp_GetCurrentThreadId
0x18000529e  nop     dword ptr [rax+rax+00h]
0x1800052a3  mov     [rbx+20h], eax
0x1800052a6  mov     [rbx+38h], r13
0x1800052aa  mov     eax, [rsp+78h+arg_8]
0x1800052b1  mov     [rbx+40h], eax
0x1800052b4  mov     [rbx+44h], ebp
0x1800052b7  mov     rax, [rsp+78h+arg_20]
0x1800052bf  mov     [rbx+28h], rax
0x1800052c3  mov     [rbx+30h], r12
0x1800052c7  mov     rax, [rsp+78h+arg_28]
0x1800052cf  mov     [rbx+88h], rax
0x1800052d6  mov     rax, [rsp+78h+arg_0]
0x1800052de  mov     [rbx+90h], rax
0x1800052e5  mov     [rbx+48h], rdi
0x1800052e9  xorps   xmm0, xmm0
0x1800052ec  xor     eax, eax
0x1800052ee  movups  xmmword ptr [rbx+68h], xmm0
0x1800052f2  mov     [rbx+78h], rax
0x1800052f6  movups  xmmword ptr [rbx+50h], xmm0
0x1800052fa  mov     [rbx+60h], rax
0x1800052fe  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005305  test    rax, rax
0x180005308  jz      short loc_180005311
0x18000530a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000530f  jmp     short loc_180005314
0x180005311  mov     rax, rdi
0x180005314  mov     [rbx+80h], rax
0x18000531b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005322  test    rax, rax
0x180005325  jz      short loc_18000532F
0x180005327  mov     rcx, rbx
0x18000532a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000532f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005336  test    rax, rax
0x180005339  jz      short loc_180005351
0x18000533b  mov     r8d, 400h
0x180005341  mov     rdx, [rsp+78h+arg_60]
0x180005349  mov     rcx, rbx
0x18000534c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005351  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005358  test    rax, rax
0x18000535b  jz      short loc_180005365
0x18000535d  mov     rcx, rbx
0x180005360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005365  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000536c  test    rax, rax
0x18000536f  jz      short loc_18000537F
0x180005371  test    byte ptr [rbx+4], 2
0x180005375  jnz     short loc_18000537F
0x180005377  mov     rcx, rbx
0x18000537a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000537f  cmp     [rbx+8], edi
0x180005382  jl      short loc_18000539E
0x180005384  cmp     r15d, 3
0x180005388  jnz     loc_18000547A
0x18000538e  mov     ecx, 8000FFFFh; this
0x180005393  mov     [rbx+8], ecx
0x180005396  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000539b  mov     [rbx+0Ch], eax
0x18000539e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800053a5  jnz     short loc_1800053CC
0x1800053a7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800053ae  test    rax, rax
0x1800053b1  jz      short loc_1800053BC
0x1800053b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053b8  test    al, al
0x1800053ba  jmp     short loc_1800053CA
0x1800053bc  call    cs:__imp_IsDebuggerPresent
0x1800053c3  nop     dword ptr [rax+rax+00h]
0x1800053c8  test    eax, eax
0x1800053ca  jz      short loc_1800053D2
0x1800053cc  test    byte ptr [rbx+4], 2
0x1800053d0  jz      short loc_1800053F6
0x1800053d2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800053d9  test    rax, rax
0x1800053dc  jz      short loc_180005440
0x1800053de  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800053e5  jnz     short loc_180005440
0x1800053e7  xor     r8d, r8d
0x1800053ea  xor     edx, edx
0x1800053ec  mov     rcx, rbx
0x1800053ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053f4  jmp     short loc_180005440
0x1800053f6  mov     ebp, 800h
0x1800053fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180005402  test    rax, rax
0x180005405  jz      short loc_18000541E
0x180005407  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000540e  jnz     short loc_18000541E
0x180005410  mov     r8d, ebp
0x180005413  mov     rdx, rsi
0x180005416  mov     rcx, rbx
0x180005419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000541e  cmp     [rsi], di
0x180005421  jnz     short loc_180005431
0x180005423  mov     r8, rbx; unsigned __int64
0x180005426  mov     rdx, rbp; unsigned __int16 *
0x180005429  mov     rcx, rsi; this
0x18000542c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005431  mov     rcx, rsi; lpOutputString
0x180005434  call    cs:__imp_OutputDebugStringW
0x18000543b  nop     dword ptr [rax+rax+00h]
0x180005440  test    byte ptr [rbx+4], 4
0x180005444  jnz     short loc_18000544F
0x180005446  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000544d  jz      short loc_180005461
0x18000544f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005456  test    rax, rax
0x180005459  jz      short loc_180005461
0x18000545b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005460  nop
0x180005461  mov     rbx, [rsp+78h+arg_10]
0x180005469  add     rsp, 40h
0x18000546d  pop     r15
0x18000546f  pop     r14
0x180005471  pop     r13
0x180005473  pop     r12
0x180005475  pop     rdi
0x180005476  pop     rsi
0x180005477  pop     rbp
0x180005478  retn
0x18000547a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
