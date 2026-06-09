# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800073a0`
- end: `0x180007695`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180003b48`
- `0x180003c08`
- `0x180003d04`
- `0x18000dd3c`

## callees

- `0x180003a90`
- `0x180006674`
- `0x180006f24`
- `0x1800073a0`
- `0x18000852c`
- `0x180008550`
- `0x1800086d4`
- `0x1800086f0`
- `0x18000ae60`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800074c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800074c3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800075e4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800075e4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007656`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007656`

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
0x1800073a0  mov     [rsp+arg_10], rbx
0x1800073a5  mov     [rsp+arg_8], edx
0x1800073a9  mov     [rsp+arg_0], rcx
0x1800073ae  push    rbp
0x1800073af  push    rsi
0x1800073b0  push    rdi
0x1800073b1  push    r12
0x1800073b3  push    r13
0x1800073b5  push    r14
0x1800073b7  push    r15
0x1800073b9  sub     rsp, 40h
0x1800073bd  mov     r12, r9
0x1800073c0  mov     r13, r8
0x1800073c3  mov     r10, rcx
0x1800073c6  xor     eax, eax
0x1800073c8  mov     rsi, [rsp+78h+lpOutputString]
0x1800073d0  mov     [rsi], ax
0x1800073d3  mov     rax, [rsp+78h+arg_60]
0x1800073db  mov     byte ptr [rax], 0
0x1800073de  mov     r14, [rsp+78h+arg_38]
0x1800073e6  mov     edi, [r14]
0x1800073e9  mov     rbx, [rsp+78h+arg_78]
0x1800073f1  mov     [rbx+8], edi
0x1800073f4  mov     eax, [r14+4]
0x1800073f8  mov     [rbx+0Ch], eax
0x1800073fb  xor     ebp, ebp
0x1800073fd  mov     r15d, [rsp+78h+arg_30]
0x180007405  mov     ecx, r15d
0x180007408  test    r15d, r15d
0x18000740b  jz      short loc_180007473
0x18000740d  sub     ecx, 1
0x180007410  jz      short loc_18000746A
0x180007412  sub     ecx, 1
0x180007415  jz      short loc_180007425
0x180007417  cmp     ecx, 1
0x18000741a  jnz     short loc_18000747C
0x18000741c  mov     ecx, edi; this
0x18000741e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007423  jmp     short loc_18000747A
0x180007425  test    edi, edi
0x180007427  js      short loc_180007461
0x180007429  mov     edi, 8007029Ch
0x18000742e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007432  mov     rax, [rsp+78h+arg_28]
0x18000743a  mov     [rsp+78h+var_50], rax; __int64
0x18000743f  mov     rax, [rsp+78h+arg_20]
0x180007447  mov     [rsp+78h+var_58], rax; __int64
0x18000744c  mov     rcx, r10; int
0x18000744f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007454  mov     [rbx+8], edi
0x180007457  mov     ecx, edi; this
0x180007459  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000745e  mov     [rbx+0Ch], eax
0x180007461  mov     ecx, edi; this
0x180007463  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007468  jmp     short loc_18000747A
0x18000746a  mov     ecx, edi; this
0x18000746c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007471  jmp     short loc_18000747A
0x180007473  mov     ecx, edi; this
0x180007475  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000747a  mov     ebp, eax
0x18000747c  mov     [rbx], r15d
0x18000747f  mov     eax, [rsp+78h+arg_70]
0x180007486  mov     [rbx+4], eax
0x180007489  cmp     dword ptr [r14+8], 1
0x18000748e  jnz     short loc_180007496
0x180007490  or      eax, 8
0x180007493  mov     [rbx+4], eax
0x180007496  mov     eax, 1
0x18000749b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800074a3  inc     eax
0x1800074a5  mov     [rbx+10h], eax
0x1800074a8  mov     rax, [rsp+78h+arg_40]
0x1800074b0  xor     edi, edi
0x1800074b2  test    rax, rax
0x1800074b5  jz      short loc_1800074BC
0x1800074b7  cmp     [rax], di
0x1800074ba  jnz     short loc_1800074BF
0x1800074bc  mov     rax, rdi
0x1800074bf  mov     [rbx+18h], rax
0x1800074c3  call    cs:__imp_GetCurrentThreadId
0x1800074c9  mov     [rbx+20h], eax
0x1800074cc  mov     [rbx+38h], r13
0x1800074d0  mov     eax, [rsp+78h+arg_8]
0x1800074d7  mov     [rbx+40h], eax
0x1800074da  mov     [rbx+44h], ebp
0x1800074dd  mov     rax, [rsp+78h+arg_20]
0x1800074e5  mov     [rbx+28h], rax
0x1800074e9  mov     [rbx+30h], r12
0x1800074ed  mov     rax, [rsp+78h+arg_28]
0x1800074f5  mov     [rbx+88h], rax
0x1800074fc  mov     rax, [rsp+78h+arg_0]
0x180007504  mov     [rbx+90h], rax
0x18000750b  mov     [rbx+48h], rdi
0x18000750f  xorps   xmm0, xmm0
0x180007512  xor     eax, eax
0x180007514  movups  xmmword ptr [rbx+68h], xmm0
0x180007518  mov     [rbx+78h], rax
0x18000751c  movups  xmmword ptr [rbx+50h], xmm0
0x180007520  mov     [rbx+60h], rax
0x180007524  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000752b  test    rax, rax
0x18000752e  jz      short loc_180007537
0x180007530  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007535  jmp     short loc_18000753A
0x180007537  mov     rax, rdi
0x18000753a  mov     [rbx+80h], rax
0x180007541  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007548  test    rax, rax
0x18000754b  jz      short loc_180007555
0x18000754d  mov     rcx, rbx
0x180007550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007555  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000755c  test    rax, rax
0x18000755f  jz      short loc_180007577
0x180007561  mov     r8d, 400h
0x180007567  mov     rdx, [rsp+78h+arg_60]
0x18000756f  mov     rcx, rbx
0x180007572  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007577  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000757e  test    rax, rax
0x180007581  jz      short loc_18000758B
0x180007583  mov     rcx, rbx
0x180007586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000758b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007592  test    rax, rax
0x180007595  jz      short loc_1800075A5
0x180007597  test    byte ptr [rbx+4], 2
0x18000759b  jnz     short loc_1800075A5
0x18000759d  mov     rcx, rbx
0x1800075a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075a5  cmp     [rbx+8], edi
0x1800075a8  jl      short loc_1800075C6
0x1800075aa  cmp     r15d, 3
0x1800075ae  jz      short loc_1800075B6
0x1800075b0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800075b6  mov     ecx, 8000FFFFh; this
0x1800075bb  mov     [rbx+8], ecx
0x1800075be  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800075c3  mov     [rbx+0Ch], eax
0x1800075c6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800075cd  jnz     short loc_1800075EE
0x1800075cf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800075d6  test    rax, rax
0x1800075d9  jz      short loc_1800075E4
0x1800075db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075e0  test    al, al
0x1800075e2  jmp     short loc_1800075EC
0x1800075e4  call    cs:__imp_IsDebuggerPresent
0x1800075ea  test    eax, eax
0x1800075ec  jz      short loc_1800075F4
0x1800075ee  test    byte ptr [rbx+4], 2
0x1800075f2  jz      short loc_180007618
0x1800075f4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800075fb  test    rax, rax
0x1800075fe  jz      short loc_18000765C
0x180007600  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007607  jnz     short loc_18000765C
0x180007609  xor     r8d, r8d
0x18000760c  xor     edx, edx
0x18000760e  mov     rcx, rbx
0x180007611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007616  jmp     short loc_18000765C
0x180007618  mov     ebp, 800h
0x18000761d  mov     rax, cs:g_pfnResultLoggingCallback
0x180007624  test    rax, rax
0x180007627  jz      short loc_180007640
0x180007629  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007630  jnz     short loc_180007640
0x180007632  mov     r8d, ebp
0x180007635  mov     rdx, rsi
0x180007638  mov     rcx, rbx
0x18000763b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007640  cmp     [rsi], di
0x180007643  jnz     short loc_180007653
0x180007645  mov     r8, rbx; unsigned __int64
0x180007648  mov     rdx, rbp; unsigned __int16 *
0x18000764b  mov     rcx, rsi; this
0x18000764e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007653  mov     rcx, rsi; lpOutputString
0x180007656  call    cs:__imp_OutputDebugStringW
0x18000765c  test    byte ptr [rbx+4], 4
0x180007660  jnz     short loc_18000766B
0x180007662  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007669  jz      short loc_18000767D
0x18000766b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007672  test    rax, rax
0x180007675  jz      short loc_18000767D
0x180007677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000767c  nop
0x18000767d  mov     rbx, [rsp+78h+arg_10]
0x180007685  add     rsp, 40h
0x180007689  pop     r15
0x18000768b  pop     r14
0x18000768d  pop     r13
0x18000768f  pop     r12
0x180007691  pop     rdi
0x180007692  pop     rsi
0x180007693  pop     rbp
0x180007694  retn
```
