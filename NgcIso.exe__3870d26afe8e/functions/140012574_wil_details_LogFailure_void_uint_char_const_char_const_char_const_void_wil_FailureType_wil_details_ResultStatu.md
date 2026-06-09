# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140012574`
- end: `0x140012869`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x140010ce8`
- `0x140010da8`
- `0x140010ea4`
- `0x140015dc4`

## callees

- `0x14000e2d4`
- `0x140010c2c`
- `0x140011cf4`
- `0x140012574`
- `0x1400132c8`
- `0x1400132f0`
- `0x1400133ac`
- `0x1400133c8`
- `0x140014e00`
- `0x140071010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400127b8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400127b8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14001282a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14001282a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012697`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140012697`

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
0x140012574  mov     [rsp+arg_10], rbx
0x140012579  mov     [rsp+arg_8], edx
0x14001257d  mov     [rsp+arg_0], rcx
0x140012582  push    rbp
0x140012583  push    rsi
0x140012584  push    rdi
0x140012585  push    r12
0x140012587  push    r13
0x140012589  push    r14
0x14001258b  push    r15
0x14001258d  sub     rsp, 40h
0x140012591  mov     r12, r9
0x140012594  mov     r13, r8
0x140012597  mov     r10, rcx
0x14001259a  xor     eax, eax
0x14001259c  mov     rsi, [rsp+78h+lpOutputString]
0x1400125a4  mov     [rsi], ax
0x1400125a7  mov     rax, [rsp+78h+arg_60]
0x1400125af  mov     byte ptr [rax], 0
0x1400125b2  mov     r14, [rsp+78h+arg_38]
0x1400125ba  mov     edi, [r14]
0x1400125bd  mov     rbx, [rsp+78h+arg_78]
0x1400125c5  mov     [rbx+8], edi
0x1400125c8  mov     eax, [r14+4]
0x1400125cc  mov     [rbx+0Ch], eax
0x1400125cf  xor     ebp, ebp
0x1400125d1  mov     r15d, [rsp+78h+arg_30]
0x1400125d9  mov     ecx, r15d
0x1400125dc  test    r15d, r15d
0x1400125df  jz      short loc_140012647
0x1400125e1  sub     ecx, 1
0x1400125e4  jz      short loc_14001263E
0x1400125e6  sub     ecx, 1
0x1400125e9  jz      short loc_1400125F9
0x1400125eb  cmp     ecx, 1
0x1400125ee  jnz     short loc_140012650
0x1400125f0  mov     ecx, edi; this
0x1400125f2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400125f7  jmp     short loc_14001264E
0x1400125f9  test    edi, edi
0x1400125fb  js      short loc_140012635
0x1400125fd  mov     edi, 8007029Ch
0x140012602  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140012606  mov     rax, [rsp+78h+arg_28]
0x14001260e  mov     [rsp+78h+var_50], rax; __int64
0x140012613  mov     rax, [rsp+78h+arg_20]
0x14001261b  mov     [rsp+78h+var_58], rax; __int64
0x140012620  mov     rcx, r10; int
0x140012623  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140012628  mov     [rbx+8], edi
0x14001262b  mov     ecx, edi; this
0x14001262d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140012632  mov     [rbx+0Ch], eax
0x140012635  mov     ecx, edi; this
0x140012637  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14001263c  jmp     short loc_14001264E
0x14001263e  mov     ecx, edi; this
0x140012640  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140012645  jmp     short loc_14001264E
0x140012647  mov     ecx, edi; this
0x140012649  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14001264e  mov     ebp, eax
0x140012650  mov     [rbx], r15d
0x140012653  mov     eax, [rsp+78h+arg_70]
0x14001265a  mov     [rbx+4], eax
0x14001265d  cmp     dword ptr [r14+8], 1
0x140012662  jnz     short loc_14001266A
0x140012664  or      eax, 8
0x140012667  mov     [rbx+4], eax
0x14001266a  mov     eax, 1
0x14001266f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140012677  inc     eax
0x140012679  mov     [rbx+10h], eax
0x14001267c  mov     rax, [rsp+78h+arg_40]
0x140012684  xor     edi, edi
0x140012686  test    rax, rax
0x140012689  jz      short loc_140012690
0x14001268b  cmp     [rax], di
0x14001268e  jnz     short loc_140012693
0x140012690  mov     rax, rdi
0x140012693  mov     [rbx+18h], rax
0x140012697  call    cs:__imp_GetCurrentThreadId
0x14001269d  mov     [rbx+20h], eax
0x1400126a0  mov     [rbx+38h], r13
0x1400126a4  mov     eax, [rsp+78h+arg_8]
0x1400126ab  mov     [rbx+40h], eax
0x1400126ae  mov     [rbx+44h], ebp
0x1400126b1  mov     rax, [rsp+78h+arg_20]
0x1400126b9  mov     [rbx+28h], rax
0x1400126bd  mov     [rbx+30h], r12
0x1400126c1  mov     rax, [rsp+78h+arg_28]
0x1400126c9  mov     [rbx+88h], rax
0x1400126d0  mov     rax, [rsp+78h+arg_0]
0x1400126d8  mov     [rbx+90h], rax
0x1400126df  mov     [rbx+48h], rdi
0x1400126e3  xorps   xmm0, xmm0
0x1400126e6  xor     eax, eax
0x1400126e8  movups  xmmword ptr [rbx+68h], xmm0
0x1400126ec  mov     [rbx+78h], rax
0x1400126f0  movups  xmmword ptr [rbx+50h], xmm0
0x1400126f4  mov     [rbx+60h], rax
0x1400126f8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400126ff  test    rax, rax
0x140012702  jz      short loc_14001270B
0x140012704  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012709  jmp     short loc_14001270E
0x14001270b  mov     rax, rdi
0x14001270e  mov     [rbx+80h], rax
0x140012715  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14001271c  test    rax, rax
0x14001271f  jz      short loc_140012729
0x140012721  mov     rcx, rbx
0x140012724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012729  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140012730  test    rax, rax
0x140012733  jz      short loc_14001274B
0x140012735  mov     r8d, 400h
0x14001273b  mov     rdx, [rsp+78h+arg_60]
0x140012743  mov     rcx, rbx
0x140012746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001274b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140012752  test    rax, rax
0x140012755  jz      short loc_14001275F
0x140012757  mov     rcx, rbx
0x14001275a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001275f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140012766  test    rax, rax
0x140012769  jz      short loc_140012779
0x14001276b  test    byte ptr [rbx+4], 2
0x14001276f  jnz     short loc_140012779
0x140012771  mov     rcx, rbx
0x140012774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012779  cmp     [rbx+8], edi
0x14001277c  jl      short loc_14001279A
0x14001277e  cmp     r15d, 3
0x140012782  jz      short loc_14001278A
0x140012784  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14001278a  mov     ecx, 8000FFFFh; this
0x14001278f  mov     [rbx+8], ecx
0x140012792  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140012797  mov     [rbx+0Ch], eax
0x14001279a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400127a1  jnz     short loc_1400127C2
0x1400127a3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400127aa  test    rax, rax
0x1400127ad  jz      short loc_1400127B8
0x1400127af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400127b4  test    al, al
0x1400127b6  jmp     short loc_1400127C0
0x1400127b8  call    cs:__imp_IsDebuggerPresent
0x1400127be  test    eax, eax
0x1400127c0  jz      short loc_1400127C8
0x1400127c2  test    byte ptr [rbx+4], 2
0x1400127c6  jz      short loc_1400127EC
0x1400127c8  mov     rax, cs:g_pfnResultLoggingCallback
0x1400127cf  test    rax, rax
0x1400127d2  jz      short loc_140012830
0x1400127d4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400127db  jnz     short loc_140012830
0x1400127dd  xor     r8d, r8d
0x1400127e0  xor     edx, edx
0x1400127e2  mov     rcx, rbx
0x1400127e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400127ea  jmp     short loc_140012830
0x1400127ec  mov     ebp, 800h
0x1400127f1  mov     rax, cs:g_pfnResultLoggingCallback
0x1400127f8  test    rax, rax
0x1400127fb  jz      short loc_140012814
0x1400127fd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140012804  jnz     short loc_140012814
0x140012806  mov     r8d, ebp
0x140012809  mov     rdx, rsi
0x14001280c  mov     rcx, rbx
0x14001280f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012814  cmp     [rsi], di
0x140012817  jnz     short loc_140012827
0x140012819  mov     r8, rbx; unsigned __int64
0x14001281c  mov     rdx, rbp; unsigned __int16 *
0x14001281f  mov     rcx, rsi; this
0x140012822  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140012827  mov     rcx, rsi; lpOutputString
0x14001282a  call    cs:__imp_OutputDebugStringW
0x140012830  test    byte ptr [rbx+4], 4
0x140012834  jnz     short loc_14001283F
0x140012836  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14001283d  jz      short loc_140012851
0x14001283f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140012846  test    rax, rax
0x140012849  jz      short loc_140012851
0x14001284b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012850  nop
0x140012851  mov     rbx, [rsp+78h+arg_10]
0x140012859  add     rsp, 40h
0x14001285d  pop     r15
0x14001285f  pop     r14
0x140012861  pop     r13
0x140012863  pop     r12
0x140012865  pop     rdi
0x140012866  pop     rsi
0x140012867  pop     rbp
0x140012868  retn
```
