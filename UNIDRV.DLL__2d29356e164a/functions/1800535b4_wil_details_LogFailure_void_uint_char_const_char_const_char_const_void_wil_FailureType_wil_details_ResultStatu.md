# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800535b4`
- end: `0x1800538ac`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180050888`
- `0x180050bd4`

## callees

- `0x18004817c`
- `0x1800507c8`
- `0x1800526e4`
- `0x1800535b4`
- `0x18005473c`
- `0x180054760`
- `0x1800548e4`
- `0x180054900`
- `0x1800563a8`
- `0x180075010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1800537f6`
- `KERNEL32!IsDebuggerPresent` at `0x1800537f6`
- `KERNEL32!OutputDebugStringW` at `0x180053868`
- `KERNEL32!OutputDebugStringW` at `0x180053868`
- `KERNEL32!GetCurrentThreadId` at `0x1800536d7`
- `KERNEL32!GetCurrentThreadId` at `0x1800536d7`

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
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

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
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
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
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
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
0x1800535b4  mov     [rsp+arg_10], rbx
0x1800535b9  mov     [rsp+arg_8], edx
0x1800535bd  mov     [rsp+arg_0], rcx
0x1800535c2  push    rbp
0x1800535c3  push    rsi
0x1800535c4  push    rdi
0x1800535c5  push    r12
0x1800535c7  push    r13
0x1800535c9  push    r14
0x1800535cb  push    r15
0x1800535cd  sub     rsp, 40h
0x1800535d1  mov     r14, [rsp+78h+arg_38]
0x1800535d9  xor     eax, eax
0x1800535db  mov     rbx, [rsp+78h+arg_78]
0x1800535e3  xor     ebp, ebp
0x1800535e5  mov     r15d, [rsp+78h+arg_30]
0x1800535ed  mov     r10, rcx
0x1800535f0  mov     rsi, [rsp+78h+lpOutputString]
0x1800535f8  mov     r12, r9
0x1800535fb  mov     r13, r8
0x1800535fe  mov     ecx, r15d
0x180053601  mov     [rsi], ax
0x180053604  mov     rax, [rsp+78h+arg_60]
0x18005360c  mov     byte ptr [rax], 0
0x18005360f  mov     edi, [r14]
0x180053612  mov     [rbx+8], edi
0x180053615  mov     eax, [r14+4]
0x180053619  mov     [rbx+0Ch], eax
0x18005361c  test    r15d, r15d
0x18005361f  jz      short loc_180053687
0x180053621  sub     ecx, 1
0x180053624  jz      short loc_18005367E
0x180053626  sub     ecx, 1
0x180053629  jz      short loc_180053639
0x18005362b  cmp     ecx, 1
0x18005362e  jnz     short loc_180053690
0x180053630  mov     ecx, edi; this
0x180053632  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180053637  jmp     short loc_18005368E
0x180053639  test    edi, edi
0x18005363b  js      short loc_180053675
0x18005363d  mov     rax, [rsp+78h+arg_28]
0x180053645  mov     edi, 8007029Ch
0x18005364a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18005364e  mov     rcx, r10; int
0x180053651  mov     [rsp+78h+var_50], rax; __int64
0x180053656  mov     rax, [rsp+78h+arg_20]
0x18005365e  mov     [rsp+78h+var_58], rax; __int64
0x180053663  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180053668  mov     ecx, edi; this
0x18005366a  mov     [rbx+8], edi
0x18005366d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180053672  mov     [rbx+0Ch], eax
0x180053675  mov     ecx, edi; this
0x180053677  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18005367c  jmp     short loc_18005368E
0x18005367e  mov     ecx, edi; this
0x180053680  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180053685  jmp     short loc_18005368E
0x180053687  mov     ecx, edi; this
0x180053689  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18005368e  mov     ebp, eax
0x180053690  mov     eax, [rsp+78h+arg_70]
0x180053697  mov     [rbx+4], eax
0x18005369a  mov     [rbx], r15d
0x18005369d  cmp     dword ptr [r14+8], 1
0x1800536a2  jnz     short loc_1800536AA
0x1800536a4  or      eax, 8
0x1800536a7  mov     [rbx+4], eax
0x1800536aa  mov     eax, 1
0x1800536af  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800536b7  inc     eax
0x1800536b9  xor     edi, edi
0x1800536bb  mov     [rbx+10h], eax
0x1800536be  mov     rax, [rsp+78h+arg_40]
0x1800536c6  test    rax, rax
0x1800536c9  jz      short loc_1800536D0
0x1800536cb  cmp     [rax], di
0x1800536ce  jnz     short loc_1800536D3
0x1800536d0  mov     rax, rdi
0x1800536d3  mov     [rbx+18h], rax
0x1800536d7  call    cs:__imp_GetCurrentThreadId
0x1800536dd  mov     [rbx+38h], r13
0x1800536e1  xorps   xmm0, xmm0
0x1800536e4  mov     [rbx+20h], eax
0x1800536e7  mov     eax, [rsp+78h+arg_8]
0x1800536ee  mov     [rbx+40h], eax
0x1800536f1  mov     rax, [rsp+78h+arg_20]
0x1800536f9  mov     [rbx+28h], rax
0x1800536fd  mov     rax, [rsp+78h+arg_28]
0x180053705  mov     [rbx+88h], rax
0x18005370c  mov     rax, [rsp+78h+arg_0]
0x180053714  mov     [rbx+90h], rax
0x18005371b  xor     eax, eax
0x18005371d  mov     [rbx+44h], ebp
0x180053720  mov     [rbx+30h], r12
0x180053724  mov     [rbx+48h], rdi
0x180053728  movups  xmmword ptr [rbx+68h], xmm0
0x18005372c  mov     [rbx+78h], rax
0x180053730  movups  xmmword ptr [rbx+50h], xmm0
0x180053734  mov     [rbx+60h], rax
0x180053738  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18005373f  test    rax, rax
0x180053742  jz      short loc_18005374B
0x180053744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053749  jmp     short loc_18005374E
0x18005374b  mov     rax, rdi
0x18005374e  mov     [rbx+80h], rax
0x180053755  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18005375c  test    rax, rax
0x18005375f  jz      short loc_180053769
0x180053761  mov     rcx, rbx
0x180053764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053769  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180053770  test    rax, rax
0x180053773  jz      short loc_18005378B
0x180053775  mov     rdx, [rsp+78h+arg_60]
0x18005377d  mov     r8d, 400h
0x180053783  mov     rcx, rbx
0x180053786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005378b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180053792  test    rax, rax
0x180053795  jz      short loc_18005379F
0x180053797  mov     rcx, rbx
0x18005379a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005379f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800537a6  test    rax, rax
0x1800537a9  jz      short loc_1800537B9
0x1800537ab  test    byte ptr [rbx+4], 2
0x1800537af  jnz     short loc_1800537B9
0x1800537b1  mov     rcx, rbx
0x1800537b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800537b9  cmp     [rbx+8], edi
0x1800537bc  jl      short loc_1800537D8
0x1800537be  cmp     r15d, 3
0x1800537c2  jnz     loc_1800538A6
0x1800537c8  mov     ecx, 8000FFFFh; this
0x1800537cd  mov     [rbx+8], ecx
0x1800537d0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800537d5  mov     [rbx+0Ch], eax
0x1800537d8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800537df  jnz     short loc_180053800
0x1800537e1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800537e8  test    rax, rax
0x1800537eb  jz      short loc_1800537F6
0x1800537ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800537f2  test    al, al
0x1800537f4  jmp     short loc_1800537FE
0x1800537f6  call    cs:__imp_IsDebuggerPresent
0x1800537fc  test    eax, eax
0x1800537fe  jz      short loc_180053806
0x180053800  test    byte ptr [rbx+4], 2
0x180053804  jz      short loc_18005382A
0x180053806  mov     rax, cs:g_pfnResultLoggingCallback
0x18005380d  test    rax, rax
0x180053810  jz      short loc_18005386E
0x180053812  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180053819  jnz     short loc_18005386E
0x18005381b  xor     r8d, r8d
0x18005381e  xor     edx, edx
0x180053820  mov     rcx, rbx
0x180053823  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053828  jmp     short loc_18005386E
0x18005382a  mov     rax, cs:g_pfnResultLoggingCallback
0x180053831  mov     ebp, 800h
0x180053836  test    rax, rax
0x180053839  jz      short loc_180053852
0x18005383b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180053842  jnz     short loc_180053852
0x180053844  mov     r8d, ebp
0x180053847  mov     rdx, rsi
0x18005384a  mov     rcx, rbx
0x18005384d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053852  cmp     [rsi], di
0x180053855  jnz     short loc_180053865
0x180053857  mov     r8, rbx; unsigned __int64
0x18005385a  mov     rdx, rbp; unsigned __int16 *
0x18005385d  mov     rcx, rsi; this
0x180053860  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180053865  mov     rcx, rsi; lpOutputString
0x180053868  call    cs:__imp_OutputDebugStringW
0x18005386e  test    byte ptr [rbx+4], 4
0x180053872  jnz     short loc_18005387D
0x180053874  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18005387b  jz      short loc_18005388E
0x18005387d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180053884  test    rax, rax
0x180053887  jz      short loc_18005388E
0x180053889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005388e  mov     rbx, [rsp+78h+arg_10]
0x180053896  add     rsp, 40h
0x18005389a  pop     r15
0x18005389c  pop     r14
0x18005389e  pop     r13
0x1800538a0  pop     r12
0x1800538a2  pop     rdi
0x1800538a3  pop     rsi
0x1800538a4  pop     rbp
0x1800538a5  retn
0x1800538a6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
