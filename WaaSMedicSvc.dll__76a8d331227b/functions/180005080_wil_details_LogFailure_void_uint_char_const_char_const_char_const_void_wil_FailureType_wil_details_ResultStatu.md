# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005080`
- end: `0x180005379`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003828`

## callees

- `0x180003234`
- `0x180004714`
- `0x180004ebc`
- `0x180005080`
- `0x180005604`
- `0x180005620`
- `0x180005634`
- `0x180005650`
- `0x1800067cc`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051a3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005334`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005334`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800052c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800052c2`

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
0x180005080  mov     [rsp+arg_10], rbx
0x180005085  mov     [rsp+arg_8], edx
0x180005089  mov     [rsp+arg_0], rcx
0x18000508e  push    rbp
0x18000508f  push    rsi
0x180005090  push    rdi
0x180005091  push    r12
0x180005093  push    r13
0x180005095  push    r14
0x180005097  push    r15
0x180005099  sub     rsp, 40h
0x18000509d  mov     r12, r9
0x1800050a0  mov     r13, r8
0x1800050a3  mov     r10, rcx
0x1800050a6  xor     eax, eax
0x1800050a8  mov     rsi, [rsp+78h+lpOutputString]
0x1800050b0  mov     [rsi], ax
0x1800050b3  mov     rax, [rsp+78h+arg_60]
0x1800050bb  mov     byte ptr [rax], 0
0x1800050be  mov     r14, [rsp+78h+arg_38]
0x1800050c6  mov     edi, [r14]
0x1800050c9  mov     rbx, [rsp+78h+arg_78]
0x1800050d1  mov     [rbx+8], edi
0x1800050d4  mov     eax, [r14+4]
0x1800050d8  mov     [rbx+0Ch], eax
0x1800050db  xor     ebp, ebp
0x1800050dd  mov     r15d, [rsp+78h+arg_30]
0x1800050e5  mov     ecx, r15d
0x1800050e8  test    r15d, r15d
0x1800050eb  jz      short loc_180005153
0x1800050ed  sub     ecx, 1
0x1800050f0  jz      short loc_18000514A
0x1800050f2  sub     ecx, 1
0x1800050f5  jz      short loc_180005105
0x1800050f7  cmp     ecx, 1
0x1800050fa  jnz     short loc_18000515C
0x1800050fc  mov     ecx, edi; this
0x1800050fe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005103  jmp     short loc_18000515A
0x180005105  test    edi, edi
0x180005107  js      short loc_180005141
0x180005109  mov     edi, 8007029Ch
0x18000510e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005112  mov     rax, [rsp+78h+arg_28]
0x18000511a  mov     [rsp+78h+var_50], rax; __int64
0x18000511f  mov     rax, [rsp+78h+arg_20]
0x180005127  mov     [rsp+78h+var_58], rax; __int64
0x18000512c  mov     rcx, r10; int
0x18000512f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005134  mov     [rbx+8], edi
0x180005137  mov     ecx, edi; this
0x180005139  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000513e  mov     [rbx+0Ch], eax
0x180005141  mov     ecx, edi; this
0x180005143  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005148  jmp     short loc_18000515A
0x18000514a  mov     ecx, edi; this
0x18000514c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005151  jmp     short loc_18000515A
0x180005153  mov     ecx, edi; this
0x180005155  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000515a  mov     ebp, eax
0x18000515c  mov     [rbx], r15d
0x18000515f  mov     eax, [rsp+78h+arg_70]
0x180005166  mov     [rbx+4], eax
0x180005169  cmp     dword ptr [r14+8], 1
0x18000516e  jnz     short loc_180005176
0x180005170  or      eax, 8
0x180005173  mov     [rbx+4], eax
0x180005176  mov     eax, 1
0x18000517b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005183  inc     eax
0x180005185  mov     [rbx+10h], eax
0x180005188  mov     rax, [rsp+78h+arg_40]
0x180005190  xor     edi, edi
0x180005192  test    rax, rax
0x180005195  jz      short loc_18000519C
0x180005197  cmp     [rax], di
0x18000519a  jnz     short loc_18000519F
0x18000519c  mov     rax, rdi
0x18000519f  mov     [rbx+18h], rax
0x1800051a3  call    cs:__imp_GetCurrentThreadId
0x1800051a9  mov     [rbx+20h], eax
0x1800051ac  mov     [rbx+38h], r13
0x1800051b0  mov     eax, [rsp+78h+arg_8]
0x1800051b7  mov     [rbx+40h], eax
0x1800051ba  mov     [rbx+44h], ebp
0x1800051bd  mov     rax, [rsp+78h+arg_20]
0x1800051c5  mov     [rbx+28h], rax
0x1800051c9  mov     [rbx+30h], r12
0x1800051cd  mov     rax, [rsp+78h+arg_28]
0x1800051d5  mov     [rbx+88h], rax
0x1800051dc  mov     rax, [rsp+78h+arg_0]
0x1800051e4  mov     [rbx+90h], rax
0x1800051eb  mov     [rbx+48h], rdi
0x1800051ef  xorps   xmm0, xmm0
0x1800051f2  xor     eax, eax
0x1800051f4  movups  xmmword ptr [rbx+68h], xmm0
0x1800051f8  mov     [rbx+78h], rax
0x1800051fc  movups  xmmword ptr [rbx+50h], xmm0
0x180005200  mov     [rbx+60h], rax
0x180005204  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000520b  test    rax, rax
0x18000520e  jz      short loc_180005217
0x180005210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005215  jmp     short loc_18000521A
0x180005217  mov     rax, rdi
0x18000521a  mov     [rbx+80h], rax
0x180005221  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005228  test    rax, rax
0x18000522b  jz      short loc_180005235
0x18000522d  mov     rcx, rbx
0x180005230  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005235  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000523c  test    rax, rax
0x18000523f  jz      short loc_180005257
0x180005241  mov     r8d, 400h
0x180005247  mov     rdx, [rsp+78h+arg_60]
0x18000524f  mov     rcx, rbx
0x180005252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005257  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000525e  test    rax, rax
0x180005261  jz      short loc_18000526B
0x180005263  mov     rcx, rbx
0x180005266  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000526b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005272  test    rax, rax
0x180005275  jz      short loc_180005285
0x180005277  test    byte ptr [rbx+4], 2
0x18000527b  jnz     short loc_180005285
0x18000527d  mov     rcx, rbx
0x180005280  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005285  cmp     [rbx+8], edi
0x180005288  jl      short loc_1800052A4
0x18000528a  cmp     r15d, 3
0x18000528e  jnz     loc_180005373
0x180005294  mov     ecx, 8000FFFFh; this
0x180005299  mov     [rbx+8], ecx
0x18000529c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800052a1  mov     [rbx+0Ch], eax
0x1800052a4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800052ab  jnz     short loc_1800052CC
0x1800052ad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800052b4  test    rax, rax
0x1800052b7  jz      short loc_1800052C2
0x1800052b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052be  test    al, al
0x1800052c0  jmp     short loc_1800052CA
0x1800052c2  call    cs:__imp_IsDebuggerPresent
0x1800052c8  test    eax, eax
0x1800052ca  jz      short loc_1800052D2
0x1800052cc  test    byte ptr [rbx+4], 2
0x1800052d0  jz      short loc_1800052F6
0x1800052d2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800052d9  test    rax, rax
0x1800052dc  jz      short loc_18000533A
0x1800052de  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800052e5  jnz     short loc_18000533A
0x1800052e7  xor     r8d, r8d
0x1800052ea  xor     edx, edx
0x1800052ec  mov     rcx, rbx
0x1800052ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052f4  jmp     short loc_18000533A
0x1800052f6  mov     ebp, 800h
0x1800052fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180005302  test    rax, rax
0x180005305  jz      short loc_18000531E
0x180005307  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000530e  jnz     short loc_18000531E
0x180005310  mov     r8d, ebp
0x180005313  mov     rdx, rsi
0x180005316  mov     rcx, rbx
0x180005319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000531e  cmp     [rsi], di
0x180005321  jnz     short loc_180005331
0x180005323  mov     r8, rbx; unsigned __int64
0x180005326  mov     rdx, rbp; unsigned __int16 *
0x180005329  mov     rcx, rsi; this
0x18000532c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005331  mov     rcx, rsi; lpOutputString
0x180005334  call    cs:__imp_OutputDebugStringW
0x18000533a  test    byte ptr [rbx+4], 4
0x18000533e  jnz     short loc_180005349
0x180005340  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005347  jz      short loc_18000535B
0x180005349  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005350  test    rax, rax
0x180005353  jz      short loc_18000535B
0x180005355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000535a  nop
0x18000535b  mov     rbx, [rsp+78h+arg_10]
0x180005363  add     rsp, 40h
0x180005367  pop     r15
0x180005369  pop     r14
0x18000536b  pop     r13
0x18000536d  pop     r12
0x18000536f  pop     rdi
0x180005370  pop     rsi
0x180005371  pop     rbp
0x180005372  retn
0x180005373  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
