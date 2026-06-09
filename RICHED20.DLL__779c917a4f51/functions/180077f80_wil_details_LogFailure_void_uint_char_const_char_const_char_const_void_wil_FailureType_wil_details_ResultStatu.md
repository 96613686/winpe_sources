# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180077f80`
- end: `0x180078278`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180075930`

## callees

- `0x18007536c`
- `0x180077204`
- `0x180077ad4`
- `0x180077f80`
- `0x180079168`
- `0x180079190`
- `0x180079314`
- `0x180079330`
- `0x18007ae8c`
- `0x180092010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800780a3`
- `KERNEL32!GetCurrentThreadId` at `0x1800780a3`
- `KERNEL32!IsDebuggerPresent` at `0x1800781c2`
- `KERNEL32!IsDebuggerPresent` at `0x1800781c2`
- `KERNEL32!OutputDebugStringW` at `0x180078234`
- `KERNEL32!OutputDebugStringW` at `0x180078234`

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
0x180077f80  mov     [rsp+arg_10], rbx
0x180077f85  mov     [rsp+arg_8], edx
0x180077f89  mov     [rsp+arg_0], rcx
0x180077f8e  push    rbp
0x180077f8f  push    rsi
0x180077f90  push    rdi
0x180077f91  push    r12
0x180077f93  push    r13
0x180077f95  push    r14
0x180077f97  push    r15
0x180077f99  sub     rsp, 40h
0x180077f9d  mov     r14, [rsp+78h+arg_38]
0x180077fa5  xor     eax, eax
0x180077fa7  mov     rbx, [rsp+78h+arg_78]
0x180077faf  xor     ebp, ebp
0x180077fb1  mov     r15d, [rsp+78h+arg_30]
0x180077fb9  mov     r10, rcx
0x180077fbc  mov     rsi, [rsp+78h+lpOutputString]
0x180077fc4  mov     r12, r9
0x180077fc7  mov     r13, r8
0x180077fca  mov     ecx, r15d
0x180077fcd  mov     [rsi], ax
0x180077fd0  mov     rax, [rsp+78h+arg_60]
0x180077fd8  mov     byte ptr [rax], 0
0x180077fdb  mov     edi, [r14]
0x180077fde  mov     [rbx+8], edi
0x180077fe1  mov     eax, [r14+4]
0x180077fe5  mov     [rbx+0Ch], eax
0x180077fe8  test    r15d, r15d
0x180077feb  jz      short loc_180078053
0x180077fed  sub     ecx, 1
0x180077ff0  jz      short loc_18007804A
0x180077ff2  sub     ecx, 1
0x180077ff5  jz      short loc_180078005
0x180077ff7  cmp     ecx, 1
0x180077ffa  jnz     short loc_18007805C
0x180077ffc  mov     ecx, edi; this
0x180077ffe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180078003  jmp     short loc_18007805A
0x180078005  test    edi, edi
0x180078007  js      short loc_180078041
0x180078009  mov     rax, [rsp+78h+arg_28]
0x180078011  mov     edi, 8007029Ch
0x180078016  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18007801a  mov     rcx, r10; int
0x18007801d  mov     [rsp+78h+var_50], rax; __int64
0x180078022  mov     rax, [rsp+78h+arg_20]
0x18007802a  mov     [rsp+78h+var_58], rax; __int64
0x18007802f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180078034  mov     ecx, edi; this
0x180078036  mov     [rbx+8], edi
0x180078039  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18007803e  mov     [rbx+0Ch], eax
0x180078041  mov     ecx, edi; this
0x180078043  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180078048  jmp     short loc_18007805A
0x18007804a  mov     ecx, edi; this
0x18007804c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180078051  jmp     short loc_18007805A
0x180078053  mov     ecx, edi; this
0x180078055  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18007805a  mov     ebp, eax
0x18007805c  mov     eax, [rsp+78h+arg_70]
0x180078063  mov     [rbx+4], eax
0x180078066  mov     [rbx], r15d
0x180078069  cmp     dword ptr [r14+8], 1
0x18007806e  jnz     short loc_180078076
0x180078070  or      eax, 8
0x180078073  mov     [rbx+4], eax
0x180078076  mov     eax, 1
0x18007807b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180078083  inc     eax
0x180078085  xor     edi, edi
0x180078087  mov     [rbx+10h], eax
0x18007808a  mov     rax, [rsp+78h+arg_40]
0x180078092  test    rax, rax
0x180078095  jz      short loc_18007809C
0x180078097  cmp     [rax], di
0x18007809a  jnz     short loc_18007809F
0x18007809c  mov     rax, rdi
0x18007809f  mov     [rbx+18h], rax
0x1800780a3  call    cs:__imp_GetCurrentThreadId
0x1800780a9  mov     [rbx+38h], r13
0x1800780ad  xorps   xmm0, xmm0
0x1800780b0  mov     [rbx+20h], eax
0x1800780b3  mov     eax, [rsp+78h+arg_8]
0x1800780ba  mov     [rbx+40h], eax
0x1800780bd  mov     rax, [rsp+78h+arg_20]
0x1800780c5  mov     [rbx+28h], rax
0x1800780c9  mov     rax, [rsp+78h+arg_28]
0x1800780d1  mov     [rbx+88h], rax
0x1800780d8  mov     rax, [rsp+78h+arg_0]
0x1800780e0  mov     [rbx+90h], rax
0x1800780e7  xor     eax, eax
0x1800780e9  mov     [rbx+44h], ebp
0x1800780ec  mov     [rbx+30h], r12
0x1800780f0  mov     [rbx+48h], rdi
0x1800780f4  movups  xmmword ptr [rbx+68h], xmm0
0x1800780f8  mov     [rbx+78h], rax
0x1800780fc  movups  xmmword ptr [rbx+50h], xmm0
0x180078100  mov     [rbx+60h], rax
0x180078104  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18007810b  test    rax, rax
0x18007810e  jz      short loc_180078117
0x180078110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078115  jmp     short loc_18007811A
0x180078117  mov     rax, rdi
0x18007811a  mov     [rbx+80h], rax
0x180078121  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180078128  test    rax, rax
0x18007812b  jz      short loc_180078135
0x18007812d  mov     rcx, rbx
0x180078130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078135  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18007813c  test    rax, rax
0x18007813f  jz      short loc_180078157
0x180078141  mov     rdx, [rsp+78h+arg_60]
0x180078149  mov     r8d, 400h
0x18007814f  mov     rcx, rbx
0x180078152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078157  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18007815e  test    rax, rax
0x180078161  jz      short loc_18007816B
0x180078163  mov     rcx, rbx
0x180078166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007816b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180078172  test    rax, rax
0x180078175  jz      short loc_180078185
0x180078177  test    byte ptr [rbx+4], 2
0x18007817b  jnz     short loc_180078185
0x18007817d  mov     rcx, rbx
0x180078180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180078185  cmp     [rbx+8], edi
0x180078188  jl      short loc_1800781A4
0x18007818a  cmp     r15d, 3
0x18007818e  jnz     loc_180078272
0x180078194  mov     ecx, 8000FFFFh; this
0x180078199  mov     [rbx+8], ecx
0x18007819c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800781a1  mov     [rbx+0Ch], eax
0x1800781a4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800781ab  jnz     short loc_1800781CC
0x1800781ad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800781b4  test    rax, rax
0x1800781b7  jz      short loc_1800781C2
0x1800781b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800781be  test    al, al
0x1800781c0  jmp     short loc_1800781CA
0x1800781c2  call    cs:__imp_IsDebuggerPresent
0x1800781c8  test    eax, eax
0x1800781ca  jz      short loc_1800781D2
0x1800781cc  test    byte ptr [rbx+4], 2
0x1800781d0  jz      short loc_1800781F6
0x1800781d2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800781d9  test    rax, rax
0x1800781dc  jz      short loc_18007823A
0x1800781de  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800781e5  jnz     short loc_18007823A
0x1800781e7  xor     r8d, r8d
0x1800781ea  xor     edx, edx
0x1800781ec  mov     rcx, rbx
0x1800781ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800781f4  jmp     short loc_18007823A
0x1800781f6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800781fd  mov     ebp, 800h
0x180078202  test    rax, rax
0x180078205  jz      short loc_18007821E
0x180078207  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18007820e  jnz     short loc_18007821E
0x180078210  mov     r8d, ebp
0x180078213  mov     rdx, rsi
0x180078216  mov     rcx, rbx
0x180078219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007821e  cmp     [rsi], di
0x180078221  jnz     short loc_180078231
0x180078223  mov     r8, rbx; unsigned __int64
0x180078226  mov     rdx, rbp; unsigned __int16 *
0x180078229  mov     rcx, rsi; this
0x18007822c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180078231  mov     rcx, rsi; lpOutputString
0x180078234  call    cs:__imp_OutputDebugStringW
0x18007823a  test    byte ptr [rbx+4], 4
0x18007823e  jnz     short loc_180078249
0x180078240  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180078247  jz      short loc_18007825A
0x180078249  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180078250  test    rax, rax
0x180078253  jz      short loc_18007825A
0x180078255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007825a  mov     rbx, [rsp+78h+arg_10]
0x180078262  add     rsp, 40h
0x180078266  pop     r15
0x180078268  pop     r14
0x18007826a  pop     r13
0x18007826c  pop     r12
0x18007826e  pop     rdi
0x18007826f  pop     rsi
0x180078270  pop     rbp
0x180078271  retn
0x180078272  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
