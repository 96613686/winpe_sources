# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004464`
- end: `0x18000475d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002bc4`

## callees

- `0x1800025e0`
- `0x180003b04`
- `0x1800042a0`
- `0x180004464`
- `0x1800049e4`
- `0x180004a00`
- `0x180004a14`
- `0x180004a30`
- `0x180005b4c`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004587`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004587`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800046a6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800046a6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004718`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004718`

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
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
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
0x180004464  mov     [rsp+arg_10], rbx
0x180004469  mov     [rsp+arg_8], edx
0x18000446d  mov     [rsp+arg_0], rcx
0x180004472  push    rbp
0x180004473  push    rsi
0x180004474  push    rdi
0x180004475  push    r12
0x180004477  push    r13
0x180004479  push    r14
0x18000447b  push    r15
0x18000447d  sub     rsp, 40h
0x180004481  mov     r12, r9
0x180004484  mov     r13, r8
0x180004487  mov     r10, rcx
0x18000448a  xor     eax, eax
0x18000448c  mov     rsi, [rsp+78h+lpOutputString]
0x180004494  mov     [rsi], ax
0x180004497  mov     rax, [rsp+78h+arg_60]
0x18000449f  mov     byte ptr [rax], 0
0x1800044a2  mov     r14, [rsp+78h+arg_38]
0x1800044aa  mov     edi, [r14]
0x1800044ad  mov     rbx, [rsp+78h+arg_78]
0x1800044b5  mov     [rbx+8], edi
0x1800044b8  mov     eax, [r14+4]
0x1800044bc  mov     [rbx+0Ch], eax
0x1800044bf  xor     ebp, ebp
0x1800044c1  mov     r15d, [rsp+78h+arg_30]
0x1800044c9  mov     ecx, r15d
0x1800044cc  test    r15d, r15d
0x1800044cf  jz      short loc_180004537
0x1800044d1  sub     ecx, 1
0x1800044d4  jz      short loc_18000452E
0x1800044d6  sub     ecx, 1
0x1800044d9  jz      short loc_1800044E9
0x1800044db  cmp     ecx, 1
0x1800044de  jnz     short loc_180004540
0x1800044e0  mov     ecx, edi; this
0x1800044e2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800044e7  jmp     short loc_18000453E
0x1800044e9  test    edi, edi
0x1800044eb  js      short loc_180004525
0x1800044ed  mov     edi, 8007029Ch
0x1800044f2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800044f6  mov     rax, [rsp+78h+arg_28]
0x1800044fe  mov     [rsp+78h+var_50], rax; __int64
0x180004503  mov     rax, [rsp+78h+arg_20]
0x18000450b  mov     [rsp+78h+var_58], rax; __int64
0x180004510  mov     rcx, r10; int
0x180004513  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004518  mov     [rbx+8], edi
0x18000451b  mov     ecx, edi; this
0x18000451d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004522  mov     [rbx+0Ch], eax
0x180004525  mov     ecx, edi; this
0x180004527  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000452c  jmp     short loc_18000453E
0x18000452e  mov     ecx, edi; this
0x180004530  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004535  jmp     short loc_18000453E
0x180004537  mov     ecx, edi; this
0x180004539  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000453e  mov     ebp, eax
0x180004540  mov     [rbx], r15d
0x180004543  mov     eax, [rsp+78h+arg_70]
0x18000454a  mov     [rbx+4], eax
0x18000454d  cmp     dword ptr [r14+8], 1
0x180004552  jnz     short loc_18000455A
0x180004554  or      eax, 8
0x180004557  mov     [rbx+4], eax
0x18000455a  mov     eax, 1
0x18000455f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004567  inc     eax
0x180004569  mov     [rbx+10h], eax
0x18000456c  mov     rax, [rsp+78h+arg_40]
0x180004574  xor     edi, edi
0x180004576  test    rax, rax
0x180004579  jz      short loc_180004580
0x18000457b  cmp     [rax], di
0x18000457e  jnz     short loc_180004583
0x180004580  mov     rax, rdi
0x180004583  mov     [rbx+18h], rax
0x180004587  call    cs:__imp_GetCurrentThreadId
0x18000458d  mov     [rbx+20h], eax
0x180004590  mov     [rbx+38h], r13
0x180004594  mov     eax, [rsp+78h+arg_8]
0x18000459b  mov     [rbx+40h], eax
0x18000459e  mov     [rbx+44h], ebp
0x1800045a1  mov     rax, [rsp+78h+arg_20]
0x1800045a9  mov     [rbx+28h], rax
0x1800045ad  mov     [rbx+30h], r12
0x1800045b1  mov     rax, [rsp+78h+arg_28]
0x1800045b9  mov     [rbx+88h], rax
0x1800045c0  mov     rax, [rsp+78h+arg_0]
0x1800045c8  mov     [rbx+90h], rax
0x1800045cf  mov     [rbx+48h], rdi
0x1800045d3  xorps   xmm0, xmm0
0x1800045d6  xor     eax, eax
0x1800045d8  movups  xmmword ptr [rbx+68h], xmm0
0x1800045dc  mov     [rbx+78h], rax
0x1800045e0  movups  xmmword ptr [rbx+50h], xmm0
0x1800045e4  mov     [rbx+60h], rax
0x1800045e8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800045ef  test    rax, rax
0x1800045f2  jz      short loc_1800045FB
0x1800045f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045f9  jmp     short loc_1800045FE
0x1800045fb  mov     rax, rdi
0x1800045fe  mov     [rbx+80h], rax
0x180004605  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000460c  test    rax, rax
0x18000460f  jz      short loc_180004619
0x180004611  mov     rcx, rbx
0x180004614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004619  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004620  test    rax, rax
0x180004623  jz      short loc_18000463B
0x180004625  mov     r8d, 400h
0x18000462b  mov     rdx, [rsp+78h+arg_60]
0x180004633  mov     rcx, rbx
0x180004636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000463b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004642  test    rax, rax
0x180004645  jz      short loc_18000464F
0x180004647  mov     rcx, rbx
0x18000464a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000464f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004656  test    rax, rax
0x180004659  jz      short loc_180004669
0x18000465b  test    byte ptr [rbx+4], 2
0x18000465f  jnz     short loc_180004669
0x180004661  mov     rcx, rbx
0x180004664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004669  cmp     [rbx+8], edi
0x18000466c  jl      short loc_180004688
0x18000466e  cmp     r15d, 3
0x180004672  jnz     loc_180004757
0x180004678  mov     ecx, 8000FFFFh; this
0x18000467d  mov     [rbx+8], ecx
0x180004680  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004685  mov     [rbx+0Ch], eax
0x180004688  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000468f  jnz     short loc_1800046B0
0x180004691  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004698  test    rax, rax
0x18000469b  jz      short loc_1800046A6
0x18000469d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046a2  test    al, al
0x1800046a4  jmp     short loc_1800046AE
0x1800046a6  call    cs:__imp_IsDebuggerPresent
0x1800046ac  test    eax, eax
0x1800046ae  jz      short loc_1800046B6
0x1800046b0  test    byte ptr [rbx+4], 2
0x1800046b4  jz      short loc_1800046DA
0x1800046b6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800046bd  test    rax, rax
0x1800046c0  jz      short loc_18000471E
0x1800046c2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800046c9  jnz     short loc_18000471E
0x1800046cb  xor     r8d, r8d
0x1800046ce  xor     edx, edx
0x1800046d0  mov     rcx, rbx
0x1800046d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046d8  jmp     short loc_18000471E
0x1800046da  mov     ebp, 800h
0x1800046df  mov     rax, cs:g_pfnResultLoggingCallback
0x1800046e6  test    rax, rax
0x1800046e9  jz      short loc_180004702
0x1800046eb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800046f2  jnz     short loc_180004702
0x1800046f4  mov     r8d, ebp
0x1800046f7  mov     rdx, rsi
0x1800046fa  mov     rcx, rbx
0x1800046fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004702  cmp     [rsi], di
0x180004705  jnz     short loc_180004715
0x180004707  mov     r8, rbx; unsigned __int64
0x18000470a  mov     rdx, rbp; unsigned __int16 *
0x18000470d  mov     rcx, rsi; this
0x180004710  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004715  mov     rcx, rsi; lpOutputString
0x180004718  call    cs:__imp_OutputDebugStringW
0x18000471e  test    byte ptr [rbx+4], 4
0x180004722  jnz     short loc_18000472D
0x180004724  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000472b  jz      short loc_18000473F
0x18000472d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004734  test    rax, rax
0x180004737  jz      short loc_18000473F
0x180004739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000473e  nop
0x18000473f  mov     rbx, [rsp+78h+arg_10]
0x180004747  add     rsp, 40h
0x18000474b  pop     r15
0x18000474d  pop     r14
0x18000474f  pop     r13
0x180004751  pop     r12
0x180004753  pop     rdi
0x180004754  pop     rsi
0x180004755  pop     rbp
0x180004756  retn
0x180004757  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
