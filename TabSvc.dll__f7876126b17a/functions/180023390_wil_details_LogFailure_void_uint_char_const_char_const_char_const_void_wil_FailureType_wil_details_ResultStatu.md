# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180023390`
- end: `0x180023685`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18001d9dc`
- `0x18001da9c`
- `0x18001dba4`
- `0x18001dc94`

## callees

- `0x18001b4b0`
- `0x18001d7a8`
- `0x180022584`
- `0x180023390`
- `0x180024aa0`
- `0x180024ac0`
- `0x180024ad4`
- `0x180024af0`
- `0x180028520`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800234b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800234b3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800235d4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800235d4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180023646`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180023646`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v25)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0, v23);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v23);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
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
0x180023390  mov     [rsp+arg_10], rbx
0x180023395  mov     [rsp+arg_8], edx
0x180023399  mov     [rsp+arg_0], rcx
0x18002339e  push    rbp
0x18002339f  push    rsi
0x1800233a0  push    rdi
0x1800233a1  push    r12
0x1800233a3  push    r13
0x1800233a5  push    r14
0x1800233a7  push    r15
0x1800233a9  sub     rsp, 40h
0x1800233ad  mov     r12, r9
0x1800233b0  mov     r13, r8
0x1800233b3  mov     r10, rcx
0x1800233b6  xor     eax, eax
0x1800233b8  mov     rsi, [rsp+78h+lpOutputString]
0x1800233c0  mov     [rsi], ax
0x1800233c3  mov     rax, [rsp+78h+arg_60]
0x1800233cb  mov     byte ptr [rax], 0
0x1800233ce  mov     r14, [rsp+78h+arg_38]
0x1800233d6  mov     edi, [r14]
0x1800233d9  mov     rbx, [rsp+78h+arg_78]
0x1800233e1  mov     [rbx+8], edi
0x1800233e4  mov     eax, [r14+4]
0x1800233e8  mov     [rbx+0Ch], eax
0x1800233eb  xor     ebp, ebp
0x1800233ed  mov     r15d, [rsp+78h+arg_30]
0x1800233f5  mov     ecx, r15d
0x1800233f8  test    r15d, r15d
0x1800233fb  jz      short loc_180023463
0x1800233fd  sub     ecx, 1
0x180023400  jz      short loc_18002345A
0x180023402  sub     ecx, 1
0x180023405  jz      short loc_180023415
0x180023407  cmp     ecx, 1
0x18002340a  jnz     short loc_18002346C
0x18002340c  mov     ecx, edi; this
0x18002340e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180023413  jmp     short loc_18002346A
0x180023415  test    edi, edi
0x180023417  js      short loc_180023451
0x180023419  mov     edi, 8007029Ch
0x18002341e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180023422  mov     rax, [rsp+78h+arg_28]
0x18002342a  mov     [rsp+78h+var_50], rax; __int64
0x18002342f  mov     rax, [rsp+78h+arg_20]
0x180023437  mov     [rsp+78h+var_58], rax; __int64
0x18002343c  mov     rcx, r10; int
0x18002343f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180023444  mov     [rbx+8], edi
0x180023447  mov     ecx, edi; this
0x180023449  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002344e  mov     [rbx+0Ch], eax
0x180023451  mov     ecx, edi; this
0x180023453  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180023458  jmp     short loc_18002346A
0x18002345a  mov     ecx, edi; this
0x18002345c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180023461  jmp     short loc_18002346A
0x180023463  mov     ecx, edi; this
0x180023465  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002346a  mov     ebp, eax
0x18002346c  mov     [rbx], r15d
0x18002346f  mov     eax, [rsp+78h+arg_70]
0x180023476  mov     [rbx+4], eax
0x180023479  cmp     dword ptr [r14+8], 1
0x18002347e  jnz     short loc_180023486
0x180023480  or      eax, 8
0x180023483  mov     [rbx+4], eax
0x180023486  mov     eax, 1
0x18002348b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180023493  inc     eax
0x180023495  mov     [rbx+10h], eax
0x180023498  mov     rax, [rsp+78h+arg_40]
0x1800234a0  xor     edi, edi
0x1800234a2  test    rax, rax
0x1800234a5  jz      short loc_1800234AC
0x1800234a7  cmp     [rax], di
0x1800234aa  jnz     short loc_1800234AF
0x1800234ac  mov     rax, rdi
0x1800234af  mov     [rbx+18h], rax
0x1800234b3  call    cs:__imp_GetCurrentThreadId
0x1800234b9  mov     [rbx+20h], eax
0x1800234bc  mov     [rbx+38h], r13
0x1800234c0  mov     eax, [rsp+78h+arg_8]
0x1800234c7  mov     [rbx+40h], eax
0x1800234ca  mov     [rbx+44h], ebp
0x1800234cd  mov     rax, [rsp+78h+arg_20]
0x1800234d5  mov     [rbx+28h], rax
0x1800234d9  mov     [rbx+30h], r12
0x1800234dd  mov     rax, [rsp+78h+arg_28]
0x1800234e5  mov     [rbx+88h], rax
0x1800234ec  mov     rax, [rsp+78h+arg_0]
0x1800234f4  mov     [rbx+90h], rax
0x1800234fb  mov     [rbx+48h], rdi
0x1800234ff  xorps   xmm0, xmm0
0x180023502  xor     eax, eax
0x180023504  movups  xmmword ptr [rbx+68h], xmm0
0x180023508  mov     [rbx+78h], rax
0x18002350c  movups  xmmword ptr [rbx+50h], xmm0
0x180023510  mov     [rbx+60h], rax
0x180023514  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002351b  test    rax, rax
0x18002351e  jz      short loc_180023527
0x180023520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023525  jmp     short loc_18002352A
0x180023527  mov     rax, rdi
0x18002352a  mov     [rbx+80h], rax
0x180023531  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180023538  test    rax, rax
0x18002353b  jz      short loc_180023545
0x18002353d  mov     rcx, rbx
0x180023540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023545  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002354c  test    rax, rax
0x18002354f  jz      short loc_180023567
0x180023551  mov     r8d, 400h
0x180023557  mov     rdx, [rsp+78h+arg_60]
0x18002355f  mov     rcx, rbx
0x180023562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023567  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002356e  test    rax, rax
0x180023571  jz      short loc_18002357B
0x180023573  mov     rcx, rbx
0x180023576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002357b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180023582  test    rax, rax
0x180023585  jz      short loc_180023595
0x180023587  test    byte ptr [rbx+4], 2
0x18002358b  jnz     short loc_180023595
0x18002358d  mov     rcx, rbx
0x180023590  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023595  cmp     [rbx+8], edi
0x180023598  jl      short loc_1800235B6
0x18002359a  cmp     r15d, 3
0x18002359e  jz      short loc_1800235A6
0x1800235a0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800235a6  mov     ecx, 8000FFFFh; this
0x1800235ab  mov     [rbx+8], ecx
0x1800235ae  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800235b3  mov     [rbx+0Ch], eax
0x1800235b6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800235bd  jnz     short loc_1800235DE
0x1800235bf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800235c6  test    rax, rax
0x1800235c9  jz      short loc_1800235D4
0x1800235cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800235d0  test    al, al
0x1800235d2  jmp     short loc_1800235DC
0x1800235d4  call    cs:__imp_IsDebuggerPresent
0x1800235da  test    eax, eax
0x1800235dc  jz      short loc_1800235E4
0x1800235de  test    byte ptr [rbx+4], 2
0x1800235e2  jz      short loc_180023608
0x1800235e4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800235eb  test    rax, rax
0x1800235ee  jz      short loc_18002364C
0x1800235f0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800235f7  jnz     short loc_18002364C
0x1800235f9  xor     r8d, r8d
0x1800235fc  xor     edx, edx
0x1800235fe  mov     rcx, rbx
0x180023601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023606  jmp     short loc_18002364C
0x180023608  mov     ebp, 800h
0x18002360d  mov     rax, cs:g_pfnResultLoggingCallback
0x180023614  test    rax, rax
0x180023617  jz      short loc_180023630
0x180023619  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180023620  jnz     short loc_180023630
0x180023622  mov     r8d, ebp
0x180023625  mov     rdx, rsi
0x180023628  mov     rcx, rbx
0x18002362b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023630  cmp     [rsi], di
0x180023633  jnz     short loc_180023643
0x180023635  mov     r8, rbx; unsigned __int64
0x180023638  mov     rdx, rbp; unsigned __int16 *
0x18002363b  mov     rcx, rsi; this
0x18002363e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180023643  mov     rcx, rsi; lpOutputString
0x180023646  call    cs:__imp_OutputDebugStringW
0x18002364c  test    byte ptr [rbx+4], 4
0x180023650  jnz     short loc_18002365B
0x180023652  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180023659  jz      short loc_18002366D
0x18002365b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180023662  test    rax, rax
0x180023665  jz      short loc_18002366D
0x180023667  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002366c  nop
0x18002366d  mov     rbx, [rsp+78h+arg_10]
0x180023675  add     rsp, 40h
0x180023679  pop     r15
0x18002367b  pop     r14
0x18002367d  pop     r13
0x18002367f  pop     r12
0x180023681  pop     rdi
0x180023682  pop     rsi
0x180023683  pop     rbp
0x180023684  retn
```
