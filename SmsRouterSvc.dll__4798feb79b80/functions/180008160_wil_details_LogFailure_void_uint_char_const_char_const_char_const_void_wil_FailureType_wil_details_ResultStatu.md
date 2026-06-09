# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008160`
- end: `0x180008459`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000639c`

## callees

- `0x180005de0`
- `0x1800077f4`
- `0x180007f9c`
- `0x180008160`
- `0x1800086e4`
- `0x180008700`
- `0x180008714`
- `0x180008730`
- `0x18000986c`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008283`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008283`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008414`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008414`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800083a2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800083a2`

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
0x180008160  mov     [rsp+arg_10], rbx
0x180008165  mov     [rsp+arg_8], edx
0x180008169  mov     [rsp+arg_0], rcx
0x18000816e  push    rbp
0x18000816f  push    rsi
0x180008170  push    rdi
0x180008171  push    r12
0x180008173  push    r13
0x180008175  push    r14
0x180008177  push    r15
0x180008179  sub     rsp, 40h
0x18000817d  mov     r12, r9
0x180008180  mov     r13, r8
0x180008183  mov     r10, rcx
0x180008186  xor     eax, eax
0x180008188  mov     rsi, [rsp+78h+lpOutputString]
0x180008190  mov     [rsi], ax
0x180008193  mov     rax, [rsp+78h+arg_60]
0x18000819b  mov     byte ptr [rax], 0
0x18000819e  mov     r14, [rsp+78h+arg_38]
0x1800081a6  mov     edi, [r14]
0x1800081a9  mov     rbx, [rsp+78h+arg_78]
0x1800081b1  mov     [rbx+8], edi
0x1800081b4  mov     eax, [r14+4]
0x1800081b8  mov     [rbx+0Ch], eax
0x1800081bb  xor     ebp, ebp
0x1800081bd  mov     r15d, [rsp+78h+arg_30]
0x1800081c5  mov     ecx, r15d
0x1800081c8  test    r15d, r15d
0x1800081cb  jz      short loc_180008233
0x1800081cd  sub     ecx, 1
0x1800081d0  jz      short loc_18000822A
0x1800081d2  sub     ecx, 1
0x1800081d5  jz      short loc_1800081E5
0x1800081d7  cmp     ecx, 1
0x1800081da  jnz     short loc_18000823C
0x1800081dc  mov     ecx, edi; this
0x1800081de  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800081e3  jmp     short loc_18000823A
0x1800081e5  test    edi, edi
0x1800081e7  js      short loc_180008221
0x1800081e9  mov     edi, 8007029Ch
0x1800081ee  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800081f2  mov     rax, [rsp+78h+arg_28]
0x1800081fa  mov     [rsp+78h+var_50], rax; __int64
0x1800081ff  mov     rax, [rsp+78h+arg_20]
0x180008207  mov     [rsp+78h+var_58], rax; __int64
0x18000820c  mov     rcx, r10; int
0x18000820f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008214  mov     [rbx+8], edi
0x180008217  mov     ecx, edi; this
0x180008219  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000821e  mov     [rbx+0Ch], eax
0x180008221  mov     ecx, edi; this
0x180008223  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008228  jmp     short loc_18000823A
0x18000822a  mov     ecx, edi; this
0x18000822c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008231  jmp     short loc_18000823A
0x180008233  mov     ecx, edi; this
0x180008235  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000823a  mov     ebp, eax
0x18000823c  mov     [rbx], r15d
0x18000823f  mov     eax, [rsp+78h+arg_70]
0x180008246  mov     [rbx+4], eax
0x180008249  cmp     dword ptr [r14+8], 1
0x18000824e  jnz     short loc_180008256
0x180008250  or      eax, 8
0x180008253  mov     [rbx+4], eax
0x180008256  mov     eax, 1
0x18000825b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008263  inc     eax
0x180008265  mov     [rbx+10h], eax
0x180008268  mov     rax, [rsp+78h+arg_40]
0x180008270  xor     edi, edi
0x180008272  test    rax, rax
0x180008275  jz      short loc_18000827C
0x180008277  cmp     [rax], di
0x18000827a  jnz     short loc_18000827F
0x18000827c  mov     rax, rdi
0x18000827f  mov     [rbx+18h], rax
0x180008283  call    cs:__imp_GetCurrentThreadId
0x180008289  mov     [rbx+20h], eax
0x18000828c  mov     [rbx+38h], r13
0x180008290  mov     eax, [rsp+78h+arg_8]
0x180008297  mov     [rbx+40h], eax
0x18000829a  mov     [rbx+44h], ebp
0x18000829d  mov     rax, [rsp+78h+arg_20]
0x1800082a5  mov     [rbx+28h], rax
0x1800082a9  mov     [rbx+30h], r12
0x1800082ad  mov     rax, [rsp+78h+arg_28]
0x1800082b5  mov     [rbx+88h], rax
0x1800082bc  mov     rax, [rsp+78h+arg_0]
0x1800082c4  mov     [rbx+90h], rax
0x1800082cb  mov     [rbx+48h], rdi
0x1800082cf  xorps   xmm0, xmm0
0x1800082d2  xor     eax, eax
0x1800082d4  movups  xmmword ptr [rbx+68h], xmm0
0x1800082d8  mov     [rbx+78h], rax
0x1800082dc  movups  xmmword ptr [rbx+50h], xmm0
0x1800082e0  mov     [rbx+60h], rax
0x1800082e4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800082eb  test    rax, rax
0x1800082ee  jz      short loc_1800082F7
0x1800082f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082f5  jmp     short loc_1800082FA
0x1800082f7  mov     rax, rdi
0x1800082fa  mov     [rbx+80h], rax
0x180008301  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008308  test    rax, rax
0x18000830b  jz      short loc_180008315
0x18000830d  mov     rcx, rbx
0x180008310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008315  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000831c  test    rax, rax
0x18000831f  jz      short loc_180008337
0x180008321  mov     r8d, 400h
0x180008327  mov     rdx, [rsp+78h+arg_60]
0x18000832f  mov     rcx, rbx
0x180008332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008337  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000833e  test    rax, rax
0x180008341  jz      short loc_18000834B
0x180008343  mov     rcx, rbx
0x180008346  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000834b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008352  test    rax, rax
0x180008355  jz      short loc_180008365
0x180008357  test    byte ptr [rbx+4], 2
0x18000835b  jnz     short loc_180008365
0x18000835d  mov     rcx, rbx
0x180008360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008365  cmp     [rbx+8], edi
0x180008368  jl      short loc_180008384
0x18000836a  cmp     r15d, 3
0x18000836e  jnz     loc_180008453
0x180008374  mov     ecx, 8000FFFFh; this
0x180008379  mov     [rbx+8], ecx
0x18000837c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008381  mov     [rbx+0Ch], eax
0x180008384  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000838b  jnz     short loc_1800083AC
0x18000838d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008394  test    rax, rax
0x180008397  jz      short loc_1800083A2
0x180008399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000839e  test    al, al
0x1800083a0  jmp     short loc_1800083AA
0x1800083a2  call    cs:__imp_IsDebuggerPresent
0x1800083a8  test    eax, eax
0x1800083aa  jz      short loc_1800083B2
0x1800083ac  test    byte ptr [rbx+4], 2
0x1800083b0  jz      short loc_1800083D6
0x1800083b2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800083b9  test    rax, rax
0x1800083bc  jz      short loc_18000841A
0x1800083be  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800083c5  jnz     short loc_18000841A
0x1800083c7  xor     r8d, r8d
0x1800083ca  xor     edx, edx
0x1800083cc  mov     rcx, rbx
0x1800083cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083d4  jmp     short loc_18000841A
0x1800083d6  mov     ebp, 800h
0x1800083db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800083e2  test    rax, rax
0x1800083e5  jz      short loc_1800083FE
0x1800083e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800083ee  jnz     short loc_1800083FE
0x1800083f0  mov     r8d, ebp
0x1800083f3  mov     rdx, rsi
0x1800083f6  mov     rcx, rbx
0x1800083f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083fe  cmp     [rsi], di
0x180008401  jnz     short loc_180008411
0x180008403  mov     r8, rbx; unsigned __int64
0x180008406  mov     rdx, rbp; unsigned __int16 *
0x180008409  mov     rcx, rsi; this
0x18000840c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008411  mov     rcx, rsi; lpOutputString
0x180008414  call    cs:__imp_OutputDebugStringW
0x18000841a  test    byte ptr [rbx+4], 4
0x18000841e  jnz     short loc_180008429
0x180008420  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008427  jz      short loc_18000843B
0x180008429  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008430  test    rax, rax
0x180008433  jz      short loc_18000843B
0x180008435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000843a  nop
0x18000843b  mov     rbx, [rsp+78h+arg_10]
0x180008443  add     rsp, 40h
0x180008447  pop     r15
0x180008449  pop     r14
0x18000844b  pop     r13
0x18000844d  pop     r12
0x18000844f  pop     rdi
0x180008450  pop     rsi
0x180008451  pop     rbp
0x180008452  retn
0x180008453  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
