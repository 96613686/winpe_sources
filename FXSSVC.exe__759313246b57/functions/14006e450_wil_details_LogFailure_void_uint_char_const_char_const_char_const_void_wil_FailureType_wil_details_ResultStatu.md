# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14006e450`
- end: `0x14006e75c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14006ba30`

## callees

- `0x14006b444`
- `0x14006d754`
- `0x14006df60`
- `0x14006e450`
- `0x14006ee78`
- `0x14006eea0`
- `0x14006efe8`
- `0x14006f008`
- `0x1400714a0`
- `0x14008b010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14006e698`
- `KERNEL32!IsDebuggerPresent` at `0x14006e698`
- `KERNEL32!OutputDebugStringW` at `0x14006e710`
- `KERNEL32!OutputDebugStringW` at `0x14006e710`
- `KERNEL32!GetCurrentThreadId` at `0x14006e573`
- `KERNEL32!GetCurrentThreadId` at `0x14006e573`

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
0x14006e450  mov     [rsp+arg_10], rbx
0x14006e455  mov     [rsp+arg_8], edx
0x14006e459  mov     [rsp+arg_0], rcx
0x14006e45e  push    rbp
0x14006e45f  push    rsi
0x14006e460  push    rdi
0x14006e461  push    r12
0x14006e463  push    r13
0x14006e465  push    r14
0x14006e467  push    r15
0x14006e469  sub     rsp, 40h
0x14006e46d  mov     r12, r9
0x14006e470  mov     r13, r8
0x14006e473  mov     r10, rcx
0x14006e476  xor     eax, eax
0x14006e478  mov     rsi, [rsp+78h+lpOutputString]
0x14006e480  mov     [rsi], ax
0x14006e483  mov     rax, [rsp+78h+arg_60]
0x14006e48b  mov     byte ptr [rax], 0
0x14006e48e  mov     r14, [rsp+78h+arg_38]
0x14006e496  mov     edi, [r14]
0x14006e499  mov     rbx, [rsp+78h+arg_78]
0x14006e4a1  mov     [rbx+8], edi
0x14006e4a4  mov     eax, [r14+4]
0x14006e4a8  mov     [rbx+0Ch], eax
0x14006e4ab  xor     ebp, ebp
0x14006e4ad  mov     r15d, [rsp+78h+arg_30]
0x14006e4b5  mov     ecx, r15d
0x14006e4b8  test    r15d, r15d
0x14006e4bb  jz      short loc_14006E523
0x14006e4bd  sub     ecx, 1
0x14006e4c0  jz      short loc_14006E51A
0x14006e4c2  sub     ecx, 1
0x14006e4c5  jz      short loc_14006E4D5
0x14006e4c7  cmp     ecx, 1
0x14006e4ca  jnz     short loc_14006E52C
0x14006e4cc  mov     ecx, edi; this
0x14006e4ce  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14006e4d3  jmp     short loc_14006E52A
0x14006e4d5  test    edi, edi
0x14006e4d7  js      short loc_14006E511
0x14006e4d9  mov     edi, 8007029Ch
0x14006e4de  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14006e4e2  mov     rax, [rsp+78h+arg_28]
0x14006e4ea  mov     [rsp+78h+var_50], rax; __int64
0x14006e4ef  mov     rax, [rsp+78h+arg_20]
0x14006e4f7  mov     [rsp+78h+var_58], rax; __int64
0x14006e4fc  mov     rcx, r10; int
0x14006e4ff  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14006e504  mov     [rbx+8], edi
0x14006e507  mov     ecx, edi; this
0x14006e509  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14006e50e  mov     [rbx+0Ch], eax
0x14006e511  mov     ecx, edi; this
0x14006e513  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14006e518  jmp     short loc_14006E52A
0x14006e51a  mov     ecx, edi; this
0x14006e51c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14006e521  jmp     short loc_14006E52A
0x14006e523  mov     ecx, edi; this
0x14006e525  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14006e52a  mov     ebp, eax
0x14006e52c  mov     [rbx], r15d
0x14006e52f  mov     eax, [rsp+78h+arg_70]
0x14006e536  mov     [rbx+4], eax
0x14006e539  cmp     dword ptr [r14+8], 1
0x14006e53e  jnz     short loc_14006E546
0x14006e540  or      eax, 8
0x14006e543  mov     [rbx+4], eax
0x14006e546  mov     eax, 1
0x14006e54b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14006e553  inc     eax
0x14006e555  mov     [rbx+10h], eax
0x14006e558  mov     rax, [rsp+78h+arg_40]
0x14006e560  xor     edi, edi
0x14006e562  test    rax, rax
0x14006e565  jz      short loc_14006E56C
0x14006e567  cmp     [rax], di
0x14006e56a  jnz     short loc_14006E56F
0x14006e56c  mov     rax, rdi
0x14006e56f  mov     [rbx+18h], rax
0x14006e573  call    cs:__imp_GetCurrentThreadId
0x14006e57a  nop     dword ptr [rax+rax+00h]
0x14006e57f  mov     [rbx+20h], eax
0x14006e582  mov     [rbx+38h], r13
0x14006e586  mov     eax, [rsp+78h+arg_8]
0x14006e58d  mov     [rbx+40h], eax
0x14006e590  mov     [rbx+44h], ebp
0x14006e593  mov     rax, [rsp+78h+arg_20]
0x14006e59b  mov     [rbx+28h], rax
0x14006e59f  mov     [rbx+30h], r12
0x14006e5a3  mov     rax, [rsp+78h+arg_28]
0x14006e5ab  mov     [rbx+88h], rax
0x14006e5b2  mov     rax, [rsp+78h+arg_0]
0x14006e5ba  mov     [rbx+90h], rax
0x14006e5c1  mov     [rbx+48h], rdi
0x14006e5c5  xorps   xmm0, xmm0
0x14006e5c8  xor     eax, eax
0x14006e5ca  movups  xmmword ptr [rbx+68h], xmm0
0x14006e5ce  mov     [rbx+78h], rax
0x14006e5d2  movups  xmmword ptr [rbx+50h], xmm0
0x14006e5d6  mov     [rbx+60h], rax
0x14006e5da  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14006e5e1  test    rax, rax
0x14006e5e4  jz      short loc_14006E5ED
0x14006e5e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e5eb  jmp     short loc_14006E5F0
0x14006e5ed  mov     rax, rdi
0x14006e5f0  mov     [rbx+80h], rax
0x14006e5f7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14006e5fe  test    rax, rax
0x14006e601  jz      short loc_14006E60B
0x14006e603  mov     rcx, rbx
0x14006e606  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e60b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14006e612  test    rax, rax
0x14006e615  jz      short loc_14006E62D
0x14006e617  mov     r8d, 400h
0x14006e61d  mov     rdx, [rsp+78h+arg_60]
0x14006e625  mov     rcx, rbx
0x14006e628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e62d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14006e634  test    rax, rax
0x14006e637  jz      short loc_14006E641
0x14006e639  mov     rcx, rbx
0x14006e63c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e641  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14006e648  test    rax, rax
0x14006e64b  jz      short loc_14006E65B
0x14006e64d  test    byte ptr [rbx+4], 2
0x14006e651  jnz     short loc_14006E65B
0x14006e653  mov     rcx, rbx
0x14006e656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e65b  cmp     [rbx+8], edi
0x14006e65e  jl      short loc_14006E67A
0x14006e660  cmp     r15d, 3
0x14006e664  jnz     loc_14006E756
0x14006e66a  mov     ecx, 8000FFFFh; this
0x14006e66f  mov     [rbx+8], ecx
0x14006e672  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14006e677  mov     [rbx+0Ch], eax
0x14006e67a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14006e681  jnz     short loc_14006E6A8
0x14006e683  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14006e68a  test    rax, rax
0x14006e68d  jz      short loc_14006E698
0x14006e68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e694  test    al, al
0x14006e696  jmp     short loc_14006E6A6
0x14006e698  call    cs:__imp_IsDebuggerPresent
0x14006e69f  nop     dword ptr [rax+rax+00h]
0x14006e6a4  test    eax, eax
0x14006e6a6  jz      short loc_14006E6AE
0x14006e6a8  test    byte ptr [rbx+4], 2
0x14006e6ac  jz      short loc_14006E6D2
0x14006e6ae  mov     rax, cs:g_pfnResultLoggingCallback
0x14006e6b5  test    rax, rax
0x14006e6b8  jz      short loc_14006E71C
0x14006e6ba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14006e6c1  jnz     short loc_14006E71C
0x14006e6c3  xor     r8d, r8d
0x14006e6c6  xor     edx, edx
0x14006e6c8  mov     rcx, rbx
0x14006e6cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e6d0  jmp     short loc_14006E71C
0x14006e6d2  mov     ebp, 800h
0x14006e6d7  mov     rax, cs:g_pfnResultLoggingCallback
0x14006e6de  test    rax, rax
0x14006e6e1  jz      short loc_14006E6FA
0x14006e6e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14006e6ea  jnz     short loc_14006E6FA
0x14006e6ec  mov     r8d, ebp
0x14006e6ef  mov     rdx, rsi
0x14006e6f2  mov     rcx, rbx
0x14006e6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e6fa  cmp     [rsi], di
0x14006e6fd  jnz     short loc_14006E70D
0x14006e6ff  mov     r8, rbx; unsigned __int64
0x14006e702  mov     rdx, rbp; unsigned __int16 *
0x14006e705  mov     rcx, rsi; this
0x14006e708  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14006e70d  mov     rcx, rsi; lpOutputString
0x14006e710  call    cs:__imp_OutputDebugStringW
0x14006e717  nop     dword ptr [rax+rax+00h]
0x14006e71c  test    byte ptr [rbx+4], 4
0x14006e720  jnz     short loc_14006E72B
0x14006e722  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14006e729  jz      short loc_14006E73D
0x14006e72b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14006e732  test    rax, rax
0x14006e735  jz      short loc_14006E73D
0x14006e737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006e73c  nop
0x14006e73d  mov     rbx, [rsp+78h+arg_10]
0x14006e745  add     rsp, 40h
0x14006e749  pop     r15
0x14006e74b  pop     r14
0x14006e74d  pop     r13
0x14006e74f  pop     r12
0x14006e751  pop     rdi
0x14006e752  pop     rsi
0x14006e753  pop     rbp
0x14006e754  retn
0x14006e756  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
