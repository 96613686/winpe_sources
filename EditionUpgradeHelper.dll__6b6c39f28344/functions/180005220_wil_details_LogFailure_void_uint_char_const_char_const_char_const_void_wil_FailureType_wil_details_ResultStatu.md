# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005220`
- end: `0x180005518`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002e74`

## callees

- `0x1800028b0`
- `0x1800048c4`
- `0x18000505c`
- `0x180005220`
- `0x180005c28`
- `0x180005c50`
- `0x180005d78`
- `0x180005d94`
- `0x180007b2c`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005343`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005343`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005462`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005462`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800054d4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800054d4`

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
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x180005220  mov     [rsp+arg_10], rbx
0x180005225  mov     [rsp+arg_8], edx
0x180005229  mov     [rsp+arg_0], rcx
0x18000522e  push    rbp
0x18000522f  push    rsi
0x180005230  push    rdi
0x180005231  push    r12
0x180005233  push    r13
0x180005235  push    r14
0x180005237  push    r15
0x180005239  sub     rsp, 40h
0x18000523d  mov     r14, [rsp+78h+arg_38]
0x180005245  xor     eax, eax
0x180005247  mov     rbx, [rsp+78h+arg_78]
0x18000524f  xor     ebp, ebp
0x180005251  mov     r15d, [rsp+78h+arg_30]
0x180005259  mov     r10, rcx
0x18000525c  mov     rsi, [rsp+78h+lpOutputString]
0x180005264  mov     r12, r9
0x180005267  mov     r13, r8
0x18000526a  mov     ecx, r15d
0x18000526d  mov     [rsi], ax
0x180005270  mov     rax, [rsp+78h+arg_60]
0x180005278  mov     byte ptr [rax], 0
0x18000527b  mov     edi, [r14]
0x18000527e  mov     [rbx+8], edi
0x180005281  mov     eax, [r14+4]
0x180005285  mov     [rbx+0Ch], eax
0x180005288  test    r15d, r15d
0x18000528b  jz      short loc_1800052F3
0x18000528d  sub     ecx, 1
0x180005290  jz      short loc_1800052EA
0x180005292  sub     ecx, 1
0x180005295  jz      short loc_1800052A5
0x180005297  cmp     ecx, 1
0x18000529a  jnz     short loc_1800052FC
0x18000529c  mov     ecx, edi; this
0x18000529e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800052a3  jmp     short loc_1800052FA
0x1800052a5  test    edi, edi
0x1800052a7  js      short loc_1800052E1
0x1800052a9  mov     rax, [rsp+78h+arg_28]
0x1800052b1  mov     edi, 8007029Ch
0x1800052b6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800052ba  mov     rcx, r10; int
0x1800052bd  mov     [rsp+78h+var_50], rax; __int64
0x1800052c2  mov     rax, [rsp+78h+arg_20]
0x1800052ca  mov     [rsp+78h+var_58], rax; __int64
0x1800052cf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800052d4  mov     ecx, edi; this
0x1800052d6  mov     [rbx+8], edi
0x1800052d9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800052de  mov     [rbx+0Ch], eax
0x1800052e1  mov     ecx, edi; this
0x1800052e3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800052e8  jmp     short loc_1800052FA
0x1800052ea  mov     ecx, edi; this
0x1800052ec  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800052f1  jmp     short loc_1800052FA
0x1800052f3  mov     ecx, edi; this
0x1800052f5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800052fa  mov     ebp, eax
0x1800052fc  mov     eax, [rsp+78h+arg_70]
0x180005303  mov     [rbx+4], eax
0x180005306  mov     [rbx], r15d
0x180005309  cmp     dword ptr [r14+8], 1
0x18000530e  jnz     short loc_180005316
0x180005310  or      eax, 8
0x180005313  mov     [rbx+4], eax
0x180005316  mov     eax, 1
0x18000531b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005323  inc     eax
0x180005325  xor     edi, edi
0x180005327  mov     [rbx+10h], eax
0x18000532a  mov     rax, [rsp+78h+arg_40]
0x180005332  test    rax, rax
0x180005335  jz      short loc_18000533C
0x180005337  cmp     [rax], di
0x18000533a  jnz     short loc_18000533F
0x18000533c  mov     rax, rdi
0x18000533f  mov     [rbx+18h], rax
0x180005343  call    cs:__imp_GetCurrentThreadId
0x180005349  mov     [rbx+38h], r13
0x18000534d  xorps   xmm0, xmm0
0x180005350  mov     [rbx+20h], eax
0x180005353  mov     eax, [rsp+78h+arg_8]
0x18000535a  mov     [rbx+40h], eax
0x18000535d  mov     rax, [rsp+78h+arg_20]
0x180005365  mov     [rbx+28h], rax
0x180005369  mov     rax, [rsp+78h+arg_28]
0x180005371  mov     [rbx+88h], rax
0x180005378  mov     rax, [rsp+78h+arg_0]
0x180005380  mov     [rbx+90h], rax
0x180005387  xor     eax, eax
0x180005389  mov     [rbx+44h], ebp
0x18000538c  mov     [rbx+30h], r12
0x180005390  mov     [rbx+48h], rdi
0x180005394  movups  xmmword ptr [rbx+68h], xmm0
0x180005398  mov     [rbx+78h], rax
0x18000539c  movups  xmmword ptr [rbx+50h], xmm0
0x1800053a0  mov     [rbx+60h], rax
0x1800053a4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800053ab  test    rax, rax
0x1800053ae  jz      short loc_1800053B7
0x1800053b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053b5  jmp     short loc_1800053BA
0x1800053b7  mov     rax, rdi
0x1800053ba  mov     [rbx+80h], rax
0x1800053c1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800053c8  test    rax, rax
0x1800053cb  jz      short loc_1800053D5
0x1800053cd  mov     rcx, rbx
0x1800053d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053d5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800053dc  test    rax, rax
0x1800053df  jz      short loc_1800053F7
0x1800053e1  mov     rdx, [rsp+78h+arg_60]
0x1800053e9  mov     r8d, 400h
0x1800053ef  mov     rcx, rbx
0x1800053f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800053f7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800053fe  test    rax, rax
0x180005401  jz      short loc_18000540B
0x180005403  mov     rcx, rbx
0x180005406  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000540b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005412  test    rax, rax
0x180005415  jz      short loc_180005425
0x180005417  test    byte ptr [rbx+4], 2
0x18000541b  jnz     short loc_180005425
0x18000541d  mov     rcx, rbx
0x180005420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005425  cmp     [rbx+8], edi
0x180005428  jl      short loc_180005444
0x18000542a  cmp     r15d, 3
0x18000542e  jnz     loc_180005512
0x180005434  mov     ecx, 8000FFFFh; this
0x180005439  mov     [rbx+8], ecx
0x18000543c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005441  mov     [rbx+0Ch], eax
0x180005444  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000544b  jnz     short loc_18000546C
0x18000544d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005454  test    rax, rax
0x180005457  jz      short loc_180005462
0x180005459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000545e  test    al, al
0x180005460  jmp     short loc_18000546A
0x180005462  call    cs:__imp_IsDebuggerPresent
0x180005468  test    eax, eax
0x18000546a  jz      short loc_180005472
0x18000546c  test    byte ptr [rbx+4], 2
0x180005470  jz      short loc_180005496
0x180005472  mov     rax, cs:g_pfnResultLoggingCallback
0x180005479  test    rax, rax
0x18000547c  jz      short loc_1800054DA
0x18000547e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005485  jnz     short loc_1800054DA
0x180005487  xor     r8d, r8d
0x18000548a  xor     edx, edx
0x18000548c  mov     rcx, rbx
0x18000548f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005494  jmp     short loc_1800054DA
0x180005496  mov     rax, cs:g_pfnResultLoggingCallback
0x18000549d  mov     ebp, 800h
0x1800054a2  test    rax, rax
0x1800054a5  jz      short loc_1800054BE
0x1800054a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800054ae  jnz     short loc_1800054BE
0x1800054b0  mov     r8d, ebp
0x1800054b3  mov     rdx, rsi
0x1800054b6  mov     rcx, rbx
0x1800054b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054be  cmp     [rsi], di
0x1800054c1  jnz     short loc_1800054D1
0x1800054c3  mov     r8, rbx; unsigned __int64
0x1800054c6  mov     rdx, rbp; unsigned __int16 *
0x1800054c9  mov     rcx, rsi; this
0x1800054cc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800054d1  mov     rcx, rsi; lpOutputString
0x1800054d4  call    cs:__imp_OutputDebugStringW
0x1800054da  test    byte ptr [rbx+4], 4
0x1800054de  jnz     short loc_1800054E9
0x1800054e0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800054e7  jz      short loc_1800054FA
0x1800054e9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800054f0  test    rax, rax
0x1800054f3  jz      short loc_1800054FA
0x1800054f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054fa  mov     rbx, [rsp+78h+arg_10]
0x180005502  add     rsp, 40h
0x180005506  pop     r15
0x180005508  pop     r14
0x18000550a  pop     r13
0x18000550c  pop     r12
0x18000550e  pop     rdi
0x18000550f  pop     rsi
0x180005510  pop     rbp
0x180005511  retn
0x180005512  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
