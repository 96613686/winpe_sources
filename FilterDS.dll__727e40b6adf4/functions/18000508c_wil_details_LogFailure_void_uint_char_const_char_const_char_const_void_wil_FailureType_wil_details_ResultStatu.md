# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000508c`
- end: `0x180005385`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003374`

## callees

- `0x180002d80`
- `0x180004694`
- `0x180004e90`
- `0x18000508c`
- `0x180005698`
- `0x1800056c0`
- `0x1800056d4`
- `0x1800056f0`
- `0x180006ba4`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800051af`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800052ce`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800052ce`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005340`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005340`

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
0x18000508c  mov     [rsp+arg_10], rbx
0x180005091  mov     [rsp+arg_8], edx
0x180005095  mov     [rsp+arg_0], rcx
0x18000509a  push    rbp
0x18000509b  push    rsi
0x18000509c  push    rdi
0x18000509d  push    r12
0x18000509f  push    r13
0x1800050a1  push    r14
0x1800050a3  push    r15
0x1800050a5  sub     rsp, 40h
0x1800050a9  mov     r12, r9
0x1800050ac  mov     r13, r8
0x1800050af  mov     r10, rcx
0x1800050b2  xor     eax, eax
0x1800050b4  mov     rsi, [rsp+78h+lpOutputString]
0x1800050bc  mov     [rsi], ax
0x1800050bf  mov     rax, [rsp+78h+arg_60]
0x1800050c7  mov     byte ptr [rax], 0
0x1800050ca  mov     r14, [rsp+78h+arg_38]
0x1800050d2  mov     edi, [r14]
0x1800050d5  mov     rbx, [rsp+78h+arg_78]
0x1800050dd  mov     [rbx+8], edi
0x1800050e0  mov     eax, [r14+4]
0x1800050e4  mov     [rbx+0Ch], eax
0x1800050e7  xor     ebp, ebp
0x1800050e9  mov     r15d, [rsp+78h+arg_30]
0x1800050f1  mov     ecx, r15d
0x1800050f4  test    r15d, r15d
0x1800050f7  jz      short loc_18000515F
0x1800050f9  sub     ecx, 1
0x1800050fc  jz      short loc_180005156
0x1800050fe  sub     ecx, 1
0x180005101  jz      short loc_180005111
0x180005103  cmp     ecx, 1
0x180005106  jnz     short loc_180005168
0x180005108  mov     ecx, edi; this
0x18000510a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000510f  jmp     short loc_180005166
0x180005111  test    edi, edi
0x180005113  js      short loc_18000514D
0x180005115  mov     edi, 8007029Ch
0x18000511a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000511e  mov     rax, [rsp+78h+arg_28]
0x180005126  mov     [rsp+78h+var_50], rax; __int64
0x18000512b  mov     rax, [rsp+78h+arg_20]
0x180005133  mov     [rsp+78h+var_58], rax; __int64
0x180005138  mov     rcx, r10; int
0x18000513b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005140  mov     [rbx+8], edi
0x180005143  mov     ecx, edi; this
0x180005145  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000514a  mov     [rbx+0Ch], eax
0x18000514d  mov     ecx, edi; this
0x18000514f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005154  jmp     short loc_180005166
0x180005156  mov     ecx, edi; this
0x180005158  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000515d  jmp     short loc_180005166
0x18000515f  mov     ecx, edi; this
0x180005161  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005166  mov     ebp, eax
0x180005168  mov     [rbx], r15d
0x18000516b  mov     eax, [rsp+78h+arg_70]
0x180005172  mov     [rbx+4], eax
0x180005175  cmp     dword ptr [r14+8], 1
0x18000517a  jnz     short loc_180005182
0x18000517c  or      eax, 8
0x18000517f  mov     [rbx+4], eax
0x180005182  mov     eax, 1
0x180005187  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000518f  inc     eax
0x180005191  mov     [rbx+10h], eax
0x180005194  mov     rax, [rsp+78h+arg_40]
0x18000519c  xor     edi, edi
0x18000519e  test    rax, rax
0x1800051a1  jz      short loc_1800051A8
0x1800051a3  cmp     [rax], di
0x1800051a6  jnz     short loc_1800051AB
0x1800051a8  mov     rax, rdi
0x1800051ab  mov     [rbx+18h], rax
0x1800051af  call    cs:__imp_GetCurrentThreadId
0x1800051b5  mov     [rbx+20h], eax
0x1800051b8  mov     [rbx+38h], r13
0x1800051bc  mov     eax, [rsp+78h+arg_8]
0x1800051c3  mov     [rbx+40h], eax
0x1800051c6  mov     [rbx+44h], ebp
0x1800051c9  mov     rax, [rsp+78h+arg_20]
0x1800051d1  mov     [rbx+28h], rax
0x1800051d5  mov     [rbx+30h], r12
0x1800051d9  mov     rax, [rsp+78h+arg_28]
0x1800051e1  mov     [rbx+88h], rax
0x1800051e8  mov     rax, [rsp+78h+arg_0]
0x1800051f0  mov     [rbx+90h], rax
0x1800051f7  mov     [rbx+48h], rdi
0x1800051fb  xorps   xmm0, xmm0
0x1800051fe  xor     eax, eax
0x180005200  movups  xmmword ptr [rbx+68h], xmm0
0x180005204  mov     [rbx+78h], rax
0x180005208  movups  xmmword ptr [rbx+50h], xmm0
0x18000520c  mov     [rbx+60h], rax
0x180005210  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005217  test    rax, rax
0x18000521a  jz      short loc_180005223
0x18000521c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005221  jmp     short loc_180005226
0x180005223  mov     rax, rdi
0x180005226  mov     [rbx+80h], rax
0x18000522d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005234  test    rax, rax
0x180005237  jz      short loc_180005241
0x180005239  mov     rcx, rbx
0x18000523c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005241  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005248  test    rax, rax
0x18000524b  jz      short loc_180005263
0x18000524d  mov     r8d, 400h
0x180005253  mov     rdx, [rsp+78h+arg_60]
0x18000525b  mov     rcx, rbx
0x18000525e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005263  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000526a  test    rax, rax
0x18000526d  jz      short loc_180005277
0x18000526f  mov     rcx, rbx
0x180005272  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005277  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000527e  test    rax, rax
0x180005281  jz      short loc_180005291
0x180005283  test    byte ptr [rbx+4], 2
0x180005287  jnz     short loc_180005291
0x180005289  mov     rcx, rbx
0x18000528c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005291  cmp     [rbx+8], edi
0x180005294  jl      short loc_1800052B0
0x180005296  cmp     r15d, 3
0x18000529a  jnz     loc_18000537F
0x1800052a0  mov     ecx, 8000FFFFh; this
0x1800052a5  mov     [rbx+8], ecx
0x1800052a8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800052ad  mov     [rbx+0Ch], eax
0x1800052b0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800052b7  jnz     short loc_1800052D8
0x1800052b9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800052c0  test    rax, rax
0x1800052c3  jz      short loc_1800052CE
0x1800052c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052ca  test    al, al
0x1800052cc  jmp     short loc_1800052D6
0x1800052ce  call    cs:__imp_IsDebuggerPresent
0x1800052d4  test    eax, eax
0x1800052d6  jz      short loc_1800052DE
0x1800052d8  test    byte ptr [rbx+4], 2
0x1800052dc  jz      short loc_180005302
0x1800052de  mov     rax, cs:g_pfnResultLoggingCallback
0x1800052e5  test    rax, rax
0x1800052e8  jz      short loc_180005346
0x1800052ea  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800052f1  jnz     short loc_180005346
0x1800052f3  xor     r8d, r8d
0x1800052f6  xor     edx, edx
0x1800052f8  mov     rcx, rbx
0x1800052fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005300  jmp     short loc_180005346
0x180005302  mov     ebp, 800h
0x180005307  mov     rax, cs:g_pfnResultLoggingCallback
0x18000530e  test    rax, rax
0x180005311  jz      short loc_18000532A
0x180005313  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000531a  jnz     short loc_18000532A
0x18000531c  mov     r8d, ebp
0x18000531f  mov     rdx, rsi
0x180005322  mov     rcx, rbx
0x180005325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000532a  cmp     [rsi], di
0x18000532d  jnz     short loc_18000533D
0x18000532f  mov     r8, rbx; unsigned __int64
0x180005332  mov     rdx, rbp; unsigned __int16 *
0x180005335  mov     rcx, rsi; this
0x180005338  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000533d  mov     rcx, rsi; lpOutputString
0x180005340  call    cs:__imp_OutputDebugStringW
0x180005346  test    byte ptr [rbx+4], 4
0x18000534a  jnz     short loc_180005355
0x18000534c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005353  jz      short loc_180005367
0x180005355  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000535c  test    rax, rax
0x18000535f  jz      short loc_180005367
0x180005361  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005366  nop
0x180005367  mov     rbx, [rsp+78h+arg_10]
0x18000536f  add     rsp, 40h
0x180005373  pop     r15
0x180005375  pop     r14
0x180005377  pop     r13
0x180005379  pop     r12
0x18000537b  pop     rdi
0x18000537c  pop     rsi
0x18000537d  pop     rbp
0x18000537e  retn
0x18000537f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
